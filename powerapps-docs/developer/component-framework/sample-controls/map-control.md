---
title: " Kartta-osa | Microsoft Docs"
description: Kartan osan toteuttaminen kulma-JS-toiminnon avulla
ms.custom: ''
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: article
ms.author: nabuthuk
author: Nkrb
ms.openlocfilehash: f4b8702ef39688bdfc5f3ce9a51bf5c8c6e0ff20
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72341330"
---
# <a name="implementing-map-component"></a>Kartan osan toteutus

Tämä malli komponentti muuttaa käyttö kokemusta, joka liittyy lomakkeen osoite kenttien vuoro vaikutukseen. Osoitteen teksti arvojen ohella tämä komponentti antaa mahdollisuuden tunnistaa tietyn osoitteen kartalla ilman, että siirryt toiseen väli lehteen tai näyttöön. 

> [!div class="mx-imgBorder"]
> ![Kartan osien](../media/map-control.png "yhdistämis komponentti")

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) 

## <a name="manifest"></a>Luettelo

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest>
    <control namespace="SampleNamespace" constructor="TSMapControl" version="1.0.0" display-name-key="TS_MapControl_Display_Key" description-key="TS_MapControl_Desc_Key" control-type="standard">
        <property name="controlValue" display-name-key="controlValue_Display_Key" description-key="controlValue_Desc_Key" of-type="SingleLine.Text" usage="bound" required="true" />
        <resources>
            <code path="index.ts" order="1" />
            <css path="css/TS_MapControl.css" order="1" />
        </resources>
    </control>
</manifest>
```

## <a name="code"></a>Koodi 

```TypeScript
import { IInputs, IOutputs } from "./generated/ManifestTypes";
export class TSMapControl
  implements ComponentFramework.StandardControl<IInputs, IOutputs> {
  // HTML IFrame element that will be used to render the map
  private _iFrameElement: HTMLIFrameElement;
  // PowerApps component framework framework delegate which will be assigned to this object which would be called whenever an update happens.
  private _notifyOutputChanged: () => void;
  // reference to ComponentFramework Context object
  private _context: ComponentFramework.Context<IInputs>;
  // API Key used to activate and embed the maps automatically
  // NOTE: You can follow the documentation at https://developers.google.com/maps/documentation/embed/get-api-key to generate your own API Key
  private MAPS_API_KEY: string = "<Replace your Key here>";
  /**
   * Empty constructor.
   */
  constructor() {}
  /**
   * Used to initialize the control instance. Controls can kick off remote server calls and other initialization actions here.
   * Data-set values are not initialized here, use updateView.
   * @param context The entire property bag available to control via Context Object; It contains values as set up by the customizer mapped to property names defined in the manifest, as well as utility functions.
   * @param notifyOutputChanged A callback method to alert the framework that the control has new outputs ready to be retrieved asynchronously.
   * @param state A piece of data that persists in one session for a single user. Can be set at any point in a controls life cycle by calling 'setControlState' in the Mode interface.
   * @param container If control is marked control-type='standard', it receives an empty div element within which it can render its content.
   */
  public init(
    context: ComponentFramework.Context<IInputs>,
    notifyOutputChanged: () => void,
    state: ComponentFramework.Dictionary,
    container: HTMLDivElement
  ) {
    this._notifyOutputChanged = notifyOutputChanged;
    this._context = context;
    this._iFrameElement = document.createElement("iframe");
    this._iFrameElement.setAttribute("class", "mapHiddenStyle");
    this.renderMap(this.buildMapUrl(context.parameters.controlValue.formatted));
    container.appendChild(this._iFrameElement);
  }
  /**
   * Checks if the url is not null and sets the value to the iFrame source to be loaded inside it and then notifies the ControlFramework that the output has changed
   * @param mapUrl : The url for the map that needs to be loaded inside the iFrame.
   */
  public renderMap(mapUrl: string) {
    if (mapUrl) {
      this._iFrameElement.setAttribute("src", mapUrl);
      this._iFrameElement.setAttribute("class", "mapVisibleStyle");
    } else {
      this._iFrameElement.setAttribute("class", "mapHiddenStyle");
    }
    this._notifyOutputChanged();
  }
  /**
   * Converts the string that is passed to a valid url that can be used to render the map for the location
   * @param addressString : any string that can be used to search for a location in maps
   * @returns the HTML encoded url that can be used to load the map if the addressString is non empty string
   */
  public buildMapUrl(addressString: string | undefined): string {
    if (addressString) {
      let url: string =
        "https://www.google.com/maps/embed/v1/place?key=" +
        this.MAPS_API_KEY +
        "&q=" +
        encodeURIComponent(addressString);
      return url;
    }
    return "";
  }
  /**
   * Called when any value in the property bag has changed. This includes field values, data-sets, global values such as container height and width, offline status, control metadata values such as label, visible, etc.
   * @param context The entire property bag available to control via Context Object; It contains values as set up by the customizer mapped to names defined in the manifest, as well as utility functions
   */
  public updateView(context: ComponentFramework.Context<IInputs>) {
    this._context = context;
    this.renderMap(this.buildMapUrl(context.parameters.controlValue.formatted));
  }
  /**
   * It is called by the framework prior to a control receiving new data.
   * @returns an object based on nomenclature defined in manifest, expecting object[s] for property marked as “bound” or “output”
   */
  public getOutputs(): IOutputs {
    // no-op: method not leveraged by this example custom control
    return {};
  }
  /**
   * Called when the control is to be removed from the DOM tree. Controls should use this call for cleanup.
   * i.e. canceling any pending remote calls, removing listeners, etc.
   */
  public destroy() {}
}
```

## <a name="resources"></a>Resursseja

```css
.SampleNamespace\.TSMapControl .mapVisibleStyle {
  width: 640px;
  height: 420px;
  visibility: visible;
}
.SampleNamespace\.TSMapControl .mapHiddenStyle {
  visibility: hidden;
}
```

Luettelo tiedostossa määritettiin tyyppiä `Single line of Text` oleva ominaisuus. Käytämme tätä sitomaan sen lomakkeen osoite-kenttään.  

> [!NOTE]
> Voit käyttää mitä tahansa kartan ohjelmointi raja pintaa, joka on käytettävissä markkinoilla. Tässä esimerkissä näytämme, miten se tehdään Google Map-ohjelmointi raja pinnalla. Sinun on luotava API-avain komponentille, jotta voit käyttää Google Map-ohjelmointi raja pintaa. Noudata ohjeita (https://developers.google.com/maps/documentation/embed/get-api-key luoda sellaisen).

Luo muuttujan nimi `MAPS_API_KEY`, jota voidaan käyttää komponentin yhteydessä.
Google Map-ohjelmointi raja pinnan avulla voit vain hahmontaa karttoja `IFRAME` sisällä. Sinun on siis luotava `IFRAME`-osa, joka hahmontaa kartan käyttämällä luotua URL-osoitetta. Oletuksena on, että määrität kartan piilotetuksi ja näytämme sen vain, kun osoitteen arvo on lomakkeessa.

`buildMapUrl` ja `renderMap` (Voit myös yhdistää ne yhdeksi) vie osoite merkki jonon ja upottaa sen kartan URL-osoitteeseen koodaten osoite merkki jonon ja määrittää sitten IFRAME-osatekijän src-osatekijän URL-osoitteeksi. Varmista myös **Notifyoutputchanged** -menetelmä, jotta ilmoitamme komponentille, että hahmontamistoiminto on muuttunut. 
 
```TypeScript
 public renderMap(mapUrl: string) {
    if (mapUrl) {
      this._iFrameElement.setAttribute("src", mapUrl);
      this._iFrameElement.setAttribute("class", "mapVisibleStyle");
    } else {
      this._iFrameElement.setAttribute("class", "mapHiddenStyle");
    }
    this._notifyOutputChanged();
  }
```

Varmista, että kutsut `renderMap`-funktiolla [updateview](../reference/control/updateview.md) -funktiolla varmistaaksesi, että ohjaus objekti päivitetään aina, kun näkymää päivitetään. 

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Lataa malli osat palvelimesta](https://go.microsoft.com/fwlink/?linkid=2088525)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin luettelon rakenteen viite](../manifest-schema-reference/index.md)
---
title: " IFRAME-osa | Microsoft Docs"
description: Toteutetaan IFRAME-osa
ms.custom: ''
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: article
ms.author: nabuthuk
author: Nkrb
ms.openlocfilehash: d10b03c478f238df02ee7e1309c0e39e758ce4c9
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72340456"
---
# <a name="implementing-a-iframe-component"></a>IFRAME-osan toteuttaminen

Tässä esimerkissä kuvataan, miten koodi komponentti sidotaan lomakkeen eri kenttiin ja käytetäänkö näiden kenttien arvoa syöte ominaisuuksina komponentille.  

> [!div class="mx-imgBorder"]
> ![Iframe-osan](../media/iframe-control.png "iframe-osa")

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) 

## <a name="manifest"></a>Luettelo

```XML
<?xml version="1.0" encoding="utf-8"?>
<manifest>
    <control namespace="SampleNamespace" constructor="TSIFrameControl" version="1.0.0" display-name-key="TS_IFrameControl_Display_Key" description-key="TS_IFrameControl_Desc_Key" control-type="standard">
        <property name="stringProperty" display-name-key="stringProperty_Display_Key" description-key="stringProperty_Desc_Key" of-type="SingleLine.Text" usage="bound" required="true" />
        <property name="latitudeValue" display-name-key="Bing_Maps_Latitude_Value" description-key="latitude" of-type="FP" usage="bound" required="true" />
        <property name="longitudeValue" display-name-key="Bing_Maps_Longitude_Value" description-key="longitude" of-type="FP" usage="bound" required="true" />
        <resources>
            <code path="index.ts" order="1" />
            <css path="css/TS_IFrameControl.css" order="2" />
        </resources>
    </control>
</manifest>
```

## <a name="code"></a>Koodi

```TypeScript
import { IInputs, IOutputs } from "./generated/ManifestTypes";
export class TSIFrameControl
  implements ComponentFramework.StandardControl<IInputs, IOutputs> {
  // reference to Bing Map IFrame HTMLElement
  private _bingMapIFrame: HTMLElement;
  // reference to the control container HTMLDivElement
  // This element contains all elements of our custom control example
  private _container: HTMLDivElement;
  // Flag if control view has been rendered
  private _controlViewRendered: Boolean;
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
    this._container = container;
    this._controlViewRendered = false;
  }
  /**
   * Called when any value in the property bag has changed. This includes field values, data-sets, global values such as container height and width, offline status, control metadata values such as label, visible, etc.
   * @param context The entire property bag available to control via Context Object; It contains values as set up by the customizer mapped to names defined in the manifest, as well as utility functions
   */
  public updateView(context: ComponentFramework.Context<IInputs>) {
    if (!this._controlViewRendered) {
      this._controlViewRendered = true;
      this.renderBingMapIFrame();
    }
    let latitude: number = context.parameters.latitudeValue.raw;
    let longitude: number = context.parameters.longitudeValue.raw;
    this.updateBingMapURL(latitude, longitude);
  }
  /**
   * Render IFrame HTML Element that hosts the Bing Map and appends the IFrame to the control container
   */
  private renderBingMapIFrame(): void {
    this._bingMapIFrame = this.createIFrameElement();
    this._container.appendChild(this._bingMapIFrame);
  }
  /**
   * Updates the URL of the Bing Map IFrame to display the updated lat/long coordinates
   * @param latitude : latitude of center point of Bing map
   * @param longitude : longitude of center point of Bing map
   */
  private updateBingMapURL(latitude: number, longitude: number): void {
    // Bing Map API:
    // https://msdn.microsoft.com/library/dn217138.aspx
    // Provide bing map query string parameters to format and style map view
    let bingMapUrlPrefix = "https://www.bing.com/maps/embed?h=400&w=300&cp=";
    let bingMapUrlPostfix = "&lvl=12&typ=d&sty=o&src=SHELL&FORM=MBEDV8";
    // Build the entire URL with the user provided latitude and longitude
    let iFrameSrc: string =
      bingMapUrlPrefix + latitude + "~" + longitude + bingMapUrlPostfix;
    // Update the IFrame to point to the updated URL
    this._bingMapIFrame.setAttribute("src", iFrameSrc);
  }
  /**
   * Helper method to create an IFrame HTML Element
   */
  private createIFrameElement(): HTMLElement {
    let iFrameElement: HTMLElement = document.createElement("iframe");
    iFrameElement.setAttribute("class", "TS_SampleControl_IFrame");
    return iFrameElement;
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
  public destroy() {
    // no-op: method not leveraged by this example custom control
  }
}
```

## <a name="resources"></a>Resursseja

```css
.SampleNamespace\.TSIFrameControl .TS_SampleControl_IFrame
{
    width: 300px;
    height: 400px;
}
```

> [!NOTE]
> PowerApps Component Framework ei vielä tue yhdistelmä kenttiä, joten et voi sitoa tätä komponenttia pakka uksen leveys-ja pituus aste-osoitteiden kenttiin. Koodi komponentti on sidottava eri liuku luku kenttään.

Tämä malli komponentti hahmontaa `IFRAME`, joka näyttää `Bing Maps URL`. Komponentti on sidottu kahteen liuku luku kenttään lomakkeessa, joka välitetään komponentiksi komponentiksi ja ruiskutetaan `IFRAME URL` päivittämään Bing-kartta annettujen syötteiden leveys-ja pituus asteina.  

Päivitä `Manifest` tiedosto sisältämään sidonnan kahdelle lisä kentälle lomakkeessa.  
Tämä muutos ilmoittaa PowerApps-komponentti kehykselle, että nämä sidotut kentät on välitettävä komponentille alustuksen aikana ja aina, kun jokin arvoista päivitetään.
  
```xml

<property name="latitudeValue" display-name-key="Bing_Maps_Latitude_Value" description-key="latitude" of-type="FP" usage="bound" required="true" />  
<property name="longitudeValue" display-name-key="Bing_Maps_Longitude_Value" description-key="longitude" of-type="FP" usage="bound" required="true" />  
```

Muita sidottuja ominaisuuksia saatetaan vaatia tai ei. Tämä pannaan täytäntöön komponentin määrittämisen aikana, kun osa sidotaan lomakkeeseen. Tämä voidaan määrittää määrittämällä ominaisuus solmun `required`-määrite Component-luettelossa. Valitse arvoksi false, jos et halua, että Component-ominaisuus on sidottu kenttään. 
 
`ControlFramework.d.ts` täytyy päivittää, jos haluat lisätä kaksi kenttää `IInputs` liittymään. Tämä on muoto, jossa PowerApps Component Framework välittää kenttien arvot. Kun lisäät nämä arvot `IInputs`-liittymään, TypeScript-tiedosto voi viitata arvoihin ja kääntää onnistuneesti.  

```TypeScript
    export interface IInputs 
    { latitudeValue: ControlFramework.PropertyTypes.NumberProperty;  
        longitudeValue: ControlFramework.PropertyTypes.NumberProperty;  
    }  
 ```

Ensimmäinen hahmontaminen muodostaa `IFRAME`-kohteen ja liittää sen ohjaus objektien säilöön. Tätä `IFRAME` käytetään **Bing-kartan**näyttämiseen. @No__t_0 URL-osoite on `Bing Map URL`, ja se sisältää sidotut kentät (latitudeValue ja pituus asteet) URL-osoitteena, joka keskittää kartan annettuun sijaintiin. 

[Updateview](../reference/control/updateview.md) -menetelmä käynnistetään, kun jokin näistä kentistä päivitetään lomakkeessa. Tämä menetelmä päivittää **Bing Map** -iframe-objektin URL-osoitteen käyttämään komponentille välitettyjä uusia leveys-ja pituus aste arvoja. Jos haluat tarkastella tätä komponenttia suorituksen aikana, sido osa lomakkeen kenttään, kuten mihin tahansa muuhun koodi komponenttiin.

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Lataa malli osat palvelimesta](https://go.microsoft.com/fwlink/?linkid=2088525)<br/>
[PowerApps Component Frameworkin luettelon rakenteen viite](../manifest-schema-reference/index.md)<br />
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br />
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)

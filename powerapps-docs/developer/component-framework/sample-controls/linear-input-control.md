---
title: " Lineaarinen syöte komponentti | Microsoft Docs"
description: Toteutetaan lineaarista syöte komponenttia
ms.custom: ''
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: article
ms.author: nabuthuk
author: Nkrb
ms.openlocfilehash: f7dcc3fef22c354b1fed684a09fb091f2d2c6cb7
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72347126"
---
# <a name="implementing-linear-input-component"></a>Toteutetaan lineaarista syöte komponenttia

Tämä malli komponentti muuttaa lomakkeen numealityyppien käyttämisen käyttö kokemusta. Sen sijaan, että kirjoitettaisiin lukuihin, lineaarinen syöte komponentti tarjoaa lineaarisen liuku säätimen, jonka avulla voidaan määrittää määritteen arvo lomakkeessa.  

Jotta voit ottaa tämän osan käyttöön, sinun on ensin määritettävä [luettelo](../manifest-schema-reference/manifest.md) tiedosto ja otettava mukautettu logiikka käyttöön TypeScript-kohteessa

> [!div class="mx-imgBorder"]
> ![Lineaarinen syöte osan](../media/linear-input-control.png "lineaarinen syöte komponentti")

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) 

## <a name="manifest"></a>Luettelo

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest>
    <control namespace="SampleNamespace" constructor="TSLinearInputControl" version="1.0.0" display-name-key="TSLinearInputControl_Display_Key" description-key="TSLinearInputControl_Desc_Key" control-type="standard">
        <type-group name="numbers">
            <type>Whole.None</type>
            <type>Currency</type>
            <type>FP</type>
            <type>Decimal</type>
        </type-group>
        <property name="controlValue" display-name-key="controlValue_Display_Key" description-key="controlValue_Desc_Key" of-type-group="numbers" usage="bound" required="true" />
        <resources>
            <code path="index.ts" order="1" />
            <css path="css/TS_LinearInputControl.css" order="1" />
        </resources>
    </control>
</manifest>
```

## <a name="code"></a>Koodi

```TypeScript
import { IInputs, IOutputs } from "./generated/ManifestTypes";
export class TSLinearInputControl
  implements ComponentFramework.StandardControl<IInputs, IOutputs> {
  // Value of the field is stored and used inside the control
  private _value: number;
  // PowerApps component framework framework delegate which will be assigned to this object which would be called whenever an update happens.
  private _notifyOutputChanged: () => void;
  // label element created as part of this control
  private labelElement: HTMLLabelElement;
  // input element that is used to create the range slider
  private inputElement: HTMLInputElement;
  // reference to the control container HTMLDivElement
  // This element contains all elements of our custom control example
  private _container: HTMLDivElement;
  // reference to ComponentFramework Context object
  private _context: ComponentFramework.Context<IInputs>;
  // Event Handler 'refreshData' reference
  private _refreshData: EventListenerOrEventListenerObject;
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
    this._context = context;
    this._container = document.createElement("div");
    this._notifyOutputChanged = notifyOutputChanged;
    this._refreshData = this.refreshData.bind(this);
    // creating HTML elements for the input type range and binding it to the function which refreshes the control data
    this.inputElement = document.createElement("input");
    this.inputElement.setAttribute("type", "range");
    this.inputElement.addEventListener("input", this._refreshData);
    //setting the max and min values for the control.
    this.inputElement.setAttribute("min", "1");
    this.inputElement.setAttribute("max", "1000");
    this.inputElement.setAttribute("class", "linearslider");
    this.inputElement.setAttribute("id", "linearrangeinput");
    // creating a HTML label element that shows the value that is set on the linear range control
    this.labelElement = document.createElement("label");
    this.labelElement.setAttribute("class", "TS_LinearRangeLabel");
    this.labelElement.setAttribute("id", "lrclabel");
    // retrieving the latest value from the control and setting it to the HTMl elements.
    this._value = context.parameters.controlValue.raw;
    this.inputElement.setAttribute(
      "value",
      context.parameters.controlValue.formatted
        ? context.parameters.controlValue.formatted
        : "0"
    );
    this.labelElement.innerHTML = context.parameters.controlValue.formatted
      ? context.parameters.controlValue.formatted
      : "0";
    // appending the HTML elements to the control's HTML container element.
    this._container.appendChild(this.inputElement);
    this._container.appendChild(this.labelElement);
    container.appendChild(this._container);
  }
  /**
   * Updates the values to the internal value variable we are storing and also updates the html label that displays the value
   * @param evt : The "Input Properties" containing the parameters, control metadata and interface functions
   */
  public refreshData(evt: Event): void {
    this._value = (this.inputElement.value as any) as number;
    this.labelElement.innerHTML = this.inputElement.value;
    this._notifyOutputChanged();
  }
  /**
   * Called when any value in the property bag has changed. This includes field values, data-sets, global values such as container height and width, offline status, control metadata values such as label, visible, etc.
   * @param context The entire property bag available to control via Context Object; It contains values as set up by the customizer mapped to names defined in the manifest, as well as utility functions
   */
  public updateView(context: ComponentFramework.Context<IInputs>): void {
    // storing the latest context from the control.
    this._value = context.parameters.controlValue.raw;
    this._context = context;
    this.inputElement.setAttribute(
      "value",
      context.parameters.controlValue.formatted
        ? context.parameters.controlValue.formatted
        : ""
    );
    this.labelElement.innerHTML = context.parameters.controlValue.formatted
      ? context.parameters.controlValue.formatted
      : "";
  }
  /**
   * It is called by the framework prior to a control receiving new data.
   * @returns an object based on nomenclature defined in manifest, expecting object[s] for property marked as “bound” or “output”
   */
  public getOutputs(): IOutputs {
    return {
      controlValue: this._value
    };
  }
  /**
   * Called when the control is to be removed from the DOM tree. Controls should use this call for cleanup.
   * i.e. canceling any pending remote calls, removing listeners, etc.
   */
  public destroy() {
    this.inputElement.removeEventListener("input", this._refreshData);
  }
}
```

## <a name="resources"></a>Resursseja

```css
.SampleNamespace\.TSLinearInputControl input[type="range"].linearslider {
  margin: 1px 0;
  background: transparent;
  -webkit-appearance: none;
  width: 100%;
  padding: 0;
  height: 24px;
  -webkit-tap-highlight-color: transparent;
}
.SampleNamespace\.TSLinearInputControl input[type="range"].linearslider:focus {
  outline: none;
}
.SampleNamespace\.TSLinearInputControl
  input[type="range"].linearslider::-webkit-slider-runnable-track {
  background: #666;
  height: 2px;
  cursor: pointer;
}
.SampleNamespace\.TSLinearInputControl
  input[type="range"].linearslider::-webkit-slider-thumb {
  background: #666;
  border: 0 solid #f00;
  height: 24px;
  width: 10px;
  border-radius: 48px;
  cursor: pointer;
  opacity: 1;
  -webkit-appearance: none;
  margin-top: -12px;
}
.SampleNamespace\.TSLinearInputControl
  input[type="range"].linearslider::-moz-range-track {
  background: #666;
  height: 2px;
  cursor: pointer;
}
.SampleNamespace\.TSLinearInputControl
  input[type="range"].linearslider::-moz-range-thumb {
  background: #666;
  border: 0 solid #f00;
  height: 24px;
  width: 10px;
  border-radius: 48px;
  cursor: pointer;
  opacity: 1;
  -webkit-appearance: none;
  margin-top: -12px;
}
.SampleNamespace\.TSLinearInputControl
  input[type="range"].linearslider::-ms-track {
  background: #666;
  height: 2px;
  cursor: pointer;
}
.SampleNamespace\.TSLinearInputControl
  input[type="range"].linearslider::-ms-thumb {
  background: #666;
  border: 0 solid #f00;
  height: 24px;
  width: 10px;
  border-radius: 48px;
  cursor: pointer;
  opacity: 1;
  -webkit-appearance: none;
}
```

Tässä esimerkissä [tyyppi ryhmä](../manifest-schema-reference/type-group.md) on määritetty ja nimetty `numbers`, joka sisältää luettelon, joka sisältää kymmen järjestelmä-, koko-, kelluva-ja valuutta-arvo tyyppejä kyseiseen ryhmään. Tätä ryhmää käytetään komponentti-ominaisuuden sitomiseen.

Tyyppiä `range` oleva syöte osa, jolla on `min` ja `max` arvo on 1 ja 1000, luodaan. Luodaan otsikko-osa, joka osoittaa arvon, joka on suhteellinen liuku säätimen sijaintiin nähden. Liitä `eventlistener`-ohjaus objektin syötteessä oleva Function-`refreshData`.

Luo paikallinen muuttuja [kontekstin](../reference/context.md) ja `notifyOutputChanged` tallentamista varten. Määritä Context ja notifyOutputChanged parametreista, jotka välitetään osana init-funktiosta.

Toteuta `refreshData`-funktiolla logiikka. Kuten näet näytteessä, otamme arvon `inputElement` ja asetat komponentin arvon, `innerHTML` `labelElement`-ominaisuuden ja kutsumme `notifyOutputChanged` niin, että muutokset on vyörytetty kehys kerroksen yläpuolelle.

```TypeScript
public refreshData(context: ControlFramework.IPropBag<InputsOutputs.IInputBag>) 
{ 
   this._value = (this.inputElement.value as any)as number; 
   this.labelElement.innerHTML = this.inputElement.value; 
   this._notifyOutputChanged(); 
} 
```

@No__t_0-menetelmässä määritteen arvo määritetään Context. parameters-parametrille ja aseta se arvo muuttujaksi, joka tallentaa osan arvon ja myös osan syöte elementit. 

```TypeScript

public updateView(context: ControlFramework.IPropBag<InputsOutputs.IInputBag>): void 
 { 
    this._value = context.parameters.controlValue.raw; 
    this._context = context; 
    this.inputElement.setAttribute("value",context.parameters.controlValue.formatted ? context.parameters.controlValue.formatted : ""); 
    this.labelElement.innerHTML = context.parameters.controlValue.formatted ? context.parameters.controlValue.formatted : ""; 
   } 
 ```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Lataa malli osat palvelimesta](https://go.microsoft.com/fwlink/?linkid=2088525)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin luettelon rakenteen viite](../manifest-schema-reference/index.md)

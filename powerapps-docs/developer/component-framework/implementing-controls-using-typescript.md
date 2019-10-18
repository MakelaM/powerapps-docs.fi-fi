---
title: Koodi komponenttien toteuttaminen TypeScript-koodin avulla | MicrosoftDocs
description: Koodi komponenttien käyttöönotto TypeScript-koodin avulla
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: index-page
ms.assetid: 18e88d702-3349-4022-a7d8-a9adf52cd34f
ms.author: nabuthuk
author: Nkrb
ms.openlocfilehash: cd57cce824c4071de12e7dc96407018dde57c2d7
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346827"
---
# <a name="implement-components-using-typescript"></a>Toteuta komponentit käyttäen TypeScript-kohdetta

Tässä opetus ohjelmassa käydään läpi uuden koodi komponentin luonti TypeScript-kohteessa. Malli komponentti on lineaarinen syöte komponentti, jonka avulla käyttäjät voivat syöttää luku arvoja käyttämällä visualisoinnin liuku säädintä kentän arvojen kirjoittamisen sijaan. 

## <a name="creating-a-new-component-project"></a>Luodaan uusi komponentti projekti

Uuden projektin luominen:

1. Avaa **kehittäjän komento rivi VS 2017-ikkunaa varten** .
1. Luo projektille uusi kansio käyttämällä seuraavaa komentoa: 
    ```CLI
    mkdir LinearComponent
    ```

1. Siirry uuteen hakemistoon käyttämällä komentoa `cd LinearComponent`. 
   
1. Luo uusi komponentti projekti, joka välittää perusparametreja, suorittamalla seuraava komento.

   ```CLI
    pac pcf init --namespace SampleNamespace --name TSLinearInputComponent --template field
    ``` 

1. Asenna projektin koonti työkalut käyttämällä komentoa `npm install`. 
2. Avaa projekti kansiosi `C:\Users\<your name>\Documents\<My_PCF_Component>` valitsemaasi kehittäjä ympäristöön ja aloita koodi komponentin kehittäminen. Nopein tapa aloittaa on suorittaa `code .` komento riviltä, kun olet `C:\Users\<your name>\Documents\<My_PCF_Component>` hakemistossa. Tämä komento avaa komponentti projektisi Visual Studio koodissa.

## <a name="implementing-manifest"></a>Toteutetaan luetteloa

Luettelo on XML-tiedosto, joka sisältää koodi komponentin metatiedot. Se määrittää myös koodi komponentin toiminnan. Tässä opetus ohjelmassa tämä luettelo tiedosto luodaan `<Your component Name>`-alikansioon. Kun avaat `ControlManifest.Input.xml` tiedoston Visual Studio koodissa, huomaat, että luettelo tiedostossa on esimääritetty joitakin ominaisuuksia. Tee muutoksia esimääritettyyn luettelo tiedostoon seuraavassa esitetyllä tavalla:

1. [Ohjaus objekti](manifest-schema-reference/control.md) solmu määrittää koodi osan nimi tilan, version ja näyttö nimen. Määritä nyt [ohjaus objektin](manifest-schema-reference/control.md) jokainen ominaisuus seuraavassa esitetyllä tavalla:

   - **nimi tila**: koodi komponentin nimi tila. 
   - **Konstruktori**: koodi komponentin konstruktori.
   - **Versio**: komponentin versio. Aina, kun päivität komponentin, sinun on päivitettävä versio, jotta näet muutokset suoritus toiminnossa.
   - **Display-Name-Key**: käyttö liittymässä näkyvän koodi osan nimi.
   - **Description-Name-Key**: käyttö liittymässä näkyvän koodi osan kuvaus.
   - **Control-type**: koodi komponentin tyyppi. Vain *vakio* koodi komponenttien tyyppiä tuetaan.

     ```XML
      <?xml version="1.0" encoding="utf-8" ?>
      <manifest>
      <control namespace="SampleNameSpace" constructor="TSLinearInputComponent" version="1.0.0" display-name-key="Linear Input Component" description-key="Allows you to enter the numeric values using the visual slider." control-type="standard">
     ```

2. [Ominaisuus](manifest-schema-reference/property.md) solmu määrittää koodi komponentin ominaisuudet, kuten kentän tieto tyypin määrittämisen. Ominaisuus solmu on määritetty alielementti ohjaus elementin alla. Määritä [ominaisuus](manifest-schema-reference/property.md) solmu seuraavassa esitetyllä tavalla:

   - **nimi**: ominaisuuden nimi.
   - **Display-Name-Key**: käyttö liittymässä näkyvän ominaisuuden näyttö nimi.
   - **Description-Name-Key**: käyttö liittymässä näkyvän ominaisuuden kuvaus. 
   - **of-Type-Group**: [tyyppiä-ryhmä käytetään,](manifest-schema-reference/type-group.md) kun halutaan käyttää useampaa kuin kahta tieto tyyppi kenttää. Lisää [tyyppi-ryhmä-](manifest-schema-reference/type-group.md) osa rinnakkaiskohteeksi luettelon `property`-osaan. @No__t_0 määrittää osan arvon ja voi sisältää koko naisia, valuuttoja, liuku lukuja tai kymmen järjestelmä arvoja.
   - **käyttö**: sisältää kaksi ominaisuutta, *sidotun* ja *syötteen*. Sidotut ominaisuudet on sidottu vain kentän arvoon. Syöte ominaisuudet on sidottu kenttään tai sallivat staattisen arvon.
   - **pakollinen**: määrittää, tarvitaanko ominaisuus.

     ```XML
      <property name="sliderValue" display-name-key="sliderValue_Display_Key" description-key="sliderValue_Desc_Key" of-type-group="numbers" usage="bound" required="true" />
      ```
3. [Resources](manifest-schema-reference/resources.md) -solmu määrittää koodi komponentin visualisoinnin. Se sisältää kaikki koodi komponentin muodostavat resurssit. [Koodi](manifest-schema-reference/code.md) on määritetty alielementti resurssi-elementin alla. Määritä [resurssit](manifest-schema-reference/resources.md) seuraavassa esitetyllä tavalla:

   - **koodi**: viittaa polkuun, jossa kaikki resurssi tiedostot sijaitsevat.
 
      ```XML
      <resources>
        <code path="index.ts" order="1" />
        <css path="css/TS_LinearInputComponent.css" order="1" />
        </resources>
        ```
      Yleisen luettelo tiedoston pitäisi näyttää suunnilleen tältä: 

     ```XML
      <?xml version="1.0" encoding="utf-8" ?>
      <manifest>
      <control namespace="SampleNamespace" constructor="TSLinearInputComponent" version="1.0.0" display-name-key="Linear Input Component" description-key="Allows you to enter the numeric values using the visual slider." control-type="standard">
        <type-group name="numbers">
          <type>Whole.None</type>
          <type>Currency</type>
          <type>FP</type>
          <type>Decimal</type>
         </type-group>
        <property name="sliderValue" display-name-key="sliderValue_Display_Key" description-key="sliderValue_Desc_Key" of-type-group="numbers" usage="bound" required="true" />
       <resources>
         <code path="index.ts" order="1" />
         <css path="css/TS_LinearInputComponent.css" order="1" />
       </resources>
      </control>
     </manifest>
     ```

4. Tallenna muutokset `ControlManifest.Input.xml` tiedostoon.
5. Luo nyt uusi kansio `TSLinearInputComponent`-kansioon ja nimeä se **CSS**-muodossa.
6. Luo CSS-tiedosto ja [Lisää tyyli koodi komponenttiin](#adding-style-to-the-code-component).
7. Luo komponentti projekti käyttämällä komentoa `npm run build`.
8. Koonti versio Luo päivitetyn TypeScript-tyyppi määritys tiedoston `TSLinearInputComponent/generated`-kansioon.

## <a name="implementing-component-logic"></a>Toteutetaan komponentti logiikkaa

Seuraava vaihe luettelo tiedoston toteutuksen jälkeen on toteuttaa komponentti logiikka käyttäen TypeScript-kohdetta. Komponentti logiikka tulee ottaa `index.ts`-tiedoston sisään. Kun avaat `index.ts` tiedoston Visual Studio koodissa, huomaat, että neljä olennaista luokkaa ovat esimääritettyjä. Seuraavaksi otetaan käyttöön koodi komponentin logiikka. 

1. Avaa `index.ts` tiedosto valintasi koodi editorissa.
2. Päivitä `TSLinearInputComponent`-luokka käyttäen seuraavaa koodia:

```TypeScript
import { IInputs, IOutputs } from "./generated/ManifestTypes";
export class TSLinearInputComponent
  implements ComponentFramework.StandardControl<IInputs, IOutputs> {
  // Value of the field is stored and used inside the component
  private _value: number;
  // PowerApps component framework delegate which will be assigned to this object which would be called whenever any update happens.
  private _notifyOutputChanged: () => void;
  // label element created as part of this component
  private labelElement: HTMLLabelElement;
  // input element that is used to create the range slider
  private inputElement: HTMLInputElement;
  // reference to the component container HTMLDivElement
  // This element contains all elements of our code component example
  private _container: HTMLDivElement;
  // reference to PowerApps component framework Context object
  private _context: ComponentFramework.Context<IInputs>;
  // Event Handler 'refreshData' reference
  private _refreshData: EventListenerOrEventListenerObject;

  constructor() {}

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
    // creating HTML elements for the input type range and binding it to the function which refreshes the component data
    this.inputElement = document.createElement("input");
    this.inputElement.setAttribute("type", "range");
    this.inputElement.addEventListener("input", this._refreshData);
    //setting the max and min values for the component.
    this.inputElement.setAttribute("min", "1");
    this.inputElement.setAttribute("max", "1000");
    this.inputElement.setAttribute("class", "linearslider");
    this.inputElement.setAttribute("id", "linearrangeinput");
    // creating a HTML label element that shows the value that is set on the linear range component
    this.labelElement = document.createElement("label");
    this.labelElement.setAttribute("class", "TS_LinearRangeLabel");
    this.labelElement.setAttribute("id", "lrclabel");
    // retrieving the latest value from the component and setting it to the HTML elements.
    this._value = context.parameters.sliderValue.raw
      ? context.parameters.sliderValue.raw
      : 0;
    this.inputElement.setAttribute(
      "value",
      context.parameters.sliderValue.formatted
        ? context.parameters.sliderValue.formatted
        : "0"
    );
    this.labelElement.innerHTML = context.parameters.sliderValue.formatted
      ? context.parameters.sliderValue.formatted
      : "0";
    // appending the HTML elements to the component's HTML container element.
    this._container.appendChild(this.inputElement);
    this._container.appendChild(this.labelElement);
    container.appendChild(this._container);
  }

  /**
   * Updates the values to the internal value variable we are storing and also updates the html label that displays the value
   * @param context : The "Input Properties" containing the parameters, component metadata and interface functions
   */

  public refreshData(evt: Event): void {
    this._value = (this.inputElement.value as any) as number;
    this.labelElement.innerHTML = this.inputElement.value;
    this._notifyOutputChanged();
  }

  public updateView(context: ComponentFramework.Context<IInputs>): void {
    // storing the latest context from the control.
    this._value = context.parameters.sliderValue.raw
      ? context.parameters.sliderValue.raw
      : 0;
    this._context = context;
    this.inputElement.setAttribute(
      "value",
      context.parameters.sliderValue.formatted
        ? context.parameters.sliderValue.formatted
        : ""
    );
    this.labelElement.innerHTML = context.parameters.sliderValue.formatted
      ? context.parameters.sliderValue.formatted
      : "";
  }

  public getOutputs(): IOutputs {
    return {
      sliderValue: this._value
    };
  }

  public destroy() {
    this.inputElement.removeEventListener("input", this._refreshData);
  }
}

```

3. Muodosta Project uudelleen käyttämällä komentoa `npm run build`. 
 
4. Komponentti käännetään `out/controls/TSLinearInputComponent`-kansioon. Koonti-artefakteja ovat seuraavat:

   - Bundle. js – yhdistetty osan lähde koodi. 
   - ControlManifest. XML – todellinen Component-kokoonpano tiedosto, joka ladataan Common Data Service-organisaatioon.

## <a name="adding-style-to-the-code-component"></a>Tyylin lisääminen koodi komponenttiin

Kehittäjät ja sovellusten tekijät voivat määrittää niiden tyyli edustaa koodi komponentteja visuaalisesti käyttämällä CSS:ää. CSS-koodin avulla kehittäjät voivat kuvailla koodi komponenttien esittämistä, mukaan lukien tyyliä, värejä, asetteluja ja fontteja. Lineaarinen-syöte komponentin [init](reference/control/init.md) -menetelmä luo syöte-osan ja määrittää Class-määritteen `linearslider`. @No__t_0 luokan tyyli on määritetty erillisessä `CSS` tiedostossa. Lisä mukautuksia tukevien komponentti resurssien, kuten `CSS`-tiedostojen, lisääminen voidaan sisällyttää koodi osaan.

1. Luo uusi `css`-alikansio `TSLinearInputComponent`-kansioon. 
2. Luo uusi `TS_LinearInputComponent.css`-tiedosto `css`-alikansioon. 
3. Lisää seuraava tyyli sisältö `TS_LinearInputComponent.css` tiedostoon:

    ```CSS
    .SampleNamespace\.TSLinearInputComponent input[type=range].linearslider {
      margin: 1px 0;
      background: transparent;
      -webkit-appearance: none;
      width: 100%;
      padding: 0;
      height: 24px;
      -webkit-tap-highlight-color: transparent
    }

    .SampleNamespace\.TSLinearInputComponent input[type=range].linearslider:focus {
      outline: none;
    }

    .SampleNamespace\.TSLinearInputComponent input[type=range].linearslider::-webkit-slider-runnable-track {
      background: #666;
      height: 2px;
      cursor: pointer
    }

    .SampleNamespace\.TSLinearInputComponent input[type=range].linearslider::-webkit-slider-thumb {
      background: #666;
      border: 0 solid #f00;
      height: 24px;
      width: 10px;
      border-radius: 48px;
      cursor: pointer;
      opacity: 1;
      -webkit-appearance: none;
      margin-top: -12px
    }

    .SampleNamespace\.TSLinearInputComponent input[type=range].linearslider::-moz-range-track {
      background: #666;
      height: 2px;
      cursor: pointer
    }

    .SampleNamespace\.TSLinearInputComponent input[type=range].linearslider::-moz-range-thumb {
      background: #666;
      border: 0 solid #f00;
      height: 24px;
      width: 10px;
      border-radius: 48px;
      cursor: pointer;
      opacity: 1;
      -webkit-appearance: none;
      margin-top: -12px
    }

    .SampleNamespace\.TSLinearInputComponent input[type=range].linearslider::-ms-track {
      background: #666;
      height: 2px;
      cursor: pointer
    }

    .SampleNamespace\.TSLinearInputComponent input[type=range].linearslider::-ms-thumb {
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

5. Tallenna `TS_LinearInputComponent.css` tiedosto.
6. Muokkaa `ControlManifest.Input.xml` tiedostoa sisältämään `CSS` Resource-tiedosto resurssi-osaan.
 
    ```XML
    <resources> 
      <code path="index.ts" order="1"/> 
      <css path="css/TS_LinearInputComponent.css" order="1"/> 
    </resources> 
     ```
7. Muodosta projekti uudelleen käyttäen seuraavaa komentoa: 
   ```CLI
   npm run build
   ```
8. Tarkista Build-tuloste **./out/Controls/TSLinearInputComponent** -kohdasta ja huomioi, että **TS_LinearInputComponent. CSS** -tiedosto on nyt sisällytetty koottujen koonti versio-artefakteihin. 

## <a name="debugging-your-code-component"></a>Koodi komponentin virheen korjaus

Kun olet suorittanut koodi komponentti logiikan, Käynnistä virheen korjaus prosessi suorittamalla seuraava komento. Lisä tietoja: [koodi komponenttien vian](debugging-custom-controls.md) määritys

```CLI
npm start
```

## <a name="packaging-your-code-components"></a>Koodi komponenttien pakkaaminen

Luo ja tuo [ratkaisun](https://docs.microsoft.com/dynamics365/customer-engagement/customize/solutions-overview) tiedosto noudattamalla seuraavia ohjeita:

1. Luo uudet kansio **ratkaisut** **LinearComponent** -kansion sisään ja siirry kansioon. 
2. Luo uusi Solution Project **LinearComponent** -kansioon käyttäen seuraavaa komentoa:
 
    ```CLI
     pac solution init --publisher-name developer --publisher-prefix dev 
    ```

   > [!NOTE]
   > [Publisher-Name](https://docs.microsoft.com/powerapps/developer/common-data-service/reference/entities/publisher) -ja [Publisher-etuliite](https://docs.microsoft.com/powerapps/maker/common-data-service/change-solution-publisher-prefix) arvojen on oltava yksilöllisiä ympäristössäsi.
 
3. Kun uusi ratkaisun projekti luodaan, sinun on viitattava sijaintiin, jossa luomasi osa sijaitsee. Voit lisätä viitta uksen käyttämällä seuraavaa komentoa:

    ```CLI
     pac solution add-reference --path c:\users\LinearComponent
    ```

4. Jos haluat luoda zip-tiedoston ratkaisusi projektista, sinun on `cd` ratkaisun projekti hakemistoon ja rakennettava projekti käyttäen seuraavaa komentoa: 

    ```CLI
     msbuild /t:restore
    ```

5. Suorita seuraava komento MSBUILD:
    ```CLI
     msbuild
    ```

    > [!NOTE]
    > Varmista, että **NuGet-kohteet & Build-tehtävät** on merkitty. Jos haluat ottaa sen käyttöön:
    > - Avaa **Visual Studio asennus ohjelma**.
    > - Visual Studio 2017, valitse **Muokkaa**.
    > - Valitse **erilliset osat**.
    > - Valitse **koodi työkalut**-kohdassa **NuGet-kohteet & muodosta tehtäviä**.

6. Luotu ratkaisun zip-tiedosto sijaitsee `Solution\bin\debug`-kansiossa.
7. [Tuo ratkaisusi manuaalisesti Common Data Service](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customize/import-update-upgrade-solution) verkko portaalin avulla, kun zip-tiedosto on valmis, tai tarkista organisaatiosi ja [käyttöönotto](import-custom-controls.md#deploying-code-components) - [OSIESI todentaminen](import-custom-controls.md#authenticating-to-your-organization) powerapps CLI-komentojen avulla.

## <a name="adding-code-components-in-model-driven-apps"></a>Koodi komponenttien lisääminen mallipohjaisissa sovelluksissa

Jos haluat lisätä koodi komponentin, kuten lineaarisen syöte komponentin, noudata ohje aiheessa [osien lisääminen kenttiin ja entiteetteihin](add-custom-controls-to-a-field-or-entity.md)annettuja ohjeita.

## <a name="adding-code-components-to-a-canvas-app"></a>Koodi komponenttien lisääminen kangas sovellukseen

Jos haluat lisätä koodi komponentit pohjaan sovellukseen, noudata ohje aiheen [Lisää koodi osia](component-framework-for-canvas-apps.md#add-components-to-a-canvas-app)pohjaan-sovellukseen ohjeita.

### <a name="see-also"></a>Katso myös

[Lataa malli osat palvelimesta](https://go.microsoft.com/fwlink/?linkid=2088525)<br/>
[Päivitä aiemmin luodut PowerApps Component Framework-osat](updating-existing-controls.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](overview.md)

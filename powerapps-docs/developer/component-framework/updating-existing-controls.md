---
title: Päivitä aiemmin luodut koodi komponentit käyttämällä PowerApps Component Framework-työkaluja | Microsoft Docs
description: Päivitä osat PowerApps Component Framework-työkalujen avulla
keywords: PowerApps Component Framework, koodi komponentti, komponentti kehys
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2cbf58a-9112-45c2-b823-2c07a310714c
ms.openlocfilehash: 05e32fb7e098dad3aabf36f2efdaf311c1bea327
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72340226"
---
# <a name="update-existing-code-components"></a>Päivitä aiemmin luodut koodi komponentit 

Jos olet PowerApps Component Framework Private Preview-osallistuja mallipohjaisia sovelluksia varten ja olet jo luonut koodi komponentteja, sinun on tehtävä joitakin pieniä päivityksiä, jotta se on yhteensopiva uusien ALM-centric-projekti rakenteiden kanssa. 

Joitakin muutoksia tarvitaan, jotta voit käyttää uusia PowerApps CLI-työkaluja nykyisillä PowerApps-komponentin kehys koodi komponenteilla.

> [!NOTE]
> Tämä ohje aihe koskee vain mallipohjaisten sovellusten koodi komponenttien päivittämistä, koska PowerApps CLI-työkalut eivät ole käytettävissä mallipohjaisten sovellusten yksityisen esikatselun aikana.  

## <a name="creating-an-empty-project"></a>Tyhjän projektin luominen

Luo uusi tyhjä projekti koodi komponenttillesi käyttämällä Powerappsia CLI. Lisä tietoja: [komponenttien luominen työkalujen avulla](create-custom-controls-using-pcf.md)

Kun projekti on perustettu, siirry koodi komponentin lähteeksi uuteen projektiin:

1. Kopioi tai korvaa osan lähde tiedosto vanhasta lähde tiedostosta **indeksiin. ts**.
2. Kopioi tai korvaa **Controlmanifest. XML** -tiedoston sisältö **Controlmanifest. Input. XML** -tiedostoon.
3. Kopioi kaikki muut oheisosan resurssit, kuten CSS, RESX tai IMG vastaavaan alikansioon vanhasta projektista uuteen projektiin.

## <a name="updating-manifest-file"></a>Päivitetään luettelo tiedostoa

Koodi osan ominaisuuksien määrittävä `ControlManifest.xml` tiedosto korvataan `ControlManifest.Input.xml` tiedostolla. Näiden kahden tiedoston rakenteessa pitäisi muuten olla hyvin vähän muutoksia.

On kuitenkin muutamia tärkeitä semanttisia muutoksia:

1. @No__t_0 resurssi merkinnän on nyt osoitettava koodi komponentin esikäännetty lähde tiedosto. Tiedosto nimi on oletus arvo **indeksiin. ts**.

   Jos esimerkiksi komponentti lähde on käytössä tiedostossa nimeltä `MyControl.ts`, `ControlManifest.Input.xml` `code` merkinnän on osoitettava kyseiseen tiedostoon. @No__t_0 tiedoston on myös oltava kelvollinen TypeScript-tiedosto. Tämä on toisin kuin vanhojen luettelo tiedostojen, jotka määrittämään kootun JS-tuloste tiedoston `code` merkinnässä.
2. Resurssi-elementtejä, kuten `code` tai `css`, `path` määrite viittaa nyt tiedoston paikalliseen polkuun levyllä. Esimerkki:

    ```XML
   <resources>
    <css path="css/YourControlName" order="1"/>
    </resources>
    ```

Yllä oleva `path`-määrite ilmaisee, että `YourControlName.css` tiedosto sijaitsee `css`-alikansiossa suhteessa nykyiseen hakemistoon, jossa `ControlManifest.Input.xml` sijaitsee levyllä.

Päivitä ControlManifest. Input. XML-tiedostot seuraavasti:

1. Muokkaa `code` `ControlManifest.Input.xml` merkintää koodi komponentin valmiiksi käännettynä lähde tiedostona (yleensä indeksistä. ts).
2. Muokkaa resurssien kaikkia polkuja viittaamaan levyllä olevien tiedostojen suhteellisiin polkuihin oikein.

## <a name="updating-the-project-files"></a>Päivitetään Projekti tiedostoja

Jos olet jo kehittänyt osan käyttämällä työkalun vanhempaa versiota ja haluat hyödyntää uusimpia ominaisuuksia, varmista, että päivität projekti tiedostosi seuraavassa esitetyllä tavalla:

1. Päivitä aiemmin luodut projektit käyttämään uusimpia moduuleja.
 
   - Päivitä `pcfproj` versio koodi, joka sijaitsee PowerApps Component Framework Project-kansiossa, seuraavasti:

      ```XML
      <Packagereference Include="Microsoft.PowerApps.MSBuild.Pcf" Version="1.*"/>
      ```
   - Päivitä Solution Project-kansiossa sijaitsevan `cdsproj` versio koodi seuraavasti:

      ```XML
      <Packagereference Include="Microsoft.PowerApps.MSBuild.Solution" Version="1.*"/>
      ```

      > [!NOTE] 
      > Kun olet tehnyt yllä olevat muutokset, Päivitä projektisi oikeaan versioon suorittamalla komento `msbuild /t:restore`.


   - Päivitä `package.json`-tiedostosi versio koodi, joka sijaitsee PowerApps Component Framework Project-kansiossa:

      ```JSON
      "devDependencies":{
       "pcf-scripts": "^1",
       "pcf-start": "^1"
          }
      ```
     > [!NOTE]
     > Kun olet tehnyt yllä olevat muutokset, Päivitä projektisi oikeaan versioon suorittamalla `npm update`-komento.

2. Jos olet aiemmin luonut todennus profiilin, sinun on luotava se uudelleen. Tämä johtuu siitä, että profiiliin lisättiin uusi ominaisuus, joka tukee muuta kuin julkista pilvi palvelua. Voit tehdä tämän seuraavasti:
 
    - Suoritetaan komentoa `pac auth clear`.
    - Suoritetaan komentoa `pac auth create --url <your org url>`.

## <a name="updating-your-project-with-the-latest-node-modules"></a>Projektin päivittäminen uusimpien solmu moduulien avulla

Vanhat projektit edellyttävät uusimpia NPM-moduuleita, jotta ne voivat hyödyntää uusimpia CLI-ominaisuuksia. Jos haluat päivittää aiemmin lataamasi solmu moduulit, siirry projekti hakemistoon kehittäjän komento kehotteeseen ja suorita komento `npm update`. 

## <a name="using-es6-module-syntax"></a>ES6-moduulin syntaksin käyttäminen

Koonti työkalut edellyttävät, että komponentti lähde viedään käyttäen Standard ES6 Module-muotoa. Vanhat komponentit viedään yleensä sisäisinä moduuleina (tunnetaan myös nimellä nimi avaruudet). Komponentin lähde tiedostoa on muokattava alla olevan mukaisesti, jotta voit tasata uudet koonti työkalut.

1. Avaa lähde tiedosto, joka toteuttaa koodi komponentin (esimerkiksi indeksistä. ts).
2. Käytä vakioES6 Export-syntaksia poistamalla moduulin määrityksen.

     Ennen
     ```TypeScript
     module SampleNamespace
     {
    export class TSLinearInputControl implements ComponentFramework.StandardControl<InputsOutputs.IInputBag, InputsOutputs.IOutputBag> {
          <your class implementation>
           }
            }
     
      ```
    Jälkeen
    ```TypeScript
     export class YourControlName implements ComponentFramework.StandardControl<IInputs, IOutputs> { 
          <your class implementation>
          }
   ```

## <a name="using-generated-manifest-typing-file"></a>Käytetään luotua luettelon kirjoitus tiedostoa

Vanhat projektit edellyttävät manuaalisesti `inputsOutputs.d.ts` kirjoitus tiedoston luomista ja muokkaamista, joka sijaitsee yleensä `private_typing`-alikansiossa. PowerApps CLI-työkalut luovat nyt tämän tiedoston automaattisesti koonti version yhteydessä. 

Code-Gen varmistaa, että komponentin lähde koodissa käytettävät `type` määritykset pysyvät synkronoituina komponentin luettelo tiedostossa määritetyn `types` kanssa.

Kirjoitus tiedosto nimetään uudelleen `ManifestTypes.d.ts` ja se luodaan nyt alikansioksi, jonka nimi on `generated`. Lisäksi `InputsOutputs.IInputBag`-ja `InputsOutputs.IOutputBag`-tyypit nimetään uudelleen `IInputs` ja `IOutputs` vastaavasti.

Uuden kirjoitus tiedoston käyttäminen:

1. Tuo uusi `ManifestTypes.d.ts`-tiedosto lisäämällä seuraava rivi komponentin lähde tiedoston yläosaan:

    tuo {Ipanokset, Ituotokset} kohteesta `./generated/ManifestTypes`.
2. Nimeä uudelleen kaikki **Inputstuotokset. Iininputbag** -viitta ukset **iinput-tietoihin**.
3. Nimeä uudelleen kaikki kohteen **Infutsoutput. IOutputBag** viitta ukset **ioutput-toiminnoille**.
4. Muodosta projekti luodaksesi uuden **Manifesttypes. d. ts** -tiedoston komennolla `npm run build`.

## <a name="troubleshooting-and-workarounds"></a>Vian määritys ja ratkaisu tavat

1. Jos saat 1ES-ilmoituksen, jossa pyydetään, miten PCF-komento sarjoja käytetään, ota huomioon, että näitä komento sarjoja käytetään ainoastaan koodi komponenttien muodostamiseen, mutta ne eivät ole niputettuja tai niiden käyttämiä.  
2. Jos olet aiemmin luonut koodi komponentin käyttämällä työkalu versiota 0.1.817.1 tai vanhempaa versiota ja haluat varmistaa, että uusimmat muodostus-ja virheen korjaus moduulit ovat käytössä, tee päivitykset Package. JSON-muotoon seuraavasti:
   
    ```JSON
     "dependencies": { "@types/node": "^10.12.18", "@types/powerapps-component-framework": "1.1.0"}, "devDependencies": { "pcf-scripts": "~0", "pcf-start": "~0" } 
    ```
3. Käyttäjä saa virheen `Failed to retrieve information about Microsoft.PowerApps.MSBuild.Pcf from remote source <Feed Url>`, kun koonti versio epäonnistuu valtuutus ongelmien vuoksi. Tässä on tämän ongelman ratkaisu:

   - Avaa NuGet. config-tiedosto kohteesta **%AppData%\nuget**. Syötteen, josta käyttäjä saa virheen, on oltava tässä tiedostossa. 
   - Poista syöte NuGet. config-tiedostosta tai luo PAT-tunnus ja lisää se NuGet. config-tiedostoon. Esimerkki:

     ```XML
     <?xml version="1.0" encoding="utf-8"?>  
     <configuration>  
     <packageSources>  
         <add key="CRMSharedFeed" value="https://dynamicscrm.pkgs.visualstudio.com/_packaging/CRMSharedFeed/nuget/v3/index.json" />  
      </packageSources>  
     <packageSourceCredentials>  
      <CRMSharedFeed>  
      <add key="Username" value="anything" />  
      <add key="Password" value="User PAT" />  
    </CRMSharedFeed>  
     </packageSourceCredentials>  
   </configuration>
     ```

### <a name="see-also"></a>Katso myös

[PowerApps Component Frameworkin rajoitukset](limitations.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](overview.md)

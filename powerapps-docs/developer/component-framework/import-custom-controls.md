---
title: Tuo komponentit | Microsoft Docs
description: Tässä aiheessa kuvataan, miten koodi komponentteja tuodaan
keywords: ''
ms.author: nabuthuk
manager: kvivek
ms.date: 06/20/2019
ms.service: powerapps
ms.suite: ''
ms.topic: article
author: Nkrb
ms.openlocfilehash: 3042202fd1790d117c2a503bd6e69eaaea15c08a
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346804"
---
# <a name="package-a-code-component"></a>Pakkaa koodi komponentti

Tässä aiheessa kuvataan, miten koodi komponentit tuodaan Common Data Service. Kun koodi komponentit on pantu täytäntöön Powerappsin avulla, seuraava vaihe on niputtaa kaikki koodi komponentti elementit ratkaisun tiedostoon ja tuoda ratkaisun tiedosto Common Data Service, jotta voit tarkastella koodi komponentteja suorituksen aikana.

Ratkaisun tiedoston luominen ja tuominen:

1. Luo uusi kansio ja nimeä IT- **ratkaisu** (tai mikä tahansa haluamasi nimi) käyttämällä komentoa `mkdir Solutions`. Siirry hakemistoon käyttämällä komentoa `cd Solutions`.

2. Luo uusi ratkaisu projekti käyttämällä komentoa `pac solution init --publisher-name <enter your publisher name> --publisher-prefix <enter your publisher prefix>`. Solution Projectia käytetään koodi komponentin niputtamiseen ratkaisun zip-tiedostoon, jota käytetään Common Data Service tuontia varten.

   > [!NOTE]
   > @No__t_0-ja `publisher-prefix`-arvojen on oltava yksilöllisiä ympäristössäsi.
 
3. Kun uusi ratkaisun projekti luodaan, viittaa **ratkaisun** kansioon sijaintiin, jossa luodun mallin osa sijaitsee. Voit lisätä viitta uksen käyttämällä alla näkyvää komentoa. Tämä viittaus ilmoittaa ratkaisu projektille, mitkä koodi komponentit tulee lisätä koonti version aikana. Voit lisätä viitta uksia useisiin komponentteihin yksittäisessä ratkaisu projektissa.

   ```CLI   
    pac solution add-reference --path <path to your PowerApps component framework project>
   ```

3. Jos haluat luoda zip-tiedoston ratkaisun projektista, siirry ratkaisun projekti hakemistoon ja Luo projekti käyttämällä komentoa `msbuild /t:build /restore`. Tämä komento luo ratkaisun projektin *MSBuild* -kohteen avulla vetämällä alas *NuGet* -riippuvuussuhteita osana Restore-toimintoa. Käytä `/restore` vain ensimmäistä kertaa, kun Solution Project on muodostettu. Jokaisen koonti version jälkeen voit suorittaa komennon `msbuild`.


    > [!NOTE]
    > - Jos MSBuild 15,9. * ei ole polussa, avaa kehittäjän komento rivi kohteelle VS 2017 ja suorita `msbuild` komennot.
    > - Ratkaisun luominen *virheen korjauksen* määrityksessä luo hallitsemattoman ratkaisun paketin. Hallitun ratkaisun paketti muodostetaan luomalla liuos *julkaisu* määrityksissä. Nämä asetukset voidaan ohittaa määrittämällä `SolutionPackageType`-ominaisuus `cdsproj`-tiedostossa.
    > - Voit määrvalita MSBuild-määrityksen `Release`, jos haluat antaa tuotannon koonti version. Esimerkki: `msbuild /p:configuration=Release`
    > - Jos kohtaat virheen, joka kertoo *moniselitteisestä projektin nimestä* , kun käytät `msbuild` komentoa ratkaisusi, varmista, että ratkaisun nimi ja projektin nimi eivät ole samat.

4. Luodut ratkaisun tiedostot sijaitsevat `\bin\debug\`-kansion sisällä sen jälkeen, kun koonti versio on onnistunut.
5. [Tuo ratkaisun manuaalisesti Common Data Service](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customize/import-update-upgrade-solution) verkko portaalin avulla tai tarkista organisaatiosi ja [käyttöönotto](#deploying-code-components) - [OSIESI todentaminen](#authenticating-to-your-organization) powerapps CLI-komentojen avulla.

## <a name="authenticating-to-your-organization"></a>Todentaminen organisaatiollesi

Voit ottaa koodi komponentit käyttöön suoraan Powerappsin kautta käyttämällä todentamista Common Data Service-organisaatioon ja painamalla sitten päivitettyjä osia. Luo todennus profiili noudattamalla seuraavia ohjeita, muodosta yhteys Common Data Service ja työnnä päivitetyt osat. 
 
1. Luo todentamis profiilisi käyttäen seuraavaa komentoa: 
 
    ```CLI
    pac auth create --url <your Common Data Service org’s url> 
    ```
 
2. Jos olet aiemmin luonut todentamis profiilin, voit tarkastella kaikkia olemassa olevia profiileja käyttämällä seuraavaa komentoa: 

   ```CLI
    pac auth list 
   ```
 
3. Jos haluat vaihtaa aiemmin luotujen todentamis profiilien välillä, käytä seuraavaa komentoa: 
   
   ```CLI
    Pac auth select --index <index of the active profile>
    ``` 

4. Saat perustiedot organisaatiosta käyttämällä seuraavaa komentoa. Tämä muodostetaan käyttämällä oletus todennus profiilia. 

    ```CLI
    pac org who 
    ```
 
5. Jos haluat poistaa tietyn todentamis profiilin, käytä komentoa `pac auth delete --index < index of the profile >`. 
6. Jos haluat tyhjentää kaikki todennus profiilit paikallisesta tieto koneesta, käytä komentoa `pac auth clear`. Tämä toiminto on peruuttamaton, koska se poistaa `authprofile.json` tiedosto-ja tunnus väli muisti tiedoston kokonaan paikallisesta tieto koneesta. 

## <a name="deploying-code-components"></a>Otetaan koodi komponentteja käyttöön 

Kun olet luonut todentamis profiilin onnistuneesti, voit aloittaa koodi osien työntämistä Common Data Service esiintymään, jossa on kaikki uusimmat muutokset. @No__t_0-ominaisuus nopeuttaa sisäisen kehittäjä jakson kehitystä, koska se ohittaa koodi komponentin versiointi vaatimukset ja ei edellytä, että rakennat ratkaisusi (cdsproj), jotta voit tuoda koodi komponentin. Jos haluat käyttää `push`-ominaisuutta, toimi seuraavasti:

1. Varmista, että sinulla on luomasi kelvollinen todennus profiili.
2. Siirry päähakemistoon, jossa koodi komponentti projekti luodaan.
3. Suorita komento `pac pcf push --publisher-prefix <your publisher prefix>`.

   > [!NOTE]
   > @No__t_0-komennon kanssa käyttämäsi julkaisijan etuliitteen tulee vastata ratkaisusi julkaisijan etuliitettä, johon komponentit sisällytetään.

## <a name="how-to-remove-components-from-a-solution"></a>Komponenttien poistaminen ratkaisusta

Jos haluat poistaa koodi osan ratkaisun tiedostosta:

1.  Muokkaa `cdsproj` tiedostoa ratkaisun projekti hakemistossa ja poista viitta ukset komponenttiin. Tässä on esimerkki komponentti viittauksesta:

   ```XML
   <ItemGroup>
       <Projectreference Include="..\pcf_component\pcf_component.pcfproj">
         <Project>0481bd83-ffb0-4b70-b526-e0b3dd63e7ef</Project>
         <Name>pcf_component </Name>
         <Targets>Build</Targets>
         <referenceOutputAssembly>false</referenceOutputAssembly>
         <OutputItemType>Content</OutputItemType>
         <CopyToOutputDirectory>Always</CopyToOutputDirectory>
       </Projectreference>
   </ItemGroup>
   ```

2. Suorita uudelleenmuodostus (tai Puhdista) käyttämällä seuraavaa komentoa:
   
    ```CLI
    msbuild /t:rebuild
    ```

### <a name="see-also"></a>Katso myös

[Koodi komponenttien lisääminen kenttään tai entiteettiin mallipohjaisissa sovelluksissa](add-custom-controls-to-a-field-or-entity.md)<br/>
[Komponenttien lisääminen kangas sovellukseen](component-framework-for-canvas-apps.md#add-components-to-a-canvas-app)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](overview.md)

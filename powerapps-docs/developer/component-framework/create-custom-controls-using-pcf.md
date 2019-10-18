---
title: Koodi komponentin luominen ja muodostaminen | Microsoft Docs
description: Aloita komponentin luominen PowerApps Component Framework-työkalujen avulla
keywords: PowerApps Component Framework, koodi komponentit, komponentti kehys
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 06/20/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2cbf58a-9112-45c2-b823-2c07a310714c
ms.openlocfilehash: 286458da2ed7b7b94f92b86355bf8785161ef778
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72347011"
---
# <a name="create-and-build-a-code-component"></a>Luo ja Rakenna koodi komponentti

Tässä ohje aiheessa kerrotaan, miten voit luoda ja ottaa käyttöön koodi komponentteja käyttämällä Powerappsia. Varmista, että olet asentanut [Microsoft POWERAPPS CLI](https://aka.ms/PowerAppsCLI).

## <a name="create-a-new-component"></a>Luo uusi komponentti

Aloita avaamalla **kehittäjän komento rivi VS 2017** POWERAPPS CLI-asennuksen asentamisen jälkeen.

1. Luo kehittäjän komento kehotteeseen VS 2017 uusi kansio paikallisessa tieto koneessa, esimerkiksi *C:\windows\tiedostot\tiedostot\oma_pcf_component* käyttäen komentoa `mkdir <Specify the folder name>`.
2. Siirry juuri luotuun kansioon käyttämällä komentoa `cd <specify your new folder path>`.
3. Luo uusi komponentti projekti suorittamalla seuraava komento suorittamalla joitakin perusparametreja:

    `pac pcf init --namespace <specify your namespace here> --name <put component name here> --template <component type>`
 
   > [!NOTE]
   > Tällä hetkellä PowerApps CLI tukee kahdentyyppisiä komponentteja: **Field** ja **DataSet**.  Pohjaan perustuvia sovelluksia varten vain **kenttä** tyyppi on tuettu tälle kokeellisen esikatselun yhteydessä.

4. Jos haluat noutaa kaikki vaaditut Projektiriippuvuudet, suorita komento `npm install`.
5. Avaa projekti kansiosi `C:\Users\<your name>\Documents\<My_PCF_Component>` missä tahansa valitsemissasi kehittäjä ympäristössä ja aloita koodi komponentin kehittäminen. Nopein tapa aloittaa suorittaminen on suorittaa `code .` komento riviltä, kun olet `C:\Users\<your name>\Documents\<My_PCF_Component>` hakemistossa. Tämä komento avaa komponentti projektisi Visual Studio koodissa.

## <a name="build-your-component"></a>Rakenna oma komponenttiisi

Voit muodostaa komponentti projektin avaamalla Project-kansion, joka sisältää `package.json` Visual Studio koodissa ja käyttämällä komentoa (Ctrl-Shift-B) ja valitsemalla sitten koonti asetukset. Vaihtoehtoisesti voit luoda osan nopeasti käyttämällä `npm run build`-komentoa kehittäjien komento kehotteeseen VS 2017-ikkunassa.

> [!TIP]
> Jos haluat tehdä komponentin virheen korjauksen koonti toiminnon aikana tai sen jälkeen, Lue artikkeli [koodi komponentin virheen korjaus](debugging-custom-controls.md).

Kun olet suorittanut komponentti logiikan kohteessa TypeScript, sinun on niputtaa kaikki koodi komponentti elementit ratkaisun tiedostoon, jotta voit tuoda ratkaisun Common Data Service. Lisä tietoja: [koodi komponentin pakkaaminen](import-custom-controls.md)

## <a name="known-configuration-issues-and-workarounds"></a>Tunnetut määritys ongelmat ja-ratkaisut

**MSBUILD-virhe MSB4036:**

1. Projekti tiedoston tehtävän nimi on sama kuin tehtävä luokan nimi.
2. Tehtävä luokka on julkinen ja toteuttaa Microsoft. Build. Framework. ITask-liittymän.
3. Tehtävä on määritetty oikein *\<UsingTask >* projekti tiedostossa tai Path-hakemistossa olevissa *. tasks-tiedostoissa.

**Päätös lauselma**

1. Avaa Visual Studio asennus ohjelma. 
1. Visual Studio 2017, valitse **Muokkaa**. 
1. Valitse **erilliset osat**.
1. Valitse koodi työkalut-kohdassa **NuGet-kohteet & muodosta tehtäviä**.

**Julkaisijan etuliite**

Jos komponentti luodaan käyttämällä powerapps CLI työkaluja-versiota, joka on pienempi kuin 0.4.3, näkyviin tulee virhe yritettäessä tuoda ratkaisun tiedosto uudelleen Common Data Service. Virhe aiheutuu siitä, että juuri tuotu osan nimi lisätään nyt julkaisijan etuliitteen avulla, jotta varmistetaan sen ainutlaatuisuus ja vältetään törmäykset.

**Kierto tapa**:

- Poista ratkaisun sisältävä osa kohteesta Common Data Service. Jos komponentti on jo määritetty lomakkeelle tai ruudukolle, se on poistettava ensin, koska komponentti ratkaisulla on riippuvuussuhde määrityksissä.  
- Tuo uusi päivitys, joka sisältää uusimman CLI-version rakentaman komponentin päivitykset.
- Uudet tuodut osat voidaan nyt määrittää lomakkeissa tai ruudukoissa.  


<!--2. When the components are created with the publisher prefix in mixed or upper case using the new CLI tooling version, it throws an error while importing the solution. This happens because the updated tooling version (0.4.3 and newer) now enforces the platform standard for lower case publisher prefix.

   **Workaround**:

    Update the solution and customizations to ensure that the associated prefix is modified to lower case and import the new solution into Common Data Service.-->


### <a name="see-also"></a>Katso myös

[Virheen korjauksen koodi komponentit](debugging-custom-controls.md)<br/>
[Pakkaa koodi komponentti](import-custom-controls.md)<br/>
[Koodi komponenttien lisääminen kenttään tai entiteettiin](add-custom-controls-to-a-field-or-entity.md)<br/>
[Päivitetään olemassa olevia koodi komponentteja](updating-existing-controls.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](overview.md)

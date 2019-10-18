---
title: Virheen korjauksen koodi komponentit | MicrosoftDocs
description: Koodi osan virheen korjaus Fiddler-ja Native virheen korjaus-toiminnon avulla
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: article
ms.assetid: 18e88d702-3349-4022-a7d8-a9adf52cd34f
ms.author: nabuthuk
author: Nkrb
ms.openlocfilehash: 088792a32f401ddaf7d3a3cd4fd4d5aa9fa472ff
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346919"
---
# <a name="debug-code-components"></a>Virheen korjauksen koodi komponentit

Kun olet suorittanut koodi komponentin logiikan, voit aloittaa koodi komponentin testauksen ja virheen korjauksen `npm start`-komennolla. Tämä muodostaa koodi komponentin ja avaa sen paikallisissa testi valuissa.

> [!div class="mx-imgBorder"]
> ![Testi valjaat 1](media/test-harness-1.png "testi valjaat 1")

Kuten yllä olevassa kuvassa näytetään, selain ikkuna avautuu ja siinä on neljä osaa. Koodi komponentti hahmonnetaan vasemmassa ruudussa, kun oikeanpuoleisessa ruudussa on **kontekstin syötteitä**, **tietojen syötöt**ja **lähdöt** -osiot.

- **Context-syötteiden** avulla voit määrittää lomake kertoimen ja testata koodi komponenttia kunkin lomake kertoimen (verkko, tabletti, Puhelin) kanssa. Tästä on hyötyä, kun koodi komponentti on riippuvainen tietystä form factor-ominaisuudesta.
- **Tieto syötteet** ovat vuorovaikutteinen käyttö liittymä, joka näyttää kaikki [luettelo](manifest-schema-reference/manifest.md) tiedostossa määritetyt ominaisuudet ja niiden [tyypit](manifest-schema-reference/types.md) tai [tyyppi ryhmät](manifest-schema-reference/type-group.md) . Sen avulla voit näpäillä kunkin ominaisuuden vedos tiedot. 
- **Tuotokset** hahmontavat tuloksen aina, kun komponentin [getoutput](reference/control/getoutputs.md) -menetelmää kutsutaan.  

     > [!div class="mx-imgBorder"]
     > ![Testi valjaat 2](media/test-harness-2.png "testi valjaat 2")

> [!NOTE]
> Jos haluat muokata `ControlManifest.Input.xml` tiedostoa tai luoda lisä ominaisuuksia, sinun on käynnistettävä virheen korjaus prosessi uudelleen, ennen kuin ne näkyvät syötteet-osassa.

## <a name="test-code-components-with-mock-data"></a>Testi koodin osat, joissa on vedos tietoja

- *Kentän* tyyppi komponenteissa voit syöttää arvoa ja tyyppiä jokaiselle **Controlmanifest. Input. XML** -tiedostosi ominaisuudelle, joka on määritetty tässä:

   > [!div class="mx-imgBorder"]
   > ![Testi valjaat 2,5]-(media/test-harness-2.5.png "testi valjaat 2,5")

- Tieto *joukon* tyyppi komponenteille voidaan ladata CSV-tiedosto, jossa on testi tietoja. Luot tai viet manuaalisesti. csv-muotoa suoraan ympäristöstäsi. Kun kelvollinen CSV-tiedosto on käytettävissä, se voidaan ladata seuraavassa esitetyllä tavalla:

   > [!div class="mx-imgBorder"]
   > ![testi valjaat 3](media/test-harness-3.png "testi valjaat 3")

- Kun olet latautunut CSV-tiedoston, sido jokainen **Controlmanifest. Input. XML** -tiedostossa määritetty ominaisuus CSV-tiedoston sarakkeeseen. Tämä tehdään poimimalla kunkin ominaisuuden sarake seuraavassa esitetyllä tavalla:

    > [!div class="mx-imgBorder"]
    > ![Testi valjaat 4](media/test-harness-4.png "testi valjaat 4")

- Jos sinulla ei ole mitään ominaisuuksia määritettynä **Controlmanifest. Input. XML** -tiedostossa, kaikki sarakkeet ladataan automaattisesti testi valjaat-luetteloon.

   > [!div class="mx-imgBorder"]
   > ![Testi valjaat 5](media/test-harness-5.png "testi valjaat 5")


## <a name="watch-mode-in-test-harness"></a>Testi sarjan kello tila

Testi valjaat tukee `watch`-tilaa, jonka avulla voit hyödyntää PowerApps Component Framework-projekteja. Jos haluat ottaa `watch`-tilan käyttöön, Aloita testi valjaat komennolla `npm start watch`. @No__t_0 tilassa mihin tahansa seuraavista komponentti varoista tehdyt muutokset otetaan automaattisesti huomioon testi valjaat-toiminnossa käynnistämättä sitä uudelleen:

1.  `index.ts` tiedosto.
2.  `ControlManifest.Input.xml` tiedosto.
3.  Tuodut kirjastot `index.ts`.
4.  Kaikki luettelo tiedostossa luetellut resurssit.

## <a name="debug-code-components-using-native-browsers"></a>Virheen korjauksen koodi komponentit alkuperäisten selainten avulla

Voit käyttää selaimen virheen korjaus ominaisuuksia osan toiminnan tarkkailemaan. Jokainen selain tarjoaa sinulle virheen korjaus työkalun, jonka avulla voit korjata koodisi suoraan selaimessa. Yleensä voit aktivoida virheen korjauksen selaimessasi painamalla **F12** -näppäintä näyttämään alkuperäisen kehittäjä työkalun, jota käytetään virheen korjaukseen.

Esimerkiksi **Microsoft Edgessä**:

- Avaa inspektori painamalla **F12** -näppäintä.
- Valitse osa.
- Siirry yläpalkissa **virheen korjaus toimintoon** ja Hae sitten Haku palkin luettelo tiedostossa kuvattua komponentin nimeä. Kirjoita esimerkiksi osan nimi, kuten `Hello World component`.

     > [!div class="mx-imgBorder"]
     > ![Virheen korjauksen osan](media/debug-control.png "virheen korjauksen osa")

> [!NOTE]
> On aina hyvä käytäntö, että asetat keskeytys kohdat komponentin elin kaaren menetelmiin, kuten [init](reference/control/init.md) ja [updateview](reference/control/updateview.md).

Voit myös käsitellä komponenttia paikallisesti reaaliajassa ja tarkkailla DOM-elementtejä asettamalla keskeytys kohdan *lähteet* -väli lehdelle seuraavassa esitetyllä tavalla:

> [!div class="mx-imgBorder"]
> ![Virheen korjauksen osan](media/debug-control-1.png "virheen korjauksen osa 1")

## <a name="fiddler-autoresponder"></a>Fiddler automaattivastaaja

Käytä Fiddler automaattivastaaja koodi komponenttien virheen korjaukseen nopeasti. Asenna [Fiddler](https://www.telerik.com/download/fiddler) ja Määritä [automaattivastaaja](https://docs.microsoft.com/dynamics365/customer-engagement/developer/streamline-javascript-development-fiddler-autoresponder)noudattamalla ohjeita.

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](overview.md)

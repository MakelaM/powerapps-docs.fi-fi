---
title: Tietojen tuominen mallipohjaisissa sovelluksissa | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
- D365CE
ms.openlocfilehash: 37e9602d48bbfbb802afefa0f6d47fad241dc6f5
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/19/2019
ms.locfileid: "63321659"
---
# <a name="import-data"></a>Tietojen tuominen

Seuraavassa on ohjeet tietojen tuomiseen sovellukseesi, jos tietosi on tallennettu laskentataulukkoon, puhelimeen tai sähköpostiohjelmaan. Voit esimerkiksi haluta tuoda asiakkaiden yhteystietoluettelon Excel-laskentataulukosta sovellukseen, jotta kaikki asiakastiedot olisivat yhdessä paikassa.
  
## <a name="step-1-get-your-import-file-ready"></a>Vaihe 1: Tuontitiedoston valmistelu  
Vie tiedot ensin Excel-tiedostoon. Seuraavia tiedostomuotoja tuetaan:
 - Excel-työkirja (.xlsx)
 - Pilkuin erotellut arvot (.csv)
  
Suurin sallittu koko .zip-tiedostolle on 32 Mt. Muiden tiedostomuotojen suurin sallittu tiedostokoko on 8 Mt.  
  
### <a name="export-data-from-an-email-program"></a>Sähköpostiohjelman tietojen vienti  
  
1.  Vie tiedot .csv-tiedostoon.  
  
     Jos tarvitset apua yhteystietojen viemiseen sähköpostiohjelmasta, avaa ohjelman Ohje-kohta ja hae tietoa hakusanalla vie tai vienti. Etsi aiheita, joiden otsikot sisältävät sanat ”yhteystietojen vienti”, ”osoitekirjan vienti” tai ”ohjattu vientitoiminto”.  
  
2.  Tallenna tiedosto sellaiseen sijaintiin, josta löydät sen helposti myöhemmin.  
  
### <a name="export-data-from-a-spreadsheet"></a>Laskentataulukon tietojen vienti  
  
1.  Avaa laskentataulukko.  
  
2.  Muokkaa tarvittaessa laskentataulukon sarakkeen nimeä, jotta se vastaa täysin tässä olevaa nimeä.  
  
    > [!WARNING]
    > Laskentataulukossa ei kuitenkaan tarvitse olla kaikkia lueteltuja sarakkeiden nimiä. Jos laskentataulukossa kuitenkin on sarakkeen nimi, sen on vastattava tarkalleen luettelossa olevaa nimeä, tai muuten tuonti ei onnistu. Muista välilyönnit. Huomaa, että sanassa ”Email” ei ole yhdysmerkkiä.  

    |**Laskentataulukon sarakkeen nimi (kirjoitusasun on oltava täysin sama)**|
    |---------|
    |Etunimi|  
    |Toinen nimi|  
    |Suku nimi|  
    |Työpuhelin|  
    |Matkapuhelin|  
    |Tehtävänimike|  
    |Työpaikan katuosoite|  
    |Työpaikan postitoimipaikka|  
    |Työpaikan osavaltio|  
    |Työpaikan postinumero|  
    |Työpaikan maa tai alue|  
    |Sähköpostiosoite|  
  
3.  Tallenna tiedosto.  
  
### <a name="export-data-from-your-phone"></a>Puhelimen tietojen vienti  

Vie tiedot (esimerkiksi yhteystiedot) puhelimesta tietokoneeseen USB-kaapelin tai sovelluksen avulla.
  
Jos tarvitset apua yhteystietojen viemiseen puhelimestasi, hae haluamallasi hakukoneella (kuten Bing) tietoa kirjoittamalla hakusanoiksi ”yhteystietojen vienti puhelimesta”.  
  
Etsi sovellus puhelimesi verkkokaupasta.  
  
## <a name="step-2-import-the-file"></a>Vaihe 2: Tuo tiedosto 
  
1. Valitse komentopalkissa **Tuo Excelistä** tai **Tuo CSV-tiedostosta**.

   > [!div class="mx-imgBorder"]
   > ![PowerAppsin päävalikko](media/import.png "PowerAppsin päävalikko")
  
2. Selaa kansioon, johon tallensit tiedoston, joka sisältää viedyt yhteystiedot. Valitse tiedosto, valitse **Avaa** ja valitse **Seuraava**.  
  
   > [!TIP]
   > Voit tuoda vain yhden tiedoston kerrallaan. Jos haluat tuoda lisää tiedostoja, suorita ohjattu toiminto myöhemmin uudelleen.
   
3. Tarkista tiedostonimi ja varmista, että kentän ja tiedon erottimet ovat oikein **Tarkista yhdistämismääritys** -asetuksen avulla. Jos kaikki näyttää hyvältä, valitse **Lopeta tuonti**.  
 
## <a name="step-3-check-that-the-import-is-successful"></a>Vaihe 3: Tarkista, että tuonti on onnistunut

Kun ohjattu toiminto on suoritettu, tarkista tiedot (esimerkiksi yhteystietoluettelo) ja varmista, että ne on tuotu oikein.  
  
1. Valitse päävalikosta **Yhteystiedot**.
  
2. Selaa yhteystietoluettelo läpi. Tarkista, että kaikki henkilöt löytyvät luettelosta, ja varmista kenttien sisältö.

## <a name="import-double-byte-characters"></a>Kaksitavuisten merkkien tuonti 

Jos tuot kaksitavuisia merkkejä sisältäviä tietoja itäaasialaisilla kielillä, varmista, että tiedoston koodauksena on UTF-8 BOM. Pelkkä UTF-8 ei välttämättä riitä.

1. Avaa CSV-tiedosto Visual Studio Coden avulla.
2. Napsauta alapalkissa otsikkoa **UTF-8** (ponnahdusikkuna avautuu). 
3. Valitse **Tallenna käyttämällä koodausta**. 

Nyt voit valita UTF-8 BOM -koodauksen tiedostoon.


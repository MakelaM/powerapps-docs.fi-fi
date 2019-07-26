---
title: Vieminen staattiseen Excel-laskenta taulukkoon mallipohjaisessa sovelluksessa | MicrosoftDocs
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
ms.openlocfilehash: 82d14f70bbdcd9faddc467636db255f0b512830e
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/19/2019
ms.locfileid: "61544817"
---
# <a name="export-to-an-excel-static-worksheet"></a>Vie staattiseen Excel-laskenta taulukkoon

Kun haluat antaa tietoja sovelluksesi tiedoista henkilölle, jolla ei ole käyttö oikeutta sovellukseen, tai sinulla on tietoja, jotka eivät muutu usein, harkitse sovellus tietojen viemistä staattiseen Office Excel-laskenta taulukkoon.

Voit viedä enintään 100 000 tietuetta kerrallaan. Oletus arvon mukaan mallipohjainen sovellus luetteloi enintään 50 tietuetta sivua kohden. Valitse luettelon alalaidassa olevat **sivu** nuolet, jos haluat tarkastella muita sivuja.  
  
## <a name="export-data-to-an-excel-static-worksheet"></a>Tietojen vieminen staattiseen Excel-laskenta taulukkoon  
Voit halutessasi viedä tiedot Excelin staattiseen laskenta taulukkoon kaikissa tietue tyypeissä. Joissakin tapa uksissa muoto voi kuitenkin olla vanha, tai tietoja ei ehkä suodateta sovelluksessa näkemiesi tietojen mukaan.  
  
1. Avaa tietue luettelo sovelluksessa, valitse **Vie Exceliin**-kohdan oikealla puolella oleva nuoli ja valitse sitten **Staattinen laskenta taulukko (vain sivu)** .  
  
2. Oletus arvon mukaan viety laskenta taulukko sisältää kentät, jotka näkyvät luettelona käyttäen samaa kenttien järjestystä, lajittelua ja kenttien leveyksiä. Jos haluat tehdä muutoksia sarakkeisiin Erikoishaku-näkymässä, valitse **Muokkaa sarakkeita**. 
  
3. Valitse **Tallenna** ja tallenna sitten. xlsx-tiedosto. Kirjoita muistiin sijainti, johon tallensit tiedoston.  
  
   > [!NOTE]
   > Jos aiot muokata Data tiedostoa myöhemmin, on suositeltavaa, että tallennat tiedoston ennen sen avaamista. Muussa tapa uksessa saatat saada tämän virhe sanoman: **Excel ei voi avata tai tallentaa enempää tiedostoja, koska käytettävissä oleva muisti tai levy tila ei riitä.**  
   > 
   > Voit korjata ongelman seuraavasti:  
   > 
   > 1. Avaa Excel ja siirry kohtaan **tiedosto** > **Asetukset** > **valvonta keskus** > **Asetukset keskus asetukset** > **Protected View**.  
   > 2.  Tyhjennä **suojatussa näkymässä**kaikki kolme kohdetta.  
   > 3.  Valitse **OK** >  **.**  
   > 
   > Suosittelemme yhä vahvasti, että tallennat ja avaat sitten Data tiedoston, sen sijaan, että poistaisit käytöstä suojaus näkymän, joka saattaa vaarantaa tieto koneesi.  


4. Avaa Excel ja avaa edellisessä vaiheessa tallentamasi. xlsx-tiedosto.  
  
   Oletus arvon mukaan viety laskenta taulukko sisältää kentät, jotka näkyvät luettelona käyttäen samaa kenttien järjestystä, lajittelua ja kenttien leveyksiä.  
  
## <a name="tips"></a>Vinkkejä  
  
- Voit lähettää staattisen viedyn laskenta taulukon sähkö postiin kenelle tahansa tai tallentaa sen jaettuun tiedostoon. Jokainen, joka avaa tiedoston, näkee kaikki tiedoston tiedot.
  
- Et voi muuttaa järjestelmä näkymän, kuten **kaikkien aktiivisten tiliesi**, sarakkeita. Sinun täytyy joko mukauttaa näkymää, joka edellyttää järjestelmänvalvojan tai Järjestelmämukauttajan käyttö oikeus roolia, tai luoda oma näkymä käyttämällä Erikoishaku-näkymää nykyisen näkymän perusteella.  
    
- Mallipohjaisissa sovelluksissa valuutta-arvot viedään Exceliin lukuina. Kun olet suorittanut viennin, voit muotoilla tiedot valuutaksi valitsemalla Excelin ohje aiheesta lukujen näyttäminen valuuttana.
  
- Sovelluksessa näkyvät päivä määrä-ja aika-arvot näkyvät vain päivä määränä, kun viet tiedoston Exceliin, mutta solussa näkyy sekä päivä määrä että aika.  
  
- Jos aiot tehdä muutoksia ja tuoda Data tiedoston takaisin sovellukseen, muista, että suojatut, lasketut ja yhdistelmä kentät (kuten koko nimi) ovat vain luku-muotoa, eikä niitä voi tuoda sovellukseen. Pystyt muokkaamaan näitä kenttiä Excelissä, mutta kun tuot tiedot takaisin sovellukseen, näitä kenttiä ei päivitetä. Jos haluat päivittää nämä kentät, kuten yhteys henkilön nimen, on suositeltavaa, että käytät kyseistä näkymää tietojen viemiseen, sen päivittämiseen Excelissä ja sen tuomiseen takaisin sovellukseen muutosten tekemistä varten.  
  


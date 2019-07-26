---
title: Vie Excel-pivot-taulukkoon mallipohjaisessa Powerappissa | MicrosoftDocs
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
ms.openlocfilehash: 90cf377f10a99dbcece1e5f556cb50e678099744
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/19/2019
ms.locfileid: "61544978"
---
# <a name="export-to-an-excel-pivottable"></a>Vieminen Excelin pivot-taulukkoon


Voit viedä sovellus tiedot Office Excel-pivot-taulukkoon, jotta näet tietojen kuviot ja trendit. Excel-pivot-taulukko on erinomainen tapa tiivistää, analysoida, tutkia ja esittelee sovellus tietojasi. Voit viedä enintään 100 000 tietuetta kerrallaan.  
  

## <a name="export-data-to-an-excel-pivottable"></a>Vie tiedot Excel-pivot-taulukkoon  
Mahdollisuus viedä tietoja Excel-pivot-taulukkoon ei ole käytettävissä kaikissa tietue tyypeissä. Jos et näe asetusta, se ei ole käytettävissä kyseisessä tietueessa.  
  
1. Avaa sovelluksesi tietue luettelo, valitse **Vie Exceliin**-kohdan oikealla puolella oleva nuoli ja valitse sitten **dynaaminen pivot-taulukko**.  
  
2. Valitse pivot-Excel-valinta ikkunan **Valitse sarakkeet** -kohdassa sarake asetukset ja valitse sitten **Vie**.  
  
   Oletus arvon mukaan **pivot-taulukon kenttä luettelona** ovat vain kentät, jotka näytetään pivot-taulukko-luetteloiden **Valitse sarakkeet** -kohdassa.  
  
3. Valitse **Tallenna** ja tallenna sitten. xlsx-tiedosto. Kirjoita muistiin sijainti, johon tallensit tiedoston.  
  
   > [!NOTE]
   > Jos aiot muokata Data tiedostoa myöhemmin, on suositeltavaa, että tallennat tiedoston ennen sen avaamista. Muussa tapa uksessa saatat saada tämän virhe sanoman: **Excel ei voi avata tai tallentaa enempää tiedostoja, koska käytettävissä oleva muisti tai levy tila ei riitä.**  
   > 
   > Ongelman korjaaminen:  
   > 
   > 1. Avaa Excel ja siirry kohtaan **tiedosto** > **Asetukset** > **valvonta keskus**.  
   > 2. Valitse **luottamus keskuksen asetukset** ja valitse sitten **Protected View**.  
   > 3. Tyhjennä **suojatussa näkymässä**kaikkien kolmen kohteen valinta ruudut.  
   > 4. Valitse **OK** >  **.**  
   > 
   > Suosittelemme yhä vahvasti, että tallennat ja avaat sitten Data tiedoston, sen sijaan, että poistaisit käytöstä suojaus näkymän, joka saattaa vaarantaa tieto koneesi.  
  
4. Avaa Excel ja avaa edellisessä vaiheessa tallentamasi. xlsx-tiedosto.  
  
5. Jos näet suojaus varoituksen **ulkoiset tieto yhteydet on poistettu käytöstä**, valitse **Ota sisältö käyttöön**.  
  
6. Jos haluat päivittää tiedoston tiedot, valitse **tiedot** -väli lehdestä **Päivitä powerappsissa**.  
  
7. Vedä kentät Pivot-taulukon kenttä-listasta pivot-taulukkoon. Saat lisä tietoja Excelin ohjeesta.  
  
## <a name="tips"></a>Vinkkejä  
  
- Powerappsissa valuutta-arvot viedään Exceliin lukuina. Kun olet suorittanut viemisen, Lue Excel-Ohje aiheesta lukujen näyttäminen valuuttana, jos haluat muotoilla tiedot valuuttana.
  
- Sovelluksessa näkyvät päivä määrä-ja aika-arvot näkyvät vain päivä määränä, kun viet tiedoston Exceliin, mutta solussa näkyy sekä päivä määrä että aika.  
  
- Jos aiot tehdä muutoksia ja tuoda Data tiedoston takaisin sovellukseen, muista, että suojatut, lasketut ja yhdistelmä kentät (kuten koko nimi) ovat vain luku-muotoa, eikä niitä voi tuoda sovellukseen. Pystyt muokkaamaan näitä kenttiä Excelissä, mutta kun tuot tiedot takaisin sovellukseen, näitä kenttiä ei päivitetä. Jos haluat päivittää nämä kentät, kuten yhteys henkilön nimen, suosittelemme, että käytät kyseistä näkymää tietojesi viemiseen, päivität sen Excelissä ja tuot sen takaisin sovellukseen muutosten tekemistä varten.  
  
 

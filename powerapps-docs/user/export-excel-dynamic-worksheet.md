---
title: Vie Excelin dynaamiseen laskenta taulukkoon mallipohjaisten Powerappsin avulla | MicrosoftDocs
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
ms.openlocfilehash: 804deaf9f12d4c73abbfd8f414f27307fe5aa7d6
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/19/2019
ms.locfileid: "63318745"
---
# <a name="export-to-an-excel-dynamic-worksheet"></a>Vie Excelin dynaamiseen laskenta taulukkoon

Vie sovelluksesi tiedot Office Excel-laskenta taulukkoon, jotta käyttäjät voivat saada uusimmat tiedot. Kuvittele, että yrityksesi toimitus johtaja saa tarvitsemasi tärkeät tiedot tarvitsematta siirtyä sovellukseen, vaan ainoastaan avata Excel-linkin työpöydälleen. Voit viedä enintään 100 000 tietuetta kerrallaan.    
  
## <a name="export-data-to-an-excel-dynamic-worksheet"></a>Vie tiedot Excelin dynaamiseen laskenta taulukkoon  

Tietoja ei voi viedä dynaamiseen laskenta taulukkoon Excelissä kaikille tietue tyypeille. Jos et näe asetusta, se ei ole käytettävissä kyseisessä tietueessa.  
  
1. Avaa tietue luettelo sovelluksessa ja valitse nuoli oikealta **Vie Exceliin**. 
  
2. Valitse **dynaaminen laskenta taulukko**.  
  
3. Valitse **Valitse sarakkeet dynaamisessa Excelissä** -valinta ikkunassa sarake asetukset ja valitse sitten **Vie**.  
  
4. Valitse **Tallenna** ja tallenna sitten. xlsx-tiedosto. Kirjoita muistiin sijainti, johon tallensit tiedoston.  
  
   > [!NOTE]
   > Jos aiot muokata Data tiedostoa myöhemmin, on suositeltavaa, että tallennat tiedoston ennen sen avaamista. Muussa tapa uksessa saatat saada tämän virhe sanoman: **Excel ei voi avata tai tallentaa enempää tiedostoja, koska käytettävissä oleva muisti tai levy tila ei riitä.**  
   > 
   > Ongelman korjaaminen:  
   > 
   >    1. Avaa Excel ja siirry kohtaan **tiedosto** > **Asetukset** > **valvonta keskus** **Asetukset keskus asetukset** > **Protected View**.  
   >    2. Tyhjennä **suojatussa näkymässä**kaikki kolme kohdetta.  
   >    3. Valitse **OK** >  **.**  
   >     
   >    Suosittelemme yhä vahvasti, että tallennat ja avaat sitten Data tiedoston, sen sijaan, että poistaisit käytöstä suojaus näkymän, joka saattaa vaarantaa tieto koneesi.  
  
5. Avaa Excel ja avaa edellisessä vaiheessa tallentamasi. xlsx-tiedosto.  
  
6. Jos näet suojaus varoituksen **ulkoiset tieto yhteydet on poistettu käytöstä**, valitse **Ota sisältö käyttöön**.  
  
7. Jos haluat päivittää tiedoston tiedot, valitse **tiedot** -väli lehdestä **Päivitä powerappsissa**.  
  
   > [!NOTE]
   > Jos sinulla on Puhelin numero, joka alkaa **+** merkki jonolla tai **–** (esimerkiksi + 1-123-456-7890), kun päivität dynaamisen laskenta taulukon, Puhelin numero-kenttä ei Näytä numeroa oikein.   
   >
   > Voit välttää ongelman käyttämällä väli lyöntejä tai **sulkeita ()** seuraavasti: + 1 123-456-7890 tai + 1 (123)-456-7890.  
  
## <a name="tips"></a>Vinkkejä  
  
- Voit lähettää dynaamisen Excel-tiedoston sähköpostitse tai tallentaa sen jaetuksi tiedostoksi, jos vastaanottajat ovat samalla toimi alueella kuin sinä. Kun vastaanottajat avaavat dynaamisen tiedoston, he näkevät tiedot, joita heillä on oikeus tarkastella sovelluksessa, joten niiden näkemä tieto voi poiketa näkemääsi.  
  
- Jotkin järjestelmä näkymät, kuten asiakkaat: Ei kampanja-aktiviteetteja viimeisten kolmen kuukauden aikana, voidaan viedä vain staattiseen Excel-laskenta taulukkoon.  
  
- Powerappsissa valuutta-arvot viedään Exceliin lukuina. Jos haluat muotoilla tiedot valuutaksi sen jälkeen, kun olet suorittanut viennin, Lue Excelin ohje aiheesta Näytä numerot valuuttana.

- Sovelluksessa näkyvät päivä määrä-ja aika-arvot näkyvät vain päivä määränä, kun viet tiedoston Exceliin, mutta solussa näkyy sekä päivä määrä että aika.  
  
- Jos aiot tehdä muutoksia ja tuoda Data tiedoston takaisin sovellukseen, muista, että suojatut, lasketut ja yhdistelmä kentät (kuten koko nimi) ovat vain luku-muotoa, eikä niitä voi tuoda sovellukseen. Pystyt muokkaamaan näitä kenttiä Excelissä, mutta kun tuot tiedot takaisin sovellukseen, näitä kenttiä ei päivitetä. Jos haluat päivittää nämä kentät, kuten yhteys henkilön nimen, on suositeltavaa, että käytät kyseistä näkymää tietojen viemiseen, sen päivittämiseen Excelissä ja sen tuomiseen takaisin sovellukseen muutosten tekemistä varten.  
 


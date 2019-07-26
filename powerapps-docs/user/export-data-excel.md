---
title: Tietojen vieminen Powerappsiin Exceliin | MicrosoftDocs
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
ms.openlocfilehash: 2c23b25c062bc5ac4be26132c63f4cc4a79c3fad
ms.sourcegitcommit: b3fd824cf0d540b964b729686b198c7ccf2c2174
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/21/2019
ms.locfileid: "67316860"
---
# <a name="export-data-to-excel"></a>Tietojen vieminen Exceliin

Pitääkö sinun analysoida tietojasi ja muuntaa nämä tiedot kannekelpoisiksi nimikkeiksi, jotka helpottavat myynnin myyntiä? Nyt voit tehdä tämän, kun viet tiedot Exceliin tai Excel Onlineen. Suurten tieto joukkojen analysoiminen ei myöskään ole ongelma, koska voit viedä enintään 100 000 riviä tietoja.
  
Voit halutessasi viedä staattisia laskenta taulukoita tai dynaamisia laskenta taulukoita, jotka voit tuoda takaisin sovellukseen. Jos tarvitset kehittyneempiä funktioita, voit viedä dynaamisen Pivot-taulukon, jonka avulla on helppo järjestää ja tiivistää tietoja.  
  
Voit viedä tietoja tavalliseen Excel-tiedostoon, jota voit käyttää missä tahansa laitteessa, kuten puhelimessasi, tabletissa tai pöytä tieto koneessa. Tiedot viedään samassa formaatissa, joka näkyy sovelluksessa. Teksti pysyy tekstinä, luvut pysyvät lukuina ja päivä määrät pysyvät päivä määrinä. Kuitenkin, kun viet tietoja sovelluksesta Exceliin, jotkin solu muotoilut saattavat muuttua. Seuraavassa taulukossa on yhteenveto siitä, miten tiedot näkyvät sovelluksissa ja miten solun muotoilu muuttuu, kun viet tiedot Exceliin.  
  
## <a name="cell-format-when-data-is-exported-from-model-driven-apps"></a>Solun muoto, kun tiedot viedään mallipohjaisista sovelluksista
  
| Mallipohjaisten sovellusten tieto muoto |                                            Solun muotoilu Excelissä                                             |
|----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|            Teksti, kaupan käynti tunnus, Puhelin, asetukset ja Hae            |                                                       Näytetään tekstinä, ja asetus joukosta tulee avattava luettelo                                                       |
|                                 Sähkö posti, URL                                 |                                                                        Näytetään yleisenä                                                                         |
|                                   Luku                                   |                                                             Näytetään lukuna ilman ryhmä erotinta                                                             |
|                                  Valuutta                                  |                                                         Näytetään lukuna, eikä se sisällä dollari merkki ($)                                                         |
|                          Vain päivä määrä, päivä määrä ja kellon aika                          |                                                                       Näytetään vain päivä määränä                                                                        |
|                       Lasketut ja koonti kentät                        | Muokattavissa Excelissä, mutta sitä ei voi tuoda takaisin Powerappsiin |
|                               Suojatut kentät                               | Muokattavissa Excelissä, mutta sitä ei voi tuoda takaisin Powerappsiin |
  
## <a name="see-which-type-of-export-works-best-for-you"></a>Tarkista, mikä vienti tyyppi sopii sinulle parhaiten  
  
|                                                                                                               Tehtävä                                                                                                                |                                              Opi lisää                                               |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
|   Tee *Ad-hoc-* tai *Entä jos* -analyysi ilman sovelluksen tietojen muokkaamista. Voit myös tehdä nopean joukko muokkauksen useisiin tietue isiin.   | [Vie Excel Onlineen](export-to-excel-online.md) |
|                                                                   Saa tilanne vedos tiedoista nykyisillä tiedoilla ja ajalla tai haluat kertoa siitä muille.                                                                    |           [Vie staattiseen Excel-laskenta taulukkoon](export-excel-static-worksheet.md)           |
| Saat uusimmat tiedot ja pystyt päivittämään sen Excelissä ja vastaamaan siihen, mitä näet sovelluksessa milloin tahansa. |          [Vie Excelin dynaamiseen laskenta taulukkoon](export-excel-dynamic-worksheet.md)          |
|                                                                      Tarkastele sovelluksen tietoja pivot-taulukossa.                                                                      |                 [Vie Excel-pivot-taulukkoon](export-excel-pivottable.md)                 |



Kun viet tietoja Excelissä (. xlsx-muoto) ja lisäät tai muokkaat sarakkeita, et voi tuoda tietoja takaisin Dynamics 365-sovellukseen. Tätä ei tueta. xlsx-tiedosto muoto.  
  
Jos käytössäsi on Excel 2010, saatat saada tämän virhe sanoman, kun viet tietoja accounts-alueesta: 
 
`The file is corrupt and cannot be opened.`  
  
Virhe sanoma tulee näkyviin Excelin asetuksen vuoksi. Voit korjata ongelman seuraavasti:  
  
1. Avaa Excel 2010.  
  
2. Siirry kohtaan **tiedosto** > **Asetukset**.  
  
3. Siirry kohtaan **luottamus keskuksen** > **luottamus keskuksen asetukset**.  
  
4. Valitse **Protected View** ja tyhjennä sitten kahden ensimmäisen vaihto ehdon valinta ruudut.  
  
5. Valitse **OK** ja sulje **Asetukset** -valinta ikkuna.  
  


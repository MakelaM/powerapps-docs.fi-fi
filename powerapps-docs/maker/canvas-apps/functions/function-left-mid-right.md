---
title: Left-, Mid- ja Right-funktiot| Microsoft Docs
description: Viitetiedot PowerAppsin funktioille Left, Mid ja Right, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ca4fbaf18d7fa993a28f5cbb70f317b4ef5d42fd
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61563575"
---
# <a name="left-mid-and-right-functions-in-powerapps"></a>Left-, Mid- ja Right-funktiot PowerAppsissa
Poimii tekstimerkkijonosta vasemmanpuoleisen osan, keskiosan tai oikeanpuoleisen osan.

## <a name="description"></a>Kuvaus
**Left**-, **Mid**- ja **Right**-funktiot palauttavat merkkijonon osan.

* **Left** palauttaa merkkijonon alun merkit.
* **Mid** palauttaa merkkijonon keskiosan merkit.
* **Right** palauttaa merkkijonon lopun merkit.

Jos määrität yhden merkkijonon argumenttina, funktio palauttaa pyytämäsi merkkijonon osan. Jos määrität yhden sarakkeen [taulukon](../working-with-tables.md), joka sisältää merkkijonoja, funktio palauttaa yksisarakkeisen taulukon niistä osista, joita olet pyytänyt merkkijonoista. Jos määrität usean sarakkeen taulukon, voit muokata sen yhden sarakkeen taulukoksi, kuten kohdassa [taulukoiden käsitteleminen](../working-with-tables.md) on kuvattu.

Jos aloituskohta on negatiivinen tai suurempi kuin merkkijonon loppukohta, **Mid** palauttaa *tyhjän*.  Voit tarkistaa merkkijonon pituuden **[Len](function-len.md)**-funktiolla. Jos pyydät enemmän merkkejä kuin merkkijono sisältää, funktio palauttaa mahdollisimman monta merkkiä.

## <a name="syntax"></a>Syntaksi
**Left**( *String*, *NumberOfCharacters* )<br>**Mid**( *String*, *StartingPosition*, *NumberOfCharacters* )<br>**Right**( *String*, *NumberOfCharacters* )

* *String* – Pakollinen. Merkkijono, josta tulos poimitaan.
* *StartingPosition*  – Pakollinen (vain **Mid**).  Aloituskohta.  Merkkijonon ensimmäinen merkki on kohta 1.
* *Merkkienmäärä* – pakollinen (**vasemmalle** ja **oikealle** vain).  Palautettavien merkkien määrä.  Jos tämä jätetään pois **Mid** funktio, funktio palauttaa osan alkaen sijainnista merkkijonon loppuun saakka.

**Left**( *SingleColumnTable*, *NumberOfCharacters* )<br>**Mid**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters* )<br>**Right**( *SingleColumnTable*, *NumberOfCharacters* )

* *SingleColumnTable* – Pakollinen. Yksisarakkeinen taulukko merkkijonoista, joista haluat poimia tulokset.
* *StartingPosition*  – Pakollinen (vain**Mid**).  Aloituskohta.  Merkkijonon ensimmäinen merkki on kohta 1.
* *Merkkienmäärä* – pakollinen (**vasemmalle** ja **oikealle** vain).  Palautettavien merkkien määrä.  Jos tämä jätetään pois **Mid** funktio, funktio palauttaa osan alkaen sijainnista merkkijonon loppuun saakka.

## <a name="examples"></a>Esimerkkejä
### <a name="single-string"></a>Yksittäinen merkkijono
Tämän osan esimerkeissä käytetään tekstisyöte-ohjausobjektia niiden [tietolähteenä](../working-with-data-sources.md). Ohjausobjektin nimi on **Author**, ja se sisältää merkkijonon "E. E. Cummings".

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Left( Author.Text, 5 )** |Poimii viisi merkkiä merkkijonon alusta. |"E. E." |
| **Mid( Author.Text, 7, 4 )** |Poimii merkkijonosta enintään neljä merkkiä seitsemännestä merkistä alkaen. |"Cumm" |
| **Mid (Author.Text, 7)** |Poimii kaikki merkkiä seitsemännestä merkistä merkkijonosta. |”Cummings” |
| **Right( Author.Text, 5 )** |Poimii viisi merkkiä merkkijonon lopusta. |"mings" |

### <a name="single-column-table"></a>Yksisarakkeinen taulukko
Jokaisessa tämän osan esimerkissä poimitaan merkkijonoja **Address**-[sarakkeesta](../working-with-tables.md#columns) tästä tietolähteestä, jonka nimi on **People**, ja palautetaan yksisarakkeinen taulukko, joka sisältää tulokset:

![](media/function-left-mid-right/people-table.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Left( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;), 8 )** |Poimii kahdeksan ensimmäistä merkkiä jokaisesta merkkijonosta. |<style> img { max-width: none } </style> ![](media/function-left-mid-right/people-table-left.png) |
| **Mid( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;), 5, 7 )** |Poimii merkkijonon keskeltä seitsemän merkkiä jokaisen merkkijonon viidennestä merkistä alkaen. |![](media/function-left-mid-right/people-table-mid.png) |
| **Right( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;), 7 )** |Poimii seitsemän viimeistä merkkiä jokaisesta merkkijonosta. |![](media/function-left-mid-right/people-table-right.png) |

### <a name="step-by-step-example"></a>Vaiheittainen esimerkki
1. Tuo tai luo [kokoelma](../working-with-data-sources.md#collections), jonka nimi on **Inventory**, ja näytä se valikoimassa, kuten kohdan [Kuvien ja tekstin näyttäminen valikoimassa](../show-images-text-gallery-sort-filter.md) ensimmäisessä toimintosarjassa on kuvattu.
2. Määritä ominaisuus **[Text](../controls/properties-core.md)** gallerian alemmalle otsikolle tällä funktiolla:
   
    **Right(ThisItem.ProductName, 3)**
   
    Otsikossa näkyy kunkin tuotteen nimen kolme viimeistä merkkiä.


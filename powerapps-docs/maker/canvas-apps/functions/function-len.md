---
title: Len-funktio | Microsoft Docs
description: Viitetietoja, kuten syntaksi ja esimerkit Len-funktiosta PowerAppsissa
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 06f8e7a80adc7a2175f2da7ab98fb1966d8cf015
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/12/2018
---
# <a name="len-function-in-powerapps"></a>PowerAppsin Len-funktio
Palauttaa tekstin merkkijonon pituuden.

## <a name="description"></a>Kuvaus
Jos määrität yhden merkkijonon argumentiksi, paluuarvo on pituus numerona.  Jos määrität yksisarakkeisen, merkkijonoja sisältävän [taulukon](../working-with-tables.md), paluuarvo on yksisarakkeinen taulukko, joka sisältää kunkin merkkijonon pituuden. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [taulukoiden käyttö](../working-with-tables.md) mukaan.

Jos määrität [tyhjän](function-isblank-isempty.md) merkkijonon, **Len** palauttaa arvon 0.

## <a name="syntax"></a>Syntaksi
**Len**( *merkkijono* )

* *Merkkijono* vaaditaan. Mitattava merkkijono.

**Len**( *YksisarakkeinenTaulukko* )

* *YksisarakkeinenTaulukko* vaaditaan. Yksisarakkeinen taulukko mitattavista merkkijonoista.

## <a name="examples"></a>Esimerkkejä
### <a name="single-string"></a>Yksittäinen merkkijono
Tämän osion esimerkkejä varten [tietolähde](../working-with-data-sources.md) on tekstinsyötön hallinta, jonka nimi on **Tekijä** ja joka sisältää merkkijonon "E. E. Cummings".

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Len( Tekijä.Teksti )** |Mittaa merkkijonon pituuden **Tekijän** hallinnassa. |14 |
| **Len( "" )** |Mittaa tyhjän merkkijonon pituuden. |0 |

### <a name="single-column-table"></a>Yksisarakkeinen taulukko
Tämän osion ensimmäisessä esimerkissä tietolähteen nimi on **Ihmiset** ja se sisältää seuraavat tiedot:

![](media/function-len/people-table.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Len( NäytäSarakkeet(&nbsp;Ihmiset,&nbsp;"Osoite"&nbsp;) )** |**Ihmiset**-taulukon **Osoite**[-sarakkeessa](../working-with-tables.md#columns):<br><ul><li>Mittaa jokaisen merkkijonon pituuden.</li><li>Palauttaa yksisarakkeisen taulukon, joka sisältää jokaisen merkkijonon pituuden.</li> |<style> img { max-width: none } </style> ![](media/function-len/people-table-len.png) |
| **Len( [ "Hello", "to the", "World", "" ] )** |Sisäisen taulukon **[Arvo](function-value.md)**-sarakkeessa:<br><ul><li>Mittaa jokaisen merkkijonon pituuden.</li><li>Palauttaa yksisarakkeisen taulukon, joka sisältää jokaisen merkkijonon pituuden.</li> |![](media/function-len/people-table-len-inline.png) |


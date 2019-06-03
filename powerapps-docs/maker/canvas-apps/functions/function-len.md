---
title: Len-funktio | Microsoft Docs
description: Viitetietoja Len-funktiosta PowerAppsissa, kuten syntaksi ja esimerkit
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
ms.openlocfilehash: d99cf1129ae23eda97b79457cb2b93db6a74a5ea
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/24/2019
ms.locfileid: "66216014"
---
# <a name="len-function-in-powerapps"></a>PowerAppsin Len-funktio
Palauttaa tekstin merkkijonon pituuden.

## <a name="description"></a>Kuvaus
Jos määrität yhden merkkijonon argumentiksi, paluuarvo on pituus numerona.  Jos määrität yksisarakkeisen, merkkijonoja sisältävän [taulukon](../working-with-tables.md), paluuarvo on yksisarakkeinen taulukko, joka sisältää kunkin merkkijonon pituuden. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [Taulukoiden käyttö](../working-with-tables.md) mukaan.

Jos määrität [tyhjä](function-isblank-isempty.md) merkkijono, **Len** palauttaa arvon 0.

## <a name="syntax"></a>Syntaksi
**Len**( *String* )

* *String* – Pakollinen. Mitattava merkkijono.

**Len**( *SingleColumnTable* )

* *SingleColumnTable* – vaaditaan. Yksisarakkeinen taulukko mitattavista merkkijonoista.

## <a name="examples"></a>Esimerkkejä
### <a name="single-string"></a>Yksittäinen merkkijono
Tämän osion esimerkkejä varten [tietolähde](../working-with-data-sources.md) on tekstinsyöttöohjausobjekti, jonka nimi on **Author** ja joka sisältää merkkijonon "E. E. Cummings".

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Len( Author.Text )** |Mittaa merkkijonon pituuden **Author**-ohjausobjektissa. |14 |
| **Len( "" )** |Mittaa tyhjän merkkijonon pituuden. |0 |

### <a name="single-column-table"></a>Yksisarakkeinen taulukko
Tämän osion ensimmäisessä esimerkissä tietolähteen nimi on **People** ja se sisältää seuraavat tiedot:

![](media/function-len/people-table.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Len( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;) )** |**People**-taulukon **Address**[-sarakkeessa](../working-with-tables.md#columns):<br><ul><li>Mittaa jokaisen merkkijonon pituuden.</li><li>Palauttaa yksisarakkeisen taulukon, joka sisältää jokaisen merkkijonon pituuden.</li> |<style> img { max-width: none } </style> ![](media/function-len/people-table-len.png) |
| **Len( [ "Hello", "to the", "World", "" ] )** |Sisäisen taulukon **[Value](function-value.md)** -sarakkeessa:<br><ul><li>Mittaa jokaisen merkkijonon pituuden.</li><li>Palauttaa yksisarakkeisen taulukon, joka sisältää jokaisen merkkijonon pituuden.</li> |![](media/function-len/people-table-len-inline.png) |


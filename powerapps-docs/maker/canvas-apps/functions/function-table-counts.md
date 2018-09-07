---
title: Count-, CountA-, CountIf- ja CountRows-funktiot | Microsoft Docs
description: PowerAppsin Count-, CountA-, CounfIf- ja CountRows-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkki
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
ms.openlocfilehash: 717baab028b480063f76b799a1267155464d8ac3
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42828208"
---
# <a name="count-counta-countif-and-countrows-functions-in-powerapps"></a>PowerAppsin Count-, CountA-, CountIf- ja CountRows-funktiot
Laskee kaikki [tietueet](../working-with-tables.md#records) [taulukossa](../working-with-tables.md), tai laskee kaikki tietueet, jotka täyttävät ehdon.

## <a name="description"></a>Kuvaus
**Count**-funktio laskee yksisarakkeisessa taulukossa niiden tietueiden lukumäärän, jotka sisältävät numeron.

**CountA**-funktio laskee yksisarakkeisessa taulukossa niiden tietueiden lukumäärän, jotka eivät ole *tyhjiä*. Tämän funktion laskentaan sisältyy [tyhjä](function-isblank-isempty.md) teksti ("").

**CountIf**-funktio laskee taulukossa niiden tietueiden lukumäärän, joiden loogisen kaavan arvo on **tosi**.  Kaava voi viitata taulukon [sarakkeisiin](../working-with-tables.md#columns).

**CountRows**-funktio laskee taulukon tietueiden lukumäärän.

Kaikki nämä funktiot palauttavat luvun.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaksi
**Count**( *SingleColumnTable* )<br>
**CountA**( *SingleColumnTable* )

* *SingleColumnTable* – Pakollinen.  Laskettava tietuesarake.  

**CountIf**( *Table*, *LogicalFormula* )

* *Taulukko* – Pakollinen.  Laskettava tietuetaulukko.
* *LogicalFormula* – Pakollinen.  Kullekin taulukon tietueelle arvioitava kaava.  Tietueet, jotka palauttavat arvon **tosi** tälle kaavalle, lasketaan.  Kaava voi viitata taulukon sarakkeisiin.

**CountRows**( *Taulukko* )

* *Taulukko* – Pakollinen.  Laskettava tietuetaulukko.

## <a name="example"></a>Esimerkki
1. Tuo tai luo [kokoelma](../working-with-data-sources.md#collections), jonka nimi on **Inventory** (katso kohdan [Kuvien ja tekstin näyttäminen valikoimassa](../show-images-text-gallery-sort-filter.md) ensimmäinen alitoimintosarja).
2. Lisää selite ja aseta sen **[Teksti](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **CountIf(Inventory, UnitsInStock < 30)**
   
    Selite näyttää luvun **2**, koska kahdella tuotteella (Ganymede ja Callisto) on alle 30 yksikköä varastossa.
3. Lisää toinen selite ja aseta sen **[Teksti](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **CountA(Inventory.UnitsInStock)**
   
    Selite näyttää luvun **5**, joka on ei-tyhjien solujen lukumäärä **UnitsInStock**-sarakkeessa.
4. Lisää toinen selite ja aseta sen **[Teksti](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **CountRows(Inventory)**
   
    Selite näyttää luvun **5**, koska kokoelma sisältää viisi riviä.


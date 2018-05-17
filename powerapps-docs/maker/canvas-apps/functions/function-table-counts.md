---
title: Count-, CountA-, CountIf- ja CountRows-funktiot | Microsoft Docs
description: PowerAppsin Count-, CountA-, CounfIf- ja CountRows-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkki
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 762fa0ae7afe6b3693f74f308ba0a776aa27ed15
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="count-counta-countif-and-countrows-functions-in-powerapps"></a>PowerAppsin Count-, CountA-, CountIf- ja CountRows-funktiot
Laskee kaikki [tietueet](../working-with-tables.md#records) [taulukossa](../working-with-tables.md), tai laskee kaikki tietueet, jotka täyttävät ehdon.

## <a name="description"></a>Kuvaus
**Count**-funktio laskee yksisarakkeisessa taulukossa niiden tietueiden lukumäärän, jotka sisältävät numeron.

**CountA**-funktio laskee yksisarakkeisessa taulukossa niiden tietueiden lukumäärän, jotka eivät ole *tyhjiä*. Tämän funktion laskentaan sisältyy [tyhjä](function-isblank-isempty.md) teksti (””).

**CountIf**-funktio laskee taulukossa niiden tietueiden lukumäärän, joiden loogisen kaavan arvo on **true**.  Kaava voi viitata taulukon [sarakkeisiin](../working-with-tables.md#columns).

**CountRows**-funktio laskee taulukon tietueiden lukumäärän.

Kaikki nämä funktiot palauttavat luvun.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaksi
**Count**( *SingleColumnTable* )<br>
**CountA**( *SingleColumnTable* )

* *SingleColumnTable* – Pakollinen.  Laskettava tietuesarake.  

**CountIf**( *Table*, *LogicalFormula* )

* *Taulukko* – Pakollinen.  Laskettava tietuetaulukko.
* *LogicalFormula* – Pakollinen.  Kullekin taulukon tietueelle arvioitava kaava.  Tietueet, jotka palauttavat arvon **true** tälle kaavalle, lasketaan.  Kaava voi viitata taulukon sarakkeisiin.

**CountRows**( *Table* )

* *Taulukko* – Pakollinen.  Laskettava tietuetaulukko.

## <a name="example"></a>Esimerkki
1. Tuo tai luo [kokoelma](../working-with-data-sources.md#collections), jonka nimi on **Inventory**, kuten kohdan [Kuvien ja tekstin näyttäminen valikoimassa](../show-images-text-gallery-sort-filter.md) ensimmäisessä alitoimintosarjassa on kuvattu.
2. Lisää selite ja aseta sen **[Teksti](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **CountIf(Inventory, UnitsInStock < 30)**
   
    Selite näyttää luvun **2**, koska kahdella tuotteella (Ganymede ja Callisto) on alle 30 yksikköä varastossa.
3. Lisää toinen selite ja aseta sen **[Teksti](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **CountA(Inventory.UnitsInStock)**
   
    Selite näyttää luvun **5**, joka on ei-tyhjien solujen lukumäärä **UnitsInStock**-sarakkeessa.
4. Lisää toinen selite ja aseta sen **[Teksti](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **CountRows(Inventory)**
   
    Selite näyttää luvun **5**, koska kokoelma sisältää viisi riviä.


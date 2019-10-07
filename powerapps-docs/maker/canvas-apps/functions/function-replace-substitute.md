---
title: Replace- ja Substitute-funktio | Microsoft Docs
description: PowerAppsin Replace- ja Substitute-funktion viitetiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/02/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ff0e016f6ab1ad4f66651ccd3cfa2711f1d85a38
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992379"
---
# <a name="replace-and-substitute-functions-in-powerapps"></a>Replace- ja Substitute-funktio PowerAppsissa
Korvaa tekstimerkkijonon osa toisella merkkijonolla.

## <a name="description"></a>Kuvaus
**Replace**-funktio tunnistaa korvattavan tekstin sen aloituskohdan ja pituuden mukaan.  

**Substitute**-funktio tunnistaa korvattavan tekstin etsimällä vastaavan merkkijonon. Jos löytyi useampi kuin yksi vastaavuus, voit korvata ne kokonaan tai määrittää yhden korvattavan.

Jos välität yksittäisen merkkijonon, palautusarvo on muunnettu merkkijono. Jos välität yksisarakkeisen, merkkijonoja sisältävän [taulukon](../working-with-tables.md), palautusarvo on yksisarakkeinen taulukko, joka sisältää muokattuja merkkijonoja. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [Taulukoiden käyttö](../working-with-tables.md) mukaisesti.

## <a name="syntax"></a>Syntaksi
**Replace**( *String*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *String* – Pakollinen. Käsiteltävä merkkijono.
* *StartingPosition* – Pakollinen. Merkin sijainti, josta korvaus aloitetaan. *String*-arvon ensimmäinen merkki on sijainnissa 1.
* *NumberOfCharacters*  – Pakollinen. Korvattavien merkkien määrä kohdassa *String*.
* *NewString* – Pakollinen. Korvaava merkkijono. Tämän argumentin merkkien määrä voi olla eri kuin *NumberOfCharacters*-argumentin.

**Substitute**( *String*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *String* – Pakollinen. Käsiteltävä merkkijono.
* *OldString* – Pakollinen. Korvattava merkkijono.
* *NewString* – Pakollinen. Korvaava merkkijono. *OldString* ja *NewString* voivat olla eri pituisia.
* *InstanceNumber* – Valinnainen. Tämän argumentin avulla voit määrittää, mikä *Oldstring* -esiintymä korvataan, jos *merkki jono* sisältää useamman kuin yhden esiintymän. Jos et määritä tätä argumenttia, kaikki esiintymät korvataan.

**Replace**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *SingleColumnTable* – Pakollinen. Käsiteltävä yksisarakkeinen merkkijonotaulukko.
* *StartingPosition* – Pakollinen. Merkin sijainti, josta korvaus aloitetaan.  Taulukon jokaisen merkkijonon ensimmäinen merkki on vastaa sijaintia 1.
* *NumberOfCharacters*  – Pakollinen. Korvattavien merkkien määrä kussakin merkkijonossa.
* *NewString* – Pakollinen.  Korvaava merkkijono. Tämän argumentin merkkien määrä voi olla eri kuin *NumberOfCharacters*-argumentin.

**Substitute**( *SingleColumnTable*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *SingleColumnTable* – Pakollinen. Käsiteltävä yksisarakkeinen merkkijonotaulukko.
* *OldString* – Pakollinen.  Korvattava merkkijono.
* *NewString* – Pakollinen.  Korvaava merkkijono. *OldString* ja *NewString* voivat olla eri pituisia.
* *InstanceNumber* – Valinnainen. Tämän argumentin avulla voit määrittää, mikä *Oldstring* -esiintymä korvataan, jos *merkki jono* sisältää useamman kuin yhden esiintymän. Jos et määritä tätä argumenttia, kaikki esiintymät korvataan.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Replace ("abcdefghijk", &nbsp;6, &nbsp;5, &nbsp; "*")** | Korvaa viisi merkkiä "abcdefghijk" yhdellä "*" merkillä, joka alkaa kuudennesta merkistä ("f"). | "abpde * k" |
| **Replace (&nbsp; "2019", &nbsp;3, &nbsp;2, &nbsp; "20" &nbsp;)** | Korvaa kaksi viimeistä merkkiä "2019" tekstillä "20". | "2020" |
| **Replace (&nbsp; "123456", &nbsp;1, &nbsp;3, &nbsp; "_" &nbsp;)** | Korvaa kohteen "123456" kolme ensimmäistä merkkiä yhdellä "_"-merkillä. | "_456" | 
| **Korvike (&nbsp; "Sales @ no__t-2Data", &nbsp; "Sales", &nbsp; "maksaa" &nbsp;)** | Korvaa merkki jonon "hinta" kohteelle "Sales". | "Hinta tiedot" | 
| **Vara jäsen ("Quarter @ no__t-11, &nbsp;2018", "1", "2", 1)** | Korvaa vain kohteen 1 ensimmäisen esiintymän käyttäen arvoa 2, koska neljännessä argumentissa (*Instancenumber*) on 1. |  "Quarter 2, 2018" |
| **Korvike ("Quarter @ no__t-11, &nbsp;2011", "1", "2", 3)** | Korvaa vain kohteen 1 kolmannen esiintymän käyttäen arvoa 2, koska neljänteen argumenttiin (*Instancenumber*) on määritetty 3. | "Quarter 1, 2012" |
| **Korvike ("Quarter @ no__t-11, &nbsp;2011", "1", "2")** | Korvaa kaikki kohteen 1 esiintymät käyttäen arvoa 2, koska neljättä argumenttia (*Instancenumber*) ei ole annettu. | "Quarter 2, 2022" |
| **Replace (<br> [&nbsp; "Quarter @ no__t-31, &nbsp;2018", <br> "Quarter @ no__t-62, &nbsp;2011", <br> "Quarter @ no__t-94, 02019"], 19, 1, "3")** | Korvaa kunkin yksisarakkeisen taulukon kunkin tietueen yhdeksännen merkin tekstillä "3". | [&nbsp; "Quarter @ no__t-13, &nbsp;2018",<br>"Quarter @ no__t-03, &nbsp;2011",<br>"Quarter @ no__t-03, &nbsp;2019" &nbsp;] |
| **Vara jäsen (<br> [&nbsp; "qtr @ no__t-31, &nbsp;2018", <br> "Quarter @ no__t-61, &nbsp;2011", <br> "Q1, &nbsp;2019" 0], 1 "1", "3", 1)** | Koska neljännessä argumentissa (*Instancenumber*) on arvo 1, korvaa vain yhden sarakkeen ensimmäisen esiintymän jokaisessa tietueessa, jossa on yksi sarake-taulukko, jossa on kolme. | [&nbsp; "qtr @ no__t-13, &nbsp;2018",<br>"Quarter @ no__t-03, &nbsp;2011",<br>"Q3, &nbsp;2019" &nbsp;] |
| **Vara jäsen (<br> [&nbsp; "qtr @ no__t-31, &nbsp;2018", <br> "Quarter @ no__t-61, &nbsp;2011", <br> "Q1, &nbsp;2019" 0], 1 "1", "3")** | Koska neljättä argumenttia (*Instancenumber*) ei ole annettu, korvaa kaikki kohteen "1" esiintymät kunkin yksittäisen sarakkeen taulukon tietueessa "3". | [&nbsp; "qtr @ no__t-13, &nbsp;2038",<br>"Quarter @ no__t-03, &nbsp;2033",<br>"Q3, &nbsp;2039" &nbsp;] |  
 



---
title: Replace- ja Substitute-funktio | Microsoft Docs
description: PowerAppsin Replace- ja Substitute-funktion viitetiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/02/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fca1953402c87ca13bc3560b827cde03a47a8e92
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551602"
ms.PowerAppsDecimalTransform: true
---
# <a name="replace-and-substitute-functions-in-powerapps"></a>Replace- ja Substitute-funktio PowerAppsissa
Korvaa tekstimerkkijonon osa toisella merkkijonolla.

## <a name="description"></a>Kuvaus
**Replace**-funktio tunnistaa korvattavan tekstin sen aloituskohdan ja pituuden mukaan.  

**Substitute**-funktio tunnistaa korvattavan tekstin etsimällä vastaavan merkkijonon. Jos useampi kuin yksi vastine löytyy, voit korvata kaikkia tai määritä jokin korvataan.

Jos välität yksittäisen merkkijonon, palautusarvo on muunnettu merkkijono. Jos välität yksisarakkeisen, merkkijonoja sisältävän [taulukon](../working-with-tables.md), palautusarvo on yksisarakkeinen taulukko, joka sisältää muokattuja merkkijonoja. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [Taulukoiden käyttö](../working-with-tables.md) mukaisesti.

## <a name="syntax"></a>Syntaksi
**Replace**( *String*; *StartingPosition*; *NumberOfCharacters*; *NewString* )

* *String* – Pakollinen. Käsiteltävä merkkijono.
* *StartingPosition* – Pakollinen. Merkin sijainti, josta korvaus aloitetaan. *String*-arvon ensimmäinen merkki on sijainnissa 1.
* *NumberOfCharacters*  – Pakollinen. Korvattavien merkkien määrä kohdassa *String*.
* *NewString* – Pakollinen. Korvaava merkkijono. Tämän argumentin merkkien määrä voi olla eri kuin *NumberOfCharacters*-argumentin.

**Substitute**( *String*; *OldString*; *NewString* [; *InstanceNumber* ] )

* *String* – Pakollinen. Käsiteltävä merkkijono.
* *OldString* – Pakollinen. Korvattava merkkijono.
* *NewString* – Pakollinen. Korvaava merkkijono. *OldString* ja *NewString* voivat olla eri pituisia.
* *InstanceNumber* – Valinnainen. Tämän argumentin avulla voit määrittää, mikä esiintymä on *OldString* korvaa, jos *merkkijonon* sisältää useamman kuin yhden esiintymän. Jos et määritä tätä argumenttia, kaikki esiintymät korvataan.

**Replace**( *SingleColumnTable*; *StartingPosition*; *NumberOfCharacters*; *NewString* )

* *SingleColumnTable* – Pakollinen. Käsiteltävä yksisarakkeinen merkkijonotaulukko.
* *StartingPosition* – Pakollinen. Merkin sijainti, josta korvaus aloitetaan.  Taulukon jokaisen merkkijonon ensimmäinen merkki on vastaa sijaintia 1.
* *NumberOfCharacters*  – Pakollinen. Korvattavien merkkien määrä kussakin merkkijonossa.
* *NewString* – Pakollinen.  Korvaava merkkijono. Tämän argumentin merkkien määrä voi olla eri kuin *NumberOfCharacters*-argumentin.

**Substitute**( *SingleColumnTable*; *OldString*; *NewString* [; *InstanceNumber* ] )

* *SingleColumnTable* – Pakollinen. Käsiteltävä yksisarakkeinen merkkijonotaulukko.
* *OldString* – Pakollinen.  Korvattava merkkijono.
* *NewString* – Pakollinen.  Korvaava merkkijono. *OldString* ja *NewString* voivat olla eri pituisia.
* *InstanceNumber* – Valinnainen. Tämän argumentin avulla voit määrittää, mikä esiintymä on *OldString* korvaa, jos *merkkijonon* sisältää useamman kuin yhden esiintymän. Jos et määritä tätä argumenttia, kaikki esiintymät korvataan.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Replace( "abcdefghijk";&nbsp;6;&nbsp;5;&nbsp;"*" )** | Korvaa ”abcdefghijk” viisi merkkiä yksittäisen ”*” merkistä alkaen alkaen (”e”). | "abcde*k" |
| **Replace(&nbsp;"2019";&nbsp;3;&nbsp;2;&nbsp;"20"&nbsp;)** | Korvaa ”2019” ja ”20” viimeiset kaksi merkkiä. | "2020" |
| **Replace(&nbsp;"123456";&nbsp;1;&nbsp;3;&nbsp;"_"&nbsp;)** | Korvaa yksittäinen ”_”-merkillä ”123456” kolme ensimmäistä merkkiä. | "_456" | 
| **Korvaava (&nbsp;”myynti&nbsp;tiedot”,&nbsp;”myynti”,&nbsp;”kustannus”&nbsp;)** | Korvaa merkkijonon ”kustannus” ”myynti”. | ”Kustannus tiedot” | 
| **Korvaava (”vuosineljänneksen&nbsp;1,&nbsp;2018”, ”1”, ”2”, 1)** | Korvaa ”1” ”2” ensimmäisen esiintymän, koska neljännen argumentin (*InstanceNumber*) on annettu 1: llä. |  ”Vuosineljänneksen 2, 2018” |
| **Korvaava (”vuosineljänneksen&nbsp;1,&nbsp;2011”, ”1”, ”2”, 3).** | Korvaa ”1” ”2” kolmas esiintymä, koska neljännen argumentin (*InstanceNumber*) on annettu 3. | ”1. Vuosineljännes, 2012” |
| **Korvaava (”vuosineljänneksen&nbsp;1,&nbsp;2011”, ”1”, ”2”)** | Korvaa kaikki esiintymät ”1” ”2”, koska neljännen argumentin (*InstanceNumber*) ei ole annettu. | ”Vuosineljänneksen 2, 2022” |
| **Korvaa (<br>[&nbsp;”vuosineljänneksen&nbsp;1;&nbsp;2018”;<br>”vuosineljänneksen&nbsp;2;&nbsp;2011”<br>”vuosineljänneksen&nbsp;4;&nbsp;2019”];<br>9; 1; ”3”)** | Korvaa ”3” yksisarakkeisen taulukon jokaiselle tietueelle yhdeksäs merkki. | [&nbsp;”Vuosineljänneksen&nbsp;3,&nbsp;2018”,<br>”Vuosineljänneksen&nbsp;3,&nbsp;2011”,<br>”Vuosineljänneksen&nbsp;3,&nbsp;2019”&nbsp;] |
| **Korvaava ( <br>[&nbsp;”vuosineljänneksellä&nbsp;1;&nbsp;2018”;<br>”vuosineljänneksen&nbsp;1;&nbsp;2011”<br>”Q1;&nbsp;2019”&nbsp;];<br>”1 ”;” 3 ”; 1)** | Koska neljännen argumentin (*InstanceNumber*) on annettu arvo on 1, korvaa ”1” ensimmäisen esiintymän ”3” yksisarakkeisen taulukon jokaiselle tietueelle. | [&nbsp;”Vuosineljänneksellä&nbsp;3,&nbsp;2018”,<br>”Vuosineljänneksen&nbsp;3,&nbsp;2011”,<br>”3. VUOSINELJÄNNEKSEN,&nbsp;2019”&nbsp;] |
| **Korvaava ( <br>[&nbsp;”vuosineljänneksellä&nbsp;1;&nbsp;2018”;<br>”vuosineljänneksen&nbsp;1;&nbsp;2011”<br>”Q1;&nbsp;2019”&nbsp;];<br>”1 ”;” 3 ”)** | Koska neljännen argumentin (*InstanceNumber*) ei ole annettu, korvaa kaikki esiintymät ”1” ”3” yksisarakkeisen taulukon jokaiselle tietueelle. | [&nbsp;”Vuosineljänneksellä&nbsp;3,&nbsp;2038”,<br>”Vuosineljänneksen&nbsp;3,&nbsp;2033”,<br>”3. VUOSINELJÄNNEKSEN,&nbsp;2039”&nbsp;] |  
 



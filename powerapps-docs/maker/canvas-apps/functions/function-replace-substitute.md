---
title: Replace- ja Substitute-funktio | Microsoft Docs
description: PowerAppsin Replace- ja Substitute-funktion viitetiedot, mukaan lukien syntaksi
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
ms.openlocfilehash: d403fc5d756934900664affc04619c5cc72af6ee
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42834355"
---
# <a name="replace-and-substitute-functions-in-powerapps"></a>Replace- ja Substitute-funktio PowerAppsissa
Korvaa tekstimerkkijonon osa toisella merkkijonolla.

## <a name="description"></a>Kuvaus
**Replace**-funktio tunnistaa korvattavan tekstin sen aloituskohdan ja pituuden mukaan.  

**Substitute**-funktio tunnistaa korvattavan tekstin etsimällä vastaavan merkkijonon.  Jos useampi kuin yksi vastine löytyy, voit määrittää, kumpi korvataan.

Jos välität yksittäisen merkkijonon, palautusarvo on muunnettu merkkijono.  Jos välität yksisarakkeisen, merkkijonoja sisältävän [taulukon](../working-with-tables.md), palautusarvo on yksisarakkeinen taulukko, joka sisältää muokattuja merkkijonoja. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [Taulukoiden käyttö](../working-with-tables.md) mukaisesti.

## <a name="syntax"></a>Syntaksi
**Replace**( *String*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *String* – Pakollinen. Käsiteltävä merkkijono.
* *StartingPosition* – Pakollinen.  Merkin sijainti, josta korvaus aloitetaan. *String*-arvon ensimmäinen merkki on sijainnissa 1.
* *NumberOfCharacters*  – Pakollinen.  Korvattavien merkkien määrä kohdassa *String*.
* *NewString* – Pakollinen.  Korvaava merkkijono. Tämän argumentin merkkien määrä voi olla eri kuin *NumberOfCharacters*-argumentin.

**Substitute**( *String*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *String* – Pakollinen. Käsiteltävä merkkijono.
* *OldString* – Pakollinen.  Korvattava merkkijono.
* *NewString* – Pakollinen.  Korvaava merkkijono. *OldString* ja *NewString* voivat olla eri pituisia.
* *InstanceNumber* – Valinnainen. Oletusarvoisesti ensimmäinen *OldString*-esiintymä korvataan. Jos *String* sisältää useamman kuin yhden esiintymän, voit määrittää, mikä esiintymä korvataan.

**Replace**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *SingleColumnTable* – Pakollinen. Käsiteltävä yksisarakkeinen merkkijonotaulukko.
* *StartingPosition* – Pakollinen.  Merkin sijainti, josta korvaus aloitetaan.  Taulukon jokaisen merkkijonon ensimmäinen merkki on vastaa sijaintia 1.
* *NumberOfCharacters*  – Pakollinen.  Korvattavien merkkien määrä kussakin merkkijonossa.
* *NewString* – Pakollinen.  Korvaava merkkijono. Tämän argumentin merkkien määrä voi olla eri kuin *NumberOfCharacters*-argumentin.

**Substitute**( *SingleColumnTable*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *SingleColumnTable* – Pakollinen. Käsiteltävä yksisarakkeinen merkkijonotaulukko.
* *OldString* – Pakollinen.  Korvattava merkkijono.
* *NewString* – Pakollinen.  Korvaava merkkijono. *OldString* ja *NewString* voivat olla eri pituisia.
* *InstanceNumber* – Valinnainen. Oletusarvoisesti ensimmäinen *OldString*-esiintymä korvataan. Jos taulukko sisältää useamman kuin yhden esiintymän, voit määrittää, mikä esiintymä korvataan.


---
title: Replace- ja Substitute-funktio | Microsoft Docs
description: PowerAppsin Replace- ja Substitute-funktion viitetiedot, mukaan lukien syntaksi
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
ms.openlocfilehash: fe8f1e1cc8e54c3abf4b44bbfe46d9f96a7adfe7
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
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
* *StartingPosition* – Pakollinen.  Merkin sijainti, josta korvaus aloitetaan. *Merkkijono*n ensimmäinen merkki on sijainnissa 1.
* *NumberOfCharacters* – Pakollinen.  Korvattavien merkkien määrä kohdassa *Merkkijono*.
* *NewString* – Pakollinen.  Korvaava merkkijono. Tämän argumentin merkkien määrä voi olla eri kuin *NumberOfCharacters*-argumentin.

**Substitute**( *String*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *Merkkijono* – Pakollinen. Käsiteltävä merkkijono.
* *OldString* – Pakollinen.  Korvattava merkkijono.
* *NewString* – Pakollinen.  Korvaava merkkijono. *OldString* ja *NewString* voivat olla eri pituisia.
* *InstanceNumber* – Valinnainen. Oletusarvoisesti ensimmäinen *OldString*-esiintymä korvataan. Jos *Merkkijono* sisältää useamman kuin yhden esiintymän, voit määrittää, mikä esiintymä korvataan.

**Replace**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *SingleColumnTable* – Pakollinen. Käsiteltävä yksisarakkeinen merkkijonotaulukko.
* *StartingPosition* – Pakollinen.  Merkin sijainti, josta korvaus aloitetaan.  Taulukon jokaisen merkkijonon ensimmäinen merkki on sijainnissa 1.
* *NumberOfCharacters* – Pakollinen.  Korvattavien merkkien määrä kussakin merkkijonossa.
* *NewString* – Pakollinen.  Korvaava merkkijono. Tämän argumentin merkkien määrä voi olla eri kuin *NumberOfCharacters*-argumentin.

**Substitute**( *SingleColumnTable*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *SingleColumnTable* – Pakollinen. Käsiteltävä yksisarakkeinen merkkijonotaulukko.
* *OldString* – Pakollinen.  Korvattava merkkijono.
* *NewString* – Pakollinen.  Korvaava merkkijono. *OldString* ja *NewString* voivat olla eri pituisia.
* *InstanceNumber* – Valinnainen. Oletusarvoisesti ensimmäinen *OldString*-esiintymä korvataan. Jos taulukko sisältää useamman kuin yhden esiintymän, voit määrittää, mikä esiintymä korvataan.


---
title: Etsi-funktio | Microsoft Docs
description: PowerAppsin Etsi-funktion viitetietoja, kuten syntaksi ja esimerkit
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
ms.openlocfilehash: f43575fbe84173485ef39f3988bf6a049a4b9417
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="find-function-in-powerapps"></a>PowerAppsin Etsi-funktio
Etsii toisen merkkijonon sisältä tekstimerkkijonon, jos se on olemassa.

## <a name="description"></a>Kuvaus
**Etsi**-funktio etsii merkkijonoa toisen merkkijonon sisältä. Kirjainkoko on merkitsevä. Jos haluat, ettei kirjainkokoa huomioida, käytä ensin argumentteihin **[Lower](function-lower-upper-proper.md)**-funktiota.

**Etsi** palauttaa löytyneen merkkijonon aloituskohdan.  Merkkijonon ensimmäinen merkki on kohta 1. **Etsi** palauttaa *tyhjän*, jos merkkijono, jossa suoritat haun, ei sisällä etsittävää merkkijonoa.

## <a name="syntax"></a>Syntaksi
**Find**( *FindString*, *WithinString* [, *StartingPosition* ] )

* *FindString* – pakollinen.  Haettava merkkijono.
* *WithinString* – pakollinen.  Merkkijono, josta haetaan.
* *StartingPosition* – valinnainen.  Aloituskohta, josta haku aloitetaan.  Ensimmäinen merkki on kohta 1.


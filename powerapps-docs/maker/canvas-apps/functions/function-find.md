---
title: Etsi-funktio | Microsoft Docs
description: PowerAppsin Etsi-funktion viitetietoja, kuten syntaksi ja esimerkit
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
ms.openlocfilehash: 8e95f03c934e0989269ff9ec21b432f609cb13ad
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31826081"
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


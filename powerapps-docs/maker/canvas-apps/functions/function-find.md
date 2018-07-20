---
title: Etsi-funktio | Microsoft Docs
description: PowerAppsin Etsi-funktion viitetietoja, kuten syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: cd2028434fb9199595360ddafdb2e41d32e6cf3a
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39019522"
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


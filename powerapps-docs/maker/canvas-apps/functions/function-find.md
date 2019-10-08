---
title: Etsi-funktio | Microsoft Docs
description: PowerAppsin Etsi-funktion viitetietoja, kuten syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fbdd29ed1757301f076ab6bebea548fcd7a963cc
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984948"
ms.PowerAppsDecimalTransform: true
---
# <a name="find-function-in-powerapps"></a>PowerAppsin Etsi-funktio
Etsii toisen merkkijonon sisältä tekstimerkkijonon, jos se on olemassa.

## <a name="description"></a>Kuvaus
**Etsi**-funktio etsii merkkijonoa toisen merkkijonon sisältä. Kirjainkoko on merkitsevä. Jos haluat, ettei kirjainkokoa huomioida, käytä ensin argumentteihin **[Lower](function-lower-upper-proper.md)** -funktiota.

**Etsi** palauttaa löytyneen merkkijonon aloituskohdan.  Merkkijonon ensimmäinen merkki on kohta 1. **Etsi** palauttaa *tyhjän*, jos merkkijono, jossa suoritat haun, ei sisällä etsittävää merkkijonoa.

## <a name="syntax"></a>Syntaksi
**Find**( *FindString*; *WithinString* [; *StartingPosition* ] )

* *FindString* – pakollinen.  Haettava merkkijono.
* *WithinString* – pakollinen.  Merkkijono, josta haetaan.
* *StartingPosition* – valinnainen.  Aloituskohta, josta haku aloitetaan.  Ensimmäinen merkki on kohta 1.


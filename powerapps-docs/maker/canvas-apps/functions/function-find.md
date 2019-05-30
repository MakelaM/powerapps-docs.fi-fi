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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 04f257b40e778d3611203f2bdc17aad5554a4ac6
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551027"
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


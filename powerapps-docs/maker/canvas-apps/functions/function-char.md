---
title: Char-funktio | Microsoft Docs
description: Viitetietoja Char-funktiosta PowerAppsissa, mukaan lukien syntaksi ja esimerkkejä
dauthor: gregli-msft
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
ms.openlocfilehash: aec27b788fff8434cfdc4e0e130487f718a42aa6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42826361"
---
# <a name="char-function-in-powerapps"></a>Char-funktio PowerAppsissa
Muuntaa merkkikoodin merkkijonoksi.

## <a name="description"></a>Kuvaus
**Char**-funktio palauttaa merkkijonon, joka sisältää haluamasi ASCII-merkin käyttöympäristössäsi.

## <a name="syntax"></a>Syntaksi
**Char**( *CharacterCode* )

* *CharacterCode* – pakollinen. ASCII-merkkikoodi, joka muunnetaan.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Char( 65 )** |Palauttaa merkin, joka vastaa ASCII-koodia 65. |A |
| **Char( 105 )** |Palauttaa merkin, joka vastaa ASCII-koodia 105. |i |
| **Char( 35 )** |Palauttaa merkin, joka vastaa ASCII-koodia 35. |# |


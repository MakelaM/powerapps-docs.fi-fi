---
title: Char-funktio | Microsoft Docs
description: Viitetietoja Char-funktiosta PowerAppsissa, mukaan lukien syntaksi ja esimerkkejä
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
ms.openlocfilehash: b5d63b26498b94943f5340d9f57f3255390c7c94
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/07/2018
ms.locfileid: "37895979"
---
# <a name="char-function-in-powerapps"></a>Char-funktio PowerAppsissa
Muuntaa merkkikoodin merkkijonoksi.

## <a name="description"></a>Kuvaus
**Char**-funktio palauttaa merkkijonon, joka sisältää haluamasi ASCII-merkin käyttöympäristössäsi.

## <a name="syntax"></a>Syntaksi
**Char**( *merkkikoodi* )

* *Merkkikoodi* – pakollinen. ASCII-merkkikoodi, joka muunnetaan.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Char( 65 )** |Palauttaa merkin, joka vastaa ASCII-koodia 65. |A |
| **Char( 105 )** |Palauttaa merkin, joka vastaa ASCII-koodia 105. |i |
| **Char( 35 )** |Palauttaa merkin, joka vastaa ASCII-koodia 35. |# |


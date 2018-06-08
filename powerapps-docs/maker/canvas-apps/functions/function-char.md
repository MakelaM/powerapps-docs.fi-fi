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
ms.openlocfilehash: 2e8281f401088f43aa7785ac5dcf7b2f07bb6f96
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31826202"
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


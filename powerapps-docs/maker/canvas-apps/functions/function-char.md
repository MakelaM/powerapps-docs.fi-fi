---
title: Char-funktio | Microsoft Docs
description: Viitetietoja Char-funktiosta PowerAppsissa, mukaan lukien syntaksi ja esimerkkejä
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
ms.openlocfilehash: 7ce510840845b1a1df2d590c4f3ffdddfc5bfb9c
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
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


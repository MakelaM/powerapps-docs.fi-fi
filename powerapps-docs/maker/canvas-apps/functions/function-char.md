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
ms.openlocfilehash: 9c701527fb02613332cfa5bc542681f8c119f3b3
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014554"
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


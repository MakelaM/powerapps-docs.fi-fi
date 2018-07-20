---
title: Defaults-funktio | Microsoft Docs
description: PowerAppsin Defaults-funktion viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/01/2015
ms.author: gregli
ms.openlocfilehash: fe49a14a350e52da1282b1d6e3a41462e87de305
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014899"
---
# <a name="defaults-function-in-powerapps"></a>PowerAppsin Defaults-funktio
Palauttaa [tietolähteen](../working-with-data-sources.md) oletusarvot.  

## <a name="description"></a>Kuvaus
Käytä **Defaults**-funktiota tietojen syöttölomakkeen esitäyttämiseen, mikä helpottaa lomakkeen täyttöä.

Funktio palauttaa [tietueen](../working-with-tables.md#records), joka sisältää tietolähteen oletusarvot.  Jos tietolähteen [sarakkeella](../working-with-tables.md#columns) ei ole oletusarvoa, ominaisuutta ei esitetä.

Tietolähteiden antamat oletustietomäärät vaihtelevat, ja joissakin tapauksissa ei anneta mitään tietoja.  Kun käsittelet [valikoimaa](../working-with-data-sources.md#collections) tai muuta tietolähdettä, joka ei tue oletusarvoja, **Defaults**-funktio palauttaa [tyhjän](function-isblank-isempty.md) tietueen.

Voit [luoda tietueen](../working-with-data-sources.md) yhdistämällä **Defaults**-funktion **[Ohjelmakorjaus](function-patch.md)**-funktioon.

## <a name="syntax"></a>Syntaksi
**Defaults**( *DataSource* )

* *Tietolähde* – Pakollinen. Tietolähde, jonka oletusarvot haluat.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Defaults(&nbsp;Scores&nbsp;)** |Palauttaa **Pisteet**-tietolähteen oletusarvot. |**{ Score: 0 }** |


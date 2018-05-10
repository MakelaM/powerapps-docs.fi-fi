---
title: Defaults-funktio | Microsoft Docs
description: PowerAppsin Defaults-funktion viitetiedot, mukaan lukien syntaksi ja esimerkkejä
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
ms.date: 11/01/2015
ms.author: gregli
ms.openlocfilehash: eb1c6b802eff4aa5bd02a2ec52626b8788c42b73
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
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


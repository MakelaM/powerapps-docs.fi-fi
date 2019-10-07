---
title: Defaults-funktio | Microsoft Docs
description: PowerAppsin Defaults-funktion viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/01/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b51d956f2c188e0b877530b28dec933d42c905a6
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992848"
---
# <a name="defaults-function-in-powerapps"></a>PowerAppsin Defaults-funktio
Palauttaa [tietolähteen](../working-with-data-sources.md) oletusarvot.  

## <a name="description"></a>Kuvaus
Käytä **Defaults**-funktiota tietojen syöttölomakkeen esitäyttämiseen, mikä helpottaa lomakkeen täyttöä.

Funktio palauttaa [tietueen](../working-with-tables.md#records), joka sisältää tietolähteen oletusarvot.  Jos tietolähteen [sarakkeella](../working-with-tables.md#columns) ei ole oletusarvoa, ominaisuutta ei esitetä.

Tietolähteiden antamat oletustietomäärät vaihtelevat, ja joissakin tapauksissa ei anneta mitään tietoja.  Kun käsittelet [valikoimaa](../working-with-data-sources.md#collections) tai muuta tietolähdettä, joka ei tue oletusarvoja, **Defaults**-funktio palauttaa [tyhjän](function-isblank-isempty.md) tietueen.

Voit [luoda tietueen](../working-with-data-sources.md) yhdistämällä **Defaults**-funktion **[Ohjelmakorjaus](function-patch.md)** -funktioon.

## <a name="syntax"></a>Syntaksi
**Defaults**( *DataSource* )

* *DataSource* – Pakollinen. Tietolähde, jonka oletusarvot haluat.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Defaults(&nbsp;Scores&nbsp;)** |Palauttaa **Pisteet**-tietolähteen oletusarvot. |**{Score: 0}** |


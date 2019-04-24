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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 83021ff0d18eb5d7322ef40eaa2bc0839b56f452
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551165"
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

* *DataSource* – Pakollinen. Tietolähde, jonka oletusarvot haluat.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Defaults(&nbsp;Scores&nbsp;)** |Palauttaa **Pisteet**-tietolähteen oletusarvot. |**{Pistemäärä: 0 }** |


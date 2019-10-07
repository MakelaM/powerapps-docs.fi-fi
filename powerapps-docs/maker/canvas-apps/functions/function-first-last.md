---
title: First-, FirstN-, Last- ja LastN-funktiot | Microsoft Docs
description: PowerAppsin First-, FirstN-, Last- ja LastN-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 48e8311d5da00b02cbefbf6f47661c89adcc80a5
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992730"
---
# <a name="first-firstn-last-and-lastn-functions-in-powerapps"></a>PowerAppsin First-, FirstN-, Last- ja LastN-funktiot
Palauttaa taulukon ensimmäiset tai viimeiset [tietueet](../working-with-tables.md#records).

## <a name="description"></a>Kuvaus
**First**-funktio palauttaa [taulukon](../working-with-tables.md) ensimmäisen tietueen.

**FirstN**-funktio palauttaa taulukon ensimmäiset tietueet. Toinen argumentti määrittää palautettavien tietueiden määrän.

**Last**-funktio palauttaa taulukon viimeisen tietueen.

**LastN**-funktio palauttaa taulukon viimeiset tietueet. Toinen argumentti määrittää palautettavien tietueiden määrän.

**First** ja **Last** palauttavat yhden tietueen.  **FirstN** ja **LastN** palauttavat taulukon, vaikka määrittäisit vain yhden tietueen.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaksi
**First**( *Table* )<br>**Last**( *Table* )

* *Table* – Pakollinen. Taulukko, jolle toiminto suoritetaan.

**FirstN**( *Table* [, *NumberOfRecords* ] )<br>**LastN**( *Table* [, *NumberOfRecords* ] )

* *Table* – Pakollinen. Taulukko, jolle toiminto suoritetaan.
* *NumberOfRecords* – Valinnainen.  Palautettavien tietueiden määrä. Jos et määritä tätä argumenttia, funktio palauttaa yhden tietueen.

## <a name="examples"></a>Esimerkkejä
Tämä taulukko palauttaa ensimmäisen tietueen taulukosta nimeltä **Työntekijät**:<br>
**First(Työntekijät)**

Tämä taulukko palauttaa viimeiset 15 tietuetta taulukosta nimeltä **Työntekijät**:<br>
**LastN(Työntekijät, 15)**


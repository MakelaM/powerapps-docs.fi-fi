---
title: First-, FirstN-, Last- ja LastN-funktiot | Microsoft Docs
description: PowerAppsin First-, FirstN-, Last- ja LastN-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 3d94a3a250041ec7524460640f0bca4351ddcacf
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39021109"
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
**First**( *Taulukko* )<br>**Last**( *Taulukko* )

* *Taulukko* – Pakollinen. Taulukko, jolle toiminto suoritetaan.

**FirstN**( *Taulukko* [, *TietueidenMäärä* ] )<br>**LastN**( *Taulukko* [, *TietueidenMäärä* ] )

* *Taulukko* – pakollinen. Taulukko, jolle toiminto suoritetaan.
* *TietueidenMäärä* – Valinnainen.  Palautettavien tietueiden määrä. Jos et määritä tätä argumenttia, funktio palauttaa yhden tietueen.

## <a name="examples"></a>Esimerkkejä
Tämä taulukko palauttaa ensimmäisen tietueen taulukosta nimeltä **Työntekijät**:<br>
**First(Työntekijät)**

Tämä taulukko palauttaa viimeiset 15 tietuetta taulukosta nimeltä **Työntekijät**:<br>
**LastN(Työntekijät, 15)**


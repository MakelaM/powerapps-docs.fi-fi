---
title: First-, FirstN-, Last- ja LastN-funktiot | Microsoft Docs
description: PowerAppsin First-, FirstN-, Last- ja LastN-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.openlocfilehash: 91a59dd4294a7ce4e3b2a6a59b70c16d9e06ee1f
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
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

* *Taulukko* – Pakollinen. Taulukko, jolle toiminto suoritetaan.
* *TietueidenMäärä* – Valinnainen.  Palautettavien tietueiden määrä. Jos et määritä tätä argumenttia, funktio palauttaa yhden tietueen.

## <a name="examples"></a>Esimerkkejä
Tämä taulukko palauttaa ensimmäisen tietueen taulukosta nimeltä **Työntekijät**:<br>
**First(Työntekijät)**

Tämä taulukko palauttaa viimeiset 15 tietuetta taulukosta nimeltä **Työntekijät**:<br>
**LastN(Työntekijät, 15)**


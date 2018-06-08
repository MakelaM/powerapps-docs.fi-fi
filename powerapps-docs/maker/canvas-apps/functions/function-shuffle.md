---
title: Shuffle-funktio | Microsoft Docs
description: PowerAppsin Shuffle-funktion viitetiedot, mukaan lukien syntaksi ja esimerkki
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
ms.openlocfilehash: 6d981c410b22dd9db52cdf077a00e6eaae83be75
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31827363"
---
# <a name="shuffle-function-in-powerapps"></a>PowerAppsin Shuffle-funktio
Järjestää [taulukon](../working-with-tables.md) [tietueet](../working-with-tables.md#records) uudelleen satunnaisesti.

## <a name="description"></a>Kuvaus
**Shuffle**-funktio järjestää taulukon tietueet uudelleen satunnaisesti.

**Shuffle** palauttaa taulukon, jolla on samat [sarakkeet](../working-with-tables.md#columns) ja sama määrä rivejä kuin argumentissa.

## <a name="syntax"></a>Syntaksi
**Shuffle**( *Table* )

* *Table* – Pakollinen.  Sekoitettava taulukko.

## <a name="example"></a>Esimerkki
Jos olet tallentanut tietoja pelikorteista [kokoelmaan](../working-with-data-sources.md#collections) nimeltä **Deck**, tämä kaava palauttaa kopion kyseisestä kokoelmasta satunnaisessa järjestyksessä.

**Shuffle(Deck)**


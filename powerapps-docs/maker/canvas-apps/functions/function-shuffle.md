---
title: Shuffle-funktio | Microsoft Docs
description: PowerAppsin Shuffle-funktion viitetiedot, mukaan lukien syntaksi ja esimerkki
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 39307e9c7b3de7bfae151709827c409fcc7087ad
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014232"
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


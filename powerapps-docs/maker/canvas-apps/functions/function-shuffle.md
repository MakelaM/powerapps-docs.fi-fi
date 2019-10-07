---
title: Shuffle-funktio | Microsoft Docs
description: PowerAppsin Shuffle-funktion viitetiedot, mukaan lukien syntaksi ja esimerkki
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
ms.openlocfilehash: 181ef038a90c9bfc7e3fe72af9514a34afce9776
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983938"
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


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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3fd93ce6cf9703e9e9fbf69c5826213d9aa78e02
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863564"
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


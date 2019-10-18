---
title: Paging | Microsoft Docs
description: ''
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12891e96-972c-4289-bbde-2bc261cd1f12
ms.openlocfilehash: ccf68c94e0b11f8a1227199609a9c21c1923ad7b
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342181"
---
# <a name="paging"></a>Sivutus

[!INCLUDE [paging-description](includes/paging-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="properties"></a>Ominaisuudet

### <a name="totalresultcount"></a>totalResultCount

Nykyisen kyselyn tulosten kokonaismäärä palvelimessa.

**Tyyppi**: `number`

### <a name="hasnextpage"></a>hasNextPage

Voiko tulos joukkoa sivuttaa taaksepäin.

**Tyyppi**: `boolean`

### <a name="haspreviouspage"></a>hasPreviousPage

Voiko tulos joukkoa sivuttaa taaksepäin.

**Tyyppi**: `boolean`

## <a name="methods"></a>Menetelmiä

|Menetelmä | Kuvaus |
| ------|-------------|
|[loadNextPage](paging/loadnextpage.md)|[!INCLUDE [loadnextpage-description](paging/includes/loadnextpage-description.md)]|
|[loadPreviousPage](paging/loadpreviouspage.md)|[!INCLUDE [loadpreviouspage-description](paging/includes/loadpreviouspage-description.md)]|
|[palauttaa](paging/reset.md)|[!INCLUDE [reset-description](paging/includes/reset-description.md)]|
|[setPageSize](paging/setpagesize.md)|[!INCLUDE [setpagesize-description](paging/includes/setpagesize-description.md)]|
|pageSize|Tieto joukon sivua kohden palautettavien tietueiden määrä. Lomakkeissa tieto joukon pageSize menee muotoilun (rivien määrän) ja muiden kanssa, joista voit valita henkilökohtaiset asetuksesi.|


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
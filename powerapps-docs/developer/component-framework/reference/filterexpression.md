---
title: FilterExpression | Microsoft Docs
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
ms.assetid: 19ad54b8-e044-4f07-a18e-b00d26b75832
ms.openlocfilehash: 7b613238f28987b688d4f2299506fa91b72a99a7
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72343975"
---
# <a name="filterexpression"></a>FilterExpression ominaisuudessa

[!INCLUDE [filterexpression-description](includes/filterexpression-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="properties"></a>Ominaisuudet

### <a name="conditions"></a>määräykset

Tähän suodattimeen liittyvien ehtojen joukkoon.

**Tyyppi**: [ConditionExpression](conditionexpression.md)[]

### <a name="filteroperator"></a>Suodatin operaattori

Operaattori käytti tämän suodattimen ehtojen yhdistämistä.

**Tyyppi**: `enum`

@No__t_0 arvo on luettelointi, jolla on seuraavat mahdolliset arvot

|Value|Jäsen|
|--|--|
|0|And|
|1|Or|

### <a name="filters"></a>suodattimet

Kaikki alemman tason suodattimet, jotka tulee arvioida tämän suodattimen arvioinnin jälkeen.

**Tyyppi**: [FilterExpression](filterexpression.md)[]<br />

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
---
title: ConditionExpression | Microsoft Docs
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
ms.assetid: bd90b3fd-a4b4-4999-8b53-d2a5dce4966b
ms.openlocfilehash: 10f7275643c0df4c2a4099a80b490fb5e27ce318
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72345539"
---
# <a name="conditionexpression"></a>ConditionExpression

[!INCLUDE [conditionexpression-description](includes/conditionexpression-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="properties"></a>Ominaisuudet

### <a name="attributename"></a>attributeName

Sen tieto joukon sarakkeen nimi, johon suodatin otetaan käyttöön.

**Tyyppi**: `string`

### <a name="conditionoperator"></a>Condition-operaattori

Operaattori, jota käytetään ehdon arvioimiseen.

**Tyyppi**: `enum`

@No__t_0 arvo on luettelointi, jolla on seuraavat mahdolliset arvot

|Value|Jäsen|
|--|--|
|-1|Ei mitään|
|0|Yhtä suuri kuin|
|1|NotEqual|
|2|GreaterThan|
|3|LessThan|
|4|Greeerequal|
|5|Lessedal|
|6|Kuten|
|8|Kohteessa|
|12|Null|
|14|Eilen|
|15|Today|
|16|Huomenna|
|17|Last7Days|
|18|Next7Days|
|19|LastWeek|
|20|ThisWeek|
|22|LastMonth|
|23|ThisMonth|
|25|Kartalla|
|26|OnOrBefore|
|27|OnOrAfter|
|28|LastYear|
|29|ThisYear|
|33|LastXDays|
|34|NextXDays|
|37|Lastxkk|
|38|Nextxkk|
|49|Sisältää|
|70|InFiscalPeriodAndYear|
|75|Edellä|
|76|Alle|
|77|NotUnder|
|78|AboveOrEqual|
|79|Aliorequal|
|87|ContainValues|

### <a name="entityaliasname"></a>Entitialiasname

Entiteetin aliaksen nimi, joten suodatusta voi käyttää linkitetyissä entiteeteissä.

**Tyyppi**: `string`

### <a name="value"></a>arvo

Ehdon arvioitu arvo.

**Tyyppi**: `string | string[]`

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
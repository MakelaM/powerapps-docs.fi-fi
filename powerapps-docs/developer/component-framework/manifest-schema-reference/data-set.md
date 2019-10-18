---
title: Tieto joukko-elementit | Microsoft Docs
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
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
ms.assetid: 9ffe8930-b290-4252-98d4-a1195b00205f
ms.openlocfilehash: adf672b036d1f49619cbc4a5ef72661fbeebf013
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346551"
---
# <a name="data-set-element"></a>tieto sarjan alku aine

[!INCLUDE [data-set-description](includes/data-set-description.md)]

## <a name="attributes"></a>Määritteet

|Nimi|Kuvaus|Tyyppi|Pakollinen|Käytettävissä kohteelle|
|--|--|--|--|-------|
|`description-key`|Määrittää ominaisuuden kuva uksen.|`string`|Valinnainen|
|`display-name-key`|Määrittää ominaisuuden nimen.|`string`|Kyllä|
|`name`|Ruudukon nimi|`string`|Kyllä|
|`cds-data-set-options`|Näyttää CommandBar, ViewSelector, QuickFindSearch, jos asetus on tosi |`boolean`|Kyllä|

## <a name="parent-elements"></a>Pääelementit

|Elementti|Kuvaus|
|--|--|
|[control](control.md)|[!INCLUDE [control-description](includes/control-description.md)]|

## <a name="example"></a>Esimerkki

```xml
 <data-set name="dataSetGrid" display-name-key="DataSetGridProperty" cds-data-set-options="displayCommandBar:true;displayViewSelector:true;displayQuickFindSearch:true">
 </data-set>
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
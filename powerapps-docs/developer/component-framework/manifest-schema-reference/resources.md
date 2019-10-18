---
title: Resurssi-alkio | Microsoft Docs
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
ms.assetid: 66599c2f-6651-4b27-92da-a38897acdfb5
ms.openlocfilehash: a7df2dde98667fd0de8489943094ad6f4ff210f0
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346068"
---
# <a name="resources-element"></a>resurssi-alkio

[!INCLUDE [resources-description](includes/resources-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="parent-elements"></a>Pääelementit

|Elementti|Kuvaus|
|--|--|
|[control](control.md)|[!INCLUDE [control-description](includes/control-description.md)]|

## <a name="child-elements"></a>Alielementit

|Elementti|Kuvaus|Esiintymät|
|--|--|--|
|[code](code.md)|[!INCLUDE [code-description](includes/code-description.md)]|1|
|[css](css.md)|[!INCLUDE [css-description](includes/css-description.md)]|vähintään 0|
|[img](img.md)|[!INCLUDE [img-description](includes/img-description.md)]|vähintään 0|
|[html](html.md)|[!INCLUDE [html-description](includes/html-description.md)]|vähintään 0|
|[resx](resx.md)|[!INCLUDE [resx-description](includes/resx-description.md)]|vähintään 0|

## <a name="example"></a>Esimerkki

```xml
<resources>
  <code path="JS_HelloWorldControl.js" order="1" />
<css path="css/JS_HelloWorldControl.css" order="1" />
        </resources>
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
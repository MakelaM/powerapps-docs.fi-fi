---
title: Luettelo-elementit | Microsoft Docs
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
ms.assetid: a48831c6-133a-4747-99fa-7cc1df4558d0
ms.openlocfilehash: d62b72c43a9c77a41c0a434a723d330ffa4b890a
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346252"
---
# <a name="manifest-element"></a>Luettelo-elementit

[!INCLUDE [manifest-description](includes/manifest-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="child-elements"></a>Alielementit

|Elementti|Kuvaus|Esiintymät|Käytettävissä kohteelle|
|--|--|--|-------|
|[control](control.md)|[!INCLUDE [control-description](includes/control-description.md)]|vähintään 1|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
|[type-group](type-group.md)|[!INCLUDE [type-group-description](includes/type-group-description.md)]|vähintään 0|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
|[property](property.md)|[!INCLUDE [property-description](includes/property-description.md)]|vähintään 0|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
|[data-set](data-set.md)|[!INCLUDE [data-set-description](includes/data-set-description.md)]|vähintään 0|Mallipohjaiset sovellukset|
|[resurssi](resources.md)|[!INCLUDE [resource-description](includes/resources-description.md)]|vähintään 1|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|

## <a name="example"></a>Esimerkki

```xml
<?xml version="1.0" encoding="utf-8" ?>
<manifest>
    <control namespace="MyNameSpace" constructor="JSHelloWorldControl" version="1.0.0" display-name-key="JS_HelloWorldControl_Display_Key" description-key="JS_HelloWorldControl_Desc_Key" control-type="standard">
        <property name="myFirstProperty" display-name-key="myFirstProperty_Display_Key" description-key="myFirstProperty_Desc_Key" of-type="SingleLine.Text" usage="bound" required="true" />
        <resources>
            <code path="JS_HelloWorldControl.js" order="1" />
            <css path="css/JS_HelloWorldControl.css" order="1" />
        </resources>
    </control>
</manifest>
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)

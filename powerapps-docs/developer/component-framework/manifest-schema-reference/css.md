---
title: CSS-elementit | Microsoft Docs
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
ms.assetid: b6119424-c0a4-4412-b25c-8239da6cbe36
ms.openlocfilehash: b7c96ba2bbb3e5d6d20df92e58ef0bc4005e7d37
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346574"
---
# <a name="css-element"></a>CSS-elementit

[!INCLUDE [css-description](includes/css-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="attributes"></a>Määritteet

|Nimi|Kuvaus|Tyyppi|Pakollinen|Käytettävissä kohteelle|
|--|--|--|--|-----|
|`path`|Suhteellinen polku w. r. t-luettelo, jossa CSS-tiedostot sijaitsevat|`string`|Kyllä|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
|`order`|Järjestys, jossa CSS-tiedostot ladataan|`Positive integer`|Valinnainen|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|

## <a name="parent-elements"></a>Pääelementit

|Elementti|Kuvaus|
|--|--|
|[resources](resources.md)|[!INCLUDE [resources-description](includes/resources-description.md)]|

## <a name="example"></a>Esimerkki

```xml
<css path="css/JS_HelloWorldControl.css" order="1" />
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)

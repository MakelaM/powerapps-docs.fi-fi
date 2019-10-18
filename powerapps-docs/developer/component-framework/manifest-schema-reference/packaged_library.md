---
title: Pakatun kirjaston alku aine | Microsoft Docs
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
ms.assetid: 41c50db2-3096-4990-ac2b-e702c161bf4f
ms.openlocfilehash: 011aa2ab527cc2bd16fc99842e2388a3a6b0918e
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346183"
---
# <a name="packaged_library-element"></a>packaged_library-alku aine

[!INCLUDE [packaged_library-description](includes/packaged_library-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset

## <a name="attributes"></a>Määritteet

|Nimi|Kuvaus|Tyyppi|Pakollinen|Käytettävissä kohteelle|
|--|--|--|--|-------|
|`path`|Paikka, jossa pakatut Kirjasto tiedostot sijaitsevat|`string`|Kyllä|Mallipohjaiset sovellukset|
|`version`|Pakatun kirjaston nykyinen versio|`string`|Kyllä|Mallipohjaiset sovellukset|

## <a name="parent-elements"></a>Pääelementit

|Elementti|Kuvaus|
|--|--|
|[kirjaston](library.md)|[!INCLUDE [library-description](includes/library-description.md)]|

## <a name="example"></a>Esimerkki

```xml
<resources>
    <library name="AngularJSCore" version=">=1" order="1">
    <packaged_library path="libs/angular.min.js" version="1.5.8" />
    </library>
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)

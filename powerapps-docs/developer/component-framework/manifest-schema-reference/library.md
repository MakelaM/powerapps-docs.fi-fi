---
title: Kirjasto-elementit | Microsoft Docs
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
ms.assetid: 90f2b4c9-7396-4ab9-bc9f-810189dc18b7
ms.openlocfilehash: bd766864e6ef971b5245afad7d49af54b9369087
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346298"
---
# <a name="library-element"></a>Kirjasto-elementit

[!INCLUDE [library-description](includes/library-description.md)]

## <a name="attributes"></a>Määritteet

|Nimi|Kuvaus|Tyyppi|Pakollinen|
|--|--|--|--|
|`name`|Kirjaston nimi|`string`|Kyllä|
|`version`|Nykyinen Kirjasto versio|Positiivinen kokonaisluku|Kyllä|
|`order`|Järjestys, jossa Kirjasto tiedostot ladataan|Positiivinen kokonaisluku|Kyllä|

## <a name="parent-elements"></a>Pääelementit

|Elementti|Kuvaus|
|--|--|
|[resources](resources.md)|[!INCLUDE [resources-description](includes/resources-description.md)]|

## <a name="child-elements"></a>Alielementit

|Elementti|Kuvaus|Esiintymät|
|--|--|--|
|[packaged_library]||vähintään 0|

## <a name="example"></a>Esimerkki

```xml
<resources>
<library name="AngularJSCore" version=">=1" order="1">
<packaged_library path="libs/angular.min.js" version="1.5.8" />
</library>
  </resources>
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
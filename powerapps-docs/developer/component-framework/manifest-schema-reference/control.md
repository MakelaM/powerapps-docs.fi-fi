---
title: Hallinta-elementit | Microsoft Docs
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
ms.assetid: 4dacd337-c9df-458e-86f3-bfb3ab543ea7
ms.openlocfilehash: aa02b89ce1e032a3cf2fdedca8f0fdf79cb84045
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346620"
---
# <a name="control-element"></a>ohjaus objektin komponentti

[!INCLUDE [control-description](includes/control-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="attributes"></a>Määritteet

|Nimi|Kuvaus|Tyyppi|Pakollinen|Käytettävissä kohteelle|
|--|--|--|--|--------|
|`namespace`|Määrittää komponentin proto tyypin|[!INCLUDE [alphanumerictype-description](includes/alphanumerictype-description.md)]|Kyllä|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
|`constructor`|Objektin alustamisen menetelmä|[!INCLUDE [alphanumerictype-description](includes/alphanumerictype-description.md)]|Kyllä|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
|`control-type`|Vakio|[!INCLUDE [controltype-description](includes/controltype-description.md)]|Ei|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
|`description-key`|Määrittää käyttö liittymässä näkyvän komponentin kuva uksen.|`string`|Ei|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
|`display-name-key`|Määrittää käyttö liittymässä näkyvän ohjaus objektin nimen.|`string`|Kyllä|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
|`preview-image`|Kuva, jota käytetään mukautus näytöissä komponentin esikatselun näyttämiseen.|`string`|Ei|Mallipohjaiset sovellukset|
|`version`|Määrittää [semanttisessa versiotuksessa](https://semver.org) määritetyn osan version|`string`|Kyllä|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
<!--|`hidden`|Määrittää, tuleeko komponentti piilottaa vai ei|[!INCLUDE [booleantype-description](includes/booleantype-description.md)]| Ei|Mallipohjaiset sovellukset|-->

## <a name="parent-elements"></a>Pääelementit

|Elementti|Kuvaus|
|--|--|
|[manifest](manifest.md)|[!INCLUDE [manifest-description](includes/manifest-description.md)]|

## <a name="child-elements"></a>Alielementit

|Elementti|Kuvaus|Esiintymät|
|--|--|--|
|[data-set](data-set.md)|[!INCLUDE [data-set-description](includes/data-set-description.md)]|vähintään 0|
|[property](property.md)|[!INCLUDE [property-description](includes/property-description.md)]|vähintään 0|
|[resources](resources.md)|[!INCLUDE [resources-description](includes/resources-description.md)]|1|
|[type-group](type-group.md)|[!INCLUDE [type-group-description](includes/type-group-description.md)]|vähintään 0|

## <a name="example"></a>Esimerkki

```xml
<control namespace="MyNameSpace" constructor="JSHelloWorldControl" version="1.0.0"
 display-name-key="JS_HelloWorldControl_Display_Key" description-key="JS_HelloWorldControl_Desc_Key"
 control-type="standard" preview-image="img/preview.png">
</control>
  ```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
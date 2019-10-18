---
title: Koodi-elementit | Microsoft Docs
description: ''
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 06/4/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
ms.assetid: 44d9fcfb-0cd8-48cc-aace-dd589099dd79
ms.openlocfilehash: 2caf89a73dba006240c5bb6e8c874dfdd795d8c2
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346643"
---
# <a name="code-element"></a>koodi-elementit

[!INCLUDE [code-description](includes/code-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="attributes"></a>Määritteet

|Nimi|Kuvaus|Tyyppi|Pakollinen|Käytettävissä kohteelle|
|--|--|--|--|-----|
|`path`|Resurssi tiedostojen sijainti paikka|`String`|Kyllä|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|
|`order`|Järjestys, jossa resurssi tiedostot ladataan|`Positive integer`|Kyllä|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) (kokeellinen esikatselu)|

## <a name="parent-elements"></a>Pääelementit

|Elementti|Kuvaus|
|--|--|
|[resources](resources.md)|[!INCLUDE [resources-description](includes/resources-description.md)]|

### <a name="example"></a>Esimerkki

```XML
<code path="TS_IncrementControl.js" order="1" />
        <css path="css/TS_IncrementControl.css" order="1" />
      <resx path="strings/TSIncrementControl.1033.resx" version="1.0.0" />
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
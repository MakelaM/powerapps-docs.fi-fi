---
title: Tyyppi ryhmä-elementit | Microsoft Docs
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
ms.assetid: ec7c1ad4-b834-4755-8a04-2c8940f75674
ms.openlocfilehash: 7b09fad6097bb837c19116d59bb90afbde4d46b2
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72345976"
---
# <a name="type-group-element"></a>tyyppi-ryhmä-elementit

[!INCLUDE [type-group-description](includes/type-group-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="attributes"></a>Määritteet

|Nimi|Kuvaus|Tyyppi|Pakollinen|
|--|--|--|--|
|`name`|Tieto tyypin nimi|`string`|Kyllä|

## <a name="parent-elements"></a>Pääelementit

|Elementti|Kuvaus|
|--|--|
|[control](control.md)|[!INCLUDE [control-description](includes/control-description.md)]|


## <a name="child-elements"></a>Alielementit

|Elementti|Kuvaus|Esiintymät|
|--|--|--|
|[tyyppi](type.md)|[!INCLUDE [type-description](includes/type-description.md)]|vähintään 1|


Tyyppi-ryhmällä on rajoitettu tuki pohjaan perustuvia sovelluksia varten tässä kokeellisen esikatselun yhteydessä. Seuraavat ongelmat ilmenevät, kun yrität tuoda komponentteja:

1. Jos kaikki tyypit, jotka luetellaan tyyppi ryhmässä, ovat yhteensopivia JavaScript-tyyppejä, kehittäjä yrittää valita luettelossa yleisimmin käytettävän vaihto ehdon. Yhteensopiviksi katsotut tyypit ovat seuraavat:
   - Merkki jonot: SingleLine. text, Multiple, SingleLine. TextArea, SingleLine. email, SingleLine. Phone, SingleLine. URL, SingleLine. ticker.
   - Numerot: desimaalimuoto, liuku luku, koko. ei mitään, valuutta.
   - Päivä määrät: DateAndTime. DateAndTime, DateAndTime. DateOnly.

2. Jos ryhmässä lueteltuja tyyppejä ei pidetä yhteensopivina, parametria käsitellään tyyppi ryhmän ensimmäisenä luettelossa ensimmäisenä tyyppinä.

### <a name="example"></a>Esimerkki

```XML
<type-group name="numbers">
      <type>Whole.None</type>
      <type>Currency</type>
      <type>FP</type>
      <type>Decimal</type>
    </type-group>
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
---
title: Popup | Microsoft Docs
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
ms.assetid: b0af1803-ae3a-41c2-a8a5-b15970bd6f96
ms.openlocfilehash: bb28a979ac721eded06025a56588023c211ea6f9
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342204"
---
# <a name="popup"></a>Ikkuna

[!INCLUDE [popup-description](includes/popup-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="properties"></a>Ominaisuudet

### <a name="closeonoutsideclick"></a>closeOnOutsideClick

Ilmaisee, sulkeeko ponnahdus ikkuna hiiren ulkopuolisen napsautuksen jälkeen. Kun asetus on `false`, ponnahdus ikkunaa ei suljeta ulkopuolisella hiiren napsautuksella.

**Tyyppi**: `boolean`

### <a name="content"></a>sisältö

Lisättävä staattinen DOM-alkio.

**Tyyppi**: [HTML-elementit](https://developer.mozilla.org/docs/Web/API/HTMLElement)

### <a name="id"></a>Tunnus

Ankkuri komponentiksi määritettävä tunnus, jos sellainen on.

**Tyyppi**: `string`

### <a name="name"></a>Nimi

Ponnahdus ikkunan nimi. Käytetään viitteenä avattuja ponnahdus ikkunoita.

**Tyyppi**: `string`

### <a name="popuptoopen"></a>popupToOpen

Avattavan ponnahdus ikkunan nimi.

**Tyyppi**: `string`

### <a name="remarks"></a>Huomautuksia

Tulee määrittää vain juuri popup-ikkunassa. Jos haluat avata sisäkkäiset ponnahdus ikkunat, tulisi antaa merkki jono, kuten `rootName.nestedName.[allOtherNestedNames]`. Jos haluat sulkea ponnahdus ikkunoita, tulisi antaa tyhjä merkki jono. Tämä ominaisuus levitetään automaattisesti alikohteisiin.

## <a name="type"></a>type

Ponnahdus ikkunan tyyppi, joka on kuvattu kohdassa Enum PopupType. Kullekin ponnahdus ikkuna joukolle on oltava vain yksi `root` popup.

**Tyyppi**: `enum`

@No__t_0 arvo on luettelointi, jolla on seuraavat mahdolliset arvot

|Value|Jäsen|
|--|--|
|1|Root|
|2|Sisäkkäisen|

### <a name="remarks"></a>Huomautuksia

Tulee olla vain yksi `Root` popup kullekin ponnahdus ikkunoita.

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
---
title: openWebResource | Microsoft Docs
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
ms.assetid: 27a1e54c-71fe-450f-8f84-b4cc125970bf
ms.openlocfilehash: 577c26dd87149fabebafe32b77395029ef4df335
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342250"
---
# <a name="openwebresource"></a>openWebResource

[!INCLUDE [openwebresource-description](includes/openwebresource-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.navigation.openWebResource(name, options, data)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|Nimi|`String`|Kyllä|Sen HTML-verkko resurssin nimi, joka avataan.|
|asetukset|`OpenWebResourceOptions`|Ei|Verkko resurssin avaamisen ikkuna-asetukset. Openwebresourctoptions-kohteella on seuraavat ominaisuudet:<br/>- **Korkeus**: `Number`. Ikkunan korkeus, jolloin tuloksena oleva sivu näytetään kuva pisteinä.<br/>- **Leveys**: `Number`. Sen ikkunan leveys, joka näyttää tuloksena olevan sivun kuva pisteinä.<br/>- **Openinnnewwindow**: `Boolean`. Ilmaisee, Avaanko verkko resurssi uudessa ikkunassa.|
|tieto|`String`|Ei|Tieto parametriin välitettävät tiedot.

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Siirtyminen](../navigation.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
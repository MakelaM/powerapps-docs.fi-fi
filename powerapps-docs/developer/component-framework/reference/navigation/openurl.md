---
title: openUrl | Microsoft Docs
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
ms.assetid: 590078f3-c604-4bd0-ac74-9cf6d8806802
ms.openlocfilehash: 21e097c739364b6cdb3935654ae9bf2b61143a06
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342273"
---
# <a name="openurl"></a>openUrl

[!INCLUDE [openurl-description](includes/openurl-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.navigation.openUrl(url, options)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|URL|`string`|Kyllä|Avattava URL-osoite.|
|asetukset|`OpenUrlOptions`|Ei|URL-osoitteen avaamisen asetukset. OpenUrlOptions-kohteella on seuraavat parametrit: <br/>- **Korkeus**: `Number`. Ikkunan korkeus, jolloin tuloksena oleva sivu näytetään kuva pisteinä.<br/>- **Leveys**: `Number`. Sen ikkunan leveys, joka näyttää tuloksena olevan sivun kuva pisteinä.|


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Siirtyminen](../navigation.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
---
title: setFullScreen | Microsoft Docs
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
ms.assetid: 1faf3e79-969e-4c1e-ac01-8e2155c609fa
ms.openlocfilehash: b7fb38bcb0102356d8d1ea2540edf0dd1f845cbd
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342618"
---
# <a name="setfullscreen"></a>setFullScreen

[!INCLUDE [setfullscreen-description](includes/setfullscreen-description.md)]

## <a name="syntax"></a>Syntaksi

`context.mode.setControlState(mode);`

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|arvo|`Boolean`|Kyllä|`True`, jos osan on oltava automaattisesti koko näytön kokoinen. `False`, jos osan koon on oltava Automaattinen, jotta sen leveys voidaan jakaa.|


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Mode](../mode.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
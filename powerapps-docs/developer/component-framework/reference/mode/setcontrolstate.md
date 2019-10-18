---
title: setControlState | Microsoft Docs
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
ms.assetid: 1052db82-7002-44ca-ad1f-9d3d4c311817
ms.openlocfilehash: 56c2221916781db646d27b131dfc00e61e742be3
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342664"
---
# <a name="setcontrolstate"></a>setControlState

[!INCLUDE [setcontrolstate-description](includes/setcontrolstate-description.md)]

## <a name="syntax"></a>Syntaksi

`context.mode.setControlState(state);`

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) 

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|tila|`Dictionary`|Kyllä|Tiedot, jotka jatkuvat yhdessä istunnossa yhdelle käyttäjälle.|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `boolean`


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Mode](../mode.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
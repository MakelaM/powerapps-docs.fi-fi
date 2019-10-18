---
title: getTimeZoneOffsetMinutes | Microsoft Docs
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
ms.assetid: 86290d20-7dbb-4932-adaa-31121ae7a3f6
ms.openlocfilehash: bc621299b19b1387225b8532ee03ff65e0e6471f
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72341008"
---
# <a name="gettimezoneoffsetminutes"></a>getTimeZoneOffsetMinutes

[!INCLUDE [gettimezoneoffsetminutes-description](includes/gettimezoneoffsetminutes-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.usersettings.getTimeZoneOffsetMinutes(date)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|Päivä määrä|`Date`|Kyllä|päivä määrä, josta siirtymä saadaan UTC-kohteesta.|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `Number` kuvaus: aika vyöhykkeen siirtymä minuutteina.


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Käyttäjä asetukset](../usersettings.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
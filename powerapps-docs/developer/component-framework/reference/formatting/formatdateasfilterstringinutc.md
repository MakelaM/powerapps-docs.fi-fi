---
title: Forfordateasfilsuodastingutc | Microsoft Docs
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
ms.assetid: a604fbbf-6d09-450d-b686-7a5cb3f3a2bc
ms.openlocfilehash: 2242e1badabd740bf414340ae3d11b29e6000ebb
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72343147"
---
# <a name="formatdateasfilterstringinutc"></a>formatDateAsFilterStringInUTC

[!INCLUDE [formatdateasfilterstringinutc-description](includes/formatdateasfilterstringinutc-description.md)]

## <a name="syntax"></a>Syntaksi

`context.formatting.formatDateAsFilterStringInUTC(value, includeTime)`

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|arvo|`Date`|kyllä|Muotoiltava päivä määrä.|
|includeTime|`boolean`|kyllä| Jos Time-komponentti tulee sisällyttää paluu arvoon.|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `string`


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Muotoilu](../formatting.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
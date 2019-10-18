---
title: getEntityMetadata | Microsoft Docs
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
ms.assetid: 6a334af7-ca5b-449c-b90f-0901824654d2
ms.openlocfilehash: 89dc2e9d567b8ff38c41df2074d2a85d6bcaf467
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72340962"
---
# <a name="getentitymetadata"></a>getEntityMetadata

[!INCLUDE [getentitymetadata-description](includes/getentitymetadata-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.utils.getEntityMetadata(entityName, attributes)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|entityName|`String`|Kyllä|Entiteetin looginen nimi.|
|määritteet|`String[]`|Ei|Määritteen metatietojen hakeminen.|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `Promise<EntityMetadata>`


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Utility](../utility.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
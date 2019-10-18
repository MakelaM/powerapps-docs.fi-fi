---
title: Hasententprivilege | Microsoft Docs
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
ms.assetid: f22723f0-c606-465c-abba-0a8c46a10e32
ms.openlocfilehash: f370d14f0b978d7ac4b6e6535677e06e7cf3f86e
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72340893"
---
# <a name="hasentityprivilege"></a>hasEntityPrivilege

[!INCLUDE [hasentityprivilege-description](includes/hasentityprivilege-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.utils.hasEntityPrivilege(entityTypeName, privilegeType, privilegeDepth)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|Entytypename|`string`|Kyllä|Entiteettityypin nimi|
|privilegeType|`enum`|Ei|Entiteetin käyttö oikeus tyypit. Sillä on seuraavat ominaisuudet:<br/>- `None = 0`<br/>- `Create = 1` <br/>- `Read = 2`<br/>- `Write = 3`<br/>- `Delete = 4`<br/>- `Assign =5`<br/>- `Share =6`<br/>- `Append =7`<br/>- `AppendTo =8`|
|privilegeDepth|`enum`|Ei|Entiteetin käyttö oikeuksien syvyys. Sillä on seuraava määrite: <br/>- `None = -1`<br/>- `Basic = 0`<br/>- `Local = 1`<br/>- `Deep = 2`<br/>- `Global = 3`|

## <a name="return-value"></a>Palautusarvo

**Tyyppi**: `boolean`

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Utility](../utility.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
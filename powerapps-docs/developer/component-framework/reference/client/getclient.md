---
title: getClient | Microsoft Docs
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
ms.assetid: 4b7c18f8-cd00-4f39-8f88-ed9306d6a055
ms.openlocfilehash: 503d24d97061548132f912351a58fbce68082d18
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72345746"
---
# <a name="getclient"></a>getClient

[!INCLUDE [getclient-description](includes/getclient-description.md)]

## <a name="syntax"></a>Syntaksi

`context.client.getClient()`

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu) 



## <a name="return-value"></a>Palautusarvo

Tyyppi: `String`

Palauttaa arvon, joka ilmaisee asiakkaan, jolle komento sarja suoritetaan.

|||
|-----|-----|
|Web| WWW-sovellus tai yhdistetty liittymä|
|Outlook| Outlook|
|Mobiililaitteiden| Mobiilisovellus|



### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Asiakas](../client.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
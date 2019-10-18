---
title: getResource | Microsoft Docs
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
ms.assetid: 5c04ba7c-acfe-4375-8dd8-6c537ded9352
ms.openlocfilehash: 919606c7b6669265a8bdd4f7b43080564e87a80f
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72341399"
---
# <a name="getresource"></a>getResource

[!INCLUDE [getresource-description](includes/getresource-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.resources.getResource(id, success, failure)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|Tunnus|`String`|Kyllä|Resurssi merkki jonon tunnus.|
|menestys|`String`|Ei|Onnistumis kutsu. Resurssi tiedot palautetaan Base 64-koodatussa muodossa.|
|epäonnistuminen|`String`|Ei|Virheen takaisinkutsu.|


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Resources](../resources.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
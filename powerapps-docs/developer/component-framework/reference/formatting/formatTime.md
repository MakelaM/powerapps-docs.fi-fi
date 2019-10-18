---
title: Forfortime | Microsoft Docs
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
ms.assetid: 148964b5-106e-4f2e-8038-9086d29dc54f
ms.openlocfilehash: cc2c7dfdbe9952d69dcda9fdd4c813965f539478
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72343331"
---
# <a name="formattime"></a>formatTime

[!INCLUDE [formattime-description](includes/formattime-description.md)]

## <a name="syntax"></a>Syntaksi

`context.formatting.formatTime(value, behavior);`

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|arvo|`Date`|Kyllä|Muotoiltava päivä määrä.|
|Käyttäytymistä|`DateTimeFieldBehavior`|Kyllä|Muotoiltavan DateTime-objektin toiminta. @No__t_0 on seuraavat ominaisuudet:<br/>-  `None =0`: Tuntematon DateTime-toiminta <br/>-  `UserLocal =1`: kunnioita käyttäjän paikallista aikaa. Päivä määrät, jotka on tallennettu UTC-muodossa<br/>-  `TimeZoneIndependent =3`: päivä määrät ja kellon ajat, jotka on tallennettu ilman muuntamista UTC-aikaan|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `string`


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Muotoilu](../formatting.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
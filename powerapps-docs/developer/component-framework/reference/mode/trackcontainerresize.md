---
title: Trackcontainin koon muutto | Microsoft Docs
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
ms.assetid: c5f482c2-dde2-460b-89a7-39e0efcc5704
ms.openlocfilehash: 8f9bc1ef17bdcb762e992d9f77dcdcd7ba1e8c50
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342549"
---
# <a name="trackcontainerresize"></a>trackContainerResize

[!INCLUDE [trackcontainerresize-description](includes/trackcontainerresize-description.md)].

Jos komponentin isännöivä pääkohde tarjoaa rajoituksensa mallipohjaisten sovellusten korkeudesta, sama koskee alikomponenttia oikein. Useimmissa tilanteissa pääkontekstia ei kuitenkaan rajoita komponentin korkeutta, joten se saa "-1" merkiksi siitä, että se voi kasvaa entisestään.

Pohjaan perustuvan sovelluksen pääkontekstissa on aina korkeus ja leveys komponentille vetämällä ja pudottamalla.

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.mode.trackContainerResize(value)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|arvo|`Boolean`|Kyllä|`True` Jos ohjaus objektien on seurattava säiliön kokoa, komponentin on oltava allocatedWidth tai allocatedHeight.|


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Mode](../mode.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)

---
title: CaptureImage | Microsoft Docs
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
ms.assetid: 1d9c0063-add2-4002-acab-1be07ca1f6b6
ms.openlocfilehash: e642af17e02334b45041df87386885536e1810af
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72345677"
---
# <a name="captureimage"></a>captureImage

[!INCLUDE[./includes/captureimage-description.md](./includes/captureimage-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.device.captureImage(options)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|`options`|`Object`|Ei|Kuvan sieppaus asetukset.|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `Promise<FileObject>`

Näytä [lupaus](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) ja [FileObject](../fileobject.md)

## <a name="remarks"></a>Huomautuksia

@No__t_0-parametri objektilla on seuraavat ominaisuudet:

|Nimi|Tyyppi|Kuvaus|
| ---|----|-----------|
|`allowEdit`|`Boolean`|Ilmaisee, Muokataanko kuvaa ennen tallentamista.|
|`height`|`Number`|Siepattavan kuvan korkeus.|
|`preferFrontCamera`|`Boolean`|Ilmaisee, sieppaanko kuva käyttämällä laitteen etukameraa.|
|`quality`|`Number`|Kuva tiedoston laatu prosentteina.|
|`width`|`Number`|Siepattavan kuvan leveys.|


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Laite](../device.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
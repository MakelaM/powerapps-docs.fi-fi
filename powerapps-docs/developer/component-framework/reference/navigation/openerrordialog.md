---
title: Openerroerrodialog | Microsoft Docs
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
ms.assetid: 10c154b9-45a0-44ee-a621-73d6a9009c6d
ms.openlocfilehash: c3371b7c3ea8bde869acc261ab7d4fc8f28ba7da
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342434"
---
# <a name="openerrordialog"></a>openErrorDialog

[!INCLUDE [openerrordialog-description](includes/openerrordialog-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.navigation.openErrorDialog(options)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|asetukset|`ErrorDialogOptions`|Kyllä|Virhe valinta ikkunan asetukset. Errorodialogoptions-kohteella on seuraavat ominaisuudet: <br/>- **tiedot**: `String`. Virheen tiedot. Kun määrität tämän, **lataus lokin tiedosto-** painike on käytettävissä virhe sanomassa, ja sen napsauttaminen antaa käyttäjien ladata teksti tiedoston tässä määritteessä määritettyyn sisältöön.<br/>- **errorCode**: `Number`. Virhe koodi. Jos vain määrität errorCode-kohteen, virhe koodin sanoma noudetaan palvelimesta automaattisesti ja näytetään virhe valinta ikkunassa. Jos määrität **errorCode** -arvon, näyttöön tulee virhe valinta ikkuna, jossa on oletus virhe sanoma.<br/>- **sanoma**: `String`. Virhe valinta ikkunassa näytettävä viesti. Sinun on asetettava joko **errorCode** -tai **Message** -määrite.|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `Promise`

## <a name="remarks"></a>Huomautuksia

Tarkastele [lupausta](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) ja [tiedostoa](https://developer.mozilla.org/docs/Web/API/File)


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Siirtyminen](../navigation.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
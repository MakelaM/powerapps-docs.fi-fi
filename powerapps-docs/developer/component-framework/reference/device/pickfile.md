---
title: PickFile | Microsoft Docs
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
ms.assetid: aae27c64-33c4-47f1-b833-4c04161c01e2
ms.openlocfilehash: a36731edc7ee5cc8edede499fc791595bc00bc8c
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72344619"
---
# <a name="pickfile"></a>pickFile

[!INCLUDE[./includes/pickfile-description.md](./includes/pickfile-description.md)]

## <a name="syntax"></a>Syntaksi

`context.device.pickFile(options)`

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|`options`|`Object`|Ei|Tiedoston poiminta vaihtoehdot.|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `Promise<FileObject[]>`

Näytä [lupaus](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) ja [FileObject](../fileobject.md)

## <a name="remarks"></a>Huomautuksia

@No__t_0-parametri objektilla on seuraavat ominaisuudet:

|Nimi|Tyyppi|Kuvaus|
|--|--|--|
|`accept`|`String`|Valittava kuva tiedosto tyypit. Kelvolliset arvot ovat *ääni*, *video*tai *kuva*.|
|`allowMultipleFiles`|`Boolean`|Ilmaisee, sallitaanko usean tiedoston valitseminen|
|`maximumAllowedFileSize`|`Number`|Valittaisten tiedostojen enimmäiskoko|


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Laite](../device.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
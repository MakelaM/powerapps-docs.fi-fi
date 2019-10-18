---
title: openFile | Microsoft Docs
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
ms.assetid: ae94e467-d12c-4a74-96f0-05a09e03c5f8
ms.openlocfilehash: 5de6eefb37450fde50127829f2a922252d08a4fb
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342687"
---
# <a name="openfile"></a>openFile

[!INCLUDE [openfile-description](includes/openfile-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.navigation.openFile(file, options)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|Tiedosto|`FileObject`|Kyllä|Avattava tiedostoa kuvaava objekti. FileObject-kohteella on seuraavat ominaisuudet: <br/>- **FileContent**: `String`. Tiedoston sisältö. <br/>- **tiedosto nimi**: `String`. Tiedoston nimi.<br/>- **tiedosto**koko: `Number`. Tiedoston koko kilo tavuina. <br/>- **MimeType**: `String`. Tiedoston MIME-tyyppi.|
|asetukset|`Object`|Ei|Objekti, joka kuvaa, avataanko vai tallennetaanko tiedosto. Objektilla on seuraava määrite: <br/>- **openmode**: Määritä 1, jos haluat avata; 2, jos haluat tallentaa. 
Jos et määritä tätä parametria, oletus arvo on 1 (avoin). Tätä parametria tuetaan vain Unified Interface-liittymässä.|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `Promise`

## <a name="remarks"></a>Huomautuksia

Näytä [lupaus](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) ja [FileObject](../fileobject.md)


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Siirtyminen](../navigation.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
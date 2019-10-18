---
title: lookupObjects | Microsoft Docs
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
ms.assetid: d213b401-cfc4-44df-b55c-f040fb6d7072
ms.openlocfilehash: 0dca29df3537389decefe2584d2fc931cea8979c
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72341146"
---
# <a name="lookupobjects"></a>lookupObjects

[!INCLUDE [lookupobjects-description](includes/lookupobjects-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.utils.lookupObjects(lookupOptions)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|LookupOptions|`UtilityApi.LookupOptions`|Kyllä|Määrittää valinta ikkunan avaamis vaihtoehdot. LookupOptions-kohteella on seuraavat ominaisuudet:<br/>- **Allowmultiselect**: `Boolean`. Ilmaisee, salliko haku useamman kuin yhden kohteen valitsemisen.<br/>- **Defaytytitytype**: `String`. Käytettävä oletus entiteettityypin.<br/>- **Defaulviewid**: `String`. Käytettävä oletus näkymä.<br/>- **Entitytypes**: `String[]`. Näytettävät entiteettityypit.<br/>- **Viewids**: `String[]`. Näkymän valitsimen käytettävissä olevat näkymät. Vain järjestelmä näkymiä tuetaan (ei käyttäjä näkymiä).|

## <a name="return-value"></a>Palautusarvo

Tyyppi: [Promise](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) <[EntityReference](../entityreference.md)[] >


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Utility](../utility.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
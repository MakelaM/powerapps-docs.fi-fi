---
title: openConfirmDialog | Microsoft Docs
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
ms.assetid: 83f2c208-696c-48b1-b65c-2ba7374d6cfc
ms.openlocfilehash: 8b7bda89b9c8d83614a4a95281853676db9cf568
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342480"
---
# <a name="openconfirmdialog"></a>openConfirmDialog

[!INCLUDE [openconfirmdialog-description](includes/openconfirmdialog-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.navigation.openConfirmDialog(confirmStrings, options)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|Confirmstring|`ConfirmDialogStrings`|Kyllä|Valinta ikkunassa käytetyt merkki jonot. Confirmdialogstring-määritteillä on seuraavat ominaisuudet:<br/>- **otsikko**: `String`. Vahvistus valinta ikkunassa näytettävä otsikko. <br/>- **alaotsikko**: `String`. Vahvistus valinta ikkunassa näytettävä alaotsikko.<br/>- **teksti**: `String`. Vahvistus valinta ikkunassa näytettävä viesti.<br/>- **Confirmbutton-otsikko**: `String`. Vahvista painikkeen nimi. Jos et määritä painikkeen otsikkoa, **OK** (käyttäjän ensisijaisella kielellä) on käytössä painikkeen nimenä.<br/>- **Cancanbuttbuttlabel**: `String` peruutus painikkeen nimi. Jos et määritä peruutus painikkeen otsikkoa, painikkeen nimenä käytetään **Peruuta** -painiketta.|
|asetukset|`ConfirmDialogOptions`|Ei|Valinta ikkunan asetukset. ConfirmDialogOptions-kohteella on seuraavat ominaisuudet:<br/>- **Korkeus**: `Number`. Vahvistus valinta ikkunan korkeus kuva pisteinä. <br/>- **Leveys**: `Number`. Vahvistus valinta ikkunan leveys kuva pisteinä|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `Promise<ConfirmDialogResponse>`

Kuvaus: palauttaa objektin, jolla on vahvistettu (Boolean)-määrite, joka ilmaisee, sulkeiko valinta ikkuna napsauttamalla vahvista-painiketta.

## <a name="remarks"></a>Huomautuksia

Näytä [lupaus](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) 


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Siirtyminen](../navigation.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
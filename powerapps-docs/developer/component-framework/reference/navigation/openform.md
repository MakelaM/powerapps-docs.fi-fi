---
title: openForm | Microsoft Docs
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
ms.assetid: bea56947-d976-4974-9ac7-2d5f5c7b6732
ms.openlocfilehash: d0754030de4880f0ad693105e96b47d785f1561b
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342365"
---
# <a name="openform"></a>openForm

[!INCLUDE [openform-description](includes/openform-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.navigation.openForm(options, parameters)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|asetukset|`EntityFormOptions`|Kyllä|Entiteettilomakkeen asetukset lomakkeen avaamista varten. Ententformoptions-määritteillä on seuraavat ominaisuudet:<br/>- **Createfromentity**: `Lookup`. Määrittää tietueen, joka antaa oletus arvot yhdistettyjen määritteiden arvojen perusteella. Haku objektilla on seuraavat merkki jono ominaisuudet: `entityType`, `id` ja `name`. <br/>- **Ententid**: `String`. Sen entiteettitietueen tunnus, josta lomake näytetään.<br/>- **Ententname**: `String`. Sen entiteetin looginen nimi, jolle lomake näytetään.<br/>- **FormID**: `String`. Näytettävän lomake esiintymän tunnus.<br/>- **Korkeus**: `Number`. Lomake ikkunan korkeus kuva pisteinä.<br/>- **Openinnnewwindow**: `boolean`. Näytetäänkö lomake uudessa ikkunassa.<br/>- **Useequiccreateform**: `Boolean`. avaatko Pikaluonnin lomakkeen. Jos et määritä tätä, `false` välitetään oletusarvoisesti.<br/>- **Leveys**: `Number`. Kuva pisteinä näytettävän lomake ikkunan leveys.<br/>- **Windowposition**: `Number`. Määritä yksi seuraavista arvoista lomakkeen ikkunan sijaintiin näytössä: `1:center` <br/> `2:side`|
|Parametrit|`Object`|Ei|Sanasto objekti, joka välittää lomakkeeseen ylimääräisiä parametreja. Virheelliset parametrit aiheuttavat virheen. Lisä tietoja on [Ohje aiheessa kenttien arvot käyttämällä lomakkeeseen välitettyjä parametreja](https://docs.microsoft.com/en-us/powerapps/developer/model-driven-apps/set-field-values-using-parameters-passed-form) ja [määrittämällä lomake hyväksymään mukautetut kysely merkki jonon parametrit](https://docs.microsoft.com/en-us/powerapps/developer/component-framework/sample-controls/navigation-api-control)|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `Promise<OpenFormSuccessResponse>`

## <a name="remarks"></a>Huomautuksia

Näytä [lupaus](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise)

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Siirtyminen](../navigation.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
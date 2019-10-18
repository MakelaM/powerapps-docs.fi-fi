---
title: Ominaisuus asetus-alkio | Microsoft Docs
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
ms.assetid: 996f10e5-8057-40ea-9680-555e4cd682ff
ms.openlocfilehash: 98e0bcf7588e72f001e45471c87f0050dd0846ba
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346229"
---
# <a name="property-set-element"></a>ominaisuus – sarjan alku

[!INCLUDE [property-set-description](includes/property-set-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset

## <a name="attributes"></a>Määritteet

|Nimi|Kuvaus|Tyyppi|Pakollinen|
|--|--|--|--|
|`name`|Kentän nimi|`string`|Kyllä|
|`display-name-key`|Käytetään mukautus näytöissä lokalisoituina merkki jonoina, jotka kuvailevat ominaisuuden nimeä|`string`|Kyllä|
|`description-key`|Käytetään mukautus näytöissä lokalisoituina merkki jonoina, jotka kuvailevat ominaisuuden kuvausta|`string`|Valinnainen|
|`of-type`|Määrittää ominaisuuden tieto tyypin|Näytä [Huomautukset](#remarks)|Valinnainen|
|`required`|Ilmaisee, onko ominaisuus pakollinen|`boolean`|Valinnainen|
|`of-type-group`|Luettelossa määritetyn tyyppi ryhmän nimi|`string`|Valinnainen|
|`usage`|Käyttö-määrite määrittää, onko ominaisuuden tarkoitus edustaa entiteettityyppi, jonka komponentti voi muuttaa (sidottu) tai vain luku-arvot (syöte)|`bound` tai `input`|Kyllä|

## <a name="parent-elements"></a>Pääelementit

|Elementti|Kuvaus|
|--|--|
|[data-set](data-set.md)|[!INCLUDE [data-set-description](includes/data-set-description.md)]|

## <a name="child-elements"></a>Alielementit

|Elementti|Kuvaus|Esiintymät|
|--|--|--|
|[tyypit](types.md)||vähintään 0|

### <a name="remarks"></a>Huomautuksia

@No__t_0 määritteen arvon on oltava jokin seuraavista:

[!INCLUDE [type-table](includes/type-table.md)]

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
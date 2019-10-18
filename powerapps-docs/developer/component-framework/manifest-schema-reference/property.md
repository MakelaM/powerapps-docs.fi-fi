---
title: Ominaisuus-alkio | Microsoft Docs
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
ms.assetid: 45f4872d-c1d2-4c5a-8721-251b96ede370
ms.openlocfilehash: ee4e0b0259d5978f3e84757d4023827ada45f01e
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346137"
---
# <a name="property-element"></a>ominaisuus-alkio

[!INCLUDE [property-description](includes/property-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="attributes"></a>Määritteet

|Nimi|Kuvaus|Tyyppi|Pakollinen|
|--|--|--|--|
|`name`|Ominaisuuden nimi|`string`|Kyllä|
|`display-name-key`|Käytetään mukautus näytöissä lokalisoituina merkki jonoina, jotka kuvaavat ominaisuuden nimeä.|`string`|Kyllä|
|`of-type`|Määrittää ominaisuuden tieto tyypin|Näytä [Huomautukset](#remarks)|Valinnainen|
|`usage`|Käyttö-määrite määrittää, onko ominaisuuden tarkoitus edustaa entiteettityyppi, jonka komponentti voi muuttaa (sidottu) tai vain luku-arvot (syöte)|`bound` tai `input`|Valinnainen|
|`required`|Onko ominaisuus pakollinen vai ei|`boolean`|Valinnainen|
|`of-type-group`|Luettelossa määritetyn tyyppi ryhmän nimi|`string`|Valinnainen|
|`description-key`|Käytetään mukautus näytöissä lokalisoituina merkki jonoina, jotka kuvaavat ominaisuuden kuvausta.|`string`|Valinnainen|
|`default-value`|Komponentille annettu oletus määritys arvo. Mallipohjaisissa sovelluksissa tämä määrite sallitaan vain syötteille, koska sidotuille parametreille on oletettavasti liitetty kenttä.|`string`|Valinnainen|

### <a name="remarks"></a>Huomautuksia

@No__t_0 määritteen arvon on oltava jokin seuraavista:

[!INCLUDE [type-table](includes/type-table.md)]

## <a name="parent-elements"></a>Pääelementit

|Elementti|Kuvaus|
|--|--|
|[manifest](manifest.md)|[!INCLUDE [manifest-description](includes/manifest-description.md)]|


## <a name="example"></a>Esimerkki

```xml
<property name="myFirstProperty" display-name-key="myFirstProperty_Display_Key" 
description-key="myFirstProperty_Desc_Key" of-type="SingleLine.Text" usage="bound" required="true" />
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)

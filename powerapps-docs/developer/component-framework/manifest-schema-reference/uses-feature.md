---
title: käyttö – ominaisuus | Microsoft Docs
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
ms.assetid: 87f5e921-4114-4710-a362-db741426a69b
ms.openlocfilehash: fe4d384c8dd53fc0f9efcf5558252984a4be74a3
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72345884"
---
# <a name="uses-feature-element"></a>käyttö-ominaisuus-osa

Ilmaisee, mitä ominaisuutta niiden osat haluavat käyttää.

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset

## <a name="parent-element"></a>Pääelementin

|Elementti|Kuvaus|
|--|--|
|ominaisuus – käyttö|Ominaisuus – käyttö-elementti toimii kääreenä käyttö ominaisuuksien elementtien ympärillä, joiden avulla kehittäjät voivat itse määrittää, mitä ominaisuuksia heidän komponenttiensa haluaa käyttää. Jos ominaisuuksia ei ole määritetty, ominaisuus-käyttö-elementtiä ei tarvita.|

## <a name="child-elements"></a>Alielementit

|Elementti|Kuvaus|Tyyppi|Pakollinen|
|--|--|---|----|
|Nimi|Komponentissa määritetyn ominaisuuden nimi|`string`|Kyllä|
|Tarvitaan|Ilmaisee, vaatiiko komponentti tätä ominaisuutta vai ei|`boolean`|Kyllä|

### <a name="example"></a>Esimerkki 

```XML
<feature-usage>
    <uses-feature name="WebAPI" required="true" />
</feature-usage>
```

Alla olevassa taulukossa näytetään näiden asetusten suhde siihen, mitä koodissa tapahtuu suorituksen aikana, onko ominaisuus toiminto käytettävissä kutsuttavissa olevassa luettelossa määritettyjen käyttö ominaisuuksien perusteella.

|Luettelo|Jos isäntä tukee|Jos Host ei tue|
|----|----|-----|
|`uses-feature name="device.captureImage" required=”true"`|`Context.device.captureImage != null`, mitään tarkistusta ei tarvita.|Varoitus suunnittelun aikana. Komponentin lataaminen epäonnistuu suorituksen aikana.|
|`uses-feature name="device.captureImage" required=”false"`|`Context.device.captureImage != null`|`Context.device.captureImage == null`, komponentti voi toteuttaa käsittelyn muokkaavasti tarkistaa tämän suorituksen aikana. |
|ei mitään|`Context.device.captureImage == null` |`Context.device.captureImage == null` |

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
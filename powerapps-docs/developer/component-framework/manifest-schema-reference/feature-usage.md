---
title: ominaisuus – käyttö | Microsoft Docs
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
ms.openlocfilehash: 21e76a2a17910fe36967364f063ff2fc9b25e153
ms.sourcegitcommit: 63ea15e2f861d43333aacda19230cd8922d7bdfd
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/01/2019
ms.locfileid: "72339628"
---
# <a name="feature-usage-element"></a>ominaisuus – käyttö-osa

Ominaisuus – käyttö-elementti toimii pakettina `uses-feature`-elementtien ympärillä, joiden avulla kehittäjät voivat itse määrittää, mitä ominaisuuksia heidän komponenttiensa haluaa käyttää. Jos ominaisuuksia ei ole määritetty, ominaisuus-käyttö-elementtiä ei tarvita.

## <a name="available-for"></a>Käytettävissä kohteelle

Mallipohjaiset sovellukset

## <a name="child-elements"></a>Alielementit

|Elementti|Kuvaus|Käytettävissä kohteelle|
|--|--|-----|
|[käyttö-ominaisuus](uses-feature.md)|Ilmaisee, mitä ominaisuutta niiden osat haluavat käyttää.|Mallipohjaiset sovellukset|


## <a name="example"></a>Esimerkki

```XML
<feature-usage>
    <uses-feature name="Device.captureAudio" required="true" />
    <uses-feature name="Device.captureImage" required="true" />
    <uses-feature name="Device.captureVideo" required="true" />
    <uses-feature name="Device.getBarcodeValue" required="true" />
    <uses-feature name="Device.getCurrentPosition" required="true" />
    <uses-feature name="Device.pickFile" required="true" />
    <uses-feature name="Utility" required="true" />
    <uses-feature name="WebAPI" required="true" />
 </feature-usage>
```

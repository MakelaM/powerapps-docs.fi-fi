---
title: Ententforcriptions | Microsoft Docs
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
ms.assetid: 418871c0-59dc-4a7c-a8f9-9364a19f7662
ms.openlocfilehash: 7429a5bac040e3c20412ac0916743a57d9d5710f
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72344366"
---
# <a name="entityformoptions"></a>Ententforcriptions

Antaa käyttöösi kaikki Entiteettilomakkeiden tiedot.

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="properties"></a>Ominaisuudet

### <a name="createfromentity"></a>createFromEntity

Määrittää tietueen, joka antaa oletus arvot yhdistettyyn määrite arvoon pohjautuen. Haku-objektilla on seuraavat ominaisuudet: entiteetin tyyppi, tunnus ja nimi.

Tyyppi: [EntityReference](entityreference.md)

### <a name="entityid"></a>Ententid

Sen entiteettitietueen yksilöivä tunnus, jolle lomake näytetään. 

**Tyyppi**: `string`

### <a name="entityname"></a>entityName

Sen entiteetin looginen nimi, jolle lomake näytetään. 

**Tyyppi**: `string`

### <a name="formid"></a>formId

Näytettävän lomake esiintymän tunnus.

**Tyyppi**: `string`

### <a name="height"></a>korkeus

Lomake ikkunan korkeus kuva pisteinä.

**Tyyppi**: `number`

### <a name="openinnewwindow"></a>Openinnnewwindow

Näytetäänkö lomake uudessa ikkunassa.

**Tyyppi**: `boolean`

### <a name="usequickcreateform"></a>Usaequiccreateform

avaatko Pikaluonnin lomakkeen. Jos et määritä tätä, oletus arvo on FALSE. 

**Tyyppi**: `boolean`

### <a name="width"></a>leveys

Kuva pisteinä näytettävän lomake ikkunan leveys.

**Tyyppi**: `boolean`

### <a name="windowposition"></a>windowPosition

Määrittää ikkunan sijainnin näytössä.

**Tyyppi**: `number`

WindowPosition-arvo on luku, jolla on seuraavat mahdolliset arvot

|Value|Sijainti|
|---|---|
|1|Keskus|
|2|Puolella|


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)
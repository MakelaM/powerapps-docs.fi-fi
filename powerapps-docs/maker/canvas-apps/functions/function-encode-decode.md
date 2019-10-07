---
title: EncodeUrl- ja PlainText-funktiot | Microsoft Docs
description: PowerAppsin EncodeUrl- ja PlainText-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c21cae9e39e3a9a1461ac3fafe576f40b70c0818
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985029"
---
# <a name="encodeurl-and-plaintext-functions-in-powerapps"></a>PowerAppsin EncodeUrl- ja PlainText-funktiot
Koodaa merkkijonoja ja poistaa niiden koodauksia.

## <a name="description"></a>Kuvaus
**Encodeurl** -funktiolla KOODATAAN URL-merkki jono, joka korvaa tietyt ei-aakkosnumeeriset merkit, joissa on% ja heksa desimaali luku.  

**Plaintext** -ominaisuus poistaa HTML-ja XML-tunnisteet ja muuntaa jotkin Tunnisteet, kuten nämä, sopivaan symboliin:

* **&amp;nbsp;**
* **&amp;quot;**

Näiden funktioiden paluuarvo on koodattu merkkijono tai merkkijono, jonka koodaus on poistettu. Tämä toiminto ei poista kaikkia HTML-ja XML-tunnisteita. 

## <a name="syntax"></a>Syntaksi
**EncodeUrl**( *Merkkijono* )

* *String* – Pakollinen.  Koodattava URL-osoite.

**PlainText**( *Merkkijono* )

* *String* – Pakollinen. Merkkijono, josta poistetaan HTML- ja XML-tunnisteet.

## <a name="examples"></a>Esimerkkejä
Jos näytät tekstivalikoimassa RSS-syötteen ja asetat valikoimassa olevan selitteen **[Text](../controls/properties-core.md)** -ominaisuudeksi **ThisItem.description**, otsikossa saattaa näkyä raakaa HTML- tai XML-koodia esimerkin mukaisesti:

```html
    <p>We have done an unusually&nbsp;&quot;deep&quot; globalization and localization.<p>
```

Jos asetat otsikon **[Text](../controls/properties-core.md)** -ominaisuudeksi **PlainText(ThisItem.description)** , teksti näkyy tämän esimerkin mukaisesti:

```
    We have done an unusually "deep" globalization and localization.
```
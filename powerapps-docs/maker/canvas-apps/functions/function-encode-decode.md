---
title: EncodeUrl- ja PlainText-funktiot | Microsoft Docs
description: PowerAppsin EncodeUrl- ja PlainText-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 30d3378f46e587e45314c30be1fce3c36b2bb120
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42832993"
---
# <a name="encodeurl-and-plaintext-functions-in-powerapps"></a>PowerAppsin EncodeUrl- ja PlainText-funktiot
Koodaa merkkijonoja ja poistaa niiden koodauksia.

## <a name="description"></a>Kuvaus
**EncodeUrl**-funktio koodaa URL-osoitemerkkijonon ja korvaa ei-aakkosnumeeriset merkit %:llä ja heksadesimaalinumerolla.  

**PlainText**-funktio poistaa HTML- ja XML-tunnisteet ja muuntaa esimerkiksi seuraavat tunnisteet asianmukaisiksi merkeiksi:

* **&amp;nbsp;**
* **&amp;quot;**

Näiden funktioiden paluuarvo on koodattu merkkijono tai merkkijono, jonka koodaus on poistettu.   

## <a name="syntax"></a>Syntaksi
**EncodeUrl**( *Merkkijono* )

* *String* – Pakollinen.  Koodattava URL-osoite.

**PlainText**( *Merkkijono* )

* *String* – Pakollinen. Merkkijono, josta poistetaan HTML- ja XML-tunnisteet.

## <a name="examples"></a>Esimerkkejä
Jos näytät tekstivalikoimassa RSS-syötteen ja asetat valikoimassa olevan selitteen **[Text](../controls/properties-core.md)**-ominaisuudeksi **ThisItem.description**, otsikossa saattaa näkyä raakaa HTML- tai XML-koodia esimerkin mukaisesti:

    <p>We have done an unusually&nbsp;&quot;deep&quot; globalization and localization.<p>

Jos asetat otsikon **[Text](../controls/properties-core.md)**-ominaisuudeksi **PlainText(ThisItem.description)**, teksti näkyy tämän esimerkin mukaisesti:

    We have done an unusually "deep" globalization and localization.

---
title: EncodeUrl- ja PlainText-funktiot | Microsoft Docs
description: PowerAppsin EncodeUrl- ja PlainText-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 7454eacbcfaaacc15eb617e673f48520ca33b6dc
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
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

* *Merkkijono* – Pakollinen.  Koodattava URL-osoite.

**PlainText**( *Merkkijono* )

* *Merkkijono* – Pakollinen. Merkkijono, josta poistetaan HTML- ja XML-tunnisteet.

## <a name="examples"></a>Esimerkkejä
Jos näytät tekstivalikoimassa RSS-syötteen ja asetat valikoimassa olevan otsikon **[Text](../controls/properties-core.md)**-ominaisuudeksi **ThisItem.description**, otsikossa saattaa näkyä raakaa HTML- tai XML-koodia esimerkin mukaisesti:

    <p>We have done an unusually&nbsp;&quot;deep&quot; globalization and localization.<p>

Jos asetat otsikon **[Text](../controls/properties-core.md)**-ominaisuudeksi **PlainText(ThisItem.description)**, teksti näkyy tämän esimerkin mukaisesti:

    We have done an unusually "deep" globalization and localization.

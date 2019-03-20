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
ms.openlocfilehash: 9956332c35b4df2773b2634cb7f66d2ea96469e4
ms.sourcegitcommit: 1b8578e38a09220ac66c5123644714139fc3c9e5
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/01/2019
ms.locfileid: "57800441"
---
# <a name="encodeurl-and-plaintext-functions-in-powerapps"></a>PowerAppsin EncodeUrl- ja PlainText-funktiot
Koodaa merkkijonoja ja poistaa niiden koodauksia.

## <a name="description"></a>Kuvaus
**EncodeUrl** funktio koodaa URL-osoitemerkkijonon ja korvaa tietyt ei-aakkosnumeeriset merkit %: llä ja heksadesimaalinumerolla.  

**PlainText** -funktio poistaa HTML- ja XML-tunnisteet ja muuntaa esimerkiksi seuraavat asianmukaisiksi merkeiksi tietyt tunnisteet:

* **&amp;nbsp;**
* **&amp;quot;**

Näiden funktioiden paluuarvo on koodattu merkkijono tai merkkijono, jonka koodaus on poistettu. Tämä funktio ei poista kaikki HTML- ja XML-tunnisteet. 

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

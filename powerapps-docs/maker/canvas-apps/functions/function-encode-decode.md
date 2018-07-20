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
ms.openlocfilehash: 3f7df27ed5b49d60437ba8e5a070fcb676f828e4
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39020695"
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

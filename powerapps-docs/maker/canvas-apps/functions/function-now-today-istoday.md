---
title: Now-, Today- ja IsToday-funktiot | Microsoft Docs
description: Viitetiedot PowerAppsin Now-, Today- ja IsToday-funktioille, mukaan lukien syntaksi ja esimerkkejä
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
ms.openlocfilehash: 410e9be47b4356a97292eb5de17c5dc10885fae3
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31829136"
---
# <a name="now-today-and-istoday-functions-in-powerapps"></a>Now-, Today- ja IsToday-funktiot PowerAppsissa
Palauttaa nykyisen päivämäärän ja ajan ja testaa, vastaako päivämäärä/aika-arvo tätä päivää.

## <a name="description"></a>Kuvaus
**Now**-funktio palauttaa nykyisen päivämäärän ja ajan päivämäärä/aika-arvona.

**Today**-funktio palauttaa nykyisen päivämäärän päivämäärä/aika-arvona. Aikaosa vastaa keskiyötä. **Today**-funktiolla on sama arvo koko päivän ajan tämän päivän keskiyöstä huomiseen keskiyöhön.

**IsToday**-funktiolla testataan, onko päivämäärä/aika-arvo tämän päivän keskiyön ja huomisen keskiyön välillä. Tämä funktio palauttaa totuusarvon **true** tai **false**.

Kaikki nämä funktiot toimivat nykyisen käyttäjän paikallisen ajan mukaisesti.

Lisätietoja on myös kohdassa [Päivämäärien ja kellonaikojen käsitteleminen](../show-text-dates-times.md).

## <a name="syntax"></a>Syntaksi
**Now**()

**Today**()

**IsToday**( *DateTime* )

* *DateTime* – Pakollinen.  Testattava päivämäärä/aika-arvo.

## <a name="examples"></a>Esimerkkejä
Tämän osion esimerkkejä varten nykyinen aika on **03.59** **12. helmikuuta 2015** ja kieli on **en-us**.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Text( Now(), "mm/dd/yyyy hh:mm:ss" )** |Hakee nykyisen päivämäärän ja ajan ja näyttää sen merkkijonona. |"02/12/2015 03:59:00" |
| **Text( Today(), "mm/dd/yyyy hh:mm:ss" )** |Hakee vain nykyisen päivämäärän, jättää aikaosan keskiyöhön ja näyttää tuloksen merkkijonona. |"02/12/2015 00:00:00" |
| **IsToday( Now() )** |Testaa, onko nykyinen päivämäärä ja aika tämän päivän keskiyön ja huomisen keskiyön välillä. |**true** |
| **IsToday( Today() )** |Testaa, onko nykyinen päivämäärä tämän päivän keskiyön ja huomisen keskiyön välillä. |**true** |
| **Text( DateAdd( Now(), 12 ), "mm/dd/yyyy hh:mm:ss" )** |Hakee nykyisen päivämäärän ja ajan, lisää tulokseen 12 päivää ja näyttää tuloksen merkkijonona. |"02/24/2015 03:59:00" |
| **Text( DateAdd( Today(), 12 ), "mm/dd/yyyy hh:mm:ss" )** |Hakee nykyisen päivämäärän, lisää tulokseen 12 päivää ja näyttää tuloksen merkkijonona. |"02/24/2015 00:00:00" |
| **IsToday( DateAdd( Now(), 12 ) )** |Testaa, onko nykyinen päivämäärä ja aika plus 12 päivää tämän päivän keskiyön ja huomisen keskiyön välillä. |**false** |
| **IsToday( DateAdd( Today(), 12 ) )** |Testaa, onko nykyinen päivämäärä plus 12 päivää tämän päivän keskiyön ja huomisen keskiyön välillä. |**false** |


---
title: DateAdd-, DateDiff- ja TimeZoneOffset-funktiot | Microsoft Docs
description: PowerAppsin DateAdd-, DateDiff- ja TimeZoneOffset-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/23/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8108dbc1c78ba57e989f7bebeb8bd0f42f696360
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985135"
ms.PowerAppsDecimalTransform: true
---
# <a name="dateadd-datediff-and-timezoneoffset-functions-in-powerapps"></a>DateAdd-, DateDiff- ja TimeZoneOffset-funktiot PowerAppsissa
Lisää tai etsii päivämäärä/aika-arvon eron ja muuntaa paikallisen ajan ja UTC-ajan välillä.

## <a name="description"></a>Kuvaus
**DateAdd**-funktio lisää yksiköitä päivämäärä/aika-arvoon. Tuloksena on uusi päivämäärä/aika-arvo. Voit myös vähentää yksiköitä päivämäärä/aika-arvosta määrittämällä negatiivisen arvon.

**DateDiff**-funktio palauttaa kahden päivämäärä/aika-arvon välisen eron. Tuloksena on yksiköiden määrä.

Molemmille funktioille yksiköt voivat olla **millisekunteja**, **sekunteja**, **minuutteja**, **tunteja**, **päiviä**, **kuukausia**, **vuosineljänneksiä** tai **vuosia**.  Molemmat funktiot käyttävät oletusarvoisesti yksikkönä **päivää**.

**TimeZoneOffset**-funktio palauttaa käyttäjän paikallisen ajan ja UTC-ajan (Coordinated Universal Time) välisen aikaeron määrän minuutteina.   

Voit käyttää **DateAdd**-funktiota **TimeZoneOffset**-funktion kanssa tehdäksesi muunnoksen käyttäjän paikallisen ajan ja UTC-ajan (Coordinated Universal Time) välillä.  **TimeZoneOffset**-funktion lisääminen muuttaa paikallisen ajan UTC-ajaksi ja sen vähentäminen (negatiivisen arvon lisääminen) UTC-ajan paikalliseksi ajaksi.

Saat lisä tietoja myös [päivä määrä-, aika-ja DateTime-tieto tyypeistä](/data-types#date-time-and-datetime) sekä [päivä määrien ja kellon aikojen käsittelystä](../show-text-dates-times.md) .

## <a name="syntax"></a>Syntaksi
**DateAdd**( *DateTime*; *Addition* [; *Units* ] )

* *DateTime* – Pakollinen. Käytettävä päivämäärä/aika-arvo.
* *Addition* – Pakollinen. *Yksikköinä (units)* annettu luku, joka lisätään *DateTime*en.
* *Units* – Valinnainen. Lisättävän *yksikön* tyyppi: **Milli**sekuntia, **sekuntia**, **minuutteja**, **tunteja**, **päiviä**, **kuukausia**, **vuosi neljänneksiä**tai **vuosia**.  Jos tätä ei määritetä, käytetään yksikköä **päivät**.

**DateDiff**( *StartDateTime*; *EndDateTime* [; *Units* ] )

* *StartDateTime* – Pakollinen. Alkupäivämäärä/aika-arvo.
* *EndDateTime* – Pakollinen. Loppupäivämäärä/aika-arvo.
* *Units* – Valinnainen. Lisättävän *yksikön* tyyppi: **Milli**sekuntia, **sekuntia**, **minuutteja**, **tunteja**, **päiviä**, **kuukausia**, **vuosi neljänneksiä**tai **vuosia**.  Jos tätä ei määritetä, käytetään yksikköä **päivät**.

**TimeZoneOffset**( [ *DateTime* ] )

* *DateTime* – Valinnainen.  Päivämäärä/aika-arvo, jolle siirtymä palautetaan.  Oletusarvoisesti käytetään nykyistä päivämäärä/aika-arvoa.

## <a name="examples"></a>Esimerkkejä
Kaikissa näissä esimerkeissä oletetaan, että nykyinen päivämäärä ja aika on **15. heinäkuuta 2013, kello 13:02**.

### <a name="simple-dateadd"></a>Yksinkertainen DateAdd

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Text( DateAdd( Now(); 3 );<br>"dd-mm-yyyy hh:mm" )** |Lisää kolme päivää (oletusarvoyksiköt) nykyiseen päivämäärään ja aikaan. |"18-07-2013 13:02" |
| **Text( DateAdd( Now(); 4; Hours );<br>"dd-mm-yyyy hh:mm" )** |Lisää nykyiseen päivämäärään ja aikaan neljä tuntia. |"15-07-2013 17:02" |
| **Text( DateAdd( Today(); 1; Months );<br>"dd-mm-yyyy hh:mm" )** |Lisää nykyiseen päivämäärän yhden kuukauden ilman aikaa, koska **Tänään** ei palauta aikaosaa. |"15-08-2013 00:00" |
| **Text( DateAdd( Now(); &#8209;;30; Minutes );<br>"dd-mm-yyyy hh:mm" )** |Vähentää nykyisestä päivämäärästä ja ajasta 30 minuuttia. |"15-07-2013 12:32" |

### <a name="simple-datediff"></a>Yksinkertainen DateDiff

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **DateDiff( Now(); DateValue("1/1/2014") )** |Palauttaa kahden arvon eron oletusyksikkönä **Päivät** |170 |
| **DateDiff( Now(); DateValue("1/1/2014"); Months )** |Palauttaa kahden arvon eron yksikkönä **kuukausia** |6 |
| **DateDiff( Now(); Today(); Minutes )** |Palauttaa eron nykyisen päivämäärä/aika-arvon ja nykyisen päivämäärän (ei aikaa) välillä minuutteina.  Koska **Now** on myöhäisempi kuin **Today**, tulos on negatiivinen. |-782 |

### <a name="converting-to-utc"></a>Muuntaminen UTC-aikaan
Voit muuntaa UTC-aikaan (Coordinated Universal Time) lisäämällä **TimeZoneOffset**-funktion tiettyyn aikaan.  

Kuvitellaan esimerkiksi, että nykyinen päivämäärä ja aika on **15. heinäkuuta 2013, kello 13:02** Tyynenmeren kesäaikaa (PDT, UTC-7).  Voit selvittää nykyisen ajan UTC-muodossa käyttämällä seuraavaa kaavaa:

* **DateAdd( Now(); TimeZoneOffset(); Minutes )**

**TimeZoneOffset**in oletusarvo on nykyinen aika, jolloin sinun ei tarvitse välittää sitä argumenttina.

Jotta näet tuloksen, käytä **Text**-funktiota muodossa *dd-mm-yyyy hh:mm*, jolloin tuloksena palautetaan **15-07-2013 20:02**.

### <a name="converting-from-utc"></a>Muuntaminen UTC-ajasta
Muunna UTC-ajasta vähentämällä **TimeZoneOffset** mistä tahansa ajasta (lisäämällä negatiivisen arvon).

Kuvitellaan esimerkiksi, että UTC-päivämäärä ja -aika **15. heinäkuuta 2013, 20:02:00** on tallennettu muuttujaan nimeltä **Aloitusaika**. Säädä aika käyttäjän aikavyöhykkeelle käyttämällä kaavaa:

* **DateAdd (StartTime, &minus;Medizoneoffset (aloitus aika), minuutit)**

Huomaa negatiivinen etumerkki ennen **TimeZoneOffset**-funktiota, mikä saa aikaan aikaeron vähentämisen lisäämisen sijaan.

Jotta näet tuloksen, käytä **Text**-funktiota muodossa *dd-mm-yyyy hh:mm*, jolloin tuloksena palautetaan **15-07-2013 13:02**, jos olet Tyynenmeren kesäajan aikavyöhykkeellä.


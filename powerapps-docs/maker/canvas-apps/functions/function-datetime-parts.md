---
title: Day-, Month-, Year-, Hour-, Minute-, Second- ja Weekday-funktiot | Microsoft Docs
description: PowerAppsin funktioiden Day, Month, Year, Hour, Minute, Second ja Weekday viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ab824432833614ba5b2002375a79e7899a8d7277
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551257"
---
# <a name="day-month-year-hour-minute-second-and-weekday-functions-in-powerapps"></a>Funktiot Day, Month, Year, Hour, Minute, Second ja Weekday PowerAppsissa
Palauttaa päivämäärä/aika-arvon yksittäisiä osia.

## <a name="description"></a>Kuvaus
**Day**-funktio palauttaa päivämäärä/aika-arvon päiväosan, jonka arvo on välillä 1–31.

**Month**-funktio palauttaa päivämäärä/aika-arvon kuukausiosan, jonka arvo on välillä 1–12.

**Year**-funktio palauttaa päivämäärä/aika-arvon vuosiosan, jonka arvo on vähintään 1900.

**Hour**-funktio palauttaa päivämäärä/aika-arvon tuntiosan, jonka arvo on välillä 0 (00.00) ja 23 (23.00).

**Minute**-funktio palauttaa päivämäärä/aika-arvon minuuttiosan, jonka arvo on välillä 0–59.

**Second**-funktio palauttaa päivämäärä/aika-arvon minuuttiosan, jonka arvo on välillä 0–59.

**Weekday**-funktio palauttaa päivämäärä/aika-arvon viikonpäiväosan.  Oletusmuotoisesti sen arvo on välillä 1 (sunnuntai) ja 7 (lauantai).  Voit määrittää viikon alkamaan eri viikonpäivänä Microsoft Excelin Weekday-funktion koodilla tai StartOfWeek-luettelointiarvolla:

| Excel-koodi | StartOfWeek-luettelointi | Kuvaus |
| --- | --- | --- |
| **1**, **17** |**StartOfWeek.Sunday** |Luvut 1 (sunnuntai) – 7 (lauantai).  Oletus. |
| **2**, **11** |**StartOfWeek.Monday** |Luvut 1 (maanantai) – 7 (sunnuntai). |
| **3** |**StartOfWeek.MondayZero** |Luvut 0 (maanantai) – 6 (sunnuntai). |
| **12** |**StartOfWeek.Tuesday** |Luvut 1 (tiistai) – 7 (maanantai). |
| **13** |**StartOfWeek.Wednesday** |Luvut 1 (keskiviikko) – 7 (tiistai). |
| **14** |**StartOfWeek.Thursday** |Luvut 1 (torstai) – 7 (keskiviikko). |
| **15** |**StartOfWeek.Friday** |Luvut 1 (perjantai) – 7 (torstai). |
| **16** |**StartOfWeek.Saturday** |Luvut 1 (lauantai) – 7 (perjantai). |

Kaikki funktiot palauttavat luvun.

Lisätietoja on kohdassa [Päivämäärien ja kellonaikojen käsitteleminen](../show-text-dates-times.md).

## <a name="syntax"></a>Syntaksi
**Day**( *DateTime* )<br>**Month**( *DateTime* )<br>**Year**( *DateTime* )<br>**Hour**( *DateTime* )<br>**Minute**( *DateTime* )<br>**Second**( *DateTime* )

* *DateTime* – Pakollinen.  Käytettävä päivämäärä/aika-arvo.  

**Weekday**( *DateTime* [, *WeekdayFirst* ] )<br>

* *DateTime* – Pakollinen.  Käytettävä päivämäärä/aika-arvo. 
* *WeekdayFirst* – Valinnainen.  Excel-koodi, joka määrittää mikä on viikon ensimmäinen viikonpäivä.  Jos ei määritetä, käytetään arvoa 1 (sunnuntai ensimmäisenä).

## <a name="examples"></a>Esimerkkejä
Seuraavassa esimerkissä nykyinen aika on **15:59:37**  **torstai, 9.4.2015**.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Year(&nbsp;Now()&nbsp;)** |Palauttaa nykyisen kellonajan ja päivämäärän vuosiosan. |2015 |
| **Kuukausi (&nbsp;Now()&nbsp;)** |Palauttaa nykyisen kellonajan ja päivämäärän kuukausiosan. |4 |
| **Day(&nbsp;Now()&nbsp;)** |Palauttaa nykyisen kellonajan ja päivämäärän päiväosan. |9 |
| **Hour(&nbsp;Now()&nbsp;)** |Palauttaa nykyisen kellonajan ja päivämäärän tuntiosan. |15 |
| **Minute(&nbsp;Now()&nbsp;)** |Palauttaa nykyisen kellonajan ja päivämäärän minuuttiosan. |59 |
| **Second(&nbsp;Now()&nbsp;)** |Palauttaa nykyisen kellonajan ja päivämäärän minuuttiosan. |37 |
| **Weekday(&nbsp;Now()&nbsp;)** |Palauttaa nykyisen kellonajan ja päivämäärän viikonpäiväosan. Oletuksena on, että sunnuntai on viikon ensimmäinen viikonpäivä. |5 |
| **Weekday(&nbsp;Now(),&nbsp;14&nbsp;)** |Palauttaa nykyisen kellonajan ja päivämäärän viikonpäiväosan ja määrittää Excel-koodilla, että torstai on viikon ensimmäinen viikonpäivä. |1 |
| **Weekday(&nbsp;Now(),&nbsp;StartOfWeek.Wednesday&nbsp;)** |Palauttaa nykyisen kellonajan ja päivämäärän viikonpäiväosan ja määrittää **StartOfWeek**-luettelointiarvolla, että keskiviikko on viikon ensimmäinen viikonpäivä. |2 |


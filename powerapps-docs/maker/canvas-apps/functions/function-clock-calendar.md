---
title: Calendar- ja Clock-funktiot | Microsoft Docs
description: PowerAppsin Calendar ja Clock-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.openlocfilehash: 0d725f00dc3617449eca9e16aedcf07c1414411f
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="calendar-and-clock-functions-in-powerapps"></a>PowerAppsin Calendar- ja Clock-funktiot
Noutavat nykyistä aluetta koskevat kello- ja kalenteritiedot.

## <a name="description"></a>Kuvaus
**Calendar**- ja **Clock**-funktiot ovat funktioita, jotka noutavat nykyistä aluetta koskevia tietoja.

Voit käyttää näitä funktioita näyttämään päivämääriä ja kellonaikoja nykyisen käyttäjän kielellä.  **Calendar**- ja **Clock**-funktioiden palauttamia yhden sarakkeen taulukoita voidaan käyttää suoraan Avattava luettelo- ja Luetteloruutu-ohjausobjektien **[Items](../controls/properties-core.md)**-ominaisuutena.

| Funktio | Kuvaus |
| --- | --- |
| **Calendar.MonthsLong()** |Palauttaa yhden sarakkeen taulukon, joka sisältää kuukausien täydet nimet, alkaen kuusta "Tammikuu". |
| **Calendar.MonthsShort()** |Palauttaa yhden sarakkeen taulukon, joka sisältää kuukausien lyhennetyt nimet, alkaen kuusta "Tammi". |
| **Calendar.WeekdaysLong()** |Palauttaa yksittäisen sarakkeen taulukon, joka sisältää viikonpäivien täydet nimet, alkaen päivästä "Maanantai". |
| **Calendar.WeekdaysShort()** |Palauttaa yksittäisen sarakkeen taulukon, joka sisältää viikonpäivien lyhennetyt nimet, alkaen päivästä "Ma". |
| **Clock.AmPm()** |Yhden sarakkeen taulukko, joka sisältää isoilla kirjaimilla merkityt "AM"- ja "PM"-määreet.  Jos kielessä käytetään 24 tunnin kelloa, taulukko on tyhjä. |
| **Clock.AmPmShort()** |Yhden sarakkeen taulukko, joka sisältää lyhyet isoilla kirjaimilla merkityt "A"- ja "P"-määreet.  Jos kielessä käytetään 24 tunnin kelloa, taulukko on tyhjä. |
| **Clock.IsClock24()** |Totuusarvo, joka merkitsee, käytetäänkö tällä alueella 24 tunnin kelloa. |

Käytä **[Text](function-text.md)**-funktiota päivämäärä- ja kellonaika-arvojen muotoilemiseksi samoilla tiedoilla.  **[Language](function-language.md)**-funktio palauttaa nykyisen kieli- ja aluetunnisteen.

## <a name="syntax"></a>Syntaksi
**Calendar.MonthsLong**()

**Calendar.MonthsShort**()

**Calendar.WeekdaysLong**()

**Calendar.WeekdaysShort**()

**Clock.AmPm**()

**Clock.AmPmShort**()

**Clock.IsClock24**()

## <a name="examples"></a>Esimerkkejä
1. Lisää Avattava valikko -ohjausobjekti.
2. Aseta **[Items](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   
   * **Calendar.MonthsLong()**
3. Sovelluksesi käyttäjät voivat nyt valita kuukauden omalla kielellään.  **MonthsLong** voidaan korvata millä tahansa yhden sarakkeen taulukolla, jotka **Calendar**-funktio palauttaa, viikonpäivä- ja kellonaikavalitsimien luomiseksi.

Suomessa, kun **[Language](function-language.md)**-funktio palauttaa "en-US", **Calendar**-funktiot palauttavat seuraavat:

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Calendar.MonthsLong()** |Paluuarvo sisältää kuukausien täydet nimet, alkaen kuukaudesta "January". |[ "January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December" ] |
| **Calendar.MonthsShort()** |Paluuarvo sisältää kuukausien lyhennetyt nimet, alkaen kuukaudesta "Jan". |[ "Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec" ] |
| **Calendar.WeekdaysLong()** |Paluuarvo sisältää viikonpäivien täydet nimet, alkaen päivästä "Sunday". |[ "Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday" ] |
| **Calendar.WeekdaysShort()** |Paluuarvo sisältää viikonpäivien lyhennetyt nimet, alkaen päivästä "Sun". |[ "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" ] |
| **Clock.AmPm()** |Tämä kieli käyttää 12 tunnin kelloa.  Paluuarvo sisältää täydet AM- ja PM-määreet isoilla kirjaimilla. |[ "AM", "PM" ] |
| **Clock.AmPmShort()** |Tämä kieli käyttää 12 tunnin kelloa.  Paluuarvo sisältää lyhyet AM- ja PM-määreet isoilla kirjaimilla. |[ "A", "P" ] |
| **Clock.IsClock24()** |Tämä kieli käyttää 24 tunnin kelloa. |**epätosi** |


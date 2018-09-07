---
title: Calendar- ja Clock-funktiot | Microsoft Docs
description: PowerAppsin Calendar- ja Clock-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.openlocfilehash: 6625df3f822462c86de1f720b7a310f5e516a6ca
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849867"
---
# <a name="calendar-and-clock-functions-in-powerapps"></a>PowerAppsin Calendar- ja Clock-funktiot PowerAppsissa
Noutavat nykyistä aluetta koskevat kello- ja kalenteritiedot.

## <a name="description"></a>Kuvaus
**Calendar**- ja **Clock**-funktiot ovat funktioita, jotka noutavat nykyistä aluetta koskevia tietoja.

Voit käyttää näitä funktioita näyttämään päivämääriä ja kellonaikoja nykyisen käyttäjän kielellä.  **Calendar**- ja **Clock**-funktioiden palauttamia yhden sarakkeen taulukoita voidaan käyttää suoraan Avattava luettelo- ja Luetteloruutu-ohjausobjektien **[Items](../controls/properties-core.md)**-ominaisuuden kanssa.

| Funktio | Kuvaus |
| --- | --- |
| **Calendar.MonthsLong()** |Yhden sarakkeen taulukko, joka sisältää kuukausien täydet nimet, alkaen ”Tammikuu”. |
| **Calendar.MonthsShort()** |Yhden sarakkeen taulukko, joka sisältää kuukausien lyhennetyt nimet, alkaen ”Tammi” eli tammikuu. |
| **Calendar.WeekdaysLong()** |Yhden sarakkeen taulukko, joka sisältää viikonpäivien täydet nimet, alkaen ”Sunnuntai”. |
| **Calendar.WeekdaysShort()** |Yhden sarakkeen taulukko, joka sisältää viikonpäivien lyhennetyt nimet. Esimerkiksi sunnuntai on ”Su”. |
| **Clock.AmPm()** |Yhden sarakkeen taulukko, joka sisältää isoilla kirjaimilla merkityt ”AM”- ja ”PM”-määreet.  Jos kielessä käytetään 24 tunnin kelloa, taulukko on tyhjä. |
| **Clock.AmPmShort()** |Yhden sarakkeen taulukko, joka sisältää lyhyet isoilla kirjaimilla merkityt ”A”- ja ”P”-määreet.  Jos kielessä käytetään 24 tunnin kelloa, taulukko on tyhjä. |
| **Clock.IsClock24()** |Totuusarvo ilmaisee käytetäänkö tällä alueella 24 tunnin kelloa. |

Käytä **[Text](function-text.md)**-funktiota, kun haluat muotoilla päivämäärä- ja kellonaika-arvot näillä samoilla tiedoilla.  **[Language](function-language.md)**-funktio palauttaa nykyisen kieli- ja aluetunnisteen.

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
3. Sovelluksesi käyttäjät voivat nyt valita kuukauden omalla kielellään.  Voit luoda viikonpäivä- ja kellonaikavalitsimia korvaamalla **MonthsLong**-kohdan millä tahansa **Calendar**-funktion palauttamalla yhden sarakkeen taulukolla.

Kun **[Language](function-language.md)**-funktio palauttaa Yhdysvalloissa arvon ”en-US”, **Calendar**-funktiot palauttavat seuraavat:

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Calendar.MonthsLong()** |Paluuarvo sisältää kuukausien täydet nimet, alkaen ”January”. |[ ”January”, ”February”, ”March”, ”April”, ”May”, ”June”, ”July”, ”August”, ”September”, ”October”, ”November”, ”December” ] |
| **Calendar.MonthsShort()** |Paluuarvo sisältää kuukausien lyhennetyt nimet, alkaen ”Jan”. |[ ”Jan”, ”Feb”, ”Mar”, ”Apr”, ”May”, ”Jun”, ”Jul”, ”Aug”, ”Sep”, ”Oct”, ”Nov”, ”Dec” ] |
| **Calendar.WeekdaysLong()** |Paluuarvo sisältää viikonpäivien täydet nimet, alkaen ”Sunday”. |[ ”Sunday”, ”Monday”, ”Tuesday”, ”Wednesday”, ”Thursday”, ”Friday”, ”Saturday” ] |
| **Calendar.WeekdaysShort()** |Paluuarvo sisältää viikonpäivien lyhennetyt nimet, alkaen ”Sun”. |[ ”Sun”, ”Mon”, ”Tue”, ”Wed”, ”Thu”, ”Fri”, ”Sat” ] |
| **Clock.AmPm()** |Tämä kieli käyttää 12 tunnin kelloa.  Paluuarvo sisältää täydet AM- ja PM-määreet isoilla kirjaimilla. |[ ”AM”, ”PM” ] |
| **Clock.AmPmShort()** |Tämä kieli käyttää 12 tunnin kelloa.  Paluuarvo sisältää lyhyet AM- ja PM-määreet isoilla kirjaimilla. |[ ”AM”, ”PM” ] |
| **Clock.IsClock24()** |Tämä kieli käyttää 12 tunnin kelloa. |**epätosi** |


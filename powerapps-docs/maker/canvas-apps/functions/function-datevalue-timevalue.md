---
title: DateValue-, TimeValue- ja DateTimeValue-funktiot | Microsoft Docs
description: Viitetiedot DateValue-, TimeValue- ja DateTimeValue-funktioille PowerAppsissa, mukaan lukien syntaksi ja esimerkkejä
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
ms.openlocfilehash: c1f11be30f56859ede0950feebc27dd1be39d011
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42834723"
---
# <a name="datevalue-timevalue-and-datetimevalue-functions-in-powerapps"></a>DateValue-, TimeValue- ja DateTimeValue-funktiot PowerAppsissa
Muuntavat merkkijonon päivämäärän ja/tai ajan päivämäärä- ja aika-arvoksi.

## <a name="description"></a>Kuvaus
**DateValue**-funktio muuntaa päivämäärämerkkijonon (esimerkiksi ”10/01/2014”) päivämäärä- ja aika-arvoksi.

**TimeValue**-funktio muuntaa aikamerkkijonon (esimerkiksi ”12:15 PM”) päivämäärä- ja aika-arvoksi.

**DateTimeValue**-funktio muuntaa päivämäärä- ja aikamerkkijonon (esimerkiksi ”January 10, 2013 12:13 AM”) päivämäärä- ja aika-arvoksi.

**DateValue**-funktio jättää huomiotta kaikki aikatiedot päivämäärämerkkijonossa ja **TimeValue**-funktio jättää huomiotta aikamerkkijonon kaikki päivämäärätiedot.

Oletuksena käytetään nykyisen käyttäjän kieliasetusta. Voit kuitenkin korvata sen, jotta merkkijonot tulkitaan oikein. Esimerkiksi 10/1/1920 tulkitaan päivämääräksi 1. lokakuuta kielessä EN ja päivämääräksi 10. tammikuuta kielessä FR.

Päivämäärien täytyy olla jossakin seuraavista muodoista:

* KK/PP/VVVV
* PP/KK/VVVV
* PP Kuu VVVV
* Kuukausi PP, VVVV

Tarkastele funktioita **[Date](function-date-time.md)** ja **[Time](function-date-time.md)**, jos haluat muuntaa numeeriset komponentit päiviksi, kuukausiksi ja vuosiksi sekä tunneiksi, minuuteiksi ja sekunneiksi.

Lisätietoja on myös kohdassa [Päivämäärien ja kellonaikojen käsittely](../show-text-dates-times.md).

Jos haluat muuntaa numeroita, tutustu **[Value](function-value.md)**-funktioon.

## <a name="syntax"></a>Syntaksi
**DateValue**( *String* [, *Language* ])<br>**DateTimeValue**( *String* [, *Language* ])<br>**TimeValue**( *String* [, *Language* ])

* *String* – pakollinen.  Tekstimerkkijono, joka sisältää päivämäärän, kellonajan tai niiden yhdistelmän.
* *Language* – valinnainen.  Kielimerkkijono, vastaa **[Language](function-language.md)**-funktion kahta ensimmäistä merkkiä.  Jos kieltä ei syötetä, käytetään nykyisen käyttäjän asiakkaan kieltä.  

## <a name="examples"></a>Esimerkkejä
### <a name="datevalue"></a>DateValue
Jos syötit **10/11/2014** tekstinsyöttöohjausobjektiin, jonka nimi on **Aloituspäivä**, ja asetit sitten tälle funktiolle selitteen ominaisuuden **[Text](../controls/properties-core.md)**:

* **Text(DateValue(Aloituspäivä.Text), DateTimeFormat.LongDate)**
  
    Selitteenä näkyisi **Saturday, October 11, 2014**, jos tietokoneen kielialueen tunnukseksi on asetettu **EN**.
  
    > [!NOTE]
  > Voit käyttää useita muita vaihtoehtoja kuin **LongDateTime** käyttämällä **DateTimeFormat**-parametria. Saat luettelon näistä vaihtoehdoista, kun kirjoitat funktiokenttään kyseisen parametrin ja huutomerkin välittömästi sen perään.
* **Text(DateValue(Aloituspäivä.Text, "fr"), DateTimeFormat.LongDate)**
  
    Selitteessä näkyisi **Monday, November 10, 2014**.

Jos tekisit saman päivämäärälle **20. lokakuuta 2014**:

* **DateDiff(DateValue(Aloituspäivä.Text), Today())**
  
    Jos tietokoneesi kielialueeksi on asetettu **EN**, selitteessä näkyisi **9**. Se vastaa päivämäärien 11. ja 20. lokakuuta välissä olevien päivien lukumäärää. **[DateDiff](function-dateadd-datediff.md)**-funktio voi näyttää eron myös kuukausina, vuosineljänneksinä tai vuosina.

### <a name="datetimevalue"></a>DateTimeValue
Jos syötät **10/11/2014 1:50:24.765 PM** tekstinsyöttöohjausobjektiin, jonka nimi on **Alku**, ja määrität sitten selitteen **[Text](../controls/properties-core.md)**-ominaisuuden seuraavalla tavalla:

* **Text(DateTimeValue(Alku.Text), DateTimeFormat.LongDateTime)**
  
    Selitteenä näkyisi **Saturday, October 11, 2014 1:50:24 PM**, jos tietokoneen kielialueen tunnukseksi on asetettu EN.
  
    > [!NOTE]
  > Voit käyttää useita muita vaihtoehtoja kuin **LongDateTime** käyttämällä **DateTimeFormat**-parametria. Saat luettelon näistä vaihtoehdoista, kun kirjoitat funktiokenttään kyseisen parametrin ja huutomerkin välittömästi sen perään.
* **Text(DateTimeValue(Alku.Text, "fr"), DateTimeFormat.LongDateTime)**
  
    Selitteessä näkyisi **Monday, November 10, 2014 1:50:24 PM**.
* **Text(DateTimeValue(Alku.Text), "pppp, kkkk pp, vvvv hh:mm:ss.fff AM/PM")**
  
    Selitteenä näkyisi **Saturday, October 11, 2014 01:50:24:765 PM**, jos tietokoneen kielialueen tunnukseksi on asetettu **EN**.
  
    Vaihtoehtoisesti voit valita määrityksen **hh:mm:ss.f** tai **hh:mm:ss.ff**, jolloin aika pyöristetään lähimpään sekunnin kymmenes- tai sadasosaan.

### <a name="timevalue"></a>TimeValue
Määritä tekstinsyöttöohjausobjekti **Päättynyt** ja määritä selitteen **[Text](../controls/properties-core.md)**-ominaisuus seuraavalla tavalla:

**If(TimeValue(Päättynyt.Text)<TimeValue("5:00:00.000 PM"), "Ehdit!", "Myöhästyit!")**

* Jos kirjoitat **4:59:59.999 PM** ohjausobjektiin **Päättynyt**, selitteessä näkyy ”Ehdit!”
* Jos kirjoitat **5:00:00.000 PM** ohjausobjektiin **Päättynyt**, selitteessä näkyy ”Myöhästyit!”


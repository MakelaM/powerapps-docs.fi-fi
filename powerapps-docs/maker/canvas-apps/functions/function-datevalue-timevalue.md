---
title: DateValue-, TimeValue- ja DateTimeValue-funktiot | Microsoft Docs
description: Viitetiedot DateValue-, TimeValue- ja DateTimeValue-funktioille PowerAppsissa, mukaan lukien syntaksi ja esimerkkejä
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 9fd392666fd79ec1342e736fe772416d435c0b77
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="datevalue-timevalue-and-datetimevalue-functions-in-powerapps"></a>DateValue-, TimeValue- ja DateTimeValue-funktiot PowerAppsissa
Muuntaa merkkijonon päivämäärän ja/tai ajan päivämäärä- ja aika-arvoksi.

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
**DateValue**( *Merkkijono* [, *Kieli* ])<br>**DateTimeValue**( *Merkkijono* [, *Kieli* ])<br>**TimeValue**( *Merkkijono* [, *Kieli* ])

* *Merkkijono* – pakollinen.  Tekstimerkkijono, joka sisältää päivämäärän, kellonajan tai niiden yhdistelmän.
* *Kieli* – valinnainen.  Kielimerkkijono, vastaa **[Language](function-language.md)**-funktion kahta ensimmäistä merkkiä.  Jos kieltä ei syötetä, käytetään nykyisen käyttäjän asiakkaan kieltä.  

## <a name="examples"></a>Esimerkkejä
### <a name="datevalue"></a>DateValue
Jos syötit **10/11/2014** tekstinsyöttöohjausobjektiin, jonka nimi on **Aloituspäivä**, ja asetit sitten tälle funktiolle selitteen ominaisuuden **[Text](../controls/properties-core.md)**:

* **Text(DateValue(Aloituspäivä.Text), DateTimeFormat.LongDate)**
  
    Selitteenä näkyisi **Saturday, October 11, 2014**, jos tietokoneen kielialueen tunnukseksi on asetettu **EN**.
  
    > [!NOTE]
> Voit käyttää useita muita vaihtoehtoja kuin **LongDateTime** käyttämällä **DateTimeFormat**-parametria. Saat luettelon näistä vaihtoehdoista, kun kirjoitat funktiokenttään kyseisen parametrin, ja huutomerkin välittömästi sen perään.
* **Text(DateValue(Aloituspäivä.Text, "fr"), DateTimeFormat.LongDate)**
  
    Selitteessä näkyisi **Monday, November 10, 2014**.

Jos tekisit saman **20. lokakuuta 2014**:

* **DateDiff(DateValue(Aloituspäivä.Text), Today())**
  
    Jos tietokoneesi kielialueeksi on asetettu **EN**, selitteessä näkyisi **9**. Se vastaa päivämäärien 11. ja 20. lokakuuta välissä olevien päivien lukumäärää. **[DateDiff](function-dateadd-datediff.md)**-funktio voi näyttää eron myös kuukausina, vuosineljänneksinä tai vuosina.

### <a name="datetimevalue"></a>DateTimeValue
Jos syötät **10/11/2014 1:50:24.765 PM** tekstinsyöttöohjausobjektiin, jonka nimi on **Alku**, ja määrität sitten selitteen **[Text](../controls/properties-core.md)**-ominaisuuden seuraavalla tavalla:

* **Text(DateTimeValue(Alku.Text), DateTimeFormat.LongDateTime)**
  
    Selitteenä näkyisi **Saturday, October 11, 2014 1:50:24 PM**, jos tietokoneen kielialueen tunnukseksi on asetettu EN.
  
    > [!NOTE]
> **DateTimeFormat**-parametrin avulla voit käyttää **LongDateTime**-muodon lisäksi on monia muita vaihtoehtoja. Saat luettelon näistä vaihtoehdoista, kun kirjoitat funktiokenttään kyseisen parametrin, ja huutomerkin välittömästi sen perään.
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


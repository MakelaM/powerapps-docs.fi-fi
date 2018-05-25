---
title: 'Päivämäärävalitsin-ohjausobjekti: viitetiedot | Microsoft Docs'
description: Päivämäärävalitsin-ohjausobjektin ominaisuudet ja esimerkkejä
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: f2605680c7b6e8f7102fd3459230344863a93f55
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="date-picker-control-in-powerapps"></a>Päivämäärävalitsin-ohjausobjekti PowerAppsissa
Ohjausobjekti, jota käyttäjä voi napsauttaa tai napauttaa päivämäärän määrittämiseksi.

## <a name="description"></a>Kuvaus
Jos lisäät **Päivämäärävalitsin**-ohjausobjektin **[Tekstisyöte](control-text-input.md)**-ohjausobjektin sijaan, autat varmistamaan, että käyttäjä määrittää päivämäärän oikeassa muodossa.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**DefaultDate** – Päivämäärän ohjausobjektin alkuarvo, ellei käyttäjä muuta sitä.

**SelectedDate** – Tällä hetkellä päivämäärä-ohjausobjektissa valittu päivämäärä.

**Muoto** – Tekstimuoto, jossa ohjausobjekti näyttää päivämäärän ja käyttäjä määrittää päivämäärän. Voit määrittää ominaisuudeksi **ShortDate** (oletus) tai **LongDate**, jonka mukaan päivämäärät muodostetaan tämän ohjausobjektin **Kieli**-ominaisuudessa. Voit myös määrittää ominaisuudeksi lausekkeen, kuten **vvvv/kk/pp**, jos haluat käyttää samaa muotoa kielestä riippumatta. Esimerkki:

* Ohjausobjekti näyttää **12/31/2017**, jos käyttäjä napsauttaa tai napauttaa vuoden 2017 viimeistä päivää, **Muoto**-ominaisuudeksi määritetään **ShortDate** ja **Kieli**-ominaisuudeksi **en-us**.
* Ohjausobjekti näyttää **dimanche 31 decembre 2017**, jos käyttäjä napsauttaa tai napauttaa vuoden 2017 viimeistä päivää, **Muoto**-ominaisuudeksi määritetään **LongDate** ja **Kieli**-ominaisuudeksi **fr-fr**.

**Kieli** – Määrittää päivämäärän, jota käytetään päivämäärien muotoiluun, mukaan lukien kuukausien nimet. Jos tätä ominaisuutta ei ole määritetty, käyttäjän laitteen asetus määrittää kielen.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviivat**, **pisteet** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun sillä on näppäimistökohdistus.

**[Väri](properties-color-border.md)** – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)**  – Salliiko ohjausobjekti käyttäjän syötettä (Muokkaa), vain tietojen tarkastelun (Näytä) vai onko se poissa käytöstä (Poistettu käytöstä).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**EndYear** – Viimeisin vuosi, johon käyttäjä voi määrittää päivämäärävalitsin-ohjausobjektin arvon.

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Fontti](properties-text.md)**  – Tekstissä käytetyn fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin leveys: **lihavoitu**, **puolilihavoitu**, **normaali** tai **ohuempi**.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[Kursivoitu](properties-text.md)** – Onko ohjausobjektin teksti kursivoitu.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[Koko](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**StartYear** – Aikaisin vuosi, johon käyttäjä voi määrittää päivämäärävalitsin-ohjausobjektin arvon.

**[TabIndex](properties-accessibility.md)** – Mukauttaa ohjausobjektien sarkainjärjestystä käytön aikana, kun arvona on nollasta poikkeava arvo.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
**[Year](../functions/function-datetime-parts.md)**( *DateTimeValue* )

## <a name="example"></a>Esimerkki
1. Lisää **Päivämäärävalitsin**-ohjausobjekti ja anna sille nimeksi **Määräaika**.
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **[Selite](control-text-box.md)**-ohjausobjekti ja määritä sen **[Teksti](properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateDiff(Today(), Deadline.SelectedDate) & " days to go!"**
   
    Haluatko lisätietoja **[DateDiff](../functions/function-dateadd-datediff.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
3. Paina F5-näppäintä, valitse päivämäärä kohdassa **Määräaika** ja napsauta tai napauta **OK**.
   
    **[Selite](control-text-box.md)**-ohjausobjekti näyttää päivien lukumäärän tämän päivän ja valitsemasi päivämäärän välillä.
4. Palaa oletustyötilaan painamalla Esc-näppäintä.


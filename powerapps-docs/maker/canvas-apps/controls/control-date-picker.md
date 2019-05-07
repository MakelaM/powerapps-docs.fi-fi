---
title: 'Päivämäärävalitsin-ohjausobjekti: viitetiedot | Microsoft Docs'
description: Päivämäärävalitsin-ohjausobjektin ominaisuudet ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 90f18c4b490564bc098046831ea932db13fce05d
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "63321708"
ms.PowerAppsDecimalTransform: true
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
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Color](properties-color-border.md)** – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)**  – Salliiko ohjausobjekti käyttäjän syötettä (Muokkaa), vain tietojen tarkastelun (Näytä) vai onko se poissa käytöstä (Poistettu käytöstä).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**EndYear** – Viimeisin vuosi, johon käyttäjä voi määrittää päivämäärävalitsin-ohjausobjektin arvon.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)**  – ohjausobjektin tekstin paino: **Lihavoitu**, **Semibold**, **Normaali**, tai **ohuempi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**IconFill** – Päivämäärävalitsimen kuvakkeen edustaväri.

**IconBackground** – Päivämäärävalitsimen kuvakkeen taustaväri.

**[Italic](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[Koko](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**StartYear** – Aikaisin vuosi, johon käyttäjä voi määrittää päivämäärävalitsin-ohjausobjektin arvon.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
**[Year](../functions/function-datetime-parts.md)**( *DateTimeValue* )

## <a name="example"></a>Esimerkki
1. Lisää **Päivämäärävalitsin**-ohjausobjekti ja anna sille nimeksi **Määräaika**.

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **[Selite](control-text-box.md)**-ohjausobjekti ja määritä sen **[Teksti](properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateDiff(Today(); Deadline.SelectedDate) & " days to go!"**

    Haluatko lisätietoja **[DateDiff](../functions/function-dateadd-datediff.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
3. Paina F5-näppäintä, valitse päivämäärä kohdassa **Määräaika** ja napsauta tai napauta **OK**.

    **[Selite](control-text-box.md)**-ohjausobjekti näyttää päivien lukumäärän tämän päivän ja valitsemasi päivämäärän välillä.
4. Palaa oletustyötilaan painamalla ESC-näppäintä.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
* [Tavalliset värikontrastivaatimukset](../accessible-apps-color.md) pätevät.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.

> [!TIP]
> Kun kalenterin on avoinna, paina **sivun ylös** ja **sivulla alaspäin** siirtyä kuukauden ja **VAIHTO + Page up** ja **VAIHTO + Page down** avulla Siirry vuoden.

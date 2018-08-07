---
title: 'Valintaruutu-ohjausobjekti: viite | Microsoft Docs'
description: Valintaruutu-ohjausobjektia koskevaa tietoa, mukaan lukien ominaisuudet ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: anneta
ms.openlocfilehash: 5f36c6e07f1f1c507f5734e51c23ba6af83eca4b
ms.sourcegitcommit: 0f6d7bb9e524202c065b9a7ef92a7f54bdc4bc7c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/07/2018
ms.locfileid: "39017199"
---
# <a name="check-box-control-in-powerapps"></a>Valintaruutu-ohjausobjekti PowerAppsissa
Ohjausobjekti, jonka käyttäjä voi valita tai tyhjentää ja asettaa siten sen arvoksi **tosi** tai **epätosi**.

## <a name="description"></a>Kuvaus
Käyttäjä voi määrittää totuusarvon käyttämällä tätä tuttua ohjausobjektia, jota on käytetty graafisissa käyttöliittymissä jo kymmeniä vuosia.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Default](properties-core.md)** – Ohjausobjektin alkuarvo ennen kuin käyttäjä muuttaa sitä.

**[Teksti](properties-core.md)**  – Teksti, joka näkyy ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

**[Arvo](properties-core.md)** – Ohjausobjektiin syötetty arvo.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**CheckboxBackgroundFill** – Valintaruutu-ohjausobjektissa valintamerkkiä ympäröivän ruudun taustaväri.

**CheckboxBorderColor** – Valintaruutu-ohjausobjektissa valintamerkkiä ympäröivän reunan väri.

**CheckboxSize** – Valintaruutu-ohjausobjektissa valintamerkkiä ympäröivän ruudun leveys ja korkeus.

**CheckmarkFill** – Valintaruutu-ohjausobjektissa olevan valintamerkin väri.

**[Väri](properties-color-border.md)** – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin paksuus: **lihavoitu**, **puolilihavoitu**, **normaali** tai **ohuempi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun hiiren kohdistin on kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)** – Onko ohjausobjektin teksti kursivoitu.

**OnCheck** – Miten sovellus reagoi, kun valintaruudun tai vaihtopainikkeen arvo muuttuu arvoon **tosi**.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnUnheck** – Miten sovellus reagoi, kun valintaruudun tai vaihtopainikkeen arvo muuttuu arvoon **epätosi**.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Reset](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**[Size](properties-text.md)** – Ohjausobjektissa näytettävän tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti alleviivattu.

**[VerticalAlign](properties-text.md)** – Ohjausobjektin tekstin sijainti suhteessa ohjausobjektin pystysuoraan keskikohtaan.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Aiheeseen liittyvät funktiot
[**If**( *Ehto*, *Tulos* )](../functions/function-if.md)

## <a name="example"></a>Esimerkki
1. Lisää **valintaruutu**-ohjausobjekti, anna sen nimeksi **chkReserve**, ja määritä sen **[Teksti](properties-core.md)**-ominaisuus näyttämään teksti **Varaa nyt**.
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **[päivämäärävalitsin](control-date-picker.md)**-ohjausobjekti ja määritä sen **[Näkyvä](properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**If(chkReserve.Value = true, true)**
   
    Haluatko lisätietoja **[If](../functions/function-if.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
3. Paina F5-näppäintä, napsauta tai napauta kohdetta **chkReserve** ja määritä sen **[Arvo](properties-core.md)**-ominaisuuden arvoksi **tosi**. Napsauta tai napauta sitten uudestaan **chkReserve**  ja määritä sen **[Arvo](properties-core.md)**-ominaisuuden arvoksi **epätosi**.
   
    **[Päivämäärävalitsin](control-date-picker.md)**-ohjausobjekti tulee näkyviin, kun **chkReserve**-asetuksen **[Value](properties-core.md)**-ominaisuuden arvo on **tosi**, mutta ei, jos se on **epätosi**.
4. Palaa oletustyötilaan painamalla ESC-näppäintä.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **CheckmarkFill** ja **CheckboxBackgroundFill**
* **CheckboxBackgroundFill** ja **[Täyttö](properties-color-border.md)**
* **CheckboxBackgroundFill** ja **[PressedFill](properties-color-border.md)**
* **CheckboxBackgroundFill** ja **[HoverFill](properties-color-border.md)**

Tämä tulee [värikontrastin vakiovaatimusten lisäksi](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[Teksti](properties-core.md)** on oltava käytössä.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.
 
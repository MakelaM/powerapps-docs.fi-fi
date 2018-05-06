---
title: 'Valintaruutu-ohjausobjekti: viitetiedot | Microsoft Docs'
description: Valintaruutu-ohjausobjektia koskevaa tietoa, mukaan lukien ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: 3784e90bbf6ed45d2b67b6211efaab279e37feca
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="check-box-control-in-powerapps"></a>Valintaruutu-ohjausobjekti PowerAppsissa
Ohjausobjekti, jonka käyttäjä voi valita tai tyhjentää ja asettaa siten sen arvoksi **true** tai **false**.

## <a name="description"></a>Kuvaus
Käyttäjä voi määrittää totuusarvon käyttämällä tätä tuttua ohjausobjektia, jota on käytetty graafisissa käyttöliittymissä jo vuosikymmenten ajan.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Default](properties-core.md)** – Ohjausobjektin alkuarvo, ennen kuin käyttäjä muuttaa sitä.

**[Text](properties-core.md)**  – Teksti, joka näkyy ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

**[Value](properties-core.md)** – Ohjausobjektiin syötetty arvo.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **Solid** (yhtenäinen), **Dashed** (katkoviiva), **Dotted** (pisteviiva) vai **None** (ei mitään).

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**CheckboxBackgroundFill** – Valintaruutu-ohjausobjektissa valintamerkkiä ympäröivän ruudun taustaväri.

**CheckboxBorderColor** – Valintaruutu-ohjausobjektissa valintamerkkiä ympäröivän reunan väri.

**CheckboxSize** – Valintaruutu-ohjausobjektissa valintamerkkiä ympäröivän ruudun leveys ja korkeus.

**CheckmarkFill** – Valintaruutu-ohjausobjektissa olevan valintamerkin väri.

**[Väri](properties-color-border.md)** – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Edit**), vain tarkastella tietoja (**View**) vai onko ominaisuus poistettu käytöstä (**Disabled**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-ominaisuuden asetuksena on **Disabled** (ei käytössä).

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-ominaisuuden asetuksena on **Disabled** (ei käytössä).

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-ominaisuuden asetuksena on **Disabled** (ei käytössä).

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Font](properties-text.md)**  – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin paino: **Bold** (lihavoitu), **Semibold** (puolilihavoitu), **Normal** (normaali) tai **Lighter** (kevyempi).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)** – Onko ohjausobjektin teksti kursivoitu.

**OnCheck** – Miten sovellus reagoi, kun valintaruudun tai vaihtopainikkeen arvo muuttuu arvoon **true**.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnUnheck** – Miten sovellus reagoi, kun valintaruudun tai vaihtopainikkeen arvo muuttuu arvoon **false**.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** –Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[Palautus](properties-core.md)**  – Palautetaanko ohjausobjektin oletusarvo.

**[Size](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)** – Onko ohjausobjektissa näkyvä teksti alleviivattua.

**[VerticalAlign](properties-text.md)** – Ohjausobjektin tekstin sijainti suhteessa ohjausobjektin pystysuoraan keskikohtaan.

**[Visible](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**If**( *Ehto*, *Tulos* )](../functions/function-if.md)

## <a name="example"></a>Esimerkki
1. Lisää **valintaruutu**-ohjausobjekti, anna sen nimeksi **chkReserve**, ja määritä sen **[Text](properties-core.md)**-ominaisuus näyttämään tekstin **Varaa nyt**.
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **[päivämäärävalitsin](control-date-picker.md)**-ohjausobjekti ja määritä sen **[Visible](properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**If(chkReserve.Value = true, true)**
   
    Haluatko lisätietoja **[If](../functions/function-if.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
3. Paina F5-näppäintä, napsauta tai napauta kohdetta **chkReserve** määrittääksesi sen **[Value](properties-core.md)**-ominaisuuden arvoksi **true** ja napsauta tai napauta sitten kohdetta **chkReserve**  uudelleen määrittääksesi sen **[Value](properties-core.md)**-ominaisuuden arvoksi **false**.
   
    **[Päivämäärävalitsin](control-date-picker.md)**-ohjausobjekti tulee näkyviin, kun **chkReserve**n **[Value](properties-core.md)**-ominaisuuden arvo on **true**, mutta ei, jos se on **false**.
4. Palaa oletustyötilaan painamalla ESC-näppäintä.


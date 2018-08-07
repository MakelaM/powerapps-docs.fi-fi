---
title: 'Valintanappi: viittaus | Microsoft Docs'
description: Valintanappeja koskevia tietoja, kuten ominaisuuksia ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/06/2018
ms.author: fikaradz
ms.openlocfilehash: b09f2ef174ecea79c0a4297bf700ba84b96bccbe
ms.sourcegitcommit: 0f6d7bb9e524202c065b9a7ef92a7f54bdc4bc7c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/07/2018
ms.locfileid: "39016049"
---
# <a name="radio-control-in-powerapps"></a>Valintanappi PowerAppsissa

Syötteen ohjausobjekti, joka näyttää useita vaihtoehtoja. Käyttäjät voivat valita niistä vain yhden kerrallaan.

## <a name="description"></a>Kuvaus

**Valintanappi**-ohjausobjekti on HTML-syötteen vakio-ohjausobjekti, jota kannattaa käyttää vain muutamassa toisensa poissulkevissa asetuksessa.

Ohjausobjektin asettelu voi olla vaaka- tai pystysuuntainen.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet

**[Oletus](properties-core.md)**  – Ohjausobjektin arvo, ennen kuin käyttäjä muuttaa sitä.

**[Kohteet](properties-core.md)** – Tietolähde, joka näkyy ohjausobjektissa, kuten valikoimassa, luettelossa tai kaaviossa.

**Asettelu** – Määrittää, onko asettelu vaaka- tai pystysuuntainen.

**[Arvo](properties-core.md)** – Ohjausobjektiin syötetty arvo.

## <a name="all-properties"></a>Kaikki ominaisuudet

**[Align](properties-text.md)** – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Väri](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

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

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**[LineHeight](properties-text.md)** – esimerkiksi tekstin tai luettelon rivien välinen etäisyys.

**[OnChange](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi käyttämällä liukusäädintä).

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**RadioBackgroundFill** – Valintanapin ympyröiden taustaväri.

**RadioBorderColor** – Valintanapin ympyrän väri kullekin valintanapin vaihtoehdolle.

**RadioSelectionFill** – Väri, joka ilmaantuu valittuna olevan valintanapin sisälle.

**RadioSize** – Valintanapin ympyröiden läpimitta.

**[Reset](properties-core.md)** – Palautetaanko ohjausobjektin oletusarvo.

**[Size](properties-text.md)** – Ohjausobjektissa näytettävän tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)** – Onko ohjausobjektissa näytettävä teksti alleviivattu.

**[Visible](properties-core.md)** – Onko ohjausobjekti näytössä vai piilotettuna.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liitetyt toiminnot

[**Distinct**( *Tietolähde*, *SarakkeenNimi* )](../functions/function-distinct.md)

## <a name="example"></a>Esimerkki

1. Lisää **Valintanappi**-ohjausobjekti, anna sille nimeksi **Hinnoittelu** ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi tämä kaava:

    **["Standard", "Premium"]**

    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?

2. Lisää **[Selite](control-text-box.md)**-ohjausobjekti, siirrä se **Valintanappi**-ohjausobjektin alapuolelle ja aseta **[Selite](control-text-box.md)**-ohjausobjektin **[Text](properties-core.md)**-ominaisuudeksi tämä kaava:

    **If ("Premium" Pricing.Selected.Value "200 euroa per päivä", "150 euroa päivässä")**

    Haluatko lisätietoja **[If](../functions/function-if.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?

3. Pidä Alt-näppäintä painettuna ja valitse jompikumpi **Valintanappi**-ohjausobjektin vaihtoehto.

    **[Selite](control-text-box.md)**-ohjausobjekti näyttää valintasi mukaisen tekstin.

4. (valinnainen) Pidä Alt-näppäintä painettuna, valitse toinen vaihtoehdoista ja tarkista, että näyttöön tulee asianmukainen teksti.

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet

### <a name="color-contrast"></a>Värikontrasti

Varmista [normaalien värikontrastivaatimusten](../accessible-apps-color.md) lisäksi riittävä värikontrasti seuraavien välillä:

* **RadioSelectionFill** ja **RadioBackgroundFill**
* **RadioBackgroundFill** ja **[Täyttö](properties-color-border.md)**

### <a name="screen-reader-support"></a>Näytönlukuohjelmien tuki

* Varmista, että jokaisella asetuksella on **[arvo](properties-core.md)**.
* Harkitse **[selitteen](control-text-box.md)** lisäämistä otsikoksi jokaisen **Valintanappi**-ohjausobjektin edelle.

### <a name="keyboard-support"></a>Näppäimistön tuki

* Määritä **[TabIndex](properties-accessibility.md)**-ominaisuudeksi nolla tai suurempi arvo, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Määritä  **[FocusedBorderColor](properties-color-border.md)**- ja **[FocusedBorderThickness](properties-color-border.md)**-ominaisuudet niin, että kohdistusilmaisimet näkyvät selvästi.
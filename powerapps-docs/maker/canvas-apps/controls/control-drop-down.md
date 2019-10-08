---
title: 'Avattava luettelo -ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja Avattava luettelo -ohjausobjektista, mukaan lukien ominaisuudet ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4a838100398196c63ef948f8f2e94d098c03a373
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993432"
ms.PowerAppsDecimalTransform: true
---
# <a name="drop-down-control-in-powerapps"></a>Avattava luettelo -ohjausobjekti PowerAppsissa
Luettelo, joka näyttää vain ensimmäisen kohdan, kunnes käyttäjä avaa luettelon.

## <a name="description"></a>Kuvaus
**Avattava luettelo** -ohjausobjekti säästää näyttötilaa erityisesti, kun luettelo sisältää paljon vaihtoehtoja. Ohjausobjekti käyttää vain yhden rivin, kunnes käyttäjä valitsee nuolenkärjen ja avaa näin lisää vaihtoehtoja.  Ohjausobjekti näyttää enintään 500 kohdetta.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Oletus](properties-core.md)**  – Ohjausobjektin alkuarvo, ellei käyttäjä määritä eri arvoa.

**[Kohteet](properties-core.md)**  – Tietolähde, joka sisältää ohjausobjektissa näkyvät kohteet. Jos lähteessä on useita sarakkeita, määritä ohjausobjektin **Arvo**-ominaisuudeksi näytettävien tietojen sarake.
  
**Arvo** – Ohjausobjektissa näytettävien tietojen sarake, jos esimerkiksi tietolähteessä on useita sarakkeita.

**Valitun** – valittua kohdetta edustava tieto tietue.

**Allowemptyselection** – määrittää, näkyykö ohjaus objektissa tyhjä valinta, jos kohdetta ei ole valittu. Sovelluksen käyttäjät voivat myös tyhjentää valintansa valitsemalla tyhjän kohteen.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**ChevronBackground** – Avattavan luettelon alaspäin osoittavan nuolen taustaväri.

**ChevronFill** – Avattavan luettelon alaspäin osoittavan nuolen väri.

**[Color](properties-color-border.md)** – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)** -asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)** -asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)** -asetuksena on **Poistettu käytöstä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[Fontweight](properties-text.md)** – ohjaus objektin tekstin paino: **Lihavoitu**, **puolilihavoitu**, **Normaali**tai **kevyempi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun hiiren kohdistin on kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)** – Onko ohjausobjektin teksti kursivoitu.

**[OnChange](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Reset](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**SelectedText (vanhentunut)** – merkki jono arvo, joka edustaa valittua kohdetta.

**[SelectionColor](properties-color-border.md)** – Luettelosta valitun kohteen tai kohteiden tekstin väri tai kynä-ohjausobjektin valintatyökalun väri.

**[SelectionFill](properties-color-border.md)** – Luettelon valitun kohteen tai kohteiden taustaväri tai kynä-ohjausobjektin valitun alueen väri.

**[Size](properties-text.md)** – Ohjausobjektissa näytettävän tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)** – Onko ohjausobjektissa näytettävä teksti alleviivattu.

**[Visible](properties-core.md)** – Onko ohjausobjekti näytössä vai piilotettuna.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="example"></a>Esimerkki

### <a name="simple-list"></a>Yksinkertainen luettelo

1. Lisää **Avattava luettelo** -ohjausobjekti ja aseta sen **[Kohteet](properties-core.md)** -ominaisuudeksi tämä lauseke:

    `["Seattle"; "Tokyo"; "London"; "Johannesburg"; "Rio de Janeiro"]`

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?

1. Näytä luettelon kohteet valitsemalla ohjausobjektin alanuoli samalla, kun painat Alt-näppäintä.

### <a name="list-from-a-data-source"></a>Luettelo tietolähteestä
Tämän toiminnon periaatteet koskevat mitä tahansa [tieto lähdettä, joka tarjoaa taulu koita](../connections-list.md#tables) , mutta näiden vaiheiden suorittamista varten sinun on avattava ympäristö, jolle on luotu Common Data Service tieto kanta ja lisätty malli tietoja.

1. [Avaa tyhjä sovellus](../data-platform-create-app-scratch.md#open-a-blank-app) ja [määritä **Tilit**-entiteetti](../data-platform-create-app-scratch.md#specify-an-entity).

1. Lisää **Avattava luettelo** -ohjausobjekti ja aseta sen **[Kohteet](properties-core.md)** -ominaisuudeksi tämä kaava:

    `Distinct(Accounts; address1_city)`

    Tämä kaava näyttää kaikki **Tilit**-entiteetin kaupungit. Jos sama kaupunki on useassa tietueessa, **[Distinct](../functions/function-distinct.md)** -funktio piilottaa kaksoiskappaleen avattavan valikon ohjausobjektissa.

1. (valinnainen) Vaihda **Avattava luettelo** -ohjausobjektin nimeksi **Kaupungit** ja lisää pystysuora **Valikoima**-ohjausobjekti. Aseta valikoiman **[Kohteet](properties-core.md)** -ominaisuudeksi tämä kaava:

    `Filter(Accounts; address1_city = Cities.Selected.Value)`

    Tämä **[suodatinfunktio](../functions/function-filter-lookup.md)** näyttää vain ne **Tilit**-entiteetin tietueet, joissa kaupunki vastaa **Kaupungit**-ohjausobjektissa valittua arvoa.

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **ChevronFill** ja **ChevronBackground**
* **ChevronHoverFill** ja **ChevronHoverBackground**
* **SelectionColor** ja **SelectionFill**
* **SelectionFill** ja **[Fill](properties-color-border.md)**

Tämä tulee [värikontrastin vakiovaatimusten lisäksi](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)** -kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.

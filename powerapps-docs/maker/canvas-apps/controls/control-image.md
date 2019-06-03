---
title: 'Kuvan ohjausobjekti: viitetiedot | Microsoft Docs'
description: Kuva-ohjausobjektin tiedot, mukaan lukien ominaisuudet ja esimerkit
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
ms.openlocfilehash: d5765c1e425a3196b5e560bb621f391d36f6580c
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61544610"
---
# <a name="image-control-in-powerapps"></a>Kuva-ohjausobjekti PowerAppsissa
Ohjausobjekti, joka näyttää kuvan esimerkiksi paikallisesta tiedostosta tai tietolähteestä.

## <a name="description"></a>Kuvaus
Jos lisäät sovellukseen vähintään yhden **kuva**-ohjausobjektin, voit näyttää yksittäisiä, tietojoukkoon kuulumattomia kuvia tai lisätä tietolähdearkiston kuvia.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Image](properties-visual.md)** – Kuvan, äänen tai mikrofonin ohjausobjektissa näkyvän kuvan nimi.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**ApplyEXIFOrientation** – Määrittää, käytetäänkö automaattisesti kuvan EXIF-tiedoissa olevaa suuntaa.

**AutoDisableOnSelect** – Poistaa ohjausobjektin automaattisesti käytöstä OnSelect-toiminnon suorittamisen ajaksi.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**CalculateOriginalDimensions** – Ottaa käyttöön ominaisuudet **OriginalHeight** (alkuperäinen korkeus) ja **OriginalWidth** (alkuperäinen leveys).

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella (**View**) vai onko ominaisuus kokonaan poissa käytöstä (**Disabled**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)** -asetuksena on **Ei käytössä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)** -asetuksena on **Disabled** (ei käytössä).

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**FlipHorizontal** – Määrittää, käännetäänkö kuva vaakasuunnassa ennen sen näyttämistä.

**FlipVertical** – Määrittää, käännetäänkö kuva pystysuunnassa ennen sen näyttämistä.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**[HoverFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä pitää hiiren osoitinta sen päällä.

**[ImagePosition](properties-visual.md)** – Kuvan tai ohjausobjektin asettelu (**Täytä**, **Sovita**, **Venytä**, **Vierekkäin** tai **Keskitä**), jos se ei ole saman kokoinen kuin näyttö.

**ImageRotation** – Määrittää kuvan kiertokulman ennen sen näyttämistä.  Arvot voivat olla ei mitään, myötäpäivään 90 astetta, vastapäivään 90 astetta ja myötäpäivään 180 astetta.

**[OnSelect](properties-core.md)** – Sovelluksen reagointitapa, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OriginalHeight** – Kuvan alkuperäinen korkeus, kun **CalculateOriginalDimensions**-ominaisuus on käytössä.

**OriginalWidth** – Kuvan alkuperäinen leveys, kun **CalculateOriginalDimensions**-ominaisuus on käytössä.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[RadiusBottomLeft](properties-size-location.md)** – Ohjausobjektin vasemman alakulman pyöristysaste.

**[RadiusBottomRight](properties-size-location.md)** – Ohjausobjektin oikean alakulman pyöristysaste.

**[RadiusTopLeft](properties-size-location.md)** – Ohjausobjektin vasemman yläkulman pyöristysaste.

**[RadiusTopRight](properties-size-location.md)** – Ohjausobjektin oikean yläkulman pyöristysaste.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**Transparency** – Läpinäkyvyys eli missä määrin kuvan takana olevat ohjausobjektit pysyvät näkyvissä.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liitetyt toiminnot
[**Remove**( *DataSource*, ThisItem )](../functions/function-remove-removeif.md)

## <a name="examples"></a>Esimerkkejä
### <a name="show-an-image-from-a-local-file"></a>Paikallisen tiedoston kuvan näyttäminen
1. Valitse **Tiedosto**-valikosta **Media** ja napauta tai napsauta sitten **Selaa**-painiketta.
2. Napauta tai napsauta kuvatiedostoa, jonka haluat lisätä. Valitse sitten **Avaa** ja palaa oletustyötilaan painamalla Esc-näppäintä.
3. Lisää **kuva**-ohjausobjekti ja määritä sen **Image**-ominaisuudeksi juuri lisäämäsi tiedoston nimi.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

    **Kuva**-ohjausobjekti näyttää valitsemasi kuvan.

### <a name="show-a-set-of-images-from-a-data-source"></a>Tietolähteen kuvajoukon näyttäminen
1. Lataa tämä [Excel-tiedosto](https://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx) ja tallenna se paikalliseen laitteeseesi.
2. Luo tai avaa sovellus PowerApps Studiossa ja valitse sitten oikeanpuoleisesta ruudusta **Lisää tietolähde**.

    Jos **Lisää tietolähde** ei näy oikeanpuoleisessa ruudussa, napsauta tai napauta vasemmassa siirtymispalkissa olevaa näyttöä.
3. Valitse **Lisää sovellukseen staattisia tietoja** (Add static data to your app). Napsauta tai napauta lataamaasi Excel-tiedostoa ja valitse sitten **Avaa**.
4. Valitse **Flooring Estimates** (lattia-arviot) -valintaruutu ja sitten **Yhdistä**.
5. Lisää kuvallinen **Valikoima**-ohjausobjekti ja määritä sen **[Items](properties-core.md)** -ominaisuudeksi **FlooringEstimates**.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

    **Valikoima**-ohjausobjekti näyttää lataamasi Excel-tiedoston linkkeihin pohjautuvia kuvia kokolattiamatoista sekä puu- ja laattalattioista.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
* [Tavalliset värikontrastivaatimukset](../accessible-apps-color.md) pätevät käytettäessä kuvaa painikkeena.
* Harkitse kuvan kontrastiongelmien tarkistamista, jos se ei ole pelkästään koristeena.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava olemassa, jos kuvaa käytetään painikkeena tai muussa kuin koristeellisessa tarkoituksessa.
* **[AccessibleLabel](properties-accessibility.md)** on oltava tyhjä tai tyhjä merkkijono **""** , jos kuva on pelkästään koristeena. Näin näytönlukuohjelmat voivat ohittaa kuvan.
* **[AccessibleLabel](properties-accessibility.md)** voi olla tyhjä tai tyhjä merkkijono **""** , jos kuvassa esitetään tarpeetonta tietoa.
  * Esimerkiksi **kuva** rataksista yhdessä **[AccessibleLabel](properties-accessibility.md)** -objektin kanssa, jonka arvo on **Asetukset**. Kuvaa ei käytetä painikkeena. Se on **[selitteen](control-text-box.md)** vieressä, jossa lukee myös **Asetukset**. Näytönlukuohjelmat lukevat kuvan tekstinä **Asetukset**, ja sitten myös selitteen tekstinä **Asetukset**. Tämä on tarpeetonta. Tässä tapauksessa **kuva** ei tarvitse **[AccessibleLabel](properties-accessibility.md)** -objektia.

    > [!IMPORTANT]
    > Näytönlukuohjelmat lukevat aina **kuva**t, joilla **[TabIndex](properties-accessibility.md)** on suurempi tai yhtä suuri kuin 0, riippumatta siitä, onko **[AccessibleLabel](properties-accessibility.md)** tyhjä vai ei. Tämä johtuu siitä, että ne hahmonnetaan painikkeina. Jos **[AccessibleLabel](properties-accessibility.md)** -objektia ei ole, näytönlukuohjelmat lukevat kuvan **painikkeena**.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)** -objektin arvo on oltava suurempi tai yhtä suuri kuin 0, jos kuvaa käytetään painikkeena. Näin näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistusilmaisimien on oltava selvästi näkyvissä, jos kuvaa käytetään painikkeena. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.

    > [!NOTE]
  > Jos **[TabIndex](properties-accessibility.md)** on suurempi tai yhtä suuri kuin 0, **kuva** hahmonnetaan painikkeena. Kuvan visuaalinen ulkoasu ei muutu, mutta näytönlukuohjelmat tunnistavat kuvan oikein painikkeeksi. Jos **[TabIndex](properties-accessibility.md)** on pienempi kuin 0, **kuva** tunnistetaan kuvana.

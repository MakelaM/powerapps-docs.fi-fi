---
title: 'Kuvan ohjausobjekti: viittaus | Microsoft Docs'
description: Kuvan ohjausobjektin tiedot, kuten ominaisuudet ja esimerkit
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
ms.openlocfilehash: 0ab25713976e9f89fa74b5f7664b13dca447841e
ms.sourcegitcommit: 87327f99636c68c62c755c4eb48861249a5a3add
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/09/2018
---
# <a name="image-control-in-powerapps"></a>Kuvan ohjausobjekti PowerAppsissa
Ohjausobjekti, joka näyttää kuvan esimerkiksi paikallisesta tiedostosta tai tietolähteestä.

## <a name="description"></a>Kuvaus
Jos lisäät sovellukseen vähintään yhden **kuvan** ohjausobjektin, voit näyttää yksittäisiä, tietojoukkoon kuulumattomia kuvia tai lisätä tietolähdearkiston kuvia.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Image](properties-visual.md)** – Kuvan, äänen tai mikrofonin ohjausobjektissa näkyvän kuvan nimi.

## <a name="additional-properties"></a>Lisäominaisuudet
**ApplyEXIFOrientation** – Määrittää, käytetäänkö automaattisesti kuvan EXIF-tiedoissa olevaa suuntaa.

**AutoDisableOnSelect** – Poistaa ohjausobjektin automaattisesti käytöstä OnSelect-toiminnon suorittamisen ajaksi.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Reunan tyyli määrittää, onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin näppäimistösyötteisen reunan paksuus.

**CalculateOriginalDimensions** – Ottaa käyttöön ominaisuudet **OriginalHeight** (alkuperäinen korkeus) ja **OriginalWidth** (alkuperäinen leveys).

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Muokkaa**) tai vain tarkastella (**Näytä**) vai onko ominaisuus kokonaan poissa käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-ominaisuus **ei ole käytössä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-ominaisuus **ei ole käytössä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**FlipHorizontal** – Määrittää, käännetäänkö kuva vaakasuunnassa ennen sen näyttämistä.

**FlipVertical** – Määrittää, käännetäänkö kuva pystysuunnassa ennen sen näyttämistä.

**[Height](properties-size-location.md)** – Ohjausobjektin korkeus eli sen ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun käyttäjä pitää hiiren osoitinta sen päällä.

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

**[RadiusBottomLeft](properties-size-location.md)** – Vasemman alakulman pyöristysaste.

**[RadiusBottomRight](properties-size-location.md)** – Oikean alakulman pyöristysaste.

**[RadiusTopLeft](properties-size-location.md)** – Vasemman yläkulman pyöristysaste.

**[RadiusTopRight](properties-size-location.md)** – Oikean yläkulman pyöristysaste.

**[Tooltip](properties-core.md)** – Työkaluvihjeen ohjeteksti, joka ilmestyy näkyviin hiiren osoittimen ollessa ohjausobjektin päällä.

**Transparency** – Läpinäkyvyys eli missä määrin kuvan takana olevat ohjausobjektit pysyvät näkyvissä.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Leveys eli ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (näytön, jos pääsäilöä ei ole).

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (näytön, jos pääsäilöä ei ole).

## <a name="related-functions"></a>Liitetyt toiminnot
[**Poista** (*DataSource*, ThisItem)](../functions/function-remove-removeif.md)

## <a name="examples"></a>Esimerkkejä
### <a name="show-an-image-from-a-local-file"></a>Paikallisen tiedoston kuvan näyttäminen
1. Valitse **Tiedostot**-valikosta **Media** ja napauta tai napsauta sitten **Selaa**-painiketta.
2. Napauta tai napsauta kuvatiedostoa, jonka haluat lisätä. Valitse sitten **Avaa** ja palaa oletustyötilaan painamalla Esc-näppäintä.
3. Lisää **kuvan** ohjausobjekti ja määritä sen **Image**-ominaisuudeksi juuri lisäämäsi tiedoston nimi.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

    **Kuvan** ohjausobjekti näyttää valitsemasi kuvan.

### <a name="show-a-set-of-images-from-a-data-source"></a>Tietolähteen kuvajoukon näyttäminen
1. Lataa tämä [Excel-tiedosto](https://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx) ja tallenna se omaan, paikalliseen laitteeseen.
2. Luo tai avaa sovellus PowerApps Studiossa ja valitse sitten oikeanpuoleisesta ruudusta **Lisää tietolähde**.

    Jos **Lisää tietolähde** ei näy oikeanpuoleisessa ruudussa, napsauta tai napauta vasemmassa siirtymispalkissa olevaa näyttöä.
3. Valitse **Lisää sovellukseen staattisia tietoja** (Add static data to your app). Napsauta tai napauta lataamaasi Excel-tiedostoa ja valitse sitten **Avaa**.
4. Valitse **Flooring Estimates** (lattia-arviot) -valintaruutu ja sitten **Yhdistä**.
5. Lisää kuvallinen **Valikoima**-ohjausobjekti ja määritä sen **[Items](properties-core.md)**-ominaisuudeksi **FlooringEstimates**.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

    **Valikoima**-ohjausobjekti näyttää lataamasi Excel-tiedoston linkkeihin pohjautuvia kuvia kokolattiamatoista sekä puu- ja laattalattioista.

---
title: 'Valintanappi: viittaus | Microsoft Docs'
description: Valintanappeja koskevia tietoja, kuten ominaisuuksia ja esimerkkejä
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
ms.openlocfilehash: 9cf051ba94e9d43b4c263d627c25affa66e6b843
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="radio-control-in-powerapps"></a>Valintanappi PowerAppsissa
Luettelo, josta voi valita vain yhden vaihtoehdon kerrallaan.

## <a name="description"></a>Kuvaus
**Valintanappi** on ohjausobjekti, jota on käytetty jo kymmeniä vuosia. Se sopii parhaiten luetteloihin, joissa on vain muutama toisensa poissulkeva vaihtoehto.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**[Default](properties-core.md)** – alkuperäinen asetus, joka on voimassa, ennen kuin käyttäjä muuttaa sitä.

**[Items](properties-core.md)** – Tietolähde, joka tulee näkyviin ohjausobjektissa, kuten galleriassa, luettelossa tai kaaviossa.

[!INCLUDE [long-items](../../../includes/long-items.md)]

**[Value](properties-core.md)**  – Ohjausobjektiin syötetty arvo.

## <a name="all-properties"></a>Kaikki ominaisuudet
**[Align](properties-text.md)** – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva**vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun sillä on näppäimistökohdistus.

**[Color](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus pois käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin paino: **lihavoitu**, **puolilihavoitu**, **normaali** tai **vaaleampi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**[LineHeight](properties-text.md)** – esimerkiksi tekstin tai luettelon rivien välinen etäisyys.

**[OnChange](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

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

**[Strikethrough](properties-text.md)** – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Mukauttaa ohjausobjektien sarkainjärjestystä suorituksen aikana, kun arvona on nollasta poikkeava arvo.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)** – Onko ohjausobjektissa näytettävä teksti alleviivattua.

**[Visible](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="related-functions"></a>Liitetyt toiminnot
[**Distinct**( *Tietolähde*, *SarakkeenNimi* )](../functions/function-distinct.md)

## <a name="example"></a>Esimerkki
1. Lisää **Valintanappi**-ohjausobjekti, anna sille nimeksi **Hinnoittelu** ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**["Standard", "Premium"]**
   
    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **[Selite](control-text-box.md)**-ohjausobjekti, siirrä se **Valintanappi**-ohjausobjektin alapuolelle ja aseta **[Selite](control-text-box.md)**-ohjausobjektin **[Text](properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**If ("Premium" Pricing.Selected.Value "200 euroa per päivä", "150 euroa päivässä")**
   
    Haluatko lisätietoja **[If](../functions/function-if.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
3. Paina F5-näppäintä ja valitse sen jälkeen jompikumpi **Valintanappi**-ohjausobjektin vaihtoehdoista.
   
    **[Selite](control-text-box.md)**-ohjausobjekti näyttää valintasi mukaisen tekstin.
4. (valinnainen) Valitse toinen **Valintanappi**-ohjausobjektin vaihtoehdoista ja tarkista, että näyttöön tulee asiaankuuluva teksti.
5. Palaa oletustyötilaan painamalla Esc.


---
title: 'Vienti- ja tuonti-ohjausobjektit: viitetiedot | Microsoft Docs'
description: Tiedot vienti- ja tuonti-ohjausobjekteista, mukaan lukien ominaisuudet ja esimerkit
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 958589deb4fdee42cb8e6df13ff15addbc06c07e
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="export-control-and-import-control-in-powerapps"></a>Vienti- ja tuonti-ohjausobjektit PowerAppsissa
Ohjausobjektit tietojen viemistä varten paikalliseen tiedostoon ja sen jälkeen näiden tietojen tuomiseen toiseen sovellukseen PowerAppsissa.

## <a name="description"></a>Kuvaus
Jos haluat luoda useamman kuin yhden sovelluksen, joka käyttää samoja tietoja, mutta et halua jakaa tietoja näiden sovellusten ulkopuolella, voit viedä ja tuoda ne käyttämällä **Vienti**-ohjausobjektia ja **Tuonti**-ohjausobjektia. Kun viet tietoja, luot pakatun tiedoston, jonka voit kopioida toiseen koneeseen, mutta et pysty lukemaan sitä missään muussa ohjelmassa kuin PowerAppsissa.

## <a name="warning"></a>Varoitus
Näiden toimintojen käyttöön ottaminen sovelluksessa saattaa altistaa sen tietoturvauhkille ja tietovuodoille.  On suositeltavaa ilmoittaa käyttäjille, että he voivat tuoda vain tunnistettuja ja luotettuja tiedostoja ja viedä vain tietoja, jotka eivät ole luottamuksellisia tai arkaluontoisia.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**Data** – Sen kokoelman, jonka haluat viedä paikalliseen tiedostoon, nimi.

* **Data**-ominaisuus on käytettävissä **Vienti**-ohjausobjektille, mutta ei **Tuonti**-ohjausobjektille.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

## <a name="additional-properties"></a>Lisäominaisuudet
**[Align](properties-text.md)**  – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)**  – Onko ohjausobjektin reuna **Solid** (kiinteä), **Dashed** (katkoviiva), **Dotted** (pisteviiva) vai **None** (ei mitään).

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Color](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Font](properties-text.md)**  – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin paino: **Bold** (lihavoitu), **Semibold** (puolilihavoitu), **Normal** (normaali) tai **Lighter** (kevyempi).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)** – Onko ohjausobjektin teksti kursivoitu.

**[Padding](properties-size-location.md)** – Tuonti- tai vientipainikkeen tekstin ja painikkeen reunojen välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** –Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[RadiusBottomLeft](properties-size-location.md)** – Vasemman alakulman pyöristysmäärä.

**[RadiusBottomRight](properties-size-location.md)** – Oikean alakulman pyöristysmäärä.

**[RadiusTopLeft](properties-size-location.md)** – Vasemman yläkulman pyöristysmäärä.

**[RadiusTopRight](properties-size-location.md)** – Oikean yläkulman pyöristysmäärä.

**[Size](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Yliviivataanko ohjausobjektissa näkyvä teksti.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Text](properties-core.md)**  – Teksti, joka näkyy ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

**[Underline](properties-text.md)** – Onko ohjausobjektissa näkyvä teksti alleviivattua.

**[VerticalAlign](properties-text.md)** – Ohjausobjektin tekstin sijainti suhteessa ohjausobjektin pystysuoraan keskikohtaan.

**[Visible](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="example"></a>Esimerkki
1. Lisää **[Painike](control-button.md)**-ohjausobjekti ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**ClearCollect(Products, {Name:"Europa", Price:"10.99"}, {Name:"Ganymede", Price:"12.49"}, {Name:"Callisto", Price:"11.79"})**
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
   
    Haluatko lisätietoja **[ClearCollect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
2. Paina F5-näppäintä, napsauta tai napauta **[Painike](control-button.md)**-ohjausobjektia ja paina ESC-näppäintä.
3. Lisää **Vienti**-ohjausobjekti ja määritä sen **Data**-ominaisuuden arvoksi **Products**.
4. Paina F5-näppäintä, napsauta tai napauta **Vienti**-ohjausobjektia ja määritä sitten sen tiedoston nimi, johon haluat viedä tiedot.
5. Napsauta tai napauta **Save** ja palaa sitten oletustyötilaan painamalla ESC-näppäintä.
6. Lisää uuteen tai aiemmin luotuun sovellukseen **tuonti**-ohjausobjekti, anna sen nimeksi **MyData**, ja määritä sen **[OnSelect](properties-core.md)**-ominaisuuden arvoksi tämä kaava:<br>
   **Collect(ImportedProducts, MyData.Data)**
7. Paina F5-näppäintä, napsauta tai napauta kohtaa **MyData**, napsauta tai napauta viemääsi tiedostoa ja napsauta tai napauta sitten **Avaa**.
8. Paina ESC-näppäintä, napsauta tai napauta kohtaa **Kokoelmat** **Tiedosto**-valikossa ja vahvista, että nykyisellä sovelluksella on viemäsi tiedot.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
Ohjeet ovat samat kuin **[Painike](control-button.md)**-ohjausobjektille, sillä **Vie** ja **Tuo** ovat erityisiä painikkeita.

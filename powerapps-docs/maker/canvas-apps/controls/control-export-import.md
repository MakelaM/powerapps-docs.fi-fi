---
title: 'Vienti- ja tuonti-ohjausobjektit: viitetiedot | Microsoft Docs'
description: Tiedot vienti- ja tuonti-ohjausobjekteista, mukaan lukien ominaisuudet ja esimerkit
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
ms.openlocfilehash: 1dde9367fe06b1bd2242fe0ac755f5eeedb71bba
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42851836"
---
# <a name="export-control-and-import-control-in-powerapps"></a>Vienti- ja tuonti-ohjausobjektit PowerAppsissa
Ohjausobjektit tietojen viemiseen paikalliseen tiedostoon ja sen jälkeen näiden tietojen tuomiseen toiseen sovellukseen PowerAppsissa.

## <a name="description"></a>Kuvaus
Jos haluat luoda useamman kuin yhden sovelluksen, joka käyttää samoja tietoja, mutta et halua jakaa tietoja näiden sovellusten ulkopuolella, voit viedä ja tuoda ne käyttämällä **Vienti**-ohjausobjektia ja **Tuonti**-ohjausobjektia. Kun viet tietoja, luot pakatun tiedoston, jonka voit kopioida toiseen koneeseen, mutta et pysty lukemaan sitä missään muussa ohjelmassa kuin PowerAppsissa.

## <a name="warning"></a>Varoitus
Näiden toimintojen käyttöön ottaminen sovelluksessa saattaa altistaa sen tietoturvauhkille ja tietovuodoille.  On suositeltavaa ilmoittaa käyttäjille, että he voivat tuoda vain tunnistettuja ja luotettuja tiedostoja ja viedä vain tietoja, jotka eivät ole luottamuksellisia tai arkaluontoisia.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**Data** – Sen kokoelman nimi, jonka haluat viedä paikalliseen tiedostoon.

* **Data**-ominaisuus on käytettävissä **Vienti**-ohjausobjektille, mutta ei **Tuonti**-ohjausobjektille.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

## <a name="additional-properties"></a>Lisäominaisuudet
**[Align](properties-text.md)**  – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

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

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun hiiren kohdistin on kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)** – Onko ohjausobjektin teksti kursivoitu.

**[Padding](properties-size-location.md)** – Tuonti- tai vientipainikkeen tekstin ja painikkeen reunojen välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[RadiusBottomLeft](properties-size-location.md)** – Ohjausobjektin vasemman alakulman pyöristysaste.

**[RadiusBottomRight](properties-size-location.md)** – Ohjausobjektin oikean alakulman pyöristysaste.

**[RadiusTopLeft](properties-size-location.md)** – Ohjausobjektin vasemman yläkulman pyöristysaste.

**[RadiusTopRight](properties-size-location.md)** – Ohjausobjektin oikean yläkulman pyöristysaste.

**[Size](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Text](properties-core.md)**  – Teksti, joka näytetään ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

**[Underline](properties-text.md)** – Ilmaisee, onko ohjausobjektissa näkyvä teksti alleviivattu.

**[VerticalAlign](properties-text.md)** – Ohjausobjektin tekstin sijainti suhteessa ohjausobjektin pystysuoraan keskikohtaan.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="example"></a>Esimerkki
1. Lisää **[Painike](control-button.md)**-ohjausobjekti ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**ClearCollect(Products, {Name:"Europa", Price:"10.99"}, {Name:"Ganymede", Price:"12.49"}, {Name:"Callisto", Price:"11.79"})**
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
   
    Haluatko lisätietoja **[ClearCollect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
2. Paina F5-näppäintä, napsauta tai napauta **[Painike](control-button.md)**-ohjausobjektia ja paina ESC-näppäintä.
3. Lisää **Vienti**-ohjausobjekti ja määritä sen **Data**-ominaisuuden arvoksi **Products**.
4. Paina F5-näppäintä, napsauta tai napauta **Vienti**-ohjausobjektia ja määritä sitten sen tiedoston nimi, johon haluat viedä tiedot.
5. Napsauta tai napauta **Tallenna** ja palaa sitten oletustyötilaan painamalla ESC-näppäintä.
6. Lisää uuteen tai aiemmin luotuun sovellukseen **Tuonti**-ohjausobjekti, anna sen nimeksi **MyData**, ja määritä sen **[OnSelect](properties-core.md)**-ominaisuuden arvoksi tämä kaava:<br>
   **Collect(ImportedProducts, MyData.Data)**
7. Paina F5-näppäintä, napsauta tai napauta kohtaa **MyData**, napsauta tai napauta viemääsi tiedostoa ja napsauta tai napauta sitten **Avaa**.
8. Paina ESC-näppäintä, napsauta tai napauta kohtaa **Kokoelmat** **Tiedosto**-valikossa ja vahvista, että nykyisellä sovelluksella on viemäsi tiedot.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
Ohjeet ovat samat kuin **[Painike](control-button.md)**-ohjausobjektille, sillä **Vie** ja **Tuo** ovat erityisiä painikkeita.

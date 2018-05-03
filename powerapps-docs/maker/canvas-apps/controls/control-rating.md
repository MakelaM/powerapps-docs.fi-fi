---
title: Luokitus-ohjausobjektin viitetiedot| Microsoft Docs
description: Tietoja Luokitus-ohjausobjektista, mukaan lukien ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: 4dd23b8c94ee4760e40b4513e7a88667f85c3a4b
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="rating-control-in-powerapps"></a>Luokitus-ohjausobjekti PowerAppsissa
Ohjausobjekti, jolla käyttäjät voivat ilmaista arvon numeron 1 ja määrittämäsi suurimman numeron väliltä.

## <a name="description"></a>Kuvaus
Tämän ohjausobjektin avulla käyttäjä voi esimerkiksi tietyn määrän tähtiä valitsemalla ilmaista, kuinka paljon hän piti jostakin asiasta.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Default](properties-core.md)** – Ohjausobjektin alkuarvo ennen kuin käyttäjä on muuttanut sitä.

**Max** – Suurin arvo, jonka käyttäjä voi antaa liukusäätimelle tai luokitukselle.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva**vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin näppäimistösyötteisen reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[OnChange](properties-core.md)**  – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**RatingFill** – Luokitus-ohjausobjektin tähtien väri.

**ReadOnly** – Voiko käyttäjä muuttaa liukusäätimen tai luokituksen ohjausobjektin arvoa.

**[Reset](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**ShowValue** – Näytetäänkö liukusäätimen tai luokituksen arvo, kun käyttäjä muuttaa kyseistä arvoa tai pitää osoitinta ohjausobjektin päällä.

**[TabIndex](properties-accessibility.md)**  – Mukauttaa ohjausobjektien sarkainjärjestystä suorituksen aikana, kun arvona on nollasta poikkeava arvo.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilotettu.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Average**( *Arvo1*, *Arvo2,* ... )](../functions/function-aggregates.md)

## <a name="example"></a>Esimerkki
1. Lisää **Luokitus**-ohjausobjekti ja anna sille nimeksi **Kvantitatiivinen**.
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **[Tekstisyöte](control-text-input.md)**-ohjausobjekti, anna sen nimeksi **Kvalitatiivinen** ja siirrä se **Luokitus**-ohjausobjektin alapuolelle.
3. Määritä **[Tekstisyöte](control-text-input.md)**-ohjausobjektin **[Default](properties-core.md)**-ominaisuudeksi **""** ja määritä sen **HintText**-ominaisuudeksi tämä kaava:
   <br>**If(Kvantitatiivinen.Value > 3, "Mistä erityisesti pidit", "Missä meillä olisi parantamisen varaa?")**
   
    Haluatko lisätietoja **[If](../functions/function-if.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
4. Paina F5-näppäintä ja napsauta tai napauta sen jälkeen neljä tai viisi tähteä **Luokitus**-ohjausobjektissa.
   
    **[Tekstisyöte](control-text-input.md)**-ohjausobjektin vihjeteksti muuttuu korkeaa luokitusta vastaavaksi.
5. Napsauta tai napauta vähemmän kuin neljä tähteä kohdassa **Kvantitatiivinen**.
   
    **[Tekstisyöte](control-text-input.md)**-ohjausobjektin vihjeteksti muuttuu alhaista luokitusta vastaavaksi.
6. Palaa oletustyötilaan painamalla Esc-näppäintä.


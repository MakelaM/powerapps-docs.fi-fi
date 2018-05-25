---
title: 'Ohjausobjektin vaihtopainike: viitetiedot | Microsoft Docs'
description: Tietoja ohjausobjektin vaihtopainikkeesta, kuten ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: dac1f8ea99746f04d2d3305e279a4bc5faf67903
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="toggle-control-in-powerapps"></a>Ohjausobjektin vaihtopainike PowerAppsissa
Ohjausobjekti, jonka käyttäjä voi ottaa käyttöön tai poistaa käytöstä siirtämällä sen kahvaa.

## <a name="description"></a>Kuvaus
Vaihtopainike on suunniteltu uusimpia käyttöliittymiä varten, mutta se toimii samalla tavalla kuin valintaruutu.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Oletus](properties-core.md)** – Ohjausobjektin alkuarvo, ennen kuin käyttäjä muuttaa sitä.

**[Arvo](properties-core.md)** – Syöteohjausobjektin arvo.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviivat**, **pisteet** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin näppäimistösyötteisen reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-ominaisuuden asetuksena on **Poistettu käytöstä**.

**FalseFill** – Värintäytön vaihtopainike, kun Poistettu käytöstä on valittuna.

**FalseHoverFill** – Värintäytön vaihtopainike hiiren osoittimen ollessa päällä, kun Poistettu käytöstä on valittuna.

**FalseText** – Teksti, joka näytetään, kun Poistettu käytöstä on valittuna.

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin kohdalla.

**[OnChange](properties-core.md)**  – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

**OnCheck** – Miten sovellus reagoi, kun valintaruudun tai vaihtopainikkeen arvo muuttuu arvoksi **true**.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnUnheck** – Miten sovellus reagoi, kun valintaruudun tai vaihtopainikkeen arvo muuttuu arvoksi **false**.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**RailFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **false** tai liukusäätimen kahvan oikealla puolella olevan viivan väri.

**RailHoverFill** – Vaihtopainikkeen ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **false** tai liukusäätimen kahvan oikealla puolella olevan viivan väri, kun osoitinta pidetään ohjausobjektin vaihtopainikkeen tai liukusäätimen kohdalla.

**[Nollaa](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**ShowLabel** – Näytetäänkö tekstiotsikko ohjausobjektin vaihtopainikkeen vieressä.

**[TabIndex](properties-accessibility.md)** – Mukauttaa ohjausobjektien sarkainjärjestystä käytön aikana, kun arvona on nollasta poikkeava arvo.

**TextPosition** – Onko selite ohjausobjektin vaihtopainikkeen vasemmalla vai oikealla puolella.

**[Työkaluvihje](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin osoittimen ollessa ohjausobjektin päällä.

**TrueFill** – Värintäytön vaihtopainike, kun Käytössä on valittuna.

**TrueHoverFill** – Värintäytön vaihtopainike hiiren osoittimen ollessa päällä, kun Käytössä on valittuna.

**TrueText** – Teksti, joka näytetään, kun Käytössä on valittuna.

**ValueFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **true** tai liukusäätimen kahvan vasemmalla puolella olevan viivan väri.

**ValueHoverFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **true** tai liukusäätimen kahvan vasemmalla puolella olevan viivan väri, kun osoitinta pidetään ohjausobjektin tai liukusäätimen päällä.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**If**( *Condition*, *Result* )](../functions/function-if.md)

## <a name="example"></a>Esimerkki
1. Lisää vaihtopainike ja anna sille nimeksi **MemberDiscount**.

    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää selite ja aseta sen **[Teksti](properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**If(MemberDiscount.Value = true, "Price: $75", "Price: $100")**

    Haluatko lisätietoja **[If](../functions/function-if.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
3. Paina F5-näppäintä ja muuta **MemberDiscount**-arvoa.

    Selitteessä on eri hinta sen mukaan, onko **MemberDiscount** käytössä vai poissa käytöstä.
4. Palaa oletustyötilaan painamalla Esc-näppäintä.

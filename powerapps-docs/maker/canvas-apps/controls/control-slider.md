---
title: 'Liukusäädin: viitetiedot | Microsoft Docs'
description: Liukusäädintä koskevaa tietoa, kuten ominaisuuksia ja esimerkkejä
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
ms.openlocfilehash: dc10ac44c1c14f182c39176a6b0216f3ede3816d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="slider-control-in-powerapps"></a>Liukusäädin PowerAppsissa
Ohjausobjekti, jolla käyttäjä voi määrittää arvon vetämällä kahvaa.

## <a name="description"></a>Kuvaus
Käyttäjä voi valita arvon pienimmän ja suurimman määrittämäsi arvon väliltä. Arvo valitaan vetämällä liukusäädintä vasemmalta oikealle tai ylhäältä alas, riippuen siitä, kumman suunnan valitset.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Default](properties-core.md)** – Ohjausobjektin alkuarvo, ennen kuin käyttäjä on muuttanut sitä.

**Max** – Suurin arvo, jonka käyttäjä voi antaa liukusäätimelle tai luokitukselle.

**Min** – Pienin arvo, jonka käyttäjä voi antaa liukusäätimelle.

**[Value](properties-core.md)** – Syöteohjausobjektin arvo.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)**  – Onko ohjausobjektin reuna **Solid** (kiinteä), **Dashed** (katkoviiva), **Dotted** (pisteviiva) vai **None** (ei mitään).

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin näppäimistösyötteisen reunan paksuus.

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**) vai onko ominaisuus kokonaan poissa käytöstä (**Disabled**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-ominaisuus **ei ole käytössä**.

**HandleActiveFill** – Liukusäätimen kahvan väri, kun käyttäjä muuttaa sen arvoa.

**HandleFill** – Vaihtopainikkeen tai liukusäätimen kahvan (elementti, jonka sijainti muuttuu) väri.

**HandleHoverFill** – Liukusäätimen kahvan väri, kun käyttäjä pitää hiiren osoitinta kahvan päällä.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**Layout** – Vierittääkö käyttäjä valikoiman läpi tai mukauttaako käyttäjä liukusäädintä ylhäältä alas (**Vertical**) vai vasemmalta oikealle (**Horizontal**).

**[OnChange](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**RailFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **false** tai liukusäätimen kahvan oikealla puolella olevan viivan väri.

**RailHoverFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **false** tai liukusäätimen kahvan oikealla puolella olevan viivan väri silloin, kun osoitinta pidetään valitsinkytkimen tai liukusäätimen yläpuolella.

**ReadOnly** – Voiko käyttäjä muuttaa liukusäätimen tai luokituksen ohjausobjektin arvoa.

**[Reset](properties-core.md)** – Palautuuko ohjausobjekti oletusarvoonsa.

**ShowValue** – Näytetäänkö liukusäätimen tai luokituksen arvo, kun käyttäjä tekee muutoksia kyseiseen arvoon tai kun tämä pitää osoitinta ohjausobjektin päällä.

**[TabIndex](properties-accessibility.md)** – Mukauttaa ohjausobjektien sarkainjärjestystä suorituksen aikana, kun arvona on nollasta poikkeava arvo.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin osoittimen ollessa ohjausobjektin päällä.

**ValueFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **true** tai liukusäätimen kahvan vasemmalla puolella olevan viivan väri.

**ValueHoverFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **true** tai liukusäätimen kahvan vasemmalla puolella olevan viivan väri, kun osoitinta pidetään ohjausobjektin tai liukusäätimen päällä.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**Sum**( *Arvo1*, *Arvo2* )](../functions/function-aggregates.md)

## <a name="example"></a>Esimerkki
1. Lisää painike ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**ClearCollect(KaupunkienVäkiluvut, {Kaupunki:"Lontoo", Maa:"Yhdistynyt kuningaskunta", Väkiluku:8615000}, {Kaupunki:"Berliini", Maa:"Saksa", Väkiluku:3562000}, {Kaupunki:"Madrid", Maa:"Espanja", Väkiluku:3165000}, {Kaupunki:"Rooma", Maa:"Italia", Väkiluku:2874000}, {Kaupunki:"Pariisi", Maa:"Ranska", Väkiluku:2273000}, {Kaupunki:"Hampuri", Maa:"Saksa", Väkiluku:1760000}, {Maa:"Barcelona", Maa:"Espanja", Väkiluku:1602000}, {Kaupunki:"München", Maa:"Saksa", Väkiluku:1494000}, {Kaupunki:"Milano", Maa:"Italia", Väkiluku:1344000})**
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
   
    Haluatko lisätietoja **[ClearCollect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
2. Paina F5-näppäintä, valitse painike ja paina sitten Esc-näppäintä.
3. Lisää liukusäädin, siirrä se painikkeen alapuolelle ja anna liukusäätimelle nimi **MinVäkiluku**.
4. Määritä liukusäätimen **Max**-ominaisuuden arvoksi **5000000** ja sen **Min**-ominaisuuden arvoksi **1000000**.
5. Lisää pystysuunnassa oleva tekstivalikoima, siirrä se liukusäätimen alapuolelle ja määritä valikoiman **[Items](properties-core.md)**-ominaisuuden arvoksi tämä kaava:<br>
   **Filter(KaupunkienVäkiluvut, Väkiluku > MinVäkiluku)**
6. Määritä valikoiman ensimmäisen kohteen ylimmän otsikon **[Text](properties-core.md)**-ominaisuudeksi **TämäKohde.Kaupunki** ja määritä alimman otsikon **[Text](properties-core.md)**-ominaisuudeksi seuraava kaava:<br> **Text(ThisItem.Väkiluku, "##,###")**
7. Paina F5-näppäintä ja säädä **MinVäkiluku**-liukusäädin näyttämään vain ne kaupungit, joiden väkiluku on suurempi kuin määrittämäsi arvo.
8. Palaa oletustyötilaan painamalla Esc-näppäintä.


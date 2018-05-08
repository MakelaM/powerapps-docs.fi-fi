---
title: 'Avattava luettelo -ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja Avattava luettelo -ohjausobjektista, mukaan lukien ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: 828292cc888d26f2060260826296960f1bd4f98f
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="drop-down-control-in-powerapps"></a>Avattava luettelo -ohjausobjekti PowerAppsissa
Luettelo, joka näyttää vain ensimmäisen kohdan, kunnes käyttäjä avaa luettelon.

## <a name="description"></a>Kuvaus
**Avattava luettelo** -ohjausobjekti säästää näyttötilaa erityisesti, kun luettelo sisältää paljon vaihtoehtoja. Ohjausobjekti käyttää vain yhden rivin, kunnes käyttäjä valitsee nuolenkärjen ja paljastaa näin lisää vaihtoehtoja.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Default](properties-core.md)** – Alkuperäinen asetus, joka on voimassa, ennen kuin käyttäjä muuttaa sitä.

**[Items](properties-core.md)** – Ohjausobjektiin, kuten valikoimaan, luetteloon tai kaavioon, näkyviin tulevan tiedon lähde.

[!INCLUDE [long-items](../../../includes/long-items.md)]

**Selected** – Valittu kohde.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun sillä on näppäimistökohdistus.

**ChevronBackground** – Avattavan luettelon alaspäin osoittavan nuolen taustaväri.

**ChevronFill** – Avattavan luettelon alaspäin osoittavan nuolen väri.

**[Color](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus pois käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Font](properties-text.md)**  – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin paino: **lihavoitu**, **puolilihavoitu**, **normaali** tai **vaaleampi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**[OnChange](properties-core.md)**  – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[Reset](properties-core.md)**  – Palautetaanko ohjausobjektin oletusarvo.

**[SelectionColor](properties-color-border.md)** – Luettelon valitun kohteen tai kohteiden tekstin väri tai kynä-ohjausobjektin valintatyökalun väri.

**[SelectionFill](properties-color-border.md)** – Luettelon valitun kohteen tai kohteiden taustaväri tai kynä-ohjausobjektin valitun alueen väri.

**[Size](properties-text.md)** – Ohjausobjektissa näytettävän tekstin fonttikoko.

**[Strikethrough](properties-text.md)** – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Mukauttaa ohjausobjektien sarkainjärjestystä suorituksen aikana, kun arvona on nollasta poikkeava arvo.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti alleviivattua.

**[Visible](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="example"></a>Esimerkki
1. Lisää **[Painike](control-button.md)**-ohjausobjekti ja aseta sen **[Text](properties-core.md)**-ominaisuudeksi **Kerää**.
   
    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Määritä **[painikkeen](control-button.md)** **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**ClearCollect(KaupunkienVäkiluvut, {Kaupunki:"Lontoo", Maa:"Yhdistynyt kuningaskunta", Väkiluku:8615000}, {Kaupunki:"Berliini", Maa:"Saksa", Väkiluku:3562000}, {Kaupunki:"Madrid", Maa:"Espanja", Väkiluku:3165000}, {Kaupunki:"Rooma", Maa:"Italia", Väkiluku:2874000}, {Kaupunki:"Pariisi", Maa:"Ranska", Väkiluku:2273000}, {Kaupunki:"Hampuri", Maa:"Saksa", Väkiluku:1760000}, {Maa:"Barcelona", Maa:"Espanja", Väkiluku:1602000}, {Kaupunki:"München", Maa:"Saksa", Väkiluku:1494000}, {Kaupunki:"Milano", Maa:"Italia", Väkiluku:1344000})**
   
    Haluatko lisätietoja **[ClearCollect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
3. Paina F5-näppäintä, napsauta tai napauta **[Painike](control-button.md)**-ohjausobjektia ja paina Esc.
4. Lisää **Avattava luettelo** -ohjausobjekti, anna sille nimeksi **Maat** ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi tämä arvo:
   <br>**Distinct(KaupunkienVäkiluvut, Maa)**
5. Lisää pystysuuntainen **Tekstivalikoima** ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**Filter(KaupunkienVäkiluvut, Maat.Selected.Value in Maa)**
6. Aseta **Tekstivalikoima**-ohjausobjektin ensimmäisessä kohteessa ylemmän **[Otsikko](control-text-box.md)**-ohjausobjektin **[Text](properties-core.md)**-ominaisuudeksi **ThisItem.Kaupunki** ja poista alempi **[Otsikko](control-text-box.md)**-ohjausobjekti.
7. Aseta **Tekstivalikoima**-ohjausobjektin **[TemplateSize](control-gallery.md)**-ominaisuudeksi **80**.
8. Paina F5, napsauta tai napauta **Maat**-luettelon alaspäin osoittavaa nuolta ja valitse luettelosta jokin vaihtoehto.
   
    **Tekstivalikoima**-ohjausobjekti näyttää vain valitsemasi maan kaupungit.


---
title: 'Luetteloruutu-ohjausobjekti: viittaus | Microsoft Docs'
description: Luetteloruutu-ohjausobjektia koskevaa tietoa, kuten ominaisuuksia ja esimerkkejä
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
ms.openlocfilehash: 71f3493064e7b877a501f9b91f93adedb0c68f6a
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="list-box-control-in-powerapps"></a>Luetteloruutu-ohjausobjekti PowerAppsissa
Luettelo, josta käyttäjä voi valita yhden tai useita kohteita.

## <a name="description"></a>Kuvaus
**Luetteloruutu**-ohjausobjekti näyttää aina kaikki käytettävissä olevat vaihtoehdot (toisin kuin **[Avattava luettelo](control-drop-down.md)** -ohjausobjekti), ja siitä käyttäjä voi valita useamman kuin yhden kohteen kerrallaan (toisin kuin **[Valintanappi](control-radio.md)**-ohjausobjekti).

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Default](properties-core.md)** – Alkuperäinen asetus, joka on voimassa, ennen kuin käyttäjä muuttaa sitä.

**[Kohteet](properties-core.md)** – Ohjausobjektiin, kuten valikoimaan, luetteloon tai kaavioon, näkyviin tulevan tiedon lähde.

[!INCLUDE [long-items](../../../includes/long-items.md)]

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviivat**, **pisteet** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun sillä on näppäimistökohdistus.

**[Väri](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Fontti](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin leveys: **lihavoitu**, **puolilihavoitu**, **normaali** tai **ohuempi**.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin kohdalla.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen kohdalla.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Kursivoitu](properties-text.md)**  – Ilmaisee, onko ohjausobjektin teksti kursivoitu.

**ItemPaddingLeft** – Luetteloruudun tekstin ja sen vasemman reunan välinen etäisyys.

**[LineHeight](properties-text.md)** – Esimerkiksi tekstin rivien tai luettelon kohteiden välinen etäisyys.

**[OnChange](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Palauta](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**[SelectionColor](properties-color-border.md)** – Luettelon valitun kohteen tai kohteiden tekstin väri tai kynä-ohjausobjektin valintatyökalun väri.

**[SelectionFill](properties-color-border.md)** – Luettelon valitun kohteen tai kohteiden taustaväri tai kynä-ohjausobjektin valitun alueen väri.

**SelectMultiple** – Voiko käyttäjä valita useamman kuin yhden kohteen luetteloruudusta.

**[Koko](properties-text.md)** – Ohjausobjektiin ilmaantuvan tekstin fonttikoko.

**[Yliviivaus](properties-text.md)**  – Ilmaisee, onko ohjausobjektissa näkyvä teksti yliviivattu.

**[TabIndex](properties-accessibility.md)** – Mukauttaa ohjausobjektien sarkainjärjestystä käytön aikana, kun arvona on nollasta poikkeava arvo.

**[Työkaluvihje](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun kohdistin on ohjausobjektin päällä.

**[Alleviivattu](properties-text.md)** – Ilmaisee, onko ohjausobjektissa näytettävä teksti alleviivattu.

**[Näkyvissä](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liitetyt toiminnot
[**Distinct**( *DataSource*, *ColumnName* )](../functions/function-distinct.md)

## <a name="example"></a>Esimerkki
1. Lisää **Luetteloruutu**-ohjausobjekti, anna sille nimeksi **CategoryList** ja aseta sen **[Kohteet](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **["Carpet","Hardwood","Tile"]**
   
    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
   
    ![Lattianpäällysteet luetteloruudussa](./media/control-list-box/category-listbox.png)
2. Lisää kolme **[Avattava luettelo](control-drop-down.md)** -ohjausobjektia, siirrä ne kohtaan **CategoryList** ja anna niille nimeksi **CarpetList**, **HardwoodList**  ja **TileList**.
3. Määritä kunkin **[Avattava luettelo](control-drop-down.md)** -ohjausobjektin **[Kohteet](properties-core.md)**-ominaisuudeksi jokin näistä arvoista:
   
   * CarpetList: **["Caserta Stone Beige","Ageless Beauty Clay", "Lush II Tundra"]**
   * HardwoodList: **["Golden Teak","Natural Hickory", "Victoria Mahogany"]**
   * TileList: **["Honey Onyx Marble","Indian Autumn Slate", "Panaria Vitality Ceramic"]**
     
     ![Lattianpäällysteiden nimet avattavissa luetteloissa](./media/control-list-box/flooring-names.png)
4. Määritä kunkin **[Avattava luettelo](control-drop-down.md)** -ohjausobjektin **[Näkyvissä](properties-core.md)**-ominaisuudeksi jokin näistä arvoista:
   
   * CarpetList: **If("Carpet" in CategoryList.SelectedItems.Value, true)**
   * HardwoodList: **If("Hardwood" in CategoryList.SelectedItems.Value, true)**
   * TileList: **If("Tile" in CategoryList.SelectedItems.Value, true)**
     
     Haluatko lisätietoja **[If](../functions/function-if.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
5. Paina F5-näppäintä ja valitse sitten yksi tai useampi kohde kohdasta **CategoryList**.
   
    Asianmukainen **[Avattava luettelo](control-drop-down.md)** -ohjausobjekti (tai useita) näkyy valintasi tai valintojesi perusteella.
   
    ![Lattianpäällysteiden nimet avattavissa luetteloissa](./media/control-list-box/selected-lists.png)
6. (valinnainen) Palaa oletustyötilaan painamalla Esc-näppäintä.


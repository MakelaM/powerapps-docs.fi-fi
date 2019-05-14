---
title: 'Luetteloruutu-ohjausobjekti: viite | Microsoft Docs'
description: Luetteloruutu-ohjausobjektia koskevaa tietoa, kuten ominaisuuksia ja esimerkkejä
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
ms.openlocfilehash: a7128ace53cc1e0754eb7247282b2ecae7642672
ms.sourcegitcommit: 8d0ba2ec0c97be91d1350180dd6881c14dec8f2d
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/10/2019
ms.locfileid: "65517416"
ms.PowerAppsDecimalTransform: true
---
# <a name="list-box-control-in-powerapps"></a>Luetteloruutu-ohjausobjekti PowerAppsissa
Luettelo, josta käyttäjä voi valita yhden tai useita kohteita.

## <a name="description"></a>Kuvaus
**Luetteloruutu**-ohjausobjekti näyttää aina kaikki käytettävissä olevat vaihtoehdot (toisin kuin **[Avattava luettelo](control-drop-down.md)** -ohjausobjekti), ja siitä käyttäjä voi valita useamman kuin yhden kohteen kerrallaan (toisin kuin **[Valintanappi](control-radio.md)**-ohjausobjekti).

## <a name="key-properties"></a>Keskeiset ominaisuudet
**[Oletus](properties-core.md)** – Alkuperäinen asetus, joka on voimassa, ennen kuin käyttäjä muuttaa sitä.

**[Kohteet](properties-core.md)** – Tietolähde, joka näkyy ohjausobjektissa, kuten valikoimassa, luettelossa tai kaaviossa.

**Valitun** – tietueen, joka edustaa valittu kohde.

Kun lisäät valikoiman, luettelon tai kaavion, ominaisuusluettelossa näkyvät **kohteet** oletusarvoisesti niin, että voit helposti määrittää tiedot, jotka uuden ohjausobjektin on tarkoitus näyttää. Voit esimerkiksi määrittää valikoiman **Kohteet**-ominaisuudeksi **Tili**-taulukon Salesforcessa, taulukon nimeltä **Varasto**, jonka loit Excelissä ja latasit pilveen, tai SharePoint-luettelon nimeltä **ConferenceSpeakers**.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

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

**[FontWeight](properties-text.md)**  – ohjausobjektin tekstin paino: **Lihavoitu**, **Semibold**, **Normaali**, tai **ohuempi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun hiiren kohdistin on kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)**  – Ilmaisee, onko ohjausobjektin teksti kursivoitu.

**ItemPaddingLeft** – Luetteloruudun tekstin ja sen vasemman reunan välinen etäisyys.

**[LineHeight](properties-text.md)** – Rivin korkeus eli esimerkiksi tekstin tai luettelon rivien välinen etäisyys.

**[OnChange](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi käyttämällä liukusäädintä).

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Reset](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**SelectedText (vanhentunut)** – merkkijonoarvon, joka edustaa valittu kohde.

**[SelectionColor](properties-color-border.md)** – Luettelosta valitun kohteen tai kohteiden tekstin väri tai kynä-ohjausobjektin valintatyökalun väri.

**[SelectionFill](properties-color-border.md)** – Luettelosta valitun kohteen tai kohteiden taustaväri tai kynä-ohjausobjektin valitun alueen väri.

**SelectMultiple** – Voiko käyttäjä valita useamman kuin yhden kohteen luetteloruudusta.

**[Koko](properties-text.md)** – Ohjausobjektiin ilmaantuvan tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)** – Onko ohjausobjektissa näytettävä teksti alleviivattu.

**[Visible](properties-core.md)** – Onko ohjausobjekti näytössä vai piilotettuna.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liitetyt toiminnot
[**Distinct**( *Tietolähde*; *SarakkeenNimi* )](../functions/function-distinct.md)

## <a name="example"></a>Esimerkki
1. Lisää **Luetteloruutu**-ohjausobjekti, anna sille nimeksi **CategoryList** ja aseta sen **[Kohteet](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **["Matto";"Kovapuu";"Laatta"]**
   
    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
   
    ![Lattianpäällysteet luetteloruudussa](./media/control-list-box/category-listbox.png)
2. Lisää kolme **[Avattava luettelo](control-drop-down.md)** -ohjausobjektia, siirrä ne kohtaan **CategoryList** ja anna niille nimeksi **CarpetList**, **HardwoodList**  ja **TileList**.
3. Määritä kunkin **[Avattava luettelo](control-drop-down.md)** -ohjausobjektin **[Kohteet](properties-core.md)**-ominaisuudeksi jokin näistä arvoista:
   
   * CarpetList: **["Caserta Stone Beige";"Ageless Beauty Clay"; "Lush II Tundra"]**
   * HardwoodList: **["Golden Teak";"Natural Hickory"; "Victoria Mahogany"]**
   * TileList: **["Honey Onyx Marble";"Indian Autumn Slate"; "Panaria Vitality Ceramic"]**
     
     ![Lattiapäällysteiden nimet avattavissa luetteloissa](./media/control-list-box/flooring-names.png)
4. Määritä kunkin **[Avattava luettelo](control-drop-down.md)** -ohjausobjektin **[Näkyvissä](properties-core.md)**-ominaisuudeksi jokin näistä arvoista:
   
   * CarpetList: **Jos (”matto” in CategoryList.SelectedItems.Value, true)**
   * HardwoodList: **IF (”Kovapuu” in CategoryList.SelectedItems.Value, true)**
   * TileList: **IF (”laatta” in CategoryList.SelectedItems.Value, true)**
     
     Haluatko lisätietoja **[If](../functions/function-if.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
5. Paina F5-näppäintä ja valitse sitten yksi tai useampi kohde kohdasta **CategoryList**.
   
    Asianmukainen **[Avattava luettelo](control-drop-down.md)** -ohjausobjekti (tai useita) näkyy valintasi tai valintojesi perusteella.
   
    ![Lattiapäällysteiden nimet avattavissa luetteloissa](./media/control-list-box/selected-lists.png)
6. (valinnainen) Palaa oletustyötilaan painamalla Esc-näppäintä.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **SelectionColor** ja **SelectionFill**
* **SelectionFill** ja **[Fill](properties-color-border.md)**
* **[HoverFill](properties-color-border.md)** ja **[Fill](properties-color-border.md)**
* **[PressedFill](properties-color-border.md)** ja **[Fill](properties-color-border.md)**

Tämä tulee [värikontrastin vakiovaatimusten lisäksi](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.

    > [!NOTE]
  > Sarkainnäppäimellä voit siirtyä **Luetteloruutuun** tai siitä pois. Nuolinäppäimillä voit siirtyä **Luetteloruudun** sisällössä.

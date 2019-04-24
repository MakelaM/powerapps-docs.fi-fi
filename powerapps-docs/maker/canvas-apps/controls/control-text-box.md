---
title: 'Selite-ohjausobjekti: viite | Microsoft Docs'
description: Tietoja selite-ohjausobjektista, mukaan lukien ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: d909b41dd61fca079fc409b51373af0789a3db84
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61548704"
---
# <a name="label-control-in-canvas-apps"></a>Selite-ohjausobjekti pohjaan perustuvat sovellukset

Kenttä, jossa näkyy tietoja, kuten tekstiä, numeroita, päivämääriä tai valuutta.

## <a name="description"></a>Kuvaus

Selitteessä näkyy tietoja, jotka määrität tekstimerkkijonoliteraalina tai kaavana. Merkkijonoliteraali näyttää tekstin juuri sellaisena kuin se kirjoitetaan, ja kaava palauttaa tekstimerkkijonon. Selitteet näkyvät usein muun ohjausobjektin (kuten näytön otsikkonauhan) ulkopuolella, selitteenä, joka yksilöi toisen ohjausobjektin (kuten luokituksen tai äänen ohjausobjektin), tai valikoimassa, jossa näytetään tietyn tyyppisiä tietoja kohteesta.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet

**[AutoHeight](properties-core.md)**  – Määritä arvoksi TOSI, jos haluat näyttää kaikki teksti sen korkeus selitteen. Aseta arvoksi epätosi, jos haluat katkaista tekstin määritettyyn korkeuteen.

**[Color](properties-color-border.md)** – Ohjausobjektin tekstin väri.

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[Text](properties-core.md)**  – Teksti, joka näytetään ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

**[DelayOutput](properties-core.md)** – Määritä arvoksi tosi, jos haluat viivästyttää toimintoa tekstinsyötön aikana.

## <a name="additional-properties"></a>Lisäominaisuudet

**[Align](properties-text.md)** – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**AutoHeight** – Suurentaako selite automaattisesti **[Korkeus](properties-size-location.md)**-ominaisuutta, jos sen **[Teksti](properties-core.md)**-ominaisuus sisältää enemmän merkkejä kuin ohjausobjekti voi näyttää kerralla.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[FontWeight](properties-text.md)**  – ohjausobjektin tekstin paino: **Lihavoitu**, **Semibold**, **Normaali**, tai **ohuempi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun hiiren kohdistin on kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**[LineHeight](properties-text.md)** – Rivin korkeus eli esimerkiksi tekstin tai luettelon rivien välinen etäisyys.

**[Live](properties-accessibility.md)**  – miten Näytönlukuohjelman ilmoittaa otsikon arvon muutokset **tekstin** ominaisuus.

* Kun **käytöstä**, näytönlukuohjelma ei muutoksia.
* Kun **Polite**, näytönlukuohjelma on valmis, ennen kuin muutokset, joka suoritettaessa näytönlukuohjelma oli puhumalla esittelyssä puhumalla.
* Kun **Assertive**, näytönlukuohjelma keskeyttää itse koskevista muutoksista, joka suoritettaessa näytönlukuohjelma oli puhumalla.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**Overflow** – Tuleeko selitteeseen vierityspalkki, jos sen **Rivitys**-ominaisuuden asetuksena on **tosi** ja ohjausobjektin **[Teksti](properties-core.md)**-ominaisuudessa on enemmän merkkejä kuin ohjausobjekti pystyy näyttämään kerralla.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**Roolin** -semanttisen roolin nimen teksti, kuten otsikko 1. Otsikon tyyli ei muutu, mutta tekee tulos semanttisesti oikea lukema tulkintaa.

**[Size](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti alleviivattu.

**[VerticalAlign](properties-text.md)** – Ohjausobjektin tekstin sijainti suhteessa ohjausobjektin pystysuoraan keskikohtaan.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**Wrap** – Rivitetäänkö teksti, joka on liian pitkä mahtumaan selitteeseen, seuraavalle riville.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät toiminnot

[**Text**( *Number*, "*FormatCodes*" )](../functions/function-text.md)

## <a name="examples"></a>Esimerkkejä

### <a name="show-a-literal-string"></a>Merkkijonoliteraalin näyttäminen

* Lisää selite ja määritä sen **[Teksti](properties-core.md)**-ominaisuudeksi **"Hei maailma"** (mukaan lukien lainausmerkit).
  
    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

### <a name="show-the-result-of-a-formula"></a>Näytä kaavan tulos

* Lisää selite ja aseta sen **[Teksti](properties-core.md)**-ominaisuudeksi esimerkiksi seuraavanlainen kaava:<br>
  **Today()**
  
    > [!NOTE]
  > Kun määrität kaavan, älä käytä lainausmerkkejä, ellei kaavan argumentti ole merkkijonoliteraali. Aseta siinä tapauksessa argumentti lainausmerkkeihin, mutta älä itse kaavaa.
  
    Haluatko lisätietoja **[Today](../functions/function-now-today-istoday.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?

### <a name="show-data-in-a-gallery"></a>Tietojen näyttäminen valikoimassa

Tässä toimenpiteessä luot kokoelman, jonka nimi on **KaupunkienVäkiluvut**. Se sisältää tietoja Euroopan kaupunkien väkiluvuista. Seuraavaksi näytät tiedot kolme selitettä sisältävässä valikoimassa ja määrität, minkä tyyppistä tietoa kukin selite näyttää.

1. Lisää painike ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **ClearCollect(KaupunkienVäkiluvut, {Kaupunki:"Lontoo", Maa:"Yhdistynyt kuningaskunta", Väkiluku:8615000}, {Kaupunki:"Berliini", Maa:"Saksa", Väkiluku:3562000}, {Kaupunki:"Madrid", Maa:"Espanja", Väkiluku:3165000}, {Kaupunki:"Rooma", Maa:"Italia", Väkiluku:2874000}, {Kaupunki:"Pariisi", Maa:"Ranska", Väkiluku:2273000}, {Kaupunki:"Hampuri", Maa:"Saksa", Väkiluku:1760000}, {Maa:"Barcelona", Maa:"Espanja", Väkiluku:1602000}, {Kaupunki:"München", Maa:"Saksa", Väkiluku:1494000}, {Kaupunki:"Milano", Maa:"Italia", Väkiluku:1344000})**
2. Paina F5-painiketta, valitse painike ja paina sitten ESC-näppäintä.
3. Lisää tekstivalikoima ja määritä sen **[Kohteet](properties-core.md)**-ominaisuuden arvoksi **KaupunkienVäkiluvut**.

    Kun valikoima on valittuna, oikeanpuoleisessa ruudussa näkyvät valikoimaa koskevat vaihtoehdot.
4. Määritä **Gallery1**-ruudussa, ylimmäksi luetteloksi **Väkiluku**, keskimmäiseksi luetteloksi **Kaupunki** ja alimmaiseksi luetteloksi **Maa**.

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet

Nimestään huolimatta **Label**-ohjausobjektia ei tarvitse käyttää toisen ohjausobjektin nimenä. Sen avulla voidaan näyttää mikä tahansa teksti.

**Label**-ohjausobjektia voidaan käyttää painikkeena tai linkkinä määrittämällä **[OnSelect](properties-core.md)**-toiminta. Tällä tavalla käytettynä siinä on samanlaisia helppokäyttötoimintojen kannalta huomioon otettavia seikkoja kuin painikkeilla.

### <a name="color-contrast"></a>Värikontrasti

Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:

* **[Color](properties-color-border.md)** ja **[Fill](properties-color-border.md)**
* Muut [tavalliset värien kontrasti vaatimukset](../accessible-apps-color.md) pätevät (käytettäessä painikkeena tai linkkinä)

### <a name="screen-reader-support"></a>Näytönlukuohjelmien tuki

* **[Teksti](properties-core.md)** on oltava käytössä.
* **[Live](properties-accessibility.md)**  on asetettava **Polite** tai **Assertive** Jos tulee näytönlukuohjelma arvon muutokset **tekstin** ominaisuus.

  > [!NOTE]
  > Näytönlukuohjelmat käsittelevät **Label**-ohjausobjekteja painikkeina, kun **[TabIndex](properties-accessibility.md)** on nolla tai suurempi.

### <a name="low-vision-support"></a>Huonon näön tuki

* **Label**-ohjausobjektin pitäisi näyttää linkiltä, jos sitä käytetään linkkinä.
  * Määritä **[Underline](properties-text.md)**-asetuksen arvoksi **true**
  * **[HoverColor](properties-color-border.md)** -ohjausobjektin asetuksen tulee olla eri kuin  **[Color](properties-color-border.md)**-ohjausobjektin asetuksen

### <a name="keyboard-support"></a>Näppäimistön tuki

* **[TabIndex](properties-accessibility.md)** -asetuksen on oltava nolla tai suurempi, jos tekstiä käytetään painikkeena tai linkkinä. Näin näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistusilmaisimien on oltava selvästi näkyvissä, jos tekstiä käytetään painikkeena tai linkkinä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.

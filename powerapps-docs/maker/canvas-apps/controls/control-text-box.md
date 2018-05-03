---
title: 'Selite-ohjausobjekti: viitetiedot | Microsoft Docs'
description: Tietoja selite-ohjausobjektista, mukaan lukien ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: f0547963060d31f86b32cc2aaff38b116d35036b
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="label-control-in-powerapps"></a>Selite-ohjausobjekti PowerAppsissa
Kenttä, jossa näkyy arvoja, kuten tekstiä, numeroita, päivämääriä tai valuutta.

## <a name="description"></a>Kuvaus
Selitteessä näkyy tietoja, jotka määrität tekstimerkkijonoliteraalina tai kaavana. Merkkijonoliteraali näyttää tekstin juuri sellaisena kuin se kirjoitetaan ja kaava palauttaa tekstimerkkijonon. Selitteet näkyvät usein muun ohjausobjektin (kuten näytön otsikkonauhan) ulkopuolella, selitteenä, joka yksilöi toisen ohjausobjektin (kuten luokituksen tai äänen ohjausobjektin) tai valikoimassa, jossa näytetään tietyn tyyppisiä tietoja kohteesta.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[AutoHeight](properties-core.md)** – Määritä arvoksi true, jos haluat, että selitteen korkeus kasvaa automaattisesti ja näyttää kaiken määritetyn tekstin. Aseta arvoksi false, jos haluat katkaista tekstin määritettyyn korkeuteen.

**[Color](properties-color-border.md)** – Ohjausobjektin tekstin väri.

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[Text](properties-core.md)**  – Teksti, joka näytetään ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

**[DelayOutput](properties-core.md)** – Määritä arvoksi true, jos haluat viivästyttää toimintoa tekstinsyötön aikana.

## <a name="additional-properties"></a>Lisäominaisuudet
**[Align](properties-text.md)** – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**AutoHeight** – Kasvaako selitteen **[Height](properties-size-location.md)**-ominaisuus automaattisesti, jos sen **[Text](properties-core.md)**-ominaisuus sisältää enemmän merkkejä kuin ohjausobjekti voi näyttää kerralla.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin paino: **lihavoitu**, **puolilihavoitu**, **normaali** tai **ohuempi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Kursivoitu](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**[LineHeight](properties-text.md)** – Rivin korkeus eli esimerkiksi tekstin tai luettelon rivien välinen etäisyys.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**Overflow** – Tuleeko selitteeseen näkyviin vierityspalkki, jos sen **Wrap**-ominaisuuden arvoksi on asetettu **true** ja ohjausobjektin **[Text](properties-core.md)**-ominaisuuden arvo sisältää enemmän merkkejä kuin ohjausobjekti pystyy näyttämään kerralla.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** –Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Size](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**[Strikethrough](properties-text.md)** – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[Tooltip](properties-core.md)** – Työkaluvihjeen ohjeteksti, joka ilmestyy näkyviin hiiren osoittimen ollessa ohjausobjektin päällä.

**[Underline](properties-text.md)** – Onko ohjausobjektissa näkyvä teksti alleviivattua.

**[VerticalAlign](properties-text.md)** – Ohjausobjektin tekstin sijainti suhteessa ohjausobjektin pystysuoraan keskikohtaan.

**[Visible](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**Wrap** – Rivitetäänkö teksti, joka on liian pitkä mahtumaan selitteeseen, seuraavalle riville.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Text**( *Number*, "*FormatCodes*" )](../functions/function-text.md)

## <a name="examples"></a>Esimerkkejä
### <a name="show-a-literal-string"></a>Näytä merkkijonoliteraali
* Lisää selite ja määritä sen **[Text](properties-core.md)**-ominaisuudeksi **"Hei maailma"** (mukaan lukien lainausmerkit).
  
    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

### <a name="show-the-result-of-a-formula"></a>Näytä kaavan tulos
* Lisää selite ja aseta sen **[Text](properties-core.md)**-ominaisuudeksi esimerkiksi seuraavanlainen kaava:<br>
  **Today()**
  
    > [!NOTE]
> Kun määrität kaavan, älä käytä lainausmerkkejä ellei kaavan argumentti ole merkkijonoliteraali. Aseta siinä tapauksessa argumentti lainausmerkkeihin, mutta älä itse kaavaa.
  
    Haluatko lisätietoja **[Today](../functions/function-now-today-istoday.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?

### <a name="show-data-in-a-gallery"></a>Tietojen näyttäminen valikoimassa
Tässä toimenpiteessä luot kokoelman, jonka nimi on **KaupunkienVäkiluvut**. Se sisältää tietoja Euroopan kaupunkien väkiluvuista. Seuraavaksi näytät tiedot kolme selitettä sisältävässä valikoimassa ja määrität, minkä tyyppistä tietoa kukin selite näyttää.

1. Lisää painike ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **ClearCollect(KaupunkienVäkiluvut, {Kaupunki:"Lontoo", Maa:"Yhdistynyt kuningaskunta", Väkiluku:8615000}, {Kaupunki:"Berliini", Maa:"Saksa", Väkiluku:3562000}, {Kaupunki:"Madrid", Maa:"Espanja", Väkiluku:3165000}, {Kaupunki:"Rooma", Maa:"Italia", Väkiluku:2874000}, {Kaupunki:"Pariisi", Maa:"Ranska", Väkiluku:2273000}, {Kaupunki:"Hampuri", Maa:"Saksa", Väkiluku:1760000}, {Maa:"Barcelona", Maa:"Espanja", Väkiluku:1602000}, {Kaupunki:"München", Maa:"Saksa", Väkiluku:1494000}, {Kaupunki:"Milano", Maa:"Italia", Väkiluku:1344000})**
2. Paina F5-painiketta, valitse painike ja paina sitten ESC-näppäintä.
3. Lisää tekstivalikoima ja määritä sen **[Items](properties-core.md)**-ominaisuuden arvoksi **KaupunkienVäkiluvut**.
   
    Kun valikoima on valittuna, oikeanpuoleisessa ruudussa näkyvät valikoimaa koskevat vaihtoehdot.
4. Määritä **Gallery1**-ruudussa, ylimmäksi luetteloksi **Väkiluku**, keskimmäiseksi luetteloksi **Kaupunki** ja alimmaiseksi luetteloksi **Maa**.


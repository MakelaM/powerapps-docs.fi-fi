---
title: 'Painike-ohjausobjekti: viittaus | Microsoft Docs'
description: Painike-ohjausobjektin tiedot, mukaan lukien ominaisuudet ja esimerkit
author: fikaradz
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: a5d818bf12bafaa5c557afae1d93b6ba0a6a7d2f
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34803439"
---
# <a name="button-control-in-powerapps"></a>Painike-ohjausobjekti PowerAppsissa
Ohjausobjekti, jota käyttäjä voi napsauttaa tai napauttaa sovelluksen toimintojen käyttämiseksi.

## <a name="description"></a>Kuvaus
Määritä **Painike**-ohjausobjektin **[OnSelect](properties-core.md)**-ominaisuudeksi yhden tai useamman kaavan suorittaminen, kun käyttäjä napsauttaa tai napauttaa ohjausobjektia.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[Text](properties-core.md)**  – Teksti, joka näytetään ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

## <a name="additional-properties"></a>Lisäominaisuudet
**[Align](properties-text.md)**  – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**AutoDisableOnSelect** – Poistaa ohjausobjektin automaattisesti käytöstä **OnSelect**-toiminnon suorittamisen ajaksi.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Väri](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Font](properties-text.md)**  – Tekstin ulkoasussa käytettävän fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin paksuus: **lihavoitu**, **puolilihavoitu**, **normaali** tai **ohuempi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun hiiren kohdistin on kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)**  – Ilmaisee, onko ohjausobjektin teksti kursivoitu.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**Pressed** – *Tosi*, kun ohjausobjektia painetaan, muulloin *epätosi*.

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

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti alleviivattu.

**[VerticalAlign](properties-text.md)** – Ohjausobjektin tekstin sijainti suhteessa ohjausobjektin pystysuoraan keskikohtaan.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Aiheeseen liittyvät funktiot
**[Navigate( *ScreenName*, *ScreenTransitionValue* )](../functions/function-navigate.md)**

## <a name="examples"></a>Esimerkkejä
### <a name="add-a-basic-formula-to-a-button"></a>Peruskaavan lisääminen painikkeeseen
1. Lisää **[Tekstisyöte](control-text-input.md)**-ohjausobjekti ja anna sille nimi **Source**.
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **Painike**-ohjausobjekti, määritä sen **[Text](properties-core.md)**-ominaisuudeksi ”Lisää” ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **UpdateContext({Total:Total + Value(Source.Text)})**
   
    Haluatko lisätietoja **[UpdateContext](../functions/function-updatecontext.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
3. Lisää **[Nimi](control-text-box.md)**-ohjausobjekti, aseta sen **[Text](properties-core.md)**-ominaisuudeksi **Total** ja paina **F5**-näppäintä.
4. Poista oletusteksti **Source**-kohdasta, kirjoita siihen numero ja sitten napsauta tai napauta **Lisää**.
   
    **[Nimi](control-text-box.md)**-ohjausobjekti näyttää kirjoittamasi numeron.
5. Poista numero **Source**-kohdasta, kirjoita siihen toinen numero ja napsauta tai napauta sitten **Lisää**.
   
    **[Nimi](control-text-box.md)**-ohjausobjekti näyttää kahden kirjoittamasi numeron summan.
6. (valinnainen) Toista edellinen vaihe vähintään yhden kerran.
7. Voit palata oletustyötilaan painamalla ESC-näppäintä (tai napsauttamalla oikean yläkulman sulkemiskuvaketta).

### <a name="configure-a-button-with-multiple-formulas"></a>Usean kaavan määrittäminen painikkeeseen
Lisää kaava, joka tyhjentää **Tekstisyöte**-ohjausobjektin syöttöjen välillä.

1. Aseta **Source**-kohdan **[HintText](control-text-input.md)**-ominaisuudeksi ”Syötä numero”.
2. Määritä **Lisää**-kohdan **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **UpdateContext({Total:Total + Value(Source.Text)});<br>UpdateContext({ClearInput: ""})**
   
    > [!NOTE]
> Erota kaavat toisistaan puolipisteellä ”**;**”.
3. Määritä **Source**-kohdan **[Default](properties-core.md)**-ominaisuudeksi **ClearInput**.
4. Paina **F5** ja testaa sovellusta laskemalla numeroita yhteen.

### <a name="add-another-button-to-reset-the-total"></a>Toisen painikkeen lisääminen kokonaismäärän nollaamiseksi
Lisää toinen painike, joka tyhjentää kokonaismäärän laskutoimitusten välillä.

1. Lisää uusi **Painike**-ohjausobjekti, määritä sen **[Text](properties-core.md)**-ominaisuudeksi ”Tyhjennä” ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **UpdateContext({Total:0})**
2. Paina **F5**, laske useita numeroita yhteen ja sitten tyhjennä kokonaismäärä napsauttamalla tai napauttamalla **Tyhjennä**.

### <a name="change-a-buttons-appearance"></a>Painikkeen ulkoasun muuttaminen
#### <a name="change-a-buttons-shape"></a>Painikkeen muodon muuttaminen
PowerApps luo oletuksena nelikulmion muotoisen **Painike**-ohjausobjektin, jonka kulmat on pyöristetty. Voit tehdä **Painike**-ohjausobjektiin perustason muokkauksia säätämällä sen ominaisuuksia **[Height](properties-size-location.md)**, **[Width](properties-size-location.md)** ja **[Radius](properties-size-location.md)**.

> [!NOTE]
> [Kuvakkeet ja muodot](control-shapes-icons.md) mahdollistavat monipuolisen muokkaamisen, ja niillä voidaan suorittaa joitakin **Painike**-ohjausobjektien perustoimintoja. **[Kuvakkeilla ja muodoilla](control-shapes-icons.md)** ei kuitenkaan ole **[Text](properties-core.md)**-ominaisuutta.

1. Lisää **Painike**-ohjausobjekti ja aseta sen **[Height](properties-size-location.md)**- ja **[Width](properties-size-location.md)**-ominaisuuksiksi **300**, jotta painikkeesta tulee suuri ja neliönmuotoinen.
2. Muuta kulmien pyöristystä muokkaamalla arvoja **[RadiusTopLeft](properties-size-location.md)**, **[RadiusTopRight](properties-size-location.md)**, **[RadiusBottomLeft](properties-size-location.md)** ja **[RadiusBottomRight](properties-size-location.md)**. Tässä on esimerkkejä eri muodoista, joiden aloituspisteenä on 300 x 300 -kokoinen neliönmuotoinen painike:
   
   * Luo ympyrä asettamalla kaikille neljälle **[Radius](properties-size-location.md)**-muuttujalle arvo **150**.
   * Luo lehden muotoinen **Painike** asettamalla ominaisuuksien **[RadiusTopLeft](properties-size-location.md)** ja **[RadiusBottomRight](properties-size-location.md)** arvoksi **300**.
   * Luo välilehden muotoinen painike asettamalla ominaisuuksien **[RadiusTopLeft](properties-size-location.md)** ja **[RadiusTopRight](properties-size-location.md)** arvoksi **300**ja ominaisuuksien **[RadiusBottomLeft](properties-size-location.md)** ja **[RadiusBottomRight](properties-size-location.md)** arvoksi **100**.

#### <a name="change-a-buttons-color-when-you-hover-over-it"></a>Painikkeen värin muuttaminen, kun hiiren on sen päällä
Oletuksena **Painike**-ohjausobjektin täyttöväri himmenee 20 %, kun hiiren osoitin on sen päällä. Voit muuttaa tätä muokkaamalla **[HoverFill](properties-color-border.md)**-ominaisuutta, joka käyttää **[ColorFade](../functions/function-colors.md)**-funktiota. Jos asetat **[ColorFade](../functions/function-colors.md)**-kaavaksi positiivisen prosenttiluvun, väri muuttuu vaaleammaksi osoittimen ollessa sen päällä, kun taas negatiivinen prosenttiluku tekee siitä tummemman.

* Muuta jonkin luomasi painikkeen **[HoverFill](properties-color-border.md)**-ominaisuuden **[ColorFade](../functions/function-colors.md)**-prosenttimäärää ja tarkastele tuloksia.

Voit myös määrittää **Painike**-ohjausobjektin värin asettamalla sen **[HoverFill](properties-color-border.md)**-ominaisuudeksi kaavan, joka sisältää **[ColorFade](../functions/function-colors.md)**-funktion sijaan **[ColorValue](../functions/function-colors.md)**-funktion, esimerkiksi **ColorValue("Red")**.

> [!NOTE]
> Väri voi olla mikä tahansa CSS-värimääritys, joko nimi tai heksadesimaaliarvo.

* Korvaa jonkin luomasi painikkeen **[ColorFade](../functions/function-colors.md)**-funktio **[ColorValue](../functions/function-colors.md)**-funktiolla ja tarkastele tuloksia.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
* [Tavalliset värikontrastivaatimukset](../accessible-apps-color.md) pätevät.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[Teksti](properties-core.md)** on oltava käytössä.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.
 
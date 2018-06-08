---
title: 'Lisää kuva -ohjausobjekti: viitetiedot | Microsoft Docs'
description: Tietoja Lisää kuva -ohjausobjektista, mukaan lukien ominaisuudet ja esimerkkejä
author: fikaradz
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: e20d76c9e8913197d4b59380a5f91dea3851c959
ms.sourcegitcommit: 7354a0c61578fcc0b9965bf557b9d7c553c73e96
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/05/2018
ms.locfileid: "34803531"
---
# <a name="add-picture-control-in-powerapps"></a>Lisää kuva -ohjausobjekti PowerAppsissa
Ottaa valokuvan tai lataa kuvat paikallisesta laitteesta.

## <a name="description"></a>Kuvaus
Tämän ohjausobjektin avulla käyttäjät voivat ottaa kuvia tai ladata kuvatiedostoja laitteestaan ja päivittää tietolähteen tällä sisällöllä. Mobiililaitteessa käyttäjälle esitetään laitteen vaihtoehtojen valintaikkuna, jossa voidaan valita, otetaanko valokuva vai käytetäänkö jo käytettävissä olevaa valokuvaa.

Tämä ohjausobjekti on ryhmitelty ohjausobjekti, joka sisältää kaksi ohjausobjektia: **Kuva** ja **Lisää mediasisältöä -painike**. **Kuvan** ohjausobjekti näyttää ladatun kuvan tai paikkamerkin, jos kuvaa ei ole ladattu. **Lisää mediasisältöä -painike** ohjaa lataamaan kuvan.

Katso [kuvan ohjausobjektin viittauksesta](control-image.md) **kuvan** ominaisuudet.

## <a name="add-media-button-properties"></a>Lisää mediasisältöä -painikkeen ominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi. Kuvan lisäämisen tarkoitus tulee kuvata.

**[Align](properties-text.md)** – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**ChangePictureText** – teksti, joka näkyy painikkeessa, kun kuva on ladattu.

**[Color](properties-color-border.md)** – Ohjausobjektin tekstin väri.

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**), vai onko ominaisuus poistettu käytöstä (**Disabled**).

**Error** – Jos kuvaa ladatessa esiintyy ongelma, tämä ominaisuus sisältää tarvittavan virhesanoman.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin paksuus: **lihavoitu**, **puolilihavoitu**, **normaali** tai **ohuempi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun hiiren kohdistin on kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**Tietoväline** – Ääni- tai video-ohjausobjektin toistaman leikkeen tunniste.

**[OnChange](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi käyttämällä liukusäädintä).

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[Täyttö](properties-size-location.md)** – Tuonti- tai vientipainikkeen tekstin ja painikkeen reunojen välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Reset](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**[Size](properties-text.md)** – Ohjausobjektissa näytettävän tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Text](properties-core.md)** – Teksti, joka näkyy painikkeessa, kun kuvaa ei ole ladattu.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti alleviivattu.

**[VerticalAlign](properties-text.md)** – Ohjausobjektin tekstin sijainti suhteessa ohjausobjektin pystysuoraan keskikohtaan.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="examples"></a>Esimerkkejä
### <a name="add-images-to-an-image-gallery-control"></a>Lisää kuvia Kuvavalikoima-ohjausobjektiin
1. Lisää **Lisää kuva** -ohjausobjekti ja napsauta sitä sen jälkeen kolmesti.
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Napsauta tai napauta **Avaa**-valintaikkunassa kuvatiedostoa ja valitse sitten **Avaa**.
3. Lisää **[Painike](control-button.md)**-ohjausobjekti, siirrä se **Lisää kuva** -ohjausobjektin alle ja määritä **[Painike](control-button.md)**-ohjausobjektin **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Collect(MyPix, AddMediaButton1.Media)**
   
    Haluatko lisätietoja **[Collect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
4. Lisää **Kuvavalikoima**-ohjausobjekti ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi **MyPix**.
5. Paina F5-näppäintä ja napsauta tai napauta sitten **[Painike](control-button.md)**-ohjausobjektia.
   
    **Lisää kuva** -ohjausobjektilta tuleva kuva näkyy **Kuvavalikoima**-ohjausobjektissa. Jos kuvasi kuvasuhde ei ole sama kuin **Kuvavalikoima**-ohjausobjektissa olevalla **[Kuva](control-image.md)**-ohjausobjektilla, määritä **[Kuva](control-image.md)**-ohjausobjektin **[ImagePosition](properties-visual.md)**-ominaisuudeksi **Sovita**.
6. Napsauta tai napauta **Lisää kuva** -ohjausobjektia, napsauta tai napauta toista kuvatiedostoa, napsauta tai napauta kohtaa **Avaa** ja napsauta tai napauta sitten lisäämääsi **[Painike](control-button.md)**-ohjausobjektia.
   
    Toinen kuva tulee näkyviin **Kuvavalikoima**-ohjausobjektiin.
7. (valinnainen) Toista edellinen vaihe yhden tai useamman kerran ja palaa sitten oletustyötilaan painamalla ESC-näppäintä.

Tallenna kuvat paikallisesti **[SaveData](../functions/function-savedata-loaddata.md)**-funktiolla tai päivitä tietolähde **[Patch](../functions/function-patch.md)**-funktiolla.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
Samat ohjeet koskevat sekä **[Painiketta](control-button.md)** että **[Kuvaa](control-image.md)**. Huomioi lisäksi seuraavat asiat:

### <a name="color-contrast"></a>Värikontrasti
* **Lisää mediasisältö -painikkeen** tekstin ja taustan välisen kontrastin on oltava riittävän suuri. Koska ladatussa kuvassa voi olla eri värejä, käytä läpinäkymätöntä **[täyttöä](properties-color-border.md)** **Lisää mediasisältöä -painikkeessa** yhtenäisen kontrastin varmistamiseksi.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **Lisää mediasisältö -painikkeessa** on oltava **teksti** ja **ChangePictureText**, jotka kehottavat käyttäjää lisäämään tai vaihtamaan kuvan.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **Lisää mediasisältöä -painikkeen** **[TabIndex](properties-accessibility.md)**-arvon on oltava nolla tai suurempi, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* **Lisää mediasisältöä -painikkeessa** on oltava selvästi näkyvät kohdistuksen ilmaisimet. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.
 
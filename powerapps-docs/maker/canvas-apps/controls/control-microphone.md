---
title: 'Mikrofoni-ohjausobjekti: viittaus | Microsoft Docs'
description: Mikrofoni-ohjausobjektin tietoja, ominaisuuksia ja esimerkkejä
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
ms.openlocfilehash: 302c2fad419146f03fe47e25b8a7563564ee7e2d
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61543949"
ms.PowerAppsDecimalTransform: true
---
# <a name="microphone-control-in-powerapps"></a>Mikrofoni-ohjausobjekti PowerAppsissa
Ohjausobjekti, jonka avulla sovelluksen käyttäjät voivat tallentaa ääniä laitteestaan.

## <a name="description"></a>Kuvaus
Sovelluksen käyttäjät voivat tehdä äänitallenteita, jos laitteessa, jossa sovellus on käynnissä, on mikrofoni.

Äänen tallennukseen käytetään Androidissa 3GP-muotoa, iOS-käyttöjärjestelmässä AAC-muotoa ja verkkoselaimissa OGG-muotoa.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**Mikrofoni** – Sovelluksen käyttämän mikrofonin numerotunnus, jos laitteessa on useampi kuin yksi mikrofoni.

**OnStop** – Miten sovellus reagoi, kun käyttäjä lopettaa taltioimisen mikrofoni-ohjausobjektilla.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi. Mikrofonin tarkoitus tulee kuvata.

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

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun hiiren kohdistin on kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun käyttäjä pitää hiiren osoitinta sen kohdalla.

**[Kuva](properties-visual.md)** – Sen kuvan nimi, joka näkyy kuvan, äänen tai mikrofonin ohjausobjektissa.

**[ImagePosition](properties-visual.md)** – Näytössä olevan kuvan tai ohjausobjektin asettelu (**Täyttö**, **Sovita**, **Stretch**, **Vierekkäin** tai **Keskitä**), jos se ei ole saman kokoinen kuin kuva.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnStart** – Miten sovellus reagoi, kun käyttäjä aloittaa tallentamisen mikrofoni-ohjausobjektilla.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Reset](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Patch**( *DataSource*; *BaseRecord*; *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Esimerkki
### <a name="add-sounds-to-a-custom-gallery-control"></a>Lisää ääniä mukautettuun valikoima-ohjausobjektiin
1. Lisää **Mikrofoni**, anna sen nimeksi **MyMic** ja määritä sen **OnStop**-ominaisuudeksi tämä kaava:<br>
   **Collect(MySounds; MyMic.Audio)**

    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?

    Haluatko lisätietoja **[Kerää](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
2. Lisää **Mukautettu valikoima** -ohjausobjekti, siirrä se kohdan **MyMic** alle ja määritä **[Kohteet](properties-core.md)**-ominaisuudeksi **Mukautettu valikoima** -ohjausobjektissa **MySounds**.
3. Lisää **Mukautettu valikoima** - ohjausobjektin mallissa **[Ääni](control-audio-video.md)**-ohjausobjekti ja määritä sen **Media**-ominaisuudeksi  **ThisItem.Url**.
4. Paina F5-näppäintä, aloita taltiointi napsauttamalla tai napauttamalla **MyMic** ja lopeta taltiointi napsauttamalla tai napauttamalla sitä uudelleen.
5. Toista taltiointi napsauttamalla tai napauttamalla **Mukautettu valikoima** -ohjausobjektin toistopainiketta **[Ääni](control-audio-video.md)**-ohjausobjektissa.
6. Lisää niin monta taltiointia kuin haluat ja palaa sitten oletustyötilaan painamalla Esc.
7. (valinnainen) Lisää **Mukautettu valikoima** -ohjausobjektin mallissa **[Painike](control-button.md)**-ohjausobjekti, määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi **Remove(MySounds; ThisItem)**, paina F5-näppäintä ja poista sitten taltiointi napsauttamalla tai napauttamalla vastaavaa **Painike**-ohjausobjektia.

Voit tallentaa taltioinnit paikallisesti **[SaveData](../functions/function-savedata-loaddata.md)**-funktiolla tai päivittää tietolähteen **[Ohjelmakorjaus](../functions/function-patch.md)**-funktiolla.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
Ohjeet ovat samat kuin **[Painike](control-button.md)**-ohjausobjektille, sillä **Mikrofoni** on erityinen painike. Huomioi lisäksi seuraavat asiat:

### <a name="audio-alternatives"></a>Vaihtoehdot äänelle
* Harkitse vaihtoehtoisen syöttötavan lisäämistä puhevammaisille käyttäjille tai käyttäjille, joilla ei ole mikrofonia. Esimerkiksi **[Tekstisyöte](control-text-input.md)**, jotta käyttäjät voivat kirjoittaa tekstiä.

### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **[Kuva](properties-visual.md)** ja painikkeen teksti ja kuvake (jos sellainen on)

Tämä tulee [värikontrastin vakiovaatimusten lisäksi](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

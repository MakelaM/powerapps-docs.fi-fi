---
title: Väri- ja reunaominaisuudet | Microsoft Docs
description: Viitetietoja ominaisuuksista, kuten BorderColor, HoverBorderColor ja PressedBorderColor
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 2f17dd975a5b8320f4b67688ab986c4e8cc98514
ms.sourcegitcommit: 21163a6d77b784f4864fce4695776c9b4652cb29
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/26/2019
ms.locfileid: "66225153"
---
# <a name="color-and-border-properties-in-powerapps"></a>Väri- ja reunaominaisuudet PowerAppsissa

## <a name="overview"></a>Yleiskatsaus

Määritä ohjausobjektin tyyli sen perusteella, miten käyttäjä käsittelee sitä.

Voit määrittää värit monella tavalla:

- [**Väri** ](../functions/function-colors.md) luettelointi: Määritä väri nimet limittäisiä tyylejä, kuten näissä esimerkeissä:

  - **Color.Red**
  - **Color.Indigo**

- [**ColorValue** ](../functions/function-colors.md) funktio: Määritä tekstimerkkijonoa, kuten värien nimiä CSS-ja heksadesimaaleina koodin notation (**#**), kuten näissä esimerkeissä:

  - **ColorValue (”erittäin Vaalea sininen”)**
  - **ColorValue( "#ff00ff" )**

- [**ColorFade** ](../functions/function-colors.md) funktio: Määritä, miten häivytetyn väri on täysin musta (-100 %) Jos haluat valkoinen täysin (100 %), kuten seuraavassa esimerkissä:

  - **ColorFade (Color.Red, 50 %)**

- [**RGBA** ](../functions/function-colors.md) funktio: Määritä 0 – 255 värin punaisen, vihreän ja sinisen osista ja alfa kanavan 0: sta (täysin läpinäkyvä) 100-prosentin (täysin läpinäkymätön), kuten seuraavassa esimerkissä:

  - **RGBA (255, 0, 255, 25 %)**

Väri-ominaisuuksia myös viitata väri muita ominaisuuksia. Esimerkiksi **Label.PressedColor** tyyppieditori voidaan määrittää kaavaan **Label1.Color**, automaattisesti yhden ominaisuuden muutokseen toiseen tyylimäärityksen mukainen.

## <a name="normal"></a>Tavallinen

Nämä ominaisuudet ovat voimassa normaalisti, kun käyttäjä ei käsittele ohjausobjektia.

**BorderColor** – Ohjausobjektin reunan väri.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Ääni](control-audio-video.md)**, **[painike](control-button.md)**, **[Kamera](control-camera.md)**, **[Kortti](control-card.md)**, **[Valintaruutu](control-check-box.md)**, **[Pylväskaavio](control-column-line-chart.md)**, **[Päivämäärävalitsin](control-date-picker.md)**, **[Näytetty lomake](control-form-detail.md)**, **[Avattava valikko](control-drop-down.md)**, **[Muokattu lomake](control-form-detail.md)**, **[Vienti](control-export-import.md)**, **[Valikoima](control-gallery.md)**, **[HTML-teksti](control-html-text.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Viivakaavio](control-column-line-chart.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[Kynän syöte](control-pen-input.md)**, **[Ympyräkaavio](control-pie-chart.md)**, **[Valintanappi](control-radio.md)**, **[Luokitus](control-rating.md)**, **[Liukusäädin](control-slider.md)**, **[Tekstisyöte](control-text-input.md)**, **[Ajastin](control-timer.md)**, **[Vaihda](control-toggle.md)** ja **[Video](control-audio-video.md)**.

**BorderStyle** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Ääni](control-audio-video.md)**, **[painike](control-button.md)**, **[Kamera](control-camera.md)**, **[Kortti](control-card.md)**, **[Valintaruutu](control-check-box.md)**, **[Pylväskaavio](control-column-line-chart.md)**, **[Päivämäärävalitsin](control-date-picker.md)**, **[Näytetty lomake](control-form-detail.md)**, **[Avattava valikko](control-drop-down.md)**, **[Muokattu lomake](control-form-detail.md)**, **[Vienti](control-export-import.md)**, **[Valikoima](control-gallery.md)**, **[HTML-teksti](control-html-text.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Viivakaavio](control-column-line-chart.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[Kynän syöte](control-pen-input.md)**, **[Ympyräkaavio](control-pie-chart.md)**, **[Valintanappi](control-radio.md)**, **[Luokitus](control-rating.md)**, **[Liukusäädin](control-slider.md)**, **[Tekstisyöte](control-text-input.md)**, **[Ajastin](control-timer.md)**, **[Vaihda](control-toggle.md)** ja **[Video](control-audio-video.md)**.

**BorderThickness** – Ohjausobjektin reunan paksuus.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Ääni](control-audio-video.md)**, **[painike](control-button.md)**, **[Kamera](control-camera.md)**, **[Kortti](control-card.md)**, **[Valintaruutu](control-check-box.md)**, **[Pylväskaavio](control-column-line-chart.md)**, **[Päivämäärävalitsin](control-date-picker.md)**, **[Näytetty lomake](control-form-detail.md)**, **[Avattava valikko](control-drop-down.md)**, **[Muokattu lomake](control-form-detail.md)**, **[Vienti](control-export-import.md)**, **[Valikoima](control-gallery.md)**, **[HTML-teksti](control-html-text.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Viivakaavio](control-column-line-chart.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[Kynän syöte](control-pen-input.md)**, **[Ympyräkaavio](control-pie-chart.md)**, **[Valintanappi](control-radio.md)**, **[Luokitus](control-rating.md)**, **[Liukusäädin](control-slider.md)**, **[Tekstisyöte](control-text-input.md)**, **[Ajastin](control-timer.md)**, **[Vaihda](control-toggle.md)** ja **[Video](control-audio-video.md)**.

**Väri** – Ohjausobjektin tekstin väri.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Kaaviosarake](control-column-line-chart.md)**, **[Päivämäärän valitsin](control-date-picker.md)**, **[Avattava luettelo](control-drop-down.md)**, **[Vienti](control-export-import.md)**, **[HTML-teksti](control-html-text.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Viivakaavio](control-column-line-chart.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[Kynän syöte](control-pen-input.md)**, **[Ympyräkaavio](control-pie-chart.md)**, **[Valintanappi](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

**Täyttö** – Ohjausobjektin taustaväri.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Ääni](control-audio-video.md)**, **[Painike](control-button.md)**, **[Kortti](control-card.md)**, **[Valintaruutu](control-check-box.md)**, **[Päivämäärävalitsin](control-date-picker.md)**, **[Näytetty lomake](control-form-detail.md)**, **[Avattava valikko](control-drop-down.md)**, **[Muokattu lomake](control-form-detail.md)**, **[Vienti](control-export-import.md)**, **[Valikoima](control-gallery.md)**, **[HTML-teksti](control-html-text.md)**, **[Kuvake](control-shapes-icons.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Otsikko](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[Kynän syöte](control-pen-input.md)**, **[Valintapainike](control-radio.md)**, **[Luokitus](control-rating.md)**, **[Näyttö](control-screen.md)**, **[Muoto](control-shapes-icons.md)**, **[Tekstisyöte](control-text-input.md)**, **[Ajastin](control-timer.md)**, **[Vaihda](control-toggle.md)** ja **[Video](control-audio-video.md)**.

## <a name="focused"></a>Kohdistettu

Nämä ominaisuudet ovat käytössä, kun ohjausobjekti on kohdistettuna.

**FocusedBorderColor** – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettuna.

**FocusedBorderThickness** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettuna.

- Nämä ominaisuudet koskevat ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Liitteet](control-attachments.md)**, **[Ääni](control-audio-video.md)**, **[Painike](control-button.md)**, **[Kamera](control-camera.md)**, **[Valintaruutu](control-check-box.md)**, **[Yhdistelmäruutu](control-combo-box.md)**, **[Päivämäärän valitsin](control-date-picker.md)**, **[Avattava](control-drop-down.md)**, **[Vie](control-export-import.md)**, **[Valikoima](control-gallery.md)**, **[Kuvake](control-shapes-icons.md)**, **[Kuva](control-image.md)**, **[Tuo](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[Radio](control-radio.md)**, **[Luokitus](control-rating.md)**, **[Muoto](control-shapes-icons.md)**, **[Liukusäädin](control-slider.md)**, **[Tekstisyöte](control-text-input.md)**, **[Ajastin](control-timer.md)**, **[Vaihda](control-toggle.md)** ja **[Video](control-audio-video.md)**.

## <a name="disabled"></a>Poistettu käytöstä

Nämä ominaisuudet ovat käytössä, kun ohjausobjekti on poistettu käytöstä.  Ohjausobjekti voidaan poistaa käytöstä, jos **[Poistettu käytöstä](properties-core.md)** -ominaisuuden arvo on *true*.

**DisabledBorderColor** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Pylväskaavio](control-column-line-chart.md)**, **[Päivämäärävalitsin](control-date-picker.md)**, **[Avattava valikko](control-drop-down.md)**, **[Vienti](control-export-import.md)**, **[HTML-teksti](control-html-text.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Otsikko](control-text-box.md)**, **[Viivakaavio](control-column-line-chart.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[Ympyräkaavio](control-pie-chart.md)**, **[Valitsinpainike](control-radio.md)**, **[Liukusäädin](control-slider.md)**, **[Tekstisyöte](control-text-input.md)**, **[Ajastin](control-timer.md)**, ja **[Vaihda](control-toggle.md)**.

**DisabledColor** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Päivämäärävalitsin](control-date-picker.md)**, **[Avattava valikko](control-drop-down.md)**, **[Vienti](control-export-import.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[Valintapainike](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

**DisabledFill** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-ominaisuuden arvoksi on asetettu **Poistettu käytöstä**.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Päivämäärävalitsin](control-date-picker.md)**, **[Avattava valikko](control-drop-down.md)**, **[Vienti](control-export-import.md)**, **[HTML-teksti](control-html-text.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[Valintapainike](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

## <a name="hover"></a>Hiiren osoittimen pitäminen päällä

Nämä ominaisuudet ovat käytössä, kun käyttäjä pitää hiiren osoitinta ohjausobjektin päällä.

**HoverBorderColor** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Pylväskaavio](control-column-line-chart.md)**, **[Avattava valikko](control-drop-down.md)**, **[Vienti](control-export-import.md)**, **[HTML-teksti](control-html-text.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Viivakaavio](control-column-line-chart.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[Ympyräkaavio](control-pie-chart.md)**, **[Liukusäädin](control-slider.md)**, **[Tekstisyöte](control-text-input.md)**, **[Ajastin](control-timer.md)** ja **[Vaihda](control-toggle.md)**.

**HoverColor** – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Avattava valikko](control-drop-down.md)**, **[Vienti](control-export-import.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[Valintapainike](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

**HoverFill** – Ohjausobjektin taustaväri, kun käyttäjä pitää hiiren osoitinta sen päällä.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Avattava valikko](control-drop-down.md)**, **[Vienti](control-export-import.md)**, **[Kuvake](control-shapes-icons.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Valintaruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[Valintapainike](control-radio.md)**, **[Muoto](control-shapes-icons.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

## <a name="pressed"></a>Painettu

Nämä ominaisuudet ovat käytössä, kun painiketta tai kuvan ohjausobjektia painetaan.

**PressedBorderColor** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Pylväskaavio](control-column-line-chart.md)**, **[Avattava valikko](control-drop-down.md)**, **[Vienti](control-export-import.md)**, **[Kuvake](control-shapes-icons.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Viivakaavio](control-column-line-chart.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[Ympyräkaavio](control-pie-chart.md)**, **[Muoto](control-shapes-icons.md)**, **[Liukusäädin](control-slider.md)**, **[Tekstisyöte](control-text-input.md)**, **[Ajastin](control-timer.md)** ja **[Vaihda](control-toggle.md)**.

**PressedColor** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Avattava valikko](control-drop-down.md)**, **[Vienti](control-export-import.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[Valintapainike](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

**PressedFill** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

- Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Avattava valikko](control-drop-down.md)**, **[Vienti](control-export-import.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Selite](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[Valintapainike](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

## <a name="selection"></a>Valinta

Nämä ominaisuudet ovat käytössä, kun käyttäjä valitsee kohteen ohjausobjektissa.

**SelectionColor** – Luettelon valitun kohteen tai kohteiden tekstin väri tai kynä-ohjausobjektin valintatyökalun väri.

- Koskee ohjausobjekteja **[Avattava valikko](control-drop-down.md)**, **[Luetteloruutu](control-list-box.md)** ja **[Kynän syöte](control-pen-input.md)**.

**SelectionFill** – Luettelon valitun kohteen tai kohteiden taustaväri tai kynä-ohjausobjektin valitun alueen väri.

- Koskee ohjausobjekteja **[Avattava valikko](control-drop-down.md)** ja **[Luetteloruutu](control-list-box.md)**.
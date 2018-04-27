---
title: Tärkeimmät ominaisuudet | Microsoft Docs
description: Disabled-, Visible- ja ReadOnly-ominaisuuksien viitetiedot
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: gregli
ms.openlocfilehash: cad53141d6896ad71caaca77b7bf07fee2ac0600
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/23/2018
---
# <a name="core-properties-in-powerapps"></a>PowerAppsin tärkeimmät ominaisuudet
Määritä, voiko käyttäjä nähdä ohjausobjektin ja olla sen kanssa vuorovaikutuksessa.

### <a name="properties"></a>Ominaisuudet
**Default** – Ohjausobjektin alkuarvo, ennen kuin käyttäjä on muuttanut sitä.

* Koskee ohjausobjekteja **[kortti](control-card.md)**, **[valintaruutu](control-check-box.md)**, **[avattava valikko](control-drop-down.md)**, **[valikoima](control-gallery.md)**, **[luetteloruutu](control-list-box.md)**, **[valintanappi](control-radio.md)**, **[luokitus](control-rating.md)**, **[liukusäädin](control-slider.md)**, **[tekstisyöte](control-text-input.md)** ja **[vaihtopainike](control-toggle.md)**.

**DelayOutput** – Määritetty arvo on tosi, mikä viivästyttää toimintoa tekstinsyötön aikana.

* Koskee ohjausobjekteja **[tekstisyöte](control-text-input.md)** ja **[kortti](control-card.md)**.

**DisplayMode** – Arvo voi olla **Muokkaa, Näytä** tai **Poistettu käytöstä**. Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Muokkaa**) tai vain tarkastella tietoja (**Näytä**) vai onko ominaisuus kokonaan poissa käytöstä (**Poistettu käytöstä**).  **Näytä**-tilassa syöteohjausobjektit, kuten **[tekstisyöte](control-text-input.md)**,  **[avattava valikko](control-drop-down.md)** ja **[päivämäärävalitsin](control-date-picker.md)** näyttävät vain tekstiarvon. Vuorovaikutteisia elementtejä tai muotoiluja ei hahmonneta.  Tämän vuoksi ne soveltuvat hyvin näytettäväksi lomakkeissa tai luettavassa tulosteessa.

* Koskee ohjausobjekteja **[lisää kuva](control-add-picture.md)**, **[ääni](control-audio-video.md)**, **[painike](control-button.md)**, **[kamera](control-camera.md)**, **[valintaruutu](control-check-box.md)**, **[pylväskaavio](control-column-line-chart.md)**, **[päivämäärävalitsin](control-date-picker.md)**, **[avattava valikko](control-drop-down.md)**, **[vie](control-export-import.md)**, **[valikoima](control-gallery.md)**, **[HTML-teksti](control-html-text.md)**, **[kuvake](control-shapes-icons.md)**, **[kuva](control-image.md)**, **[tuo](control-export-import.md)**, **[selite](control-text-box.md)**, **[viivakaavio](control-column-line-chart.md)**, **[luetteloruutu](control-list-box.md)**, **[mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[kynäsyöte](control-pen-input.md)**, **[ympyräkaavio](control-pie-chart.md)**, **[valintanappi](control-radio.md)**, **[luokitus](control-rating.md)**, **[muoto](control-shapes-icons.md)**, **[liukusäädin](control-slider.md)**, **[tekstisyöte](control-text-input.md)**, **[ajastin](control-timer.md)**, **[vaihtopainike](control-toggle.md)** ja **[video](control-audio-video.md)**.

**Items** – Ohjausobjektissa, kuten valikoimassa, luettelossa tai kaaviossa näytetyn tiedon lähde.

* Koskee ohjausobjekteja **[pylväskaavio](control-column-line-chart.md)**, **[avattava valikko](control-drop-down.md)**, **[valikoima](control-gallery.md)**, **[viivakaavio](control-column-line-chart.md)**, **[luetteloruutu](control-list-box.md)**, **[ympyräkaavio](control-pie-chart.md)** ja **[valintanappi](control-radio.md)**.

**OnChange** – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

* Koskee ohjausobjekteja **[lisää kuva](control-add-picture.md)**, **[avattava valikko](control-drop-down.md)**, **[luetteloruutu](control-list-box.md)**, **[valintanappi](control-radio.md)**, **[luokitus](control-rating.md)**, **[liukusäädin](control-slider.md)**, **[tekstisyöte](control-text-input.md)** ja **[vaihtopainike](control-toggle.md)**.

**OnSelect** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

* Koskee ohjausobjekteja **[lisää kuva](control-add-picture.md)**, **[painike](control-button.md)**, **[kamera](control-camera.md)**, **[valintaruutu](control-check-box.md)**, **[pylväskaavio](control-column-line-chart.md)**, **[päivämäärävalitsin](control-date-picker.md)**, **[avattava valikko](control-drop-down.md)**, **[vie](control-export-import.md)**, **[HTML-teksti](control-html-text.md)**, **[kuvake](control-shapes-icons.md)**, **[kuva](control-image.md)**, **[tuo](control-export-import.md)**, **[selite](control-text-box.md)**, **[viivakaavio](control-column-line-chart.md)**, **[luetteloruutu](control-list-box.md)**, **[mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[kynäsyöte](control-pen-input.md)**, **[ympyräkaavio](control-pie-chart.md)**, **[valintanappi](control-radio.md)**, **[luokitus](control-rating.md)**, **[muoto](control-shapes-icons.md)**, **[liukusäädin](control-slider.md)**, **[tekstisyöte](control-text-input.md)**, **[ajastin](control-timer.md)** ja **[vaihtopainike](control-toggle.md)**.

**Reset** – Palautuuko ohjausobjekti oletusarvoonsa.  Katso myös **[Reset](../functions/function-reset.md)**-funktio.

* Koskee ohjausobjekteja **[ääni](control-audio-video.md)**, **[valintaruutu](control-check-box.md)**, **[avattava valikko](control-drop-down.md)**, **[luetteloruutu](control-list-box.md)**, **[mikrofoni](control-microphone.md)**, **[valintanappi](control-radio.md)**, **[luokitus](control-rating.md)**, **[liukusäädin](control-slider.md)**, **[tekstisyöte](control-text-input.md)**, **[ajastin](control-timer.md)**, **[vaihtopainike](control-toggle.md)** ja **[video](control-audio-video.md)**.

**Text** – Teksti, joka näytetään ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

* Koskee ohjausobjekteja **[lisää kuva](control-add-picture.md)**, **[painike](control-button.md)**, **[valintaruutu](control-check-box.md)**, **[vie](control-export-import.md)**, **[tuo](control-export-import.md)**, **[selite](control-text-box.md)**, **[tekstisyöte](control-text-input.md)** ja **[ajastin](control-timer.md)**.

**Tooltip** – Ohjeteksti, joka ilmestyy näkyviin osoittimen ollessa ohjausobjektin päällä.

* Koskee ohjausobjekteja **[ääni](control-audio-video.md)**, **[painike](control-button.md)**, **[kamera](control-camera.md)**, **[valintaruutu](control-check-box.md)**, **[avattava valikko](control-drop-down.md)**, **[HTML-teksti](control-html-text.md)**, **[kuva](control-image.md)**, **[selite](control-text-box.md)**, **[luetteloruutu](control-list-box.md)**, **[mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[kynäsyöte](control-pen-input.md)**, **[valintanappi](control-radio.md)**, **[luokitus](control-rating.md)**, **[liukusäädin](control-slider.md)**, **[tekstisyöte](control-text-input.md)**, **[ajastin](control-timer.md)**, **[vaihtopainike](control-toggle.md)** ja **[video](control-audio-video.md)**.

**Value** – Syöteohjausobjektin arvo.

* Koskee ohjausobjekteja **[valintaruutu](control-check-box.md)**, **[valintanappi](control-radio.md)**, **[liukusäädin](control-slider.md)** ja **[vaihtopainike](control-toggle.md)**.

**Visible** – Määrittää, onko ohjausobjekti näkyvä vai piilotettu.

* Koskee ohjausobjekteja **[lisää kuva](control-add-picture.md)**, **[ääni](control-audio-video.md)**, **[painike](control-button.md)**, **[kamera](control-camera.md)**, **[kortti](control-card.md)**, **[valintaruutu](control-check-box.md)**, **[pylväskaavio](control-column-line-chart.md)**, **[päivämäärävalitsin](control-date-picker.md)**, **[näytä lomake](control-form-detail.md)**, **[avattava valikko](control-drop-down.md)**, **[muokkaa lomaketta](control-form-detail.md)**, **[vie](control-export-import.md)**, **[valikoima](control-gallery.md)**, **[HTML-teksti](control-html-text.md)**, **[kuvake](control-shapes-icons.md)**, **[kuva](control-image.md)**, **[tuo](control-export-import.md)**, **[selite](control-text-box.md)**, **[viivakaavio](control-column-line-chart.md)**, **[luetteloruutu](control-list-box.md)**, **[mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[kynäsyöte](control-pen-input.md)**, **[ympyräkaavio](control-pie-chart.md)**, **[valintanappi](control-radio.md)**, **[luokitus](control-rating.md)**, **[muoto](control-shapes-icons.md)**, **[liukusäädin](control-slider.md)**, **[tekstisyöte](control-text-input.md)**, **[ajastin](control-timer.md)**, **[vaihtopainike](control-toggle.md)** ja **[video](control-audio-video.md)**.


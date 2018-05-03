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
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="core-properties-in-powerapps"></a>Tärkeimmät ominaisuudet PowerAppsissa
Määritä, voiko käyttäjä nähdä ohjausobjektin ja olla sen kanssa vuorovaikutuksessa.

### <a name="properties"></a>Ominaisuudet
**Default** – Ohjausobjektin alkuarvo, ennen kuin käyttäjä on muuttanut sitä.

* Koskee ohjausobjekteja **[Card](control-card.md)**, **[Check box](control-check-box.md)**, **[Drop down](control-drop-down.md)**, **[Gallery](control-gallery.md)**, **[List Box](control-list-box.md)**, **[Radio](control-radio.md)**, **[Rating](control-rating.md)**, **[Slider](control-slider.md)**, **[Text input](control-text-input.md)** ja **[Toggle](control-toggle.md)**.

**DelayOutput** – Määritä arvoksi true, jos haluat viivästyttää toimintoa tekstinsyötön aikana.

* Koskee ohjausobjekteja **[Text input](control-text-input.md)**, **[Card](control-card.md)**

**DisplayMode** – Arvo voi olla **Muokkaa, Näytä** tai **Ei käytössä**. Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Muokkaa**) tai vain tarkastella tietoja (**Näytä**) vai onko ominaisuus kokonaan poissa käytöstä (**Poistettu käytöstä**).  **Näytä**-tilassa syöteohjausobjektit, kuten **[tekstisyöte](control-text-input.md)**,  **[avattava valikko](control-drop-down.md)** ja **[päivämäärävalitsin](control-date-picker.md)** näyttävät vain tekstiarvon. Vuorovaikutteisia elementtejä tai muotoiluja ei hahmonneta.  Tämän vuoksi ne soveltuvat hyvin näytettäväksi lomakkeissa tai luettavassa tulosteessa.

* Koskee ohjausobjekteja **[Add picture](control-add-picture.md)**, **[Audio](control-audio-video.md)**, **[Button](control-button.md)**, **[Camera](control-camera.md)**, **[Check box](control-check-box.md)**, **[Column chart](control-column-line-chart.md)**, **[Date Picker](control-date-picker.md)**, **[Drop down](control-drop-down.md)**, **[Export](control-export-import.md)**, **[Gallery](control-gallery.md)**, **[HTML text](control-html-text.md)**, **[Icon](control-shapes-icons.md)**, **[Image](control-image.md)**, **[Import](control-export-import.md)**, **[Label](control-text-box.md)**, **[Line chart](control-column-line-chart.md)**, **[List Box](control-list-box.md)**, **[Microphone](control-microphone.md)**, **[PDF viewer](control-pdf-viewer.md)**, **[Pen input](control-pen-input.md)**, **[Pie chart](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Rating](control-rating.md)**, **[Shape](control-shapes-icons.md)**, **[Slider](control-slider.md)**, **[Text input](control-text-input.md)**, **[Timer](control-timer.md)**, **[Toggle](control-toggle.md)** ja **[Video](control-audio-video.md)**.

**Items** – Ohjausobjektissa, kuten valikoimassa, luettelossa tai kaaviossa näytetyn tiedon lähde.

* Koskee ohjausobjekteja **[Column chart](control-column-line-chart.md)**, **[Drop down](control-drop-down.md)**, **[Gallery](control-gallery.md)**, **[Line chart](control-column-line-chart.md)**, **[List Box](control-list-box.md)**, **[Pie chart](control-pie-chart.md)** ja **[Radio](control-radio.md)**.

**OnChange** – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

* Koskee ohjausobjekteja **[Add picture](control-add-picture.md)**, **[Drop down](control-drop-down.md)**, **[List Box](control-list-box.md)**, **[Radio](control-radio.md)**, **[Rating](control-rating.md)**, **[Slider](control-slider.md)**, **[Text input](control-text-input.md)** ja **[Toggle](control-toggle.md)**.

**OnSelect** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

* Koskee ohjausobjekteja **[Add picture](control-add-picture.md)**, **[Button](control-button.md)**, **[Camera](control-camera.md)**, **[Check box](control-check-box.md)**, **[Column chart](control-column-line-chart.md)**, **[Date Picker](control-date-picker.md)**, **[Drop down](control-drop-down.md)**, **[Export](control-export-import.md)**, **[HTML text](control-html-text.md)**, **[Icon](control-shapes-icons.md)**, **[Image](control-image.md)**, **[Import](control-export-import.md)**, **[Label](control-text-box.md)**, **[Line chart](control-column-line-chart.md)**, **[List Box](control-list-box.md)**, **[Microphone](control-microphone.md)**, **[PDF viewer](control-pdf-viewer.md)**, **[Pen input](control-pen-input.md)**, **[Pie chart](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Rating](control-rating.md)**, **[Shape](control-shapes-icons.md)**, **[Slider](control-slider.md)**, **[Text input](control-text-input.md)**, **[Timer](control-timer.md)** ja **[Toggle](control-toggle.md)**.

**Reset** – Palautuuko ohjausobjekti oletusarvoonsa.  Katso myös **[Reset](../functions/function-reset.md)**-funktio.

* Koskee ohjausobjekteja **[Audio](control-audio-video.md)**, **[Check box](control-check-box.md)**, **[Drop down](control-drop-down.md)**, **[List Box](control-list-box.md)**, **[Microphone](control-microphone.md)**, **[Radio](control-radio.md)**, **[Rating](control-rating.md)**, **[Slider](control-slider.md)**, **[Text input](control-text-input.md)**, **[Timer](control-timer.md)**, **[Toggle](control-toggle.md)** ja **[Video](control-audio-video.md)**.

**Text** – Teksti, joka näytetään ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

* Koskee ohjausobjekteja **[Add picture](control-add-picture.md)**, **[Button](control-button.md)**, **[Check box](control-check-box.md)**, **[Export](control-export-import.md)**, **[Import](control-export-import.md)**, **[Label](control-text-box.md)**, **[Text input](control-text-input.md)** ja **[Timer](control-timer.md)**.

**Tooltip** – Ohjeteksti, joka ilmestyy näkyviin osoittimen ollessa ohjausobjektin päällä.

* Koskee ohjausobjekteja **[Audio](control-audio-video.md)**, **[Button](control-button.md)**, **[Camera](control-camera.md)**, **[Check box](control-check-box.md)**, **[Drop down](control-drop-down.md)**, **[HTML text](control-html-text.md)**, **[Image](control-image.md)**, **[Label](control-text-box.md)**, **[List Box](control-list-box.md)**, **[Microphone](control-microphone.md)**, **[PDF viewer](control-pdf-viewer.md)**, **[Pen input](control-pen-input.md)**, **[Radio](control-radio.md)**, **[Rating](control-rating.md)**, **[Slider](control-slider.md)**, **[Text input](control-text-input.md)**, **[Timer](control-timer.md)**, **[Toggle](control-toggle.md)** ja **[Video](control-audio-video.md)**.

**Value** – Syöteohjausobjektin arvo.

* Koskee ohjausobjekteja **[Check box](control-check-box.md)**, **[Radio](control-radio.md)**, **[Slider](control-slider.md)** ja **[Toggle](control-toggle.md)**.

**Visible** – Onko ohjausobjekti näkyvissä vai piilossa.

* Koskee ohjausobjekteja **[Add picture](control-add-picture.md)**, **[Audio](control-audio-video.md)**, **[Button](control-button.md)**, **[Camera](control-camera.md)**, **[Card](control-card.md)**, **[Check box](control-check-box.md)**, **[Column chart](control-column-line-chart.md)**, **[Date Picker](control-date-picker.md)**, **[Display form](control-form-detail.md)**, **[Drop down](control-drop-down.md)**, **[Edit form](control-form-detail.md)**, **[Export](control-export-import.md)**, **[Gallery](control-gallery.md)**, **[HTML text](control-html-text.md)**, **[Icon](control-shapes-icons.md)**, **[Image](control-image.md)**, **[Import](control-export-import.md)**, **[Label](control-text-box.md)**, **[Line chart](control-column-line-chart.md)**, **[List Box](control-list-box.md)**, **[Microphone](control-microphone.md)**, **[PDF viewer](control-pdf-viewer.md)**, **[Pen input](control-pen-input.md)**, **[Pie chart](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Rating](control-rating.md)**, **[Shape](control-shapes-icons.md)**, **[Slider](control-slider.md)**, **[Text input](control-text-input.md)**, **[Timer](control-timer.md)**, **[Toggle](control-toggle.md)** ja **[Video](control-audio-video.md)**.


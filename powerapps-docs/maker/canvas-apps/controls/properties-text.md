---
title: Tekstin ominaisuudet | Microsoft Docs
description: Viitetiedot ominaisuuksille, kuten Text, Tooltip ja HintText
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
ms.openlocfilehash: 6d79f5a93fd89de1c3994f43c285e9d96cb00af6
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="text-properties-in-powerapps"></a>Tekstin ominaisuudet PowerAppsissa
Määritä, kuinka teksti näytetään ohjausobjektissa, työkaluvihjeessä, kun käyttäjä kirjoittaa tietoja, tai määritä muita tekstiin liittyviä ominaisuuksia.

## <a name="text-appearance"></a>Tekstin ulkoasu
**Font** – Näytössä näkyvän fonttiperheen nimi.

* Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Kaaviosarake](control-column-line-chart.md)**, **[Päivämäärän valitsin](control-date-picker.md)**, **[Avattava luettelo](control-drop-down.md)**, **[Vie](control-export-import.md)**, **[HTML-teksti](control-html-text.md)**, **[Tuo](control-export-import.md)**, **[Otsikko](control-text-box.md)**, **[Viivakaavio](control-column-line-chart.md)**, **[Luetteloruutu](control-list-box.md)**, **[Lohkokaavio](control-pie-chart.md)**, **[Valintanappi](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

**FontWeight** – Ohjausobjektin tekstin paino: **lihavoitu**, **puolilihavoitu**, **normaali** tai **vaaleampi**.

* Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Päivämäärän valitsin](control-date-picker.md)**, **[Avattava luettelo](control-drop-down.md)**, **[Vie](control-export-import.md)**, **[Tuo](control-export-import.md)**, **[Otsikko](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Valintanappi](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

**Italic** – Onko ohjausobjektin teksti kursivoitu.

* Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Päivämäärän valitsin](control-date-picker.md)**, **[Avattava luettelo](control-drop-down.md)**, **[Vie](control-export-import.md)**, **[Tuo](control-export-import.md)**, **[Otsikko](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Valintanappi](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

**Size** – Ohjausobjektissa näytettävän tekstin fonttikoko.

* Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Kaaviosarake](control-column-line-chart.md)**, **[Päivämäärän valitsin](control-date-picker.md)**, **[Avattava luettelo](control-drop-down.md)**, **[Vie](control-export-import.md)**, **[HTML-teksti](control-html-text.md)**, **[Tuo](control-export-import.md)**, **[Otsikko](control-text-box.md)**, **[Viivakaavio](control-column-line-chart.md)**, **[Luetteloruutu](control-list-box.md)**, **[Kynäsyöte](control-pen-input.md)**, **[Lohkokaavio](control-pie-chart.md)**, **[Valintanappi](control-radio.md)** ja **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

**Strikethrough** – Onko ohjausobjektissa näkyvä teksti yliviivattua.

* Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Avattava luettelo](control-drop-down.md)**, **[Vie](control-export-import.md)**, **[Tuo](control-export-import.md)**, **[Otsikko](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Valintanappi](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

**Underline** – Onko ohjausobjektissa näkyvä teksti alleviivattua.

* Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Avattava luettelo](control-drop-down.md)**, **[Vie](control-export-import.md)**, **[Tuo](control-export-import.md)**, **[Otsikko](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Valintanappi](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

## <a name="text-placement"></a>Tekstin sijoittaminen
**Align** – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

* Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Vie](control-export-import.md)**, **[Tuo](control-export-import.md)**, **[Otsikko](control-text-box.md)**, **[Valintanappi](control-radio.md)**, **[Tekstisyöte](control-text-input.md)** ja **[Ajastin](control-timer.md)**.

**LineHeight** – Esimerkiksi tekstin tai luettelon rivien välinen etäisyys.

* Koskee ohjausobjekteja **[Luetteloruutu](control-list-box.md)**, **[Otsikko](control-text-box.md)**, **[Valintanappi](control-radio.md)** ja **[Tekstisyöte](control-text-input.md)**.

**VerticalAlign** – Ohjausobjektin tekstin sijainti suhteessa ohjausobjektin pystysuoraan keskikohtaan.

* Koskee ohjausobjekteja **[Lisää kuva](control-add-picture.md)**, **[Painike](control-button.md)**, **[Valintaruutu](control-check-box.md)**, **[Vie](control-export-import.md)**, **[Tuo](control-export-import.md)** ja **[Otsikko](control-text-box.md)**.


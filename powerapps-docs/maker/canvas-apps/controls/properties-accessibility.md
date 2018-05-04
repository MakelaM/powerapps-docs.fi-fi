---
title: Helppokäyttöominaisuudet | Microsoft Docs
description: Tietoja ominaisuuksista, kuten TabIndex ja työvaluvihje
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
ms.date: 01/26/2017
ms.author: fikaradz
ms.openlocfilehash: d35b4bc7a6e479ce47ad0a0b841a6ed9ccfd1a52
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="accessibility-properties-in-powerapps"></a>PowerAppsin helppokäyttöominaisuudet
Ominaisuuksia, jotka on määritetty auttamaan toimintarajoitteisia ihmisiä käyttämään ohjausobjekteja.

### <a name="properties"></a>Ominaisuudet
**AccessiblityLabel** – Näytönlukuohjelmien luettavaksi tarkoitetun ohjausobjektin kuvaus.   Jos kuvan, kuvakkeen tai muodon ohjausobjektin kohdalla on tyhjä arvo, ohjausobjekti piilotetaan näytönlukijalta ja sitä käsitellään muotoiluna.

* Koskee ohjausobjekteja **[Ääni](control-audio-video.md)**, **[Painike](control-button.md)**, **[Kamera](control-camera.md)**, **[Valintaruutu](control-check-box.md)**, **[Avattava valikko](control-drop-down.md)**, **[HTML-teksti](control-html-text.md)**, **[Kuva](control-image.md)**, **[Selite](control-text-box.md)**, **[Luetteloruutu](control-list-box.md)**, **[Mikrofoni](control-microphone.md)**, **[PDF-katseluohjelma](control-pdf-viewer.md)**, **[Kynäsyöte](control-pen-input.md)**, **[Valintanappi](control-radio.md)**, **[Luokitus](control-rating.md)**, **[Liukusäädin](control-slider.md)**, **[Tekstisyöte](control-text-input.md)**, **[Ajastin](control-timer.md)**, **[Vaihto](control-toggle.md)** ja and **[Video](control-audio-video.md)**.

**TabIndex** – Mukauttaa ohjausobjektien sarkainjärjestystä suorituksen aikana.

Oletusarvo on nolla, ja se määrittää oletusmuotoisen sarkainjärjestyksen ohjausobjektin XY-koordinaattien perusteella.  Jos asetuksiin määritetään nollaa korkeampi arvo, ohjausobjektin sarkain siirtyy kaikkien oletusarvoilla määritettyjen ohjausobjektien edelle.  Kun esimerkiksi TabIndex-arvolla 2 asetettua ohjausobjektia selataan, se edeltää ohjausobjektia, jonka TabIndex-arvo on 3 tai enemmän.

Huomaa, että Lomake- ja Valikoima - ohjausobjekti ja muut säilöt selaavat aina kaikki säilön elementit, ennen kuin siirtyvät säilön ulkopuolella oleviin ohjausobjekteihin.  Säilön sarkainjärjestys määräytyy alemman tason ohjausobjektin pienimmän TabIndex-arvon mukaan.

Jos TabIndex-arvoksi asetetaan -1, sarkainpääsy ohjausobjektiin estetään; jos arvoa käytetään kuvaan, kuvakkeeseen tai muotoon, kyseisestä elementistä tulee ei-interaktiivinen.

* Koskee ohjausobjekteja **[Painike](control-button.md)**, **[Päivämäärävalitsin](control-date-picker.md)**,  **[Avattava valikko](control-drop-down.md)**, **[Kuva](control-image.md)**, **[Tuonti](control-export-import.md)**, **[Luetteloruutu](control-list-box.md)**, **[Valintanappi](control-radio.md)**, **[Luokitus](control-rating.md)**, **[Liukusäädin](control-slider.md)**, **[Tekstisyöte](control-text-input.md)** ja  **[Vaihto](control-toggle.md)**.

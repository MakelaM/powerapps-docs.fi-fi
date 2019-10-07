---
title: 'Viiva koodi – skannerin ohjaus objekti: viittaus | Microsoft Docs'
description: Viiva koodi skannerin ohjaus objektin tiedot, mukaan lukien ominaisuudet ja esimerkit
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 11/25/2018
ms.author: fikaradz
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 56d8ca116b4b683d7096ef08f550dfa11c32d3c6
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986437"
---
# <a name="barcode-scanner-control-for-canvas-apps"></a>Viiva koodin ja skannerin ohjaus objekti kangas sovelluksille

Skannaa viiva koodeja, QR-koodeja ja tieto matriisi koodeja Android-tai iOS-laitteella. Ei tueta selaimessa.

## <a name="description"></a>Kuvaus

Ohjaus objekti avaa alkuperäisen skannerin Android-tai iOS-laitteessa. Skanneri tunnistaa automaattisesti viiva koodin, QR-koodin tai tieto matriisi koodin, kun se on näkymässä. Ohjaus objekti ei tue skannausta selaimessa.

Ohjaus objekti tukee QR-koodeja, tieto matriisi koodeja ja tämäntyyppisiä viiva koodeja:

- UPC A
- UPC E
- EAN 8
- EAN 13
- KOODI 39
- KOODI 128
- ITF
- PDF 417

## <a name="key-properties"></a>Tärkeimmät ominaisuudet

**Value** – Output-ominaisuus, joka sisältää viimeksi skannatun koodin teksti arvon.

**Teksti** – teksti, joka näkyy skanneria aktivoessa painikkeessa.

**Onscan** – miten sovellus reagoi, kun viiva koodin skannaus onnistuu.

## <a name="additional-properties"></a>Lisäominaisuudet

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**), vai onko ominaisuus poistettu käytöstä (**Disabled**).

**Flashlightenabled** – onko tasku lamppu käytössä automaattisesti, kun skanneri avataan.

**[Korkeus](properties-size-location.md)** – skannerin Aktivoi tavan painikkeen korkeus.

**Prefrontcamera** – otetaanko skannaukseen käyttöön etukamera, kun se on käytettävissä.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**Tyyppi** : viimeisimmän tarkistuksen aikana havaittu koodi tyyppi.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – skannerin Aktivoi tavan painikkeen leveys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
Samat ohjeet **[painike](control-button.md)** -ohjaus objektille koskevat **viiva koodi skannerin** ohjaus objektia, koska se on painike, joka käynnistää tarkistuksen.

### <a name="visual-alternatives"></a>Visuaaliset vaihto ehdot
* Viivakoodinlukija on painike, joka ei Näytä tarkistuksen tulosta. Harkitse tarkistuksen tuloksen näyttämistä **[nimi](control-text-box.md)** -ohjaus objektin avulla. Valitse selitteen **[teksti](properties-core.md)** -ominaisuudeksi viiva koodi skannerin **arvo** -ominaisuus. Valitse nimen **[Live](properties-accessibility.md)** -ominaisuudeksi **kohtelias** , jotta näytön luku ohjelman käyttäjille ilmoitetaan muutoksista. Tämä muutos tekee skannatun arvon kaikkien käyttöön visuaalisesta kyvystä riippumatta.

* Käyttäjät, joilla on visuaalisia ja motorisia rajoitteita, eivät ehkä halua osoittaa kameraa viiva koodilla. Harkitse toisen syöte muodon, kuten **[teksti syöte](control-text-input.md)** -ohjaus objektin, lisäämistä, jotta käyttäjät voivat kirjoittaa viiva koodeja.

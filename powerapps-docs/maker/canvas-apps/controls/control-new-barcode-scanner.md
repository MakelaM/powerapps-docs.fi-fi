---
title: 'Viivakoodiskanneri ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja, kuten ominaisuudet ja esimerkkejä, Viivakoodiskanneri ohjausobjektista
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 11/25/2018
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 961f8908014ef9cd85eadacb97a7c1dfc7e52b25
ms.sourcegitcommit: eef2d6d9a9c7f5c8a44b9734817f59dc0eac3ecf
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/07/2019
ms.locfileid: "57800993"
---
# <a name="barcode-scanner-control-for-canvas-apps"></a>Viivakoodiskanneri ohjausobjekti pohjaan perustuvat sovellukset

Skannaa viivakoodeja, QR-koodeja ja tietojen matriisi-koodit Android tai iOS-laitteessa. Selain ei tueta.

## <a name="description"></a>Kuvaus

Ohjausobjektin avautuu alkuperäisellä skannerilla, Androidille tai iOS-laitteessa. Skanneri tunnistaa automaattisesti viivakoodi, QR-koodin tai tietojen matriisi-koodin, kun näkymässä. Ohjausobjektin ei tue tarkistus selaimessa.

Ohjausobjekti tukee QR-koodit, tietojen matriisi-koodit ja nämä erityyppisiä viivakoodeja:

- UPC A
- UPC E
- EAN 8
- EAN 13
- KOODIN 39
- KOODIN 128
- ITF
- PDF 417

## <a name="key-properties"></a>Tärkeimmät ominaisuudet

**Arvo** – tuloksena ominaisuus, joka sisältää koodia, joka viimeksi skannattiin tekstiarvo.

**Tekstin** -teksti, joka näkyy painikkeessa, joka aktivoi skanneri.

**OnScan** – miten sovellus reagoi, kun viivakoodi tarkistetaan onnistuneesti.

## <a name="additional-properties"></a>Lisäominaisuudet

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**), vai onko ominaisuus poistettu käytöstä (**Disabled**).

**FlashlightEnabled** – onko taskulampun otetaan käyttöön automaattisesti, kun skanneri on avattu.

**[Korkeus](properties-size-location.md)**  – painike, joka aktivoi skanneri korkeus.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**Tyyppi** -koodin, joka oli havaittu tarkistuksessa, ajankohdan tyyppi.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)**  – painike, joka aktivoi skanneri leveyden.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

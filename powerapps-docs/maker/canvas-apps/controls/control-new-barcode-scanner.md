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
ms.openlocfilehash: 1e41ec8d228e62c22354d77777a8390bfd442f8c
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61543961"
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

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
Ohjeet ovat samat kuin **[painike](control-button.md)** ohjausobjektin koskevat **Viivakoodiskanneri** ohjausobjekti, koska se on tarkistuksen käynnistävän painikkeen.

### <a name="visual-alternatives"></a>Visualisoinnin vaihtoehtoihin
* Viivakoodiskanneri on painike, joka ei Näytä tarkistus tuloksen. Harkitse näytetään tarkistuksen tuloksen **[nimen](control-text-box.md)** ohjausobjektin. Määritä selitteen **[tekstin](properties-core.md)** viivakoodiskannerin ominaisuudeksi **arvo** ominaisuus. Määritä selitteen **[Live](properties-accessibility.md)** ominaisuudeksi **Polite** niin, että Näytönlukuohjelman käyttäjät saavat ilmoituksen muuttuu. Tämä muutos tekee skannatun arvon helppokäyttöisen kaikille käyttäjille visual kyvyn riippumatta.

* Käyttäjät, joilla on visualisointi ja moottoripyörän ehkä halua osoita kameran viivakoodia. Harkitse toisen lomakkeen syötteen, kuten **[Tekstisyöte](control-text-input.md)** ohjausobjektin kirjoittaa viivakoodeja.

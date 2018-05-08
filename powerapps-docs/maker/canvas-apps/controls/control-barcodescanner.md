---
title: 'Viivakoodiskannerin ohjausobjekti: viittaus | Microsoft Docs'
description: Viivakoodiskannerin ohjausobjektia koskevia tietoja, kuten ominaisuudet ja esimerkkejä
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
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 264c360af0175b6a5dddd74306b32c7d1ecaef1d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="barcode-scanner-control-experimental-in-powerapps"></a>Viivakoodiskannerin ohjausobjekti (kokeellinen) PowerAppsissa
Kokeellinen ohjausobjekti, jolla käyttäjä voi ottaa valokuvia käyttämällä laitteen viivakoodiskanneria.

## <a name="description"></a>Kuvaus
Jos lisäät tämän ohjausobjektin, käyttäjä voi päivittää tietolähteeseen yhden tai useita valokuvia mistä tahansa sovelluksen käyttöpaikasta.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**barcode scanner** – Sovelluksen käyttämän viivakoodiskannerin numeerinen tunnus laitteessa, jossa on useampi kuin yksi viivakoodiskanneri.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva**vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**Brightness** – Miten paljon valoa käyttäjä näkee kuvassa.

**Contrast** – Miten helposti käyttäjä voi erottaa samankaltaiset värit kuvasta.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnStream** – Miten sovellus reagoi, kun **Stream**-ominaisuus päivitetään.

**Photo** – Kuva, joka siepataan, kun käyttäjä ottaa kuvan.

**Stream** – **StreamRate** -ominaisuuden perusteella automaattisesti päivitetty kuva.

**StreamRate** – Miten usein kuva päivitetään **Stream**-ominaisuudessa millisekunteina.  Tämä arvo voi olla välillä 100 (1/10 sekuntia) – 3 600 000 (1 tunti).

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun kohdistin on ohjausobjektin päällä.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan (tai näytön, jos pääsäilöä ei ole) välinen etäisyys.

**Zoom** – Prosenttiosuus, jonka verran viivakoodiskannerin kuvaa tai PDF-katseluohjelman tiedoston näkymää suurennetaan.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Patch**( *Tietolähde*, *Perustietue*, *Muutostietue* )](../functions/function-patch.md)

## <a name="example"></a>Esimerkki
### <a name="add-photos-to-an-image-gallery-control"></a>Lisää valokuvia Kuvavalikoima-ohjausobjektiin
1. Lisää **viivakoodiskannerin** ohjausobjekti ja anna sen nimeksi **Oma viivakoodiskanneri**

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **Selite**-ohjausobjekti ja määritä sen tulosteeksi viivakoodin arvo.  
3. Skannaa tyypin viivakoodi BarcodeType-ominaisuudella.
4. Selite näyttää skannatun viivakoodin.

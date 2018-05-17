---
title: 'Äänen ja videon ohjausobjektit: viittaus | Microsoft Docs'
description: Äänen ja videon ohjausobjekteja koskevaa tietoa, mukaan lukien ominaisuuksia ja esimerkkejä
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
ms.openlocfilehash: 1661477ced59a678ac278dfcebe5e6f661c3e3f1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="audio-and-video-controls-in-powerapps"></a>Äänen ja videon ohjausobjektit PowerAppsissa
Ohjausobjekti, joka toistaa äänitiedoston, videotiedoston tai videon YouTubessa.

## <a name="description"></a>Kuvaus
**Ääni**-ohjausobjekti toistaa äänileikkeen tiedostosta, tallenteen **[Mikrofoni](control-microphone.md)**-ohjausobjektista tai ääniraidan videotiedoston. **Video**-ohjausobjekti toistaa videoleikkeen tiedostosta tai YouTubesta, jos määrität URL-osoitteen valinnaisella tekstityksellä.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**Loop** – Alkaako ääni- tai videoleike automaattisesti alusta, kun sen toistaminen lopetetaan.

**Media** – Ääni- tai video-ohjausobjektin toistaman leikkeen tunniste.

**ShowControls** – Näytetäänkö ääni- tai videosoittimessa esimerkiksi toistopainike ja äänenvoimakkuuden liukusäädin sekä näytetäänkö kynän ohjausobjektissa esimerkiksi piirustuksen, poistamisen ja tyhjentämisen kuvakkeet.

## <a name="additional-properties"></a>Lisäominaisuudet
**AutoPause** – Keskeytetäänkö ääni- tai videoleike automaattisesti, jos käyttäjä siirtyy eri näyttöön.

**AutoStart** – Alkaako ääni- tai video-ohjausobjekti toistaa leikettä automaattisesti, kun käyttäjä siirtyy tämän ohjausobjektin sisältävään näyttöön.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviivat**, **pisteet** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**ClosedCaptionsUrl** – Vain video-ohjausobjekti.  Tekstityksen URL-osoite WebVTT-muodossa.  Sekä videon että tekstityksen URL-osoitteiden on oltava HTTPS-muodossa. Jos palvelin isännöi sekä video- että tekstitystiedostoa, palvelimen tulee tukea CORS:ää.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[Kuva](properties-visual.md)** – Kuvan, äänen tai mikrofonin ohjausobjektissa näkyvän kuvan nimi.

**[ImagePosition](properties-visual.md)** – Kuvan tai ohjausobjektin asettelu (**Täyttö**, **Sovita**, **Venytä**, **Vierekkäin** tai **Center**), jos kuva tai ohjausobjekti ei ole saman kokoinen kuin näyttö.

**OnEnd** – Miten sovellus reagoi, kun ääni- tai videoleikkeen toistaminen loppuu.

**OnPause** – Miten sovellus reagoi, kun käyttäjä keskeyttää leikkeen, jota ääni- tai video-ohjausobjekti on toistamassa.

**OnStart** – Miten sovellus reagoi, kun käyttäjä aloittaa tallentamisen mikrofoniohjausobjektilla.

**Keskeytetty** – *True*, jos median toisto -ohjausobjekti on sillä hetkellä keskeytetty, muuten *false*.

**[Nollaa](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**Start** – Toistetaanko ääni- tai videoleike.

**StartTime** – Aika siitä, kun ääni- tai videoleikkeen toistaminen on aloitettu.

**Aika** – Mediaohjausobjektin nykyinen sijainti.

**[Työkaluvihje](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin osoittimen ollessa ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**First**( *TableName* )](../functions/function-first-last.md)

## <a name="examples"></a>Esimerkkejä
### <a name="play-an-audio-or-video-file"></a>Ääni- tai videotiedoston toistaminen
1. Napsauta tai napauta **Tiedosto**-valikossa **Media**, napsauta tai napauta **Videot** tai **Ääni** ja sitten **Selaa**.
2. Selaa käytettävään tiedostoon, napsauta tai napauta sitä ja sitten **Avaa**.
3. Palaa oletustyötilaan painamalla Esc-näppäintä, lisää **Ääni**- tai **Video**-ohjausobjekti ja aseta sen **Media**-ominaisuus lisäämääsi tiedostoon.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?
4. Paina F5-näppäintä ja toista leike napsauttamalla tai napauttamalla lisäämäsi ohjausobjektin toistopainiketta.

    > [!TIP]
> **Video**-ohjausobjektin toistopainike tulee näkyviin, kun pidät osoitinta ohjausobjektin päällä.
5. Palaa oletustyötilaan painamalla Esc-näppäintä.

### <a name="play-a-youtube-video"></a>Toista YouTube-video
1. Lisää **Video**-ohjausobjekti ja aseta sen **Media**-ominaisuus YouTube-videon URL-osoitteeseen lainausmerkeissä.
2. Paina F5 ja toista sitten leike napsauttamalla tai napauttamalla **Video**-ohjausobjektin toistopainiketta.
3. Palaa oletustyötilaan painamalla Esc-näppäintä.

---
title: 'PDF-katseluohjelman ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja PDF-katseluohjelman ohjausobjektista, kuten ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: c3ed17faae5963f71531b2fdc2ef9b08ee2569cc
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="pdf-viewer-control-experimental-in-powerapps"></a>PDF-katseluohjelman ohjausobjekti (kokeellinen) PowerAppsissa
Kokeellinen ohjausobjekti, joka näyttää PDF-tiedoston sisällön.

## <a name="description"></a>Kuvaus
Näytä tekstiä, grafiikkaa ja muuta sisältöä PDF-tiedostossa lisäämällä tämä ohjausobjekti. Määritä ohjausobjektin **Document**-ominaisuuden arvoksi kaksoislainausmerkeissä oleva URL-osoite, joka viittaa tiedostoon, jonka haluat näyttää.

## <a name="limitations"></a>Rajoitukset
Huomaa, että PowerAppsin suojausarkkitehtuurin vuoksi PDF-katseluohjelma tukee vain HTTPS-linkkejä, ei HTTP-linkkejä.  
Jos PDF-tiedosto sijaitsee palvelimella, jonka CORS-asetukset ovat rajoittavat, tiedostoa ei ehkä voi tarkastella sovelluksessa.  Tämän ongelman ratkaisemiseksi PDF-tiedostoja isännöivän palvelimen täytyy sallia eri alkuperiä sisältävät pyynnöt (CORS), jotka ovat peräisin osoitteesta powerapps.com.

Jos asiakirjaa ei voi avata PowerAppsissa, loppukäyttäjälle annetaan mahdollisuus avata asiakirja ulkoisessa selaimessa.  Vaihtoehto on käytettävissä myös järjestelmävalikossa kaikille ulkoisille asiakirjoille.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**Document** – Kaksoislainausmerkeissä oleva PDF-tiedoston URL-osoite.

## <a name="additional-properties"></a>Lisäominaisuudet
**ActualZoom** – Ohjausobjektin todellinen zoomaus, joka voi erota **Zoom**-ominaisuudella pyydetystä zoomauksesta.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviivat**, **pisteet** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**CurrentFindText** – Käytössä oleva hakusana.

**CurrentPage** – Näytettävän PDF-tiedoston sivunumero.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**FindNext** – Etsii seuraavan **FindText**-esiintymän asiakirjasta.

**FindPrevious** – Etsii edellisen **FindText**-esiintymän asiakirjasta.

**FindText** – Asiakirjasta etsittävä hakusana.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnStateChange** – Miten sovellus reagoi, kun ohjausobjektin tila muuttuu.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**Sivu** – Sen sivun sivunumero, jonka haluat näyttää.

**PageCount** – Asiakirjan sivujen lukumäärä.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**ShowControls** – Näytetäänkö ääni- tai videosoittimessa esimerkiksi toistopainike ja äänenvoimakkuuden liukusäädin sekä näytetäänkö kynän ohjausobjektissa esimerkiksi piirustuksen, poistamisen ja tyhjentämisen kuvakkeet.

**[Työkaluvihje](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

**Zoom** – Prosenttiosuus, jolla kameran kuvaa tai PDF-katseluohjelman tiedoston näkymää suurennetaan.

## <a name="example"></a>Esimerkki
* Lisää **PDF-katseluohjelman** ohjausobjekti ja määritä sen **Document**-ominaisuuden arvoksi PDF-tiedoston URL-osoite lainausmerkeissä, kuten seuraavassa esimerkissä:<br>
  **"http://www.who.int/gho/publications/world_health_statistics/EN_WHS2015_TOC.pdf?ua=1"**

    Ohjausobjekti näyttää PDF-tiedoston.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

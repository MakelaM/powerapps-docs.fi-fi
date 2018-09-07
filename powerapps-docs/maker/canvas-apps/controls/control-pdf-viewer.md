---
title: 'PDF-katseluohjelman ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja PDF-katseluohjelman ohjausobjektista, kuten ominaisuudet ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8d3add2ccb460e11211baa993c61902856c8f083
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833717"
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

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

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

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

**Zoom** – Prosenttiosuus, jolla kameran kuvaa tai PDF-katseluohjelman tiedoston näkymää suurennetaan.

## <a name="example"></a>Esimerkki

Lisää **PDF-katseluohjelman** ohjausobjekti ja määritä sen **Document**-ominaisuuden arvoksi PDF-tiedoston URL-osoite lainausmerkeissä, kuten seuraavassa esimerkissä:

  **"https://blog.mozilla.org/security/files/2015/05/HTTPS-FAQ.pdf"**

    The control shows the PDF file.

    Don't know how to [add and configure a control](../add-configure-controls.md)?

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet

Kaikkia PDF-tiedostojen helppokäyttötoimintoja ei tueta, sillä **PDF-katseluohjelma** on vielä koevaiheessa. Tämän vuoksi **ShowControls**-ominaisuudeksi on asetettava **true**, jotta käyttäjät voivat avata tiedoston ulkoisessa sovelluksessa.

Opi luomaan helppokäyttöisiä PDF-tiedostoja [WCAG 2.0](https://www.w3.org/TR/WCAG-TECHS/pdf.html)- ja [PDF/UA](https://www.pdfa.org/pdfua-the-iso-standard-for-universal-accessibility/)-standardien avulla.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* Harkitse otsikon lisäämistä **[selitteen](control-text-box.md)** avulla, jos PDF-tiedostossa ei ole otsikkoa. Otsikko voidaan sijoittaa välittömästi ennen **PDF-katseluohjelmaa**.

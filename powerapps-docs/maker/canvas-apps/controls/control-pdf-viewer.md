---
title: 'PDF-katseluohjelman ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja PDF-katseluohjelman ohjausobjektista, kuten ominaisuudet ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9fdd7f25a729fa71111e1fd5d82e04b7cea874f3
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986427"
---
# <a name="pdf-viewer-control-experimental-in-powerapps"></a>PDF-katseluohjelman ohjausobjekti (kokeellinen) PowerAppsissa
Kokeellinen ohjausobjekti, joka näyttää PDF-tiedoston sisällön.

## <a name="description"></a>Kuvaus
Näytä tekstiä, grafiikkaa ja muuta sisältöä PDF-tiedostossa lisäämällä tämä ohjausobjekti. Määritä ohjausobjektin **Document**-ominaisuuden arvoksi kaksoislainausmerkeissä oleva URL-osoite, joka viittaa tiedostoon, jonka haluat näyttää.

## <a name="limitations"></a>Rajoitukset
1. Powerappsin suojaus arkkitehtuuri edellyttää, että PDF-katselu ohjelma tukee vain HTTPS-linkkejä, ei http:tä.  

2. **Document** -ominaisuuden on linkitettävä suoraan PDF-tiedostoon. Palvelimen uudelleenohjauksia tai HTML-näkymiä asia kirjasta ei tueta.

3. Tiedostoa isännöivä palvelin ei saa vaatia todentamista.

4. Et välttämättä pysty lukemaan PDF-tiedostoa sovelluksessasi, jos tiedosto sijaitsee palvelimessa, jossa on rajoittavia ristiinorigon resurssien jakamis asetuksia (CORS). Jos haluat ratkaista tämän ongelman, PDF-tiedostoja isännöivän palvelimen on sallittava ristiinorigin-pyynnöt osoitteesta powerapps.com.

Sovelluksen käyttäjät voivat kiertää nämä rajoitukset avaamalla PDF-tiedostoja ulkoisessa selaimessa pyydettäessä, jos ohjaus objekti ei voi avata asia kirjaa. Vaihtoehto on käytettävissä myös järjestelmävalikossa kaikille ulkoisille asiakirjoille.

Sovellusten tekijät voivat kiertää näitä rajoituksia sisällyttämällä PDF-dokumentteja sovelluksen multimediaresurssina. Tällä tavalla PDF-katselu ohjelman ohjaus objekti voi aina näyttää asia kirjan.

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

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)** -asetuksena on **Poistettu käytöstä**.

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

Ohjausobjekti näyttää PDF-tiedoston.

Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet

Kaikkia PDF-tiedostojen helppokäyttötoimintoja ei tueta, sillä **PDF-katseluohjelma** on vielä koevaiheessa. Tämän vuoksi **ShowControls**-ominaisuudeksi on asetettava **true**, jotta käyttäjät voivat avata tiedoston ulkoisessa sovelluksessa.

Opi luomaan helppokäyttöisiä PDF-tiedostoja [WCAG 2.0](https://www.w3.org/TR/WCAG-TECHS/pdf.html)- ja [PDF/UA](https://www.pdfa.org/pdfua-the-iso-standard-for-universal-accessibility/)-standardien avulla.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* Harkitse otsikon lisäämistä **[selitteen](control-text-box.md)** avulla, jos PDF-tiedostossa ei ole otsikkoa. Otsikko voidaan sijoittaa välittömästi ennen **PDF-katseluohjelmaa**.

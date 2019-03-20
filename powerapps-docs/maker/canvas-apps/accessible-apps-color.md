---
title: Helppokäyttöisyysvärit pohjaan perustuvissa sovelluksissa | Microsoft Docs
description: Värikontrastiopas pohjaan perustuville sovelluksille PowerAppsissa
author: tahoon
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/23/2018
ms.author: tahoon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 586c82804380846ef400f020c4ce55c07262730f
ms.sourcegitcommit: 4db9c763455d141a7e1dd569a50c86bd9e50ebf0
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/20/2019
ms.locfileid: "57802028"
---
# <a name="accessible-colors-for-canvas-apps-in-powerapps"></a>Pohjaan perustuvien sovellusten helppokäyttöisyysvärit PowerAppsissa
Pohjaan perustuvissa sovelluksissa käytettävien värien tulisi olla sellaisia, että värisokeat ja näkökyvyltään alentuneen henkilöt voivat käyttää sovelluksia. Kaikki PowerAppsin teemat ovat oletusarvoisesti helppokäyttöisiä. Kun muokkaat sovelluksessa käytettyjä värejä, varmista helppokäyttöisyys seuraavien ohjeiden mukaisesti. Verkossa on käytettävissä useita työkaluja, mitkä voivat auttaa tunnistamaan värikontrastiongelmia.

## <a name="minimum-contrast-for-text"></a>Tekstin vähimmäiskontrasti
* Tekstin ja sen taustan kontrastisuhteen on oltava vähintään 4,5:1
* Suuren tekstin kontrastinsuhteen on oltava vähintään 3:1
* Käytöstä poistetulla tekstillä ei ole kontrastivaatimuksia

Vuorovaikutteisten ohjausobjektien seuraavien osien välillä on oltava riittävä värikontrasti:
* **[Väri](controls/properties-color-border.md)** ja **[täyttö](controls/properties-color-border.md)**
* **[PressedColor](controls/properties-color-border.md)**-väri ja  **[PressedFill](controls/properties-color-border.md)**-täyttö
* **[HoverColor](controls/properties-color-border.md)**-väri ja **[HoverFill](controls/properties-color-border.md)**-täyttö

## <a name="minimum-contrast-for-non-text"></a>Ei-tekstisisällön vähimmäiskontrasti

> [!NOTE]
> [WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html) -standardin kontrastivaatimukset koskevat vain tekstiä. Huomioi helppokäyttöisyyttä suunnitellessasi tulevaisuudessa käyttöön otettavat [WCAG 2.1 kontrastiohjeet](https://www.w3.org/TR/WCAG21/#non-text-contrast), jotka koskevat käyttöliittymän osia, kuten kuvakkeita. Näiden osien suositeltava vähimmäiskontrastisuhde on 3:1. Tässä osassa kuvataan koskevat ohjeet ovat **valinnainen** WCAG 2.0 yhteensopivuutta.

### <a name="user-interface-components"></a>Käyttöliittymän osat
Vuorovaikutteisten ohjausobjektien seuraavien osien välillä on oltava riittävä värikontrasti:
* **[FocusedBorderColor](controls/properties-color-border.md)**-väri ja ohjausobjektin ulkopuolinen väri

Värikontrastien lisätarkistukset koskevat ohjausobjekteja, joissa koko alue sisältää tietoa tai on vuorovaikutteinen. Tällainen voi olla esimerkiksi **[painike](controls/control-button.md)** tai **[kuvake](controls/control-shapes-icons.md)**, jota käytetään painikkeena. Näin voit varmistaa, että ohjausobjektin rajat ovat selkeät ja että käyttäjät tietävät, mitä kohtaa he voivat napsauttaa tai napauttaa.

Jos tällaisilla ohjausobjekteilla on reuna, seuraavien värikontrastien pitäisi olla riittävät:
* **[BorderColor](controls/properties-color-border.md)**-väri ja ohjausobjektin ulkopuolinen väri
* **[BorderColor](controls/properties-color-border.md)**-väri ja ohjausobjektin ulkopuolinen väri
* **[HoverBorderColor](controls/properties-color-border.md)**-väri ja ohjausobjektin ulkopuolinen väri

Jos tällaisilla ohjausobjekteilla ei ole reunaa, seuraavien värikontrastien pitäisi olla riittävät:
* **[Täyttö](controls/properties-color-border.md)** ja ohjausobjektin ulkopuolinen väri
* **[PressedFill](controls/properties-color-border.md)**-täyttö ja ohjausobjektin ulkopuolinen väri
* **[HoverFill](controls/properties-color-border.md)**-täyttö ja ohjausobjektin ulkopuolinen väri

### <a name="graphical-objects"></a>Graafiset objektit
Jos kuva välittää tärkeitä tietoja, tarkista, esiintyykö siinä kontrastiongelmia. Tämä koskee ohjausobjekteja, joissa voidaan näyttää kuva: **[Ääni](controls/control-audio-video.md)**,  **[kuvan](controls/control-image.md)**,  **[mikrofoni](controls/control-microphone.md)**, ja **[videon](controls/control-audio-video.md)**.

Tarkista, esiintyykö videosisällössä kontrastiongelmia. Voit vaihtoehtoisesti tai lisäksi lisätä videota kuvaavan [tekstityksen](controls/control-audio-video.md).

## <a name="provide-other-visual-cues"></a>Muiden visuaalisten elementtien lisääminen
Varmista, että sovellus välittää tietoa muillakin keinoilla kuin värillä. Esimerkiksi punavihervärisokeat käyttäjät eivät pysty erottamaan virheestä kertovaa punaista ilmoitusta onnistumisesta kertovasta vihreästä ilmoituksesta.

Voit välittää merkityksen lisäelementeillä, kuten **[kuvakkeilla](controls/control-shapes-icons.md)**, tai tekstityyleillä, kuten **[kursivoinnilla](controls/properties-text.md)** ja **[alleviivauksella](controls/properties-text.md)**.

## <a name="next-steps"></a>Seuraavat vaiheet
Lue lisää [Helppokäyttöisyysasetuksista](controls/properties-accessibility.md) PowerAppsin ohjausobjekteista ja kokeile [helppokäyttöisyyden tarkistusta](accessibility-checker.md).

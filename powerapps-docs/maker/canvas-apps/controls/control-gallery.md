---
title: 'Valikoima-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja, kuten ominaisuudet ja esimerkkejä, Valikoima-ohjausobjektista
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 05/25/2017
ms.author: sharik
ms.openlocfilehash: fcb482844e430444fd95bb2d0c85a8da23c91d84
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/07/2018
ms.locfileid: "37897727"
---
# <a name="gallery-control-in-powerapps"></a>PowerAppsin Valikoima-ohjausobjekti
Ohjausobjekti, joka sisältää muita ohjausobjekteja ja tietoja.

## <a name="description"></a>Kuvaus
**Valikoima**-ohjausobjekti voi näyttää useita tietolähteen tietueita ja jokainen tietue voi sisältää useita tietotyyppejä. **Valikoima**-ohjausobjekti voi esimerkiksi näyttää useita yhteystietoja ja jokaiselle kohteelle tietoja, kuten nimen, osoitteen ja puhelinnumeron. Jokainen tietokenttä näytetään erillisenä ohjausobjektina **Valikoima**-ohjausobjektin sisällä ja voit määrittää nämä ohjausobjektit niiden mallipohjissa. Mallipohja näytetään valikoiman ensimmäisenä kohteena **Valikoima**-ohjausobjektin vasemmassa reunassa vaakasuuntaisena ja **Valikoima**-ohjausobjektin yläosassa pystysuuntaisena. Mallipohjaan tekemäsi muutokset näkyvät **Valikoima**-ohjausobjektin eri osissa.

Saatavilla on ennalta määritettyjä Valikoima-ohjausobjekteja kuvien ja tekstin näyttämiseen sekä valikoima kohteille, joiden korkeudet eroavat.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Default](properties-core.md)** – Tietolähteen kohde tai tietue, joka valitaan valikoimaan sovelluksen käynnistymisen yhteydessä.

**[Items](properties-core.md)** – Ohjausobjektiin, kuten valikoimaan, luetteloon tai kaavioon, näkyviin tulevan tiedon lähde.

**Selected** – Valittu kohde.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi. Käytetään kuvaamaan kohteiden luetteloa.

**AllItems** – Kaikki valikoiman kohteet, mukaan lukien lisäohjausarvot, jotka ovat osa valikoiman mallipohjaa.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**Layout** – Vierittääkö käyttäjä valikoiman läpi tai mukauttaako käyttäjä liukusäädintä ylhäältä alas (**Vertical**) vai vasemmalta oikealle (**Horizontal**).

**NavigationStep** – Kuinka paljon valikoimaa vieritetään, jos sen **ShowNavigation**-ominaisuudeksi on asetettu **tosi** ja käyttäjä valitsee valikoiman jommassakummassa päässä olevan siirtymisnuolen.

**ShowNavigation** – Näytetäänkö valikoiman päissä nuolet, joiden avulla käyttäjä voi selata valikoiman kohteita napsauttamalla tai napauttamalla nuolta.

**ShowScrollbar** – Näytetäänkö vierityspalkki, kun käyttäjä siirtää hiiren osoittimen valikoiman päälle.

**Snap** – Kohdistetaanko valikoima automaattisesti näyttämään seuraava kohde kokonaan, kun käyttäjä vierittää valikoimaa.

**TemplateFill** – Valikoiman taustaväri.

**TemplatePadding** – Valikoiman kohteiden välinen etäisyys.

**TemplateSize** – Valikoiman mallipohjan korkeus pystysuoralla asettelulla tai valikoiman leveys vaakasuoralla asettelulla.

**Transition** – Visuaalinen efekti (**Pop**, **Push** tai **None**), kun käyttäjä siirtää osoittimen valikoiman sisältämän kohteen päälle.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**WrapCount** – Näytettävien kohteiden määrä riviä tai saraketta kohden perustuen vaaka- tai pystysuoraan asetteluun.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**Filter**( *Tietolähde*, *Kaava* )](../functions/function-filter-lookup.md)

## <a name="examples"></a>Esimerkkejä
### <a name="show-and-filter-data"></a>Tietojen näyttäminen ja suodattaminen
* [Tekstin näyttäminen](control-text-box.md#show-data-in-a-gallery)
* [Kuvien näyttäminen](control-image.md#show-a-set-of-images-from-a-data-source)
* [Tietojen suodattaminen luettelovaihtoehdon valinnalla](control-drop-down.md#example)
* [Tietojen suodattaminen liukusäätimellä](control-slider.md#example)

### <a name="get-data-from-the-user"></a>Tietojen vastaanottaminen käyttäjältä
* [Tekstin vastaanottaminen](control-text-input.md#collect-data)
* [Kuvien vastaanottaminen](control-add-picture.md#add-images-to-an-image-gallery-control)
* [Valokuvien vastaanottaminen](control-camera.md#example)
* [Äänien vastaanottaminen](control-microphone.md#example)
* [Piirustusten vastaanottaminen](control-pen-input.md#create-a-set-of-images)


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Jos valikoiman kohteiden on tarkoitus olla valittavissa napsauttamalla niitä, seuraavien objektien välillä on oltava asianmukainen värikontrasti:
* **[BorderColor](properties-color-border.md)** ja väri valikoiman ulkopuolella (jos reuna on käytössä)
* **[Täyttö](properties-color-border.md)** ja väri valikoiman ulkopuolella (jos reuna ei ole käytössä)

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

    > [!NOTE]
  > Näytönlukuohjelmat ilmoittavat, kun valikoiman kohteet muuttuvat. **AccessibleLabel** mainitaan myös. Tämä antaa ilmoitukselle kontekstin, mikä on erityisen tärkeää, jos samassa näytössä on useampi valikoima.

### <a name="keyboard-support"></a>Näppäimistön tuki
* Suosittelemme asettamaan **ShowScrollbar**-ominaisuuden arvoksi **tosi**. Useimmissa kosketusnäyttölaitteissa vierityspalkki näytetään ainoastaan vierittäessä.
* Jos valikoiman kohteiden on tarkoitus olla valittavissa napsauttamalla niitä, vain näppäimistöä käyttävien käyttäjien on myös voitava valita kohteet jollain tavalla. Voit mahdollistaa tämän lisäämällä **[painikkeen](control-button.md)**, jonka **OnSelect**-ominaisuuden arvoksi on asetettu **Select(Parent)**.

    > [!NOTE]
  > Valikoiman ulkopuolella olevia ohjausobjekteja ei oteta huomioon valikoimassa käytettävässä näppäimistön siirtymisjärjestyksessä. Valikoiman ohjausobjektien **[TabIndex](properties-accessibility.md)**-ominaisuus on rajoitettu. Lue lisätietoja [helppokäyttöisyysasetuksista](properties-accessibility.md).

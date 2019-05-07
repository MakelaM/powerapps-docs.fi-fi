---
title: 'Valikoima-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja, kuten ominaisuudet ja esimerkkejä, Valikoima-ohjausobjektista
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/25/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ba5df28f03ec5e7c9a3d8146aecb0427d8145b13
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61544242"
ms.PowerAppsDecimalTransform: true
---
# <a name="gallery-control-in-canvas-apps"></a>Valikoima-ohjausobjektin pohjaan perustuvat sovellukset

Ohjausobjekti, joka sisältää muita ohjausobjekteja ja tietoja.

## <a name="description"></a>Kuvaus

**Valikoima**-ohjausobjekti voi näyttää useita tietolähteen tietueita ja jokainen tietue voi sisältää useita tietotyyppejä. **Valikoima**-ohjausobjekti voi esimerkiksi näyttää useita yhteystietoja ja jokaiselle kohteelle tietoja, kuten nimen, osoitteen ja puhelinnumeron. Jokainen tietokenttä näytetään erillisenä ohjausobjektina **Valikoima**-ohjausobjektin sisällä ja voit määrittää nämä ohjausobjektit niiden mallipohjissa. Mallipohja näytetään valikoiman ensimmäisenä kohteena **Valikoima**-ohjausobjektin vasemmassa reunassa vaakasuuntaisena ja **Valikoima**-ohjausobjektin yläosassa pystysuuntaisena. Mallipohjaan tekemäsi muutokset näkyvät **Valikoima**-ohjausobjektin eri osissa.

Ennalta määritetyt malleja näytetään kuvien ja tekstin näyttäminen valikoimassa ovat käytettävissä sekä valikoiman kohteiden muuttujan korkeus.

## <a name="limitations"></a>Rajoitukset

Jos käyttäjä vierittää **joustava korkeus** valikoima-ohjausobjektin, ennen kuin kaikki kohteet ladataan, kohteen n tällä hetkellä view saattaa sijaita alaspäin ja ole näkymän kun tietojen lataaminen on valmis. Voit välttää tämän ongelman käyttämällä vakio **valikoiman** ohjausobjektin sijaan **joustava korkeus** variant.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet

**[Default](properties-core.md)** – Tietolähteen kohde tai tietue, joka valitaan valikoimaan sovelluksen käynnistymisen yhteydessä.

**[Items](properties-core.md)** – Ohjausobjektiin, kuten valikoimaan, luetteloon tai kaavioon, näkyviin tulevan tiedon lähde.

**Selected** – Valittu kohde.

## <a name="additional-properties"></a>Lisäominaisuudet

**[AccessibleLabel](properties-accessibility.md)**  – näytönlukuohjelmien valikoiman (ei sen sisältämät kohteet) nimen. Käytetään kuvaamaan kohteiden luetteloa.

**AllItems** – Kaikki valikoiman kohteet, mukaan lukien lisäohjausarvot, jotka ovat osa valikoiman mallipohjaa.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**ItemAccessibleLabel** – näytönlukuohjelmien valikoiman jokaisen kohteen nimi. Tulee kuvata kunkin kohteen ominaisuudet.

**NavigationStep** – Kuinka paljon valikoimaa vieritetään, jos sen **ShowNavigation**-ominaisuudeksi on asetettu **tosi** ja käyttäjä valitsee valikoiman jommassakummassa päässä olevan siirtymisnuolen.

**Joka voidaan valita** – näytetäänkö valikoimakohteet voidaan valita. Kun **true**, näytönlukuohjelmat määrittää valikoiman, joka voidaan valita luettelona ja valitse kohde napsauttamalla tai napauttamalla sitä. Kun **false**, näytönlukuohjelmat määrittää valikoiman säännöllisesti luettelona ja napsauttamalla tai napauttamalla kohdetta ei valita sen.

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

[**Filter**( *Tietolähde*; *Kaava* )](../functions/function-filter-lookup.md)

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

* Kun valikoiman kohteiden on useita ohjausobjekteja, käytä **ItemAccessibleLabel** laskemiseen valikoiman kohteen sisältö.

* Määrittää arvon **valittavissa** - **true** Jos haluat, että käyttäjät voivat valita valikoimakohteen. Muussa tapauksessa asetus kyseisen arvon **false**.

* Kun valikoiman kohteiden on useita ohjausobjekteja, käytä **ItemAccessibleLabel** antaa yhteenvedon valikoiman kohteen sisältö.

* **Joka voidaan valita** on asetettava oikein, sen mukaan, onko käyttäjien on tarkoitettu valita valikoimakohteen.

### <a name="keyboard-support"></a>Näppäimistön tuki

* Suosittelemme asettamaan **ShowScrollbar**-ominaisuuden arvoksi **tosi**. Useimmissa kosketusnäyttölaitteissa vierityspalkki näytetään ainoastaan vierittäessä.
* Jos valikoiman kohteiden on tarkoitus olla valittavissa napsauttamalla niitä, vain näppäimistöä käyttävien käyttäjien on myös voitava valita kohteet jollain tavalla. Voit mahdollistaa tämän lisäämällä **[painikkeen](control-button.md)**, jonka **OnSelect**-ominaisuuden arvoksi on asetettu **Select(Parent)**.

    > [!NOTE]
  > Valikoiman ulkopuolella olevia ohjausobjekteja ei oteta huomioon valikoimassa käytettävässä näppäimistön siirtymisjärjestyksessä. Valikoiman ohjausobjektien **[TabIndex](properties-accessibility.md)**-ominaisuus on rajoitettu. Lue lisätietoja [helppokäyttöisyysasetuksista](properties-accessibility.md).

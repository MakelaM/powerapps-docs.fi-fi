---
title: 'Valikoima-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja, kuten ominaisuudet ja esimerkkejä, Valikoima-ohjausobjektista
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/25/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 964f57c427b8e9e2e2f7a50e3d6e149ddea8e8b0
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986681"
ms.PowerAppsDecimalTransform: true
---
# <a name="gallery-control-in-canvas-apps"></a>Valikoima-ohjaus objekti kangas sovelluksissa

Ohjausobjekti, joka sisältää muita ohjausobjekteja ja tietoja.

## <a name="description"></a>Kuvaus

**Valikoima**-ohjausobjekti voi näyttää useita tietolähteen tietueita ja jokainen tietue voi sisältää useita tietotyyppejä. **Valikoima**-ohjausobjekti voi esimerkiksi näyttää useita yhteystietoja ja jokaiselle kohteelle tietoja, kuten nimen, osoitteen ja puhelinnumeron. Jokainen tietokenttä näytetään erillisenä ohjausobjektina **Valikoima**-ohjausobjektin sisällä ja voit määrittää nämä ohjausobjektit niiden mallipohjissa. Mallipohja näytetään valikoiman ensimmäisenä kohteena **Valikoima**-ohjausobjektin vasemmassa reunassa vaakasuuntaisena ja **Valikoima**-ohjausobjektin yläosassa pystysuuntaisena. Mallipohjaan tekemäsi muutokset näkyvät **Valikoima**-ohjausobjektin eri osissa.

Käytettävissä on esimääritettyjä malleja, joiden avulla näytetään kuvia ja tekstiä valikoimassa sekä valikoiman muuttuja korkeus kohteita.

## <a name="limitations"></a>Rajoitukset

Jos käyttäjä vierittää **joustavan korkeuden** valikoima-ohjaus objektia, ennen kuin kaikki kohteet on ladattu, parhaillaan näkymässä oleva kohde voidaan työntää alas ja olla poissa näkymästä, kun tietojen lataaminen on valmis. Voit välttää tämän ongelman käyttämällä vakio **valikoima** -ohjaus objektia **joustavan korkeuden** muunnoksen sijaan.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet

**[Default](properties-core.md)** – Tietolähteen kohde tai tietue, joka valitaan valikoimaan sovelluksen käynnistymisen yhteydessä.

**[Items](properties-core.md)** – Ohjausobjektiin, kuten valikoimaan, luetteloon tai kaavioon, näkyviin tulevan tiedon lähde.

**Selected** – Valittu kohde.

## <a name="additional-properties"></a>Lisäominaisuudet

**[AccessibleLabel](properties-accessibility.md)** – näytön luku ohjelmien valikoiman (ei sen sisältämien kohteiden) otsikko. Käytetään kuvaamaan kohteiden luetteloa.

**AllItems** – Kaikki valikoiman kohteet, mukaan lukien lisäohjausarvot, jotka ovat osa valikoiman mallipohjaa.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**ItemAccessibleLabel** – näytön luku ohjelmien kunkin valikoiman kohteen nimi. Pitäisi kuvailla, mitä kukin kohde on.

**NavigationStep** – Kuinka paljon valikoimaa vieritetään, jos sen **ShowNavigation**-ominaisuudeksi on asetettu **tosi** ja käyttäjä valitsee valikoiman jommassakummassa päässä olevan siirtymisnuolen.

**Selectable** – onko valikoima kohteita valittavissa. Kun asetus on **tosi**, näytön luku ohjelmat tunnistavat valikoiman valittavissa luettelona ja valitset kohteen napsauttamalla tai napauttamalla sitä. Kun asetus on **Epätosi**, näytön luku ohjelmat tunnistavat valikoiman säännölliseksi luetteloksi ja napsauttamalla tai napauttamalla kohdetta ei ole valittuna.

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
    > Näytön luku ohjelmat ilmoittavat, kun valikoiman kohteet muuttuvat. **AccessibleLabel** mainitaan myös. Tämä antaa ilmoitukselle kontekstin, mikä on erityisen tärkeää, jos samassa näytössä on useampi valikoima.

* Kun valikoima kohde sisältää useita ohjaus objektin, voit tehdä yhteenvedon valikoiman kohteen sisällöstä käyttämällä **ItemAccessibleLabel** .

* Määritä **selectable** -arvoksi **True** , jos haluat, että käyttäjät valitsevat valikoiman kohteen. Muussa tapa uksessa valitse arvoksi **false**.

* Kun valikoima kohde sisältää useita ohjaus objektin, voit antaa yhteenvedon valikoiman kohteen sisällöstä **ItemAccessibleLabel** -kohteen avulla.

* **Selectable** tulee määrittää oikein sen mukaan, onko käyttäjien tarkoitus valita valikoima kohde.

### <a name="keyboard-support"></a>Näppäimistön tuki

* Suosittelemme asettamaan **ShowScrollbar**-ominaisuuden arvoksi **tosi**. Useimmissa kosketusnäyttölaitteissa vierityspalkki näytetään ainoastaan vierittäessä.
* Jos valikoiman kohteiden on tarkoitus olla valittavissa napsauttamalla niitä, vain näppäimistöä käyttävien käyttäjien on myös voitava valita kohteet jollain tavalla. Voit mahdollistaa tämän lisäämällä **[painikkeen](control-button.md)** , jonka **OnSelect**-ominaisuuden arvoksi on asetettu **Select(Parent)** .

    > [!NOTE]
  > Valikoiman ulkopuolella olevia ohjausobjekteja ei oteta huomioon valikoimassa käytettävässä näppäimistön siirtymisjärjestyksessä. Valikoiman ohjausobjektien **[TabIndex](properties-accessibility.md)** -ominaisuus on rajoitettu. Lue lisätietoja [helppokäyttöisyysasetuksista](properties-accessibility.md).

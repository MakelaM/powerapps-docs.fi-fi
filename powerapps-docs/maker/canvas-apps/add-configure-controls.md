---
title: Lisää ja määritä pohjaan perustuvan sovelluksen ohjausobjekti | Microsoft Docs
description: Vaiheittaiset ohjeet pohjaan perustuvan sovelluksen ohjausobjektin lisäämiseen ja määrittämiseen suoraan työkaluriviltä, Ominaisuudet-välilehdestä tai kaavariviltä.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/25/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9d16e4c7b8d15611b06644520c0ee39417fd3ee0
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994694"
---
# <a name="add-and-configure-a-canvas-app-control-in-powerapps"></a>Pohjaan perustuvan sovelluksen ohjausobjektin lisääminen ja määrittäminen PowerAppsissa

Lisää käyttöliittymäelementtejä pohjaan perustuvaan sovellukseesi ja määritä niiden ulkoasua ja toimintaa suoraan työkaluriviltä, **Ominaisuudet**-välilehdestä tai kaavariviltä. Nämä käyttöliittymäelementit ovat nimeltään ohjausobjekteja. Niiden määritettävät osat ovat nimeltään ominaisuuksia.

## <a name="prerequisites"></a>Edellytykset

1. Jos sinulla ei vielä ole PowerApps-käyttö oikeutta, [Rekisteröidy](../signup-for-powerapps.md)ja [Kirjaudu](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)sisään.
1. Vie hiiren osoitin **Luo oma sovellus**-kohdan alta **tyhjä**-kohtaan ja valitse sitten **Tee tämä sovellus**.
1. Jos sinua kehotetaan tekemään intro-esittely, Tutustu PowerApps-liittymän avain alueisiin valitsemalla **Seuraava** ja valitse sitten **Ohita**.

    Voit aina tehdä esittelyn myöhemmin valitsemalla kysymys merkki kuvakkeen näytön oikeasta yläkulmasta ja valitsemalla sitten **Ota intro-esittely**.

## <a name="add-and-select-a-control"></a>Lisää ja valitse ohjaus objekti

Suorita **Lisää** -väli lehdessä jompikumpi seuraavista vaiheista:

- Valitse **otsikko** tai **painike** , jos haluat lisätä jonkin näistä ohjaus objekti tyypeistä.
- Valitse ohjaus objekti luokka ja valitse sitten lisättävän ohjaus objektin tyyppi.

Valitse esimerkiksi **Uusi näyttö**ja valitse sitten **tyhjä** , jos haluat lisätä sovellukseen tyhjän näytön. (Näytöt ovat ohjaus objekti tyyppi, joka voi sisältää muunlaisia ohjaus objekti tyyppejä.)

![Lisää näyttö](./media/add-configure-controls/add-screen.png)

Uuden näytön nimi on **Screen2** , ja se näkyy vasemmassa siirtymis ruudussa. Tässä ruudussa näkyy hierarkkinen luettelo sovelluksessasi olevasta ohjaus objekteista, joiden avulla voit helposti etsiä ja valita kunkin ohjaus objektin.

![Screen2 listassa](./media/add-configure-controls/list-screen2.png)

Jos haluat näyttää, miten tämä lista toimii, valitse **Lisää** -väli lehdestä **nimi** . Uusi ohjaus objekti näkyy hierarkkisessa luettelossa kohdassa **Screen2** .

![Screen2 listassa](./media/add-configure-controls/add-label.png)

Näytössä on oletus arvon mukaan teksti ruutu, jossa on kuusi kahvaa. Tämän ruudun tyyppi ympäröi kumpi ohjaus objekti on valittuna. Jos valitset näytön napsauttamalla tai napauttamalla sitä (mutta otsikon ulkopuolelle), ruutu poistuu selitteessä. Jos haluat valita otsikon uudelleen, napsauta tai napauta sitä tai napsauta tai napauta sen nimeä hierarkkisessa ohjaus objekti listassa.

> [!IMPORTANT]
> Sinun on aina valittava ohjaus objekti, ennen kuin voit määrittää sen.

## <a name="rename-a-control"></a>Ohjaus objektin nimeäminen uudelleen

Siirrä hiiren osoitin ohjaus objektien hierarkkisessa luettelossa sen ohjaus objektin päälle, jonka haluat nimetä uudelleen, valitse näkyviin tulevassa kolme pistettä sisältävä painike ja valitse sitten **Nimeä uudelleen**. Sen jälkeen voit kirjoittaa yksilöllisen, ikimuistoisen nimen, jotta sovelluksesi muodostaminen helpottuu.

![Ohjausobjektin nimeäminen uudelleen](./media/add-configure-controls/rename-control.png)

## <a name="delete-a-control"></a>Poista ohjaus objekti

Siirrä hiiren osoitin ohjaus objektien hierarkkisessa luettelossa poistettavan ohjaus objektin päälle, valitse näyttöön tulevassa painikkeessa kolme pistettä ja valitse sitten **Poista**. Jos haluat poistaa ohjaus objektin, joka ei ole näyttö, voit myös valita ohjaus objektin piirto alustalla ja painaa sitten Delete-näppäintä.

![Poista ohjaus objekti](./media/add-configure-controls/delete-control.png)

## <a name="reorder-screens"></a>Järjestä näytöt uudelleen

Siirrä hiiren osoitin ohjaus objektien hierarkkisessa luettelossa sellaisen näytön päälle, jonka haluat siirtää ylös-tai alaspäin, valitse näyttöön tulevassa painike ja valitse sitten **Siirrä ylös** tai **Siirrä alas**.

![Järjestä näyttö uudelleen](./media/add-configure-controls/reorder-screen.png)

> [!NOTE]
> Kun sovellus avataan, hierarkkinen ohjaus objektien luettelon yläreunassa oleva näyttö näkyy yleensä ensin. Voit kuitenkin määrittää eri näytön asettamalla **[ONSTART](controls/control-screen.md)** -ominaisuudeksi kaavan, joka sisältää **[Navigoi](functions/function-navigate.md)** -tehtävän.

## <a name="move-and-resize-a-control"></a>Ohjaus objektin siirtäminen ja koon muuttaminen

Jos haluat siirtää ohjaus objektia, valitse se, siirrä kohdistin sen keskelle niin, että nelipäinen nuoli tulee näkyviin, ja vedä sitten ohjaus objekti eri sijaintiin.

![Siirrä ohjaus objekti](./media/add-configure-controls/move-control.png)

Jos haluat muuttaa ohjaus objektin kokoa, valitse se, siirrä hiiren osoitin valinta ruudun minkä tahansa kahvan päälle niin, että kaksipäinen nuoli tulee näkyviin, ja vedä sitten kahvaa.

![Siirrä ohjaus objekti](./media/add-configure-controls/resize-control.png)

> [!NOTE]
> Kuten tässä ohje aiheessa kuvataan myöhemmin, voit myös siirtää ohjaus objektia ja muuttaa sen kokoa muuttamalla mitä tahansa **[X](controls/properties-size-location.md)** -, **[Y](controls/properties-size-location.md)** -, **[Height](controls/properties-size-location.md)** -ja **[Width](controls/properties-size-location.md)** -ominaisuuksien yhdistelmää kaava rivillä.

## <a name="change-the-text-of-a-label-or-a-button"></a>Otsikon tai painikkeen tekstin muuttaminen

Valitse selite tai painike, kaksoisnapsauta ohjaus objektissa näkyvää tekstiä ja kirjoita sitten haluamasi teksti.

![Muuta tekstiä](./media/add-configure-controls/change-text.png)

> [!NOTE]
> Kuten tässä ohje aiheessa kuvataan myöhemmin, voit myös muuttaa tätä tekstiä muokkaamalla sen **[teksti](controls/properties-core.md)** -ominaisuutta kaava rivillä.

## <a name="configure-a-control-from-the-toolbar"></a>Ohjausobjektin määrittäminen työkaluriviltä

Voit määrittää useampia ohjausobjektin asetuksia määrittämällä objektin työkaluriviltä kuin määrittämällä ohjausobjektin suoraan.

Voit esimerkiksi valita otsikon, valita **Aloitus** -väli lehden ja muuttaa tekstin fonttia selitteessä.

![Muuta fonttia](./media/add-configure-controls/change-font.png)

## <a name="configure-a-control-from-the-properties-tab"></a>Ohjausobjektin määrittäminen Ominaisuudet-välilehdeltä

**Ominaisuudet** -väli lehden avulla voit määrittää laajemman valikoiman asetuksia kuin voit määrittämällä ohjaus objektin työkalu riviltä.

Voit esimerkiksi valita ohjaus objektin ja näyttää tai piilottaa sen muuttamalla sen **Visible** -ominaisuutta.

![Valitse näkyvyys](./media/add-configure-controls/set-visibility.png)

## <a name="configure-a-control-in-the-formula-bar"></a>Ohjausobjektin määrittäminen kaavariviltä

Sen sijaan, että määrittäisit ohjaus objektin suoraan työkalu riviltä tai **Ominaisuudet** -väli lehdellä, voit määrittää ohjaus objektin valitsemalla ominaisuuden ominaisuus-listasta ja määrittämällä sitten arvon kaava rivillä. Tämän lähestymistavan avulla voit hakea ominaisuuksia aakkosjärjestyksen mukaan ja määrittää useampia arvotyyppejä.

Voit esimerkiksi valita otsikon ja määrittää sen seuraavilla tavoilla:

- Siirrä se valitsemalla Ominaisuudet-listasta **X** tai **Ky** ja määrittämällä sitten eri luku kaava rivillä.

    ![X-ominaisuuden asetus](./media/add-configure-controls/x-property.png)

- Muuta sen kokoa valitsemalla Ominaisuudet-listasta **Korkeus** tai **Leveys** ja määrittämällä sitten eri luku kaava rivillä.

    ![Valitse korkeus-ominaisuus](./media/add-configure-controls/height-property.png)

- Muuta sen tekstiä valitsemalla ominaisuus luettelon **teksti** ja määrittämällä sitten mikä tahansa literaalimerkkijonon, lausekkeen tai kaavan yhdistelmä kaava rivillä.

    - Literaalimerkkijonoa ympäröi lainaus merkit, ja se näkyy täsmälleen samalla tavalla kuin kirjoitat. **"Hello, World"** on literaalimerkkijono.

        ![Teksti-ominaisuuden arvoksi literaalimerkkijono](./media/add-configure-controls/literal-string.png)

    - Lauseke ei sisällä funktioita, ja se perustuu usein toisen ohjaus objektin ominaisuuteen. **Screen1. korkeus** on lauseke, joka ilmaisee **Screen1**-kohteen korkeuden.

        ![Teksti-ominaisuuden lisääminen lausekkeeseen](./media/add-configure-controls/expression.png)

    - Kaava sisältää vähintään yhden funktion. **Now** -funktio palauttaa nykyisen päivä määrän ja ajan paikallisessa aika vyöhykkeessä ja **teksti** funktio muotoilee arvot, kuten päivä määrät, kellon ajat ja valuutan.

        ![Teksti-ominaisuuden asetus kaavaan](./media/add-configure-controls/formula.png)

        Kaavat ovat yleensä paljon monimutkaisempia kuin tämän esimerkin, jotta ne voivat päivittää tietoja, lajitella, suodattaa ja suorittaa muita toimintoja. Saat lisä tietoja [kaava viittauksesta](formula-reference.md).

## <a name="next-steps"></a>Seuraavat vaiheet

- Etsi vaiheittaisia ohjeita yleisten ohjaus objektien, kuten [näyttöjen](add-screen-context-variables.md), [luetteloiden](add-list-box-drop-down-list-radio-button.md), [valikoimien](add-gallery.md), [lomakkeiden](add-form.md)ja [kaavioiden](use-line-pie-bar-chart.md), määrittämiseen.
- Etsi viite tietoja kustakin ohjaus objektin tyypistä [ohjaus objektin viitteessä](reference-properties.md).

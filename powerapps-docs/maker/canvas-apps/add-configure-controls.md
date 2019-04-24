---
title: Lisää ja määritä pohjaan perustuvan sovelluksen ohjausobjekti | Microsoft Docs
description: Vaiheittaiset ohjeet pohjaan perustuvan sovelluksen ohjausobjektin lisäämiseen ja määrittämiseen suoraan työkaluriviltä, Ominaisuudet-välilehdestä tai kaavariviltä.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/25/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 798a355e1c8728b41f3e92f183d4a4e2831b7cc2
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61530387"
---
# <a name="add-and-configure-a-canvas-app-control-in-powerapps"></a>Pohjaan perustuvan sovelluksen ohjausobjektin lisääminen ja määrittäminen PowerAppsissa

Lisää käyttöliittymäelementtejä pohjaan perustuvaan sovellukseesi ja määritä niiden ulkoasua ja toimintaa suoraan työkaluriviltä, **Ominaisuudet**-välilehdestä tai kaavariviltä. Nämä käyttöliittymäelementit ovat nimeltään ohjausobjekteja. Niiden määritettävät osat ovat nimeltään ominaisuuksia.

## <a name="prerequisites"></a>Edellytykset

1. Jos sinulla ei vielä ole PowerApps-käyttöoikeus [Rekisteröidy](../signup-for-powerapps.md), ja sitten [Kirjaudu sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
1. Valitse **Tee oma sovellukseni**, osoitin **pohjaan perustuva sovellus tyhjästä**, ja valitse sitten **Tee tämä sovellus**.
1. Jos sinua pyydetään esittely, valitse **seuraava** aloitusnäytön-PowerApps-käyttöliittymän (tai valitse **Ohita**).

    Voit voit aina katsella esittelyn myöhemmin valitsemalla näytön oikean yläkulman kysymysmerkkikuvaketta ja valitsemalla sitten **esittely**.

## <a name="add-and-select-a-control"></a>Lisää ja valitse ohjausobjekti

Valitse **Lisää** välilehti, suorita jompikumpi seuraavista vaiheista:

- Valitse **nimen** tai **painike** lisäämään tällaisia ohjausobjekteja.
- Valitse luokka ohjausobjektien ja valitse sitten ohjausobjekti, jonka haluat lisätä tyyppi.

Valitse esimerkiksi **uuden näytön**, ja valitse sitten **tyhjä** Lisää tyhjä näyttö sovellukseesi. (Näyttöjä ovat ohjausobjektissa, joka voi sisältää ohjausobjekteja.)

![Lisää näyttö](./media/add-configure-controls/add-screen.png)

Uuden näytön nimi on **Screen2** ja se näkyy vasemmassa siirtymisruudussa. Tässä ruudussa näkyy sovelluksesi ohjausobjektien hierarkkisessa luettelossa, niin, että voit helposti etsiä ja valita kunkin ohjausobjektin.

![Screen2 luettelossa](./media/add-configure-controls/list-screen2.png)

Osoittaa, miten tämän luettelon toimii, valitse **nimen** , **Lisää** välilehti. Uusi ohjausobjekti näkyy kohdassa **Screen2** hierarkkisessa luettelossa.

![Screen2 luettelossa](./media/add-configure-controls/add-label.png)

Näytöllä kuusi kahvat ympäröi valintaruutu nimen oletusarvon mukaan. Ruudun tyypin ympäröi tallennettuun ohjausobjekti on valittuna. Jos valitset näytössä napsauttamalla tai napauttamalla sen (mutta ulkopuolelle selite), selite katoaa ruutuun. Valitse selite uudelleen, voit napsauttamalla tai napauttamalla sen tai napsauttamalla tai napauttamalla **Label2** ohjausobjektien hierarkkisessa luettelossa.

> [!IMPORTANT]
> Sinun täytyy valita ohjausobjektin aina, ennen kuin voit määrittää sen.

## <a name="rename-a-control"></a>Ohjausobjektin nimeäminen uudelleen

Valitse hierarkkisessa luettelossa ohjausobjekteja, hiiren osoitinta ohjausobjektin, jonka haluat nimetä uudelleen, pistettä, joka näkyy ja valitse sitten **nimeä**. Kirjoita yksilöllinen ja helposti muistettavan tehdä helposti sovelluksen nimi.

![Ohjausobjektin nimeäminen uudelleen](./media/add-configure-controls/rename-control.png)

## <a name="delete-a-control"></a>Ohjausobjektin poistaminen

Hierarkkisessa luettelossa ohjausobjektien, hiiren osoitinta ohjausobjektin, jonka haluat poistaa, valitse kolme pistettä, joka näkyy ja valitse sitten **poistaa**. Jos haluat poistaa ohjausobjekti, joka ei ole näyttö, voit myös valita ohjausobjektin pohjalla ja paina Delete-näppäintä.

![Poista ohjausobjekti](./media/add-configure-controls/delete-control.png)

## <a name="reorder-screens"></a>Näyttöjen järjestäminen uudelleen

Osoitin ohjausobjektien hierarkkisessa luettelossa näytön, jonka haluat siirtää tai alas, valitse kolme pistettä, joka tulee näkyviin, ja valitse sitten **ylöspäin** tai **alaspäin**.

![Näytön järjestäminen uudelleen](./media/add-configure-controls/reorder-screen.png)

> [!NOTE]
> Kun sovellus avataan, yläosassa oleva ohjausobjektien hierarkkisessa luettelossa näytön yleensä näkyy ensimmäisenä. Mutta voit määrittää eri näyttöön määrittämällä **[OnStart](controls/control-screen.md)** ominaisuuden näyttämään kaavan, joka sisältää **[Navigate](functions/function-navigate.md)** funktio.

## <a name="move-and-resize-a-control"></a>Siirrä ja muuta ohjausobjektin kokoa

Siirrä ohjausobjektia valitsemalla se keskipiste hiirtä niin, että tulee neljän joista-nuoli ja vetämällä ohjausobjektin eri sijaintiin.

![Siirrä ohjausobjektia](./media/add-configure-controls/move-control.png)

Muuta ohjausobjektin kokoa, valitse se, mitä tahansa valintaruudun kahvaa hiirtä niin, että näkyviin tulee kaksi joista-nuoli ja vetämällä kahvaa.

![Siirrä ohjausobjektia](./media/add-configure-controls/resize-control.png)

> [!NOTE]
> Kuten tässä ohjeaiheessa kuvataan myöhemmin, voit myös siirtää ja muuta ohjausobjektin kokoa muokkaamalla minkä tahansa yhdistelmän sen  **[X](controls/properties-size-location.md)**,  **[Y](controls/properties-size-location.md)**,  **[Korkeus](controls/properties-size-location.md)**, ja **[leveys](controls/properties-size-location.md)** ominaisuudet kaavarivillä.

## <a name="change-the-text-of-a-label-or-a-button"></a>Muuta selitteen tai painikkeen teksti

Valitse otsikko tai painikkeen, kaksoisnapsauta ohjausobjektissa näkyvä teksti ja kirjoita sitten haluamasi teksti.

![Muuta teksti](./media/add-configure-controls/change-text.png)

> [!NOTE]
> Tässä aiheessa kuvataan myöhemmin, voit myös muuttaa tekstiä muokkaamalla sen **[tekstin](controls/properties-core.md)** ominaisuus kaavarivillä.

## <a name="configure-a-control-from-the-toolbar"></a>Ohjausobjektin määrittäminen työkaluriviltä

Voit määrittää useampia ohjausobjektin asetuksia määrittämällä objektin työkaluriviltä kuin määrittämällä ohjausobjektin suoraan.

Voit esimerkiksi, valitse nimi, valitse **aloitus** välilehti ja muuta sitten selitteen tekstin fontin.

![Muuta fontti](./media/add-configure-controls/change-font.png)

## <a name="configure-a-control-from-the-properties-tab"></a>Ohjausobjektin määrittäminen Ominaisuudet-välilehdeltä

Käyttämällä **ominaisuudet** välilehdessä voit määrittää erilaisia vaihtoehtoja kuin määrittämällä ohjausobjektin työkaluriviltä.

Esimerkiksi, voit valita ohjausobjektin ja sitten näyttää tai piilottaa muuttamalla sen **näkyvissä** ominaisuus.

![Määritä näkyvyys](./media/add-configure-controls/set-visibility.png)

## <a name="configure-a-control-in-the-formula-bar"></a>Ohjausobjektin määrittäminen kaavariviltä

Sen sijaan, että määrittäisit ohjausobjektin suoraan työkaluriviltä, ja tässä **ominaisuudet** välilehdessä voit määrittää ohjausobjektin ominaisuusluettelo ominaisuuden valitsemalla ja määrittämällä arvon kaavariville. Tämän lähestymistavan avulla voit hakea ominaisuuksia aakkosjärjestyksen mukaan ja määrittää useampia arvotyyppejä.

Voit esimerkiksi Valitse nimi ja määritä se seuraavasti:

- Siirrä se valitsemalla **X** tai **Y** ominaisuudet-luettelossa ja määrittämällä kaavarivillä eri.

    ![Määrittää X-ominaisuus](./media/add-configure-controls/x-property.png)

- Muuta sen kokoa valitsemalla **korkeus** tai **leveys** ominaisuudet-luettelossa ja määrittämällä kaavarivillä eri.

    ![Määritä Height-ominaisuus](./media/add-configure-controls/height-property.png)

- Muuta sen tekstiä valitsemalla **tekstin** ominaisuudet-luettelossa ja määrittämällä kaavarivillä literaalimerkkijono, lausekkeen tai kaavan.

    - Literaalimerkkijono on lainausmerkkien sisällä, ja se näkyy täsmälleen, heti sitä kirjoitettaessa. **”Hello, world”** ole merkkijonoliteraali.

        ![Aseta Text-ominaisuudeksi literaalimerkkijono](./media/add-configure-controls/literal-string.png)

    - Lauseke ei sisällä funktion ja perustuu usein toisen ohjausobjektin ominaisuuden. **Screen1.Height** on lauseke, joka näyttää korkeus **Screen1**.

        ![Aseta Text-ominaisuudeksi lausekkeen](./media/add-configure-controls/expression.png)

    - Kaava sisältää yhden tai useita funktioita. **Nyt** -funktio palauttaa nykyisen päivämäärän ja ajan paikallisen aikavyöhykkeen, ja **tekstin** funktio muotoilee arvoja, kuten päivämäärät, kertaa ja valuutta.

        ![Aseta Text-ominaisuudeksi kaavan](./media/add-configure-controls/formula.png)

        Kaavat ovat yleensä paljon monimutkaisempaa kuin tässä esimerkissä, jotta ne päivittää tiedot, lajitella ne, suodattaa se ja tehdä muita toimia. Jos haluat lisätietoja, katso [kaavan viittaus](formula-reference.md).

## <a name="next-steps"></a>Seuraavat vaiheet

- Vaiheittaiset ohjeet etsiä määrittäminen yleisiä ohjausobjekteja, kuten [näyttöjä](add-screen-context-variables.md), [luettelo](add-list-box-drop-down-list-radio-button.md), [valikoimat](add-gallery.md), [lomakkeiden](add-form.md), ja [kaavioiden](use-line-pie-bar-chart.md).
- Löytää kullakin Ohjausobjektityypillä tietoja [ohjausobjekti viittaus](reference-properties.md).

---
title: Lisää ja määritä ohjausobjekti | Microsoft Docs
description: Vaiheittaiset ohjeet ohjausobjektin lisäämiseen ja määrittämiseen suoraan työkaluriviltä, Ominaisuudet-välilehdestä tai kaavariviltä.
documentationcenter: na
author: aftowen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 07/10/2017
ms.author: anneta
ms.openlocfilehash: c3b1fb9802541159726a33cacd07c6f9743de0e2
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/07/2018
ms.locfileid: "37896692"
---
# <a name="add-and-configure-a-control-in-powerapps"></a>Ohjausobjektin lisääminen ja määrittäminen PowerAppsissa
Lisää käyttöliittymäelementtejä sovellukseesi ja määritä niiden ulkoasua ja toimintaa suoraan työkaluriviltä, **Ominaisuudet**-välilehdestä tai kaavariviltä. Nämä käyttöliittymäelementit ovat nimeltään ohjausobjekteja. Niiden määritettävät osat ovat nimeltään ominaisuuksia.

## <a name="prerequisites"></a>Edellytykset
1. [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](https://web.powerapps.com) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.

2. Napsauta tai napauta PowerApps Studion **Tiedosto-valikon** (lähellä vasenta reunaa) kohtaa **Uusi**.

    ![Tiedosto-valikon Uusi-vaihtoehto](./media/add-configure-controls/file-new.png)

3. Napsauta tai napauta **Tyhjä sovellus** -ruudun kohtaa **Puhelinasettelu**.

    ![Luo sovellus alusta alkaen](./media/add-configure-controls/blank-app.png)

4. Jos sinua pyydetään katsomaan esittely PowerApps-käyttöliittymän avainalueista, voit katsoa sen napsauttamalla tai napauttamalla **Seuraava**. Ohita esittely napsauttamalla tai napauttamalla **Ohita**.

    ![Esittelyn avausruutu](./media/add-configure-controls/quick-tour.png)

    Voit aina katsella esittelyn myöhemmin napsauttamalla tai napauttamalla kysymysmerkkikuvaketta, joka on lähellä ruudun oikeaa yläkulmaa, ja napsauttamalla tai napauttamalla sitten **Katso esittely**.

## <a name="add-a-control"></a>Ohjausobjektin lisääminen
Voit lisätä minkä tahansa ohjausobjektin useista eri luokista napsauttamalla tai napauttamalla työkalurivin **Lisää**-välilehteä, napsauttamalla tai napauttamalla luokkaa ja valitsemalla sitten haluamasi ohjausobjektin. Tässä osassa voit tarkastella eri luokkien ohjausobjekteja, tutustua lisättävien ohjausobjektien tyyppeihin ja oppia löytämään ne.

Napsauta tai napauta **Lisää**-välilehdestä mitä tahansa luokkaa ja valitse sitten ohjausobjekti, jonka haluat lisätä:

**Teksti**: selite, tekstisyöte, HTML-teksti, kynäsyöte<br>
**Ohjausobjektit**: painike, avattava luettelo, päivämäärävalitsin, luetteloruutu, valintaruutu, valintanappi, vaihtopainike, liukusäädin, luokitus, ajastin<br>
**Valikoima**: pystysuora, vaakasuora, joustava korkeus, tyhjä pystysuuntainen, tyhjä vaakasuuntainen, tyhjä joustava korkeus<br>
**Tietotaulukko**<br>
**Lomakkeet**: muokkaa, näytä, entiteettilomake<br>
**Media**: kuva, kamera, viivakoodi, video, ääni, mikrofoni, lisää kuva<br>
**Kaaviot**: pylväskaavio, viivakaavio, ympyräkaavio<br>
**Kuvakkeet**

> [!TIP]
> Jos tarvitset enemmän tilaa ohjausobjekteille, [lisää toinen näyttö](add-screen-context-variables.md).

## <a name="configure-a-control-directly"></a>Ohjausobjektin määrittäminen suoraan
Tässä menettelyssä lisätään ja määritetään **selite**ohjausobjekti, mutta samat periaatteet pätevät myös moniin muihin ohjausobjekteihin.

1. Napsauta tai napauta **Lisää**-välilehteä ja valitse **Selite**.

    ![Lisää-välilehti](./media/add-configure-controls/insert-text-box.png)

    Kun lisäät ohjausobjektin, se on valittuna oletusarvoisesti. Voit myös valita aiemmin luodun ohjausobjektin napsauttamalla tai napauttamalla sitä. Kun ohjausobjekti on valittuna, sitä ympäröi valintaruutu, ja muut käyttöliittymän alueet muuttuvat siten, että voit määrittää valitun ohjausobjektin. Esimerkiksi valittu **selite**ohjausobjekti muistuttaa seuraavaa kuvaa.

    ![Valittu selite](./media/add-configure-controls/selected-text-box.png)

    > [!IMPORTANT]
   > Jos ohjausobjekti on valittuna, kun valitset toisen ohjausobjektin tai tyhjän alueen näytössä, ensimmäinen elementti ei ole enää valittuna.
2. Kavenna **selite**ohjausobjektia vetämällä valintakehyksen oikeassa reunassa olevaa kahvaa vasemmalle. (Keskikahva näkyy vain, jos zoomaat lähemmäs.)

    ![Selite, jonka kokoa on muutettu](./media/add-configure-controls/shorter-text-box.png)

     Voit myös muuttaa ohjausobjektin kokoa muokkaamalla sen **[Korkeus](controls/properties-size-location.md)**- ja **[Leveys](controls/properties-size-location.md)**-ominaisuuksia tavalla, joka kuvataan myöhemmin tässä aiheessa.

3. Siirrä **selite**ohjausobjektia vetämällä valintakehystä (tai muokkaamalla **[X](controls/properties-size-location.md)**- ja **[Y](controls/properties-size-location.md)**-ominaisuuksia tavalla, joka kuvataan myöhemmin tässä aiheessa).

4. Napsauta **selite**ohjausobjektissa näkyvää tekstiä kolmesti ja kirjoita **Hei maailma**.

    ![Selite, jossa on mukautettua tekstiä](./media/add-configure-controls/change-text-directly.png)

     Voit muokata tekstiä määrittämällä ohjausobjektin **[Teksti](controls/properties-core.md)**-ominaisuuden tavalla, joka kuvataan myöhemmin tässä aiheessa.

## <a name="configure-a-control-from-the-toolbar"></a>Ohjausobjektin määrittäminen työkaluriviltä
Voit määrittää useampia ohjausobjektin asetuksia määrittämällä objektin työkaluriviltä kuin määrittämällä ohjausobjektin suoraan.

1. Napsauta tai napauta työkalurivin **Aloitus**-välilehteä, kun **selite**ohjausobjekti on valittuna.

    ![Aloitus-välilehti](./media/add-configure-controls/home-tab.png)

2. Napsauta tai napauta **Täytä** ja valitse sitten väri, esimerkiksi vedenvihreä.

    ![Täyttöasetukset](./media/add-configure-controls/fill-option.png)

    **Selite**ohjausobjekti muuttuu muutostesi mukaisesti.

    ![Selite, jossa on vedenvihreä täyttö](./media/add-configure-controls/change-fill.png)

3. Fonttiperheen tai tekstin koon muuttaminen (esimerkiksi 18 pisteen Georgia).

    ![Fonttiohjausobjektit](./media/add-configure-controls/font-size.png)

    **Selite**ohjausobjekti muuttuu muutostesi mukaisesti.

    ![18 pisteen Georgia](./media/add-configure-controls/change-font.png)

4. Napsauta tai napauta **Selite**-välilehteä, napsauta tai napauta **VerticalAlign** ja valitse **Top**.

    ![Tekstiruutu-välilehti](./media/add-configure-controls/text-box-tab.png)

    **Selite**ohjausobjekti muuttuu muutostesi mukaisesti.

    ![Selite, jonka teksti on tasattu ruudun yläreunaan](./media/add-configure-controls/change-align.png)

## <a name="configure-a-control-from-the-properties-tab"></a>Ohjausobjektin määrittäminen Ominaisuudet-välilehdeltä
Käyttämällä **Ominaisuudet**-välilehteä voit määrittää ohjausobjektin kirjoittamatta kaavaa. Tässä menettelyssä lisätään ja määritetään toinen **selite**ohjausobjekti, mutta samat periaatteet pätevät myös moniin muihin ohjausobjekteihin.

1. Lisää toinen **selite**ohjausobjekti tavalla, joka kuvattiin aiemmin tässä aiheessa.

2. Napsauta tai napauta oikeanpuoleisessa ruudussa olevaa **Ominaisuudet**-välilehteä, kun uusi ohjausobjekti on valittuna.

    ![Ominaisuuspaneeli](./media/add-configure-controls/properties-panel.png)

3. Kirjoita **tekstiruutuun** **Ominaisuudet-välilehti**.

    ![Ominaisuuspaneelin selitteen teksti](./media/add-configure-controls/properties-panel-text.png)

    Kirjoitettu teksti näytetään **selite**ohjausobjektissa.

    ![Ominaisuuspaneelin pohjan teksti](./media/add-configure-controls/properties-panel-canvas-text.png)

4. Napsauta tai napauta **Ominaisuus**paneelin **Täytä**-kuvaketta ja valitse sitten väri.

    ![Ominaisuuspaneelin värin teksti](./media/add-configure-controls/properties-panel-color.png)

    **Selite**ohjausobjekti muuttuu muutostesi mukaisesti.

    ![Ominaisuuspaneelin pohjan väri](./media/add-configure-controls/properties-panel-canvas-color.png)

5. Napsauta tai napauta ominaisuuspaneelin **Väri**-ominaisuutta.

    ![Ominaisuuspaneelin ominaisuus](./media/add-configure-controls/properties-panel-property.png)

    **Väri**-ominaisuuden arvo korostetaan kaavarivillä.

    ![Ominaisuuspaneelin ominaisuuslauseke](./media/add-configure-controls/properties-panel-property-expression.png)

6. Poista toinen **selite**ohjausobjekti napsauttamalla tai napauttamalla sitä ja painamalla sitten Poista.

## <a name="configure-a-control-in-the-formula-bar"></a>Ohjausobjektin määrittäminen kaavariviltä
Kaavariviltä voit määrittää ominaisuuksia, joita ei voi määrittää suoraan **Ominaisuudet**-välilehdeltä tai työkaluriviltä. Voit esimerkiksi määrittää työkaluvihjeen, joka tulee näkyviin, kun käyttäjä osoittaa ohjausobjektia, mutta ei napsauta tai napauta sitä. Voit myös määrittää monimutkaisia kaavoja, jotka tekevät sovelluksestasi entistä tehokkaamman.

Aiemmin tässä aiheessa tehdyt muutokset ovat päivittäneet määritettävän ohjausobjektin jonkin [ominaisuuden](reference-properties.md) arvoa.

* Kun muutit ohjausobjektin kokoa, muutit sen **[Leveys](controls/properties-size-location.md)**-ominaisuutta.
* Kun siirsit ohjausobjektia, muutit sen **[X](controls/properties-size-location.md)**- ja **[Y](controls/properties-size-location.md)**-ominaisuuksia.
* Kun muutit ohjausobjektin näyttämää tekstiä, muutit sen **[Teksti](controls/properties-core.md)**-ominaisuutta.

Sen sijaan, että määrittäisit ohjausobjektin suoraan, **Ominaisuudet**-välilehdeltä tai työkaluriviltä, voit päivittää ominaisuuden arvon valitsemalla sen ominaisuusluettelosta ja määrittämällä arvon kaavariville. Tämän lähestymistavan avulla voit hakea ominaisuuksia aakkosjärjestyksen mukaan ja määrittää useampia arvotyyppejä.

1. Valitse jäljellä oleva **selite**ohjausobjekti, napsauta tai napauta ominaisuusluettelossa **[Teksti](controls/properties-core.md)**-ominaisuutta ja kirjoita kaavariville **"Yrityksen nimi"** (mukaan lukien lainausmerkit).

    ![Literaalimerkkijono selitteessä](./media/add-configure-controls/text-literal.png)

    Ympäröimällä merkkijonon lainausmerkeillä määrität, että sitä käsitellään täsmälleen samalla tavalla, kuin se on kirjoitettu. Vaihtoehtoisesti voit määrittää ominaisuuden arvoksi kaavan.

2. Valitse **selite**ohjausobjekti, napsauta tai napauta ominaisuusluettelossa **[Teksti](controls/properties-core.md)**-ominaisuutta ja kirjoita kaavariville **Today()** (ilman kysymysmerkkejä).

    Ohjausobjekti näyttää nykyisen päivämäärän.

    ![Today-funktio](./media/add-configure-controls/today-function.png)

    > [!TIP]
   > Voit [muotoilla päivämäärän ja kellonajan](show-text-dates-times.md) usein eri tavoin, minkä lisäksi voit suorittaa niillä laskutoimituksia.

## <a name="configure-two-controls-to-interact-with-each-other"></a>Kahden ohjausobjektin määrittäminen vuorovaikutukseen toistensa kanssa
Tässä menettelyssä lisätään valintaruutu ja määritetään selitettä, jonka määritit näytettäväksi vain, kun valintaruutu on valittuna.

1. Napsauta tai napauta **Lisää**-välilehteä.

    ![Lisää-välilehti](./media/add-configure-controls/insert-tab.png)

2. Napsauta tai napauta **Ohjausobjektit** ja napsauta tai napauta **valintaruutu**.

    ![Lisää valintaruutu](./media/add-configure-controls/insert-check-box.png)

3. Siirrä **valintaruutu**ohjausobjektia siten, että se näkyy **selite**ohjausobjektin alla, ja määritä **valintaruutu**ohjausobjektin **[Teksti](controls/properties-core.md)**-ominaisuudeksi **Näytä teksti**.

    ![Määritä valintaruutu](./media/add-configure-controls/configure-check-box.png)

4. Varmista, että **valintaruutu**ohjausobjekti on edelleen valittuna, napsauta tai napauta sen nimeä **Ominaisuudet**-välilehden yläpuolella ja kirjoita **MyCheckbox**

    ![Nimeä valintaruutu uudelleen](./media/add-configure-controls/properties-panel-rename.png)

5. Valitse **selite**ohjausobjekti napsauttamalla tai napauttamalla sitä.

6. Valitse **Ominaisuudet**-välilehti ja napsauta tai napauta **Näkyvissä**-ominaisuutta.

    ![Näkyvissä-ominaisuus](./media/add-configure-controls/properties-panel-visible-property.png)

7. Poista kaavariviltä arvo **true** ja kirjoita tai liitä seuraava kaava:

    **If(MyCheckbox.Value = true, true, false)**

    Tämä **[If-funktio](functions/function-if.md)** ilmaisee, että selite näytetään vain, jos valintaruutu on valittuna. Koska valintaruudun valinta poistetaan, **selite**ohjausobjekti katoaa (lukuun ottamatta valintakehystä).

    ![Näkyvissä-kaava](./media/add-configure-controls/visible-formula.png)

8. Lisää valintakehys napsauttamalla tai napauttamalla **valintaruutu**ohjausobjektia. Napsauta tai napauta sitä sitten uudelleen, jos haluat lisätä valintamerkin.

    **Selite** tulee näkyviin uudelleen:

    ![Selite tulee näkyviin, kun valintaruutu on valittuna](./media/add-configure-controls/show-text.png)

9. Piilota **selite**ohjausobjekti poistamalla **valintaruutu**ohjausobjektin valinta.

    ![Selite katoaa näkyvistä, kun valintaruutu ei ole valittuna](./media/add-configure-controls/hide-text.png)

Esimerkki on perustasoa, mutta voit määrittää sovelluksesi toimintaa ja ulkoasua yksinkertaisesta monimutkaiseen muodostamalla yhden tai useamman [kaavan](formula-reference.md).

## <a name="rename-a-screen-or-a-control"></a>Näytön tai ohjausobjektin nimeäminen uudelleen
Voit muodostaa helpommin luettavia ja ylläpidettäviä kaavoja nimeämällä näytön tai ohjausobjektin uudelleen.

1. Napsauta tai napauta näyttöä tai ohjausobjektia, jonka haluat nimetä uudelleen.

2. Napsauta tai napauta oikeanpuoleisessa ruudussa ohjausobjektin nimeä (suoraan **Ominaisuudet**-välilehden yläpuolella) ja kirjoita haluamasi nimi.

    ![Nimeä valintaruutu uudelleen](./media/add-configure-controls/properties-panel-rename.png)

## <a name="find-and-select-a-screen-or-a-control"></a>Näytön tai ohjausobjektin etsiminen ja valitseminen
Voit etsiä ja valita näytön tai ohjausobjektin hakemalla sitä vasemmanpuoleisessa ruudussa, vaikka se olisi piilotettu tai päällekkäinen toisen ohjausobjektin kanssa. Tässä ruudussa näkyy joko pikkukuva sovelluksen jokaisesta näytöstä tai hierarkkinen näkymä jokaisesta ruudusta ja niiden sisältämistä ohjausobjekteista.

* **Voit siirtyä pikkukuvien ja hierarkkisen näkymän välillä** napsauttamalla tai napauttamalla ruudun oikeassa yläkulmassa olevaa kuvaketta.

    ![Näkymien vaihtaminen](./media/add-configure-controls/toggle-view.png)

* **Etsi ohjausobjekteja** kirjoittamalla yksi tai useampi merkki. Tämä korostaa ne ohjausobjektit, jotka sisältävät kirjoittamasi tekstin.

    Voit valita ohjausobjektin sovelluksessa napsauttamalla tai napauttamalla hakutulosta.

    ![Hae puunäkymässä](./media/add-configure-controls/search.png)

* **Voit siirtää näytön ylös- tai alaspäin, kopioida sen, poistaa sen tai nimetä sen uudelleen** napsauttamalla sitä hiiren kakkospainikkeella (tai napsauttamalla tai napauttamalla sen vieressä olevia kolmea pistettä) ja valitsemalla sitten haluamasi vaihtoehdon.

    ![Puunäkymän pikavalikko](./media/add-configure-controls/context.png)

* **Voit kopioida, liittää tai poistaa ohjausobjektin tai nimetä sen uudelleen** napsauttamalla sitä hiiren kakkospainikkeella (tai napsauttamalla tai napauttamalla sen vieressä olevia kolmea pistettä) ja valitsemalla sitten haluamasi vaihtoehdon.

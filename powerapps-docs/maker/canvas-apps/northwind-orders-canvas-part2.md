---
title: Luo yhteenveto lomake pohjaan perustuvan sovelluksen | Microsoft Docs
description: Luo Yhteenveto lomakkeen pohjaan perustuvan sovelluksen Northwind Traders tietojen hallintaan
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/25/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5c40cb030241d142a2ee2a68d32f7fb839a350ff
ms.sourcegitcommit: 55bc11ac6a964f22301c9fdadb06ee34e1399f83
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/07/2019
ms.locfileid: "66805916"
---
# <a name="create-a-summary-form-in-a-canvas-app"></a>Luo yhteenveto lomake pohjaan perustuva sovellus

Noudata vaiheittaiset ohjeet pohjaan perustuvan sovelluksen hallintaan kuvitteellisia tietoja Northwind Traders tietokannassa Yhteenveto lomakkeen luomiseen. Tämä ohjeaihe on osa pidempää sarjaa, jossa selitetään business-sovelluksen rakentaminen Common Data Service-relaatiotietoja. Saat parhaat tulokset Tutustu aiheet tässä järjestyksessä:

1. [Luo order-valikoima](northwind-orders-canvas-part1.md).
2. Luo yhteenveto lomake (**tässä ohjeaiheessa**).
3. [Luo tietoja-valikoiman](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> ![Näytön alueiden määritys](media/northwind-orders-canvas-part1/orders-parts.png)

## <a name="prerequisites"></a>Edellytykset

1. [Asenna Northwind Traders tietokantaa ja sovelluksia](northwind-install.md).
1. Tarkista [pohjaan perustuvan sovelluksen yleiskatsaus](northwind-orders-canvas-overview.md) Northwind Traders varten.
1. [Luo tilauksen valikoiman](northwind-orders-canvas-part1.md) itsellesi tai avaa **Northwind tilaukset (pohjaan perustuvat) - Aloita osa 2** sovelluksen, joka sisältää jo valikoiman.

## <a name="add-a-title-bar"></a>Lisää otsikkorivi

Sovelluksen yläreunassa luoda otsikkorivi, joka mahtuu painikkeita tässä ohjeaiheessa loppuun mennessä.

1. - **Puu näkymän** ruudussa **Screen1** sen varmistamiseksi, että et vahingossa lisäät ohjausobjektin tilauksen valikoiman:

    > [!div class="mx-imgBorder"]
    > ![Valitse Screen1 puunäkymässä](media/northwind-orders-canvas-part2/titlebar-01.png)

1. Käyttöön **Lisää** -välilehden **nimen** lisätä [ **nimen** ](controls/control-text-box.md) ohjausobjekti:

    > [!div class="mx-imgBorder"]
    > ![Lisää selite](media/northwind-orders-canvas-part2/titlebar-02.png)

    Uusi selite näytetään vain kerran, valikoiman yläpuolelta. Jos se tulee näkyviin valikoiman jokaisen kohteen, poistaa ensimmäisen esiintymän nimen, varmista, että näytön valitaan (kuten edellisessä vaiheessa kuvataan) ja Aseta otsikon uudelleen.

1. Siirrä ja muuta ulottuvan näytön yläreunan uusi nimi:

    > [!div class="mx-imgBorder"]
    > ![Siirrä ja muuta selite](media/northwind-orders-canvas-part2/titlebar-03.png)

1. Kaksoisnapsauta otsikon teksti ja kirjoita sitten **Northwind tilaukset**.

    Vaihtoehtoisesti muokata **tekstin** ominaisuus kaavarivillä saman tuloksen:

    > [!div class="mx-imgBorder"]
    > ![Muuta otsikkoriviä](media/northwind-orders-canvas-part2/titlebar-04.png)

1. Valitse **aloitus** Muotoile otsikon-välilehdessä:
    - Fontin kokoa 24 osoittaa.
    - Lihavoi teksti.
    - Tee teksti valkoinen.
    - Keskitä teksti.
    - Lisää tummansinistä täytön taustalla.

    > [!div class="mx-imgBorder"]
    > ![Aloitus-välilehden muotoiluasetukset](media/northwind-orders-canvas-part2/titlebar-05.png)

## <a name="add-an-edit-form-control"></a>Muokkaa-lomake-ohjausobjektin lisääminen

Tässä osassa voit lisätä ohjausobjekteja näyttämään käyttäjä valitsee valikoiman tilauksen yhteenveto.

1. Käyttöön **Lisää** Lisää-välilehdessä [ **muokkauslomake** ](controls/control-form-detail.md) ohjausobjekti:

    > [!div class="mx-imgBorder"]
    > ![Muokkaa-lomake-ohjausobjektin lisääminen](media/northwind-orders-canvas-part2/form-01.png)

    Oletusarvoisesti lomakkeen näkyy vasemmassa yläkulmassa, jossa muita ohjausobjekteja voi vaikeuttaa löytää:

    > [!div class="mx-imgBorder"]
    > ![Muokkaa lomaketta-ohjausobjektin oletussijainti](media/northwind-orders-canvas-part2/form-02.png)

1. Siirrä lomaketta ja muuta sen kattamaan otsikkorivin alapuolella näytön oikeassa yläkulmassa:

    > [!div class="mx-imgBorder"]
    > ![Siirrä ja muuta muokkaa lomake-ohjausobjekti](media/northwind-orders-canvas-part2/form-03.png)

1. Määritä kaavarivillä **DataSource** -ominaisuuden arvoksi:

    ```powerapps-dot
    Orders
    ```

    > [!div class="mx-imgBorder"]
    > ![Muokkaa lomakkeen ohjausobjektin DataSource-ominaisuudeksi asetettu](media/northwind-orders-canvas-part2/form-04.png)

    Voit määrittää saman ominaisuuden **ominaisuudet** välilehti lähellä oikeaa reunaa, mutta tätä lähestymistapaa Lisää kenttiä, joita et tarvitse lomakkeeseen. Jos käytät kaavariviä, lomake on tyhjä.

## <a name="add-and-arrange-fields"></a>Lisää ja Järjestä kentät

1. - **Ominaisuudet** lähellä oikeaa reunaa, valitse välilehti **Muokkaa kenttiä** avaamiseen **kentät** ruudussa:

    > [!div class="mx-imgBorder"]
    > ![Avaa kentät-ruudussa](media/northwind-orders-canvas-part2/form-05.png)

1. - **Kentät** ruudussa **Lisää kenttä**, ja valitse sitten valintaruudut **asiakkaan** ja **työntekijän** kentät.

    > [!div class="mx-imgBorder"]
    > ![Lisää asiakkaan ja työntekijä-kenttiä Muokkaa lomake-ohjausobjekti](media/northwind-orders-canvas-part2/form-06.png)

1. Vieritä alaspäin, kunnes nämä kentät näkyvät ja valitse sitten niiden valintaruudut:

    - **Muistiinpanot**
    - **Tilauksen päivämäärä**
    - **Numero**
    - **Tilauksen tila**
    - **Maksettu päivämäärä**

    > [!div class="mx-imgBorder"]
    > ![Lisää viisi kenttää Muokkaa lomake-ohjausobjekti](media/northwind-orders-canvas-part2/form-07.png)

1. Alareunassa **kentät** ruudussa **Lisää**, ja sulje sitten **kentät** ruudussa.

    Lomake näyttää seitsemän kentät:

    > [!div class="mx-imgBorder"]
    > ![Muokkaa lomakkeen ohjausobjekti näyttää seitsemän kentät](media/northwind-orders-canvas-part2/form-08.png)

    > [!NOTE]
    > Minkä tahansa kentän näkyy punainen virhe-kuvake, jos ongelma saattanut, kun tietojen haun lähteestä. Voit ratkaista tämän ongelman päivittämällä tiedot:
    >
    > 1. Valitse **Näytä**-välilehdessä **Tietolähteet**.
    > 1. - **Tietojen** ruudussa **tietolähteet**.
    > 1. Kohdan **tilaukset**, valitse kolme pistettä (...), valitse **Päivitä**, ja sulje sitten **tietojen** ruudussa.
    >
    > Jos asiakkaan tai työntekijän nimi yhdistelmäruutu näyttää edelleen virhe, tarkista **ensisijainen tekstin** ja **käyttämällä SearchField** kunkin valitsemalla sen ja avaamalla ruudun **tietojen** ruutu. -Asiakas-ruudun molempiin kenttiin on asetettava **nwind_company**. Työntekijän-ruudun molempiin kenttiin on asetettava **nwind_lastname**.

1. Kun lomake on valittuna, Muuta lomakkeen sarakkeiden määrä 3 12 **ominaisuudet** välilehti lähellä oikeaa reunaa.

    Tässä vaiheessa lisää joustavuutta, kuten Järjestä kentät:

    > [!div class="mx-imgBorder"]
    > ![Muuta sitten Muokkaa lomakkeen ohjausobjektin sarakkeiden määrä](media/northwind-orders-canvas-part2/form-08b.png)

    Monta Käyttöliittymän suunnitteluista riippuvaisia 12 sarakkeen asettelut, koska ne tasaisesti mahtuu rivien 1, 2, 3, 4, 6 ja 12 ohjausobjekteja. Tässä aiheessa luot rivit, jotka sisältävät 1, 2 tai 4 ohjausobjekteja.

1. Siirtäminen ja koon muuttaminen kentät vetämällä niiden kahvoista tavalliseen tapaan muun ohjausobjektin siten, että kukin rivi sisältää korttien tiedot ovat määritetyssä järjestyksessä:

    - Ensimmäisellä rivillä: **Tilausnumero**, **tilauksen tila**, **Tilauspäivä**, ja **maksettu päivämäärä**
    - Toinen rivi: **Asiakkaan** ja **työntekijä**
    - Kolmas rivi: **Muistiinpanot**

    > [!NOTE]
    > Olet ehkä helpompi leventää **huomautuksia**, **asiakkaan**, ja **työntekijän** tietojen kortit, ennen kuin voit järjestää ne.

    > [!div class="mx-imgBorder"]
    > ![Siirrä ja muuta kentät](media/northwind-orders-canvas-part2/form-rearrange.gif)

    Lisätietoja siitä, miten voit järjestää lomakkeen kenttien: [Tutustu tietolomakkeen asetteluun pohjaan perustuvat sovellukset-](working-with-form-layout.md).

## <a name="hide-time-controls"></a>Piilota ohjausobjektien

Tässä esimerkissä sinun ei tarvitse päivämääräkentät aika osia, koska kyseinen taso askelväliä voi heikentää käyttäjä. Jos poistat ne, kaavoissa, jotka ovat riippuvaisia näiden ohjausobjektien päivitettävä päivämääräarvot tai määrittää toisen ohjausobjektin sijainnin tiedot-kortti saattaa aiheuttaa ongelmia. Sen sijaan piilottaa aika ohjausobjektit määrittämällä niiden **näkyvissä** ominaisuus.

1. - **Puu näkymän** ruudussa **tilauspäivämäärän** tietokortti.

    Kortti voi olla eri nimi, mutta se sisältää **tilauspäivämäärän**.

1. Valitse tunnin, minuutin ja erotinmerkkiä ohjausobjektit VAIHTO-näppäintä pohjassa **tilauspäivämäärän** tietokortti.

    > [!div class="mx-imgBorder"]
    > ![Valitse aika ohjausobjektit tilauspäivämäärän kortissa](media/northwind-orders-canvas-part2/form-09.png)

1. Määritä niiden **näkyvissä** ominaisuudeksi **false**.

    Kaikkia valittuja ohjausobjekteja kadota muodossa:

    > [!div class="mx-imgBorder"]
    > ![Määritä Visible-ominaisuuden arvoksi false.](media/northwind-orders-canvas-part2/form-10.png)

1. Muuta kokoa [ **päivämäärävalitsin** ](controls/control-date-picker.md) täydellisen päivämäärän ohjausobjektin:

    > [!div class="mx-imgBorder"]
    > ![Muuta päivämäärävalitsimen](media/northwind-orders-canvas-part2/form-11.png)

    Seuraavaksi toista viimeisten muutaman vaiheet **maksettu päivämäärä** kenttä.

1. - **Puu näkymän** ruudussa aika ohjausobjektit **maksettu päivämäärä** tietokortti:

    > [!div class="mx-imgBorder"]
    > ![Valitse ohjausobjekti kortissa maksettu päivämäärä](media/northwind-orders-canvas-part2/form-12.png)

1. Määritä valittuja ohjausobjekteja **näkyvissä** ominaisuudeksi **false**:

    > [!div class="mx-imgBorder"]
    > ![Määritä Visible-ominaisuuden arvoksi false.](media/northwind-orders-canvas-part2/form-13.png)

1. Päivämäärävalitsin-kokoa **päivämäärä maksettu** kortti:

    > [!div class="mx-imgBorder"]
    > ![Muuta päivämäärävalitsimen](media/northwind-orders-canvas-part2/form-14.png)

## <a name="connect-the-order-gallery"></a>Yhdistä order-valikoima

1. - **Puu näkymän** ruudussa Kutista löytää tilauksen valikoiman nimi muodossa ja, tarvittaessa nimeä sen **Gallery1**.

1. Määritä Yhteenveto lomakkeen **kohteen** ominaisuudeksi seuraava lauseke:

    ```powerapps-dot
    Gallery1.Selected
    ```

    > [!div class="mx-imgBorder"]
    > ![Määrittää kohteen ominaisuuden arvo](media/northwind-orders-canvas-part2/form-15.png)

    Lomake on haluamassasi järjestyksessä sovelluksen käyttäjä valitsee luettelon yhteenveto.

    > [!div class="mx-imgBorder"]
    > ![Valitse tilaus luetteloa ja näyttää sen yleiskatsaus muodossa](media/northwind-orders-canvas-part2/form-select.gif)

## <a name="replace-a-data-card"></a>Korvaa tietojen kortti

**Tilausnumero** on tunnus, joka Common Data Service-määrittää automaattisesti, kun tietue luodaan. Tämä kenttä on [ **Tekstisyöte** ](controls/control-text-input.md) ohjausobjektin oletusarvon mukaan, mutta se korvataan ja selite niin, että käyttäjä voi muokata tässä kentässä.

1. Valitse lomake, valitse **Muokkaa kenttiä** - **ominaisuudet** välilehti lähellä oikeaa reunaa ja valitse sitten **tilausnumero** kenttä:

    > [!div class="mx-imgBorder"]
    > ![Valitse tilauksen numerokenttää](media/northwind-orders-canvas-part2/alt-01.png)

1. Avaa **ohjausobjekti tyyppi** luettelo:

    > [!div class="mx-imgBorder"]
    > ![Avaa ** tyyppi ** luettelo](media/northwind-orders-canvas-part2/alt-02.png)

1. Valitse **Näytä teksti** tietokortti:

    > [!div class="mx-imgBorder"]
    > ![Valitse ** tekstin ** tietojen kortti](media/northwind-orders-canvas-part2/alt-02b.png)

1. Sulje **kentät** ruudussa.

    Käyttäjä voi enää muuttaa tilausnumero:

    > [!div class="mx-imgBorder"]
    > ![Numero on vain luku-tilassa](media/northwind-orders-canvas-part2/alt-03.png)

1. Valitse **aloitus** muuttaa 20 pisteeseen tilausnumero fonttikokoa niin, että kenttä on helpompi löytää-välilehdessä:

    > [!div class="mx-imgBorder"]
    > ![Muuta tilausnumero fonttikokoa](media/northwind-orders-canvas-part2/alt-04.png)

## <a name="use-a-many-to-one-relationship"></a>Käytä monta yhteen-suhde

**Tilaukset** entiteetillä on monta-yhteen suhdetta **työntekijät** entiteetin: kullakin työntekijällä voit luoda useita tilauksia, mutta kunkin tilauksen voidaan määrittää vain yhdelle työntekijälle. Kun käyttäjä valitsee työntekijä [ **yhdistelmäruutu** ](controls/control-combo-box.md) ohjausobjektin, sen **valittu** ominaisuus tarjoaa kyseisen työntekijän koko tietue **työntekijät**  entiteetin. Näin ollen voit määrittää [ **kuvan** ](controls/control-image.md) ohjausobjekti näyttämään haluamasi työntekijän kuvan käyttäjä valitsee yhdistelmäruudun.

1. Valitse **työntekijän** tietokortti:

    > [!div class="mx-imgBorder"]
    > ![Valitse työntekijän tietokortti](media/northwind-orders-canvas-part2/employee-01.png)

1. Tässä **lisäasetukset** lähellä oikeaa reunaa välilehdeltä tiedot Avaa kortin lukitus jotta voit muokata kaavoja, jotka olivat aiemmin vain luku-tilassa:

    > [!div class="mx-imgBorder"]
    > ![Työntekijän tietoja kortin lukituksen avaaminen](media/northwind-orders-canvas-part2/employee-02.png)

1. Vähennä tietokortti, tehdäksemme työntekijän kuva yhdistelmäruudun leveys:

    > [!div class="mx-imgBorder"]
    > ![Yhdistelmäruutu ohjausobjektin koon](media/northwind-orders-canvas-part2/employee-03b.png)

1. Valitse **Lisää** -välilehden **Media** > **kuvan**:

    > [!div class="mx-imgBorder"]
    > ![Lisää kuva](media/northwind-orders-canvas-part2/employee-04.png)

    Kuva näkyy tietokortti, joka laajentaa sen mukaisesti:

    > [!div class="mx-imgBorder"]
    > ![Työntekijän tietoja kortin, jossa kuva-ohjausobjekti](media/northwind-orders-canvas-part2/employee-05.png)

1. Muuta kuvan kokoa ja siirrä se yhdistelmäruudun oikealla:

    > [!div class="mx-imgBorder"]
    > ![Siirrä ja muuta kuva-ohjausobjektin](media/northwind-orders-canvas-part2/employee-06.png)

1. Määritä **kuvan** ominaisuudeksi tämä kaava numero DataCardValue loppuun korvaamalla tarvittaessa:

    ```powerapps-dot
    DataCardValue7.Selected.Picture
    ```

    > [!div class="mx-imgBorder"]
    > ![Määrittää kuvan Image-ominaisuus](media/northwind-orders-canvas-part2/employee-07.png)

    Valitun työntekijän kuva näkyy.

1. Kun pidät Alt-näppäintä, valitse eri työntekijä yhdistelmäruudussa vahvistaaksesi, että kuva muuttuu.

    > [!div class="mx-imgBorder"]
    > ![Valitse työntekijä näyttää kyseisen työntekijän kuva](media/northwind-orders-canvas-part2/employee-select.gif)

## <a name="add-a-save-icon"></a>Tallenna lisäämiskuvake

1. - **Puu näkymän** ruudussa **Screen1**, ja valitse sitten **Lisää** > **kuvakkeet**  >  **Tarkista**:

    > [!div class="mx-imgBorder"]
    > ![Lisää valintamerkki kuvake](media/northwind-orders-canvas-part2/save-01.png)

    [ **Tarkista** ](controls/control-shapes-icons.md) kuvake näkyy vasemmassa yläkulmassa oletusarvon mukaan, jossa muita ohjausobjekteja voi tehdä kuvake vaikea löytää:

    > [!div class="mx-imgBorder"]
    > ![Oletussijainti kuvake](media/northwind-orders-canvas-part2/save-02.png)

1. Käyttöön **aloitus** muuttaa-välilehden **väri** valkoinen, kuvakkeen kokoa ja siirrä se otsikkorivin oikean reunan lähellä olevaa kuvaketta ominaisuus:

    > [!div class="mx-imgBorder"]
    > ![Määritä väriä, kokoa ja Tallenna sijainti kuvake](media/northwind-orders-canvas-part2/save-03.png)

1. - **Puu näkymän** ruudussa Vahvista, että lomakkeen nimi on **Form1**, ja määritä sitten kuvakkeen **OnSelect** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    SubmitForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä Tallenna kuvakkeen OnSelect-ominaisuus](media/northwind-orders-canvas-part2/save-04.png)

    Kun käyttäjä valitsee kuvakkeen, [ **SubmitForm** ](functions/function-form.md) funktio kerää muodossa muutettu arvoja ja lähettää ne tietolähteeseen. Pistettä maaliskuuta näytön yläreunassa, kun tiedot lähetetään ja tilauksen valikoima päivittyy muutokset, kun prosessi on valmis.

1. Määritä kuvakkeen **DisplayMode** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    If( Form1.Unsaved, DisplayMode.Edit, DisplayMode.Disabled )
    ```

    > [!div class="mx-imgBorder"]
    > ![Kuvakkeen DisplayMode-ominaisuuden](media/northwind-orders-canvas-part2/save-05.png)

    Jos lomake-kaikki muutokset on tallennettu, kuvake on poistettu käytöstä, ja se näkyy **DisabledColor**, jonka määrittää Seuraava.

1. Määritä kuvakkeen **DisabledColor** ominaisuudeksi tämä arvo:

    ```powerapps-dot
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Kuvakkeen DisabledColor ominaisuuden](media/northwind-orders-canvas-part2/save-06.png)

    Käyttäjä voi tallentaa muutoksia tilaus valitsemalla Tarkista-kuvakkeen, joka on poistettu käytöstä ja himmennettynä, kunnes käyttäjä tekee muutoksen jälkeen:

    > [!div class="mx-imgBorder"]
    > ![muutosten tallentaminen](media/northwind-orders-canvas-part2/save-submit.gif)

## <a name="add-a-cancel-icon"></a>Lisää Peruuta-kuvaketta

1. Valitse **Lisää** -välilehden **kuvakkeet** > **Peruuta**:

    > [!div class="mx-imgBorder"]
    > ![Lisää Peruuta-kuvaketta](media/northwind-orders-canvas-part2/save-07.png)

    Kuvake näkyy vasemmassa yläkulmassa oletusarvoisesti, jossa muita ohjausobjekteja voi tehdä kuvake vaikea löytää:

    > [!div class="mx-imgBorder"]
    > ![Peruuta-kuvaketta oletussijainti](media/northwind-orders-canvas-part2/save-08.png)

1. - **Aloitus** -välilehdessä olevaa kuvaketta muuttaa **väri** valkoinen, kuvakkeen kokoa ja siirrä se tarkistus-kuvake vasemmalta ominaisuus:

    > [!div class="mx-imgBorder"]
    > ![Muuta väriä, kokoa ja sijaintia Peruuta-kuvaketta](media/northwind-orders-canvas-part2/save-09.png)

1. Määritä Peruuta-kuvaketta **OnSelect** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    ResetForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Peruuta-kuvaketta OnSelect-ominaisuuden](media/northwind-orders-canvas-part2/save-10.png)

    [ **ResetForm** ](functions/function-form.md) funktio Hylkää kaikki muutokset lomakkeeseen, joka palauttaa sen alkuperäiseen tilaan.

1. Määritä Peruuta-kuvaketta **DisplayMode** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    If( Form1.Unsaved Or Form1.Mode = FormMode.New, DisplayMode.Edit, DisplayMode.Disabled )
    ```

    > [!div class="mx-imgBorder"]
    > ![Peruuta-kuvaketta DisplayMode-ominaisuuden](media/northwind-orders-canvas-part2/save-11.png)

    Tämä kaava eroaa hieman se tarkistus-kuvakkeen. Peruuta-kuvaketta on poistettu käytöstä, jos kaikki muutokset on tallennettu tai lomake on **uusi** tilan, joka ottaa Seuraava. Tässä tapauksessa **ResetForm** hylkää uuden tietueen.

1. Määritä Peruuta-kuvaketta **DisabledColor** ominaisuudeksi tämä arvo:

    ```powerapps-dot
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Peruuta-kuvaketta DisabledColor ominaisuuden](media/northwind-orders-canvas-part2/save-12.png)

    Käyttäjä peruuttaa tilauksen muutokset ja tarkista ja Peruuta-kuvakkeet on poistettu käytöstä ja himmennettynä, jos kaikki muutokset on tallennettu:

    > [!div class="mx-imgBorder"]
    > ![Tallennetaan ja peruutetaan muutokset](media/northwind-orders-canvas-part2/save-cancel.gif)

## <a name="add-an-add-icon"></a>Lisää Lisää-kuvake

1. Valitse **Lisää** -välilehden **kuvakkeet** > **Lisää**.

    > [!div class="mx-imgBorder"]
    > ![Lisää Lisää-kuvake](media/northwind-orders-canvas-part2/save-13.png)

    **Lisää** kuvake näkyy vasemmassa yläkulmassa oletusarvon mukaan, jossa muita ohjausobjekteja voi vaikeuttaa löytää:

    > [!div class="mx-imgBorder"]
    > ![Lisää kuvake oletussijainti](media/northwind-orders-canvas-part2/save-14.png)

1. Käyttöön **aloitus** välilehti, Määritä **väri** Lisää-kuvaketta, valkoinen, kuvakkeen kokoa ja siirrä se vasemmalla puolella Peruuta-kuvaketta ominaisuus:

    > [!div class="mx-imgBorder"]
    > ![Muuta väriä, kokoa ja lisää kuvaketta sijainti](media/northwind-orders-canvas-part2/save-15.png)

1. Määritä lisää kuvakkeen **OnSelect** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    NewForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Lisää kuvake OnSelect-ominaisuuden](media/northwind-orders-canvas-part2/save-15b.png)

    [ **NewForm** ](functions/function-form.md) funktio näyttää tyhjä tietue muodossa.  

1. Määritä lisää kuvakkeen **DisplayMode** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    If( Form1.Unsaved Or Form1.Mode = FormMode.New, DisplayMode.Disabled, DisplayMode.Edit )
    ```

    > [!div class="mx-imgBorder"]
    > ![Lisää kuvake DisplayMode-ominaisuuden](media/northwind-orders-canvas-part2/save-16.png)

    Kaava poistaa käytöstä näissä olosuhteissa Lisää-kuvaketta:

    - Käyttäjä tekee muutoksia, mutta ei tallenna tai Peruuta, joka on Vastakkaiset toiminta-valintaruutu ja Peruuta-kuvakkeet.
    - Käyttäjä valitsee Lisää-kuvaketta, mutta ei tee muutoksia.

1. Määritä lisää kuvakkeen **DisabledColor** ominaisuudeksi tämä arvo:

    ```powerapps-dot
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Lisää kuvake DisabledColor ominaisuuden](media/northwind-orders-canvas-part2/save-17.png)

    Käyttäjä voi luoda tilauksen, jos hän ei tehdä muutoksia tai ne tallentaa tai peruuttaa ne tehdyt muutokset. (Jos käyttäjä valitsee tämän kuvakkeen, hän voi valita sitä uudelleen, kunnes ne yhden tai useamman muutokset ja Tallenna tai Peruuta muutokset):

    > [!div class="mx-imgBorder"]
    > ![Tilauksen luominen](media/northwind-orders-canvas-part2/save-new.gif)

> [!NOTE]
> Jos luot ja tallennat tilauksen, joudut ehkä vierittämään tilauksen valikoima näyttämään uuden tilauksen. Se ei ole yhteensä hinta, koska et ole lisännyt mitään Tilaustiedot vielä.

## <a name="add-a-trash-icon"></a>Lisää Roskakori-kuvaketta

1. Valitse **Lisää** -välilehden **kuvakkeet** > **roskakori**.

    > [!div class="mx-imgBorder"]
    > ![Lisää roskakorikuvake](media/northwind-orders-canvas-part2/save-18.png)

    **Roskakori** kuvake näkyy vasemmassa yläkulmassa oletusarvon mukaan, jossa muita ohjausobjekteja voi vaikeuttaa löytää:

    > [!div class="mx-imgBorder"]
    > ![Oletussijainti Roskakorin kuvaketta](media/northwind-orders-canvas-part2/save-19.png)

1. - **Aloitus** välilehdeltä muuttaa roskakorin kuvaketta **väri** ominaisuuden valkoinen, kuvakkeen kokoa ja siirrä se vasemmalta puolelta Lisää kuvaketta:

    > [!div class="mx-imgBorder"]
    > ![Muuta väriä, kokoa ja sijaintia Roskakorin kuvaketta](media/northwind-orders-canvas-part2/save-20.png)

1. Määritä Roskakorin kuvaketta **OnSelect** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    Remove( Orders, Gallery1.Selected )
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä Roskakorin kuvaketta OnSelect-ominaisuus](media/northwind-orders-canvas-part2/save-21.png)

    [ **Poistaa** ](functions/function-remove-removeif.md) -funktio poistaa tietueen tietolähteestä. Tässä kaavassa funktio poistaa tietueen, joka valitaan tilauksen valikoimassa. Koska lomake näyttää lisätietoja tietuetta, jotta käyttäjä helpommin tunnistaa tietueen, joka poistaa kaavan lähellä yhteenvetona (ei valikoiman tilauksen) näkyy Roskakorin kuvaketta.

1. Määritä Roskakorin kuvaketta **DisplayMode** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    If( Form1.Mode = FormMode.New, DisplayMode.Disabled, DisplayMode.Edit )
    ```

    > [!div class="mx-imgBorder"]
    > ![Roskakorin kuvaketta DisplayMode-ominaisuuden](media/northwind-orders-canvas-part2/save-22.png)

    Tämä kaava poistaa käytöstä Roskakorin kuvaketta, jos käyttäjä on luomassa tietuetta. Ennen kuin käyttäjä tallentaa tietueen **poistaa** funktiolla ei ole tietuetta, poista.

1. Määritä Roskakorin kuvaketta **DisabledColor** ominaisuudeksi tämä arvo:

    ```powerapps-dot
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![DisabledColor ominaisuuden Roskakori-kuvaketta](media/northwind-orders-canvas-part2/save-23.png)

    Käyttäjä voi poistaa tilaus.

    > [!div class="mx-imgBorder"]
    > ![Poistetaan tilauksia](media/northwind-orders-canvas-part2/save-delete.gif)

## <a name="summary"></a>Yhteenveto

Recap, lisätä lomakkeen, jonka käyttäjä voi näyttää ja muokata kunkin tilauksen yhteenveto ja käyttää näitä elementtejä:

- Lomake, joka näyttää tietoja **tilaukset** entiteetin: **Form1.DataSource =** `Orders`
- Lomakkeen ja tilauksen valikoiman välinen yhteys: **Form1.Item =** `Gallery1.Selected`
- Vaihtoehtoinen ohjausobjektille **tilausnumero** kenttä: **Näytä teksti**
- Näytä kuva työntekijän monta yhteen suhde **työntekijän** tietokortti: `DataCardValue1.Selected.Picture`
- Kuvake muutosten tallentamiseksi tilauksen: `SubmitForm( Form1 )`
- Kuvakkeen Peruuta tilaus muutokset: `ResetForm( Form1 )`
- Kuvakkeen tilauksen luominen: `NewForm( Form1 )`
- Kuvakkeen poistaa tilauksen: `Remove( Orders, Gallery1.Selected )`

## <a name="next-step"></a>Seuraava vaihe

Seuraavassa aiheessa lisäät toisen valikoima näyttämään jokaisen order tuotteet ja muutat näiden tietojen avulla [ **Patch** ](functions/function-patch.md) funktio.

> [!div class="nextstepaction"]
> [Luo tietoja-valikoiman](northwind-orders-canvas-part3.md)

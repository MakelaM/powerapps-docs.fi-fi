---
title: Luo pohjaan perustuva sovellus tilauksen valikoiman | Microsoft Docs
description: Luo tilauksen valikoiman pohjaan perustuvan sovelluksen Northwind Traders tietojen hallintaan
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
ms.openlocfilehash: 94d6c104cb888bb13f3724231d7891d622f5377b
ms.sourcegitcommit: e85072f7a80da308c4caabe20adbf2509588ca57
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/07/2019
ms.locfileid: "66761001"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-an-order-gallery-in-a-canvas-app"></a>Luo pohjaan perustuva sovellus order-valikoima

Noudata vaiheittaiset ohjeet luoda tilauksen valikoiman pohjaan perustuvan sovelluksen hallintaan kuvitteellisia tietoja Northwind Traders tietokannassa. Tämä ohjeaihe on osa pidempää sarjaa, jossa selitetään business-sovelluksen rakentaminen Common Data Service-relaatiotietoja. Saat parhaat tulokset Tutustu aiheet tässä järjestyksessä:

1. Luo order-valikoima (**tässä ohjeaiheessa**).
1. [Luo yhteenveto lomake](northwind-orders-canvas-part2.md).
1. [Luo tietoja-valikoiman](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> ![Näytön alueiden määritys](media/northwind-orders-canvas-part1/orders-parts.png)

## <a name="prerequisites"></a>Edellytykset

- [Asenna Northwind Traders tietokantaa ja sovelluksia](northwind-install.md).
- Lue [yleiskatsaus kangas-sovellus](northwind-orders-canvas-overview.md) Northwind Traders varten.

## <a name="create-a-blank-app"></a>Tyhjän sovelluksen luominen

1. [Kirjaudu sisään Powerappsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), ja luo tyhjä tablettisovellus.

    > [!div class="mx-imgBorder"]
    > ![Kangas-sovellus tyhjä ruutu](media/northwind-orders-canvas-part1/start-01.png)

1. Nimeä sovelluksesi haluamasi tapaan, ja valitse sitten **Luo**.

    > [!div class="mx-imgBorder"]
    > ![Tyhjä-valintaikkunasta kangas-sovellus](media/northwind-orders-canvas-part1/start-02.png)

    PowerApps Studio avautuu siten, että voit lisätä tietolähteiden ja ohjausobjektien sovelluksesi:

    > [!div class="mx-imgBorder"]
    > ![PowerApps Studio](media/northwind-orders-canvas-part1/start-03.png)

1. Ota käyttöön [kokeellinen ominaisuus](working-with-experimental.md) näyttämään suoraan kaavarivin kaavan tulos.

    1. Valitse **tiedoston** -valikosta **sovellusasetukset**, ja valitse sitten **lisäasetukset**.
    1. Vieritä alas-ominaisuuksien luettelo ja ottaa käyttöön **käyttöön kaavarivin tulosnäkymään**:

        > [!div class="mx-imgBorder"]
        > ![Kokeellinen ominaisuuksien luettelo](media/northwind-orders-canvas-part1/start-04.png)

1. Valitse vasemmassa yläkulmassa, palaa puhtaalta pöydältä taaksepäin osoittava nuoli.

## <a name="add-the-data"></a>Lisää tiedot

1. Käyttöön **Näytä** -välilehden **tietolähteet**, ja valitse sitten **Lisää tietolähde** - **tietojen** ruudussa:

    > [!div class="mx-imgBorder"]
    > ![Valitse näkymä, tietolähteiden, Lisää tietolähde](media/northwind-orders-canvas-part1/datasource-01.png)

1. Valitse **Common Data Service-** .

    Jos **Common Data Service-** ei näy, yhteyksien luettelo **uusi yhteys**, ja lisää se.

    > [!div class="mx-imgBorder"]
    > ![Yhteyksien luettelo](media/northwind-orders-canvas-part1/datasource-02.png)

1. Valitse **Valitse entiteetti**, tyyppi **tilaukset**, valitse **tilaukset** valintaruutu, ja valitse sitten **Yhdistä**:

    > [!div class="mx-imgBorder"]
    > ![Entiteettien luettelo](media/northwind-orders-canvas-part1/datasource-03.png)

    Olet lisännyt **tilaukset** sovelluksesi tietolähde:

    > [!div class="mx-imgBorder"]
    > ![Tietoruutu](media/northwind-orders-canvas-part1/datasource-04.png)

    **Tilaukset** entiteetti sisältää useita kenttiä seuraavista tyypeistä:

    > [!div class="mx-imgBorder"]
    > ![Tilaukset-entiteetin kenttien luettelo](media/northwind-orders-canvas-part1/datasource-05.png)

    Jokaisella kentällä on **näyttönimi** ja **nimi**, jota kutsutaan myös looginen nimi. Molemmat nimet viittaavat samaan asiaan. Yleensä käytät näyttönimi kun rakennat sovelluksen, mutta joissakin tapauksissa edellyttävät enemmän suojatuilta **nimi**, kuten toimintosarjassa.

1. Sulje PowerApps Studio **tietojen** ruutu valitsemalla sen oikeassa yläkulmassa olevaa Sulje (x)-kuvaketta.

## <a name="create-the-order-gallery"></a>Luo order-valikoima

1. Käyttöön **Lisää** -välilehden **valikoiman** > **tyhjä, pysty** Lisää [ **valikoiman** ](controls/control-gallery.md)ohjausobjektin, jossa näkyvät tilaukset.

    > [!div class="mx-imgBorder"]
    > ![INSERT-, valikoiman tyhjä, pysty](media/northwind-orders-canvas-part1/orders-01.png)

1. Kaavarivillä, Määritä valikoiman **kohteet** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Sort( Orders; 'Order Number'; Descending )
    ```

    [ **Lajittele** ](functions/function-sort.md) funktio järjestää luettelossa niin, että uusin tilaus (jolla on suurin tilausnumero) näkyy ensimmäisen.

    > [!div class="mx-imgBorder"]
    > ![Valikoiman Items-ominaisuuden asettaminen](media/northwind-orders-canvas-part1/orders-02.png)

1. - **Ominaisuudet** välilehti lähellä oikeaa reunaa, Avaa **asettelu** luettelo:

    > [!div class="mx-imgBorder"]
    > ![Asettelu-vaihtoehtojen luettelo](media/northwind-orders-canvas-part1/orders-03.png)

1. Valitse valintaluettelossa, **otsikko ja alaotsikko**:

    > [!div class="mx-imgBorder"]
    > ![Valitse asettelu](media/northwind-orders-canvas-part1/orders-04.png)

    Kaksi [ **nimen** ](controls/control-text-box.md) ohjausobjektit on lisätty valikoiman mallipohjaa. Oletusarvoisesti nämä ohjausobjektit sisältävät kaksi saraketta **tilaukset** entiteettiä, joka voit muuttaa seuraava. Valikoiman mallipohjaa replikoidaan pystysuunnassa jokainen tietue entiteetissä.

1. Jos suljettujen **tietojen** ruudussa **Muokkaa** (kohdan **kentät**)- **ominaisuudet** välilehti lähellä oikeaa reunaa.

1. Tässä **tietojen** ruudussa **Title1** (tai Valitse ylemmästä selite valikoiman mallipohjaa).

1. Kaavarivillä, Määritä nimen **tekstin** ominaisuudeksi seuraava lauseke:

    ```powerapps-comma
    "Order " & ThisItem.'Order Number'
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä selitteen otsikon tekstin ominaisuutta](media/northwind-orders-canvas-part1/orders-06.png)

    Tilausnumero tulee näkyviin valikoiman jokaisen kohteen yläreunassa. Valikoima-mallin **ThisItem** antaa käyttöoikeudet kaikki kentät **tilauksen** entiteetin.

1. Tässä **tietojen** ruudussa **Subtitle1** (tai valitse alemmalle otsikolle valikoiman mallipohjaa):

    > [!div class="mx-imgBorder"]
    > ![Valitse alaotsikko selite](media/northwind-orders-canvas-part1/orders-07.png)

1. Kaavarivillä, Määritä nimen **tekstin** ominaisuudeksi seuraava lauseke:

    ```powerapps-comma
    ThisItem.Customer.Company
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä alaotsikko selitteen tekstin ominaisuutta](media/northwind-orders-canvas-part1/orders-08.png)

    Kun kirjoitat tätä kaavaa, se saattaa näkyä punainen koukeroviiva virhe hetken. Virhe tulee Tyhjennä valitset mitään kaavarivin ulkopuolella ja palaat sitten kaavariville kohdistin. Jos virhe jatkuu tai arvo ei ole näkyvissä, valitse **Näytä** -välilehden **tietolähteet**, ja päivitä sitten **tilaukset** entiteetin valitsemalla kolme pistettä (...) oikeasta tietolähteen nimi.

    Kun määrität **ThisItem.Customer**, olet hyödyntämällä monta yhteen-suhde **tilaukset** ja **asiakkaille** entiteetit ja noudetaan asiakastietueen joka on liitetty kunkin tilauksen. Asiakastietueen, tiedot haetaan **yrityksen** sarakkeen näyttämistä varten.

    Voit näyttää kaikki suhteet- **tilaukset** entiteetin muihin kohteisiin, mukaan lukien **asiakkaan** entiteetin:

    > [!div class="mx-imgBorder"]
    > ![Yhteyksien luettelo](media/northwind-orders-canvas-part1/orders-09.png)

1. Sulje **tietojen** ruutu valitsemalla sen oikeassa yläkulmassa olevaa Sulje (x)-kuvaketta.

## <a name="show-each-orders-status"></a>Näytä kunkin tilauksen tila

Tässä toimenpiteessä lisätään tilaa selitteen valikoimassa ja määritä se näyttää kunkin tilauksen tilan erivärisinä tietojen perusteella.

1. Pienennä mallin valikoiman ensimmäinen selite leveyttä **Title1**:

    > [!div class="mx-imgBorder"]
    > ![Valikoiman mallipohjaa Title1](media/northwind-orders-canvas-part1/status-01.png)

1. Toista edelliset vaiheet toiseksi selitteeksi **Subtitle1**:

    > [!div class="mx-imgBorder"]
    > ![Valikoiman mallipohjaa Subtitle1](media/northwind-orders-canvas-part1/status-02.png)

1. Valikoiman malli (tai ohjausobjektin mallissa) valittuna, valitse **nimen** , **Lisää** välilehti:

    > [!div class="mx-imgBorder"]
    > ![Lisää selite](media/northwind-orders-canvas-part1/status-03.png)

1. Siirrä uusi selite oikealla puolella **Title1** nimi:

    > [!div class="mx-imgBorder"]
    > ![Siirrä ja muuta selite](media/northwind-orders-canvas-part1/status-04.png)

1. Määritä **tekstin** ominaisuudeksi uusi seuraava lauseke:

    ```powerapps-comma
    ThisItem.'Order Status'
    ```

    > [!div class="mx-imgBorder"]
    > ![Aseta Text-ominaisuudeksi](media/northwind-orders-canvas-part1/status-05.png)

    - **Tilaukset** entiteetin **tilauksen tila** kenttä sisältää arvon **tilausten tila** asetusjoukko. Asetusjoukon muistuttaa luettelointi muissa ohjelmointityökaluissa. Jokainen asetusten joukko on määritetty tietokannassa, jotta käyttäjät voivat määrittää vain asetukset, jotka ovat joukko. **Tilausten tila** asetusjoukko on myös yleinen, ei paikallinen, jotta voit käyttää sitä muihin entiteetteihin:

    > [!div class="mx-imgBorder"]
    > ![Tilaukset tila asetusjoukko](media/northwind-orders-canvas-part1/status-06.png)

    Kussakin asetuksessa joukon on nimi, joka tulee näkyviin, jos Näytä selitteessä. Nämä nimet voidaan lokalisoida ja sovellus tunnistaa vaihtoehtoja, onko englanninkielinen käyttäjä valitsee **Apple**, Ranskan käyttäjä valitsee **Pomme**, tai Espanja käyttäjä valitsee **Manzana**. Tästä syystä et voi luoda kaavan, joka on riippuvainen vaihtoehdon-koodattu merkkijono, sillä tässä ohjeaiheessa kerrotaan myöhemmin.

    Kaavoissa ympäröi **tilauksen tila** kanssa heittomerkit, koska se sisältää välilyönti. Kuitenkin nimellä toimii samalla tavalla kuin mikä tahansa muu nimi powerappsissa, kuten **asiakkaan** tai **yrityksen**, does.

1. Valitse **aloitus** välilehdestä 20 pisteiden tila selitteen fontin kokoa ja Tasaa oikealle teksti:

    > [!div class="mx-imgBorder"]
    > ![Muuta fonttikokoa ja tasaus](media/northwind-orders-canvas-part1/status-07.png)

1. Määritä kaavarivillä **väri** ominaisuudeksi tila tämä kaava:

    ```powerapps-comma
    Switch( ThisItem.'Order Status';
        'Orders Status'.Closed; Green;
        'Orders Status'.New; Black;
        'Orders Status'.Invoiced; Blue;
        'Orders Status'.Shipped; Purple
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Ominaisuuden tilan selite väri](media/northwind-orders-canvas-part1/status-08.png)

    Powerappsin estää kaavan, joka on riippuvainen vaihtoehdoissa joukon koodattu merkkijono, sillä tällaiset kaavat saattaa aiheuttaa sopimatonta tulokset, jos asetuksen nimiä ovat lokalisoitu luomista. Sen sijaan **Switch** funktio määrittää värin haluamasi jossain kohdassa esiintyy käyttäjän asetusten perusteella nimen perusteella.

    Käyttämällä tätä kaavaa paikkaan eri tila arvot näkyvät eri värit edellisen graafinen näyttää.

## <a name="display-each-orders-total"></a>Näytä jokaisen order yhteensä

1. Valitse ensimmäinen kohde valikoimassa ja joka on valikoiman mallipohjaa:

    > [!div class="mx-imgBorder"]
    > ![Valitse haluamasi valikoiman mallipohja](media/northwind-orders-canvas-part1/aggregate-01.png)

1. Valitse **Lisää** -välilehden **nimen** Lisää toinen selite:

    > [!div class="mx-imgBorder"]
    > ![Lisää selite](media/northwind-orders-canvas-part1/aggregate-02.png)

1. Siirrä uusi selite, niin, että se näkyy tilan selite:

    > [!div class="mx-imgBorder"]
    > ![Kokoa ja Siirrä uusi otsikko](media/northwind-orders-canvas-part1/aggregate-03.png)

1. Kaavarivillä, Määritä uusi otsikko **tekstin** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Text( Sum( ThisItem.'Order Details'; Quantity * 'Unit Price' ); "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Kaava lasketaan tilauksen kokonaiskustannukset](media/northwind-orders-canvas-part1/aggregate-04.png)

    Tässä kaavassa [ **summa** ](functions/function-aggregates.md) funktio lisää olevien tietueiden **Tilaustiedot** entiteetin, jotka liittyvät jokaiselle tietueelle **tilauksen**entiteetin yksi-moneen-suhteen kautta. Nämä nimikkeiden täytetään jokaisen order ja käytät samalla yksi-moneen-suhde näyttää ja muokata nimikkeiden näytön oikeassa-alueella.

    Tämä kaava näkyy sininen alleviivaus ja [delegointia varoitus](delegation-overview.md) koska Common Data Service ei tue delegointia monimutkaisia koostefunktioita (esimerkiksi summa kertolasku). Voit ohittaa nämä tiedot, koska ei ole tässä esimerkissä tilaus sisältää enemmän kuin 500 nimikkeiden. Jos eri sovelluksen tarvittaessa voit lisätä tämä raja- **sovellusasetukset**.

    [ **Tekstin** ](functions/function-text.md) Tässä kaavassa funktio lisää valuuttamerkin ja muotoilee tuhansia ja desimaalimerkki tuloksen. Sellaisenaan, kaava sisältää kielitunnisteen Yhdysvaltain Englanti ( **[$-en-US]** ) ja dollari symboli ( **$** ). Jos poistat kielitunnisteen, se korvataan yhdessä kieliasetusten perusteella ja otsikko näyttää kyseisen tunnisteen asianmukainen muodoista. Jos jätät dollarin symbolin, otsikko näyttää asianmukaisen valuuttasymbolin käyttäjän asetusten perusteella. Voit kuitenkin pakottaa korvaamalla dollarin symbolin sellaisen, jonka haluat näkyvän eri merkkiä.

1. Valitse **aloitus** välilehdestä uusin nimen fonttikoon muuttaminen 20 osoittaa ja Tasaa oikealle sen tekstiä:

    > [!div class="mx-imgBorder"]
    > ![Muuta fonttikokoa ja selitteen tasaus](media/northwind-orders-canvas-part1/aggregate-05.png)

1. Siirrä valikoimaa näytön vasemman reunan ja Pienennä valikoiman leveyttä Sulje tilaa.

1. Lisää valikoiman korkeutta, jotta se on lähes korkea kuin näytön, mutta jätä hieman tilaa yläreunassa otsikkorivi, johon lisäät seuraavassa aiheessa alussa:

    > [!div class="mx-imgBorder"]
    > ![Siirrä ja muuta valikoiman kokoa](media/northwind-orders-canvas-part1/aggregate-06.png)

## <a name="summary"></a>Yhteenveto

Recap, voit aloittaa luo yhden näytön pohjaan perustuvan sovelluksen lisäämällä order-valikoimassa ja joka sisältää näitä elementtejä:

- Lausekkeen näyttämään tilausnumero: `"Orders " & ThisItem.OrderNumber`
- Monta yhteen-suhde kenttä: `ThisItem.Customer.Company`
- Otsikko, joka sisältää joukon vaihtoehto nimi: `ThisItem.'Order Status'`
- Otsikko, joka muuttaa minkä vaihtoehdon joukon selite näyttää-muodossa: `Switch( ThisItem.'Order Status'; 'Orders Status'.Closed; Green; ...`
- Monimutkainen koostefunktion yksi-moneen-suhteen päälle: `Sum( ThisItem.'Order Details'; Quantity * 'Unit Price' )`

## <a name="next-topic"></a>Seuraavassa aiheessa

Seuraavassa aiheessa lisäämme [ **muokkauslomake** ](controls/control-form-detail.md) ohjausobjekti näyttää ja muokkaa Yhteenveto riippumatta tilauksen käyttäjä valitsee valikoimasta juuri luomasi.

> [!div class="nextstepaction"]
> [Luo yhteenveto lomake](northwind-orders-canvas-part2.md)
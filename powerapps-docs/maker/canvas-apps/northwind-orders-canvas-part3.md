---
title: Yksityiskohta valikoiman luominen kangas sovelluksessa | Microsoft Docs
description: Yksityiskohta valikoiman luominen kangas sovelluksessa Northwind Traders-tietojen hallintaa varten
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
ms.openlocfilehash: 36fc8c552dea9331ff5ffbaa2dca3bdac5508306
ms.sourcegitcommit: 39b32abb19ad9fae98ca986ded6974bcbbb3cea7
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/24/2019
ms.locfileid: "68475429"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-a-detail-gallery-in-a-canvas-app"></a>Yksityiskohta valikoiman luominen kangas sovelluksessa

Noudata vaiheittaisia ohjeita luodaksesi yksityiskohta valikoiman kangas sovellukseen, jotta voit hallita kuvitteellisia tietoja Northwind Traders-tieto kannassa. Tämä ohje aihe on osa sarjaa, jossa kerrotaan, miten voit luoda liiketoiminta sovelluksen relaatio tietoihin Common Data Service. Parhaat tulokset saat tutustumalla seuraaviin aihe isiin:

1. [Luo tilaus valikoima](northwind-orders-canvas-part1.md).
1. [Luo Yhteenveto lomake](northwind-orders-canvas-part2.md).
1. Luo yksityiskohta valikoima (**Tämä aihe**).

> [!div class="mx-imgBorder"]
> ![Näyttö alueiden määrittäminen](media/northwind-orders-canvas-part1/orders-parts.png)

## <a name="prerequisites"></a>Edellytykset

Ennen kuin aloitat tämän ohje aiheen, sinun on asennettava tieto kanta edellä kuvatulla tavalla. Sen jälkeen sinun täytyy joko luoda tilaus valikoima ja yhteenveto lomake tai avata **Northwind-tila ukset (piirto alusta)-BEGIN Part 3-** sovellus, joka sisältää jo kyseisen valikoiman ja kyseisen lomakkeen.

## <a name="create-another-title-bar"></a>Luo toinen otsikko rivi

1. Valitse näytön yläreunassa [**Selite**](controls/control-text-box.md) -ohjaus objekti, joka toimii otsikko rivillä, kopioi se painamalla CTRL-C ja liitä se sitten painamalla CTRL-V:

    > [!div class="mx-imgBorder"]
    > ![Kopioi ja liitä otsikko rivi](media/northwind-orders-canvas-part3/details-01.png)

1. Muuta kopion kokoa ja siirrä se niin, että se näkyy vain yhteenveto-lomakkeessa.

1. Poista teksti kopiosta jommallakummalla seuraavista tavoista:

    - Valitse teksti kaksoisnapsauttamalla sitä ja paina sitten Delete-näppäintä.
    - Valitse selitteen **teksti** -ominaisuudeksi tyhjä merkki jono ( **""** ).

    > [!div class="mx-imgBorder"]
    > ![Poista teksti otsikko rivin kopiosta](media/northwind-orders-canvas-part3/details-02.png)

## <a name="add-a-gallery"></a>Lisää valikoima

1. Lisää [**valikoima**](controls/control-gallery.md) -ohjaus objekti, jossa on **tyhjä pystysuuntainen** rakenne:

    > [!div class="mx-imgBorder"]
    > ![Lisää tyhjä pystysuuntainen valikoima](media/northwind-orders-canvas-part3/details-03.png)

    Vasemmassa yläkulmassa näkyy uusi valikoima, joka näyttää tila uksen tiedot:

    > [!div class="mx-imgBorder"]
    > ![Tila uksen oletus sijainti-tieto valikoima](media/northwind-orders-canvas-part3/details-04.png)

1. Sulje **tiedot** -ruutu ja muuta sitten tieto valikoiman kokoa ja siirrä sitä oikeaan alakulmaan uuden otsikko rivin alapuolelle:

    > [!div class="mx-imgBorder"]
    > ![Tila uksen lopullinen sijainti-tieto valikoima](media/northwind-orders-canvas-part3/details-05.png)

1. Valitse tieto valikoiman **Items** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Gallery1.Selected.'Order Details'
    ```

    > [!div class="mx-imgBorder"]
    > ![Tieto valikoiman Items-ominaisuuden asetukset](media/northwind-orders-canvas-part3/details-06.png)

    Jos näkyviin tulee virhe, varmista, että tilaus valikoiman nimi on **Gallery1** ( **puun näkymä** ruudussa lähellä vasenta reunaa). Jos kyseisellä valikoimalla on eri nimi, nimeä se uudelleen **Gallery1**.

    Olet juuri linkittänyt kaksi galleriaa. Kun käyttäjä valitsee järjestys valikoimassa järjestyksen, kyseinen valinta tunnistaa tietueen Order-entiteetissä. Jos tässä järjestyksessä on yksi tai useampi Line-kohde, Order **-entiteetin** tietue on linkitetty yhteen tai useaan **Order Details** -entiteetin tietueeseen, ja näiden tietueiden tiedot näkyvät tieto valikoimassa. Tämä toiminta kuvastaa yksi moneen-suhdetta, joka luotiin sinulle **tila ukset** -ja **tilaus tiedot** -entiteettien välillä. Kaava, jonka määritit "kävelee", tuo suhde käyttämällä piste merkintää:

    > [!div class="mx-imgBorder"]
    > ![Tila ukset-entiteetin ja Order Details-entiteetin välillä on yksi-moneen-suhde](media/northwind-orders-canvas-part3/schema-orders-rel.png)

## <a name="show-product-names"></a>Näytä tuote nimet

1. Valitse tieto valikoimasta **Lisää kohde Lisää-väli lehdestä** ja valitse valikoiman malli:

    > [!div class="mx-imgBorder"]
    > ![Valitse tieto valikoiman malli](media/northwind-orders-canvas-part3/details-07.png)

    Varmista, että olet valinnut valikoima-mallin itse valikoiman sijaan. Muokkaus alueen tulee olla hieman valikoiman reunan sisäpuolella ja todennäköisesti lyhyempi kuin valikoiman korkeus. Kun lisäät ohjaus objektit tähän malliin, ne toistetaan valikoiman kullekin kohteelle.

1. Lisää selite **Lisää** -väli lehden yksityiskohta valikoimaan.

    Otsikon pitäisi näkyä valikoimassa; Jos näin ei tapahdu, yritä uudelleen, mutta varmista, että valitset valikoiman mallin ennen selitteen lisäämistä.

    > [!div class="mx-imgBorder"]
    > ![Lisää selite yksityiskohta valikoimaan](media/northwind-orders-canvas-part3/details-08.png)

1. Valitse uuden nimen **teksti** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    ThisItem.Product.'Product Name'
    ```

    Jos tekstiä ei tule näkyviin, valitse nuoli järjestys **0901** , joka on lähellä tilaus valikoiman alareunaa.

1. Muuta selitteen kokoa niin, että koko teksti tulee näkyviin:

    > [!div class="mx-imgBorder"]
    > ![Näytä tuotteen nimi tila uksen tiedot-kohdassa](media/northwind-orders-canvas-part3/details-09.png)

    Tämä lauseke kävelee **Order Details** -entiteetin tietueesta. Tietue säilytetään Thisitem-  kohteessa **Order Products** -entiteetin kautta monta yhteen-suhteen kautta:

    > [!div class="mx-imgBorder"]
    > ![Monta yhteen-suhde Order Details-entiteetin ja Order Product-entiteetin välillä](media/northwind-orders-canvas-part3/schema-orderdetails-rel.png)

    **Tuote nimi** kenttä (ja muut kentät, joita aiot käyttää) poimitaan:

    > [!div class="mx-imgBorder"]
    > ![Tila uksen tuotteet-entiteetin kentät](media/northwind-orders-canvas-part3/schema-products-fields.png)

## <a name="show-product-images"></a>Näytä tuote kuvat

1. Lisää **Lisää** -väli lehdessä [**kuva**](controls/control-image.md) -ohjaus objekti tieto valikoimaan:

    > [!div class="mx-imgBorder"]
    > ![Lisää kuva-ohjaus objekti](media/northwind-orders-canvas-part3/details-10.png)

1. Muuta kuvan kokoa ja siirrä sitä vierekkäin.

    > [!TIP]
    > Jos haluat hienosäätää ohjaus objektin kokoa ja sijaintia, ala muuttaa sen kokoa tai siirtää sitä painamatta Alt-näppäintä ja muuta sen kokoa tai Siirrä ohjaus objektia samalla, kun painat Alt-näppäintä:

    > [!div class="mx-imgBorder"]
    > ![Siirrä kuva-ohjaus objekti](media/northwind-orders-canvas-part3/details-11.png)

1. Valitse kuvan **kuva** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    ThisItem.Product.Picture
    ```

    Lauseke viittaa jälleen tuotteeseen, joka liittyy tähän tila uksen yksityiskohtiin, ja poimii näytettävän **kuva** -kentän.

    > [!div class="mx-imgBorder"]
    > ![Näytä tuote kuva](media/northwind-orders-canvas-part3/details-12.png)

1. Pienennä valikoiman mallin korkeutta niin, että kerrallaan näkyy useampi kuin yksi **tilaus tieto** tietue:

    > [!div class="mx-imgBorder"]
    > ![Lyhennä valikoiman mallia](media/northwind-orders-canvas-part3/details-13.png)

## <a name="show-product-quantity-and-cost"></a>Näytä tuotteen määrä ja hinta

1. Lisää **Lisää** -väli lehdessä toinen selite yksityiskohta valikoimaan ja muuta sen kokoa ja Siirrä uusi selite tuote tietojen oikealle puolelle.

1. Valitse uuden nimen **teksti** -ominaisuudeksi tämä lauseke:

    ```powerapps-comma
    ThisItem.Quantity
    ```

    Tämä kaava hakee tiedot suoraan **Order Details** -entiteetistä (suhdetta ei vaadita).

    > [!div class="mx-imgBorder"]
    > ![Näytä tuote määrä](media/northwind-orders-canvas-part3/details-13b.png) 

1. Muuta **Aloitus** -väli lehdellä tämän ohjaus objektin tasaus **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Muuta tasausta](media/northwind-orders-canvas-part3/details-14.png)

1. Lisää **Lisää** -väli lehdessä toinen selite tieto valikoimaan ja muuta sen kokoa ja siirrä selite määrän nimen oikealle puolelle.

1. Valitse uuden nimen **teksti** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Text( ThisItem.'Unit Price'; "[$-en-US]$ #,###.00" )
    ```

    Jos et sisällytä kieli koodia ( **[$-en-US]** ), se lisätään sinulle kielen ja alueen perusteella. Jos käytät eri kieli koodia, sinun kannattaa poistaa **$** heti Close Square-Haka Sulje ( **]** ) ja lisätä sitten oma valuutta-symboli kyseiseen sijaintiin.

    > [!div class="mx-imgBorder"]
    > ![Näytä yksikkö hinta](media/northwind-orders-canvas-part3/details-15.png)

1. Muuta **Aloitus** -väli lehdellä tämän ohjaus objektin tasaus **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Muuta tasausta](media/northwind-orders-canvas-part3/details-16.png)

1. Lisää **Lisää** -väli lehdessä toinen selite-ohjaus objekti tieto valikoimaan ja muuta sen kokoa ja Siirrä uusi selite yksikkö hinnan oikealle puolelle.

1. Valitse uuden nimen **teksti** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Text( ThisItem.Quantity * ThisItem.'Unit Price'; "[$-en-US]$ #,###.00" )
    ```

    Jos et sisällytä kieli koodia ( **[$-en-US]** ), se lisätään puolestasi oman kielesi ja alueesi mukaan. Jos koodi on erilainen, sinun kannattaa käyttää omaa valuutta symbolia **$** heti Close Square kiinnike ( **]** )-kohteen sijaan.

    > [!div class="mx-imgBorder"]
    > ![Näytä kokonaishinta](media/northwind-orders-canvas-part3/details-17.png)

1. Muuta **Aloitus** -väli lehdellä tämän ohjaus objektin tasaus **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Muuta tasausta](media/northwind-orders-canvas-part3/details-18.png)

    Olet lisännyt ohjaus objektin tieto valikoimaan nyt.

1. Varmista, että tieto valikoima ei ole enää valittuna, valitsemalla **puunäkymä** -ruudussa **Screen1** .

## <a name="add-text-to-the-new-title-bar"></a>Lisää teksti uuteen otsikko riville

1. Lisää toinen selite näyttöön **Lisää** -väli lehdessä:

    > [!div class="mx-imgBorder"]
    > ![Lisää selite](media/northwind-orders-canvas-part3/details-19.png)

1. Muuta uuden selitteen kokoa ja siirrä se toisen otsikko rivin tuotteiden kuvien yläpuolelle ja muuta sitten **Aloitus** -väli lehden tekstin väriksi valkoinen.

1. Kaksoisnapsauta otsikon tekstiä ja kirjoita sitten **tuote**:

    > [!div class="mx-imgBorder"]
    > ![Muuta otsikon teksti tuotteeksi](media/northwind-orders-canvas-part3/details-20.png)

1. Kopioi ja liitä tuotteen nimi ja muuta sen kokoa ja siirrä kopio määrä-sarakkeen yläpuolelle.

1. Kaksoisnapsauta uuden nimen tekstiä ja kirjoita sitten **määrä**:

    > [!div class="mx-imgBorder"]
    > ![Muuta otsikon teksti määräksi määrä](media/northwind-orders-canvas-part3/details-21.png)

1. Kopioi ja liitä määrän nimi ja muuta sen kokoa ja siirrä kopio yksikkö hinta-sarakkeen yläpuolelle.

1. Kaksoisnapsauta uuden nimen tekstiä ja kirjoita sitten **yksikkö hinta**:

    > [!div class="mx-imgBorder"]
    > ![Muuta otsikon teksti yksikkö hinnaksi](media/northwind-orders-canvas-part3/details-22.png)

1. Kopioi ja liitä yksikkö hinnan nimi ja muuta sen kokoa ja siirrä kopio laajennetun hinnan sarakkeen yläpuolelle.

1. Kaksoisnapsauta uuden nimen tekstiä ja kirjoita sitten **Extended**:

    > [!div class="mx-imgBorder"]
    > ![Muuta otsikon teksti laajennettuna](media/northwind-orders-canvas-part3/details-23.png)

## <a name="display-order-totals"></a>Näytä tilausten kokonaissummat

1. Pienennä tieto valikoiman korkeutta niin, että tilaa tila uksen kokonaisarvoiksi näytön alareunassa:

    > [!div class="mx-imgBorder"]
    > ![Lyhennä tilaus-tieto valikoima](media/northwind-orders-canvas-part3/sum-01.png)

1. Kopioi ja liitä otsikko rivi näytön keskelle ja siirrä sitten kopio näytön alareunaan:

    > [!div class="mx-imgBorder"]
    > ![Kopioi otsikko rivi ja siirrä kopio alareunaan](media/northwind-orders-canvas-part3/sum-02.png)

1. Kopioi ja liitä tuote selite keskimmäisestä otsikko palkista ja siirrä sitten kopio alimmalle otsikko riville, joka on vain **määrä** -sarakkeen vasemmalla puolella.

1. Kaksoisnapsauta uuden nimen tekstiä ja kirjoita sitten seuraava teksti:<br>**Tila uksen summat:**

    > [!div class="mx-imgBorder"]
    > ![Lisää otsikko tilausten kokonaisarvoiksi](media/northwind-orders-canvas-part3/sum-03.png)

1. Kopioi ja liitä tila uksen summa-otsikko ja muuta sen kokoa ja siirrä kopio tila uksen summa-otsikon oikealle puolelle.

1. Valitse uuden nimen **teksti** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Sum( Gallery1.Selected.'Order Details'; Quantity )
    ```

    Tämä kaava näyttää delegointi varoituksen, mutta voit ohittaa sen, koska mikään yksittäinen tilaus ei sisällä enempää kuin 500 tuotetta.

1. Valitse **Aloitus** -väli lehdeltä uuden nimen tekstin tasaus **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Muuta tasausta](media/northwind-orders-canvas-part3/sum-04.png)

1. Kopioi ja liitä tämä selite-ohjaus objekti ja muuta sen kokoa ja siirrä kopiota **laajennetussa** sarakkeessa.

1. Valitse kopion **teksti** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Text( Sum( Gallery1.Selected.'Order Details'; Quantity * 'Unit Price' ); "[$-en-US]$ #,###.00" )
    ```

    Tämä kaava näyttää delegointi varoituksen, mutta voit ohittaa sen, koska mikään yksittäinen tilaus ei sisällä enempää kuin 500 tuotetta.

    > [!div class="mx-imgBorder"]
    > ![Näytä tila uksen kokonaiskustannukset](media/northwind-orders-canvas-part3/sum-05.png)

## <a name="add-space-for-new-details"></a>Lisää tilaa uusille tiedoissa

Voit näyttää tietoja missä tahansa valikoimassa, mutta et voi päivittää sitä tai lisätä tietueita. Lisää tiedot-valikoimaan alue, jossa käyttäjä voi määrittää tietueen **Order Details** -entiteetissä ja lisätä kyseisen tietueen tila uksen.

1. Pienennä tieto valikoiman korkeutta niin, että se tekee tilaa yksittäisen kohteen muokkaus tilaan kyseisen valikoiman alla.

    Tässä tilassa lisäät ohjaus objektin, jotta käyttäjä voi lisätä tila uksen tiedot:

    > [!div class="mx-imgBorder"]
    > ![Lyhennä tieto valikoimaa](media/northwind-orders-canvas-part3/add-details-01.png)

1. Lisää otsikko **Lisää** -väli lehteen ja muuta sen kokoa ja siirrä se yksityiskohta valikoiman alapuolelle.

    > [!div class="mx-imgBorder"]
    > ![Lisää otsikko](media/northwind-orders-canvas-part3/add-details-02.png)

1. Kaksoisnapsauta uuden nimen tekstiä ja paina sitten Delete-näppäintä.

1. Määritä **Aloitus** -väli lehdessä uuden nimen **täyttö** väriksi **lightblue**:

    > [!div class="mx-imgBorder"]
    > ![Muuta otsikon täyttö vaaleansini seksi](media/northwind-orders-canvas-part3/add-details-03.png)

## <a name="add-the-order-details-data-source"></a>Lisää tilaus tietojen tieto lähde

1. Valitse **näkymä** -väli lehdeltä **tieto lähteet**ja valitse sitten **tieto** ruudusta **Lisää tieto lähde** :

    > [!div class="mx-imgBorder"]
    > ![Lisää tieto lähde](media/northwind-orders-canvas-part3/add-details-04.png)

1. Valitse **Common Data Service**:

    > [!div class="mx-imgBorder"]
    > ![Valitse Common Data Service](media/northwind-orders-canvas-part3/add-details-05.png)

1. Kirjoita **tiedot** -ruudun yläreunaan haku-ruutuun **järjestys** , valitse **tila uksen tiedot** -valinta ruutu ja valitse sitten **Yhdistä** ruudun alareunasta:

    > [!div class="mx-imgBorder"]
    > ![Määritä tilaus tietojen entiteetti](media/northwind-orders-canvas-part3/add-details-06.png)

    Olet juuri lisännyt toisen tieto lähteen sovellukseen:

    > [!div class="mx-imgBorder"]
    > ![Tieto lähteiden luettelo](media/northwind-orders-canvas-part3/add-details-07.png)

    Sinun täytyy lisätä tämä tieto lähde, koska vaikka sovellus voi lukea yksi-moneen-suhteen, sovellus ei voi vielä kirjoittaa muutoksia takaisin. Sovelluksen on tehtävä muutoksia suoraan liittyvän entiteetin kanssa.

1. Sulje **tiedot** -ruutu.

## <a name="select-a-product"></a>Valitse tuote

1. Valitse **Lisää** -väli lehdeltä **ohjaus objektin** > **yhdistelmä ruutu**:

    > [!div class="mx-imgBorder"]
    > ![Lisää yhdistelmä ruutu](media/northwind-orders-canvas-part3/add-details-08.png)

    [**Yhdistelmä ruutu**](controls/control-combo-box.md) -ohjaus objekti näkyy vasemmassa yläkulmassa.

1. Valitse yhdistelmä ruudun **Items** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Choices( 'Order Details'.Product )
    ```

    > [!div class="mx-imgBorder"]
    > ![Yhdistelmä ruudun Items-ominaisuuden asetukset](media/northwind-orders-canvas-part3/add-details-09.png)

    [**Choices**](functions/function-choices.md) -funktio palauttaa **tila uksen tiedot** -entiteetin **tuote** -kentän kaikkien mahdollisten arvojen taulukon. Tämä kenttä on monta yhteen-suhteen haku, joten **valinnat** palauttavat kaikki **Order Products** -entiteetin tietueet.

    > [!NOTE]
    > Voit myös käyttää vaihto ehtoja asetus **joukkojen kanssa,** jos haluat palauttaa taulukon kaikista vaihto ehdoista. Näissä vaiheissa ei mainittu tätä lähestymis tapaa, mutta käytit sitä jo, kun lisäsit yhdistelmä ruudun, joka näyttää **tila uksen tilan** yhteenveto lomakkeessa.

1. Avaa **tiedot** -ruudussa **ensisijainen teksti** -lista ja valitse sitten **nwind_productname**. 

1. Avaa **Searchfield** -luettelosta ja valitse sitten **nwind_productname**.

    Voit määrittää loogisen nimen, koska **tieto** ruutu ei tue näyttö nimiä tässä tapa uksessa vielä:

    > [!div class="mx-imgBorder"]
    > ![Yhdistelmä ruudun ensisijaisen tekstin asetukset](media/northwind-orders-canvas-part3/add-details-10.png)

1. Sulje **tiedot** -ruutu.

1. Valitse **Ominaisuudet** -väli lehden lähellä oikeaa reunaa, vieritä alas, poista **Salli useita valintoja**-vaihto ehto ja varmista, että **Salli hakeminen** on käytössä:

    > [!div class="mx-imgBorder"]
    > ![Poista käytöstä useita valintoja ja ota hakeminen käyttöön](media/northwind-orders-canvas-part3/add-details-12.png)

1. Muuta yhdistelmä ruudun kokoa ja siirrä se vaaleansinisellä alueella juuri tuote nimi-sarakkeessa tieto valikoimassa:

    > [!div class="mx-imgBorder"]
    > ![Siirrä yhdistelmä ruutu](media/northwind-orders-canvas-part3/add-details-13.png)

    Tässä yhdistelmä ruudussa käyttäjä määrittää tietueen **tuote** -entiteetissä sen **tilaus tietojen** tietueelle, jonka sovellus luo.

1. Pidä Alt-näppäintä painettuna ja valitse yhdistelmä ruudun alanuoli.

    > [!TIP]
    > Pitämällä Alt-näppäintä painettuna voit käsitellä ohjaus objektien PowerApps Studio avaamatta esikatselutilaa.

1. Valitse näkyviin tulevasta tuote luettelosta tuote:

    > [!div class="mx-imgBorder"]
    > ![Valitse tuote yhdistelmä ruudusta](media/northwind-orders-canvas-part3/add-details-14.png)

## <a name="add-a-product-image"></a>Lisää tuote kuva

1. Valitse **Lisää** -väli lehdeltä **tieto väline** > **kuva**:

    > [!div class="mx-imgBorder"]
    > ![Lisää kuva-ohjaus objekti](media/northwind-orders-canvas-part3/add-details-15.png)

    [**Kuva**](controls/control-image.md) -ohjaus objekti näkyy vasemmassa yläkulmassa:

    > [!div class="mx-imgBorder"]
    > ![Kuva ohjaus objektin oletus sijainti](media/northwind-orders-canvas-part3/add-details-16.png)

1. Muuta kuvan kokoa ja siirrä se vaaleansinisellä alueella muiden tuote kuvien alapuolelle ja valitse yhdistelmä ruudun vierestä.

1. Valitse kuvan **ominaisuudeksi** :

    ```powerapps-comma
    ComboBox1.Selected.Picture
    ```

    > [!div class="mx-imgBorder"]
    > ![Kuvan kuva-ominaisuuden asetukset](media/northwind-orders-canvas-part3/add-details-17.png)

    Käytät samaa temppua, jota käytit näyttääksesi työn tekijän kuvan yhteenveto lomakkeessa. Yhdistelmä ruudun **valittu** ominaisuus palauttaa koko tietueen riippumatta siitä, mitä tuotetta käyttäjä valitsee, mukaan lukien **kuva** -kentän.

## <a name="add-a-quantity-box"></a>Lisää määrä ruutu

1. Valitse **Lisää** -väli lehdeltä **teksti** > **teksti syöte**:

    > [!div class="mx-imgBorder"]
    > ![Lisää teksti syöte ruutu](media/northwind-orders-canvas-part3/add-details-18.png)

    [**Teksti syöte**](controls/control-text-input.md) -ohjaus objekti näkyy vasemmassa yläkulmassa:

    > [!div class="mx-imgBorder"]
    > ![Teksti syöte ruudun oletus sijainti](media/northwind-orders-canvas-part3/add-details-19.png)

1. Muuta kokoa ja Siirrä teksti syöte ruutu yhdistelmä ruudun oikealla puolella tieto valikoiman määrä-sarakkeessa:

    > [!div class="mx-imgBorder"]
    > ![Muuta teksti syöte ruudun kokoa ja siirrä sitä](media/northwind-orders-canvas-part3/add-details-20.png)

    Käyttämällä tätä teksti syöte ruutua käyttäjä määrittää **tilaus tiedot** -tietueen **määrä** -kentän.

1. Määrittää tämän ohjaus objektin **oletus** ominaisuudeksi **""** :

    > [!div class="mx-imgBorder"]
    > ![Valitse teksti syöte ruudun * * default * *-ominaisuus](media/northwind-orders-canvas-part3/add-details-21.png)

1. Valitse **Aloitus** -väli lehdeltä tämän ohjaus objektin tekstin tasaus **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Muuta tasausta](media/northwind-orders-canvas-part3/add-details-22.png)

## <a name="show-the-unit-and-extended-prices"></a>Näytä yksikkö ja laajennetut hinnat

1. Lisää **Selite** -ohjaus objekti **Lisää** -väli lehteen.

    Selite näkyy näytön vasemmassa yläkulmassa:

    > [!div class="mx-imgBorder"]
    > ![Lisää otsikko](media/northwind-orders-canvas-part3/add-details-23.png)

1. Muuta tekstin syöttö-ohjaus objektin oikealla puolella olevaa otsikkoa ja siirrä sen **teksti** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Text( ComboBox1.Selected.'List Price'; "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Nimen teksti-ominaisuuden asetukset](media/northwind-orders-canvas-part3/add-details-24.png)

    Tämä ohjaus objekti esittää **tilaus tuotteet** -entiteetin **lista hinnan** . Tämä arvo ratkaisee **tilaus tiedot** -tietueen **yksikkö hinta** -kentän.

    > [!NOTE]
    > Tässä skenaariossa arvo on vain luku-tilassa, mutta muut skenaariot saattavat kutsua sovelluksen käyttäjää muokkaamaan sitä. Käytä siinä tapa uksessa **teksti syöte** -ohjaus objektia ja määritä sen **default** -ominaisuudeksi **List Price**.

1. Valitse **Aloitus** -väli lehdeltä luettelo hinta-otsikon tekstin tasaus **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Muuta tasausta](media/northwind-orders-canvas-part3/add-details-25.png)

1. Kopioi ja liitä luettelo hinta-otsikko ja muuta sen kokoa ja siirrä kopio luettelo – hinta-otsikon oikealle puolelle.

1. Valitse uuden nimen **teksti** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Text( Value(TextInput1.Text) * ComboBox1.Selected.'List Price'; "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Uuden nimen teksti-ominaisuuden asetukset](media/northwind-orders-canvas-part3/add-details-27.png)

    Tämä ohjaus objekti esittää laajennetun hinnan sovelluksen käyttäjän määrittämän määrän ja sovelluksen käyttäjän valitseman tuotteen luettelo hinnan perusteella. Se on puhtaasti Tiedottava sovellus käyttäjälle.

1. Kaksoisnapsauta määrän teksti syöte-ohjaus objektia ja kirjoita sitten luku.

    **Laajennetun** hinnan nimi lasketaan uudelleen näyttämään uusi arvo:

    > [!div class="mx-imgBorder"]
    > ![Määritä määrä ja Näytä kokonaishinta](media/northwind-orders-canvas-part3/add-details-28.png)

## <a name="add-an-add-icon"></a>Lisää kuvake

1. Valitse **Lisää** -väli lehdeltä **kuvakkeet** > **Lisää**:

    > [!div class="mx-imgBorder"]
    > ![Lisää kuvake](media/northwind-orders-canvas-part3/add-details-29.png)

    Kuvake näkyy näytön vasemmassa yläkulmassa.

    > [!div class="mx-imgBorder"]
    > ![Add-kuvakkeen oletus sijainti](media/northwind-orders-canvas-part3/add-details-30.png)

1. Muuta tämän kuvakkeen kokoa ja siirrä se vaaleansinisen alueen oikeaan reunaan ja aseta kuvakkeen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Patch( 'Order Details';
        Defaults('Order Details');
        {
            Order: Gallery1.Selected;
            Product: ComboBox1.Selected;
            Quantity: Value(TextInput1.Text);
            'Unit Price': ComboBox1.Selected.'List Price'
        }
    );;
    Refresh( Orders );;
    Reset( ComboBox1 );;
    Reset( TextInput1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä kuvakkeen OnSelect-ominaisuus](media/northwind-orders-canvas-part3/add-details-31.png)

    Yleensä [**patch**](functions/function-patch.md) -toiminto päivittää ja luo tietueita, ja tämän kaavan tietyt argumentit määrittävät ne tarkat muutokset, jotka toiminto tekee.

    - Ensimmäinen argumentti määrittää tieto lähteen (tässä tapa uksessa **tila uksen tiedot** -entiteetin), jossa funktiolla päivitetään tai luodaan tietue.
    - Toinen argumentti määrittää, että-funktiolla luodaan **tila uksen tiedot** -entiteetin oletus arvot sisältävä tietue, ellei kolmannessa argumentissa toisin määritetä.
    - Kolmas argumentti määrittää, että uudessa tietueessa on neljä saraketta, jotka sisältävät käyttäjän arvoja.

      - **Order** -sarake sisältää sen järjestyksen numeron, jonka käyttäjä valitsi Order Galleryssa.
      - **Tuote** -sarake sisältää tuotteen nimen, jonka käyttäjä valitsi yhdistelmä ruudussa, joka näyttää tuotteet.
      - **Määrä** -sarake sisältää arvon, jonka käyttäjä määritti teksti syöte-ruudussa.
      - **Yksikkö hinta** -sarake sisältää sen tuotteen luettelo hinnan, jonka käyttäjä valitsi tälle tila uksen tiedoille.

    > [!NOTE]
    > Voit luoda kaavoja, jotka käyttävät tietoja mistä tahansa sarakkeesta ( **Order Products** -entiteetissä) mistä tahansa tuotteesta, jonka sovellus käyttäjä valitsee tuotteet-yhdistelmä ruudusta. Kun käyttäjä valitsee tietueen **Order Products** -entiteetistä, tuote nimi näkyy tässä yhdistelmä ruudussa, mutta myös tuotteen yksikkö hinta näkyy selitteessä. Jokainen kangas sovelluksen haku arvo viittaa koko tietueeseen, ei vain ensisijaiseen avaimeen.

    **Refresh** -funktiolla varmistetaan, että **tila ukset** -entiteetti heijastaa tietuetta, jonka olet juuri lisännyt **tila uksen tiedot** -entiteettiin. **Reset** -funktiolla tyhjennetään tuote-, määrä-ja yksikkö hinta-tiedot niin, että käyttäjä voi helpommin luoda toisen tila uksen tiedot samalle tilaukselle.

1. Paina F5-näppäintä ja valitse sitten **Lisää** -kuvake.

    Järjestys vastaa määrittämiasi tietoja:

    > [!div class="mx-imgBorder"]
    > ![Animaatio tila uksen tietojen lisäämisestä](media/northwind-orders-canvas-part3/add-details.gif)

1. valinnainen Lisää toinen kohde järjestykseen.

1. Sulje esikatselutila painamalla ESC-näppäintä.

## <a name="remove-an-order-detail"></a>Tila uksen tietojen poistaminen

1. Valitse näytön keskeltä tieto valikoiman malli:

    > [!div class="mx-imgBorder"]
    > ![Valitse valikoima malli](media/northwind-orders-canvas-part3/remove-details-01.png)

1. Valitse **Lisää** -väli lehdeltä **kuvakkeet** > ,**roska kori**:

    > [!div class="mx-imgBorder"]
    > ![Lisää roska kori-kuvake](media/northwind-orders-canvas-part3/remove-details-02.png)

    Roska kori-kuvake näkyy valikoiman mallin vasemmassa yläkulmassa.

    > [!div class="mx-imgBorder"]
    > ![Kuvakkeen oletus sijainti](media/northwind-orders-canvas-part3/remove-details-03.png)

1. Muuta ja siirrä roska kori-kuvake tieto valikoiman mallin oikealle puolelle ja määritä kuvakkeen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Remove( 'Order Details'; ThisItem );; Refresh( Orders )
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä kuvakkeen OnSelect-ominaisuus](media/northwind-orders-canvas-part3/remove-details-04.png)

    Tätä kirjoitettaessa et voi poistaa tietuetta suoraan suhteesta, joten [**Remove**](functions/function-remove-removeif.md) -funktiolla poistetaan tietue suoraan liittyvästä entiteetistä. **Thisitem** määrittää poistettavan tietueen, joka on perä isin samasta tietueesta tieto valikoimassa, jossa roska kori-kuvake tulee näkyviin.

    Toiminto käyttää väli muistissa olevia tietoja, joten Refresh  -toiminto ilmoittaa **tila ukset** -entiteetille, että sovellus on muuttanut jotakin siihen liittyvistä entiteeteistä.

1. Avaa esikatselutila painamalla F5-näppäintä ja valitse sitten roska kori kuvake kunkin tila uksen **tieto** tietueen vierestä, jonka haluat poistaa tila uksen avulla.

1. Kokeile lisätä ja poistaa tila uksen eri tilaus tietoja:

    > [!div class="mx-imgBorder"]
    > ![Animaatio tila uksen tietojen lisäämisestä ja poistamisesta](media/northwind-orders-canvas-part3/remove-details.gif)

## <a name="in-conclusion"></a>Lopuksi

Voit lisätä uuden valikoiman, joka näyttää tila uksen tiedot sekä ohjaus objektin, joka lisää ja poistaa tila uksen tiedot sovelluksessa. Käytit näitä elementtejä:

- Toinen valikoima-ohjaus objekti, joka on linkitetty tilaus valikoimaan yksi moneen-suhteen kautta: **Gallery2. Items** = `Gallery1.Selected.'Order Details'`
- Monta yhteen-suhde **Order Details** -entiteetistä **Order Products** -entiteettiin: `ThisItem.Product.'Product Name'` ja`ThisItem.Product.Picture`
- **Choices** -funktiolla saadaan tuote luettelo:`Choices( 'Order Details'.Product' )`
- Yhdistelmä ruudun **valittu** ominaisuus, joka on valmiiksi monta yhteen liittyvä tietue: `ComboBox1.Selected.Picture` ja`ComboBox1.Selected.'List Price'`
- **Patch** -funktiolla luodaan **tilaus tietojen** tietue:`Patch( 'Order Details'; Defaults( 'Order Details' ); ... )`
- **Poista** -funktiolla voit poistaa **tilaus tiedot** -tietueen:`Remove( 'Order Details'; ThisItem )`

Tämä aiheiden sarja on ollut nopea vaihe vaiheelta, miten voit käyttää Common Data Service suhteita ja asetus joukkoja pohjaan sovelluksena opetus tarkoituksiin. Ennen kuin vapautat minkä tahansa sovelluksen tuotantoon, harkitse kentän tarkistamista, virheiden käsittelyä ja monia muita tekijöitä.

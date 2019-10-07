---
title: Tilaus valikoiman luominen kangas sovelluksessa | Microsoft Docs
description: Luo tilaus valikoima kangas sovellukseen Northwind Traders-tietojen hallintaa varten
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/25/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ac6586067105d5f6cd1ce2aab5568450804fe4c6
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71990878"
---
# <a name="create-an-order-gallery-in-a-canvas-app"></a>Tilaus valikoiman luominen kangas sovelluksessa

Noudata vaiheittaisia ohjeita luodaksesi tilaus valikoiman kangas sovellukseen, jotta voit hallita kuvitteellisia tietoja Northwind Traders-tieto kannassa. Tämä ohje aihe on osa sarjaa, jossa kerrotaan, miten voit luoda liiketoiminta sovelluksen relaatio tietoihin Common Data Service. Parhaat tulokset saat tutustumalla seuraaviin aihe isiin:

1. Luo tilaus valikoima (**Tämä aihe**).
1. [Luo Yhteenveto lomake](northwind-orders-canvas-part2.md).
1. [Luo tieto valikoima](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> ![Näytön alueiden määritelmät @ no__t-1

## <a name="prerequisites"></a>Edellytykset

- [Asenna Northwind Traders-tieto kanta ja-sovellukset](northwind-install.md).
- Lue Northwind Traders- [kangas sovelluksen Yleiskatsaus](northwind-orders-canvas-overview.md) .

## <a name="create-a-blank-app"></a>Tyhjän sovelluksen luominen

1. [Kirjaudu sisään Powerappsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)ja luo tyhjä Tablet-sovellus.

    > [!div class="mx-imgBorder"]
    > ![Canvas-sovellus tyhjästä ruudusta @ no__t-1

1. Anna sovellukselle nimi haluamallasi tavalla ja valitse sitten **Luo**.

    > [!div class="mx-imgBorder"]
    > ![Canvas-sovellus tyhjästä valinta ikkunasta @ no__t-1

    PowerApps Studio avautuu, jotta voit lisätä tieto lähteitä ja ohjaus objektin sovellukseesi:

    > [!div class="mx-imgBorder"]
    > ![PowerApps Studio @ no__t-1

1. Ota käyttöön [kokeellinen ominaisuus](working-with-experimental.md) , joka näyttää kaavan tuloksen suoraan kaava riviltä.

    1. Valitse **tiedosto-** valikosta **sovelluksen asetukset**ja valitse sitten **lisä asetukset**.
    1. Vieritä ominaisuuksien luettelon alaosaan ja ota sitten **käyttöön kaava palkin tulos-näkymä**:

        > [!div class="mx-imgBorder"]
        > ![Luettelo kokeellisista ominaisuuksista @ no__t-1

1. Palaa tyhjälle pohjalle valitsemalla vasemmassa yläkulmassa takaisin-nuoli.

## <a name="add-the-data"></a>Lisää tiedot

1. Valitse **näkymä** -väli lehdeltä **tieto lähteet**ja valitse sitten **tieto** ruudusta **Lisää tieto lähde** :

    > [!div class="mx-imgBorder"]
    > ![Valitse Näytä, tieto lähteet, lisää tieto lähde @ no__t-1

1. Valitse **Common Data Service**.

    Jos **Common Data Service** ei näy yhteyksien luettelossa, valitse **Uusi yhteys**ja lisää se.

    > [!div class="mx-imgBorder"]
    > ![Yhteyksien luettelo @ no__t-1

1. Valitse **Valitse entiteetti**, kirjoita **tila ukset**, valitse **tila ukset** -valinta ruutu ja valitse sitten **Yhdistä**:

    > [!div class="mx-imgBorder"]
    > ![Entiteettien luettelo @ no__t-1

    Olet lisännyt **tila ukset** -tieto lähteen sovellukseesi:

    > [!div class="mx-imgBorder"]
    > ![Tietoruutu @ no__t-1

    **Tila ukset** -entiteetti sisältää useita erityyppisiä kenttiä:

    > [!div class="mx-imgBorder"]
    > ![Luettelo tila ukset-entiteetin kentistä @ no__t-1

    Jokaisella kentällä on **näyttö nimi** ja **nimi**, jota kutsutaan joskus loogiseksi nimeksi. Molemmat nimet viittaavat samaan asiaan. Yleensä käytät näyttö nimeä, kun luot sovelluksen, mutta joissakin tapa uksissa tarvitaan enemmän arvoituksellinen **nimi**, kuten on mainittu toimenpiteessä.

1. Sulje **tiedot** -ruutu PowerApps Studio valitsemalla sen oikeasta yläkulmasta Sulje-kuvake (x).

## <a name="create-the-order-gallery"></a>Luo tilaus valikoima

1. Valitse **Lisää** -väli lehdestä **valikoima** > **tyhjä pystysuuntainen** , jos haluat lisätä [**valikoima**](controls/control-gallery.md) -ohjaus objektin, joka näyttää tila ukset.

    > [!div class="mx-imgBorder"]
    > ![Insert, Gallery, Blank pysty @ no__t-1

1. Valitse kaava riviltä valikoiman **Items** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    Sort( Orders, 'Order Number', Descending )
    ```

    Lajittelu-funktiolla [**lajitellaan**](functions/function-sort.md) luettelossa, että uusin järjestys (jonka järjestys numero on suurin) näkyy ensin.

    > [!div class="mx-imgBorder"]
    > ![Joukon Items-ominaisuus valikoimassa @ no__t-1

1. Avaa **Ominaisuudet** -väli lehden oikean reunan lähellä oleva **ulkoasu** -lista:

    > [!div class="mx-imgBorder"]
    > ![Luettelo taitto vaihtoehdoista @ no__t-1

1. Valitse vaihto ehtojen luettelosta **otsikko ja alaotsikko**:

    > [!div class="mx-imgBorder"]
    > ![Valitse ulkoasu @ no__t-1

    Kaksi [**nimi**](controls/control-text-box.md) ohjaus objektia lisätään valikoiman malliin. Oletus arvon mukaan näissä ohjaus objekteissa näkyy kaksi **tila ukset** -entiteetin saraketta, joita muutetaan seuraavaksi. Valikoiman malli kopioidaan vertikaalisesti kullekin entiteetin tietueelle.

1. Jos olet sulkenut **tiedot** -ruudun, valitse **Muokkaa** ( **kentät**-kohdan vierestä) **Ominaisuudet** -väli lehdellä lähellä oikeaa reunaa.

1. Valitse **tiedot** -ruudussa **Title1** (tai valitse yläosan otsikko valikoiman mallissa).

1. Valitse kaava riviltä selitteen **teksti** -ominaisuudeksi tämä lauseke:

    ```powerapps-dot
    "Order " & ThisItem.'Order Number'
    ```

    > [!div class="mx-imgBorder"]
    > ![Valitse otsikko-otsikon teksti-ominaisuus @ no__t-1

    Järjestys numero näkyy kunkin valikoima kohteen yläosassa. Valikoima-mallissa **thisitem** myöntää käyttö oikeuden **Order** -entiteetin kaikkiin kenttiin.

1. Valitse **tiedot** -ruudussa **Subtitle1** (tai valitse pienempi otsikko valikoiman mallissa):

    > [!div class="mx-imgBorder"]
    > ![Valitse tekstityksen nimi @ no__t-1

1. Valitse kaava riviltä selitteen **teksti** -ominaisuudeksi tämä lauseke:

    ```powerapps-dot
    ThisItem.Customer.Company
    ```

    > [!div class="mx-imgBorder"]
    > ![Valitse tekstityksen otsikon teksti-ominaisuus @ no__t-1

    Kun olet antanut tämän kaavan, se saattaa näyttää punaisena koukeroinen virhe hetken. Virhe tulee tyhjentää, jos valitset jotakin kaava rivin ulkopuolisesta kohdasta ja palautat sitten kohdistimen kaava riville. Jos virhe toistuu tai et näe arvoa, valitse **näkymä** -väli lehti, valitse **tieto lähteet**ja päivitä sitten **tila ukset** -entiteetti valitsemalla tieto lähteen nimen oikealla puolella kolme pistettä (...).

    Kun määrität **thisitem. Customer**-kohteen, olet hyödyntämällä monta yhteen-suhdetta **tilausten** ja **asiakkaiden** entiteettien välillä ja noutamassa kuhunkin tila uksessa liitettyä asiakas tietuetta. Asiakas tietueesta poimitaan tietoja **Company** -sarakkeessa näytettäväksi.

    Voit näyttää kaikki **tila ukset** -entiteetin väliset yhteydet muihin entiteetteihin, mukaan lukien **asiakas** -entiteettiin:

    > [!div class="mx-imgBorder"]
    > ![Luettelon suhteista @ no__t-1

1. Sulje **tiedot** -ruutu valitsemalla sen oikeasta yläkulmasta sulkemis kuvake (x).

## <a name="show-each-orders-status"></a>Näytä kunkin tila uksen tila

Tässä toimenpiteessä lisäät tilaa valikoimaan otsikkoa varten ja määrität sen näyttämään kunkin tila uksen tilan eri värillä tietojen perusteella.

1. Pienennä valikoiman mallissa ensimmäisen otsikon leveys **Title1**:

    > [!div class="mx-imgBorder"]
    > ![Titlis1 valikoiman mallissa @ no__t-1

1. Toista edellinen vaihe toisella otsikolla, **Subtitle1**:

    > [!div class="mx-imgBorder"]
    > ![Alilostit1 valikoiman mallissa @ no__t-1

1. Kun valikoima malli (tai mallin ohjaus objekti) on valittuna, valitse **Lisää** -väli lehdestä **Selite** :

    > [!div class="mx-imgBorder"]
    > ![Lisää nimi @ no__t-1

1. Siirrä uusi selite **Title1** -nimen oikealle puolelle:

    > [!div class="mx-imgBorder"]
    > ![Siirrä otsikkoa ja muuta sen kokoa @ no__t-1

1. Valitse uuden otsikon **Text** -ominaisuudeksi tämä lauseke:

    ```powerapps-dot
    ThisItem.'Order Status'
    ```

    > [!div class="mx-imgBorder"]
    > ![Valitse teksti-ominaisuus @ no__t-1

    Tila **ukset** -entiteetissä tila **uksen tila** -kentässä on arvo **tilausten tila** -asetus joukosta. Asetus joukossa on samanlainen luettelointi muissa ohjelmointi työkaluissa. Jokainen asetus asetus on määritetty tieto kannassa, joten käyttäjät voivat määrittää vain asetukset, jotka ovat joukossa. **Tila uksen tila** -asetus asetus on myös yleinen, ei paikallinen, joten voit käyttää sitä muissa entiteeteissä:

    > [!div class="mx-imgBorder"]
    > ![Orders-tila vaihtoehto asetus on @ no__t-1

    Jokaisella sarjan asetuksella on nimi, joka tulee näkyviin, jos näytät sen selitteessä. Nämä nimet voidaan lokalisoida, ja sovellus tunnistaa samalla vaihto ehdolla, valitseeko Englanti käyttäjä **Applen**, ranskankielinen käyttäjä valitsee **Pomme**tai espanjalainen käyttäjä valitsee **Manzanan**. Tästä syystä et voi luoda kaavaa, joka on riippuvainen kiinteästi koodatusta merkki jonosta, koska tämä aihe esittelee myöhemmin.

    Kaavoissa täytyy ympäröidä tila **uksen tila** heitto merkeillä, koska se sisältää väli lyönnin. Nimi toimii kuitenkin samalla tavalla kuin mikä tahansa muu nimi Powerappsissa, kuten **asiakas** tai **yritys**, ei.

1. Suurenna **Aloitus** -väli lehdessä tila otsikon fontin kokoa 20 pisteeseen ja Tasaa teksti oikealle:

    > [!div class="mx-imgBorder"]
    > ![Fontin koon ja tasa uksen muuttaminen @ no__t-1

1. Valitse kaava riviltä tila-otsikon **Color** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    Switch( ThisItem.'Order Status',
        'Orders Status'.Closed, Green,
        'Orders Status'.New, Black,
        'Orders Status'.Invoiced, Blue,
        'Orders Status'.Shipped, Purple
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Valitse tila nimen Color-ominaisuudeksi @ no__t-1

    PowerApps estää sinua luomasta kaavaa, joka käyttää kiinteästi koodattua merkki jonoa sarjan kullekin asetukselle, koska tällaiset kaavat saattavat tuottaa epäsopivia tuloksia, jos asetuksen nimet on lokalisoitu. Sen sijaan **Switch** -funktiolla määräytyy sen mukaan, mikä merkki jono näkyy selitteessä käyttäjän asetusten perusteella.

    Kun tämä kaava on käytössä, eri tila-arvot näkyvät eri väreissä, kuten edellinen grafiikka näyttää.

## <a name="display-each-orders-total"></a>Näytä kunkin tila uksen kokonaissumma

1. Valitse valikoiman ensimmäinen kohde, joka on valikoiman malli:

    > [!div class="mx-imgBorder"]
    > ![Valitse valikoima malli @ no__t-1

1. Lisää toinen selite valitsemalla **Lisää** -väli lehdestä **otsikko** :

    > [!div class="mx-imgBorder"]
    > ![Lisää nimi @ no__t-1

1. Siirrä uusi selite niin, että se näkyy tila-otsikon alla:

    > [!div class="mx-imgBorder"]
    > ![Resize ja Siirrä uusi nimi @ no__t-1

1. Valitse kaava riviltä uuden nimen **teksti** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    Text( Sum( ThisItem.'Order Details', Quantity * 'Unit Price' ), "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Formula tila uksen kokonaishinnan laskemiseen @ no__t-1

    Tässä kaavassa Sum-funktiolla [**lasketaan**](functions/function-aggregates.md) yhteen Order **Details** -entiteetin tietueet, jotka on liitetty **Order** yksikön-entiteetin kuhunkin tietueeseen yksi-moneen-suhteen kautta. Nämä rivit muodostavat kunkin järjestyksen, ja käytät samaa yksi-moneen-suhdetta näyttämään ja muokkaamaan rivin kohteita näytön oikeassa alakulmassa.

    Tässä kaavassa näytetään sininen alleviivaus ja [delegointi varoitus](delegation-overview.md) , koska Common Data Service ei tue monimutkaisten kooste funktioiden delegoimista (esimerkiksi kertolaskun summa). Voit ohittaa nämä tiedot, koska mikään tässä esimerkissä oleva järjestys ei sisällä enempää kuin 500 rivin kohdetta. Jos se on tarpeen eri sovellukselle, voit suurentaa kyseistä rajaa **sovelluksen asetuksissa**.

    Tämän kaavan [**teksti**](functions/function-text.md) -funktiolla lisätään valuutta symboli, joka muotoilee tuloksen tuhansina ja desimaalina erottimina. Kuten kirjoitettu, kaava sisältää Yhdysvaltojen kielen merkinnän Englanti ( **[$-en-US]** ) ja dollarin symboli ( **$** ). Jos poistat kieli tunnisteen, se korvataan yhdellä kieli asetusten perusteella, ja selitteessä näkyy kyseisen tunnisteen asianmukaiset muodot. Jos jätät dollarin symbolin, nimi näyttää asianmukaisen valuutta symbolin käyttäjän asetusten mukaan. Voit kuitenkin pakottaa eri symbolin näkymään korvaamalla dollarin symbolin haluamallasi.

1. Vaihda **Aloitus** -väli lehdessä uusimman otsikon fontti kooksi 20 pistettä ja Tasaa sen teksti oikealle:

    > [!div class="mx-imgBorder"]
    > ![Fontin koon ja tekstin tasa uksen muuttaminen @ no__t-1

1. Siirrä valikoimaa näytön vasempaan reunaan ja pienennä valikoiman leveyttä niin, että se sulkee tilaa.

1. Suurenna valikoiman korkeutta niin, että se on lähes yhtä pitkä kuin näyttö, mutta jätä hieman tilaa yläosassa otsikko riville, jonka lisäät seuraavan aiheen alkuun:

    > [!div class="mx-imgBorder"]
    > ![Siirrä ja muuta valikoiman kokoa @ no__t-1

## <a name="summary"></a>Yhteenveto

Voit kerrata uudelleen luomalla yhden näytön kangas sovelluksen lisäämällä tilaus valikoiman, joka sisältää seuraavat elementit:

- Järjestys numeron näyttämisen lauseke: `"Orders " & ThisItem.OrderNumber`
- Kenttä monta yhteen-suhteessa: `ThisItem.Customer.Company`
- Nimi, joka sisältää joukon asetuksen nimen: `ThisItem.'Order Status'`
- Selite, joka muuttaa muotoa sen perusteella, mikä asetus on kohteessa, jonka nimi näytetään: `Switch( ThisItem.'Order Status', 'Orders Status'.Closed, Green, ...`
- Monitasoinen kooste funktio yksi-moneen-suhteen kanssa: `Sum( ThisItem.'Order Details', Quantity * 'Unit Price' )`

## <a name="next-topic"></a>Seuraava aihe

Seuraavassa aiheessa lisätään [**Muokkaa lomaketta**](controls/control-form-detail.md) -ohjaus objekti, joka näyttää ja Muokkaa yhteenvetoa siitä, minkä järjestyksen käyttäjä valitsee juuri luomaasi valikoimaan.

> [!div class="nextstepaction"]
> [Luo Yhteenveto lomake](northwind-orders-canvas-part2.md)
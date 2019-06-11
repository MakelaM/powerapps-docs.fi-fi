---
title: Luo pohjaan perustuvan sovelluksen tietoja-valikoiman | Microsoft Docs
description: Luo tietoja-valikoiman pohjaan perustuvan sovelluksen Northwind Traders tietojen hallintaan
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
ms.openlocfilehash: 9549b8f389cf696cf3fc8e4659da6b418383ac6e
ms.sourcegitcommit: e85072f7a80da308c4caabe20adbf2509588ca57
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/07/2019
ms.locfileid: "66760955"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-a-detail-gallery-in-a-canvas-app"></a>Luo tietoja-valikoiman pohjaan perustuva sovellus

Noudata vaiheittaiset ohjeet tietoja-valikoiman luomiseen pohjaan perustuvan sovelluksen hallintaan kuvitteellisia tietoja Northwind Traders tietokannassa. Tämä ohjeaihe on osa pidempää sarjaa, jossa selitetään business-sovelluksen rakentaminen Common Data Service-relaatiotietoja. Saat parhaat tulokset Tutustu aiheet tässä järjestyksessä:

1. [Luo order-valikoima](northwind-orders-canvas-part1.md).
1. [Luo yhteenveto lomake](northwind-orders-canvas-part2.md).
1. Luo valikoima tiedot (**tässä ohjeaiheessa**).

> [!div class="mx-imgBorder"]
> ![Näytön alueiden määritys](media/northwind-orders-canvas-part1/orders-parts.png)

## <a name="prerequisites"></a>Edellytykset

Ennen kuin aloitat tässä ohjeaiheessa, sinun on asennettava tietokanta, jotka kuvattiin aiemmin tässä ohjeaiheessa. Voit sitten Luo order-valikoimassa ja yhteenveto lomakkeen tai avaa **Northwind tilaukset (pohjaan perustuvat) - Aloita osa 3** sovelluksen, joka sisältää jo valikoiman ja lomakkeen.

## <a name="create-another-title-bar"></a>Luo toinen otsikkorivi

1. Valitse näytön yläreunassa [ **nimen** ](controls/control-text-box.md) ohjausobjekti, joka toimii otsikkorivi, kopioi se painamalla Ctrl + C ja liitä se painamalla Ctrl-V:

    > [!div class="mx-imgBorder"]
    > ![Kopioi ja liitä otsikkorivi](media/northwind-orders-canvas-part3/details-01.png)

1. Kokoa ja Siirrä kopion, niin, että se ilmaantuu Yhteenveto lomakkeen.

1. Poista teksti kopiosta jommankumman seuraavista tavoista:

    - Kaksoisnapsauta valitsemalla se ja paina sitten Poista.
    - Määritä selitteen **tekstin** ominaisuus tyhjäksi merkkijonoksi ( **””** ).

    > [!div class="mx-imgBorder"]
    > ![Poista teksti otsikkorivin alapuolella kopiosta](media/northwind-orders-canvas-part3/details-02.png)

## <a name="add-a-gallery"></a>Lisää valikoima

1. Lisää [ **valikoiman** ](controls/control-gallery.md) ohjausobjektin **tyhjä, pysty** asettelu:

    > [!div class="mx-imgBorder"]
    > ![Lisää tyhjä pystysuuntainen valikoima](media/northwind-orders-canvas-part3/details-03.png)

    Uusi valikoima, jossa näkyvät tilaustiedot, näkyy vasemmassa yläkulmassa:

    > [!div class="mx-imgBorder"]
    > ![Tilauksen tiedot valikoiman oletussijainti](media/northwind-orders-canvas-part3/details-04.png)

1. Sulje **tietojen** ruudussa ja muuta kokoa ja Siirrä tietoja-valikoiman oikeassa alakulmassa, uusi otsikkorivin alapuolella:

    > [!div class="mx-imgBorder"]
    > ![Tilauksen tiedot valikoiman lopullisen sijainti](media/northwind-orders-canvas-part3/details-05.png)

1. Määritä **kohteet** ominaisuus tiedot tämä kaava:

    ```powerapps-comma
    Gallery1.Selected.'Order Details'
    ```

    > [!div class="mx-imgBorder"]
    > ![Tietoja-valikoiman Items-ominaisuuden asettaminen](media/northwind-orders-canvas-part3/details-06.png)

    Jos näyttöön tulee virhesanoma, Vahvista, että tilauksen valikoima nimeltä **Gallery1** (- **puu näkymän** ruudussa lähellä vasenta reunaa). Jos valikoiman on eri nimi, nimeä se uudelleen **Gallery1**.

    Olet juuri yhdistänyt kaksi valikoimat. Kun käyttäjä valitsee tilauksen tilauksen valikoimassa, valinta tunnistaa tietueen **tilaukset** entiteetin. Jos tilaus sisältää vähintään yhden rivin kohdetta, tietueen **tilaukset** entiteetti on linkitetty yksi tai useampi tietueiden **Tilaustiedot** entiteettien ja tietojen tietueet näkyvät tietoja-valikoiman. Toiminta vastaa yksi-moneen-suhde, joka on luotu puolestasi **tilaukset** ja **Tilaustiedot** entiteettejä. Kaava, jonka määritit ”ohjaa” suhteen piste merkintätapaa käyttämällä:

    > [!div class="mx-imgBorder"]
    > ![Yksi moneen suhde tilaukset-kohteen ja Tilaustiedot-kohteen](media/northwind-orders-canvas-part3/schema-orders-rel.png)

## <a name="show-product-names"></a>Näytä tuotenimiä

1. Valitse valikoiman tiedot **Lisää kohde Lisää-välilehdestä** ja valitse haluamasi valikoiman mallipohja:

    > [!div class="mx-imgBorder"]
    > ![Valitse malli, tietoja-valikoiman](media/northwind-orders-canvas-part3/details-07.png)

    Varmista, että olet valinnut valikoiman mallipohja on sen sijaan, että itse valikoima. Määritetyissä tulee olla hieman raja valikoiman sisällä ja todennäköisesti lyhyempi kuin valikoiman korkeus. Kun lisäät ohjausobjekteja tätä mallia, ne toistuvat kunkin kohteen valikoimassa.

1. Valitse **Lisää** Lisää selitteenä valikoiman tiedot-välilehdessä.

    Että selite näytetään; valikoiman sisällä Jos näin ei ole, yritä uudelleen, mutta valitse valikoiman mallipohjaa, ennen kuin lisäät nimen.

    > [!div class="mx-imgBorder"]
    > ![Lisää selite valikoiman tiedot](media/northwind-orders-canvas-part3/details-08.png)

1. Määritä uuden nimen **tekstin** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    ThisItem.Product.'Product Name'
    ```

    Jos tekstiä ei ole, valitsemalla nuoli **tilauksen 0901** tilauksen valikoiman alaosassa.

1. Muuttaa selitteen kokoa siten, että koko teksti näkyy:

    > [!div class="mx-imgBorder"]
    > ![Näytä tuotteen nimen tilauksen tiedot](media/northwind-orders-canvas-part3/details-09.png)

    Tämä lauseke ohjaa tietueesta **Tilaustiedot** entiteetin. Tietueen säilytetään **ThisItem** over- **tilata tuotteita** entiteetin monta yhteen-suhteen kautta:

    > [!div class="mx-imgBorder"]
    > ![Tilauksen tiedot entiteetin ja tilauksen tuote-entiteetin monta yhteen suhde](media/northwind-orders-canvas-part3/schema-orderdetails-rel.png)

    **Tuotenimi** kenttä (ja muut kentät, jotka olet käyttämässä) poimitaan:

    > [!div class="mx-imgBorder"]
    > ![Tilauksen tuotteiden entiteetin kenttien](media/northwind-orders-canvas-part3/schema-products-fields.png)

## <a name="show-product-images"></a>Tuotekuvien näyttäminen

1. Käyttöön **Lisää** Lisää-välilehdessä [ **kuvan** ](controls/control-image.md) tietoja-valikoiman komponentin:

    > [!div class="mx-imgBorder"]
    > ![Lisää kuva-ohjausobjekti](media/northwind-orders-canvas-part3/details-10.png)

1. Kokoa ja Siirrä kuva ja otsikko on rinnakkain.

    > [!TIP]
    > Yksityiskohtaisemman ohjausobjektin koon ja sijainnin ohjausobjektin Aloita kokoa tai siirtää ilman painamalla Alt-näppäintä ja jatka kokoa tai siirtää ohjausobjektia, kun pidät Alt-näppäintä:

    > [!div class="mx-imgBorder"]
    > ![Siirrä kuva-ohjausobjekti](media/northwind-orders-canvas-part3/details-11.png)

1. Määrittää kuvan **kuvan** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    ThisItem.Product.Picture
    ```

    Uudelleen tuotteen, joka on liitetty tämä lauseke viittaa tilauksen tiedot ja poimitaan **kuvan** kenttää sen näyttämiseksi.

    > [!div class="mx-imgBorder"]
    > ![Näytä kuva](media/northwind-orders-canvas-part3/details-12.png)

1. Pienennä valikoiman mallipohjaa niin, että enemmän kuin yksi korkeutta **tilauksen tiedot** tietue näytetään yhdellä kertaa:

    > [!div class="mx-imgBorder"]
    > ![Lyhennä valikoiman mallipohjaa](media/northwind-orders-canvas-part3/details-13.png)

## <a name="show-product-quantity-and-cost"></a>Näytä tuotteen määrä ja kustannukset

1. Valitse **Lisää** välilehti, Lisää toinen selite tietoja-valikoiman ja kokoa ja Siirrä uusi otsikko tuotetiedot oikealla.

1. Määritä uuden nimen **tekstin** ominaisuudeksi seuraava lauseke:

    ```powerapps-comma
    ThisItem.Quantity
    ```

    Tämä kaava hakee tiedot suoraan **Tilaustiedot** entiteetin (ei pakollinen suhde).

    > [!div class="mx-imgBorder"]
    > ![Näytä tuotteen määrä](media/northwind-orders-canvas-part3/details-13b.png) 

1. Käyttöön **aloitus** muuttaa tämän ohjausobjektin tasaus-välilehden **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Tasauksen muuttaminen](media/northwind-orders-canvas-part3/details-14.png)

1. Valitse **Lisää** välilehti, Lisää toinen selite tietoja-valikoiman ja kokoa ja Siirrä selite määrä nimen oikealle puolelle.

1. Määritä uuden nimen **tekstin** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Text( ThisItem.'Unit Price'; "[$-en-US]$ #,###.00" )
    ```

    Jos et määritä kielitunnisteen ( **[$-en-US]** ), se lisätään kielen ja alueen perusteella. Jos käytät eri kielitunnisteen, haluat poistaa **$** vain jälkeen Sulje hakasulje ( **]** ), ja lisää sitten oman valuuttasymbolin tässä asemassa.

    > [!div class="mx-imgBorder"]
    > ![Näytä Yksikköhinta](media/northwind-orders-canvas-part3/details-15.png)

1. Käyttöön **aloitus** muuttaa tämän ohjausobjektin tasaus-välilehden **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Tasauksen muuttaminen](media/northwind-orders-canvas-part3/details-16.png)

1. Valitse **Lisää** välilehti, Lisää toinen tietoja-valikoiman ja kokoa ja Siirrä uusi otsikko Yksikköhinta oikealla.

1. Määritä uuden nimen **tekstin** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Text( ThisItem.Quantity * ThisItem.'Unit Price'; "[$-en-US]$ #,###.00" )
    ```

    Uudelleen, jos et määritä kielitunnisteen ( **[$-en-US]** ), se lisätään kielen ja alueen perusteella. Tunniste on erilainen, jos haluat käyttää omia valuuttasymbolia sijasta **$** vain jälkeen Sulje hakasulje ( **]** ).

    > [!div class="mx-imgBorder"]
    > ![Näytä kokonaishinta](media/northwind-orders-canvas-part3/details-17.png)

1. Käyttöön **aloitus** muuttaa tämän ohjausobjektin tasaus-välilehden **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Tasauksen muuttaminen](media/northwind-orders-canvas-part3/details-18.png)

    Nyt olet valmis tietoja-valikoiman lisääminen ohjausobjekteja.

1. - **Puu näkymän** ruudussa **Screen1** sen varmistamiseksi, että tietoja-valikoiman ei ole enää valittuna.

## <a name="add-text-to-the-new-title-bar"></a>Lisää uusi otsikkorivin teksti

1. Valitse **Lisää** -välilehden Lisää toinen selite näytön seuraavaan:

    > [!div class="mx-imgBorder"]
    > ![Lisää otsikko](media/northwind-orders-canvas-part3/details-19.png)

1. Kokoa ja Siirrä uusi selite tuotteiden kuvat yllä toinen otsikkorivillä ja muuta sitten tekstin väri valkoinen **aloitus** välilehti.

1. Kaksoisnapsauta otsikon teksti ja kirjoita sitten **tuotteen**:

    > [!div class="mx-imgBorder"]
    > ![Muuta tuotteen nimen teksti](media/northwind-orders-canvas-part3/details-20.png)

1. Kopioi ja liitä tuotteen nimen, ja sitten kokoa ja Siirrä kopion määrä-sarakkeessa yläpuolella.

1. Kaksoisnapsauta uuden nimen teksti ja kirjoita sitten **määrä**:

    > [!div class="mx-imgBorder"]
    > ![Muuta nimen teksti määrä](media/northwind-orders-canvas-part3/details-21.png)

1. Kopioi ja liitä määrä, nimen ja sitten kokoa ja Siirrä kopion Yksikköhinta sarakkeen yläpuolella.

1. Kaksoisnapsauta uuden nimen teksti ja kirjoita sitten **Yksikköhinta**:

    > [!div class="mx-imgBorder"]
    > ![Muuta Yksikköhinta nimen teksti](media/northwind-orders-canvas-part3/details-22.png)

1. Kopioi ja liitä Yksikköhinta nimen ja sitten kokoa ja Siirrä kopion Laajennettu hinta-sarakkeen yläpuolella.

1. Kaksoisnapsauta uuden nimen teksti ja kirjoita sitten **laajennettua**:

    > [!div class="mx-imgBorder"]
    > ![Muuta laajennettua nimen teksti](media/northwind-orders-canvas-part3/details-23.png)

## <a name="display-order-totals"></a>Näytä kokonaissummat

1. Pienennä tehdäksemme tilausten kokonaissummat näytön alareunassa tietoja-valikoiman korkeutta:

    > [!div class="mx-imgBorder"]
    > ![Lyhennä Tilaustiedot valikoima](media/northwind-orders-canvas-part3/sum-01.png)

1. Kopioi ja Liitä näytön keskellä otsikkorivin ja siirrä sitten näytön alareunasta kopion:

    > [!div class="mx-imgBorder"]
    > ![Kopioi otsikkorivi ja Siirrä kopioi alareunaan](media/northwind-orders-canvas-part3/sum-02.png)

1. Kopioi ja liitä Keskimmäinen otsikkorivin tuotteen selite ja siirrä sitten kopion alareunan otsikkorivillä, joka vasemmalla puolella **määrä** sarake.

1. Kaksoisnapsauta uuden nimen teksti ja kirjoita tämä teksti:<br>**Tilauksen yhteensä:**

    > [!div class="mx-imgBorder"]
    > ![Lisää otsikko kokonaissummat](media/northwind-orders-canvas-part3/sum-03.png)

1. Kopioi ja liitä-kokonaissummat, nimen ja sitten kokoa ja Siirrä kopion kokonaissummat otsikon oikealla puolella.

1. Määritä uuden nimen **tekstin** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Sum( Gallery1.Selected.'Order Details'; Quantity )
    ```

    Tämä kaava näyttää delegointia varoitus, mutta voit ohittaa koska ei ole yhdessä tilauksessa sisältää enemmän kuin 500 tuotteita.

1. Käyttöön **aloitus** asetettu uuden otsikon tekstin tasaus-välilehden **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Tasauksen muuttaminen](media/northwind-orders-canvas-part3/sum-04.png)

1. Kopioi ja Liitä tämä Selite-ohjausobjekti ja kokoa ja Siirrä kohdassa kopion **laajennettua** sarake.

1. Määritä kopioi **tekstin** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Text( Sum( Gallery1.Selected.'Order Details'; Quantity * 'Unit Price' ); "[$-en-US]$ #,###.00" )
    ```

    Tämä kaava näyttää delegointia varoitus, mutta voit ohittaa koska ei ole yhdessä tilauksessa sisältää enemmän kuin 500 tuotteita.

    > [!div class="mx-imgBorder"]
    > ![Näytä tilauksen kokonaiskustannukset](media/northwind-orders-canvas-part3/sum-05.png)

## <a name="add-space-for-new-details"></a>Lisää uusi saat

Minkä tahansa valikoiman voit näyttää tiedot mutta et voi päivittää tai lisätä tietueita. Tietoja-valikoiman alle lisäät on alue, jossa käyttäjä voi määrittää tietueen **Tilaustiedot** entiteetin ja lisää joka tallentaa tilaukseksi.

1. Pienennä tiedot valikoiman tarpeeksi tilaa yhden kohteen muokkaamisen tilaa kohdassa valikoiman korkeutta.

    Tähän lisäät ohjausobjekteja siten, että käyttäjä voi lisätä tilauksen tiedot:

    > [!div class="mx-imgBorder"]
    > ![Lyhennä valikoiman tiedot](media/northwind-orders-canvas-part3/add-details-01.png)

1. Valitse **Lisää** välilehti, Lisää selite, ja kokoa ja Siirrä tietoja-valikoiman alle.

    > [!div class="mx-imgBorder"]
    > ![Lisää selite](media/northwind-orders-canvas-part3/add-details-02.png)

1. Uusi selitteen tekstinä, ja paina sitten Poista.

1. Valitse **aloitus** välilehti, Määritä uusi otsikko **Täytä** väri, jota **LightBlue**:

    > [!div class="mx-imgBorder"]
    > ![Muuta otsikon täyttö Vaaleansininen](media/northwind-orders-canvas-part3/add-details-03.png)

## <a name="add-the-order-details-data-source"></a>Lisää Tilaustiedot tietolähde

1. Käyttöön **Näytä** -välilehden **tietolähteet**, ja valitse sitten **Lisää tietolähde** - **tietojen** ruudussa:

    > [!div class="mx-imgBorder"]
    > ![Lisää tietolähde](media/northwind-orders-canvas-part3/add-details-04.png)

1. Valitse **Common Data Service-** :

    > [!div class="mx-imgBorder"]
    > ![Valitse Common Data Service](media/northwind-orders-canvas-part3/add-details-05.png)

1. Yläosassa **tietojen** ruudussa, tyyppi **tilauksen** hakuruutuun, valitse **Tilaustiedot** valintaruutu ja valitse sitten **Yhdistä** osoitteessa -ruudun alaosassa:

    > [!div class="mx-imgBorder"]
    > ![Tilauksen tietojen entiteetti](media/northwind-orders-canvas-part3/add-details-06.png)

    Olet juuri lisäämäsi toiseen tietolähteeseen sovellukseen:

    > [!div class="mx-imgBorder"]
    > ![Tietolähteiden luettelo](media/northwind-orders-canvas-part3/add-details-07.png)

    Sinun on lisättävä tätä tietolähdettä, koska sovelluksen lukea yksi-moneen-suhde, vaikka sovellus ei ole vielä takaisinkirjoittamiseen. Sovellus täytyy tehdä muutoksia suoraan liittyvän entiteetin kanssa.

1. Sulje **tietojen** ruudussa.

## <a name="select-a-product"></a>Valitse tuote

1. Valitse **Lisää** -välilehden **ohjausobjekteja** > **yhdistelmäruudun**:

    > [!div class="mx-imgBorder"]
    > ![Lisää yhdistelmäruutu](media/northwind-orders-canvas-part3/add-details-08.png)

    [ **Yhdistelmäruudun** ](controls/control-combo-box.md) ohjausobjekti näkyy vasemmassa yläkulmassa.

1. Määritä yhdistelmäruudun **kohteet** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Choices( 'Order Details'.Product )
    ```

    > [!div class="mx-imgBorder"]
    > ![Ruudun Items-ominaisuuden asettaminen yhdistelmäruutu](media/northwind-orders-canvas-part3/add-details-09.png)

    [ **Vaihtoehtoja** ](functions/function-choices.md) funktio palauttaa kaikki mahdolliset arvot **tuotteen** kenttää **Tilaustiedot** entiteetin. Tämä kenttä on niin monta yhteen-suhteen haun **vaihtoehtoja** palauttaa kaikki tietueet **tilata tuotteita** entiteetin.

    > [!NOTE]
    > Voit myös käyttää **vaihtoehtoja** Asetusjoukot palautettavien taulukon kaikki asetukset. Vaiheet ei mainita tietueryhmän, mutta se käyttää jo, kun olet lisännyt yhdistelmäruudun, joka näyttää **tilauksen tila** yhteenveto muodossa.

1. - **Tietojen** ruutu, avattuna **ensisijainen tekstin** luettelo ja valitse sitten **nwind_productname**. 

1. Avaa **käyttämällä SearchField** luettelo ja valitse sitten **nwind_productname**.

    Määritä looginen nimi, koska **tietojen** ruudussa ei tue näyttönimiä tässä tapauksessa vielä:

    > [!div class="mx-imgBorder"]
    > ![Määritä ensisijainen teksti-yhdistelmäruutu](media/northwind-orders-canvas-part3/add-details-10.png)

1. Sulje **tietojen** ruudussa.

1. - **Ominaisuudet** lähellä oikeaa reunaa, Vieritä alaspäin välilehdeltä käytöstä **Monivalinnan salliminen**, ja varmista, että **Salli haun** on otettu käyttöön:

    > [!div class="mx-imgBorder"]
    > ![Monivalinta käytöstä ja ota käyttöön](media/northwind-orders-canvas-part3/add-details-12.png)

1. Kokoa ja Siirrä yhdistelmäruudun vaaleansinisen alue, vain tietoja-valikoiman tuotteen nimi-sarakkeen:

    > [!div class="mx-imgBorder"]
    > ![Siirrä yhdistelmäruutu](media/northwind-orders-canvas-part3/add-details-13.png)

    Tämä yhdistelmäruutu käyttäjän määrittää tietueen **tuotteen** entiteetin **Tilaustiedot** tietueen, joka luo sovelluksen.

1. Kun pidät alhaalla Alt-näppäintä, valitse yhdistelmäruudun alanuolta.

    > [!TIP]
    > Pitämällä Alt-näppäintä voit käsitellä PowerApps Studio-ohjausobjektit avaamatta esikatselutilassa.

1. Luettelossa olevien tuotteiden, joka tulee näkyviin Valitse tuote:

    > [!div class="mx-imgBorder"]
    > ![Valitse tuote-yhdistelmäruutu](media/northwind-orders-canvas-part3/add-details-14.png)

## <a name="add-a-product-image"></a>Lisää tuotteen kuva

1. Valitse **Lisää** -välilehden **Media** > **kuvan**:

    > [!div class="mx-imgBorder"]
    > ![Lisää kuva-ohjausobjekti](media/northwind-orders-canvas-part3/add-details-15.png)

    [ **Kuvan** ](controls/control-image.md) ohjausobjekti näkyy vasemmassa yläkulmassa:

    > [!div class="mx-imgBorder"]
    > ![Kuva-ohjausobjektin oletussijainti](media/northwind-orders-canvas-part3/add-details-16.png)

1. Kokoa ja Siirrä kuvaa vaaleansinisen alueelta, valitse muita tuotekuvien yhdistelmäruudun vieressä.

1. Määritä **kuvan** ominaisuuden kuva:

    ```powerapps-comma
    ComboBox1.Selected.Picture
    ```

    > [!div class="mx-imgBorder"]
    > ![Määrittää kuvan Image-ominaisuus](media/northwind-orders-canvas-part3/add-details-17.png)

    Käytät samaan ajaa saman asian sinuna käytetään näyttämään työntekijän kuva yhteenveto muodossa. **Valittu** yhdistelmäruudun-ominaisuus palauttaa koko tietueen haluamasi käyttäjä valitsee, tuotteen **kuvan** kenttä.

## <a name="add-a-quantity-box"></a>Lisää määrä-ruutu

1. Valitse **Lisää** -välilehden **tekstin** > **Tekstisyöte**:

    > [!div class="mx-imgBorder"]
    > ![Lisää tekstisyötteen ruutu](media/northwind-orders-canvas-part3/add-details-18.png)

    [ **Tekstisyöte** ](controls/control-text-input.md) ohjausobjekti näkyy vasemmassa yläkulmassa:

    > [!div class="mx-imgBorder"]
    > ![Oletussijainti tekstisyötteen ruutu](media/northwind-orders-canvas-part3/add-details-19.png)

1. Kokoa ja Siirrä tekstisyötteen ruutua yhdistelmäruudun tietoja-valikoiman määrä-sarakkeen oikealla:

    > [!div class="mx-imgBorder"]
    > ![Kokoa ja Siirrä tekstisyötteen ruutua](media/northwind-orders-canvas-part3/add-details-20.png)

    Tämä tekstisyötteen ruutu avulla käyttäjä määrittää **määrä** kenttään **Tilaustiedot** tietueen.

1. Määritä **oletus** tämän ohjausobjektin ominaisuuden **””** :

    > [!div class="mx-imgBorder"]
    > ![Määritä ** ominaisuuden oletusarvon ** tekstisyötteen ruutu](media/northwind-orders-canvas-part3/add-details-21.png)

1. Valitse **aloitus** Määritä tämän ohjausobjektin tekstin tasaus-välilehden **oikealle**:

    > [!div class="mx-imgBorder"]
    > ![Tasauksen muuttaminen](media/northwind-orders-canvas-part3/add-details-22.png)

## <a name="show-the-unit-and-extended-prices"></a>Näytä yksikkö ja laajennettu hinnat

1. Käyttöön **Lisää** Lisää-välilehdessä **nimen** ohjausobjektin.

    Selite tulee näkyviin näytön vasemmassa yläkulmassa:

    > [!div class="mx-imgBorder"]
    > ![Lisää selite](media/northwind-orders-canvas-part3/add-details-23.png)

1. Kokoa ja Siirrä selite oikealla puolella Tekstisyöte-ohjausobjekti ja määritä selitteen **tekstin** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Text( ComboBox1.Selected.'List Price'; "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Määrittää selitteen tekstin ominaisuutta](media/northwind-orders-canvas-part3/add-details-24.png)

    Tämä ohjausobjekti näyttää **luettelon hinta** - **tilata tuotteita** entiteetin. Tämä arvo määrittää **Yksikköhinta** kenttää **Tilaustiedot** tietueen.

    > [!NOTE]
    > Tämän skenaarion arvo on vain luku-tilassa, mutta muut skenaarioita voi kutsua sovelluksen käyttäjä voi muokata sitä. Tässä tapauksessa käyttää **Tekstisyöte** ohjausobjekti ja määritä sen **oletus** ominaisuudeksi **luettelon hinta**.

1. Valitse **aloitus** Määritä luettelon hinta selitteen tekstin tasaus-välilehdessä **oikeassa**:

    > [!div class="mx-imgBorder"]
    > ![Tasauksen muuttaminen](media/northwind-orders-canvas-part3/add-details-25.png)

1. Kopioi ja liitä luettelon hinta-nimen ja sitten kokoa ja Siirrä kopion luettelon hinta-otsikon oikealla.

1. Määritä uuden nimen **tekstin** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Text( Value(TextInput1.Text) * ComboBox1.Selected.'List Price'; "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä uusi selitteen tekstin ominaisuutta](media/northwind-orders-canvas-part3/add-details-27.png)

    Tämä ohjausobjekti näyttää kokonaishinta määrä, joka sovelluksen käyttäjälle määritetty ja tuotteen, sovelluksen käyttäjä valitsi luettelon hinnan perusteella. On vain tiedoksi sovelluksen käyttäjälle.

1. Kaksoisnapsauta Tekstisyöte-ohjausobjektiin, määrä ja kirjoita sitten luku.

    **Laajennettua** nimen hinta laskee uudelleen näyttämään uusi arvo:

    > [!div class="mx-imgBorder"]
    > ![Määrittää määrän ja näyttää Laajennettu hinta](media/northwind-orders-canvas-part3/add-details-28.png)

## <a name="add-an-add-icon"></a>Lisää Lisää-kuvake

1. Valitse **Lisää** -välilehden **kuvakkeet** > **Lisää**:

    > [!div class="mx-imgBorder"]
    > ![Lisää Lisää kuvake](media/northwind-orders-canvas-part3/add-details-29.png)

    Kuvake näkyy näytön vasemmassa yläkulmassa.

    > [!div class="mx-imgBorder"]
    > ![Lisää kuvake oletussijainti](media/northwind-orders-canvas-part3/add-details-30.png)

1. Kokoa ja Siirrä tämä kuvake oikeassa reunassa vaaleansinisen aluetta ja määritä sitten kuvakkeen **OnSelect** -ominaisuuden arvoksi tämä kaava:

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
    > ![Kuvakkeen OnSelect-ominaisuuden](media/northwind-orders-canvas-part3/add-details-31.png)

    Yleisesti ottaen [ **Patch** ](functions/function-patch.md) funktio päivittää ja luo tietueita ja tietyt määritteet Tässä kaavassa Määritä tarkka muutokset, jotka funktio tekee.

    - Ensimmäinen argumentti määrittää tietolähteen (Tässä tapauksessa, **Tilaustiedot** entiteetin), funktio päivittää tai luoda tietueen.
    - Toinen argumentti määrittää, että funktio luo tietueen oletusarvoilla varten **Tilaustiedot** entiteetin ellei muuta ilmoiteta kolmannen argumentin.
    - Kolmas argumentti määrittää, neljän sarakkeen uusi tietue sisältää arvoja käyttäjältä.

      - **Tilauksen** sarake sisältää, jonka käyttäjä valitsi tilauksen valikoiman tilauksen määrä.
      - **Tuotteen** sarake sisältää, yhdistelmäruudun valitulle käyttäjälle, joka näkyy tuotteiden tuotteen nimi.
      - **Määrä** sarake sisältää arvon, joka määritettiin tekstisyötteen ruutua.
      - **Yksikköhinta** sarake sisältää tuotteen, jonka käyttäjä valitsi tämän tilauksen saat luettelon hinnan.

    > [!NOTE]
    > Voit luoda kaavoja, jotka käyttävät minkä tahansa sarakkeen tiedot (- **tilata tuotteita** entiteetin) haluamasi tuotteen sovelluksen käyttäjä valitsee yhdistelmäruutu, joka sisältää tuotteita. Kun käyttäjä valitsee tietueen **tilata tuotteita** entiteetin tuotteen nimen näkyvät kyseisen yhdistelmäruudun tuotolla myös tuotteen yksikköhinta näkyviin. Pohjaan perustuvan sovelluksen lookup kunkin arvon viittaa koko tietueen, ei ainoastaan ensisijainen avain.

    **Päivitä** funktio varmistaa, että **tilaukset** entiteetin kuvastaa, jotka olet juuri lisäämäsi tietue **Tilaustiedot** entiteetin. **Vaihtaa** funktio poistaa tuotteen, määrä ja Yksikköhinta tiedot, niin, että käyttäjä voi helpommin luoda toisen tilauksen-tiedot samassa järjestyksessä.

1. Paina F5-näppäintä ja valitse sitten **Lisää** kuvake.

    Tilauksen kuvastaa, jonka määritit tiedot:

    > [!div class="mx-imgBorder"]
    > ![Animaatio lisäämällä tilauksen tiedot](media/northwind-orders-canvas-part3/add-details.gif)

1. (valinnainen) Lisää toinen kohde tilauksen.

1. Sulje esikatselutila painamalla ESC-näppäintä.

## <a name="remove-an-order-detail"></a>Poista tilauksen tiedot

1. Valitse näytön keskellä tietoja-valikoiman malli:

    > [!div class="mx-imgBorder"]
    > ![Valitse valikoiman mallipohja](media/northwind-orders-canvas-part3/remove-details-01.png)

1. Valitse **Lisää** -välilehden **kuvakkeet** > **roskakori**:

    > [!div class="mx-imgBorder"]
    > ![Lisää roskakorikuvake](media/northwind-orders-canvas-part3/remove-details-02.png)

    Roskakori-kuvake vasemmassa yläkulmassa valikoiman mallipohjaa.

    > [!div class="mx-imgBorder"]
    > ![Oletussijainti kuvake](media/northwind-orders-canvas-part3/remove-details-03.png)

1. Kokoa ja Siirrä tietoja-valikoiman mallipohja oikealla puolella Roskakorin kuvaketta ja määritä kuvakkeen **OnSelect** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Remove( 'Order Details'; ThisItem );; Refresh( Orders )
    ```

    > [!div class="mx-imgBorder"]
    > ![Kuvakkeen OnSelect-ominaisuuden](media/northwind-orders-canvas-part3/remove-details-04.png)

    Tätä kirjoitettaessa tietuetta ei voi poistaa suoraan suhteen, joten [ **poistaa** ](functions/function-remove-removeif.md) -funktio poistaa tietueen suoraan liittyvässä entiteetissä. **ThisItem** määrittää poistaa tietueen tietoja-valikoiman Roskakorin kuvaketta esiintyvien samaa tietuetta.

    Uudelleen, toiminto käyttää välimuistiin tallennettuja tietoja, joten **Päivitä** funktio ilmoittaa **tilaukset** entiteetin, sovelluksella on muuttunut jokin sen liittyvät entiteetit.

1. Paina F5-näppäintä, Avaa esikatselutila ja valitse sitten kunkin Roskakori-kuvaketta **Tilaustiedot** tietueen, jonka haluat poistaa tilauksen.

1. Yritä lisätä ja eri tilauksen tiedot poistetaan tilauksesi:

    > [!div class="mx-imgBorder"]
    > ![Animaation lisäämällä ja poistamalla Tilaustiedot](media/northwind-orders-canvas-part3/remove-details.gif)

## <a name="in-conclusion"></a>Erityisesti

Recap, lisätä toisen valikoima näyttämään Tilaustiedot ja ohjausobjektien lisääminen ja poistaminen sovelluksessa tilauksen tiedot. Voit käyttää näitä elementtejä:

- Toinen Valikoimaohjausobjekti, linkitetty tilauksen valikoiman yksi-moneen-suhteen kautta: **Gallery2.items** = `Gallery1.Selected.'Order Details'`
- Monta yhteen suhteen **Tilaustiedot** entiteetti **tilata tuotteita** entiteetin: `ThisItem.Product.'Product Name'` ja `ThisItem.Product.Picture`
- **Vaihtoehtoja** toimintoa käytetään saamaan olevien tuotteiden luettelosta: `Choices( 'Order Details'.Product' )`
- **Valittu** yhdistelmäruudun kuin valmis monta-yhteen-ominaisuuden liittyvä tietue: `ComboBox1.Selected.Picture` ja `ComboBox1.Selected.'List Price'`
- **Patch** toiminto **Tilaustiedot** tietueen: `Patch( 'Order Details'; Defaults( 'Order Details' ); ... )`
- **Poistaa** funktio poistaa **Tilaustiedot** tietueen: `Remove( 'Order Details'; ThisItem )`

Tämän sarjan aiheet on nopea vaiheittaiset ohjeet käyttämällä Common Data Service-suhteita ja asetusjoukkojen pohjaan perustuvassa sovelluksessa opetustarkoituksiin. Ennen kuin vapautat mikä tahansa sovellus tuotantoon, sinun kannattaa harkita Kenttävahvistus Virheenkäsittely ja muiden tekijöiden.

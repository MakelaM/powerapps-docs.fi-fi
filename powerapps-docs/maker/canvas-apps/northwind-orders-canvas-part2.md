---
title: Yhteenveto lomakkeen luominen kangas sovelluksessa | Microsoft Docs
description: Luo Yhteenveto lomake kangas sovellukseen Northwind Traders-tietojen hallintaa varten
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
ms.openlocfilehash: d151249caebdb2a6f142943074a409bc626ff662
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995865"
---
# <a name="create-a-summary-form-in-a-canvas-app"></a>Yhteenveto lomakkeen luominen kangas sovelluksessa

Noudata vaiheittaisia ohjeita ja luo Yhteenveto lomake kangas sovelluksessa, jotta voit hallita kuvitteellisia tietoja Northwind Traders-tieto kannassa. Tämä ohje aihe on osa sarjaa, jossa kerrotaan, miten voit luoda liiketoiminta sovelluksen relaatio tietoihin Common Data Service. Parhaat tulokset saat tutustumalla seuraaviin aihe isiin:

1. [Luo tilaus valikoima](northwind-orders-canvas-part1.md).
2. Luo Yhteenveto lomake (**Tämä aihe**).
3. [Luo tieto valikoima](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> ![Näytön alueiden määritelmät @ no__t-1

## <a name="prerequisites"></a>Edellytykset

1. [Asenna Northwind Traders-tieto kanta ja-sovellukset](northwind-install.md).
1. Tutustu Northwind Traders- [kangas sovelluksen yleiskatsaukseen](northwind-orders-canvas-overview.md) .
1. [Luo tilaus valikoima](northwind-orders-canvas-part1.md) itse tai avaa **Northwind-tila ukset (piirto alusta) – Aloita osan 2** sovellus, joka sisältää jo kyseisen valikoiman.

## <a name="add-a-title-bar"></a>Lisää otsikkorivi

Luo sovelluksen yläosassa otsikko rivi, joka sisältää toiminto painikkeita tämän aiheen loppuun mennessä.

1. Valitse **puunäkymä** -ruudussa **Screen1** varmistaaksesi, ettet vahingossa lisää ohjaus objektia tilaus valikoimaan:

    > [!div class="mx-imgBorder"]
    > ![Valitse Screen1 puunäkymän ruudussa @ no__t-1

1. Lisää [**Selite**](controls/control-text-box.md) -ohjaus objekti valitsemalla **Lisää** -väli lehdestä **otsikko** :

    > [!div class="mx-imgBorder"]
    > ![Lisää otsikko @ no__t-1

    Uuden nimen pitäisi näkyä vain kerran valikoiman yläpuolella. Jos se näkyy kunkin valikoiman kohdassa, Poista nimen ensimmäinen esiintymä, varmista, että näyttö on valittuna (kuten edellisessä vaiheessa kuvataan), ja lisää sitten selite uudelleen.

1. Siirrä uutta otsikkoa ja muuta sen kokoa niin, että se ulottuu näytön yläreunaan:

    > [!div class="mx-imgBorder"]
    > ![Siirrä otsikkoa ja muuta sen kokoa @ no__t-1

1. Kaksoisnapsauta otsikon tekstiä ja kirjoita sitten **Northwind-tila ukset**.

    Vaihtoehtoisesti voit muokata kaava rivin **Text** -ominaisuutta saman tuloksen saavuttamiseksi:

    > [!div class="mx-imgBorder"]
    > ![ muuta otsikko rivin teksti @ no__t-1

1. Muotoile otsikko **Aloitus** -väli lehdellä:
    - Suurenna fontin kokoa 24 pisteeseen.
    - Lihavoi teksti.
    - Tee tekstistä valkoinen.
    - Keskitä teksti.
    - Lisää taustalle tumma sininen täyttö.

    > [!div class="mx-imgBorder"]
    > ![Muotoilun asetukset aloitus-väli lehdessä @ no__t-1

## <a name="add-an-edit-form-control"></a>Muokkaa lomaketta-ohjaus objektin lisääminen

Tässä osiossa lisätään ohjaus objektien yhteenveto, joka näyttää yhteenvedon mistä tahansa järjestyksestä, jonka käyttäjä valitsee valikoimasta.

1. Lisää [**Muokkaa lomaketta**](controls/control-form-detail.md) -ohjaus objekti **Lisää** -väli lehdessä:

    > [!div class="mx-imgBorder"]
    > ![Lisää Muokkaa lomaketta-ohjaus objekti @ no__t-1

    Oletus arvon mukaan lomake näkyy vasemmassa yläkulmassa, jossa muiden ohjaus objektien löytäminen voi olla hankalaa:

    > [!div class="mx-imgBorder"]
    > ![Muokkaa lomake-ohjaus objektia oletus sijainnissa @ no__t-1

1. Siirrä lomaketta ja muuta sen kokoa niin, että se kattaa näytön oikean yläkulman otsikko rivin alla:

    > [!div class="mx-imgBorder"]
    > ![Muokkaa lomaketta-ohjaus objektin siirtäminen ja koon muuttaminen @ no__t-1

1. Valitse kaava riviltä lomakkeen **DataSource** -ominaisuudeksi tämä arvo:

    ```powerapps-dot
    Orders
    ```

    > [!div class="mx-imgBorder"]
    > ![Muokkaa lomaketta-ohjaus objektin DataSource-ominaisuudeksi @ no__t-1

    Voit valita saman ominaisuuden **Ominaisuudet** -väli lehdessä lähellä oikeaa reunaa, mutta tämä lähestymis tapa lisää kenttiä, joita et tarvitse lomakkeeseen. Jos käytät kaava riviä, lomake pysyy tyhjänä.

## <a name="add-and-arrange-fields"></a>Kenttien lisääminen ja järjestäminen

1. Avaa **kentät** -ruutu valitsemalla **Ominaisuudet** -väli lehden lähellä oikeaa reunaa **Muokkaa kenttiä** :

    > [!div class="mx-imgBorder"]
    > ![Avaa kentät-ruutu @ no__t-1

1. Valitse **kentät** -ruudussa **Lisää kenttä**ja valitse sitten **asiakas** -ja **työntekijä** kenttien valinta ruudut.

    > [!div class="mx-imgBorder"]
    > ![Lisää asiakas-ja työntekijä kentät Muokkaa lomaketta-ohjaus objektiin @ no__t-1

1. Vieritä alaspäin, kunnes nämä kentät tulevat näkyviin, ja valitse sitten niiden valinta ruudut:

    - **Muistiinpanot**
    - **Tila uksen päivä määrä**
    - **Tila uksen numero**
    - **Tila uksen tila**
    - **Maksettu päivä määrä**

    > [!div class="mx-imgBorder"]
    > ![Lisää viisi kenttää Muokkaa lomaketta-ohjaus objektiin @ no__t-1

1. Valitse **kentät** -ruudun alareunasta **Lisää**ja sulje sitten **kentät** -ruutu.

    Lomakkeessa näkyvät seitsemän kenttää:

    > [!div class="mx-imgBorder"]
    > ![Muokkaa lomaketta-ohjaus objekti sisältää seitsemän kenttää @ no__t-1

    > [!NOTE]
    > Jos jokin kenttä ilmaisee punaista virhe kuvaketta, ilmeni ongelma, kun tietoja vedettiin lähteestä. Ratkaise virhe päivittämällä tiedot:
    >
    > 1. Valitse **Näytä**-välilehdessä **Tietolähteet**.
    > 1. Valitse tieto **ruudussa** **tieto lähteet**.
    > 1. Valitse **tila ukset**-kohdan vierestä kolme pistettä (...), valitse **Päivitä**ja sulje **tiedot** -ruutu.
    >
    > Jos asiakkaan tai työn tekijän nimen yhdistelmä ruutu näyttää edelleen virheen, tarkista kunkin ruudun **ensisijainen teksti** -ja haku **kenttä** valitsemalla se ja avaamalla sitten **tieto** ruutu. Asiakas-ruudussa molempien kenttien arvoksi on asetettava **nwind_company**. Työn tekijä-ruudussa molempien kenttien arvoksi on asetettava **nwind_lastname**.

1. Kun lomake on valittuna, muuta lomakkeen sarakkeiden määrä 3-12: n **Ominaisuudet** -väli lehdellä lähellä oikeaa reunaa.

    Tämä vaihe lisää joustavuutta, kun järjestät kenttiä:

    > [!div class="mx-imgBorder"]
    > ![Muuta sitten sarakkeiden määrä Muokkaa lomaketta-ohjaus objektissa @ no__t-1

    Monet käyttö liittymä mallit käyttävät 12-sarake asetteluja, koska ne voivat sijoittaa tasaisesti 1, 2, 3, 4, 6 ja 12 ohjaus objektin riveihin. Tässä ohje aiheessa luodaan rivejä, jotka sisältävät 1, 2 tai 4 ohjaus objektia.

1. Siirrä kenttiä ja muuta niiden kokoa vetämällä niiden kahvoja samalla tavalla kuin mitä tahansa muuta ohjaus objektia, jotta jokainen rivi sisältää nämä tieto kortit määritetyssä järjestyksessä:

    - Ensimmäinen rivi: Tila uksen **numero**, tila uksen **tila**, **tilaus päivämäärä**ja **maksettu päivä määrä**
    - Toinen rivi: **Asiakas** ja **työn tekijä**
    - Kolmas rivi: **Muistiinpanot**

    > [!NOTE]
    > **Muistiinpanojen**, **asiakkaiden**ja **työn tekijöiden** tieto korttien laajentaminen voi olla helpompaa ennen niiden järjestämistä.

    > [!div class="mx-imgBorder"]
    > ![Siirrä kenttiä ja muuta niiden kokoa @ no__t-1

    Lisä tietoja kenttien järjestämisestä lomakkeessa: [Tutustu kangas sovellusten tieto lomakkeen rakenteeseen](working-with-form-layout.md).

## <a name="hide-time-controls"></a>Piilota aika-ohjaus painikkeet

Tässä esimerkissä et tarvitse päivämäärä kenttien aika-osia, koska kyseinen askel väli voi häiritä käyttäjää. Jos poistat ne, saatat aiheuttaa ongelmia kaavoissa, jotka perustuvat kyse isiin ohjaus objekteihin, päivittääkseen päivämäärä arvoja tai määrittäessään toisen ohjaus objektin sijaintia tieto kortissa. Sen sijaan voit piilottaa aika-ohjaus objektin asettamalla sen **Visible** -ominaisuuden.

1. Valitse **puunäkymä** -ruudussa **Order Date** -tieto kortti.

    Kortilla voi olla eri nimi, mutta se sisältää **tilaus päivämäärän**.

1. Pidä Vaihto näppäintä painettuna ja valitse tunti-, minuutti-ja kaksoispiste-erotin-ohjaus objekti **Order Date** -tieto kortissa.

    > [!div class="mx-imgBorder"]
    > ![Valitse Time-ohjaus painikkeet Order Date-kortissa @ no__t-1

1. Määrittää ohjaus objektien **Visible** -ominaisuudeksi **false**.

    Kaikki valitut ohjaus toiminnot katoavat lomakkeesta:

    > [!div class="mx-imgBorder"]
    > ![Valitse Visible-ominaisuudeksi false. ](media/northwind-orders-canvas-part2/form-10.png)

1. Muuta [**päivämäärä valitsin**](controls/control-date-picker.md) -ohjaus objektin kokoa niin, että se näyttää koko päivä määrän:

    > [!div class="mx-imgBorder"]
    > ![Muuta päivämäärä valitsin-ohjaus objektin kokoa @ no__t-1

    Seuraavaksi toistat viimeiset vaiheet **maksetun päivä määrä** -kentän kohdalla.

1. Valitse **puunäkymä** -ruudussa Time ohjaus objekteja **maksetun päivä määrä** -tieto kortissa:

    > [!div class="mx-imgBorder"]
    > ![Valitse Time Control maksetun päivä määrän kortissa @ no__t-1

1. Määrittää valittujen ohjaus objektien **Visible** -ominaisuudeksi **false**:

    > [!div class="mx-imgBorder"]
    > ![Valitse Visible-ominaisuudeksi false. ](media/northwind-orders-canvas-part2/form-13.png)

1. Muuta päivämäärä valitsimen kokoa **Date maksullisella** kortilla:

    > [!div class="mx-imgBorder"]
    > ![Muuta päivämäärä valitsin-ohjaus objektin kokoa @ no__t-1

## <a name="connect-the-order-gallery"></a>Yhdistä tilaus valikoima

1. Kutista **puunäkymä** -ruudussa lomake, jotta löydät helpommin tilaus valikoiman nimen, ja nimeä se tarvittaessa uudelleen nimellä **Gallery1**.

1. Valitse Yhteenveto lomakkeen **Item** -ominaisuudeksi tämä lauseke:

    ```powerapps-dot
    Gallery1.Selected
    ```

    > [!div class="mx-imgBorder"]
    > ![Joukon kohteen ominaisuus lomakkeessa @ no__t-1

    Lomakkeessa näytetään Yhteenveto siitä, missä järjestyksessä sovellus käyttäjä valitsee luettelossa.

    > [!div class="mx-imgBorder"]
    > ![Valitse luettelosta tila uksen yleiskatsaus muodossa @ no__t-1

## <a name="replace-a-data-card"></a>Korvaa tieto kortti

**Tilaus numero** on tunnus, joka Common Data Service määrittää automaattisesti, kun luot tietueen. Tällä kentällä on oletus arvon mukaan [**teksti syöte**](controls/control-text-input.md) -ohjaus objekti, mutta korvaat sen otsikolla, jotta käyttäjä ei voi muokata tätä kenttää.

1. Valitse lomake, valitse **Muokkaa kenttiä** **Ominaisuudet** -väli lehdellä lähellä oikeaa reunaa ja valitse sitten **tila uksen numero** -kenttä:

    > [!div class="mx-imgBorder"]
    > ![Valitse tilaus numero kenttä @ no__t-1

1. Avaa **ohjaus objektin tyyppi** -lista:

    > [!div class="mx-imgBorder"]
    > ![Avaa * * ohjaus objekti tyyppi * * List @ no__t-1

1. Valitse **Näytä teksti** tieto kortti:

    > [!div class="mx-imgBorder"]
    > ![Valitse * * Näytä teksti * * tieto kortti @ no__t-1

1. Sulje **kentät** -ruutu.

    Käyttäjä ei voi enää muuttaa järjestys numeroa:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Tilausnumero on vain luku-tilassa @ no__t-1

1. Vaihda **Aloitus** -väli lehdellä järjestys numeron fontin kooksi 20 pistettä, jotta kenttää on helpompi löytää:

    > [!div class="mx-imgBorder"]
    > ![Muuta järjestys numeron fontin koko @ no__t-1

## <a name="use-a-many-to-one-relationship"></a>Monta yhteen-suhteen käyttäminen

**Order** -entiteetillä on monta yhteen-suhde **työn tekijät** -entiteettiin: jokainen työn tekijä voi luoda useita tila uksia, mutta jokainen tilaus voidaan määrittää vain yhdelle työn tekijälle. Kun käyttäjä valitsee työn tekijän [**yhdistelmä ruutu**](controls/control-combo-box.md) -ohjaus objektissa, sen **valittu** ominaisuus antaa työn tekijän koko tietueen **työn tekijät** -entiteetistä. Tämän seura uksena voit määrittää [**kuva**](controls/control-image.md) -ohjaus objektin näyttämään kuvan siitä, mitä työn tekijää käyttäjä valitsee yhdistelmä ruudusta.

1. Valitse **työn tekijän** tieto kortti:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Valitse työn tekijän tieto kortti @ no__t-1

1. Avaa **lisä asetukset** -väli lehden oikean reunan lähellä oleva tieto kortti, jotta voit muokata vain luku-tilassa olevia kaavoja:

    > [!div class="mx-imgBorder"]
    > ![Työn tekijän tieto kortin lukituksen poistaminen @ no__t-1

1. Pienennä tieto kortissa yhdistelmä ruudun leveyttä, jotta voit tehdä tilaa työn tekijän kuvalle:

    > [!div class="mx-imgBorder"]
    > ![Muuta yhdistelmä ruudun ohjaus objektin kokoa @ no__t-1

1. Valitse **Lisää** -väli lehdeltä **tieto väline** > -**kuva**:

    > [!div class="mx-imgBorder"]
    > ![Lisää kuva @ no__t-1

    Tieto kortissa näkyy kuva, joka laajenee sen mukaan:

    > [!div class="mx-imgBorder"]
    > ![Työntekijätietokortti ja kuva ohjaus objekti @ no__t-1

1. Muuta kuvan kokoa ja siirrä se yhdistelmä ruudun oikealle puolelle:

    > [!div class="mx-imgBorder"]
    > ![Siirrä kuva-ohjaus objektia ja muuta sen kokoa @ no__t-1

1. Valitse kuvan **ominaisuudeksi** Tämä kaava ja korvaa luku DataCardValue-kohteen lopussa tarvittaessa:

    ```powerapps-dot
    DataCardValue7.Selected.Picture
    ```

    > [!div class="mx-imgBorder"]
    > ![Kuvaa kuvan ominaisuudeksi @ no__t-1

    Valitun työn tekijän kuva tulee näkyviin.

1. Kun pidät Alt-näppäintä painettuna, valitse toinen työn tekijä yhdistelmä ruudusta vahvistaaksesi, että kuva muuttuu myös.

    > [!div class="mx-imgBorder"]
    > ![Valitse työn tekijä, joka näyttää, että työn tekijän kuva @ no__t-1

## <a name="add-a-save-icon"></a>Lisää tallennus kuvake

1. Valitse **puunäkymä** -ruudussa **Screen1**ja valitse sitten **lisää** > **kuvaketta** > **Tarkista**:

    > [!div class="mx-imgBorder"]
    > ![Lisää Check-Mark-kuvake @ no__t-1

    [**Tarkistus**](controls/control-shapes-icons.md) kuvake näkyy Oletus arvon mukaan vasemmassa yläkulmassa, jossa muut ohjaus objektin kuvakkeet saattavat vaikeuttaa sen löytämistä:

    > [!div class="mx-imgBorder"]
    > ![Icon oletus sijainnissa @ no__t-1

1. Vaihda **Aloitus** -väli lehdessä kuvakkeen **väri** -ominaisuudeksi valkoinen, muuta kuvakkeen kokoa ja siirrä se otsikko rivin oikean reunan lähelle:

    > [!div class="mx-imgBorder"]
    > ![Määritä Save-kuvakkeen väri, koko ja sijainti @ no__t-1

1. Varmista **puunäkymä** -ruudussa, että lomakkeen nimi on **Form1**, ja määritä sitten kuvakkeen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    SubmitForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä Tallenna-kuvakkeen OnSelect-ominaisuudeksi @ no__t-1

    Kun käyttäjä valitsee kuvakkeen, [**Submitform**](functions/function-form.md) -funktiolla kerätään kaikki muuttuneet arvot lomakkeeseen ja lähetetään ne tieto lähteeseen. Pisteet maaliskuussa näytön yläreunassa, kun tiedot lähetetään, ja järjestys valikoima heijastaa muutoksia prosessin päättymisen jälkeen.

1. Valitse kuvakkeen **DisplayMode** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    If( Form1.Unsaved, DisplayMode.Edit, DisplayMode.Disabled )
    ```

    > [!div class="mx-imgBorder"]
    > ![Asenna kuvakkeen DisplayMode-ominaisuus @ no__t-1

    Jos kaikki lomakkeen muutokset on tallennettu, kuvake on poistettu käytöstä ja näkyy **Disabledcolor**-kohteessa, joka määritetään seuraavaksi.

1. Valitse kuvakkeen **disabledcolor** -ominaisuudeksi tämä arvo:

    ```powerapps-dot
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Asenna kuvakkeen DisabledColor-ominaisuus @ no__t-1

    Käyttäjä voi tallentaa tila uksen muutokset valitsemalla Tarkista-kuvakkeen, joka poistetaan käytöstä ja himmennetään, kunnes käyttäjä tekee toisen muutoksen:

    > [!div class="mx-imgBorder"]
    > ![muutosten tallentaminen @ no__t-1

## <a name="add-a-cancel-icon"></a>Lisää peruutus kuvake

1. Valitse **Lisää** -väli lehdeltä **kuvakkeet** > **Peruuta**:

    > [!div class="mx-imgBorder"]
    > ![Lisää peruutus kuvake @ no__t-1

    Kuvake näkyy Oletus arvon mukaan vasemmassa yläkulmassa, jossa muut ohjaus objektin kuvakkeet saattavat vaikeuttaa sen löytämistä:

    > [!div class="mx-imgBorder"]
    > ![Peruuta-kuvake oletus sijainnissa @ no__t-1

1. Vaihda **Aloitus** -väli lehdessä kuvakkeen **väri** -ominaisuudeksi valkoinen, muuta kuvakkeen kokoa ja siirrä se tarkistus kuvakkeen vasemmalle puolelle:

    > [!div class="mx-imgBorder"]
    > ![Peruuta-kuvakkeen värin, koon ja sijainnin muuttaminen @ no__t-1

1. Määritä peruutus kuvakkeen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    ResetForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä peruutus kuvakkeen OnSelect-ominaisuudeksi @ no__t-1

    [**Resetform**](functions/function-form.md) -funktio hylkää kaikki lomakkeen muutokset, mikä palauttaa sen alkuperäiseen tilaan.

1. Valitse Peruuta-kuvakkeen **DisplayMode** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    If( Form1.Unsaved Or Form1.Mode = FormMode.New, DisplayMode.Edit, DisplayMode.Disabled )
    ```

    > [!div class="mx-imgBorder"]
    > ![Valitse peruutus kuvakkeen DisplayMode-ominaisuus @ no__t-1

    Tämä kaava eroaa hieman tarkistus kuvakkeen yhdestä kohteesta. Peruutus kuvake on poistettu käytöstä, jos kaikki muutokset on tallennettu tai jos lomake on **uudessa** tilassa, joka otetaan käyttöön seuraavaksi. Tässä tapa uksessa **Resetform** hylkää uuden tietueen.

1. Valitse Peruuta-kuvakkeen **disabledcolor** -ominaisuudeksi tämä arvo:

    ```powerapps-dot
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Valitse Peruuta-kuvakkeen DisabledColor-ominaisuus @ no__t-1

    Käyttäjä voi peruuttaa tila uksen muutokset, ja tarkistus-ja peruutus kuvakkeet on poistettu käytöstä ja himmennettynä, jos kaikki muutokset on tallennettu:

    > [!div class="mx-imgBorder"]
    > ![Muutosten tallentaminen ja peruuttaminen @ no__t-1

## <a name="add-an-add-icon"></a>Lisää kuvake

1. Valitse **Lisää** -väli lehdeltä **kuvakkeet** > **Add**.

    > [!div class="mx-imgBorder"]
    > ![Lisää kuvake @ no__t-1

    **Lisää** -kuvake näkyy Oletus arvon mukaan vasemmassa yläkulmassa, jossa muiden ohjaus objektien löytäminen voi olla hankalaa:

    > [!div class="mx-imgBorder"]
    > ![Lisää-kuvakkeen oletus sijainti @ no__t-1

1. Valitse **Aloitus** -väli lehdeltä lisää-kuvakkeen **väri** -ominaisuudeksi valkoinen, muuta kuvakkeen kokoa ja siirrä se peruutus kuvakkeen vasemmalle puolelle:

    > [!div class="mx-imgBorder"]
    > ![Muuta lisää-kuvakkeen väriä, kokoa ja sijaintia @ no__t-1

1. Määritä lisää-kuvakkeen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    NewForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä lisää-kuvakkeen OnSelect-ominaisuudeksi @ no__t-1

    [**NewForm**](functions/function-form.md) -funktiolla näytetään tyhjä tietue lomakkeessa.  

1. Valitse Lisää-kuvakkeen **DisplayMode** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    If( Form1.Unsaved Or Form1.Mode = FormMode.New, DisplayMode.Disabled, DisplayMode.Edit )
    ```

    > [!div class="mx-imgBorder"]
    > ![Lisää kuvakkeen DisplayMode-ominaisuus @ no__t-1

    Kaava poistaa Lisää-kuvakkeen käytöstä näissä olosuhteissa:

    - Käyttäjä tekee muutoksia, mutta ei Tallenna tai Peruuta niitä, mikä on päinvastainen käyttäytyminen tarkistus-ja peruutus kuvakkeissa.
    - Käyttäjä valitsee lisää-kuvakkeen, mutta ei tee muutoksia.

1. Valitse Lisää-kuvakkeen **disabledcolor** -ominaisuudeksi tämä arvo:

    ```powerapps-dot
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Valitse lisää-kuvakkeen DisabledColor-ominaisuus @ no__t-1

    Käyttäjä voi luoda tila uksen, jos hän ei tee muutoksia tai jos hän tallentaa tai peruuttaa tekemäsi muutokset. (Jos käyttäjä valitsee tämän kuvakkeen, hän ei voi valita sitä uudelleen, ennen kuin hän tekee yhden tai useamman muutoksen ja tallentaa tai peruuttaa muutokset):

    > [!div class="mx-imgBorder"]
    > ![Luo tilaus @ no__t-1

> [!NOTE]
> Jos luot ja tallennat tila uksen, sinun on ehkä vieritettävä alaspäin järjestys valikoimassa, jotta voit näyttää uuden tilauksesi. Sillä ei ole kokonaishintaa, koska et ole vielä lisännyt tila uksen tietoja.

## <a name="add-a-trash-icon"></a>Lisää roska kori-kuvake

1. Valitse **Lisää** -väli lehdeltä **kuvakkeet** > **roska koriin**.

    > [!div class="mx-imgBorder"]
    > ![Lisää roska kori kuvake @ no__t-1

    **Roska kori** -kuvake näkyy Oletus arvon mukaan vasemmassa yläkulmassa, jossa muiden ohjaus objektien löytäminen voi olla hankalaa:

    > [!div class="mx-imgBorder"]
    > ![Roska kori kuvakkeen oletus sijainti @ no__t-1

1. Vaihda **Aloitus** -väli lehdellä roska kori-kuvakkeen **väri** -ominaisuudeksi valkoinen, muuta kuvakkeen kokoa ja siirrä se lisää-kuvakkeen vasemmalle puolelle:

    > [!div class="mx-imgBorder"]
    > ![Roska kori kuvakkeen värin, koon ja sijainnin muuttaminen @ no__t-1

1. Määritä Trash-kuvakkeen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    Remove( Orders, Gallery1.Selected )
    ```

    > [!div class="mx-imgBorder"]
    > ![Määritä Trash-kuvakkeen OnSelect-ominaisuudeksi @ no__t-1

    [**Remove**](functions/function-remove-removeif.md) -funktiolla poistetaan tietue tieto lähteestä. Tässä kaavassa tämä ominaisuus poistaa tila uksen valikoimasta valitun tietueen. Roska kori-kuvake näkyy yhteenveto lomakkeen lähellä (ei järjestys valikoimassa), koska lomake näyttää lisä tietoja tietueesta, joten käyttäjä voi helpommin tunnistaa tietueen, jonka kaava poistaa.

1. Valitse Trash-kuvakkeen **DisplayMode** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    If( Form1.Mode = FormMode.New, DisplayMode.Disabled, DisplayMode.Edit )
    ```

    > [!div class="mx-imgBorder"]
    > ![Roska korin kuvakkeen DisplayMode-ominaisuuden arvo on @ no__t-1

    Tämä kaava poistaa käytöstä roska kori-kuvakkeen, jos käyttäjä luo tietueen. **Poista** -funktiolla ei ole poistettavaa tietuetta, ennen kuin käyttäjä tallentaa tietueen.

1. Valitse Trash-kuvakkeen **disabledcolor** -ominaisuudeksi tämä arvo:

    ```powerapps-dot
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Roska korin kuvakkeen DisabledColor-ominaisuuden arvo on @ no__t-1

    Käyttäjä voi poistaa tila uksen.

    > [!div class="mx-imgBorder"]
    > ![Tilausten poistaminen @ no__t-1

## <a name="summary"></a>Yhteenveto

Voit lisätä yhteenvedon lomakkeeseen, jossa käyttäjä voi näyttää ja muokata kunkin tila uksen yhteenvetoa, ja käytit näitä elementtejä:

- Lomake, joka sisältää **tila ukset** -entiteetin tiedot: **Form1. DataSource =** `Orders`
- Lomakkeen ja järjestys valikoiman välinen kytkentä: **Form1. Item =** `Gallery1.Selected`
- **Järjestys numero** -kentän vaihtoehtoinen ohjaus objekti: **Näytä teksti**
- Monta yhteen-suhde, joka näyttää työn tekijän kuvan **työn tekijän** tieto kortissa: `DataCardValue1.Selected.Picture`
- Kuvake, joka tallentaa tila uksen muutokset: `SubmitForm( Form1 )`
- Kuvake, joka peruuttaa tila uksen muutokset: `ResetForm( Form1 )`
- Tila uksen luonnin kuvake: `NewForm( Form1 )`
- Tila uksen poistamis kuvake: `Remove( Orders, Gallery1.Selected )`

## <a name="next-step"></a>Seuraava vaihe

Seuraavassa ohje aiheessa lisäät toisen valikoiman, joka näyttää kunkin tila uksen tuotteet, ja muutat näitä tietoja käyttämällä [**patch**](functions/function-patch.md) -funktiolla.

> [!div class="nextstepaction"]
> [Luo tieto valikoima](northwind-orders-canvas-part3.md)

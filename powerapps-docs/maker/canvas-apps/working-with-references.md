---
title: Tutustu tietue viittauksiin ja polymorfisten hakujen | Microsoft Docs
description: Tietue viittausten ja polymorfisten hakujen käsitteleminen kangas sovelluksissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/14/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ebb7b9d5eb203a32ef0ec931a8f653125e8f5f26
ms.sourcegitcommit: 5899d37e38ed7111d5a9d9f3561449782702a5e9
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/17/2019
ms.locfileid: "71037947"
ms.PowerAppsDecimalTransform: true
---
# <a name="understand-record-references-and-polymorphic-lookups-in-canvas-apps"></a>Tutustu tietue viittauksiin ja polymorfisten hakujen pohjaan kangas sovelluksissa

Kun kirjoitit tutkimus paperin koulussa, olet luultavasti antanut luettelon viittauksista lopussa. Et ole käyttänyt kopiota todellisesta tausta materiaalista, jota käytit, vaan ennemminkin verkko linkkiä, kirjan otsikkoa ja tekijää tai muita tietoja, jotta joku voisi jäljittää alkuperäisen lähteen. Olet sekoitettu erilaisia lähteitä yksittäisessä listassa, sanoma lehti artikkelit ääni tallenteiden vieressä, joista jokaisella on omat tarkat tiedot asianmukaisesta viitteestä. Esimerkiksi Wikipedia-artikkeleihin sisältyy usein [pitkä luettelo viitta uksista](https://en.wikipedia.org/wiki/Microsoft#References).

Kangas sovelluksissa käytät usein tieto lähteistä ladattujen tietueiden kopioita. Voit tunnistaa haluamasi tietueen käyttämällä [**haku**](functions/function-filter-lookup.md) -ja [**suodatus**](functions/function-filter-lookup.md) funktioita ja [**valikoima**](controls/control-gallery.md) -ohjaus objektin **valittua** ominaisuutta. Kaikkien **suodatinten** tai **valittujen** tietueiden entiteettityyppiä on sama, joten voit käyttää kenttiä yksinkertaisella. *Kentän* merkintä. Nämä kopiot sisältävät usein viite tietoja, joiden avulla voit päivittää alkuperäisen lähteen [**patch**](functions/function-patch.md) -funktiolla.

Kangas sovellukset tukevat myös *tietue viittauksia*. Kuten tutkimus-paperi viittaus, tietue viittaus viittaa tietueeseen ilman, että se sisältää täydellisen kopion siitä. Tällainen viittaus voi viitata minkä tahansa entiteetin tietueeseen. Samoin kuin tutkimus-paperi viittaukset, voit sekoittaa tietueita eri entiteeteistä yhdestä sarakkeesta.

Monet tietue viittausten toiminnot ovat identtisiä tietueiden parissa työskentelemisen kanssa. Voit verrata tietue viittauksia toisiinsa ja koko tietue isiin. Voit valita tietue viittauksen arvon käyttämällä **patch** -funktiota samalla tavalla kuin haku, jolla on täydellinen tietue.

On olemassa yksi tärkeä käyttö ero: et voi käyttää tietue viittauksen kenttiä suoraan muodostamatta ensin sitä, mihin entiteettiin se viittaa. Tämä johtuu siitä, että kangas sovellukset edellyttävät, että kaikki tyypit tunnetaan kaavojen kirjoittamisessa. Koska et tiedä tietue viittauksen tyyppiä, ennen kuin sovellus on käynnissä, et voi käyttää yksinkertaista. *Kentän* merkintä suoraan. Entiteettityyppiä on ensin määritettävä dynaamisesti [**Istype**](functions/function-astype-istype.md) -funktiolla ja sitten käytettävä. [**Astionpe**](functions/function-astype-istype.md) -funktion tuloksen *kenttä* merkintä.

*Entiteettityypin* viittaa entiteetin kunkin tietueen rakenteeseen. Kullakin entiteetillä on yksilöivä kenttä joukko, jolla on eri nimet ja tieto tyypit. Entiteetin jokainen tietue perii kyseisen rakenteen; kahdella tietueilla on sama entiteettityyppi, jos ne ovat perä isin samasta entiteetistä.

## <a name="polymorphic-lookups"></a>Polymorfinen haut

Common Data Service tukee tietueiden välisiä suhteita. Jokaisella **accounts** -entiteetin tietueella on **ensisijainen yhteys henkilön** haku kenttä tietueeseen **yhteys tiedot** -entiteetissä. Haku voi viittaa vain **yhteys tiedoissa** olevaan tietueeseen, eikä se voi tarkoittaa esimerkiksi **teamsin** entiteetin tietuetta. Tämä viimeinen yksityiskohta on tärkeä, koska tiedät aina, mitkä kentät ovat käytettävissä hakua varten.

Common Data Service tukee myös polymorfisten hakujen tekemistä, mikä voi tarkoittaa tietueen mistä tahansa sarjan entiteetistä. **Omistaja** -kenttä voi esimerkiksi viittaa tietueeseen **käyttäjät** -entiteetissä tai **teams** -entiteetissä. Sama haku kenttä eri tietueissa voi koskea eri entiteettien tietueita. Tässä tapa uksessa et aina tiedä, mitkä kentät ovat käytettävissä.

Piirto alustan tietue viittaukset suunniteltiin Common Data Service polymorfisten hakujen käsittelemistä varten. Voit myös käyttää tietue viittauksia tämän kontekstin ulkopuolella. Näin nämä kaksi käsitettä eroavat toisistaan.

Seuraavassa osiossa alat tutkia näitä käsitteitä käyttämällä **omistajan** hakua.

## <a name="show-the-fields-of-a-record-owner"></a>Tietueen omistajan kenttien näyttäminen

Jokainen Common Data Service entiteetti sisältää **omistaja** -kentän. Tätä kenttää ei voi poistaa, et voi lisätä toista, ja se edellyttää aina arvoa.

Kentän näyttäminen Tilientiteetissä:

1. Avaa [Tämä PowerApps-sivusto](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
1. Valitse vasemmassa siirtymis palkissa **tieto** > **entiteetit**.
1. Valitse entiteettiluettelosta **tili**.
1. Avaa oikean yläkulman suodatin lista (oletus asetus **on oletus arvo** ) ja valitse sitten **Kaikki**.
1. Vieritä alaspäin, kunnes **omistaja** -kenttä tulee näkyviin.

 > [!div class="mx-imgBorder"]
 > ![Tili-entiteetin omistaja-kenttä](media/working-with-references/owner-field.png)

Tämä haku kenttä voi viittaa tietueeseen joko **tiimit** -entiteetistä tai **käyttäjät** -entiteetistä. Kaikilla näiden entiteettien tietueella ei ole oikeutta olla **omistaja**; Tarkista Tuetut roolit, jos suoritat ongelman.

Tässä kuvassa on yksinkertainen **tili**valikoima, jossa **accounts** -entiteetti on lisätty sovellukseen tieto lähteenä:

> [!div class="mx-imgBorder"]
> ![Valikoima-ohjaus objektissa näkyvät asiakkaat](media/working-with-references/accounts-gallery.png)

> [!IMPORTANT]
> Tässä ohje aiheessa grafiikka näyttää joitakin nimiä ja muita arvoja, jotka eivät ole osa Common Data Service mukana olevia malli tietoja. Vaiheet osoittavat tarkasti, miten voit määrittää ohjaus objektin tiettyä tulosta varten, mutta käyttö kokemuksesi vaihtelee organisaatiosi tietojen mukaan.

Jos haluat näyttää valikoiman kunkin tilin omistajan, saatat haluta käyttää kaavaa **ThisItem.Owner.name**. **Ryhmä** -entiteetin nimi-kenttä on kuitenkin **ryhmän nimi**, ja **käyttäjä** -entiteetin nimi-kenttä on **koko nimi**. Sovellus ei voi tietää, minkä tyyppistä hakua käytät, ennen kuin suoritat sovelluksen, ja se voi vaihdella tietueiden välillä **accounts** -entiteetissä.

Tarvitset kaavan, joka voi sopeutua tähän varianssiin. Sinun on myös lisättävä tieto lähteet entiteettityypsille, jotka **omistaja** voi olla (tässä tapa uksessa **käyttäjät** ja **tiimit**). Lisää nämä kolme tieto lähdettä sovellukseesi:

> [!div class="mx-imgBorder"]
> ![Tieto ruudun accounts, teams ja users-entiteetit](media/working-with-references/accounts-datasources.png)

Kun näitä tieto lähteitä on käytössä, voit näyttää joko käyttäjän tai ryhmän nimen tämän kaavan avulla:

```powerapps-comma
If( IsType( ThisItem.Owner; [@Teams] );
    "Team: " & AsType( ThisItem.Owner; [@Teams] ).'Team Name';
    "User: " & AsType( ThisItem.Owner; [@Users] ).'Full Name' )
```

> [!div class="mx-imgBorder"]
> ![Valikoima-ohjaus objektissa näkyvät Asiakkaat, joiden omistaja-kenttä on näkyvissä](media/working-with-references/accounts-displayowner.png)

Tässä kaavassa **Istype** -funktiolla testataan **omistaja** -kenttää **teamsin** entiteetille. Jos tämä entiteettityyppiä on, **Asitpe** -ominaisuus heittää sen **Ryhmä** tietueeseen. Tässä vaiheessa voit käyttää kaikkia **teamsin** entiteetin kenttiä, mukaan lukien **tiimin nimeä**, käyttämällä kohdetta *. Kentän* merkintä. Jos **Istype** määrittää, että **omistaja** ei ole tietue **teamsin** entiteetissä, kentän on oltava tietue **käyttäjä** -entiteetissä, koska **omistaja** -kenttä vaaditaan (ei voi olla *tyhjä*).

Käytät [Global-operaattoria](functions/operators.md#disambiguation-operator) **[@Teams]** ja **[@Users]** , jotta voit varmistaa, että käytät yleistä entiteettityyppiä. Et tarvitse sitä tässä tapa uksessa, mutta se on hyvä tapa muodostaa. Yksi moneen-suhteista on usein risti riidassa valikoiman tietue alueen kanssa, ja tämä käytäntö välttää sekaannuksen.

Jos haluat käyttää tietue viittauksen kenttiä, sinun on ensin käytettävä **Asype** -funktiolla sitä tietyn entiteettityypin. Et voi käyttää kenttiä suoraan **omistaja** -kentästä, koska järjestelmä ei tiedä, mitä entiteettityyppiä haluat käyttää.

**Asttype** -funktio palauttaa virheen, jos **omistaja** -kenttä ei vastaa pyydettyä entiteettityyppiä, joten voit yksinkertaistaa tätä kaavaa **iferror** -funktiolla. Ota ensin käyttöön kokeellisen ominaisuuden **kaava tason virheiden hallinta**:

> [!div class="mx-imgBorder"]
> ![Kokeellinen valitsin, jolla voidaan ottaa käyttöön kaava tason virheiden hallinta](media/working-with-references/accounts-iferror.png)

Korvaa sitten edellinen kaava tällä:

```powerapps-comma
IfError(
    "Team: " & AsType( ThisItem.Owner; [@Teams] ).'Team Name';
    "User: " & AsType( ThisItem.Owner; [@Users] ).'Full Name' )
```

## <a name="filter-based-on-an-owner"></a>Suodata omistajan mukaan

Onnittelut – olet saanut valmiiksi tietueen viitta uksen työstämistä koskevan vaikeimman näkö kohdan. Muut käyttö tapaukset ovat yksinkertaisemmin, koska ne eivät käytä tietueen kenttiä. Ota kohdassa huomioon suodatus, jota tutustut tässä osiossa.

Lisää **yhdistelmä ruutu** -ohjaus objekti valikoiman yläpuolelle ja määrittää nämä uuden ohjaus objektin ominaisuudet:

- **Kohteet**:`Users`
- **Selectmultiple**:`false`

> [!div class="mx-imgBorder"]
> ![Lisätty yhdistelmä ruutu-ohjaus objekti valikoiman yläpuolelle, kun Items-ominaisuus on valittu käyttäjille](media/working-with-references/filter-insert-combobox.png)

Jos haluat suodattaa valikoiman tämän yhdistelmä ruudun valitun käyttäjän mukaan, valitse valikoiman **kohteet** -ominaisuudeksi Tämä kaava:

```powerapps-comma
Filter( Accounts; Owner = ComboBox1.Selected )
```

> [!div class="mx-imgBorder"]
> ![Suodatettu valikoima yhdistelmä ruutu-ohjaus objektissa määritetyn arvon perusteella](media/working-with-references/filter-accounts.png)

> [!IMPORTANT]
> Tämän ohje aiheen ohjeet ovat tarkkoja, jos noudatat vaiheita tarkalleen. Mikä tahansa kaava, joka viittaa sen nimen mukaiseen ohjaus objektiin, epäonnistuu kuitenkin, jos ohjaus objektissa on eri nimi. Jos poistat ja lisäät samaa tyyppiä olevan ohjaus objektin, ohjaus objektin nimen lopussa oleva luku muuttuu. Jos kaava näyttää virheen, varmista, että se sisältää kaikkien ohjaus objektien oikeat nimet.

Sinun ei tarvitse käyttää **istype-tai Astynpe** -menetelmää, koska vertaat tietue viittauksia muihin tietue viittauksiin tai täydellisiin tietue isiin. Sovellus tuntee entiteettityypin **ComboBox1. Selected** , koska se on johdettu **käyttäjät** -entiteetistä. Asiakkaat, joiden omistaja on ryhmä, eivät vastaa suodatus ehtoa.

Voit saada hieman hienouuden tukemalla suodatusta joko käyttäjä tai ryhmä.

1. Vapauta tilaa näytön yläreunassa muuttamalla valikoiman kokoa ja siirtämällä yhdistelmä ruutua, lisäämällä [ **valinta** ](controls/control-radio.md) merkki valikoiman yläpuolelle ja määrittämällä sitten nämä ominaisuudet uudelle ohjaus objektille:

    - **Kohteet**:`[ "All"; "Users"; "Teams" ]`
    - **Ulkoasu**:`Layout.Horizontal`

1. Määritä **yhdistelmä ruutu** -ohjaus objektille tämä ominaisuus (jos yhdistelmä ruutu katoaa, valitse Radio-ohjaus objektin **käyttäjät** ):

    - **Näkyvä**:`Radio1.Selected.Value = "Users"`

1. Kopioi ja liitä **yhdistelmä ruutu** -ohjaus objekti, siirrä kopio suoraan alkuperäisen päälle ja aseta sitten nämä ominaisuudet kopiolle:

    - **Kohteet**:`Teams`
    - **Näkyvä**:`Radio1.Selected.Value = "Teams"`

    Sovellus näyttää vain yhden yhdistelmä ruudun kerrallaan Radio-ohjaus objektin tilan mukaan. Koska ne ovat suoraan toistensa yläpuolella, ne näyttävät olevan sama ohjaus objekti, joka muuttaa sen sisältöä.

1. Valitse lopuksi **valikoima** -ohjaus objektin **Items** -ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    Filter( Accounts;
        Radio1.Selected.Value = "All"
        Or (Radio1.Selected.Value = "Users" And Owner = ComboBox1.Selected)
        Or (Radio1.Selected.Value = "Teams" And Owner = ComboBox1_1.Selected)
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Suodatettu valikoima, joka näyttää kaikki tietueet tai tietyn käyttäjän tai ryhmän](media/working-with-references/filter-combobox.png)

Näiden muutosten avulla voit näyttää kaikki tietueet tai suodattaa ne joko käyttäjän tai ryhmän perusteella:

> [!div class="mx-imgBorder"]
> ![Animaatio, joka näyttää eri suodatetut tulokset Radio-ohjaus objektin ja yhdistelmä ruutujen perusteella](media/working-with-references/filter-allthree.gif)

Kaava on täysin delegoitava. Osa, joka vertaa valinta nappi arvoja, on vakio kaikissa tietueissa, ja se arvioidaan, ennen kuin muut suodattimet lähetetään Common Data Service.

Jos haluat suodattaa omistajan tyypin mukaan, voit käyttää **Istype** -toimintoa, mutta sitä ei ole vielä delegoitava.

> [!div class="mx-imgBorder"]
> ![Suodata omistajan tyypin mukaan IsType-toiminnon avulla](media/working-with-references/filter-bytype.png)

## <a name="update-the-owner-by-using-patch"></a>Päivitä omistaja käyttämällä korjaus tiedostoa

Voit päivittää **omistaja** -kentän samalla tavalla kuin mitä tahansa muuta hakua. Jos haluat, että valittuna olevan tilin omistaja on määritetty ensimmäiselle työryhmälle:

```powerapps-comma
Patch( Accounts; Gallery1.Selected; { Owner: First( Teams ) } )
```

Tämä lähestymis tapa ei poikkea normaalista haku-tyypistä, koska sovellus tuntee **ensimmäisen (tiimit)** tyypin. Jos haluat sen sijaan ensimmäisen käyttäjän, korvaa kyseinen osa **ensin (käyttäjät)** . **Patch** -funktiolla tiedetään, että **omistaja** -kentän arvoksi voidaan valita jompikumpi näistä kahdesta entiteettityypistä.

Tämän ominaisuuden lisääminen sovellukseen:

1. Valitse **puunäkymä** -ruudussa **Radio** -ohjaus objekti ja kaksi **yhdistelmä ruutu** -ohjaus objektia samalla kertaa.

1. Valitse kolme pistettä-valikosta **Kopioi nämä kohteet**.

    > [!div class="mx-imgBorder"]
    > ![Useiden ohjaus objektien kopio puunäkymän avulla](media/working-with-references/patch-copy.png)

1. Valitse samasta valikosta **Liitä**.

    > [!div class="mx-imgBorder"]
    > ![Useiden ohjaus objektien liittäminen puunäkymän avulla](media/working-with-references/patch-paste.png)

1. Siirrä kopio idut ohjaus painikkeet valikoiman oikealle puolelle.

    > [!div class="mx-imgBorder"]
    > ![Siirretty kopio idut ohjaus painikkeet valikoiman oikealle puolelle](media/working-with-references/patch-position.png)

1. Valitse kopioitu **Radio** -ohjaus objekti ja muuta näitä ominaisuuksia:

    - Kohteet`[ "Users"; "Teams" ]`
    - Oletus`If( IsType( Gallery1.Selected.Owner; Users ); "Users"; "Teams" )`

    > [!div class="mx-imgBorder"]
    > ![Poistettu kaikki valinta Radio-ohjaus objektista](media/working-with-references/patch-noall.png) 

1. Valitse **Radio** -ohjaus objektissa **käyttäjät** niin, että luettelo käyttäjistä on näkyvissä **yhdistelmä ruutu** -ohjaus objekti.

1. Valitse näkyvä **yhdistelmä ruutu** -ohjaus objekti ja Määritä **Defaulttselecteditems** -ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    If( IsType( Gallery1.Selected.Owner; Users );
        AsType( Gallery1.Selected.Owner; Users );
        Blank()
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Käyttäjien yhdistelmä ruutuun määritetty oletus ominaisuus](media/working-with-references/patch-default-users.png)

1. Valitse **Radio** -ohjaus objektissa **joukkueet** , jotta **yhdistelmä ruutu** -ohjaus objekti, joka luetteloi tiimit, on näkyvissä.

1. Valitse valinta **nappi** , jos haluat ottaa valinnan pois käyttäjien nyt näkymätön- **yhdistelmä ruutu** -ohjaus objektista.

1. Valitse ryhmien näkyvä **yhdistelmä ruutu** -ohjaus objekti ja aseta sen **Defaulselecteditems** -ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    If( IsType( Gallery1.Selected.Owner; Teams );
        AsType( Gallery1.Selected.Owner; Teams );
        Blank()
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Teamsin yhdistelmä ruutuun määritetty oletus ominaisuus](media/working-with-references/patch-default-teams.png)

1. Lisää **painike** -ohjaus objekti, siirrä se **yhdistelmä ruutu** -ohjaus objektin alle ja Aseta painikkeen **teksti** -ominaisuudeksi `"Patch Owner"`.

1. Määritä painikkeen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Patch( Accounts; Gallery1.Selected;
        { Owner: If( Radio1_1.Selected.Value = "Users";
                ComboBox1_2.Selected;
                ComboBox1_3.Selected ) } )
    ```

    > [!div class="mx-imgBorder"]
    > ![Painikkeen ohjaus objektin kaava](media/working-with-references/patch-button.png)

Kopioitu **Radio** -ja **yhdistelmä ruutu** -ohjaus objekti näyttää valikoiman valittuna olevan tilin omistajan. Samoilla ohjaus objekteilla voit määrittää tilin omistajan mille tahansa työryhmälle tai käyttäjälle valitsemalla painikkeen:

> [!div class="mx-imgBorder"]
> ![Animaatio, joka näyttää omistajan, joko käyttäjän tai ryhmän, korjauksen](media/working-with-references/patch-allthree.gif)

## <a name="show-the-owner-by-using-a-form"></a>Omistajan näyttäminen lomakkeen avulla

Voit näyttää **omistaja** -kentän lomakkeen sisällä lisäämällä mukautetun kortin. Tätä kirjoitettaessa et voi muuttaa kentän arvoa lomake-ohjaus objektin avulla.

1. Lisää **Muokkaa lomaketta** -ohjaus objekti ja muuta sen kokoa ja siirrä se oikeaan alakulmaan.

1. Avaa **Ominaisuudet** -väli lehden näytön oikean puolen lähellä oleva **tieto lähde** luettelo ja valitse sitten **accounts**.

    > [!div class="mx-imgBorder"]
    > ![Lomake-ohjaus objekti, joka näyttää tyhjät arvot sisältäviä lisä kenttiä](media/working-with-references/form-insert.png)  

1. Valitse lomakkeen **Item** - `Gallery1.Selected`ominaisuudeksi.

    > [!div class="mx-imgBorder"]
    > ![Lomake-ohjaus objekti, joka näyttää valikoiman valitusta kohteesta asuttuja lisä kenttiä](media/working-with-references/form-item.png)

1. Valitse **Ominaisuudet** -väli lehdeltä näytön oikean puolen lähellä **Muokkaa kenttiä**.

1. Valitse **kentät** -ruudussa kolme pistettä ja valitse sitten **Lisää mukautettu kortti**.

    > [!div class="mx-imgBorder"]
    > ![Komento mukautetun kortin lisäämistä varten](media/working-with-references/form-customcard.png)

    Uusi kortti näkyy lomake-ohjaus objektin alaosassa.

1. Muuta kortin kokoa tarvittaessa, jotta näet kaiken tekstin.

    > [!div class="mx-imgBorder"]
    > ![Lisätyn mukautetun kortin, tyhjä](media/working-with-references/form-inserted-customcard.png)

1. Lisää **Selite** -ohjaus objekti mukautettuun korttiin ja määritä sitten selitteen **teksti** -ominaisuudeksi kaava, jota käytit valikoimassa:

    ```powerapps-comma
    If( IsType( ThisItem.Owner; Teams );
        "Team: " & AsType( ThisItem.Owner; Teams ).'Team Name';
        "User: " & AsType( ThisItem.Owner; Users ).'Full Name' )
    ```

    > [!div class="mx-imgBorder"]
    > ![Mukautettu kortti, joka näyttää omistaja-kentän selite ohjaus objektissa](media/working-with-references/form-displayowner.png)

Valikoiman kullekin valinnalle näytetään-lomakkeessa Lisää tilin kenttiä, mukaan lukien tietueen omistaja. Jos muutat omistajaa käyttämällä **patch** -painiketta, myös lomake-ohjaus objekti ilmaisee muutoksen.

> [!div class="mx-imgBorder"]
> ![Animaatio, joka näyttää lomake-ohjaus objektin, joka vastaa valikoiman muutoksiin](media/working-with-references/form-allthree.gif)

## <a name="show-the-fields-of-a-customer"></a>Näytä asiakkaan kentät

Common Data Service **asiakas** haku kenttä on toinen polymorfinen haku, joka on hyvin samankaltainen kuin **omistaja**.

**Omistaja** on rajoitettu yhteen entiteettiä kohti, mutta entiteetit voivat sisältää nollan, yhden tai useamman **asiakkaan** haku kentän. **Contacts** System-entiteetti sisältää **yrityksen nimi** -kentän, joka on **asiakkaan** haku kenttä.

> [!div class="mx-imgBorder"]
> ![Yhteys henkilö-entiteetti, joka näyttää yrityksen nimi-kentän asiakas tieto tyyppinä, jota ei vaadita](media/working-with-references/customer-companyname.png)

Voit lisätä entiteettiin Lisää **asiakkaan** haku kenttiä valitsemalla uuden kentän **asiakas** tieto tyypin.

![Asiakas tieto tyyppi tieto tyyppien luettelo kenttää luotaessa](media/working-with-references/customer-datatype.png)

**Asiakas** haku kenttä voi viittaa tietueeseen joko **accounts** -entiteetistä tai **Contacts** -entiteetistä. Käytät **Istype-ja Astynpe** -funktioita näiden entiteettien kanssa, joten nyt on hyvä aika lisätä ne tieto lähteiksi (voit jättää **tiimit** ja **käyttäjät** paikoilleen).

> [!div class="mx-imgBorder"]
> ![Tieto ruudun accounts, teamsin, users ja Contacts-entiteetit](media/working-with-references/customer-datasources.png)

**Asiakas** -ja **omistaja** -kenttien käsittely on niin samanlaista, että voit kirjaimellisesti kopioida sovelluksen (**tiedosto** > **Tallenna nimellä**ja määrittää sitten eri nimen) ja tehdä nämä yksinkertaiset vaihdot:

| Location | **Omistajan** malli | **Asiakas** malli |
|----------|-----------|------------------|
| Koko | **Omistaja** | **' Asiakkaan nimi '** |
| Koko | **Käyttäjät** | **Tilit** |
| Koko | **Teams** | **Yhteys tiedot** |
| Valikoiman **kohteet** -ominaisuus | **Tilit** | **Yhteys tiedot** |
| Lomakkeen **Items** -ominaisuus | **Tilit** | **Yhteys tiedot** |
| **Korjauksen** ensimmäinen argumentti<br>painikkeen **onselect** -ominaisuudessa | **Tilit** | **Yhteys tiedot** |
| Suodata radion **kohteet** -ominaisuus | **[&nbsp;"Kaikki";&nbsp;"käyttäjät";&nbsp;"tiimit"&nbsp;]** | **[&nbsp;"Kaikki";&nbsp;"Accounts"&nbsp;; "Contacts"&nbsp;]** |
| Patch radion **Items** -ominaisuus | **["Käyttäjät"; "tiimit"]** | **["Accounts"; "Contacts"]** |
| Yhdistelmä ruudun **näkyvä** ominaisuus | **"Käyttäjät"** ja **"tiimit"** | **"Accounts"** ja **"Contacts"** |

Esimerkiksi uudella valikoimalla on oltava tämä **Items** -ominaisuus:

```powerapps-comma
Filter( Contacts;
    Radio1.Selected.Value = "All"
    Or (Radio1.Selected.Value = "Accounts" And 'Company Name' = ComboBox1.Selected)
    Or (Radio1.Selected.Value = "Contacts" And 'Company Name' = ComboBox1_1.Selected)
)
```

> [!div class="mx-imgBorder"]
> ![Omistaja sovelluksesta johdettu asiakas sovellus, jossa on käytetty yksinkertaisia muutoksia](media/working-with-references/customer-simple-update.png)

Kaksi tärkeää eroa **asiakkaan** ja **omistajan** välillä edellyttää päivitystä valikoiman ja lomakkeen sisällä oleviin kaavoihin:

1. Yksi moneen-suhde **asiakkaiden** ja **yhteys henkilöiden** välillä on etusijalla, kun viittaat näihin entiteettityypin nimen mukaan. Käytä  **\[tilin sijaan accounts];;yhteystietojensijastayhteystietoja].\@**  **\[ \@** Kun käytät maailmanlaajuista Saksan operaattoria, varmistat, että viittaat entiteettityypin **Istype-ja Astynpe** - [operaattoriin](functions/operators.md#disambiguation-operator). Tämä ongelma on vain valikoima-ja lomake-ohjaus objektien tietue kontekstista.

1. **Omistaja** -kentällä on oltava arvo, mutta **asiakas** kentät voivat olla *tyhjiä*. Jos haluat näyttää oikean tuloksen ilman tyypin nimeä, testaa tätä tapausta [ **isblank** -funktiolla](functions/function-isblank-isempty.md)ja Näytä sen sijaan tyhjä teksti merkki jono.

Molemmat näistä muutoksista ovat samassa kaavassa, joka näkyy lomakkeen mukautetussa kortissa sekä valikoiman nimi-ohjaus objektin **teksti** -ominaisuudessa:

```powerapps-comma
If( IsBlank( ThisItem.'Company Name' ); "";
    IsType( ThisItem.'Company Name'; [@Accounts] );
        "Account: " & AsType( ThisItem.'Company Name'; [@Accounts] ).'Account Name';
    "Contact: " & AsType( ThisItem.'Company Name'; [@Contacts] ).'Full Name'
)
```

> [!div class="mx-imgBorder"]
> ![Päivitä valikoiman tekstityksen otsikko-ohjaus objektin Text-ominaisuus](media/working-with-references/customer-update.png)

Näiden muutosten avulla voit tarkastella ja muuttaa **yrityksen nimi** -kenttää **yhteys tiedot** -entiteetissä.

> [!div class="mx-imgBorder"]
> ![Animaatio, joka osoittaa, miten yhteys henkilön valitseminen muuttaa muita ohjaus objektin ja lomakkeen](media/working-with-references/customer-allthree.gif)

## <a name="understand-regarding-lookup-fields"></a>Tietoja haku kentistä

**Liittyy** -haku kenttä eroaa hieman niistä, jotka olet jo käsitellyt tässä aiheessa. Aloitat käyttämällä tähän aiheeseen aiemmin kuvattuja kuvioita, niin opit myös muita temppuja.

Voit aloittaa yksinkertaisesti **Faksi** -entiteetissä. Tällä entiteetillä on polymorfinen **koskien** haku kenttää, joka voi koskea **asiakkaita**, **yhteyshenkilöitä**ja muita entiteettejä. Voit ottaa sovelluksen käyttöön **asiakkaille** ja muokata sitä **fakseja**varten.

| Location | **Asiakas** malli | **Faksien** malli |
|----------|-----------|------------------|
| Koko | **' Asiakkaan nimi '** | **Koskevat** |
| Valikoiman **kohteet** -ominaisuus | **Yhteys tiedot** | **Faksit** |
| Lomakkeen **Items** -ominaisuus | **Yhteys tiedot** | **Faksit** |
| **Korjauksen** ensimmäinen argumentti<br> painikkeen **onselect** -ominaisuudessa | **Yhteys tiedot** | **Faksit** |

Sinun on lisättävä tieto lähde: tällä kertaa **fakseja**varten. Valitse **näkymä** -väli lehdeltä **tieto lähteet**:

> [!div class="mx-imgBorder"]
> ![Tieto ruutu, jossa näkyvät Asiakkaat, tiimit, käyttäjät, yhteys henkilöt ja faksit](media/working-with-references/faxes-datasources.png)

Tärkeä **ero liittyy siihen** , että se ei rajoitu vain **asiakkuudet** ja **yhteys henkilöt**. Entiteettien luettelo on itse asiassa laajennettavissa mukautetuilla entiteeteillä. Suurin osa sovelluksesta mahtuu tähän pisteeseen ilman muokkausta, mutta sinun täytyy päivittää kaavan nimi valikoimassa ja lomakkeessa:

```powerapps-comma
If( IsBlank( ThisItem.Regarding ); "";
    IsType( ThisItem.Regarding; [@Accounts] );
        "Account: " & AsType( ThisItem.Regarding; [@Accounts] ).'Account Name';
    IsType( ThisItem.Regarding; [@Contacts] );
        "Contacts: " & AsType( ThisItem.Regarding; [@Contacts] ).'Full Name';
    ""
)
```

> [!div class="mx-imgBorder"]
> ![Otsikko-ohjaus objektin päivitetty teksti-ominaisuus koskien hakuja](media/working-with-references/regarding-label.png)

Kun olet tehnyt nämä muutokset, voit **käyttää liittyy-hakua samalla** tavalla kuin teit **omistajan** ja **asiakkaan** haut.

> [!div class="mx-imgBorder"]
> ![Animaatio, joka osoittaa, miten kohteen valitseminen valikoimassa muuttaa muita ohjaus objektien ja lomakkeen](media/working-with-references/regarding-allthree.gif)

## <a name="understand-regarding-relationships"></a>Tietoja suhteista

**Liittyen** eroaa **omistajasta** ja **asiakkaasta** , koska edellinen koskee monta yhteen-suhdetta. Käänteisen, yksi moneen-suhteen avulla voit kirjoittaa **ensin (accounts). Faksit**.

Varmuuskopioidaan ja tarkastellaan entiteettimäärityksiä. Common Data Service-entiteettejä, **kuten fakseja**, **tehtäviä**, **Sähkö posti viestejä**, **muistiinpanoja**, **puhe luita**, **kirjeitä**ja **keskusteluja** , on määritetty [*aktiviteeteiksi*](../../developer/common-data-service/activity-entities.md). Voit myös luoda omia [mukautettuja toimintoentiteettejä](../../developer/common-data-service/custom-activities.md). Kun tarkastelet tai luot Activity-entiteettiä, sen asetukset näkyvät **Lisää asetuksia**-kohdassa.

![Entiteetin luonnin yhteydessä tehtävän entiteetin asetus](media/working-with-references/activity-entitytype.png)

Muut entiteetit voivat liittyä Activity-entiteettiin, jos ne on otettu käyttöön tehtävä *tehtävinä* entiteetin asetuksissa. **Asiakkaat**, **yhteys henkilöt**ja monet muut vakioentiteetit on määritetty (jälleen **Lisää asetuksia**-kohdassa).

![Tehtävä tehtävän asetus entiteetin luonnin yhteydessä](media/working-with-references/activity-entityuse.png)

Kaikilla toimintoentiteeteillä ja toimintotehtäväentiteeteillä on epäsuora suhde. Jos muutat suodatinta **Kaikki** näytön yläreunassa, valitse **faksit** -entiteetti ja valitse sitten **yhteydet** -väli lehti, Kaikki entiteetit, jotka voivat olla kohteena **olevan haun kohde** , näkyvät.

> [!div class="mx-imgBorder"]
> ![Monta yhteen-suhteita koskevien faksien entiteetin yhteydet](media/working-with-references/activity-manytoone.png)

Jos näytät **accounts** -entiteetin yhteydet, näkyviin tulee kaikki entiteetit, jotka voivat olla **liittyy** -haku kentän lähde.

> [!div class="mx-imgBorder"]
> ![Asiakkuus-entiteetin yhteydet, jotka koskevat yksi-moneen-suhteita](media/working-with-references/activity-onetomany.png)

Mitä se tarkoittaa?

- Kun kirjoitat kaavoja, sinun on otettava huomioon, että toimintoentiteettien luettelo ei ole kiinteä, ja voit luoda oman. Kaavan on hoidettava asianmukaisesti toiminta-entiteetti, jota ei odotettu.
- Tehtävä tehtävillä ja aktiviteeteillä on yksi-moneen-suhde. Voit helposti pyytää kaikkia tiliin liittyviä fakseja.

Tutustu tähän käsitteeseen sovelluksessa:

1. Lisää toinen näyttö.

    > [!div class="mx-imgBorder"]
    > ![Tyhjän näytön lisääminen](media/working-with-references/activitypointer-newscreen.png)

1. Lisää valikoima-ohjaus objekti, muuta sen kokoa ja siirrä se sitten näytön vasempaan reunaan.

1. Valitse **Ominaisuudet** -väli lehdestä näytön oikean puolen vieressä valikoiman **kohteet** **tiliksi**.

    > [!div class="mx-imgBorder"]
    > ![Kohteiden lisääminen accounts-ominaisuus ruutuun](media/working-with-references/activitypointer-accounts.png)

1. Määritä valikoiman asetteluksi **otsikko**ja määritä sitten title-kentän arvoksi **tilin nimi**.

    > [!div class="mx-imgBorder"]
    > ![Valitse ominaisuudet-ruudun valikoima-ohjaus objektin asetteluksi](media/working-with-references/activitypointer-account-name.png)

1. Lisää toinen valikoima, muuta sen kokoa ja siirrä se sitten näytön oikealle puolelle.

1. Valitse uuden valikoiman **Items** - `Gallery2.Selected.Faxes`ominaisuudeksi.

    Tämä vaihe palauttaa määritetyn tilin suodatetun faksien luettelon.

    > [!div class="mx-imgBorder"]
    > ![Valitse sen valikoiman Items-ominaisuus, joka sisältää fakseja](media/working-with-references/activitypointer-faxes.png)

1. Aseta valikoiman asetteluksi **otsikko ja alaotsikko**ja aseta sitten otsikko-kenttä näyttämään **Aihe** -kenttä (joka voi olla pieni **Aihe**).

    > [!div class="mx-imgBorder"]
    > ![Valitse otsikko aihe-kenttään](media/working-with-references/activitypointer-subject.png)

Kun valitset kohteen tili luettelosta, faksien luettelossa näkyvät vain kyseisen tilin faksit.

> [!div class="mx-imgBorder"]
> ![Animaatio, joka näyttää valikoiman Faksi luettelon ajavassa tilit-valikoimassa](media/working-with-references/activitypointer-allthree.gif)

## <a name="activity-entity"></a>Aktiviteetin entiteetti

Kuten edellisessä osiossa kuvataan, voit näyttää kaikki tilin faksit. Voit kuitenkin myös näyttää kaikki tilin toiminnot, kuten faksit, sähkö posti viestit, puhelut ja muut toimet.

Jälkimmäisessä skenaariossa käytät **Activity** -entiteettiä. Voit näyttää tämän entiteetin kääntämällä **Kaikki** -kohdan oikeassa yläkulmassa, jolloin voit poistaa suodattimen entiteettiluettelosta.

> [!div class="mx-imgBorder"]
> ![Tehtävä-entiteetin näyttämisessä käytettävien entiteettien luettelo](media/working-with-references/activitypointer-entity.png)

**Aktiviteetti** -entiteetti on erityinen. Aina, kun lisäät tietueen Faxes-entiteettiin, järjestelmä myös luo **aktiviteetti** - **entiteetissä** tietueen, joka sisältää kaikkien Aktiviteetti entiteettien yleiset kentät. Näistä kentistä **Aihe** on yksi mielenkiintoisimmista.

Voit näyttää kaikki aktiviteetit muuttamalla vain yhtä riviä edellisessä esimerkissä. Korvaa `Gallery2.Selected.Faxes` käyttäen `Gallery2.Selected.Activities`.

> [!div class="mx-imgBorder"]
> ![Toisen valikoiman Items-ominaisuuden muutos, faksauksen muuttaminen toimintoihin](media/working-with-references/activitypointer-gallery.png)

Tietueet tulevat **Activity** -entiteetistä, mutta voit kuitenkin käyttää **istype** -toimintoa tunnistamaan, millaista toimintaa ne ovat. Sinun on lisättävä tieto lähde, ennen kuin käytät **Istype** -kohdetta entiteettityyppiä.

> [!div class="mx-imgBorder"]
> ![Tieto ruutu, jossa näkyvät kaikki IsType-funktion edellyttämät entiteetit](media/working-with-references/activity-datasources.png)

Käyttämällä tätä kaavaa voit näyttää tietue tyypin valikoiman otsikko-ohjaus objektissa:

```powerapps-comma
If( IsType( ThisItem; [@Faxes] ); "Fax";
    IsType( ThisItem; [@'Phone Calls'] ); "Phone Call";
    IsType( ThisItem; [@'Email Messages'] ); "Email Message";
    IsType( ThisItem; [@Chats] ); "Chat";
    "Unknown"
)
```

> [!div class="mx-imgBorder"]
> ![Valitse teksti-ominaisuudeksi kaava, joka näyttää faksien, puhe luiden ja muiden toimintojen tiedot](media/working-with-references/activitypointer-type.png)

Voit käyttää myös **asttype** -menetelmää tietyn tyypin kenttien käyttämiseen. Tämä kaava määrittää esimerkiksi kunkin tehtävän tyypin ja puhelin puheluiden puhelin numeron ja puhelu suunnan **Puhelin numerot** -entiteetistä:

```powerapps-comma
If( IsType( ThisItem; [@Faxes] ); "Fax";
    IsType( ThisItem; [@'Phone Calls'] );
       "Phone Call: " &
       AsType( ThisItem; [@'Phone Calls'] ).'Phone Number' &
       " (" & AsType( ThisItem; [@'Phone Calls'] ).Direction & ")";
    IsType( ThisItem; [@'Email Messages'] ); "Email Message";
    IsType( ThisItem; [@Chats] ); "Chat";
    "Unknown"
)
```

> [!div class="mx-imgBorder"]
> ![Laajennetun tekstin ominaisuus, jossa on lisä tietoja puhe luun](media/working-with-references/activitypointer-phonecall.png)

Tämän seura uksena sovellus esittää täydellisen luettelon toiminnoista. **Aihe** -kenttä näkyy kaikentyyppisissä tehtävissä, olipa kaava otettu huomioon tai ei. Jos sinulla on sellaisia toiminta tyyppejä, joista tiedät, voit näyttää niiden tyyppi nimet ja tyyppi tiedot kustakin tehtävästä.

> [!div class="mx-imgBorder"]
> ![Valmis näyttö, joka näyttää eri toimintojen tiedot](media/working-with-references/activitypointer-complete.png)

## <a name="notes-entity"></a>Notes-entiteetti

Tähän mennessä kaikki **liittyvät** esimerkit perustuvat toimintoihin, mutta **Notes** -entiteetti edustaa toista tapausta.

Kun luot entiteetin, voit ottaa liitteet käyttöön.

> [!div class="mx-imgBorder"]
> ![Liitteiden ja muistiinpanojen käyttöönottoa entiteetin luonnin yhteydessä](media/working-with-references/notes-entity.png)

Jos valitset valinta ruudun liitteiden ottamista käyttöön, luot **liittyvän** suhteen **Notes** -entiteettiin, koska tämä graafinen näytetään **accounts** -entiteetissä:

> [!div class="mx-imgBorder"]
> ![Tili-entiteetti, joka näyttää suhteen muistiinpanoihin yksi-moneen-suhteen kautta](media/working-with-references/notes-relationships.png)

Tätä eroa lukuun ottamatta käytät **liittyy** -hakua samalla tavalla kuin käytät toimintoja. Entiteeteille, jotka on otettu käyttöön liitteille, on yksi moneen-suhde **muistiinpanoihin**, kuten tässä esimerkissä:

`First( Accounts ).Notes`

> [!NOTE]
> Tätä kirjoitettaessa **liittyy** -haku ei ole käytettävissä **Notes** -entiteetille. Et voi lukea tai suodattaa **liittyy** -kentän perusteella, etkä voi valita kenttää käyttämällä **patch**-menetelmää.
>
> Käänteisen **huomautuksen** yksi-moneen-suhde on kuitenkin käytettävissä, joten voit suodattaa liite tietojen luettelon tietueelle, joka on otettu käyttöön liitteille. [**Relate**](functions/function-relate-unrelate.md) -funktiolla voit myös lisätä huomautuksen tietueen **Notes** -taulukkoon, mutta Huomautus täytyy luoda ensin, kuten tässä esimerkissä:
>
>`Relate( ThisItem.Notes; Patch( Notes; Defaults( Notes ); { Title: "A new note" } ) )`

## <a name="activity-parties"></a>Aktiviteetti juhlat

Tämän kirjoituksen alusta sovellukset eivät tue toiminta osapuolia.
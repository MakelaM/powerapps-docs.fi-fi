---
title: Relate-ja Unrelate-Funktiot | Microsoft Docs
description: Powerappsin Relate-ja Unrelate-funktioiden viite tiedot, mukaan lukien syntaksi ja esimerkki
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/22/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d8ba0cef60b268caafb57e18ae80a522905ba45b
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992757"
ms.PowerAppsDecimalTransform: true
---
# <a name="relate-and-unrelate-functions-in-powerapps"></a>Powerappsin Relate-ja Unrelate-Funktiot

Yhdistä Kahden entiteetin tietueet yhteen moneen-tai monta-moneen-suhteen kautta.

## <a name="description"></a>Kuvaus

**Relate** -funktiolla linkit ovat kaksi tietuetta yksi-moneen-tai monta-moneen-suhteen Common Data Service. **Unrelate** -toiminto kumoaa prosessin ja poistaa linkin.

Yksi-moneen-yhteyksissä monilla entiteetillä on viite avain kenttä, joka osoittaa yhden entiteetin tietueeseen. **Relate** määrittää tämän kentän näyttämään yhden entiteetin tietyn tietueen, kun taas **unrelate** määrittää tämän kentän *tyhjäksi*. Jos kenttä on jo määritetty, kun **Relate** kutsutaan, olemassa oleva linkki katoaa uuden linkin hyväksi. Voit myös määrittää tämän kentän käyttämällä [**patch**](function-patch.md) -toimintoa tai **[Muokkaa lomaketta](../controls/control-form-detail.md)** -ohjaus objektia. **Relate** -funktiolla ei tarvitse käyttää.

Monille moneen-suhteille järjestelmä, joka linkittää tietueet, ylläpitää piilotetun liitoksen taulukkoa. Et voi käyttää tätä Join-taulukkoa suoraan; sitä voi lukea vain yksi-moneen-projektion avulla ja asettaa **Relate** -ja **unrelate** -funktioiden kautta. Millään liittyvällä entiteetillä ei ole viite avainta.

Ensimmäisessä argumentissa määrittämäsi entiteetin tiedot päivitetään vastaamaan muutosta, mutta toisessa argumentissa määrittämäsi entiteetin tiedot eivät. Tiedot on päivitettävä manuaalisesti **[Refresh](function-refresh.md)** -funktiolla näyttämään toiminnon tuloksen.

Nämä funktiot eivät koskaan Luo tai poista tietuetta. Ne koskevat vain kahta jo olemassa olevaa tietuetta tai yhdistävät ne.

Voit käyttää näitä funktioita vain [toiminta kaavoissa](../working-with-formulas-in-depth.md).

> [!NOTE]
> Nämä funktiot ovat osa esikatselutoimintoa, ja niiden käyttäytyminen on käytettävissä vain, kun **relaatio tiedot, asetus joukot ja muut CDS-ominaisuuden uudet ominaisuudet** ovat käytössä. Tämä on sovellus tason asetus, joka on oletus arvon mukaan käytössä uusille sovelluksille. Jos haluat löytää tämän ominaisuuden valitsimen, avaa **tiedosto-** valikko, valitse **sovellus asetukset**ja valitse sitten **lisä asetukset**. Palautteesi on meille erittäin arvokasta. Kerro meille mielipiteesi [PowerApps-yhteisön keskustelupalstoilla](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To).

## <a name="syntax"></a>Syntaksi

**Relate**( *Entity1RelatedTable*; *Entity2Record* )

* *Entity1RelatedTable* – pakollinen. Jos kyseessä on *Entity1*-tietue, *Entity2* -tietueiden taulukko, joka liittyy yksi-moneen-tai monta-moneen-suhteen kautta.
* *Entity2Record* – pakollinen. Suhteeseen lisättävä *Entity2* -tietue.

**Unrelate**( *Entity1RelatedTable*; *Entity2Record* )

* *Entity1RelatedTable* – pakollinen. Jos kyseessä on *Entity1*-tietue, *Entity2* -tietueiden taulukko, joka liittyy yksi-moneen-tai monta-moneen-suhteen kautta.
* *Entity2Record* – pakollinen. Suhteesta poistettava *Entity2* -tietue.

## <a name="examples"></a>Esimerkkejä

Harkitse **tuote** -entiteettiä, jolla on seuraavat suhteet, kuten näkyy [powerapps-portaalin entiteetin katselu ohjelmassa](../../common-data-service/create-edit-entities-portal.md):

| Suhteen näyttö nimi | Liittyvä entiteetti | Suhde tyyppi |
| --- | --- |
| Tuote varaus | Tekeminen | Yksi moneen |
| Tuote &harr; yhteys henkilö | Yhteystiedot | Monta moneen |

**Tuotteet** ja **vara ukset** liittyvät yhden moneen-suhteen kautta.  Jos haluat liittää **vara ukset** -entiteetin ensimmäisen tietueen **Products** -entiteetin ensimmäiseen tietueeseen:

`Relate( First( Products ).Reservations; First( Reservations ) )`

Näiden tietueiden välisen suhteen poistaminen:

`Unrelate( First( Products ).Reservations; First( Reservations ) )`

Emme luo tai poista tietueita tai kirjaa, mutta vain tietueiden välistä suhdetta muokattiin.

**Tuotteet** ja **yhteys tiedot** liittyvät monen moneen-suhteen kautta.  Jos haluat liittää **yhteys tiedot** -entiteetin ensimmäisen tietueen **Products** -entiteetin ensimmäiseen tietueeseen:

`Relate( First( Products ).Contacts; First( Contacts ) )`

Kuten monta moneen-yhteydet ovat symmetriset, olisimme voineet tehdä tämän myös vastakkaiseen suuntaan:

`Relate( First( Contacts ).Products; First( Products ) )`

Näiden tietueiden välisen suhteen poistaminen:

`Unrelate( First( Products ).Contacts; First( Contacts ) )`

tai

`Unrelate( First( Contacts ).Products; First( Products ) )`

Tämän jälkeen käydään läpi nämä toiminnot näillä entiteeteillä käyttämällä sovellusta, jonka **valikoima** -ja **yhdistelmä ruutu** -ohjaus objekteilla voit valita tietueita.

Nämä esimerkit riippuvat ympäristöösi asenne tuista malli tiedoista. [Luo kokeilu ympäristö, joka sisältää malli tiedot](../../model-driven-apps/overview-model-driven-samples.md#get-sample-apps) [, tai Lisää malli tietoja olemassa olevaan ympäristöön](../../model-driven-apps/overview-model-driven-samples.md#install-or-uninstall-sample-data).

### <a name="one-to-many"></a>Yksi moneen

#### <a name="relate-function"></a>**Relate** -funktiolla

Luot ensin yksinkertaisen sovelluksen, jotta voit tarkastella ja määrittää tuotteeseen liittyviä vara uksia.

1. Luo [Tablet-sovellus](../data-platform-create-app-scratch.md)tyhjästä.

1. Valitse **Näytä**-välilehdessä **Tietolähteet**.

1. Valitse **tiedot** -ruudussa **lisää tieto lähde** > **Common Data Service** > **tuotetta** > **Muodosta yhteys**.  

    Products-entiteetti on osa yllä ladattuja malli tietoja.

     ![Lisää Products-entiteetti tieto lähteeksi](media/function-relate-unrelate/products-connect.png)

1. Lisää tyhjä pystysuuntainen **[valikoima](../controls/control-gallery.md)** -ohjaus **objekti Lisää-väli lehdessä** .

1. Varmista, että juuri lisäämäsi ohjaus objekti on nimeltään **Gallery1**, ja Siirrä ja muuta sen kokoa niin, että se täyttää näytön vasemman puolen.

1. Valitse **Ominaisuudet** -väli lehdeltä **Gallery1** **Items** -ominaisuudeksi **tuotteet** ja sen **ulkoasu** **kuvaan ja otsikkoon**.

    ![Määritä Tuottetvalikoima](media/function-relate-unrelate/products-gallery.png)

1. Varmista **Gallery1**, että **nimi** -ohjaus objektin nimi on **Title1**ja aseta sen **teksti** -ominaisuudeksi **ThisItem.name**.

    ![Määritä nimi Gallery1](media/function-relate-unrelate/products-title.png)

1. Valitse näyttö, jos haluat välttää seuraavan kohteen lisäämisen **Gallery1**.  Lisää toinen tyhjä pystysuuntainen **valikoima** -ohjaus objekti ja varmista, että sen nimi on **gallery2**.

    **Gallery2** näyttää vara ukset siitä, mitä tuotetta käyttäjä valitsee **Gallery1**.

1. Siirrä **gallery2** ja muuta sen kokoa niin, että se täyttää näytön oikean yläneljänneksen.

1. valinnainen Lisää sininen **Selite** -ohjaus objekti yllä **gallery2**, kuten seuraavassa kuvassa näytetään.

1. Valitse kaava riviltä **gallery2** - **kohteen Items** -ominaisuudeksi **Gallery1. selected. Reservations**.

    ![Määritä gallery2 Items](media/function-relate-unrelate/reservations-gallery.png)

1. Valitse Ominaisuudet-ruudussa **gallery2**- **asetteluksi** **title**.

    ![Määritä gallery2-ulkoasu](media/function-relate-unrelate/reservations-gallery-right.png)

1. Lisää **gallery2**-ohjaus objektiin **[yhdistelmä ruutu](../controls/control-combo-box.md)** -ohjaus objekti, varmista, että sen nimi on **ComboBox1**, ja Siirrä ja muuta sen kokoa, jotta muut ohjaus objektin **gallery2**eivät estä.

1. Valitse **Ominaisuudet** -väli lehdessä **ComboBox1** **Items** -ominaisuudeksi **tuotteet**.

    ![Kohteiden ominaisuuksien asetus tuotteisiin](media/function-relate-unrelate/reservations-combo-right.png)

1. Vieritä alas **Ominaisuudet** -väli lehdessä ja valitse **ComboBox1** **Salli usean valinnan** ominaisuudeksi ei **käytössä**.

    ![Salli usean valinnan asetukseksi ei käytössä](media/function-relate-unrelate/reservations-singleselect-right.png)

1. Valitse kaava riviltä **ComboBox1** **Defaulttselecteditems** -ominaisuudeksi **Thisitem. ' Product Reservation '** .

    ![Valitse ReserveCombo-kohteelle DefaultSelectedItems](media/function-relate-unrelate/reservations-combo.png)

1. Määritä **gallery2** **NextArrow2** **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Relate( ComboBox1.Selected.Reservations; ThisItem )
    ```

    Kun käyttäjä valitsee tämän kuvakkeen, nykyinen varaus muuttuu tuotteeseen, jonka käyttäjä valitsi kohteessa **ComboBox1**.

    ![Määritä NextArrow2](media/function-relate-unrelate/reservations-relate.png)

1. Testaa sovellusta esikatselutilassa painamalla F5-näppäintä.

Tämän sovelluksen avulla käyttäjä voi siirtää vara uksen yhdestä tuotteesta toiseen. Jos haluat tehdä vara uksen yhdelle tuotteelle, käyttäjä voi valita eri tuotteen **ComboBox1** ja muuttaa tätä varausta valitsemalla **NextArrow2** .

![Osoittaminen Relate-funktiolla yksi moneen-sovelluksessa](media/function-relate-unrelate/reservations-reassign.gif)

#### <a name="unrelate-function"></a>**Unrelate** -funktiolla

Tässä vaiheessa voit siirtää suhteen tietueesta toiseen, mutta et voi poistaa suhdetta kokonaan. Voit käyttää **Unrelationate** -funktiolla katkaisemaan varaus tietueen mistä tahansa tuotteesta.

1. Valitse **Näytä**-välilehdessä **Tietolähteet**.

1. Valitse **tiedot** -ruudussa **lisää tieto lähde** > **Common Data Service** > **vara ukset** > **Connect**.

1. **Gallery2**, Määritä **onselect** -kaava kohteelle **NextArrow2** tähän kaavaan:

    ```powerapps-comma
    If( IsBlank( ComboBox1.Selected );
        Unrelate( Gallery1.Selected.Reservations; ThisItem );
        Relate( ComboBox1.Selected.Reservations; ThisItem )
    );;
    Refresh( Reservations )
    ```
    ![Määritä oikea-kuvake](media/function-relate-unrelate/reservations-relate-unrelate.png)

1. Kopioi **gallery2** leike pöydälle valitsemalla se ja painamalla CTRL-C.

1. Liitä **gallery2** -kaksoiskappale samaan näyttöön painamalla CTRL-V ja siirrä se sitten näytön oikeaan alakulmaan.

1. valinnainen Jos lisäsit otsikon **gallery2**yläpuolelle, toista kaksi edellistä vaihetta tälle otsikolle.

1. Varmista, että **gallery2** -kohteen kaksoiskappale on nimeltään **Gallery2_1**ja aseta sen **Items** -ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    Filter( Reservations; IsBlank( 'Product Reservation' ) )
    ```

    Näyttöön tulee delegointi varoitus, mutta tässä esimerkissä ei ole merkitystä pienen tieto määrän kanssa.

    ![Gallery2_1-kohteen Items-ominaisuuden asetus](media/function-relate-unrelate/reservations-lost.png)

Näiden muutosten avulla käyttäjät voivat tyhjentää **ComboBox1** -kohteen valinnan, jos kyseinen henkilö ei ole varannut tuotetta. Yhteys henkilöt, jotka eivät ole varanneet tuotetta, näkyvät **Gallery2_1** , joissa käyttäjät voivat antaa kunkin yhteys tiedon tuotteeseen.

   ![Osoita Relate-ja Unrelate-Funktiot yhdessä moneen-sovelluksessa](media/function-relate-unrelate/reservations-lostandfound.gif)

### <a name="many-to-many"></a>Monta moneen

#### <a name="create-a-many-to-many-relationship"></a>Monta-moneen-suhteen luominen

Malli tiedot eivät sisällä monta-moneen-suhdetta, mutta luot sellaisen tuote-entiteetin ja yhteys tiedot-entiteetin välille. Käyttäjät voivat liittää kunkin tuotteen useampaan kuin yhteen yhteys tietoon ja kuhunkin yhteys tietoon useampaan kuin yhteen tuotteeseen.

1. Valitse [tältä sivulta](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)vasemmasta siirtymis palkista **tiedot** ja valitse sitten **entiteetit**.

    ![Avaa entiteettien luettelo](media/function-relate-unrelate/entity-list.png)

1. Muuta entiteettisuodinta sisältämään kaikki entiteetit.

    Oletus arvon mukaan malli entiteetit eivät ole näkyvissä.

    ![Poista entiteettisuodatin](media/function-relate-unrelate/entity-all.png)

1. Vieritä alaspäin, avaa **tuote** -entiteetti ja valitse **yhteydet**.

    ![Tuote-entiteetin yhteydet-väli lehti](media/function-relate-unrelate/entity-relationships.png)

1. Valitse **Lisää suhde** > **monta-** moneen.

    ![Lisää monta moneen-suhde](media/function-relate-unrelate/entity-manytomany.png)

1. Valitse suhteen **yhteys** henkilö-entiteetti.

    ![Valitse yhteys henkilö-entiteetti](media/function-relate-unrelate/entity-contact.png)

1. Valitse **Done** > **Tallenna entiteetti**.

    ![Tuote-entiteetin suhde luettelo](media/function-relate-unrelate/entity-done.png)

#### <a name="relate-and-unrelate-contacts-with-one-or-more-products"></a>Suhteuttaa ja poistaa yhteys tietoja yhdestä tai useammasta tuotteesta

Luot toisen sovelluksen, joka muistuttaa aiemmin tässä aiheessa luomaasi sovellusta, mutta uusi sovellus tarjoaa monta-moneen-suhteen. Jokainen yhteys henkilö voi varata useita tuotteita vain yhden sijaan.

1. Luo tyhjään sovellukseen tableteille **Gallery1** , kun tämän ohje aiheen [ensimmäinen menettely](#one-to-many) on kuvattu.

1. Lisää toinen tyhjä pystysuuntainen **valikoima** -ohjaus objekti, varmista, että sen nimi on **gallery2**, ja siirrä se sitten näytön oikeaan yläkulmaan.

    Myöhemmin tässä ohje aiheessa lisäät **yhdistelmä ruutu** -ohjaus objektin kohdassa **gallery2**.

1. Valitse kaava riviltä **gallery2** **Items** -ominaisuudeksi **Gallery1. selected. Contacts**.

    ![Määritä ContactsGallery](media/function-relate-unrelate/contacts-gallery.png)

1. Valitse **Ominaisuudet** -väli lehdeltä **asetteluksi** **Image and title**.

    ![Määritä ContactsGallery](media/function-relate-unrelate/contacts-gallery-right.png)

1. Varmista **gallery2**, **että nimi-ohjaus objektin** nimi on **Title2**ja aseta sen **teksti** -ominaisuudeksi **thisitem. ' Full Name '** .

    Tähän ohjaus objektiin ei tule tekstiä, ennen kuin suoritat tämän toiminnon ja määrität yhteys tiedon tuotteeksi.

    ![Näytä yhteys henkilön nimi](media/function-relate-unrelate/contacts-title.png)

1. Poista **NextArrow2**, Lisää **peruutus** kuvake ja varmista, että sen nimi on **icon1**.

1. Määritä **peruutus** kuvakkeen **onselect** -ominaisuudeksi Tämä kaava: 

    ```powerapps-comma
    Unrelate( Gallery1.Selected.Contacts; ThisItem )
    ```

    ![Määritä peruutus kuvake](media/function-relate-unrelate/contacts-unrelate.png)

1. Valitse **Näytä**-välilehdessä **Tietolähteet**.

1. Valitse **tiedot** -ruudussa **lisää tieto lähde** > **Common Data Service** > **yhteys tiedot** > **Connect**.

1. Lisää **gallery2**-kohtaan **yhdistelmä ruutu** -ohjaus objekti, varmista, että sen nimi on **ComboBox1**, ja määritä sen **kohteet** -ominaisuudeksi **yhteys tiedot**.

    ![Yhdistelmä ruudun kohteet-ominaisuuden määrittäminen](media/function-relate-unrelate/contacts-combo.png)

1. Valitse **Ominaisuudet** -väli lehdestä **Salli usean valinnan** **asetukseksi ei käytössä**.

    ![Yhdistelmä ruudun rakenne-ominaisuuden määrittäminen](media/function-relate-unrelate/contacts-combo-right.png)

1. Lisää **Lisää** -kuvake ja määritä sen **onselect** -ominaisuudeksi Tämä kaava: 

    ```powerapps-comma
    Relate( Gallery1.Selected.Contacts; ComboBox1.Selected )
    ```

    ![Määritä lisää-kuvake](media/function-relate-unrelate/contacts-relate.png)

Tämän sovelluksen avulla käyttäjät voivat nyt vapaasti yhdistää ja poistaa yhteys tieto joukon kuhunkin tuotteeseen.

- Jos haluat lisätä yhteys tiedon tuotteeseen, valitse yhteys tieto näytön alareunassa olevasta yhdistelmä ruudusta ja valitse sitten **Lisää** -kuvake.
- Jos haluat poistaa yhteys tiedon tuotteesta, valitse kyseisen yhteys henkilön **peruutus** kuvake.

    Toisin kuin yksi moneen, monta moneen-suhde sallii käyttäjien liittää saman kontaktin useisiin tuotteisiin.

![Osoita Relate-ja Unrelate-Funktiot monta moneen-sovelluksessa](media/function-relate-unrelate/contacts-relate-unrelate.gif)

#### <a name="in-reverse-relate-and-unrelate-products-with-multiple-contacts"></a>Käänteisesti: Yhdistä ja poista toisiinsa liittyvät tuotteet useilla yhteys tiedoilla

Monta moneen-yhteydet ovat symmetriset. Voit laajentaa esimerkin, jos haluat lisätä tuotteita yhteys tietoon ja näyttää sitten kahden näytön välillä, miltä suhde näyttää kummassakin suunnassa.

1. Valitse **Onvisible** -ominaisuudeksi **Screen1** , jos haluat **päivittää (tuotteet)** .

    Kun päivität yksi-moneen-tai monta-moneen-suhteen, vain **Relate** -tai **unrelate** -kutsun ensimmäisen argumentin entiteetin tiedot päivitetään. Toinen on päivitettävä manuaalisesti, jos haluat kääntää tämän sovelluksen näyttöjen välillä.

    ![Asenna OnVisible-ominaisuus Päivitä-funktiolla](media/function-relate-unrelate/contacts-refresh.png)

1. Kaksinkertainen **Screen1**.

    Kaksoiskappaleen nimi on **Screen1_1** , ja se muodostaa perustan yhteys tietojen puolen suhteen katseluille.

    ![Näytön kaksoiskappale](media/function-relate-unrelate/contacts-duplicate.png)

1. Jos haluat luoda käänteisen näkymän, muuta näitä kaavoja **Screen1_1**-ohjaus objekteilla:

    - Screen1_1. OnVisible = `Refresh( Contacts )`
    - Gallery1_1. Items = `Contacts`
    - Title1_1. Text = `ThisItem.'Full Name'`
    - Label1_1. Text = `"Selected Contact Products"`
    - Gallery2_1. Items = `Gallery1_1.Selected.Products`
    - Title2_1. Text = `ThisItem.Name`
    - Icon1_1. OnSelect = `Unrelate( Gallery1_1.Selected.Products; ThisItem )`
    - ComboBox1_1. Items = `Products`
    - Icon2_1. OnSelect = `Relate( Gallery1_1.Selected.Products; ComboBox1_1.Selected )`

    Tulos näyttää hyvin samanlaiselta kuin edellinen näyttö, mutta se tulee **yhteys tietojen** puolelta.

    ![Näytä monta moneen-suhde alkaen yhteys henkilöistä](media/function-relate-unrelate/reverse-screen.png)

1. Lisää **nuolet ylös alaspäin** -kuvake ja määritä sen **onselect** -ominaisuudeksi **siirtyminen (Screen1, ei mitään)** .  Tee sama **Screen1** kaavalla **Navigoi (Screen1_1, None)** .

    ![Lisää siirtyminen näyttöjen välillä](media/function-relate-unrelate/reverse-navigate.png)

Tämän uuden näytön avulla käyttäjät voivat lisätä yhteys tiedon tuotteeseen ja siirtyä sitten yhteys tietojen näkymään ja nähdä liittyvän tuotteen. Yhteydet ovat symmetriset ja jaettu kahden näytön välillä.

![Näyttää monta moneen-suhteen kummallakin puolella](media/function-relate-unrelate/contacts-reverse.gif)

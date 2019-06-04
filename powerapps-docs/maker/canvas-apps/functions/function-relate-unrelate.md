---
title: Liittyvät ja Unrelate Funktiot | Microsoft Docs
description: Viitetiedot, mukaan lukien syntaksi ja Esimerkki Relate ja Unrelate-Funktiot powerappsissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/22/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4b2c6b9518e987ef17f2ff2b50987568c8a0b69f
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61527207"
ms.PowerAppsDecimalTransform: true
---
# <a name="relate-and-unrelate-functions-in-powerapps"></a>Liittyvät ja Unrelate-Funktiot powerappsissa

Liittyvät ja unrelate kautta yksi-moneen- tai monta-moneen-suhteen kahden entiteetin tietueet.

## <a name="description"></a>Kuvaus

**Relate** funktio yhdistää kaksi tietuetta yksi-moneen- tai monta-moneen-suhteen Common Data Service-kautta. **Unrelate** funktio kääntää prosessi ja poistaa linkin.

Yksi moneen suhteiden monta kohteella viiteavain kenttä, joka osoittaa yhden entiteetin tietueen. **Liittyvät** määrittää tämän kentän osoittamaan tietyn tietueen yhden entiteetin, kun **Unrelate** määrittää tämän kentän *tyhjä*. Jos kenttä on jo määritetty kun **Relate** on nimeltään, nykyisen linkin menetetään, koska uuden linkin. Voit myös määrittää tämän kentän avulla [ **Patch** ](function-patch.md) funktio tai **[muokkauslomake](../controls/control-form-detail.md)** ohjausobjektin; mitä tarvitset Käytä **yhdistäminen**  funktio.

Monta-moneen-suhteita järjestelmän, joka yhdistää tietueet ylläpitää piilotettu join-taulukoksi. Liity tässä taulukossa ei voi käyttää suoraan. se voidaan lukea vain yksi-moneen-projektion ja asetettu kautta **Relate** ja **Unrelate** funktioita. Kumpikaan liittyvä entiteetti on foreign key.

Ensimmäinen argumentti määrittämääsi entiteettiin tiedot päivitetään muutoksen, mutta toinen argumentti määrittämääsi entiteettiin tiedot eivät. Tietojen on oltava manuaalisesti päivittää kanssa **[Päivitä](function-refresh.md)** funktiota näyttämään toiminnon tuloksen.

Nämä funktiot koskaan luoda tai poistaa tietueen. He vain liittyvät tai unrelate kaksi tietuetta, jotka on jo olemassa.

Voit käyttää näitä funktioita vain [toimintakaavoissa](../working-with-formulas-in-depth.md).

> [!NOTE]
> Nämä funktiot ovat osa esikatseluominaisuudet ja niiden toiminta on käytettävissä vain, kun **relaatiotietoja asetusjoukkoja ja muihin uusiin ominaisuuksiin cds** on käytössä. Tämä on sovelluksen tason-asetus, joka on oletusarvoisesti uusille sovelluksille. Voit etsiä tämän ominaisuusvalitsimen avaamalla **tiedoston** valikosta **sovellusasetukset**, ja valitse sitten **lisäasetukset**. Palautteesi on meille erittäin arvokasta. Kerro meille mielipiteesi [PowerApps-yhteisön keskustelupalstoilla](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To).

## <a name="syntax"></a>Syntaksi

**Liittyvät**( *Entity1RelatedTable*; *Entity2Record* )

* *Entity1RelatedTable* – pakollinen. Tietueen *Entity1*, on *Entity2* liittyvät yksi-moneen- tai monta-moneen-suhteen kautta.
* *Entity2Record* – pakollinen. *Entity2* tietueen lisäämiseen suhteen.

**Unrelate**( *Entity1RelatedTable*; *Entity2Record* )

* *Entity1RelatedTable* – pakollinen. Tietueen *Entity1*, on *Entity2* liittyvät yksi-moneen- tai monta-moneen-suhteen kautta.
* *Entity2Record* – pakollinen. *Entity2* tietueen Poista suhde.

## <a name="examples"></a>Esimerkkejä

Harkitse **tuotteiden** entiteettiä seuraava suhteita osoitetulla tavalla [PowerApps-portaali entiteetin katseluohjelman](../../common-data-service/create-edit-entities-portal.md):

| Suhteen näyttönimi | Liittyvä entiteetti | Suhteen tyyppi |
| --- | --- |
| Tuotteen varaus | Varauksen | Yksi-moneen |
| Tuotteen &harr; yhteyttä | Yhteystiedot | Monta moneen |

**Tuotteiden** ja **varaukset** liittyvät yksi-moneen-suhde.  Yhdistetään ensimmäisen tietueen **varaukset** entiteetti, jolla ensimmäisen tietueen **tuotteiden** entiteetin:

`Relate( First( Products ).Reservations; First( Reservations ) )`

Jos haluat poistaa nämä tietueet suhdetta:

`Unrelate( First( Products ).Reservations; First( Reservations ) )`

Milloin ei ollut Luomme tai poista tai tietue, vain tietueen välisen suhteen on muokattu.

**Tuotteiden** ja **yhteystiedot** liittyvät monta-moneen-suhde.  Yhdistetään ensimmäisen tietueen **yhteystiedot** entiteetti, jolla ensimmäisen tietueen **tuotteiden** entiteetin:

`Relate( First( Products ).Contacts; First( Contacts ) )`

Kuin monta moneen suhteita symmetrisen, emme voi myös olet tehnyt tämän vastakkaiseen suuntaan:

`Relate( First( Contacts ).Products; First( Products ) )`

Jos haluat poistaa nämä tietueet suhdetta:

`Unrelate( First( Products ).Contacts; First( Contacts ) )`

tai:

`Unrelate( First( Contacts ).Products; First( Products ) )`

Läpikäyntiin, että seuraavat tarkalleen näitä entiteettejä avulla sovellus nämä toiminnot **valikoiman** ja **yhdistelmäruudun** ohjausobjektit valitsemalla liittyvät tietueet.

Näissä esimerkeissä riippuu asennetaan ympäristösi mallitiedot. Joko [luoda kokeiluympäristöön, mukaan lukien näytetiedot](../../model-driven-apps/overview-model-driven-samples.md#get-sample-apps) tai [mallitietoja lisääminen olemassa ympäristön](../../model-driven-apps/overview-model-driven-samples.md#install-or-uninstall-sample-data).

### <a name="one-to-many"></a>Yksi-moneen

#### <a name="relate-function"></a>**Liittyvät** funktio

Ensin luot yksinkertaisen sovelluksen, voit tarkastella ja määrittää varaukset, jotka liittyvät tuote uudelleen.

1. Luo [tyhjä tablettisovellus](../data-platform-create-app-scratch.md).

1. Valitse **Näytä**-välilehdessä **Tietolähteet**.

1. - **Tietojen** ruudussa **tietolähde** > **Common Data Service-**  > **tuotteiden**  >  **Yhteyden**.  

    Tuotteiden entiteetti on osa ladata yllä mallitiedot.

     ![Lisää tietolähde tuotteet-entiteettiin](media/function-relate-unrelate/products-connect.png)

1. Valitse **Lisää** -välilehden Lisää tyhjä vaakasuuntainen **[valikoiman](../controls/control-gallery.md)** ohjausobjektin.

1. Varmista, että ohjausobjekti, jonka juuri lisäsit nimeltä **Gallery1**, ja Siirrä ja muuta se täyttää näytön vasemmassa reunassa.

1. Käyttöön **ominaisuudet** välilehti, Määritä **Gallery1**käyttäjän **kohteet** -ominaisuuden arvoksi **tuotteiden** ja sen **asettelu** avulla **Kuva ja otsikko**.

    ![Määritä ProductsGallery](media/function-relate-unrelate/products-gallery.png)

1. - **Gallery1**, varmista, että **nimen** ohjausobjektin nimi on **Title1**, ja aseta sen **tekstin** ominaisuudeksi  **ThisItem.Name**.

    ![Määritä selitteen Gallery1](media/function-relate-unrelate/products-title.png)

1. Valitse näytön välttämiseksi seuraavan kohteen lisääminen **Gallery1**.  Lisää toinen tyhjä vaakasuuntainen **valikoiman** ohjausobjekti ja varmista, että se on nimetty **Gallery2**.

    **Gallery2** näyttää haluamasi tuotteen, jonka käyttäjä valitsee varaukset **Gallery1**.

1. Siirtäminen ja koon muuttaminen **Gallery2** täyttää näytön oikeassa-neljännes.

1. (valinnainen) Lisää sininen **nimen** ohjausobjektin yllä **Gallery2**, kuten seuraavassa kuvassa.

1. Määritä kaavarivillä **kohteet** ominaisuuden **Gallery2** - **Gallery1.Selected.Reservations**.

    ![Määritä Gallery2 kohteet](media/function-relate-unrelate/reservations-gallery.png)

1. Määritä ominaisuudet-ruudussa **Gallery2**käyttäjän **asettelu** - **otsikko**.

    ![Määritä Gallery2 asettelu](media/function-relate-unrelate/reservations-gallery-right.png)

1. - **Gallery2**, Lisää **[yhdistelmäruudun](../controls/control-combo-box.md)** ohjausobjekti, varmista, että se on nimetty **ComboBox1**, ja Siirrä ja muuta sen välttämiseksi, estä muiden ohjausobjektien **Gallery2**.

1. Käyttöön **ominaisuudet** välilehti, Määritä **ComboBox1**käyttäjän **kohteet** ominaisuudeksi **tuotteiden**.

    ![Items-ominaisuuden arvoksi tuotteet](media/function-relate-unrelate/reservations-combo-right.png)

1. Vieritä alaspäin **ominaisuudet** välilehti ja määritä **ComboBox1**käyttäjän **Monivalinnan salliminen** ominaisuudeksi **käytöstä**.

    ![Määritä Salli useita valintoja ei ole käytössä](media/function-relate-unrelate/reservations-singleselect-right.png)

1. Määritä kaavarivillä **ComboBox1**käyttäjän **DefaultSelectedItems** ominaisuudeksi **ThisItem. 'Tuotteen varauksen'** .

    ![Määritä DefaultSelectedItems ReserveCombo](media/function-relate-unrelate/reservations-combo.png)

1. - **Gallery2**, Määritä **NextArrow2**käyttäjän **OnSelect** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Relate( ComboBox1.Selected.Reservations; ThisItem )
    ```

    Kun käyttäjä valitsee tämän kuvakkeen, nykyinen varauksen muuttuu tuote, jonka käyttäjä valitsi **ComboBox1**.

    ![Määritä NextArrow2](media/function-relate-unrelate/reservations-relate.png)

1. Paina F5-näppäintä testaat sovellustasi esikatselutilassa.

Tämän sovelluksen avulla käyttäjä voi siirtää varauksen yhdessä tuotteessa toiseen. Varauksen yksi tuote, käyttäjä voi valita eri tuotteen **ComboBox1** ja valitse sitten **NextArrow2** muuttamiseksi kyseisen varaus.

![Osoittaa funktion Relate yksi-moneen-sovelluksessa](media/function-relate-unrelate/reservations-reassign.gif)

#### <a name="unrelate-function"></a>**Unrelate** funktio

Tässä vaiheessa voit siirtää suhteen tietueesta toiseen, mutta ei voi poistaa yhteyden kokonaan. Voit määrittää **Unrelate** funktiota varauksen tietueen katkaista tuotetta.

1. Valitse **Näytä**-välilehdessä **Tietolähteet**.

1. - **Tietojen** ruudussa **tietolähde** > **Common Data Service-**  > **varaukset**  >  **Yhteyden**.

1. - **Gallery2**, Määritä **OnSelect** kaavaa **NextArrow2** tämä kaava:

    ```powerapps-comma
    If( IsBlank( ComboBox1.Selected );
        Unrelate( Gallery1.Selected.Reservations; ThisItem );
        Relate( ComboBox1.Selected.Reservations; ThisItem )
    );;
    Refresh( Reservations )
    ```
    ![Määritä oikea kuvake](media/function-relate-unrelate/reservations-relate-unrelate.png)

1. Kopioi **Gallery2** valitsemalla sen ja painamalla Ctrl-C. Leikepöydälle

1. Liitä kaksoiskappaleen **Gallery2** sama näytön painamalla Ctrl-V ja siirrä se oikeaan neljännes näytön.

1. (valinnainen) Jos olet lisännyt yllä selitteen **Gallery2**, toista edelliset kaksi vaihetta merkin.

1. Varmista, kaksoiskappale **Gallery2** nimeltä **Gallery2_1**, ja aseta sen **kohteet** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Filter( Reservations; IsBlank( 'Product Reservation' ) )
    ```

    Delegointi varoituksen, mutta luontimenetelmällä ei tässä esimerkissä pieni tietomäärän kanssa.

    ![Gallery2_1 Items-ominaisuuden asettaminen](media/function-relate-unrelate/reservations-lost.png)

Nämä muutokset käyttäjät poistamalla valinnan **ComboBox1** yhteyshenkilön, jos hän ei ole varattu tuote. Yhteyshenkilöt, joilla ei ole vielä varattu tuotteen näkyvät **Gallery2_1** tuotetta, jossa käyttäjät voivat määrittää jokaisen yhteystiedon.

   ![Esitellä Relate ja Unrelate Funktiot yksi-moneen-sovelluksessa](media/function-relate-unrelate/reservations-lostandfound.gif)

### <a name="many-to-many"></a>Monta moneen

#### <a name="create-a-many-to-many-relationship"></a>Luo monta-moneen-suhde

Mallitietojen ei sisällä monta-moneen-suhde, mutta luot tuotteet-entiteettiin ja yhteystiedot-entiteetin välillä. Käyttäjille voidaan liittää kunkin tuotteen useita yhteystietoja ja jokaisen yhteystiedon useampi kuin yksi tuotteeseen.

1. - [Tämän sivun](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), valitse **tietojen** vasemmassa siirtymisruudussa ja sitten Valitse **entiteetit**.

    ![Avaa entiteettien luettelo](media/function-relate-unrelate/entity-list.png)

1. Sisällytä kaikki entiteetit suodattimeen entiteetin.

    Oletusarvon mukaan malli-entiteetit eivät näy.

    ![Poista entiteetti suodatin](media/function-relate-unrelate/entity-all.png)

1. Vieritä alaspäin, Avaa **tuotteen** entiteetin ja valitse **suhteita**.

    ![Tuote-entiteetin suhteet-välilehti](media/function-relate-unrelate/entity-relationships.png)

1. Valitse **Lisää suhde** > **monta-moneen**.

    ![Lisää monta-moneen-suhde](media/function-relate-unrelate/entity-manytomany.png)

1. Valitse **yhteyttä** entiteetin suhteen.

    ![Valitse yhteyshenkilö-entiteetin](media/function-relate-unrelate/entity-contact.png)

1. Valitse **valmis** > **Tallenna entiteetti**.

    ![Suhteet tuotteiden entiteetin luettelo](media/function-relate-unrelate/entity-done.png)

#### <a name="relate-and-unrelate-contacts-with-one-or-more-products"></a>Liittyvät ja unrelate yhteystietoja ja vähintään yksi tuote

Luot toiseen sovellukseen, joka muistuttaa loit aiemmin tässä ohjeaiheessa, mutta uusi sovellus tarjouksen monta-moneen-suhde. Jokaisen yhteystiedon voi varata useita tuotteita vain yksi sijaan.

1. Luo tyhjä sovellus tabletille, **Gallery1** kuin [ensimmäisessä toimintosarjassa](#one-to-many) Tässä aiheessa kuvataan.

1. Lisää toinen tyhjä, pysty **valikoiman** ohjausobjekti, varmista, että se on nimetty **Gallery2**, ja siirrä se sitten näytön oikeassa yläkulmassa.

    Myöhemmin tässä aiheessa lisäämme **yhdistelmäruudun** ohjausobjekti kohdassa **Gallery2**.

1. Määritä kaavarivillä **Gallery2**käyttäjän **kohteet** ominaisuudeksi **Gallery1.Selected.Contacts**.

    ![Määritä ContactsGallery](media/function-relate-unrelate/contacts-gallery.png)

1. Valitse **ominaisuudet** välilehti, Määritä **asettelu** - **kuva ja otsikko**.

    ![Määritä ContactsGallery](media/function-relate-unrelate/contacts-gallery-right.png)

1. - **Gallery2**, varmista, että **nimen** ohjausobjektin nimi on **Otsikko2**, ja aseta sen **tekstin** ominaisuudeksi  **ThisItem. 'Koko nimi ”** .

    Ei näy tekstiä, jotta ohjausobjektin ennen kuin tämän vaiheen ja määrittää yhteystiedon tuote.

    ![Näytä yhteyshenkilön nimi](media/function-relate-unrelate/contacts-title.png)

1. Poistaa **NextArrow2**, Lisää **Peruuta** kuvake, ja varmista, että se on nimetty **icon1**.

1. Määritä **Peruuta** kuvakkeen **OnSelect** -ominaisuuden arvoksi tämä kaava: 

    ```powerapps-comma
    Unrelate( Gallery1.Selected.Contacts; ThisItem )
    ```

    ![Määritä Peruuta-kuvaketta](media/function-relate-unrelate/contacts-unrelate.png)

1. Valitse **Näytä**-välilehdessä **Tietolähteet**.

1. - **Tietojen** ruudussa **tietolähde** > **Common Data Service-**  > **yhteystiedot**  >  **Yhteyden**.

1. Kohdassa **Gallery2**, Lisää **yhdistelmäruudun** ohjausobjekti, varmista, että se on nimetty **ComboBox1**, ja aseta sen **kohteet** ominaisuudeksi**Yhteystiedot**.

    ![Määritä combo box Items-ominaisuuden](media/function-relate-unrelate/contacts-combo.png)

1. Valitse **ominaisuudet** välilehti, Määritä **Monivalinnan salliminen** - **käytöstä**.

    ![Yhdistelmäruudun asettelu-ominaisuuden määrittäminen](media/function-relate-unrelate/contacts-combo-right.png)

1. Lisää **Lisää** kuvaketta ja aseta sen **OnSelect** -ominaisuuden arvoksi tämä kaava: 

    ```powerapps-comma
    Relate( Gallery1.Selected.Contacts; ComboBox1.Selected )
    ```

    ![Määritä Lisää kuvake](media/function-relate-unrelate/contacts-relate.png)

Tämän sovelluksen avulla käyttäjät voivat nyt vapaasti liittyvät ja unrelate yhteystietojen kunkin tuotteen.

- Lisäämään yhteystiedon tuotteen valitsemalla henkilön näytön alareunassa yhdistelmäruutu ja valitse sitten **Lisää** kuvake.
- Jos haluat poistaa yhteystiedon tuotteen, valitse **Peruuta** sen kuvake.

    Toisin kuin yksi-moneen-monta-moneen-suhde käyttäjät voivat liittää useita tuotteita samaa yhteyttä.

![Esitellä Relate ja Unrelate Funktiot monta-moneen-sovelluksessa](media/function-relate-unrelate/contacts-relate-unrelate.gif)

#### <a name="in-reverse-relate-and-unrelate-products-with-multiple-contacts"></a>Käänteisessä: liittyvät ja unrelate tuotteita useita yhteystietoja

Monta-moneen-suhteet ovat symmetrisen. Voit laajentaa katselutilaan näyttämään, miten suhteen näkyy suuntaan kaksi näyttöä ja lisätä tuotteita yhteystiedon esimerkki.

1. Määritä **OnVisible** ominaisuuden **Screen1** - **päivitys (tuotteet)** .

    Kun päivität yksi-moneen- tai monta-moneen-suhde, vain ensimmäinen argumentti entiteetin tiedot **Relate** tai **Unrelate** kutsun päivitetään. Toinen on päivitettävä manuaalisesti, jos haluat kääntää tämän sovelluksen näyttöjen välillä.

    ![Määritä OnVisible-ominaisuuden arvoksi päivitystoiminto](media/function-relate-unrelate/contacts-refresh.png)

1. Monista **Screen1**.

    Kaksoiskappale nimetään **Screen1_1** ja katsomalla suhteet laidasta yhteyshenkilöt perusta.

    ![Näytön kaksoiskappale](media/function-relate-unrelate/contacts-duplicate.png)

1. Käänteinen näkymän luomiseksi muuttaa näistä kaavoista ohjausobjekteilla **Screen1_1**:

    - Screen1_1.OnVisible = `Refresh( Contacts )`
    - Gallery1_1.items = `Contacts`
    - Title1_1.Text = `ThisItem.'Full Name'`
    - Label1_1.Text = `"Selected Contact Products"`
    - Gallery2_1.items = `Gallery1_1.Selected.Products`
    - Title2_1.Text = `ThisItem.Name`
    - Icon1_1.OnSelect = `Unrelate( Gallery1_1.Selected.Products; ThisItem )`
    - ComboBox1_1.Items = `Products`
    - Icon2_1.OnSelect = `Relate( Gallery1_1.Selected.Products; ComboBox1_1.Selected )`

    Tulos näyttää samalta kuin hyvin edelliseen näyttöön, mutta se tulee suhteen **yhteystiedot** puolella.

    ![Näytä yhteystiedot alkaen monta-moneen-suhde](media/function-relate-unrelate/reverse-screen.png)

1. Lisää **nuolet ylös ja alas** kuvaketta ja aseta sen **OnSelect** ominaisuudeksi **Navigate (Screen1, ei mitään)** .  Tehdä saman asian **Screen1** kaavalla **Navigate (Screen1_1, ei mitään)** .

    ![Lisää näyttöjen välillä siirtyminen](media/function-relate-unrelate/reverse-navigate.png)

Tämän uuden näytön, jossa käyttäjät voivat yhteystietojen lisääminen tuotteen ja sitten Käännä näkymään, yhteystiedot ja näet liittyvät tuotteen. Suhteet ovat symmetrisen ja jaettu kaksi näyttöjen välillä.

![Esitetään monelle-suhteen puolella](media/function-relate-unrelate/contacts-reverse.gif)

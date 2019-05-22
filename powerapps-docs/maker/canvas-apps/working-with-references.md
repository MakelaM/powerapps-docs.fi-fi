---
title: Tutustu tietueen viittaukset ja polymorfinen hakuja | Microsoft Docs
description: Tietueen viittaukset ja polymorfinen hakujen pohjaan perustuvat sovellukset
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/17/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 80755667a9c7c36eb47999f7f8b2f939eb032c69
ms.sourcegitcommit: 93096dfa1aadba77159db1e5922f3d5528eecb7a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/21/2019
ms.locfileid: "65986444"
---
# <a name="understand-record-references-and-polymorphic-lookups-in-canvas-apps"></a>Tutustu tietueen viittaukset ja polymorfinen hakujen pohjaan perustuvat sovellukset

Kun kirjoitit tutkimus paperin oppilaitoksen antamasi todennäköisesti loppuun suositukset luettelo. Hakuun ei sisällytetty kopiointi todellinen taustan materiaalia, voit käyttää sen sijaan Verkkolinkki, kirjan nimi ja tekijä tai muita tietoja, mutta niin, että joku voi jäljittää alkuperäiseen lähteeseen. Yhdistettyjä erilaisia tietolähteitä yksittäisen luettelon sanomalehti artikkelit äänitallenteita, jokainen omia tiedot-oikea lainaus vieressä. Esimerkiksi Wikipedia-artikkelit sisältävät usein [viittaukset pitkä luettelo](https://en.wikipedia.org/wiki/Microsoft#References).

Pohjaan perustuvat sovellukset voit usein käyttää ladattavien tietolähteistä tietueiden kopioita. Voit käyttää [ **LookUp** ](functions/function-filter-lookup.md) ja [ **suodatin** ](functions/function-filter-lookup.md) Funktiot ja [ **valikoiman** ](controls/control-gallery.md) ohjausobjektin **valittu** ominaisuus, jonka haluat tietyn tietueen tunnistamiseen. Kaikki tietueet **suodatin** tai **valittu** on saman tyyppinen entiteetti, joten voit käyttää kentät yksinkertainen. *Kentän* merkintätapaa. Nämä kopiot sisältävät usein tietoja, jotta voit käyttää [ **Patch** ](functions/function-patch.md) funktiota alkuperäisen tietolähteen päivittämiseksi.

Pohjaan perustuvat sovellukset tukevat myös *tietueen viittaukset*. Paljon tutkimus paperin viittausta, kuten tietueen viittaus viittaa tietueen ilman täydellisen kopion. Viittaukset voi viitata kaikki entiteetin tietueen. Myös tutkimus paperin viittaukset, kuten voit yhdistellä tietueita eri entiteettejä vain yksi sarake.

Useita toimintoja tietueen viittaukset ovat samanlaisia kuin tietueiden käsittelemisestä. Voit verrata tietueen viittaukset toisiinsa ja koko tietueita. Voit määrittää tietueen viittaus-arvon **Patch** toimi samalla tavalla kuin haun koko tietueen kanssa.

On tärkeää käyttö yksi ero: viittaus tietueen kenttiä ei voi käyttää suoraan ilman ensimmäistä muodostamisen, mikä entiteettiin se viittaa. Tämä johtuu siitä pohjaan perustuvat sovellukset edellyttävät, että kaikki tunnetuksi kun kirjoitat kaavoja. Koska et ole varma tietueen viittauksen tyyppi, kunnes sovellus on käynnissä, et voi käyttää yksinkertaista. *Kentän* suoraan merkintätapaa. Sinun on määritettävä käyttäen entiteettityyppi dynaamisesti [ **IsType** ](functions/function-astype-istype.md) funktio ja käytä. *Kentän* notation-tuloksen [ **AsType** ](functions/function-astype-istype.md) funktio.

*Entiteettityyppi* viittaa jokainen tietue entiteetissä rakenteeseen. Jokainen entiteetti sisältää yksilöivä kentät, joissa on eri nimiä ja tietotyyppejä. Entiteetin tietueiden perii kyseisen rakenne. kaksi tietuetta on sama kohteen tyyppi, jos ne ovat peräisin samaan entiteettiin.

## <a name="polymorphic-lookups"></a>Polymorfinen haut

Common Data Service tukee kenttien väliset yhteydet. Jokaiselle tietueelle **tilit** kohteella **ensisijaisen yhteyshenkilön** hakukentän tietueeseen **yhteystiedot** entiteetin. Hakukentän voi viitata vain tietueen **yhteystiedot** ja ei voi viitata tietueen, esimerkiksi **Teams** entiteetin. Viimeisin tiedot on tärkeä, koska aina tiedät, mitä kenttiä on käytettävissä hakua varten.

Common Data Service tukee myös polymorfinen haut, joka voi viitata tietueen entiteetistä mitään joukon. Esimerkiksi **omistaja** voi viitata mihin tietueen **käyttäjät** entiteetin tai **Teams** entiteetin. Eri tietuetta samaan hakukenttään voi viitata eri entiteettien tietueiden. Tässä tapauksessa voit aina tiedä, mitkä kentät ovat käytettävissä.

Pohjaan tietueen viittaukset suunniteltiin käsitteleminen polymorfinen hakuja tässä Common Data Service. Voit myös käyttää tietueen viittaukset kontekstissa, joka on kaksi käsitteitä suoratoistoon ulkopuolella.

Seuraavassa osiossa, voit alkaa tutkia näistä käsitteistä käsitteleminen **omistaja** haku.

## <a name="show-the-fields-of-a-record-owner"></a>Näytä tietueen omistajan kentät

Common Data Service-Jokainen entiteetti sisältää **omistaja** kenttä. Tämä kenttä ei voi poistaa, ei voi lisätä toisen ja se edellyttää aina arvo.

Näytä- **tilin** entiteetin:

1. Avaa [PowerApps-sivusto](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
1. Valitse vasemmassa siirtymispalkissa **tietojen** > **entiteetit**.
1. Valitse luettelossa, **tilin**.
1. Oikeassa yläkulmassa, Avaa suodatinluettelon (joka on määritetty **oletusarvon** oletusarvon mukaan), ja valitse sitten **kaikki**.
1. Vieritä alaspäin, kunnes **omistaja** kenttä tulee näkyviin.

 > [!div class="mx-imgBorder"]
 > ![Omistaja-kentästä tili-entiteetistä](media/working-with-references/owner-field.png)

Tämän hakukentän voi viitata tietueen joko **Teams** entiteetin tai **käyttäjät** entiteetin. Nämä entiteetit ei jokaisessa tietueessa on oikeus voi **omistaja**; Tarkista tuettujen rooleja, jos kohtaat ongelman.

Tässä kaaviossa näkyy yksinkertainen valikoiman **tilit**, jossa **tilit** entiteetti on lisätty sovellukseen tietolähde:

> [!div class="mx-imgBorder"]
> ![Tilit näkyvät valikoima-ohjausobjekti](media/working-with-references/accounts-gallery.png)

> [!IMPORTANT]
> Tässä ohjeaiheessa koko grafiikka Joidenkin nimien ja muiden arvojen näyttäminen, jotka eivät ole osa mallitietoja, joka toimitetaan Common Data Service. Ohjeita tarkasti esitellään määrittää tietyn tuloksen ohjausobjekteja, mutta kokemuksesi vaihtelee organisaatiosi tiedot.

Näyttää kunkin tilin omistajan valikoimassa, voit ehkä käyttää kaavaa tietoja **ThisItem.Owner.Name**. Kuitenkin nimikentän **ryhmän** entiteetti on **joukkueen nimi**, ja nimikentän **käyttäjän** entiteetti on **KokoNimi**. Sovellus ei voi, haku käyttämäsi käytät ennen kuin voit suorittaa sovelluksen ja tietueiden voi vaihdella **tilit** entiteetin.

Sinun on kaava, joka voi sopeutua varianssi johtuu. Sinun on lisättävä tietolähteitä, entiteetin kirjoittaa, myös **omistaja** voitu (Tässä tapauksessa **käyttäjät** ja **Teams**). Näiden kolmen tietolähteiden lisääminen sovellukseen:

> [!div class="mx-imgBorder"]
> ![Tilit, ryhmiä ja käyttäjiä tietoruudun entiteetit](media/working-with-references/accounts-datasources.png)

Nämä tiedot tietolähteiden sijoittaa, tämä kaava avulla voit näyttää käyttäjän tai ryhmän nimi:

```powerapps-dot
If( IsType( ThisItem.Owner, [@Teams] ),
    "Team: " & AsType( ThisItem.Owner, [@Teams] ).'Team Name',
    "User: " & AsType( ThisItem.Owner, [@Users] ).'Full Name' )
```

> [!div class="mx-imgBorder"]
> ![Omistaja-kenttä näkyy valikoima-ohjausobjektissa näkyy tilit](media/working-with-references/accounts-displayowner.png)

Tässä kaavassa **IsType** funktio Testaa **omistaja** kentän vastaan **Teams** entiteetin. Jos se on kyseisen entiteetin tyyppiä **AsType** funktion valaistustiedot se **ryhmän** tietueen. Tässä vaiheessa voit käyttää kaikki kentät **Teams** entiteetin, mukaan lukien **joukkueen nimi**, käyttämällä *. Kentän* merkintätapaa. Jos **IsType** , joka määrittää **omistaja** ei ole tietuetta **Teams** entiteetin kyseisen kentän arvon täytyy olla tietueen **käyttäjät** entiteetin koska **omistaja** kenttä on pakollinen (ei voi olla *tyhjä*).

Käytät [yleinen selvitysoperaattoria](functions/operators.md#disambiguation-operator) - **[@Teams]** ja **[@Users]** sen varmistamiseksi, että käytät Yleinen kohteen tyyppi. Et tarvitse sitä tässä tapauksessa, mutta se on hyvä hyvä lomakkeeseen. Valikoiman tietuealueen ristiriidassa usein yksi-moneen-suhteita, ja tämä käytäntö estää kyseistä vaikeutua.

Käyttää viittauksen tietueen kenttiä, sinun on ensin käytettävä **AsType** funktio muuntaa sen tietyn entiteettityyppi. Et voi käyttää suoraan kentät **omistaja** kenttää, koska järjestelmä ei tiedä, mitä kohteen tyyppi, jota haluat käyttää.

**AsType** funktio palauttaa virheen, jos **omistaja** kenttä ei vastaa vaadittua-kohteen tyyppi, jotta voit käyttää **IfError** funktion yksinkertaista kaava. Ota ensin kokeellinen ominaisuus käyttöön **kaavatason virheiden hallinta**:

> [!div class="mx-imgBorder"]
> ![Kokeellinen Vaihda käyttöön kaavatason virheiden hallinta](media/working-with-references/accounts-iferror.png)

Tällä tietojoukolla korvataan Edellinen kaava:

```powerapps-dot
IfError(
    "Team: " & AsType( ThisItem.Owner, [@Teams] ).'Team Name',
    "User: " & AsType( ThisItem.Owner, [@Users] ).'Full Name' )
```

## <a name="filter-based-on-an-owner"></a>Suodattaa omistajan mukaan

Onnittelut – olet suorittanut vaikeimmista käsitteleminen tietueen viittaus osaan. Käytä muissa tapauksissa on suoraviivaisempaa, koska ne eivät käyttää tietueen kentät. Palvelupyynnön in-kohdan kestää suodatusta, joka tutustut tässä osassa.

Lisää **yhdistelmäruudun** valikoiman yläpuolelta ohjausobjekti ja määritä uuden ohjausobjektin nämä ominaisuudet:

- **Kohteet**: `Users`
- **SelectMultiple**: `false`

> [!div class="mx-imgBorder"]
> ![Lisätty yhdistelmäruutu ohjausobjekti yllä valikoiman kohteet-ominaisuuden arvoksi käyttäjät](media/working-with-references/filter-insert-combobox.png)

Voit suodattaa valikoiman tämä yhdistelmäruutu valinnut tietyn käyttäjän, Määritä valikoiman **kohteet** -ominaisuuden arvoksi tämä kaava:

```powerapps-dot
Filter( Accounts, Owner = ComboBox1.Selected )
```

> [!div class="mx-imgBorder"]
> ![Suodatettu valikoiman yhdistelmäruutu ohjausobjektin arvon perusteella](media/working-with-references/filter-accounts.png)

> [!IMPORTANT]
> Tämän aiheen ohjeita ovat oikein, jos noudatat tarkalleen. Kuitenkin mikä tahansa kaava, joka viittaa ohjausobjektiin sen nimen mukaan epäonnistuu, jos ohjausobjekti on eri nimi. Jos poistat ja Lisää ohjausobjekti samaa tyyppiä, niiden ohjausobjektin nimen lopussa muuttuu. Mikä tahansa kaava, joka näyttää virheen Varmista, että se sisältää kaikki ohjausobjektit oikeat nimet.

Sinun ei tarvitse käyttää **IsType** tai **AsType** koska vertailet tietueen viittaukset tietueen viittaukset tai koko tietueita. Sovelluksen entiteettityyppi on määritetty **ComboBox1.Selected** koska se on johdettu **käyttäjät** entiteetin. Tilit, joiden omistaja on tiimin ei vastaa suodatuskriteeriä.

Voit saada hieman monimutkaisempi tukemalla suodatus käyttäjän tai ryhmän.

1. Vapauta levytilaa näytön yläreunan lähellä valikoiman koon muuttaminen ja siirtäminen yhdistelmäruudun, Lisää [ **Radio** ohjausobjektin](controls/control-radio.md) , valikoiman yläpuolelta ja määritä sitten uuden ohjausobjektin nämä ominaisuudet:

    - **Kohteet**: `[ "All", "Users", "Teams" ]`
    - **Asettelu**: `Layout.Horizontal`

1. Varten **yhdistelmäruudun** ohjausobjekti, Määritä tämän ominaisuuden (Jos yhdistelmäruudun katoaa, valitse **käyttäjät** radio ohjausobjektin):

    - **Näkyvissä**: `Radio1.Selected.Value = "Users"`

1. Kopioi ja liitä **yhdistelmäruudun** ohjausobjekti, siirtää kopion suoraan alkuperäisen ja määritä sitten kopion nämä ominaisuudet:

    - **Kohteet**: `Teams`
    - **Näkyvissä**: `Radio1.Selected.Value = "Teams"`

    Sovellus näkyy vain yksi yhdistelmäruudun kerrallaan valintanappeja tilan mukaan. Koska ne ovat toisiinsa yläpuolella, ne näkyvät voi ohjausobjekti, joka muuttaa sen sisällön.

1. Lopuksi **kohteet** -ominaisuuden **valikoiman** ominaisuudeksi tämä kaava:

    ```powerapps-dot
    Filter( Accounts,
        Radio1.Selected.Value = "All"
        Or (Radio1.Selected.Value = "Users" And Owner = ComboBox1.Selected)
        Or (Radio1.Selected.Value = "Teams" And Owner = ComboBox1_1.Selected)
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![suodatettu valikoima näyttää kaikki tietueet tai tietyn käyttäjän tai ryhmän](media/working-with-references/filter-combobox.png)

Nämä muutokset voit näyttää kaikki tietueet tai suodattaa niitä käyttäjän tai ryhmän perusteella:

> [!div class="mx-imgBorder"]
> ![animaatio näyttää eri suodatetun tuloksen perusteella valintanappi ja yhdistelmäruutu ruudut](media/working-with-references/filter-allthree.gif)

Kaava on täysin delegoitavat. Osa, joka on verrattaessa valintanapin arvoja on vakio kaikissa tietueissa ja arvioidaan, ennen kuin suodatin loput lähetetään Common Data Service.

Jos haluat suodattaa omistajan tyyppi, voit käyttää **IsType** funktiota, mutta käyttäjän ei vielä ole delegoitavissa.

> [!div class="mx-imgBorder"]
> ![Suodattaa omistajatyypin mukaan käyttämällä IsType](media/working-with-references/filter-bytype.png)

## <a name="update-the-owner-by-using-patch"></a>Päivittää omistaja käyttämällä korjaustiedosto

Voit päivittää **omistaja** samalla tavalla kuin muita lookup kenttää. Määrittää ensimmäisen tiimille valittuna tilin omistaja:

```powerapps-dot
Patch( Accounts, Gallery1.Selected, { Owner: First( Teams ) } )
```

Tämä lähestymistapa ei erota hakusarakkeen Normaali koska sovelluksen tyyppi on määritetty **ensimmäisen (Teams)**. Jos haluat ensimmäinen käyttäjä sen sijaan, korvata kyseisen osan kanssa **ensimmäisen (käyttäjät)**. **Patch** funktio tietää, **omistaja** kahden entiteetin tällaisten voidaan määrittää kentän.

Lisää tämän ominaisuuden sovellukseen:

1. - **Puu näkymän** ruudussa **Radio** ohjausobjektin ja kahden **yhdistelmäruudun** ohjausobjektit samaan aikaan.

1. Valitse kolme pistettä-valikko **kopioi nämä kohteet**.

    > [!div class="mx-imgBorder"]
    > ![Kopio puunäkymässä useita ohjausobjekteja](media/working-with-references/patch-copy.png)

1. Valitse sama valikosta **Liitä**.

    > [!div class="mx-imgBorder"]
    > ![Liitä puunäkymässä useita ohjausobjekteja](media/working-with-references/patch-paste.png)

1. Siirrä kopioitujen ohjausobjektien oikealle valikoiman.

    > [!div class="mx-imgBorder"]
    > ![Siirtää oikealle valikoiman kopioitujen ohjausobjektien](media/working-with-references/patch-position.png)

1. Valitse kopioitu **Radio** ohjausobjekti ja muuta sitten nämä ominaisuudet:

    - Kohteet: `[ "Users", "Teams" ]`
    - Oletus: `If( IsType( Gallery1.Selected.Owner, Users ), "Users", "Teams" )`

    > [!div class="mx-imgBorder"]
    > ![Poistaa kaikki valinta valintanappi](media/working-with-references/patch-noall.png) 

1. - **Radio** , ohjausobjektin **käyttäjät** niin, että **yhdistelmäruudun** ohjausobjekti, joka on luettelo käyttäjistä, on näkyvissä.

1. Valitse näkyvissä **yhdistelmäruudun** ohjausobjekti ja määritä sitten **DefaultSelectedItems** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    If( IsType( Gallery1.Selected.Owner, Users ),
        AsType( Gallery1.Selected.Owner, Users ),
        Blank()
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Default-ominaisuus määrittää käyttäjät-yhdistelmäruutu](media/working-with-references/patch-default-users.png)

1. - **Radio** , ohjausobjektin **Teams** niin, että **yhdistelmäruudun** ohjausobjekti, joka näyttää ryhmien luettelon on näkyvissä.

1. Valitse **Radio** ottamiseksi pois nyt-näkymätön valinta valvonta **yhdistelmäruudun** ohjausobjektin, jolla käyttäjät.

1. Valitse näkyvissä **yhdistelmäruudun** tiimeille ohjausobjekti ja määritä sitten sen **DefaultSelectedItems** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    If( IsType( Gallery1.Selected.Owner, Teams ),
        AsType( Gallery1.Selected.Owner, Teams ),
        Blank()
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Default-ominaisuus määrittää Teams-yhdistelmäruutu](media/working-with-references/patch-default-teams.png)

1. Lisää **painike** ohjausobjekti, siirrä se **yhdistelmäruudun** ohjausobjekti ja määritä sitten painikkeen **tekstin** ominaisuudeksi `"Patch Owner"`.

1. Määritä **OnSelect** ominaisuuden painikkeen tämä kaava:

    ```powerapps-dot
    Patch( Accounts, Gallery1.Selected,
        { Owner: If( Radio1_1.Selected.Value = "Users",
                ComboBox1_2.Selected,
                ComboBox1_3.Selected ) } )
    ```

    > [!div class="mx-imgBorder"]
    > ![Kaava määrittää painike-ohjausobjekti](media/working-with-references/patch-button.png)

Kopioitu **Radio** ja **yhdistelmäruudun** ohjausobjektit sisältävät valittuna tilin omistajan valikoimassa. Samoja ohjausobjekteja voit määrittää tilin omistajan ryhmän tai käyttäjän valitsemalla painiketta:

> [!div class="mx-imgBorder"]
> ![Animaatio näytetään patch käyttäjän tai ryhmän omistajan](media/working-with-references/patch-allthree.gif)

## <a name="show-the-owner-by-using-a-form"></a>Näytä omistajan mukaan lomakkeen avulla

Voit näyttää **omistaja** kentän lisäämällä mukautettu kortti lomakkeen sisällä. Tätä kirjoitettaessa kenttä, jonka lomakkeen ohjausobjektin arvoa ei voi muuttaa.

1. Lisää **muokkauslomake** ohjausobjekti, kokoa ja siirrä se oikeaan yläkulmaan.

1. Käyttöön **ominaisuudet** välilehti lähellä näytön, Avaa oikealla puolella **tietolähteen** luettelo ja valitse sitten **tilit**.

    > [!div class="mx-imgBorder"]
    > ![Lomake-ohjausobjekti näyttää lisäkenttiä tyhjillä arvoilla](media/working-with-references/form-insert.png)  

1. Määritä lomakkeen **kohteen** ominaisuudeksi `Gallery1.Selected`.

    > [!div class="mx-imgBorder"]
    > ![Entiteettilomakkeen ohjausobjektin lisäkenttiä, täytetty valitusta kohteesta valikoimassa näytetään](media/working-with-references/form-item.png)

1. Valitse **ominaisuudet** välilehti lähellä näytön, valitse oikealla puolella **Muokkaa kenttiä**.

1. Tässä **kentät** ruudussa, valitse kolme pistettä ja valitse sitten **Lisää mukautettu kortti**.

    > [!div class="mx-imgBorder"]
    > ![Komentoa lisäämällä mukautettu kortti](media/working-with-references/form-customcard.png)

    Uuden kortin tulee lomake-ohjausobjektin alareunassa.

1. Muuta kortti näyttää kaikki teksti tarvittaessa.

    > [!div class="mx-imgBorder"]
    > ![Lisätty mukautettu kortti, tyhjä](media/working-with-references/form-inserted-customcard.png)

1. Lisää **nimen** mukautetun korttiin ohjausobjekti ja määritä sitten selitteen **tekstin** ominaisuudeksi kaava, jota käytit valikoimassa:

    ```powerapps-dot
    If( IsType( ThisItem.Owner, Teams ),
        "Team: " & AsType( ThisItem.Owner, Teams ).'Team Name',
        "User: " & AsType( ThisItem.Owner, Users ).'Full Name' )
    ```

    > [!div class="mx-imgBorder"]
    > ![Näytetään omistaja-kentän nimi-ohjausobjektin mukautettu kortti](media/working-with-references/form-displayowner.png)

Valikoiman jokaisen valinnan tilin omistajan tietueen kenttiä näkyvät lomakkeessa. Jos omistaja muuttaa käyttämällä **Patch** painikkeen, lomakeohjausobjekti näyttää myös muutokset.

> [!div class="mx-imgBorder"]
> ![Animaatio näytetään lomake-ohjausobjektin, muutokset valikoiman vastaaminen](media/working-with-references/form-allthree.gif)

## <a name="show-the-fields-of-a-customer"></a>Näytä asiakkaan kentät

Common Data Service- **asiakkaan** hakukenttä on toinen polymorfinen haku, joka muistuttaa **omistaja**.

**Omistajan** on rajoitettu yhden entiteetin, mutta entiteetit voivat sisältää nolla, yksi tai useampi **asiakkaan** hakukenttiä. **Yhteystiedot** järjestelmäentiteetti sisältää **yrityksen nimi** kenttä, joka on **asiakkaan** hakukentän.

> [!div class="mx-imgBorder"]
> ![Yrityksen nimi-kenttä näkyy asiakkaan tietotyyppi, joka ei ole pakollinen yhteystietoentiteetti](media/working-with-references/customer-companyname.png)

Voit lisätä Lisää **asiakkaan** hakukenttien entiteettiin valitsemalla **asiakkaan** uuden kentän tietotyyppi.

![Asiakkaan tietotyyppi tietotyyppejä luettelosta luotaessa kenttä](media/working-with-references/customer-datatype.png)

A **asiakkaan** hakukentän voi viitata tietueen joko **tilit** entiteetin tai **yhteystiedot** entiteetin. Käytät **IsType** ja **AsType** Funktiot näihin entiteetteihin nyt on hyvä lisätä ne tietolähteinä (Voit jättää **Teams** ja **käyttäjät**  paikkaan).

> [!div class="mx-imgBorder"]
> ![Tilit, ryhmiä, käyttäjät ja yhteystiedot entiteetit tietoruudun](media/working-with-references/customer-datasources.png)

Käsittely **asiakkaan** ja **omistaja** kentät on niin samankaltaisia, voit kopioida kirjaimellisesti sovelluksen (**tiedoston** > **Tallenna nimellä**, ja määritä eri nimi) ja tehdä nämä yksinkertainen korvaukset:

| Location | **Omistajan** malli | **Asiakkaan** malli |
|----------|-----------|------------------|
| Koko | **Omistaja** | **Asiakkaan nimi** |
| Koko | **Käyttäjät** | **Tilit** |
| Koko | **Ryhmät** | **Yhteystiedot** |
| Valikoiman **kohteet** ominaisuus | **Tilit** | **Yhteystiedot** |
| Lomakkeen **kohteet** ominaisuus | **Tilit** | **Yhteystiedot** |
| Ensimmäisen elementin **korjaustiedosto**<br>painikkeen Click- **OnSelect** ominaisuus | **Tilit** | **Yhteystiedot** |
| Suodata käyttäjän radio **kohteet** ominaisuus | **[&nbsp;”All”,&nbsp;”käyttäjät”&nbsp;”Teams”&nbsp;]** | **[&nbsp;”All”,&nbsp;”asiakkaat”&nbsp;”yhteystiedot”&nbsp;]** |
| Patch radio käyttäjän **kohteet** ominaisuus | **[”Käyttäjät”, ”Teams”]** | **[”Asiakkaat”, ”yhteyshenkilöt”]** |
| Yhdistelmäruudun **näkyvissä** ominaisuus | **”Käyttäjät”** ja **”Teams”** | **”Asiakkaat”** ja **”yhteystiedot”** |

Uusi valikoima tulee olla esimerkiksi tämä **kohteet** ominaisuus:

```powerapps-dot
Filter( Contacts,
    Radio1.Selected.Value = "All"
    Or (Radio1.Selected.Value = "Accounts" And 'Company Name' = ComboBox1.Selected)
    Or (Radio1.Selected.Value = "Contacts" And 'Company Name' = ComboBox1_1.Selected)
)
```

> [!div class="mx-imgBorder"]
> ![Asiakkaan sovelluksen johdettu sovelluksen omistajan kanssa yksinkertaisia muutoksia käyttöön](media/working-with-references/customer-simple-update.png)

Kaksi tärkeitä eroja **asiakkaan** ja **omistaja** edellyttää päivitystä kaavat valikoiman ja lomakkeen sisällä:

1. Yksi moneen suhteita **tilit** ja **yhteystiedot** etusijalla, kun viittaat nämä entiteettityyppejä nimen mukaan. Sijaan **tilit**, käytä  **\[ \@tilit]**; sijaan **yhteystiedot**, käytä  **\[ \@ Yhteystiedot]**. Käyttämällä [yleinen selvitysoperaattoria](functions/operators.md#disambiguation-operator), varmista, että, johon viitataan kohteen tyyppi **IsType** ja **AsType**. Tämä ongelma on olemassa vain kontekstissa tietueen valikoimassa ja lomake-ohjausobjekteja.

1. **Omistaja** kentän on oltava arvo, mutta **asiakkaan** kentät voidaan *tyhjä*. Tässä tapauksessa haetaan näyttämään tyyppinimi ilman oikeita tuloksia [ **IsBlank** funktion](functions/function-isblank-isempty.md), ja Näytä tyhjää tekstimerkkijonoa sen sijaan.

Molemmat nämä muutokset ovat samaa kaavaa, jotka näkyvät lomakkeessa, myös mukautettu kortti esimerkiksi **tekstin** valikoiman nimi-ohjausobjektin ominaisuus:

```powerapps-dot
If( IsBlank( ThisItem.'Company Name' ), "",
    IsType( ThisItem.'Company Name', [@Accounts] ),
        "Account: " & AsType( ThisItem.'Company Name', [@Accounts] ).'Account Name',
    "Contact: " & AsType( ThisItem.'Company Name', [@Contacts] ).'Full Name'
)
```

> [!div class="mx-imgBorder"]
> ![Päivitä alaotsikko nimi-ohjausobjektin valikoiman Text-ominaisuus](media/working-with-references/customer-update.png)

Nämä muutokset, voit tarkastella ja muuttaa **yrityksen nimi** kenttää **yhteystiedot** entiteetin.

> [!div class="mx-imgBorder"]
> ![Esitettävä animaatio näyttää, miten valitsemalla yhteystiedon muuttuu muita ohjausobjekteja ja lomake](media/working-with-references/customer-allthree.gif)

> [!NOTE]
> Tätä kirjoitettaessa **asiakkaan** hakuja on seuraavat rajoitukset:
>
> - Ei voi suodattaa luettelon tietyn tietueen perusteella **yhteystiedot** tai **tilit** entiteettejä. Suodattimen valintanapin ympyröiden edellisessä esimerkissä ei toimi.
> - Vain asiakas-kenttä, joka toimii on järjestelmän määrittämää **yrityksen nimi** , **yhteystiedot** entiteetin, jota käytettiin edellisessä esimerkissä. Lisäämällä asiakkaan mukautetun kentän ei vielä tueta.
> - Asiakas-kenttää ei voi poistaa käyttämällä **Patch** voit määrittää sen *tyhjä*.

## <a name="understand-regarding-lookup-fields"></a>Tutustu liittyy hakukenttiä

**Liittyy** hakukentän eroaa hieman ne, jotka olet jo työskennellyt kanssa tässä ohjeaiheessa. Soveltamalla kuviot, jotka on kuvattu tässä ohjeaiheessa alat ja sitten opit muita vinkkejä.

Voit aloittaa yksinkertaisesti **faksit** entiteetin. Tällä entiteetillä on polymorfinen **liittyy** hakukenttä, joka voi viitata **tilit**, **yhteystiedot**, ja muihin entiteetteihin. Sovellus voidaan suorittaa **asiakkaille** ja muokata sitä varten **faksit**.

| Location | **Asiakkaan** malli | **Faksit** malli |
|----------|-----------|------------------|
| Koko | **Asiakkaan nimi** | **Liittyy** |
| Valikoiman **kohteet** ominaisuus | **Yhteystiedot** | **Faksit** |
| Lomakkeen **kohteet** ominaisuus | **Yhteystiedot** | **Faksit** |
| Ensimmäisen elementin **korjaustiedosto**<br> painikkeen Click- **OnSelect** ominaisuus | **Yhteystiedot** | **Faksit** |

Uudelleen, sinun tulee Lisää tietolähde: Tämä aika määrittää **faksit**. Käyttöön **Näytä** -välilehden **tietolähteet**:

> [!div class="mx-imgBorder"]
> ![Tietoruutu näytetään tilit, Teams, käyttäjät, yhteystiedot ja faksit entiteetit](media/working-with-references/faxes-datasources.png)

Tärkeä ero **liittyy** on, että se ei ole rajoitettu **tilit** ja **yhteystiedot**. Itse asiassa luettelossa on laajennettava mukautettuihin entiteetteihin. Useimmat sovelluksen mahtuu tässä vaiheessa ilman muutoksia, mutta sinun on päivitettävä kaava valikoiman ja lomakkeen nimi:

```powerapps-dot
If( IsBlank( ThisItem.Regarding ), "",
    IsType( ThisItem.Regarding, [@Accounts] ),
        "Account: " & AsType( ThisItem.Regarding, [@Accounts] ).'Account Name',
    IsType( ThisItem.Regarding, [@Contacts] ),
        "Contacts: " & AsType( ThisItem.Regarding, [@Contacts] ).'Full Name',
    ""
)
```

> [!div class="mx-imgBorder"]
> ![Päivitetty Text-ominaisuus alaotsikko ohjausobjekti koskevat haut](media/working-with-references/regarding-label.png)

Kun teet nämä muutokset, voit käsitellä **liittyy** samalla tavalla kuin teit lookup **omistaja** ja **asiakkaan** hakuja.

> [!div class="mx-imgBorder"]
> ![Esitettävä animaatio näyttää, miten valitsemalla valikoiman kohde muuttuu muita ohjausobjekteja ja lomake](media/working-with-references/regarding-allthree.gif)

> [!NOTE]
> Tätä kirjoitettaessa **liittyy** hakuja on seuraavat rajoitukset:
>
> - Et voi suodattaa luettelon tietyn tietueen perusteella. Suodattimen valintanapin ympyröiden edellisessä esimerkissä ei toimi.
> - Liittyen-kenttä ei voi poistaa käyttämällä **Patch** voit määrittää sen *tyhjä*.

## <a name="understand-regarding-relationships"></a>Tutustu liittyy suhteet

**Liittyy** eroaa **omistaja** ja **asiakkaan** koska ensiksi liittyy monta yhteen-suhde. Näytteitä, käänteiseen, yksi-moneen-suhde avulla voit kirjoittaa **ensimmäisen (tiliä). Faksit**.

Aloitetaan Varmuuskopioi ja kohteiden määritelmiä. Common Data Service-entiteettejä, kuten- **faksit**, **tehtäviä**, **sähköpostiviestejä**, **huomautuksia**, **puheluita**, **Kirjaimia**, ja **keskustelut** määritetään [ *toiminnot*](../../developer/common-data-service/activity-entities.md). Voit myös luoda omia [mukautettuun toimintoon entiteetit](../../developer/common-data-service/custom-activities.md). Kun tarkastelet tai toiminnon entiteetin, sen asetukset näkyvät kohdassa **Lisää asetuksia**.

![Toiminnon entiteetin asetusta, kun entiteetin luominen](media/working-with-references/activity-entitytype.png)

Muut entiteetit voivat liittyä toisiinsa toiminta-entiteettiin, jos ne on otettu käyttöön *tehtävän* entiteetin asetuksissa. **Tilien**, **yhteystiedot**, ja monet muut vakioentiteetit ovat siis (uudelleen, valitse **Lisää asetuksia**).

![Toiminnon tehtävä asetusta, kun entiteetin luominen](media/working-with-references/activity-entityuse.png)

Kaikki toiminta entiteettejä ja entiteettejä, toiminta-tehtävä on epäsuora suhde. Jos muutat suodattimen **kaikki** näytön yläreunassa, valitse **faksit** entiteetin ja valitse sitten **suhteita** välilehteä kaikki entiteetit, jotka voivat olla  **Liittyy** lookup näkyvät.

> [!div class="mx-imgBorder"]
> ![Näytetään koskien monta yhteen-suhteiden faksit entiteetin suhteet](media/working-with-references/activity-manytoone.png)

Jos näytät suhteet **tilit** entiteetti, kaikki entiteetit, jotka voidaan lähde **liittyy** hakukentän näkyvät.

> [!div class="mx-imgBorder"]
> ![Tili-entiteetistä, jossa näkyy koskien yksi-moneen-suhteita suhteiden](media/working-with-references/activity-onetomany.png)

Mitä se kaikki tarkoittaa?

- Kun kirjoitat kaavoja, harkitse toiminta luettelossa ei ole kiinteä, että voit luoda omia. Kaava on käsiteltävä toiminta-entiteetti, jonka ei pitäisi asianmukaisesti.
- Toiminnon tehtäviä ja toiminnot on yksi-moneen-suhde. Voit helposti pyytää kaikki faksit, jotka liittyvät tiliin.

Tutki tämä konsepti sovelluksessa:

1. Lisää toinen näyttö.

    > [!div class="mx-imgBorder"]
    > ![Lisää tyhjä näyttö](media/working-with-references/activitypointer-newscreen.png)

1. Valikoima-ohjausobjektin lisääminen, muuta sen kokoa ja siirrä se näytön vasemmassa reunassa.

1. Käyttöön **ominaisuudet** välilehti lähellä näytön oikealla puolella, Määritä valikoiman **kohteet** - **tilit**.

    > [!div class="mx-imgBorder"]
    > ![Määrität kohteet tilien ominaisuus-ruudussa](media/working-with-references/activitypointer-accounts.png)

1. Aseta valikoiman asettelu **otsikko**, ja määritä sitten otsikko-kenttään **tilin nimi**.

    > [!div class="mx-imgBorder"]
    > ![Otsikon asettelun määrittäminen valikoima-ohjausobjektin ominaisuudet-ruutu](media/working-with-references/activitypointer-account-name.png)

1. Lisää toinen valikoima, muuta sen kokoa ja siirrä se näytön oikeassa reunassa.

1. Määritä uusi valikoiman **kohteet** ominaisuudeksi `Gallery2.Selected.Faxes`.

    Tässä vaiheessa palauttaa suodatetun faksiluettelon annettu tili.

    > [!div class="mx-imgBorder"]
    > ![Valikoiman, joka sisältää faksit Items-ominaisuuden asettaminen](media/working-with-references/activitypointer-faxes.png)

1. Aseta valikoiman asettelu **otsikko ja alaotsikko**, ja Aseta otsikkokenttä näyttämään **aihe** kenttä (joka voi olla kirjaimiksi **aihe**).

    > [!div class="mx-imgBorder"]
    > ![Määritä aihe-kentän nimi](media/working-with-references/activitypointer-subject.png)

Kun valitset kohteen luettelo tileistä, faksien luettelossa faksit vain tilin.

> [!div class="mx-imgBorder"]
> ![Animaatio määrittämiseksi faksiluettelon tilit valikoimassa näytetään valinta](media/working-with-references/activitypointer-allthree.gif)

## <a name="activity-entity"></a>Toiminta-entiteetti

Edellisen osan ohjeiden mukaan, voit näyttää kaikki faksit tili. Voit kuitenkin myös näyttää kaikki toiminnot on tilille, mukaan lukien faksit, sähköpostiviestit, puhelut ja muu vuorovaikutus.

Jälkimmäisessä skenaariossa käytät **toiminta** entiteetin. Voit näyttää tämän entiteetin ottamalla käyttöön **kaikki** oikeassa yläkulmassa voit poistaa suodattimen entiteettien luettelon.

> [!div class="mx-imgBorder"]
> ![Luettelossa näytetään toiminta-entiteetti](media/working-with-references/activitypointer-entity.png)

**Toiminta** entiteetti on erityinen. Aina, kun lisäät tietueen **faksit** entiteetin, järjestelmä luo myös tietueen **toiminta** entiteetin kentillä, jotka ovat yhteisiä kaikki toiminta-entiteetit. Näiden kenttien **aihe** on yksi eniten kiinnostavia.

Voit näyttää kaikki toiminnot muuttamalla vain yhden rivin edellisessä esimerkissä. Korvaa `Gallery2.Selected.Faxes` kanssa `Gallery2.Selected.Activities`.

> [!div class="mx-imgBorder"]
> ![Toinen valikoima, vaihdetaan faksit toimiin Items-ominaisuuden muutos](media/working-with-references/activitypointer-gallery.png)

Tietueet ovat peräisin **toiminta** entiteetin, mutta voit kuitenkin käyttää **IsType** funktio tunnistaa, millaisen toiminta ne ovat. Uudelleen, ennen kuin voit käyttää **IsType** entiteettityyppi, sinun on lisättävä tietolähteeseen.

> [!div class="mx-imgBorder"]
> ![Tietoruutu näytetään kaikki entiteetit, joita tarvitaan IsType-funktio](media/working-with-references/activity-datasources.png)

Voit näyttää selitteen ohjausobjektin valikoiman sisällä tietuetyyppi käyttämällä tätä kaavaa:

```powerapps-dot
If( IsType( ThisItem, [@Faxes] ), "Fax",
    IsType( ThisItem, [@'Phone Calls'] ), "Phone Call",
    IsType( ThisItem, [@'Email Messages'] ), "Email Message",
    IsType( ThisItem, [@Chats] ), "Chat",
    "Unknown"
)
```

> [!div class="mx-imgBorder"]
> ![Aseta text-ominaisuudeksi kaava, joka näyttää tiedot faksit, puhelut ja muita toimintoja](media/working-with-references/activitypointer-type.png)

Voit myös käyttää **AsType** käyttämään tietyn tyypin kentät. Esimerkiksi Tämä kaava määrittää kunkin toiminnon tyyppi, ja näyttää puheluita, phone numero ja kutsu suunta- **puhelinnumerot** entiteetin:

```powerapps-dot
If( IsType( ThisItem, [@Faxes] ), "Fax",
    IsType( ThisItem, [@'Phone Calls'] ),
       "Phone Call: " &
       AsType( ThisItem, [@'Phone Calls'] ).'Phone Number' &
       " (" & AsType( ThisItem, [@'Phone Calls'] ).Direction & ")",
    IsType( ThisItem, [@'Email Messages'] ), "Email Message",
    IsType( ThisItem, [@Chats] ), "Chat",
    "Unknown"
)
```

> [!div class="mx-imgBorder"]
> ![Laajennettu tekstiominaisuus, jonka puhelun lisätietoja](media/working-with-references/activitypointer-phonecall.png)

Tällöin sovellus näyttää luettelon kaikista toimintoja. **Aihe** kenttä tulee kaikenlaisia toiminnoista, kaava ottaa niitä huomioon vai ei. Erilaisia toimintoja, jotka tunnet voit näyttää niiden Kirjoita nimet ja kunkin toiminnon tyyppi liittyviä tietoja.

> [!div class="mx-imgBorder"]
> ![Suorittaa erilaisia toimintoja tiedot näytetään](media/working-with-references/activitypointer-complete.png)

## <a name="notes-entity"></a>Huomautuksia entiteetti

Tähän mennessä kaikista **liittyy** esimerkkejä pitänyt perustua toiminnoista, mutta **huomautuksia** entiteetin edustaa toisesta tapauksesta.

Kun luot entiteetin, voit ottaa liitteet.

> [!div class="mx-imgBorder"]
> ![Liitteet ja muistiinpanot käyttöön, kun luot entiteetin](media/working-with-references/notes-entity.png)

Jos valitset valintaruutu käyttöön liitteet, luot **liittyy** suhde **huomautuksia** entiteetin kuin tässä kuvassa näkyvät **tilit** entiteetin:

> [!div class="mx-imgBorder"]
> ![Tili-entiteetistä, näytetään suhteen huomautuksia yksi-moneen-suhteen kautta](media/working-with-references/notes-relationships.png)

Tämä ero kuin voit käyttää **liittyy** haku, jossa toiminnot käyttää samalla tavalla. Entiteettejä, jotka ovat käytössä liitteet olla yksi moneen suhde **huomautuksia**, kuten tässä esimerkissä:

`First( Accounts ).Notes`

> [!NOTE]
> Tätä kirjoitettaessa **liittyy** haku ei ole käytettävissä **huomautuksia** entiteetin. Ei voi lukea tai suodattimen perusteella **liittyy** kenttää ja ei voi määrittää kentän **Patch**.
>
> Kuitenkin päinvastoin **huomautuksia** yksi-moneen-suhde on saatavilla, joten voit suodattaa luettelon tietueen, joka on otettu käyttöön liitteet huomautukset. Voit myös käyttää [ **Relate** ](functions/function-relate-unrelate.md) funktio Lisää huomautus tietueen **huomautuksia** taulukkoa, mutta huomautuksen on luotava ensin, tämän esimerkin mukaisesti:
>
>`Relate( ThisItem.Notes, Patch( Notes, Defaults( Notes ), { Title: "A new note" } ) )`

## <a name="activity-parties"></a>Aktiviteetin osapuolet

Tätä kirjoitettaessa pohjaan perustuvat sovellukset eivät tue aktiviteetin osapuolet.
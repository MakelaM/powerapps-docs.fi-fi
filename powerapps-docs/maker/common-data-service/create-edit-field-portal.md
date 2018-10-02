---
title: Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-portaalin avulla | MicrosoftDocs
ms.custom: ''
ms.date: 05/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-fields-for-common-data-service-for-apps-using-powerapps-portal"></a>Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-portaalin avulla

[PowerApps-portaalissa](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) on helppo luoda ja muokata entiteettikenttiä Common Data Service sovelluksille -ratkaisun avulla.

Portaalin avulla voi määrittää yleisimmät asetukset, mutta jotkin asetukset on määritettävä ratkaisunhallinnan avulla. <br />Lisätietoja: 
- [Kenttien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa](create-edit-fields.md)
- [Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md)

## <a name="view-fields"></a>Näyttökentät

1. Valitse [PowerApps-portaalissa](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) joko **Mallipohjainen**- tai **Kaavio**-suunnittelutila.
2. Valitse **Tiedot** > **Entiteetit** ja valitse sitten entiteetti, jonka kenttiä haluat tarkastella.
3. Kun **Kentät**-välilehti on valittu, voit valita seuraavat näkymät: 

 |Näkymä|Kuvaus|
 |--|--|
 |**Kaikki**| Näyttää entiteetin kaikki kentät|
 |**Mukautettu**|Näyttää vain entiteetin mukautetut kentät|
 |**Oletus**|Näyttää vain entiteetin vakiokentät|
<!-- TODO: What is the actual difference between All and Default? -->

## <a name="create-a-field"></a>Kentän luominen

Kun tarkastelet kenttiä, valitse komentopalkissa **Lisää kenttä**. Näyttöön tulee **Kentän ominaisuudet** -paneeli.

![Kentän ominaisuudet](media/field-properties.png)


Alun perin käytettävissä on vain kolme kentän ominaisuutta:

 |Ominaisuus|Kuvaus|
 |--|--|
 |**Näyttönimi**|Käyttöliittymän kentässä näytettävä teksti.|
 |**Nimi**|Yksilöllinen nimi ympäristössä. Nimi luodaan annetun näyttönimen perusteella. Voit kuitenkin muokata sitä ennen tallennusta. Nimeä ei voi muuttaa kentän luomisen jälkeen, koska kenttään voidaan viitata sovelluksissa tai koodissa. Nimellä on mukautuksen etuliite **CDS:n oletusjulkaisijan** alussa.|
 |**Tietotyyppi**|Määrittää, miten arvot tallennetaan ja miten ne muotoillaan joissakin sovelluksissa. Kentän tietotyyppiä ei voi muuttaa tallennuksen jälkeen, koska se saattaa vaikuttaa entiteetin tietoihin.|

Voit määrittää lisäasetuksia **tietotyypin** valinnasta riippuen.

## <a name="field-data-types"></a>Kentän tietotyypit

Kenttätyyppejä on paljon, mutta voit luoda vain joitakin niistä. Lisätietoja kenttien tiedoista on kohdassa [Kenttien tyypit ja kentän tietotyypit](types-of-fields.md).

Kun luot kenttää, **tietotyyppi** mahdollistaa seuraavat vaihtoehdot:

### <a name="text"></a>Teksti 

Vakiotekstikenttiin voi tallentaa jopa 4 000 merkkiä. [Pituuden oletusarvo](#max-length) -asetuksen arvoksi on määritetty alempi arvo, jota voi muokata.

|Tietotyyppi|Kuvaus|
|--|--|
|**Teksti**|Tekstiarvo, joka näkyy yksirivisessä tekstiruudussa.|
|**Tekstialue**|Tekstiarvo, joka näkyy monirivisessä tekstiruudussa. Jos tarvitset enemmän kuin 4 000 merkkiä, käytä [monirivistä](#multi-line-field) tietotyyppiä.|
|**Sähköposti**|Sähköpostiosoitteeksi vahvistettu ja kentän mailto-linkiksi hahmonnettu tekstiarvo. |
|**URL-osoite**|URL-osoitteeksi vahvistettu ja URL-osoitteen avaavaksi linkiksi hahmonnettu tekstiarvo.|
|**Osaketunnus**|Kaupankäyntitunnuksen tekstiarvo. Se näyttää linkin, joka avaa pörssin kaupankäyntitunnuksen tarjouksen. |
|**Puhelin**|Puhelinnumeroksi vahvistettu ja linkiksi hahmonnettu tekstiarvo, joka aloittaa Skype-puhelun. |

#### <a name="max-length"></a> - enimmäispituus 

Tekstiä sisältävillä kentillä on absoluuttinen enimmäismäärä, joka riippuu tyypistä. **Enimmäispituus**-asetus määrittää arvon, joka on alempi kuin ympäristölle määritetty arvo. Voit kasvattaa tätä enimmäispituutta, mutta älä pienennä sitä, jos järjestelmän tiedot ylittävät pienemmän arvon.

### <a name="whole-number"></a>Kokonaisluku

Näihin kenttiin tallennetaan tiedot numeroina. Niiden esitystapa- ja vahvistusasetukset ovat erilaiset.

|Tietotyyppi|Kuvaus|
|--|--|
|**Kokonaisluku**|Numeroarvo, joka esitetään tekstiruudussa.|
|**Kesto**|Numeroarvo, joka esitetään aikavälit sisältävänä avattavana luettelona. Käyttäjä voi valita arvon luettelosta tai antaa kokonaislukuarvon, joka edustaa minuuttien määrää.|
|**Aikavyöhyke**|Numeroarvo, joka esitetään aikavyöhykeluettelon sisältävänä avattavana luettelona.|
|**Kieli**|Numeroarvo, joka esitetään avattavana luettelona, joka sisältää ympäristössä käytössä olevien kielten luettelon. Jos muita kieliä ei ole otettu käyttöön, peruskieli on ainoa vaihtoehto. Tallennettu arvo on kielialueen tunnuksen arvo kieltä varten.|


### <a name="date-time"></a>Päivämäärä ja aika

Näihin kenttiin tallennetaan aika-arvoja. Voit tallentaa arvoja jo ajankohdasta 1.1.1753 kello 00.00 alkaen.

|Tietotyyppi|Kuvaus|
|--|--|
|**Päivämäärä ja aika**|Päivämäärän ja ajan arvo.|
|**Vain päivämäärä**|Päivämäärän ja ajan arvo, joka näkyy vain päivämääränä. Ajan arvo tallennetaan järjestelmään muodossa 00.00 (00:00:00).|

Voit myös määrittää tietyn **toimintatavan** päivämäärän ja ajan kenttiin **Lisäasetukset**-kohtaan.

- **Käyttäjän paikallinen** : Näyttää nykyisen käyttäjän paikallisen aikavyöhykkeen mukaan muunnetut arvot. Tämä on uusien kenttien oletusarvo.
- **Vain päivämäärä**: Tämä toimintatapa on **Vain päivämäärä** -tyypin käytettävissä. Näyttää arvot ilman aikavyöhykkeen muuntamista. Käytä tätä kohtaa esimerkiksi syntymäpäivissä ja vuosipäivissä.
- **Aikavyöhykkeestä riippumaton**: Näyttää arvot ilman aikavyöhykkeen muuntamista.

Lisätietoja. [Päivämäärä ja aika -kentän toimintatapa ja muoto](behavior-format-date-time-field.md)

### <a name="other-data-types"></a>Muut tietotyypit

|Tietotyyppi|Kuvaus|
|--|--|
|**Valuutta**|Ympäristöä varten määritettyjen valuuttojen rahallinen arvo. Voit määrittää tarkkuustason tai valita tarkkuuden tietyn valuutan perusteella tai organisaation käyttämän yhden standardin. Lisätietoja: [Valuuttakenttien käyttäminen](types-of-fields.md#using-currency-fields)|
|**Desimaaliluku**| Desimaaliarvo, jonka tarkkuus on enintään 10 desimaalia. Lisätietoja: [Oikean numerotyypin käyttäminen](types-of-fields.md#using-the-right-type-of-number)|
|**Liukuluku**|Liukuluku, jonka tarkkuus on enintään 5 desimaalia. Lisätietoja: [Oikean numerotyypin käyttäminen](types-of-fields.md#using-the-right-type-of-number)|
|**Kuva**|Näyttää sovelluksessa yhden kuvan tietuetta kohti. Kussakin entiteetissä voi olla vain yksi kuvanäkymä. Kuvakentälle luonnin yhteydessä annettava **nimi** ohitetaan. Kuvakenttien nimeksi annetaan aina EntityImage.|
|**Monivalinta-asetusjoukko**|Näyttää asetusluettelon, josta voi valita useita asetuksia.|
|<a name="multi-line-field"></a> **Monirivinen teksti**|Tekstiarvo, joka näkyy monirivisessä tekstiruudussa. Merkkien enimmäismäärä on 1 048 576. Voit pienentää [enimmäispituutta](#max-length). |
|**Asetusjoukko**|Näyttää asetusluettelon, josta voi valita vain yhden asetuksen.|
|**Kaksi asetusta**|Näyttää kaksi vaihtoehtoa, joista voi valita vain toisen. Valitse kullekin vaihtoehdolle näytettävä otsikko. Oletusarvot ovat **Kyllä** ja **Ei**.|

## <a name="save-new-field"></a>Tallenna uusi kenttä

Kun olet määrittänyt **Näyttönimi**-, **Nimi**- ja **Tietotyyppi**-ominaisuudet, voit sulkea **Kentän ominaisuudet** -paneelin valitsemalla **Valmis**. 

Voit jatkaa entiteetin muokkaamista ja lisätä kenttiä tai palata ja jatkaa tämän kentän muokkaamista. Kenttä luodaan vasta, kun valitset **Tallenna entiteetti** -kohdan. Tällöin entiteetin kaikki muutokset tallennetaan.

![Tallenna entiteetti -painike](media/save-entity-button.png)

Voit myös valita **Hylkää**-painikkeen, jos haluat hylätä tekemäsi muutokset.
 
## <a name="edit-a-field"></a>Kentän muokkaaminen

Valitse muokattava kenttä kenttien tarkastelun yhteydessä. Voit muokata **näyttönimeä**, mutta et voi muuttaa **nimeä** ja **tietotyyppiä**, jos olet tallentanut kenttään lisättävän entiteetin muutokset.

### <a name="general-properties"></a>Yleiset ominaisuudet
Jokaisella kentällä on seuraavat ominaisuudet, joita voit muuttaa:

|Ominaisuus|Kuvaus|
|--|--|
|**Pakollinen**|Kun tämä on valittuna, tietueen voi tallentaa vain, jos kentässä on tietoja.|
|**Etsittävissä**|Poista tämän valinta niiden entiteettien kentiltä, joita et käytä.  Jos kentässä voi tehdä hakuja, se näkyy **Erikoishaku**-kohdassa ja sitä voi käyttää näkymiä mukautettaessa. Jos tämän kohdan valinta poistetaan, erikoishaun käyttäjien saamien tulosten määrä pienenee.|
|**Kuvaus**|Tämä löytyy **Lisäasetukset**-kohdasta. Anna käyttäjälle kentän käyttämistä koskevat ohjeet. Nämä kuvaukset näkyvät käyttäjälle työkaluvihjeinä mallipohjaisissa sovelluksissa, kun käyttäjä pitää hiiren osoitinta kentän otsikon päällä.|

> [!NOTE]
> **Kenttien määrittäminen pakollisiksi**: Ole varovainen, kun määrität kenttiä pakollisiksi. Käyttäjät eivät halua käyttää sovellusta, jos he eivät voi tallentaa tietueita, koska he eivät tiedä pakollisen kentän edellyttämiä tietoja. Käyttäjät voivat ilmoittaa virheellisiä tietoja voidakseen tallentaa tietueen ja jatkaakseen töitään.
>
>**Määritä tarve dynaamisesti**: Voit muuttaa vaatimustasoa mallipohjaisissa sovelluksissa liiketoimintasäännöillä tai lomakkeen komentosarjoilla, kun tietueiden tiedot muuttuvat käyttäjien käsitellessä niitä. Lisätietoja: [Liiketoimintasääntöjen ja suositusten luonti käyttämällä lomakkeen logiikkaa](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)
>
>**Erikoishaun saatavuus**: Erikoishaku on tällä hetkellä saatavilla vain mallipohjaisissa sovelluksissa, joissa käytetään WWW-asiakasohjelmaa. Erikoishaku ei ole saatavilla Unified Interface -asiakasohjelmissa tällä hetkellä.

## <a name="calculated-or-rollup"></a>Laskennallinen tai koonti

Voit määrittää mukautetun kentän **laskennalliseksi kentäksi** tai **koontikentäksi**. Kenttiä, jotka eivät ole laskennallisia kenttiä tai koontikenttiä, sanotaan joskus *yksinkertaisiksi* kentiksi.

### <a name="calculated"></a>Laskettu

Laskennallisen kentän avulla voit syöttää kaavan ja määrittää kenttään arvon. Nämä tietotyypit voidaan määrittää laskennallisiksi kentiksi: **Valuutta**, **Päivämäärä ja aika**, **Vain päivämäärä**, **Desimaaliluku**, **Kesto**, **Sähköposti**, **Kieli**, **Monivalinta-asetusjoukko**, **Asetusjoukko**, **Teksti**, **Tekstialue**, **Kaupankäyntitunnus**, **Aikavyöhyke**, **Kaksi asetusta**, **URL-osoite** ja **Kokonaisluku**.

Lisätietoja: [Laskennallisten kenttien määrittäminen manuaalisen laskennan automatisointia varten](define-calculated-fields.md)

### <a name="rollup"></a>Koonti

Koontikentän avulla voit määrittää koontitoiminnot, jotka suoritetaan säännöllisesti kentän numeroarvon määrittämiseksi. Nämä tietotyypit voidaan määrittää laskennallisiksi kentiksi: **Valuutta**, **Päivämäärä ja aika**, **Vain päivämäärä**, **Desimaaliluku**, **Kesto**, **Kieli**, **Aikavyöhyke** ja **Kokonaisluku**.

Lisätietoja: [Arvot kokoavien koontikenttien määrittäminen](define-rollup-fields.md)

## <a name="number-field-options"></a>Numerokentän asetukset

Numerokentän jokaisella tyypillä on absoluuttiset vähimmäis- ja enimmäisarvot. Voit määrittää näille absoluuttisille arvoille soveltuvan **vähimmäis**- ja **enimmäisarvon**. Tee niin, jotta CDS sovelluksille -ratkaisu voi tarkistaa tietojen arvot, jotka haluat tallentaa kenttään.

Voit määrittää **Liukuluku**- ja **Desimaaliluku**-tietotyypeille useita **desimaalilukuja**.


## <a name="option-set-field-options"></a>Asetusjoukkokentän asetukset

Kentät, joilla on oma asetusjoukko, voivat sisältää omat *paikalliset* asetukset. Ne voivat myös viitata yleiseen joukkoon *yleisiä* asetuksia, jota voidaan käyttää useissa kentissä.

Yleisen asetusjoukon käyttäminen kannattaa, jos useille kentille luodaan sama asetusjoukko. Kun yleinen asetusjoukko on määritetty, käyttäjä voi ylläpitää asetusjoukkoa yhdessä paikassa. 

Kun valitset **Monivalinta-asetusjoukko**- tai **Asetusjoukko**-tietotyypin, suunnitteluohjelmaan tulee saatavilla olevien yleisten asetusjoukkojen luettelo. Voit valita niistä joukon, jonka avulla voit luoda **uuden asetusjoukon**.

![Asetusjoukon tyypin valitseminen](media/option-set-options.png)

Jos valitset **uuden asetusjoukon**, luodaan uusi yleinen asetusjoukko oletustoiminnan mukaisesti.

> [!NOTE]
> Kun muokkaat uuden yleisen asetusjoukon asetuksia, käytä **Näyttönimi**- ja **Nimi**-arvoja yleisessä asetusjoukossa kentän sijaan. Oletusarvot vastaavat kentän arvoja. Voit kuitenkin muokata arvoja yleisen asetusjoukon muokkaamisen yhteydessä ja muuttaa arvoja niin, että ne eivät vastaa käsittelyssä olevan kentän arvoja.

Jos haluat luoda paikallisen asetusjoukon, valitse **Näytä lisää** ja valitse sitten **Paikallinen asetusjoukko**.

![Paikallinen asetusjoukko](media/local-option-set.png)

> [!NOTE]
> Jos määrität jokaisen asetusjoukon yleiseksi asetusjoukoksi, yleisten asetusjoukkojen luettelo kasvaa. Tällöin sen hallinta voi olla vaikeaa. Jos tiedät, että asetusjoukkoa tullaan käyttämään vain yhdessä paikassa, käytä paikallista asetusjoukkoa.

[!INCLUDE [cc_remove-option-warning](../../includes/cc_remove-option-warning.md)]

## <a name="delete-a-field"></a>Kentän poistaminen

Käyttäjä, jolla on järjestelmänvalvojan käyttöoikeusrooli, voi poistaa minkä tahansa mukautetun kentän, joka ei sisälly hallittuun ratkaisuun. Kun kenttä poistetaan, kaikki kenttään tallennetut tiedot menetetään. Poistetun kentät tiedot voidaan palauttaa vain palauttamalla tietokanta hetkeen ennen kentän poistamista.

> [!NOTE]
> Ennen mukautetun kentän poistamista sinun on poistettava muissa ratkaisun osissa mahdollisesti olevat riippuvuudet. 

Jos valitset [kenttien tarkastelemisen](#view-fields) yhteydessä mukautetun kentän, joka voidaan poistaa luettelosta, näkyviin tulee **Poista kenttä** -komento, joka on käytössä.

![Kentän poistaminen portaalin avulla](media/delete-field-portal.png)

Poista kenttä **Poista kenttä** -komennon avulla. Kun kenttä on poistettu, entiteetin muutokset on tallennettava.

![Entiteetin tallentaminen kentän poistamisen jälkeen](media/delete-field-portal-save-entity.png)

> [!NOTE]
> Jos näyttöön tulee riippuvuuksiin liittyvä virhesanoma, etsi riippuvuuden ratkaisunhallinnan avulla. Lisätietoja: [Kentän riippuvuuksien tarkistaminen](create-edit-field-solution-explorer.md#check-field-dependencies)

## <a name="ime-mode"></a>IME-tila

Kaikissa kentissä, joihin voi kirjoittaa suoraan tekstiä, on IME-tila. IME-editoria käytetään itäaasialaisissa kielissä, kuten japanissa. IME-editorien avulla käyttäjä voi syöttää tuhansia itäaasialaisissa kirjoitetuissa kielissä käytettyjä merkkejä tavallisella 101-näppäimisellä näppäimistöllä.



### <a name="see-also"></a>Katso myös  
[Kenttien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa](create-edit-fields.md)<br />
[Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md)<br />
[Kenttien tyypit ja kentän tietojen tyypit](types-of-fields.md)<br />
[Voit automatisoida manuaalisen laskennan laskettujen kenttien määrittämiseen](define-calculated-fields.md)<br />
[Määritä koontikenttiä, jotka kokoavat arvoja](define-rollup-fields.md)<br />
[Päivämäärän ja kellonajan kentän toimintatapa ja muoto](behavior-format-date-time-field.md)

---
title: Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla | MicrosoftDocs
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
# <a name="create-and-edit-fields-for-common-data-service-for-apps-using-powerapps-solution-explorer"></a>Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla

Ratkaisunhallinta on eräs tapa luoda kenttiä Common Data Service sovelluksille -ratkaisuun ja muokata niitä.

[PowerApps-portaalin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) avulla voi määrittää yleisimmät asetukset, mutta jotkin asetukset on määritettävä ratkaisunhallinnan avulla. <br />Lisätietoja: 
- [Kenttien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa](create-edit-fields.md)
- [Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-portaalin avulla](create-edit-field-portal.md)
  
## <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Jokaisen luodun mukautetun kentän nimeen sisältyy mukautuksen etuliite. Tämä määritetään työn alla olevan ratkaisun ratkaisujulkaisijassa. Jos haluat käyttää mukautuksen etuliitettä, varmista, että käsittelyssä on hallitsematon ratkaisu, jonka mukautuksen etuliitteen haluat tälle entiteetille. Lisätietoja: [Ratkaisujulkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]


## <a name="view-fields"></a>Näyttökentät

Kun ratkaisunhallinta on auki, laajenna **Osat**-kohdassa **Entiteetit** ja valitse entiteetti, johon haluat luoda kentän tai jonka kenttää haluat muokata.

![Ratkaisunhallinnan kenttien näkymä](media/solution-explorer-fields-view.png)

Voit valita seuraavat näkymät: 

 |Näkymä|Kuvaus|
 |--|--|
 |**Kaikki**| Näyttää entiteetin kaikki kentät|
 |**Mukautettu**|Näyttää vain entiteetin mukautetut kentät|
 |**Mukautettavissa**|Näyttää vain muokattavissa olevat kentät|

## <a name="create-a-field"></a>Kentän luominen

Valitse kenttien tarkastelemisen aikana komentopalkissa **Uusi**-kohta, jolloin uusi kenttälomake avautuu.  Tietyt hallittuun ratkaisuun sisältyvät vakioentiteetit tai mukautetut entiteetit eivät ehkä salli uusien kenttien lisäämistä.

> [!NOTE]
> Mallipohjaisille sovelluksille voi luoda uuden kentän myös lomake-editorissa. Luo lomake-editorissa uusi kenttä valitsemalla **Kenttien hallinta** -kohdan alapuolella oleva **Uusi kenttä**. Lisätietoja: [Kentän lisääminen lomakkeeseen](../model-driven-apps/add-field-form.md)

![Ratkaisunhallinnan uusi kenttälomake](media/solution-explorer-new-field-form.png)

Syötä tiedot ja vahvista seuraaville ominaisuuksille määritetyt oletusarvot ennen tallennusta.

|Ominaisuus|Kuvaus|
|--|--|
|**Näyttönimi**|Käyttöliittymän kentässä näytettävä teksti. Voit muuttaa tämän tallentamisen jälkeen, mutta syötetty arvo luo **Nimi**-kentän arvon.|
|**Kenttävaatimus**|Määrittää, onko kentässä oltava tietoja, jotta tietue voidaan tallentaa. Lisätietoja: [Kenttävaatimuksen asetukset](#field-requirement-options)|
|**Nimi**|Yksilöllinen nimi ympäristössä. Nimi luodaan annetun näyttönimen perusteella. Voit kuitenkin muokata sitä ennen tallennusta. Nimeä ei voi muuttaa kentän luomisen jälkeen, koska kenttään voidaan viitata sovelluksissa tai koodissa. Nimellä on mukautuksen etuliite nykyisen ratkaisun julkaisijan alussa.|
|**Etsittävissä**|Määritä käyttämättömän entiteetin kenttien arvoksi **Ei**.  Jos kentässä voi tehdä hakuja, se näkyy mallipohjaisissa sovelluksissa **Erikoishaku**-kohdassa ja sitä voi käyttää näkymiä mukautettaessa. Jos tämän kohdan valinta poistetaan, erikoishaun käyttäjien saamien tulosten määrä pienenee.|
|**Kentän suojaus**|Määrittää, onko kentän tiedot suojattu entiteettiä korkeammalla tasolla. Lisätietoja: [Käytön hallinta kenttätason suojauksen avulla](/dynamics365/customer-engagement/admin/field-level-security)|
|**Seuranta**|Määrittää voiko tämän kentän tietoja seurata, kun seuranta on käytössä entiteetissä. Lisätietoja: [Tietojen ja käyttäjien toimintojen seuraaminen suojausta ja säädösten noudattamista varten](/customer-engagement/admin/audit-data-user-activity)|
|**Kuvaus**|Anna käyttäjälle kentän käyttämistä koskevat ohjeet. Nämä kuvaukset näkyvät käyttäjälle työkaluvihjeinä mallipohjaisissa sovelluksissa, kun käyttäjä pitää hiiren osoitinta kentän otsikon päällä.|
|**Näkyy yleisessä suodatuksessa vuorovaikutteisessa kokemuksessa**|Lisätietoja: [Vuorovaikutteisen kokemuksen koontinäyttöjen määrittäminen](/dynamics365/customer-engagement/customize/configure-interactive-experience-dashboards) |
|**Lajiteltavissa vuorovaikutteisen kokemuksen koontinäytössä**|Lisätietoja: [Vuorovaikutteisen kokemuksen koontinäyttöjen määrittäminen](/dynamics365/customer-engagement/customize/configure-interactive-experience-dashboards)|
|**Tietotyyppi**|Määrittää, miten arvot tallennetaan ja miten ne muotoillaan joissakin sovelluksissa. Kentän tietotyyppiä ei voi muuttaa tallennuksen jälkeen, koska se saattaa vaikuttaa entiteetin tietoihin. Lisätietoja: [Kentän tietotyypit](#field-data-types)|
|**Kenttätyyppi**|Määrittää, onko kenttä **yksinkertainen**, **laskennallinen** vai **koontikenttä**. Lisätietoja: [Kenttätyyppi](#field-type)|
|**Muoto**|Määrittää, miten kenttä muotoillaan. Käytettävissä olevat muotoiluasetukset riippuvat **tietotyypistä**.|

Voit määrittää lisäasetuksia **tietotyypin** valinnasta riippuen. Lisätietoja: [Kentän tietotyypit](#field-data-types)

## <a name="field-requirement-options"></a>Kenttävaatimuksen asetukset

Kenttävaatimuksen asetuksia on kolme:
- **Valinnainen**: Tietue voidaan tallentaa, vaikka kentässä ei ole tietoja.
- **Suositeltava**: Tietue voidaan tallentaa, vaikka kentässä ei ole tietoja. Sininen symboli kentän vieressä kuitenkin osoittaa, että kenttä on tärkeä.
- **Pakollinen**: Tietuetta ei voi tallentaa, jos kentässä ei ole tietoja.
> [!NOTE]
> Ole varovainen, kun teet kentistä pakollisia. Käyttäjät eivät halua käyttää sovellusta, jos he eivät voi tallentaa tietueita, koska he eivät tiedä pakollisen kentän edellyttämiä tietoja. Käyttäjät voivat ilmoittaa virheellisiä tietoja voidakseen tallentaa tietueen ja jatkaakseen töitään. Voit muuttaa vaatimustasoa liiketoimintasäännöillä tai lomakkeen komentosarjoilla, kun tietueiden tiedot muuttuvat käyttäjien käsitellessä niitä. Lisätietoja: [Liiketoimintasääntöjen ja suositusten luonti käyttämällä lomakkeen logiikkaa](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)

## <a name="field-data-types"></a>Kentän tietotyypit

Kenttätyyppejä on paljon, mutta voit luoda vain joitakin niistä. Lisätietoja kenttien tiedoista on kohdassa [Kenttien tyypit ja kentän tietotyypit](types-of-fields.md).

Kun luot kenttää, **tietotyyppi** mahdollistaa seuraavat vaihtoehdot:

|Asetus|Kuvaus|
|--|--|
|**Yksi tekstirivi**|Tässä kentässä voi olla enintään 4 000 merkkiä tekstiä. Voit määrittää enimmäispituuden tätä pienemmäksi. Kentässä on useita tekstin ulkoasua muuttavia muotoiluasetuksia.  Lisätietoja: [Yhden tekstirivin asetukset](#single-line-of-text-options)|
|**Asetusjoukko**|Näyttää asetusluettelon, josta voi valita yhden asetuksen. Lisätietoja: [Asetusjoukkokentän asetukset](#option-set-field-options)|
|**MultiSelect-asetusjoukko (monivalinta)**|Näyttää asetusluettelon, josta voi valita useita asetuksia. Lisätietoja: [Asetusjoukkokentän asetukset](#option-set-field-options)|
|**Kaksi asetusta**|Näyttää asetusluettelon, jonka kahdesta asetuksesta voit valita toisen.<br /><br /> Kaksi asetusta -kentissä ei ole muotoiluasetuksia kenttätasolla. Kun lisäät sen lomakkeeseen, voit valita niiden näyttämisen valintanappina, valintaruutuna tai valintaluettelona.|
|**Kuva**|Näyttää sovelluksessa yhden kuvan tietuetta kohti. Kussakin entiteetissä voi olla vain yksi kuvanäkymä. Kuvakenttien nimeksi annetaan aina `EntityImage`.|
|**Kokonaisluku**|Tämän kentän arvona voi käyttää kokonaislukua -2 147 483 648–2 147 483 647.  Tällä kentällä on asetuksia, jotka muuttuvat sen mukaan, miten kenttä esitetään. Lisätietoja: [Kokonaisluvun asetukset](#whole-number-options)|
|**Liukuluku**|Tämän kentän arvoissa voi käyttää enintään 5 desimaalin tarkkuutta arvoalueella -100 000 000 000–100 000 000 000. Voit määrittää tarkkuustason sekä suurimman ja pienimmän arvon. Lisätietoja: [Oikean numerotyypin käyttäminen](types-of-fields.md#using-the-right-type-of-number)|
|**Desimaaliluku**|Tämän kentän arvoissa voi käyttää enintään 10 desimaalin tarkkuutta arvoalueella -100 000 000 000–100 000 000 000. Voit määrittää tarkkuustason sekä suurimman ja pienimmän arvon. Lisätietoja: [Oikean numerotyypin käyttäminen](types-of-fields.md#using-the-right-type-of-number)|
|**Valuutta**|Tämän kentän rahallisen arvon on oltava -922 337 203 685 477–922 337 203 685 477. Voit määrittää tarkkuustason tai valita tarkkuuden tietyn valuutan perusteella tai organisaation käyttämän yhden standardin. Lisätietoja: [Valuuttakenttien käyttäminen](types-of-fields.md#using-currency-fields)|
|**Useita tekstirivejä**|Tässä kentässä voi olla enintään 1 048 576 merkkiä tekstiä. Voit määrittää enimmäispituuden tätä pienemmäksi. Voit määrittää kentän mitat. kun lisäät sen mallipohjaisen sovelluksen lomakkeeseen.|
|**Päivämäärä ja aika**|Näihin kenttiin tallennetaan aika-arvoja. Voit tallentaa arvoja jo ajankohdasta 1.1.1753 kello 00.00 alkaen. Lisätietoja: [Päivämäärän ja ajan asetukset](#date-and-time-options)|
|**Valinta**|Kenttä sallii viittauksen määrittämisen tietyn entiteettityypin yhteen tietueeseen. Jotkin järjestelmän valintakentät toimivat eri tavoin. Lisätietoja: [Erityyppiset haut](types-of-fields.md#different-types-of-lookups)|
|**Asiakas**|Hakukenttä, jonka avulla voit määrittää asiakkaan, joka voi olla asiakkuus tai yhteyshenkilö.  Lisätietoja: [Erityyppiset haut](types-of-fields.md#different-types-of-lookups)|

### <a name="single-line-of-text-options"></a>Yhden tekstirivin asetukset

Yksi tekstirivi -tietotyypillä on seuraavat muotoiluasetukset:

|Muotoilu|Kuvaus|
|--|--|
|**Teksti**|Tekstiarvo, joka näkyy yksirivisessä tekstiruudussa.|
|**Tekstialue**|Tekstiarvo, joka näkyy monirivisessä tekstiruudussa. Jos tarvitset enemmän kuin 4 000 merkkiä, käytä **Useita tekstirivejä** tietotyyppiä.|
|**Sähköposti**|Sähköpostiosoitteeksi vahvistettu ja kentän mailto-linkiksi hahmonnettu tekstiarvo. |
|**URL-osoite**|URL-osoitteeksi vahvistettu ja URL-osoitteen avaavaksi linkiksi hahmonnettu tekstiarvo.|
|**Osaketunnus**|Kaupankäyntitunnuksen tekstiarvo. Se näyttää linkin, joka avaa pörssin kaupankäyntitunnuksen tarjouksen. |
|**Puhelin**|Puhelinnumeroksi vahvistettu ja linkiksi hahmonnettu tekstiarvo, joka aloittaa Skype-puhelun. |

Voit määrittää myös **enimmäispituuden**, jolloin järjestelmä ei salli määrittämääsi arvoa pidempiä tekstiarvoja.

### <a name="option-set-field-options"></a>Asetusjoukkokentän asetukset

Kentät, joilla on oma asetusjoukko, voivat sisältää omat *paikalliset* asetukset. Ne voivat myös viitata yleiseen joukkoon *yleisiä* asetuksia, jota voidaan käyttää useissa kentissä.

Yleisen asetusjoukon käyttäminen kannattaa, jos useille kentille luodaan sama asetusjoukko. Kun yleinen asetusjoukko on määritetty, käyttäjä voi ylläpitää asetusjoukkoa yhdessä paikassa. 

Kun valitset **Monivalinta-asetusjoukko**- tai **Asetusjoukko**-tietotyypin, ratkaisunhallinnan suunnitteluohjelma antaa oletusarvoisesti asetukseksi paikallisen asetusjoukon.

![Paikallisen asetusjoukon määrittäminen](media/local-option-set-solution-explorer.png)

#### <a name="configure-local-options"></a>Paikallisten asetusten määrittäminen

[!INCLUDE [cc_configure-option-set-options-solution-explorer](../../includes/cc_configure-option-set-options-solution-explorer.md)]

#### <a name="use-existing-option-set"></a>Käytä aiemmin luotua asetusjoukkoa

Jos valitset **Käytä olemassa olevaa asetusjoukkoa** -arvon, suunnitteluohjelma näyttää olemassa olevien *yleisten asetusjoukkojen* luettelon. Se näyttää myös **Muokkaa**- ja **Uusi**-painikkeet, joiden avulla voi määrittää tämän kentän käyttämät yleiset asetukset.

![Yleisen asetusjoukon määrittäminen](media/global-option-set-solution-explorer.png)

Voit määrittää yleiset asetusjoukot myös erikseen. Lisätietoja: [Common Data Service sovelluksille -ratkaisun yleisten asetusjoukkojen luominen ja muokkaaminen (valintaluettelot)](create-edit-global-option-sets.md)

> [!NOTE]
> Jos määrität jokaisen asetusjoukon yleiseksi asetusjoukoksi, yleisten asetusjoukkojen luettelo kasvaa. Tällöin sen hallinta voi olla vaikeaa. Jos tiedät, että asetusjoukkoa tullaan käyttämään vain yhdessä paikassa, käytä paikallista asetusjoukkoa.


### <a name="whole-number-options"></a>Kokonaisluvun asetukset

Kokonaislukukentillä on seuraavat muotoiluvaihtoehdot:

|Muotoilu|Kuvaus|
|--|--|
|**Ei mikään**|Numeroarvo, joka esitetään tekstiruudussa.|
|**Kesto**|Numeroarvo, joka esitetään aikavälit sisältävänä avattavana luettelona. Käyttäjä voi valita arvon luettelosta tai antaa kokonaislukuarvon, joka edustaa minuuttien määrää.|
|**Aikavyöhyke**|Numeroarvo, joka esitetään aikavyöhykeluettelon sisältävänä avattavana luettelona.|
|**Kieli**|Numeroarvo, joka esitetään avattavana luettelona, joka sisältää ympäristössä käytössä olevien kielten luettelon. Jos muita kieliä ei ole otettu käyttöön, peruskieli on ainoa vaihtoehto. Tallennettu arvo on kielialueen tunnuksen arvo kieltä varten.|

Voit myös määrittää sallitut enimmäis- ja vähimmäisarvot.

### <a name="date-and-time-options"></a>Päivämäärän ja ajan asetukset

Päivämäärän ja ajan kentillä on seuraavat asetukset:

|Muotoilu |Kuvaus|
|--|--|
|**Päivämäärä ja aika**|Päivämäärän ja ajan arvo.|
|**Vain päivämäärä**|Päivämäärän ja ajan arvo, joka näkyy vain päivämääränä. Ajan arvo tallennetaan järjestelmään muodossa 00.00 (00:00:00).|

Voit myös määrittää tietyn **toimintatavan** päivämäärän ja ajan kenttiin **Lisäasetukset**-kohtaan.

- **Käyttäjän paikallinen** : Näyttää nykyisen käyttäjän paikallisen aikavyöhykkeen mukaan muunnetut arvot. Tämä on uusien kenttien oletusarvo.
- **Vain päivämäärä**: Tämä toimintatapa on **Vain päivämäärä** -tyypin käytettävissä. Näyttää arvot ilman aikavyöhykkeen muuntamista. Käytä tätä kohtaa esimerkiksi syntymäpäivissä ja vuosipäivissä.
- **Aikavyöhykkeestä riippumaton**: Näyttää arvot ilman aikavyöhykkeen muuntamista.

Lisätietoja. [Päivämäärä ja aika -kentän toimintatapa ja muoto](behavior-format-date-time-field.md)

## <a name="field-type"></a>Kenttälaji

Voit määrittää mukautetun kentän **kenttätyypin** **yksinkertaiseksi**, **laskennalliseksi** tai **koontikentäksi**. 

### <a name="simple"></a>Pelkistetty

Yksinkertainen kenttä tarkoittaa sitä, että kyseessä ei ole laskennallinen kenttä tai koontikenttä.

### <a name="calculated"></a>Laskettu

Laskennallisen kentän avulla voit syöttää kaavan ja määrittää kenttään arvon. Laskennallisille kentille voi määrittää nämä tietotyypit: **Valuutta**, **Päivämäärä ja aika**,  **Desimaaliluku**,  **Monivalinta-asetusjoukko**, **Asetusjoukko**, **Yksi tekstirivi**, **Kaksi asetusta** ja **Kokonaisluku**.

Lisätietoja: [Laskennallisten kenttien määrittäminen manuaalisen laskennan automatisointia varten](define-calculated-fields.md)

### <a name="rollup"></a>Koonti

Koontikentän avulla voit määrittää koontitoiminnot, jotka suoritetaan säännöllisesti kentän numeroarvon määrittämiseksi. Nämä tietotyypit voidaan määrittää laskennallisiksi kentiksi: **Valuutta**, **Päivämäärä ja aika**, **Desimaaliluku** ja **Kokonaisluku**.

Lisätietoja: [Arvot kokoavien koontikenttien määrittäminen](define-rollup-fields.md)

## <a name="save-new-field"></a>Tallenna uusi kenttä

Kun olet määrittänyt kentän, käytä jotain komentopalkin seuraavista kolmesta komennosta:

|Komento|Kuvaus|
|--|--|
|**Tallenna**|Tallenna kentän määritys ja jätä lomakeikkuna auki.|
|**Tallenna ja sulje**|Tallenna kentän määritys ja sulje lomakeikkuna.|
|**Tallenna ja luo uusi**|Tallenna kentän määritys ja luo uusi kenttä avaamalla uusi lomake.|


## <a name="edit-a-field"></a>Kentän muokkaaminen 

Valitse [kenttien tarkastelemisen](#view-fields) yhteydessä muokattava kenttä. Tietyt hallittuun ratkaisuun sisältyvät vakiokentät tai mukautetut kentät eivät ehkä salli niiden muokkaamista.

> [!NOTE]
> Jos kenttä on jo lisätty lomakkeeseen, voit avata lomakkeen muokkaamisen yhteydessä **kentän ominaisuudet** kaksoisnapsauttamalla kenttää. Valitse **Tiedot**-välilehdessä **Muokkaa**. Lisätietoja: [Kentän lisääminen lomakkeeseen](../model-driven-apps/add-field-form.md)

Kun kenttää on muutettu, mukautukset on julkaistava. 

- Jos haluat julkaista yhden entiteetin muutokset, valitse **Osat**-kohdassa **Entiteetit** ja valitse sitten muutettu entiteetti. Valitse **Toiminnot**-työkalurivillä **Julkaise**.  
  
- Jos haluat julkaista kaikki useisiin entiteetteihin tai osiin tehdyt muutokset, valitse **Toiminnot**-työkalurivillä **Julkaise kaikki mukautukset**.  
  
> [!NOTE]
>  Ratkaisun asentaminen tai mukautusten julkaiseminen saattaa häiritä järjestelmän normaalikäyttöä. Julkaisun julkaiseminen kannattaa ajoittaa siten, että häiritsee mahdollisimman vähän käyttäjien toimintaa.  

### <a name="edit-multiple-fields"></a>Useiden kenttien muokkaaminen

Jos haluat muokata kenttiä, valitse ensin muokattavat kentät (Vaihto-näppäimellä) ja valitse sitten **Toiminnot**-työkalurivillä **Muokkaa**. 
  
Kun valitset muokattavaksi useita kenttiä, **Muokkaa useita kenttiä** -valintaikkuna avautuu. Voit muokata **Kenttävaatimus**-, **Haettavissa**- ja **Seuranta**-asetuksia. 

## <a name="delete-a-field"></a>Kentän poistaminen

Käyttäjä, jolla on järjestelmänvalvojan käyttöoikeusrooli, voi poistaa minkä tahansa mukautetun kentän, joka ei sisälly hallittuun ratkaisuun. Kun kenttä poistetaan, kaikki kenttään tallennetut tiedot menetetään. Poistetun kentät tiedot voidaan palauttaa vain palauttamalla tietokanta hetkeen ennen kentän poistamista.

> [!NOTE]
> Ennen mukautetun kentän poistamista sinun on poistettava muissa ratkaisun osissa mahdollisesti olevat riippuvuudet. 

1. Valitse [kenttien tarkastelemisen](#view-fields) yhteydessä mukautettu kenttä, joka voidaan poistaa luettelosta, ja valitse sitten komentopalkissa ![Poista komento](../model-driven-apps/media/delete.gif) -painike.
2. Valitse **Vahvista poistaminen** -valintaikkunassa **Poista**.

> [!TIP]
> Voit valita useita mukautettuja kenttiä, jotka poistetaan yhden toiminnon aikana.

### <a name="check-field-dependencies"></a>Kentän riippuvuuksien tarkistaminen 

Valitse kenttä luettelosta. Valitse **Lisää toimintoja** -valikosta **Näytä riippuvuudet**.

![Kentän riippuvuuksien näyttäminen](media/check-field-dependencies.png)

Riippuvuudet tarkoittavat mitä tahansa kenttään liittyvää käyttöä, joka estää kentän poistamisen. Jos kenttää esimerkiksi käytetään lomakkeessa tai näkymässä, sinun on poistettava ensin viittaukset kenttään kyseisissä ratkaisun osissa.  
  
Jos poistat valintakentän, sen 1:N-entiteettisuhde poistetaan automaattisesti.  

## <a name="ime-mode"></a>IME-tila

Kaikissa kentissä, joihin voi kirjoittaa suoraan tekstiä, on IME-tila. IME-editoria käytetään itäaasialaisissa kielissä, kuten japanissa. IME-editorien avulla käyttäjä voi syöttää tuhansia itäaasialaisissa kirjoitetuissa kielissä käytettyjä merkkejä tavallisella 101-näppäimisellä näppäimistöllä.


### <a name="see-also"></a>Katso myös  
[Kenttien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa](create-edit-fields.md)<br />
[Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-portaalin avulla](create-edit-field-portal.md)<br />
[Kenttien tyypit ja kentän tietojen tyypit](types-of-fields.md)<br />
[Voit automatisoida manuaalisen laskennan laskettujen kenttien määrittämiseen](define-calculated-fields.md)<br />
[Määritä koontikenttiä, jotka kokoavat arvoja](define-rollup-fields.md)<br />
[Päivämäärän ja kellonajan kentän toimintatapa ja muoto](behavior-format-date-time-field.md)

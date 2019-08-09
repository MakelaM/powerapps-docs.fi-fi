---
title: Entiteettisuhteiden yleiskatsaus kohteelle Common Data Service | MicrosoftDocs
ms.custom: ''
ms.date: 04/25/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: c765b6d9-4d87-4c2d-aae2-5b1c3b664a71
caps.latest.revision: 28
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="entity-relationships-overview"></a>Entiteettisuhteiden yleiskatsaus
Entiteettien väliset suhteet määrittävät, kuinka tietueita voidaan liittää toisiinsa tietokannassa. Yksinkertaisimmalla tasolla valintakentän lisääminen entiteetille luo uuden 1:N (Yhdestä Useampaan) -suhteen kahden entiteetin välille ja mahdollistaa kentän laittamisen lomakkeelle. Valintakentän avulla käyttäjät voivat liittää useita entiteetin *alitietueita* yhdeksi *pääentiteettitietueeksi*.  
  
Sen lisäksi, että ne määrittävät miten tietueet liittyvät toisiinsa, 1:N-entiteettisuhteet tarjoavat tietoja, jotka vastaavat seuraaviin kysymyksiin:  
  
- Kun tietue poistetaan, pitääkö siihen liittyvät tietueet myös poistaa?  
- Kun tietue delegoidaan, pitääkö kaikki tietueeseen liittyvät tiedot myös delegoida uudelle omistajalle?  
- Miten voin virtaviivaistaa tietojen syöttämistä kun luon uuden, jo olemassa olevaan tietueeseen liittyvän tietueen?  
- Miten tietueita tarkastelevat käyttäjät saavat tarkastella liittyviä tietueita?  
  
 Entiteetit voivat olla osana myös N:N (Monta Moneen) -suhdetta, jossa kahden entiteetin tietueiden täysi määrä voidaan liittää toisiinsa.  

<a name="BKMK_Connections"></a>

## <a name="decide-whether-to-use-entity-relationships-or-connections"></a>Entiteettisuhteiden vai -liitosten valinnan arviointi 
Entiteettisuhteet ovat metatietoa, joka tekee muutoksia tietokantaan. Nämä suhteet mahdollistavat tehokkaan tiedonhaun. Entiteettisuhteiden avulla voit määrittää muodollisia suhteita, jotka määrittävät entiteetin, tai joita useimmat tietueet voivat käyttää. Esimerkiksi mahdollisuus ilman potentiaalista asiakasta ei olisi hyödyllinen. Mahdollisuus-entiteetillä on myös N:N-suhde Kilpailija-entiteetin kanssa. Tämä mahdollistaa useamman kilpailijan lisäämisen mahdollisuuteen. Voit halutessasi siepata nämä tiedot ja luoda raportin, joka sisältää kilpailijat.  
  
Toisenlaisia, vähemmän muodollisia suhteita tietueiden välillä kutsutaan *liitoksiksi*. Esimerkiksi voi olla hyödyllistä tietää, jos kaksi yhteyshenkilöä ovat naimisissa, tai ehkä ystäviä työn ulkopuolella, tai ehkä yhteystieto on tehnyt töitä toisen asiakkaan kanssa. Useimmat yritykset eivät luo raportteja tämän tyyppisistä tiedoista tai edes vaadi niiden syöttämistä, joten ei todennäköisesti kannata luoda niille entiteettisuhteita. Lisätietoja: [Liitosroolien määrittäminen](configure-connection-roles.md)

  
<a name="BKMK_TypesOfRelationships"></a>
 
## <a name="types-of-entity-relationships"></a>Entiteettisuhteiden tyypit
Tarkasteltaessa ratkaisuhallintaa saattaa luulla, että entiteettisuhteita on kolmenlaisia. Niitä on tosiasiassa vain kaksi, kuten seuraavassa taulukossa esitetään.  
  
|Suhteen tyyppi|Kuvaus|  
|-----------------------|-----------------|  
|**1:N (Yksi Moneen)**|Entiteettisuhde, jossa yksi **ensisijaisen entiteetin** tietue voidaan liittää moneen muun **liittyvän entiteettin** tietueeseen liittyvällä entiteetillä olevan valintakentän vuoksi.<br /><br /> Ensisijaisen entiteetin tietuetta tarkastellessa näytetään luettelo siihen liitetyistä liittyvien entiteettien tietueista.|  
|**N:N (Monta Moneen)**|Entiteettisuhde, joka riippuu erikoisesta **suhde-entiteetistä**, joka mahdollistaa yhden entiteetin tietueiden liittämisen toisen entiteetin tietueisiin. Tällaista entiteettiä kutsutaan myös intersect-entiteetiksi.<br /><br /> Kun tarkastelet kumman tahansa N:N-suhteisen entiteetin tietueita, saat luettelon kaikista siihen liittyvistä toisen entiteetin tietueista.|  
  
**N:1 (Monta Yhteen)** -suhteen tyyppi esitellään käyttöliittymässä, koska suunnitteluohjelmassa näkyy näkymä entiteettien perusteella ryhmiteltynä. 1:N-suhteet ovat tosiasiallisesti entiteettien *välisiä* ja viittaavat kumpaankin joko **ensisijaisena entiteettinä** tai **liittyvänä entiteettinä**. Liittyvällä entiteetillä, jota voidaan myös kutsua *alientiteetiksi*, on valintakenttä, jolla on mahdollista tallentaa viite ensisijaisen entiteetin tietueeseen. Ensisijaista entiteettiä voidaan kutsua myös *pääentiteetiksi*. N:1-suhde on vain 1:N-suhde, jota tarkastellaan liittyvän entiteetin näkökulmasta.  
 
## <a name="entity-relationship-behavior"></a>Entiteettisuhteen käyttäytyminen
Liittyvien entiteettien käyttäytymistiedot ovat tärkeitä, koska niiden avulla varmistetaan tietojen yhtenäisyys. Tietojen avulla voi myös automatisoida yrityksen liiketoimintaprosesseja.

### <a name="preserve-data-integrity"></a>Tietojen yhtenäisyyden säilyttäminen
Joidenkin entiteettien tarkoitus on vain tukea muita entiteettejä. Niillä ei ole itsenäistä merkitystä. Niissä on yleensä pakollinen valintakentän, joka muodostaa linkin tuettavaan ensisijaiseen entiteettiin. Mitä tapahtuu, kun ensisijainen tietue poistetaan?

Voit määrittää tämän liiketoimintasääntöjen mukaisesti suhteen käyttäytymisen avulla. Käytössä on kaksivaihtoehtoa:

- Estä ensisijaisen entiteetin poistaminen, jotta liittyvät entiteettitietueet voidaan täsmäyttää esimerkiksi liittämällä ne toiseen ensisijaiseen entiteettiin.
- Salli liittyvien entiteettien automaattinen poistaminen ensisijaisen entiteettitietueen poiston yhteydessä.

Jos liittyvä entiteetti ei tue ensisijaista entiteettiä, voit sallia ensisijaisen entiteetin poistamisen, jolloin hakukentän arvo tyhjennetään.

### <a name="automate-business-processes"></a>Liiketoimintaprosessien automatisointi
Oletetaan, että sinulla on uusi myyjä ja haluat delegoida hänelle osan toiselle myyjälle delegoiduista asiakkaista. Kullakin asiakastietueella voi olla useita tehtäväaktiviteetteja. Uudelleendelegoitavat aktiiviset asiakkaat on helppo löytää ja delegoida uudelle myyjälle. Mutta mitä tapahtuu asiakkaisiin liitetyille tehtäväaktiviteeteille? Haluatko avata kunkin tehtävän ja päättää, delegoidaanko nekin uudelle myyjälle? Luultavasti et. Sen sijaan voit antaa suhteen soveltaa automaattisesti vakiosääntöjä. Näitä sääntöjä sovelletaan vain uudelleendelegoitavien asiakkaiden tehtävätietueisiin. Vaihtoehtosi ovat:  
  
- Uudelleendelegoi kaikki aktiiviset tehtävät.  
- Uudelleendelegoi kaikki tehtävät. 
- Älä uudelleendelegoi tehtäviä.  
- Uudelleendelegoi kaikki tehtävät, jotka on delegoitu asiakkaiden edelliselle omistajalle.  
  
Suhde voi ohjata, kuinka ensisijaisen entiteetin tietueelle suoritetut toiminnot laskeutuvat liitetyn entiteetin tietueille.  

### <a name="behaviors"></a>Toimintatavat
Useita erilaisia toimintatapoja voidaan ottaa käyttöön tiettyjen toimintojen yhteydessä.

|Toimintatapa|Kuvaus|
|--|--|
|**Limittäisyys**|Suorita toiminto kaikille aktiivisen liittyvän entiteetin tietueille.|
|**Kaikki limittäin**|Suorita toiminto kaikille liittyvän entiteetin tietueille.|
|**Ei mitään limittäin**|Älä tee mitään.|
|**Poista linkki**|Poista kaikkien liittyvien tietueiden hakuarvo.|
|**Rajoita**|Estä ensisijaisen entiteetin tietueiden poistaminen, kun niillä on liittyviä entiteettitietueita.|
|**Käyttäjän limittäin**|Suorita toiminto kaikille liittyville entiteetin tietueille, joilla on sama omistaja kuin pääentiteetin tietueella.|

### <a name="actions"></a>Toiminnot
Seuraavat toiminnot voivat käynnistää tiettyjä toimintatapoja:

|Kenttä|Kuvaus|Asetukset|
|--|--|--|
|**Delegoi**|Mitä tapahtuu, kun ensisijainen entiteettitietue delegoidaan jollekin toiselle?|Kaikki limittäin<br />Limittäisyys<br />Käyttäjän omistamien limittäminen<br />Ei mitään limittäin|
|**Määritä ylätaso uudelleen**|Mitä tapahtuu, kun ylätason suhteen liittyvän entiteetin hakuarvoa muutetaan?<br />Lisätietoja: [Ylätason entiteettisuhteet](#parental-entity-relationships)|Kaikki limittäin<br />Limittäisyys<br />Käyttäjän omistamien limittäminen<br />Ei mitään limittäin|
|**Jaa**|Mitä tapahtuu, kun ensisijaisen entiteetin tietue jaetaan?|Kaikki limittäin<br />Limittäisyys<br />Käyttäjän omistamien limittäminen<br />Ei mitään limittäin|
|**Poista**|Mitä tapahtuu, kun ensisijainen entiteettitietue poistetaan?|Kaikki limittäin<br />Poista linkki<br />Rajoita|
|**Poista jako**|Mitä tapahtuu, kun ensisijaisen entiteettitietueen jako poistetaan?|Kaikki limittäin<br />Limittäisyys<br />Käyttäjän omistamien limittäminen<br />Ei mitään limittäin|
|**Yhdistäminen**|Mitä tapahtuu, kun ensisijainen entiteettitietue yhdistetään?|Kaikki limittäin<br />Ei mitään limittäin|
|**Koostenäkymä**|Mikä on tähän suhteeseen liitetyn koostenäkymän haluttu toimintatapa? |Kaikki limittäin<br />Limittäisyys<br />Käyttäjän omistamien limittäminen<br />Ei mitään limittäin|


### <a name="parental-entity-relationships"></a>Ylätason entiteettisuhteet
Jokaisella entiteettiparilla, jolla voi olla 1:N-suhde, voi olla useita 1:N-suhteita entiteettien välillä. Yleensä kuitenkin vain yhtä näistä suhteista pidetään ylätason entiteettisuhteena.

Ylätason entiteettisuhde on mikä tahansa 1:N-entiteettisuhde, jossa seuraavan taulukon **ylätason** sarakkeen yhden limittäisyysasetuksen arvo on tosi.

|Toiminto|Ylätaso|Ei ylätasoa|  
|------------|--------------|------------------|  
|**Delegoi**|Kaikki limittäin<br />Käyttäjän omistamien limittäminen<br />Limittäisyys|Ei mitään limittäin|  
|**Poista**|Kaikki limittäin|Poista linkki<br />Rajoita|  
|**Määritä ylätaso uudelleen**|Kaikki limittäin<br />Käyttäjän omistamien limittäminen<br />Limittäisyys|Ei mitään limittäin|  
|**Jaa**|Kaikki limittäin<br />Käyttäjän omistamien limittäminen<br />Limittäisyys|Ei mitään limittäin|  
|**Poista jako**|Kaikki limittäin<br />Käyttäjän omistamien limittäminen<br />Limittäisyys|Ei mitään limittäin|  

Jos luot esimerkiksi uuden mukautetun entiteetin ja lisäät 1:N-entiteettisuhteen ja asiakkaan entiteetin, jossa mukautettu entiteetti on liittyvä entiteetti, voit määrittää kyseisen entiteettisuhteen toiminnot niin, että ne käyttävät **Ylätaso**-sarakkeen asetuksia. Jos lisäät myöhemmin toisen 1:N-entiteettisuhteen niin, että mukautettu entiteetti on viittaava entiteetti, voit määrittää toiminnot vain **Ei ylätasoa** -sarakkeen asetusten käyttöä varten.

Yleensä tämä tarkoittaa sitä, että jokaisella entiteettiparilla on vain yksi ylätason suhde. Joissakin tapauksissa liittyvän entiteetin haku voi sallia suhteelle useita entiteettityyppejä.

Entiteetillä voi esimerkiksi olla Asiakas-haku, joka voi viitata joko yhteyshenkilö- tai asiakasentiteettiin. Käytettävissä on kaksi erilaista ylätason 1:N-entiteettisuhdetta.

Aktiviteettientiteetillä on samanlainen entiteettien ylätason entiteettisuhteiden joukko, joka voidaan liittää Liittyy-hakukentän avulla.

<a name="BKMK_RelationshipBehaviorLimitations"></a>   

### <a name="limitations-on-behaviors-you-can-set"></a>Rajoituksia asetettaviin toimintatapoihin
Ylätason suhteiden vuoksi entiteettisuhteiden määrittämisessä on tiettyjä rajoituksia, jotka on hyvä pitää mielessä.  
  
- Mukautettu entiteetti ei voi olla ensisijainen entiteetti sellaisessa suhteessa, jossa on siihen liittyvä limittäinen järjestelmäentiteetti. Tämän vuoksi ensisijaisen, mukautetun entiteetin ja siihen liittyvän järjestelmäentiteetin välillä ei voi olla suhdetta, jossa jokin toiminnon määritys on **Kaikki limittäin**, **Limittäin aktiivinen** tai **Käyttäjän limittäin**.  
- Uuden suhteen toimintojen määritys ei voi olla **Kaikki limittäin** eikä **Limittäin aktiivinen** tai **Käyttäjän limittäin**, jos suhteen liittyvä entiteetti on jo liittyvänä entiteettinä jossakin toisessa suhteessa, jonka toimintojen määritys on **Kaikki limittäin**, **Limittäin aktiivinen** tai **Käyttäjän limittäin**. Näin vältetään sellaisten suhteiden muodostuminen, joissa on monta ylätasoa.  

### <a name="see-also"></a>Katso myös
[Yksiköt/metatiedot yleiskatsaus](create-edit-metadata.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -suhteen luominen ja muokkaaminen](create-edit-1n-relationships.md)<br />
[Monta moneen (N:N) -entiteettisuhteiden luominen](create-edit-nn-relationships.md)


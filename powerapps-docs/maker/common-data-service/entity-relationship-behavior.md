---
redirect_url: 'create-edit-entity-relationships#entity-relationship-behavior'
title: Entiteetin suhteen toiminta (Common Data Service) | Microsoft-dokumentit
description: <Description>
ms.custom: ''
ms.date: 08/01/2018
ms.reviewer: ''
ms.service: powerapps
ms.topic: article
author: Mattp123
ms.author: matp
manager: kvivek
---
# <a name="entity-relationship-behavior"></a>Entiteettisuhteen käyttäytyminen

Liittyvien entiteettien käyttäytymistiedot ovat tärkeitä, koska niiden avulla varmistetaan tietojen yhtenäisyys. Tietojen avulla voi myös automatisoida yrityksen liiketoimintaprosesseja.

## <a name="preserve-data-integrity"></a>Tietojen yhtenäisyyden säilyttäminen

Joidenkin entiteettien tarkoitus on vain tukea muita entiteettejä. Niillä ei ole itsenäistä merkitystä. Niissä on yleensä pakollinen valintakentän, joka muodostaa linkin tuettavaan ensisijaiseen entiteettiin. Mitä tapahtuu, kun ensisijainen tietue poistetaan?

Voit määrittää tämän liiketoimintasääntöjen mukaisesti suhteen käyttäytymisen avulla. Käytössä on kaksivaihtoehtoa:

- Estä ensisijaisen entiteetin poistaminen, jotta liittyvät entiteettitietueet voidaan täsmäyttää esimerkiksi liittämällä ne toiseen ensisijaiseen entiteettiin.
- Salli liittyvien entiteettien automaattinen poistaminen ensisijaisen entiteettitietueen poiston yhteydessä.

Jos liittyvä entiteetti ei tue ensisijaista entiteettiä, voit sallia ensisijaisen entiteetin poistamisen, jolloin hakukentän arvo tyhjennetään.

## <a name="automate-business-processes"></a>Liiketoimintaprosessien automatisointi
  
Oletetaan, että sinulla on uusi myyjä ja haluat delegoida hänelle osan toiselle myyjälle delegoiduista asiakkaista. Kullakin asiakastietueella voi olla useita tehtäväaktiviteetteja. Uudelleendelegoitavat aktiiviset asiakkaat on helppo löytää ja delegoida uudelle myyjälle. Mutta mitä tapahtuu asiakkaisiin liitetyille tehtäväaktiviteeteille? Haluatko avata kunkin tehtävän ja päättää, delegoidaanko nekin uudelle myyjälle? Luultavasti et. Sen sijaan voit antaa suhteen soveltaa automaattisesti vakiosääntöjä. Näitä sääntöjä sovelletaan vain uudelleendelegoitavien asiakkaiden tehtävätietueisiin. Vaihtoehtosi ovat:  
  
- Uudelleendelegoi kaikki aktiiviset tehtävät.  
- Uudelleendelegoi kaikki tehtävät. 
- Älä uudelleendelegoi tehtäviä.  
- Uudelleendelegoi kaikki tehtävät, jotka on delegoitu asiakkaiden edelliselle omistajalle.  
  
Suhde voi ohjata, kuinka ensisijaisen entiteetin tietueelle suoritetut toiminnot laskeutuvat liitetyn entiteetin tietueille.  

## <a name="behaviors"></a>Toimintatavat

Useita erilaisia toimintatapoja voidaan ottaa käyttöön tiettyjen toimintojen yhteydessä.

|Toimintatapa|Kuvaus|
|--|--|
|**Limittäisyys**|Suorita toiminto kaikille aktiivisen liittyvän entiteetin tietueille.|
|**Kaikki limittäin**|Suorita toiminto kaikille liittyvän entiteetin tietueille.|
|**Ei mitään limittäin**|Älä tee mitään.|
|**Poista linkki**|Poista kaikkien liittyvien tietueiden hakuarvo.|
|**Rajoita**|Estä ensisijaisen entiteetin tietueiden poistaminen, kun niillä on liittyviä entiteettitietueita.|
|**Käyttäjän limittäin**|Suorita toiminto kaikille liittyville entiteetin tietueille, joilla on sama omistaja kuin pääentiteetin tietueella.|

## <a name="actions"></a>Toiminnot

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


## <a name="parental-entity-relationships"></a>Ylätason entiteettisuhteet

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

## <a name="limitations-on-behaviors-you-can-set"></a>Rajoituksia asetettaviin toimintatapoihin
  
Ylätason suhteiden vuoksi entiteettisuhteiden määrittämisessä on tiettyjä rajoituksia, jotka on hyvä pitää mielessä.  
  
- Mukautettu entiteetti ei voi olla ensisijainen entiteetti sellaisessa suhteessa, jossa on siihen liittyvä limittäinen järjestelmäentiteetti. Tämän vuoksi ensisijaisen, mukautetun entiteetin ja siihen liittyvän järjestelmäentiteetin välillä ei voi olla suhdetta, jossa jokin toiminnon määritys on **Kaikki limittäin**, **Limittäin aktiivinen** tai **Käyttäjän limittäin**.  
- Uuden suhteen toimintojen määritys ei voi olla **Kaikki limittäin** eikä **Limittäin aktiivinen** tai **Käyttäjän limittäin**, jos suhteen liittyvä entiteetti on jo liittyvänä entiteettinä jossakin toisessa suhteessa, jonka toimintojen määritys on **Kaikki limittäin**, **Limittäin aktiivinen** tai **Käyttäjän limittäin**. Näin vältetään sellaisten suhteiden muodostuminen, joissa on monta ylätasoa.  

---
title: Viitetietueiden vaihtoehtoisten avainten määrittäminen Common Data Servicessä | MicrosoftDocs
description: Tietoja tietueisiin viittaavien vaihtoehtoisten avainten määrittämisestä Common Data Servicessä
ms.custom: ''
ms.date: 06/06/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 29e53691-0b18-4fde-a1d0-7490aa227898
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-alternate-keys-to-reference-records"></a>Tietueisiin viittaavien vaihtoehtoisten avainten määrittäminen

*Vaihtoehtoiset avaimet* mahdollistavat tietojen tehokkaan ja täsmällisen integroinnin ulkoisista järjestelmistä. Jos ulkoinen järjestelmä ei tallenna GUID-tunnuksia, on tärkeää yksilöidä tietueet Common Data Servicessä. 

Tietojen integrointijärjestelmä yksilöi tietueet vaihtoehtoisten avainten avulla yhdessä tai useassa entiteettikentän arvossa, joka edustaa yksilöivää yhdistelmää. Jokaisella vaihtoehtoisella avaimella on yksilöllinen nimi. 

Jos haluat yksilöidä esimerkiksi tilitietueen vaihtoehtoisen avaimen avulla, voit käyttää tilinumeroa tai tilinumerokenttää yhdessä joidenkin muiden sellaisten kenttien kanssa, joiden arvoja ei voi muuttaa.

> [!NOTE]
> Vaikka voit määrittää vaihtoehtoisia avaimia PowerAppsin avulla, niitä voi käyttää vain ohjelmoidusti koodissa. Lisätietoja vaihtoehtoisten avainten käyttämisestä ohjelmoidusti on kohdassa:   
> - [Sovelluskehittäjän dokumentaatio: Tietueen luominen vaihtoehtoisen avaimen avulla](/dynamics365/customer-engagement/developer/use-alternate-key-create-record) 
> - [Sovelluskehittäjän dokumentaatio: Tietueen ja Web -ohjelmointirajapinnan hakeminen vaihtoehtoisen avaimen avulla](/dynamics365/customer-engagement/developer/webapi/retrieve-entity-using-web-api#retrieve-using-an-alternate-key)

Seuraavassa kerrotaan joitakin vaihtoehtoisten avainten ominaisuuksien käyttämisestä saatavia hyötyjä:  
  
- Tietueiden haku nopeutuu.  
- Tietojen joukkotoiminnot tehostuvat.  
- Ohjelmointi yksinkertaistuu, kun ulkoisista järjestelmistä tuodaan tietoja ilman tietueiden tunnuksia.  
  

## <a name="creating-an-alternate-key"></a>Vaihtoehtoisen avaimen luominen

Vaihtoehtoisia avaimia voi luoda kahden suunnitteluohjelman avulla:

|Suunnittelija| Kuvaus|
|--|--|
|[PowerApps-portaali](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Tarjoaa helpon ja nopean käyttökokemuksen, mutta jotkin asetukset eivät ole käytettävissä.<br />Lisätietoja: [Vaihtoehtoisten avainten määrittäminen PowerApps-portaalin avulla](define-alternate-keys-portal.md)|
|Ratkaisunhallinta|Tämä ei ole niin helppo tapa, mutta tarjoaa enemmän joustavuutta vähemmän yleisille vaatimuksille.<br />Lisätietoja: [Vaihtoehtoisten avainten määrittäminen ratkaisunhallinnan avulla](define-alternate-keys-solution-explorer.md) |

> [!NOTE]
> Voit luoda vaihtoehtoisia avaimia ympäristössä myös seuraavasti:
> - Tuo ratkaisu, joka sisältää vaihtoehtoisen avaimen määrityksen.
> - Sovelluskehittäjä voi myös luoda niitä kirjoittamalla koodia. Lisätietoja: [Sovelluskehittäjän dokumentaatio: Entiteetin vaihtoehtoisten avainten määrittäminen](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)

Tämän ohjeaiheen tietojen avulla voit valita käytettävän suunnitteluohjelman. 

Luo vaihtoehtoisia avaimia [PowerApps-portaalin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) avulla, jos seuraavia vaatimuksia ei tarvitse ottaa huomioon:

- Luo vaihtoehtoinen avain ratkaisussa, joka on jokin muu kuin Common Data Servicen oletusratkaisu.
- Seuraa helposti luotua järjestelmätyötä, joka seuraa tuki-indeksien luomisen edistymistä


## <a name="limits-in-creating-alternate-keys"></a>Rajoittaa vaihtoehtoisten avainten luomista

Vaihtoehtoisten avainten luonnissa on rajoituksia.

### <a name="fields-that-can-be-used-for-alternate-keys"></a>Vaihtoehtoisissa kentissä käytettävät kentät

Vain näitä kenttiä voi käyttää vaihtoehtoisten kenttien luomisessa:
 - Desimaali
 - Kokonaisluku (kokonaisluku)
 - Yksi tekstirivi (merkkijono)

### <a name="number-of-keys"></a>Avainten määrä

Voit määrittää entiteetille enintään viisi erilaista avainta.
 
### <a name="valid-key-size"></a>Sallittu avaimen koko

Kun avain on luotu, järjestelmä varmistaa, että ympäristö voi tukea avainta ja sen, että avaimen kokonaiskoko ei riko SQL:ään perustuvan indeksin rajoituksia, kuten 900 tavua per avain ja 16 saraketta per avain. Jos avaimen koko ei vastaa rajoituksia, näyttöön tulee virhesanoma.

### <a name="unicode-characters-in-key-value"></a>Unicode-merkit avaimen arvossa

Jos vaihtoehtoisessa avaimessa käytettävät kentän tiedot noudattavat seuraavia merkkejä, korjaustiedostot tai upsert-toiminnot eivät toimi: `<`,`>`,`*`,`%`,`&`,`:`,`/`,`\\`. 

Jos tarvitaan vain yksilöllisyyttä, tämä tapa toimii, mutta jos näitä avaimia on käytettävä tietojen integroinnin osana, avain on paras luoda kentille, joilla ei ole näitä merkkejä sisältäviä tietoja.

## <a name="track-the-status-of-the-creation-of-the-alternate-key"></a>Vaihtoehtoisen avaimen luomisen tilan seuranta

Kun vaihtoehtoinen avain luodaan, se käynnistää järjestelmätyön, joka luo tietokantatauluille indeksit. Indeksit ottavat käyttöön vaihtoehtoisten avainten käyttämissä kentissä yksilölliset rajoitukset. Vaihtoehtoinen avain on käytössä vasta, kun nämä indeksit on luotu. Näiden indeksien luominen voi kestää jonkin aikaa. Tämä riippuu järjestelmässä olevien tietojen määrästä. 

Järjestelmätyön tila määrittää vaihtoehtoisen avaimen tilan. Vaihtoehtoisella avaimella voi olla seuraavat tilat:
- **Odottaa**
- **Kesken**
- **Aktiivinen**
- **Epäonnistunut**

Kun järjestelmätyö on valmis, vaihtoehtoisen avaimen tila on **Aktiivinen** ja se on valmis käytettäväksi.

Jos järjestelmätyö epäonnistuu, etsi järjestelmätyö ja tarkastele virheitä. Järjestelmätyöllä on nimi, jonka muoto on seuraava: `Create index for {0} for entity {1}`, jossa `0` on vaihtoehtoisen avaimen **näyttönimi** ja `1` entiteetin nimi.


> [!NOTE]
> Jos haluat seurata järjestelmätyön tilaa, luo indeksi ratkaisunhallinnan avulla. Se sisältää linkin järjestelmätyöhön, joten voit seurata työtä. Lisätietoja: [(Valinnainen) Järjestelmätyön seurannan indeksien luonnin tarkasteleminen](define-alternate-keys-solution-explorer.md#optional-view-the-system-job-tracking-creation-of-indexes)
  
  
### <a name="see-also"></a>Katso myös  

[Vaihtoehtoisten avainten määrittäminen PowerApps-portaalin avulla](define-alternate-keys-portal.md)<br />
[Vaihtoehtoisten avainten määrittäminen ratkaisunhallinnan avulla](define-alternate-keys-solution-explorer.md)<br />
[Sovelluskehittäjän dokumentaatio: Entiteetin vaihtoehtoisten avainten määrittäminen](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)<br />
[Sovelluskehittäjän dokumentaatio: Tietueen luominen vaihtoehtoisen avaimen avulla](/dynamics365/customer-engagement/developer/use-alternate-key-create-record)

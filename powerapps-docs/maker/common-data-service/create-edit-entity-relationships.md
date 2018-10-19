---
title: Common Data Service sovelluksille -ratkaisun entiteettisuhteiden yleiskatsaus | MicrosoftDocs
ms.custom: ''
ms.date: 05/26/2018
ms.reviewer: ''
ms.service: crm-online
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
manager: brycho
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
 
## <a name="see-also"></a>Katso myös

[Yksiköt/metatiedot yleiskatsaus](create-edit-metadata.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -suhteen luominen ja muokkaaminen](create-edit-1n-relationships.md)<br />
[Monta moneen (N:N) -entiteettisuhteiden luominen](create-edit-nn-relationships.md)


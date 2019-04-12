---
title: Entiteettien tyypit | MicrosoftDocs
ms.custom: ''
ms.date: 05/30/2018
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
ms.assetid: 2f3f6053-0b9e-41e7-bd94-2239351e9f4b
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="types-of-entities"></a>Entiteettien tyypit

Ennen entiteettien luomista ja muokkaamista Common Data Servicessä on tiedettävä, että olemassa on erityyppisiä entiteettejä. Kun mukautettu entiteetti on luotu, näitä tyyppejä ei voi muuttaa. Kaksi tärkeintä divisioonaa perustuvat entiteetin omistukseen ja siihen, ovatko entiteetit aktiviteettientiteettejä.  
  
<a name="BKMK_EntityOwnership"></a>

## <a name="entity-ownership"></a>Entiteetin omistus  

Entiteetin omistuksella on neljä eri tyyppiä. Kun luot mukautetun entiteetin, ainoat vaihtoehdot ovat **käyttäjän tai ryhmän omistama** tai **organisaation omistama**. Muista, että muilla entiteeteillä on erilaisia omistustyyppejä.  
  
|Omistus|Kuvaus|  
|---------------|-----------------|  
|**Liiketoiminnan omistama**|Näiden entiteettien tiedot kuuluvat liiketoimintayksikölle. Tietojen käyttämistä voidaan hallita liiketoimintayksikön tasolla.|  
|**Ei mikään**|Tiedot, joita toinen entiteetti ei omista.|  
|**Organisaation omistama**|Tiedot kuuluvat organisaatiolle. Tietojen käyttämistä hallitaan organisaation tasolla.|  
|**Käyttäjän tai ryhmän omistama**|Tiedot kuuluvat käyttäjälle tai ryhmälle. Näille tietueille suoritettavia toimintoja voidaan hallita käyttäjän tasolla.|  
  
  
> [!IMPORTANT]
>  Omistusta ei voi muuttaa entiteetin luonnin jälkeen. Varmista ennen entiteetin luontia, että olet valinnut oikean omistustyypin. Jos huomaat myöhemmin, että mukautetun entiteetin tyyppiä on muutettava, entiteetti on poistettava ja sen tilalle on luotava uusi entiteetti.
  
<a name="BKMK_ActivityEntities"></a>

## <a name="activity-entities"></a>Aktiviteettientiteetit

Aktiviteetin voidaan ajatella olevan mikä tahansa toiminto, jolle voidaan tehdä merkintä kalenteriin. Aktiviteetillä on aikadimensiot (alkamisaika, päättymisaika, määräpäivä ja kesto), joiden avulla toiminnon suoritusajankohta voidaan määrittää. Aktiviteetit sisältävät myös tietoja, joiden avulla voidaan määrittää aktiviteetin edustama toiminto, esimerkiksi aihe tai kuvaus. Aktiviteetti voidaan avata, peruuttaa tai suorittaa valmiiksi. Aktiviteetin Valmis-tilalla on useita alitilan arvoja. Näiden avulla voidaan määrittää, miten aktiviteetti suoritettiin valmiiksi.  
  
Aktiviteettientiteetin omistaja voi olla vain käyttäjä tai ryhmä. Organisaatio ei voi omistaa aktiviteettientiteettiä.  
  
Seuraavassa taulukossa on Common Data Service -oletusympäristön käytettävissä olevien aktiviteettientiteettien luettelo.
  
|Nimi|Kuvaus|Näytä aktiviteettivalikoissa|Viite|
|----------|-----------------|----------------|---------------|  
|**Tapaaminen**|Sitoutuminen, jolle on määritetty aikaväli aloitus- ja päättymisaikoineen sekä kestoineen.|Kyllä|[Tapaaminen](/powerapps/developer/common-data-service/reference/entities/appointment)|
|**Sähköposti**|Sähköpostiprotokollia käyttämällä toimitettava aktiviteetti.|Kyllä|[Sähköposti ](/powerapps/developer/common-data-service/reference/entities/email)|
|**Faksi**|Aktiviteetti, joka seuraa puhelun tulosta ja faksin sivumäärää sekä tallentaa haluttaessa tiedostosta sähköisen kopion.|Kyllä|[Faksi](/powerapps/developer/common-data-service/reference/entities/fax)|
|**Kirje**|Kirjeen toimittamista seuraava aktiviteetti. Aktiviteetti voi sisältää kirjeen sähköisen kopion.|Kyllä|[Kirje](/powerapps/developer/common-data-service/reference/entities/letter)|
|**Phone Call**|Aktiviteetti, jolla seurataan puhelua.|Kyllä|[PhoneCall ](/powerapps/developer/common-data-service/reference/entities/phonecall)|
|**Toistuva tapaaminen**|Toistuvien tapaamisten sarjan pääkohde.|Kyllä|[RecurringAppointmentMaster](/powerapps/developer/common-data-service/reference/entities/recurringappointmentmaster)|
|**Tehtävä**|Yleinen aktiviteetti, joka tarkoittaa tehtävää työtä.|Kyllä|[Tehtävä](/powerapps/developer/common-data-service/reference/entities/task)|
  
Voit luoda uusia mukautettuja aktiviteettientiteettejä. Voit esimerkiksi luoda mukautetun aktiviteettientiteetin pikaviestien tallentamista varten. Aktiviteettientiteetin luominen on erilaista kuin muun kuin aktiviteettientiteetin luominen, koska ensisijaista kenttää ei määritetä. Kaikkien aktiviteettientiteettien **Ensisijainen kenttä** -kohdan ja muiden aktiviteettientiteetin määrittämien yleisten kenttien arvoksi on määritetty **Aihe**. Tällöin kaiken tyyppiset aktiviteetit ovat näkymässä, jossa näytetään vain yleiset kentät.  

> [!NOTE]
> Et voi luoda mukautettua aktiviteettia PowerApps-portaalin avulla. Avaa ratkaisunhallinta **Lisäasetukset**-painikkeen avulla.
  
Voit luoda mukautetun aktiviteettientiteetin valitsemalla **Määritä aktiviteettientiteetiksi**. Tämän jälkeen **Näytä aktiviteettivalikoissa** näkyy valittuna. Tämän asetuksen avulla voi luoda tämän tyyppisen aktiviteetin aktiviteettivalikoissa. Tätä ei valita aktiviteeteille, jotka liitetään yleensä tiettyihin tapahtumiin ja jotka on luotu koodin tai työnkulun avulla. Näitä asetuksia ei voi muuttaa entiteetin tallennuksen jälkeen.  

### <a name="see-also"></a>Katso myös
[Entiteettien luominen tai muokkaaminen](create-edit-entities.md)

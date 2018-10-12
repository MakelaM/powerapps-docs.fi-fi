---
title: Entiteettityypit | MicrosoftDocs
ms.custom: ''
ms.date: 05/30/2018
ms.reviewer: ''
ms.service: crm-online
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
ms.openlocfilehash: 60e16ff8cb5c40a37cf0a5243b420f77c4a695bb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681625"
---
# <a name="types-of-entities"></a>Entiteettityypit

Ennen kuin aloitat entiteettien luomisen tai muokkaamisen Common Data Service for Apps -palvelussa, sinun on syytä tuntea eri entiteettityypit. Kun luot mukautetun entiteetin, et voi enää vaihtaa sen tyyppiä. Kaksi merkittävää eroa perustuvat entiteetin omistajuuteen ja siihen, ovatko entiteetit aktiviteettientiteettejä.  
  
<a name="BKMK_EntityOwnership"></a>

## <a name="entity-ownership"></a>Entiteetin omistajuus  

Entiteeteillä on neljä eri omistajuustyyppiä. Kun luot mukautetun entiteetin, se voi olla vain **käyttäjän tai tiimin omistama** tai **organisaation omistama**. Muilla entiteeteillä on kuitenkin erilaisia omistajuustyyppejä.  
  
|Omistajuus|Kuvaus|  
|---------------|-----------------|  
|**Yrityksen omistama**|Näiden entiteettien tiedot kuuluvat liiketoimintayksikölle. Tietojen käyttöä voidaan hallita liiketoimintayksikön tasolla.|  
|**Ei mitään**|Toinen entiteetti ei omista tietoja.|  
|**Organisaation omistama**|Tiedot kuuluvat organisaatiolle. Tietojen käyttöä hallitaan organisaation tasolla.|  
|**Käyttäjän tai tiimin omistama**|Tiedot kuuluvat käyttäjälle tai tiimille. Näille tietueille suoritettavia toimintoja hallitaan käyttäjätasolla.|  
  
  
> [!IMPORTANT]
>  Kun entiteetti on luotu, sen omistajuutta ei voi enää muuttaa. Ennen kuin luot entiteetin, varmista, että valitset oikean omistajuustyypin. Jos myöhemmin päätät, että mukautetun entiteetin täytyy olla erityyppinen, sinun täytyy poistaa se ja luoda uusi.
  
<a name="BKMK_ActivityEntities"></a>

## <a name="activity-entities"></a>Aktiviteettientiteetit

Aktiviteetiksi voidaan katsoa tahansa toiminto, josta voidaan tehdä merkintä kalenteriin. Aktiviteetilla on aikadimensiot (alkamis- ja päättymisaika, määräpäivä ja kesto), joiden avulla määritetään, milloin toiminto tapahtui tai tapahtuu. Aktiviteetit sisältävät myös tietoja, joiden avulla määritetään, mitä toiminto edustaa. Tällaisia tietoja ovat esimerkiksi aihe ja kuvaus. Aktiviteetin voi avata, peruuttaa tai suorittaa. Aktiviteetin suoritustilalla on useita alatila-arvoja, joiden avulla voidaan selkeyttää tapaa, jolla aktiviteetti suoritettiin.  
  
Aktiviteettientiteettejä voivat omistaa vain käyttäjät ja tiimit, organisaatiot eivät voi omistaa niitä.  
  
Seuraavassa taulukossa luetellaan aktiviteettientiteetit, jotka ovat oletusarvoisesti käytettävissä CDS for Apps -ympäristössä.
  
|Nimi|Kuvaus|Näytetään aktiviteettivalikoissa|Viittaus|
|----------|-----------------|----------------|---------------|  
|**Tapaaminen**|Tämä on sitoumus, joka edustaa aikaväliä, jolle on määritetty alkamis- ja päättymisajat sekä kesto.|Kyllä|[Appointment](/powerapps/developer/common-data-service/reference/entities/appointment)|
|**Sähköposti**|Tämä on aktiviteetti, joka suoritetaan sähköpostiprotokollien välityksellä.|Kyllä|[Email ](/powerapps/developer/common-data-service/reference/entities/email)|
|**Faksi**|Tämä on aktiviteetti, joka seuraa faksin lopputulosta ja sivumäärää ja valinnaisesti tallentaa tiedoston sähköisen kopion.|Kyllä|[Fax](/powerapps/developer/common-data-service/reference/entities/fax)|
|**Kirje**|Tämä on aktiviteetti, joka seuraa kirjeen toimitusta perille. Aktiviteetti voi sisältää kirjeen sähköisen kopion.|Kyllä|[Letter](/powerapps/developer/common-data-service/reference/entities/letter)|
|**Puhelu**|Tämä aktiviteetti seuraa puhelua.|Kyllä|[PhoneCall ](/powerapps/developer/common-data-service/reference/entities/phonecall)|
|**Toistuva tapaaminen**|Tämä on toistuvien tapaamisten sarjan päätapaaminen.|Kyllä|[RecurringAppointmentMaster](/powerapps/developer/common-data-service/reference/entities/recurringappointmentmaster)|
|**Tehtävä**|Tämä on yleinen aktiviteetti, joka edustaa tehtäviä töitä.|Kyllä|[Task](/powerapps/developer/common-data-service/reference/entities/task)|
  
Voit luoda uusia mukautettuja aktiviteettientiteettejä. Voit esimerkiksi luoda mukautetun aktiviteettientiteetin, jolla tallennat pikaviestit. Aktiviteettientiteetin luominen eroaa muiden entiteettien luomisesta, koska et määritä ensisijaista kenttää. Kaikilla aktiviteeteilla on **ensisijainen kenttä**, jonka arvoksi on määritetty **Aihe**, sekä muita yleisiä kenttiä, jotka määritetään aktiviteettientiteetillä. Tämän ansiosta kaikentyyppiset aktiviteetit voidaan näyttää näkymässä, jossa näytetään vain yleiset kentät.  

> [!NOTE]
> Et voi luoda mukautettua aktiviteettia PowerApps-portaalissa. Sinun täytyy avata ratkaisunhallinta **lisäasetusten** painikkeella.
  
Jos haluat luoda mukautetun aktiviteettientiteetin, valitse **Määritä aktiviteettientiteetiksi**. Kun valitset tämän, **Näytä aktiviteettivalikoissa** on valittuna. Tämän asetuksen avulla ihmiset voivat luoda tällaisen aktiviteetin aktiviteettivalikoissa. Tämä ei ole valittuna aktiviteeteille, jotka on yleensä liitetty tiettyihin tapahtumiin ja jotka luodaan taustalla koodin tai työnkulun avulla. Kun tallennat entiteetin, et voi enää muokata näitä asetuksia.  

### <a name="see-also"></a>Katso myös
[Luo tai muokkaa entiteettejä](create-edit-entities.md)

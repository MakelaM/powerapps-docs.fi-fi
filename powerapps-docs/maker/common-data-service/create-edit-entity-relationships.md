---
title: Common Data Service for Appsin entiteettisuhteiden luominen ja muokkaaminen | MicrosoftDocs
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
ms.openlocfilehash: 896b026bc72022e66e548db95f78d785e14fdf23
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674592"
---
# <a name="create-and-edit-relationships-between-entities"></a>Entiteettien välisten suhteiden luominen ja muokkaaminen 

Entiteettiyhteydet määrittävät, miten tietueet voivat liittyä toisiinsa tietokannassa. Yksinkertaisimmalla tasolla hakukentän lisääminen entiteettiin luo uuden 1:N (yksi moneen) -suhteen kahden entiteetin välille, ja sen avulla voit sijoittaa kyseisen hakukentän lomakkeeseen. Hakukentän avulla käyttäjät voivat liittää kyseisen entiteetin useita *alitietueita* entiteetin yhteen *päätietueeseen*.  
  
Sen lisäksi, että 1:N-entiteettisuhteet määrittävät tietueiden suhteet toisiin tietueisiin, ne myös tarjoavat tiedot, joilla on mahdollista vastata seuraaviin kysymyksiin:  
  
- Kun poistan tietueen, tulisiko myös tähän tietueeseen mahdollisesti liittyvät muut tietueet poistaa?  
- Kun määritän tietueen uudelle omistajalle, onko määritettävä myös tähän tietueeseen liittyvät muut tietueet?  
- Miten voin tehostaa tietojen syöttämisen prosessia, kun luon uuden liittyvän tietueen olemassa olevan tietueen kontekstiin?  
- Miten tietuetta tarkastelevien pitäisi pystyä tarkastelemaan liittyviä tietueita?  
  
 Entiteetit voivat osallistua myös N:N (monta moneen) -suhteisiin, joissa kahden tietueen mikä tahansa määrä tietueita voi liittyä toisiinsa.  

<a name="BKMK_Connections"></a>

## <a name="decide-whether-to-use-entity-relationships-or-connections"></a>Entiteettien suhteiden ja yhteyksien valitseminen 
 
Entiteettien suhteet ovat metatietoa, joka tekee muutoksia tietokantaan. Suhteiden avulla kyselyt voivat noutaa liittyviä tietoja erittäin tehokkaasti. Entiteettien välisten suhteiden avulla voit määrittää muodolliset suhteet. Ne määrittävät entiteetit, joita useimmat tietueet voivat käyttää. Esimerkiksi mahdollisuus ilman potentiaalista asiakasta ei olisi kovin hyödyllinen. Mahdollisuusentiteetillä on myös N:N-suhde kilpailijaentiteetin kanssa. Näin mahdollisuuteen voi lisätä useita kilpailijoita. Nämä tiedot kannattaa taltioida ja luoda niistä raportti, joka näyttää kilpailijat.  
  
Käytettävissä on lisäksi vähemmän muodollisia tietueiden välisiä suhteita, joita kutsutaan *yhteyksiksi*. Saattaa olla esimerkiksi hyödyllistä tietää, jos kaksi yhteyshenkilöä ovat naimisissa tai ystäviä vapaa-ajalla. Ehkäpä yksi yhteyshenkilö on aiemmin työskennellyt toiselle asiakkaalle. Useimmat yritykset eivät luo raportteja käyttämällä tämän tyyppisiä tietoja tai edellytä tällaisten tietojen antamista, jolloin entiteettien välisiä suhteita ei välttämättä kannata luoda. Lisätietoja: [Yhteysroolien määrittäminen](configure-connection-roles.md)

  
<a name="BKMK_TypesOfRelationships"></a>
 
## <a name="types-of-entity-relationships"></a>Entiteettisuhteiden tyypit

Ratkaisunhallintaa tarkastelemalla saattaisi luulla, että entiteettisuhteita on kolmea eri tyyppiä. Itse asiassa niitä on vain kaksi, kuten seuraavassa taulukossa esitetään.  
  
|Suhteen tyyppi|Kuvaus|  
|-----------------------|-----------------|  
|**1:N (yksi moneen)**|Entiteettisuhde, jossa yksi **ensisijaisen entiteetin** entiteettitietue voidaan liittää useisiin muihin **liittyvän entiteetin** tietueisiin liittyvässä entiteetissä olevan hakukentän ansiosta.<br /><br /> Kun tarkastelet ensisijaisen entiteetin tietuetta, näet luettelon siihen yhdistetyistä liittyvän entiteetin tietueista.|  
|**N:N (monta moneen)**|Tämä entiteettisuhde on riippuvainen erityisestä **suhde-entiteetistä**, jota kutsutaan toisinaan Leikkaa-entiteetiksi (Intersect). Siten yhden entiteetin useita tietueita voidaan liittää useisiin toisen entiteetin tietueisiin.<br /><br /> Kun tarkastelet kumman tahansa N:N-suhteessa olevan entiteetin tietueita, näet luettelon niihin mahdollisesti liittyvistä toisen entiteetin tietueista.|  
  
**N:1 (monta yhteen)** -suhdetyyppi on olemassa käyttöliittymässä, koska suunnitteluohjelma näyttää näkymän, joka on ryhmitelty entiteettien mukaan. 1:N-suhteet ovat olemassa itse asiassa entiteettien *välillä*, ja ne viittaavat kumpaankin entiteettiin joko **ensisijaisena entiteettinä** tai **liittyvänä entiteettinä**. Liittyvässä entiteetissä, jota kutsutaan myös *alientiteetiksi*, on hakukenttä, jonka avulla voidaan tallentaa viittaus tietueeseen ensisijaisesta entiteetistä, jota kutsutaan myös *pääentiteetiksi*. N:1-suhde on vain 1:N-suhde tarkasteltuna liittyvän entiteetin näkökulmasta.  
 
## <a name="see-also"></a>Katso myös

[Entiteettien ja metatietojen yleiskatsaus](create-edit-metadata.md)<br />
[1:N (yksi moneen)- tai N:1 (monta yhteen) -suhteiden luominen ja muokkaaminen](create-edit-1n-relationships.md)<br />
[Monta moneen (N:N) -entiteettisuhteiden luominen](create-edit-nn-relationships.md)


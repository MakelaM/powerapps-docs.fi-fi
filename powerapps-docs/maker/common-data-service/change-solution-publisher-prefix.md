---
title: Ratkaisun julkaisijan etuliitteen muuttaminen | MicrosoftDocs
ms.custom: ''
ms.date: 05/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: ece684h8-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
ms.openlocfilehash: 5881dd6742dd441d135768d3a96fd36dbef9e700
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677656"
---
# <a name="change-the-solution-publisher-prefix"></a>Ratkaisun julkaisijan etuliitteen muuttaminen

Jokainen tekemäsi mukautus on osa ratkaisua. Jokaisella ratkaisulla on julkaisija. Oletusarvon mukaan PowerAppsissa käyttämäsi ratkaisu on **Common Data Services -oletusratkaisu**, joka liitetään **CDS-oletusjulkaisijaan**.

Oletusarvoinen mukautuksen etuliite määritetään satunnaisesti tälle julkaisijalle. Se voi olla esimerkiksi `cr8a3`. Tämä etuliite lisätään jokaisen organisaatiollesi luodun uuden metatietokohteen nimen eteen niiden yksilöllistä tunnistamista varten. Jos luot uuden entiteetin nimeltä **Animal**, CDS for Appsin käyttävä yksilöivä nimi on `cr8a3_animal`. Sama koskee uusia kenttiä (määritteitä), suhteita ja asetusjoukkoja.

Mukautuksen etuliitteellä ei ole juurikaan merkitystä, ellet aio jakaa ratkaisuasi niin, että se asennetaan yhdessä toiselle ratkaisun julkaisijalle luotujen metatietokohteiden kanssa. Etuliite ei näy useimmille sovellustesi käyttäjille. Se näkyy kuitenkin kehittäjille ja teknisille asiantuntijoille, jotka laativat esimerkiksi raportteja. Se auttaa heitä ymmärtämään nopeasti, mikä ratkaisu on lisännyt kohteen.

Tästä syystä monet haluavat muuttaa ratkaisun julkaisijan etuliitteen merkityksellisempään muotoon, erityisesti muista ratkaisuista tuotuja metatietokohteita varten. 

> [!NOTE]
> Jos muutat ratkaisun julkaisijan etuliitteen, tee se ennen kuin luot uusia metatietokohteita. Et voi muuttaa metatietokohteiden nimiä.
> Kun muutat mukautuksen etuliitteen arvon, varmista, että siirryt seuraavaan kenttään. **Asetuksen arvon etuliite** luo automaattisesti numeron mukautuksen etuliitteen perusteella. Tätä numeroa käytetään, kun lisäät asetuksia asetusjoukkoihin, ja se näyttää, millä ratkaisulla asetus on lisätty. 

## <a name="change-the-solution-publisher-prefix-for-the-cds-default-publisher"></a>Ratkaisun julkaisijan etuliitteen muuttaminen CDS-oletusjulkaisijalle  

 1. Valitse PowerApps-portaalin vasemmassa alakulmassa **Mallipohjainen**.
 2. Valitse vasemmassa siirtymisruudussa **Lisäasetukset** avataksesi **Common Data Services -oletusratkaisun**
 3. Valitse ratkaisunhallinnan vasemmassa siirtymisruudussa **Tiedot**-alue.
 4. Valitse **Julkaisija**-linkki avataksesi **CDS-oletusjulkaisija**-lomakkeen.
 5. Muokkaa **Etuliite**-kentän arvoa haluamasi mukautuksen etuliitteen mukaan.
 6. Napsauta **Tallenna ja sulje**.
  
## <a name="change-the-solution-publisher-prefix-for-any-publisher"></a>Ratkaisun julkaisijan etuliitteen muuttaminen kaikille julkaisijoille

Ratkaisujen jakajat käyttävät yleensä luomaansa ratkaisua **Common Data Services -oletusratkaisun** sijaan. Mukautuksen etuliite määritetään yleensä, kun ratkaisu luodaan. Voit muuttaa mukautuksen etuliitteen muille hallitsemattomille ratkaisuille seuraavasti: 

 1. Valitse PowerApps-portaalin vasemmassa alakulmassa **Mallipohjainen**.
 2. Valitse vasemmassa siirtymisruudussa **Lisäasetukset** avataksesi **Common Data Services -oletusratkaisun**
 3. Muokkaa sivun URL-osoitetta ja poista siitä kaikki kohdan `dynamics.com` jälkeen, ja lataa sitten sivu uudelleen.
 4. Valitse **Asetukset** > **Mukautukset** > **Mukautukset**. 
 5. Napsauta **Julkaisijat**. Näkyviin tulee nyt käytettävissä olevien julkaisijoiden luettelo.
 6. Valitse julkaisija, jota haluat muokata, niin julkaisijan lomake avautuu.
 7. Muokkaa **Etuliite**-kentän arvoa haluamasi mukautuksen etuliitteen mukaan.
 6. Napsauta **Tallenna ja sulje**.
  
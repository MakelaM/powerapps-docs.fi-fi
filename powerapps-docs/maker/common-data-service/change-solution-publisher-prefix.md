---
title: Ratkaisujulkaisijan etuliitteen muuttaminen | MicrosoftDocs
ms.custom: ''
ms.date: 05/11/2018
ms.reviewer: ''
ms.service: powerapps
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="change-the-solution-publisher-prefix"></a>Ratkaisujulkaisijan etuliitteen muuttaminen

Jokainen tehty mukautus on osa ratkaisua. Jokaisella ratkaisulla on julkaisija. Oletusarvoisesti PowerAppsissa käytettävä ratkaisu on **Common Data Services -oletusratkaisu**, joka liitetään **Common Data Service -oletusjulkaisijaan**.

Mukautuksen oletusetuliite liitetään satunnaisesti tähän julkaisijaan. Se voi olla esimerkiksi `cr8a3`. Tämä tarkoittaa sitä, että jokaisella organisaatioon luotavalla metatietojen uudella kohteella on alkuun liitettynä nimissä kohteiden yksilöimistä varten. Jos luot uuden entiteetin, jonka nimi on **Eläin**, Common Data Servicen käyttämä yksilöllinen nimi on `cr8a3_animal`. Sama koskee uusia kenttiä (määritteitä), suhteita tai asetusjoukon asetuksia.

Jos et jaa ratkaisua niin, että se asennetaan yhdessä toiselle ratkaisunjulkaisijalle luotujen metatietojen kohteiden kanssa, mukautuksen etuliite voi oikeastaan olla mikä tahansa. Se ei näy sovelluksen useimmille käyttäjille. Se näkyy kuitenkin sovelluskäyttäjille ja esimerkiksi henkilöille, jotka luovat raportteja. Tämän avulla voi nopeasti saada lisätietoja kohteen lisänneestä ratkaisusta.

Tämän vuoksi useat käyttäjät haluavat muuttaa ratkaisunjulkaisijan etuliitettä niin, että ne ovat merkityksellisiä, erityisesti sellaisten metatietojen kohteiden tarkastelemisen yhteydessä, jotka on tuotu muista ratkaisuista. 

> [!NOTE]
> Jos muutat ratkaisunjulkaisijan etuliitettä, tee se ennen uusien metatietojen kohteiden luomista. Et voi muuttaa metatietojen kohteiden nimiä.
> Kun vaihdat mukautetun etuliitteen arvoa, muista siirtyä sarkaimella seuraavaan kenttään. **Asetuksen arvon etuliite** luo automaattisesti luvun mukautuksen etuliitteen perusteella. Tätä lukua käytetään, kun lisäät asetuksia asetusjoukkoihin. Se myös ilmaisee, millä ratkaisulla asetus lisättiin. 

## <a name="change-the-solution-publisher-prefix-for-the-common-data-service-default-publisher"></a>Common Data Servicen oletusjulkaisijan ratkaisujulkaisijan etuliitteen muuttaminen  

 1. Valitse PowerApps-portaalissa vasemmassa alakulmassa **Mallipohjainen**.
 2. Valitse vasemmalla olevassa siirtymistoiminnossa **Lisätiedot**, jolloin **Common Data Services -oletusratkaisu** avautuu
 3. Valitse ratkaisunhallinnassa vasemmalla olevassa siirtymistoiminnossa **Tiedot**-alue.
 4. Valitse **Julkaisija**-linkki, jolloin **Common Data Service -oletusjulkaisija**-lomake avautuu.
 5. Muokkaa **Etuliite**-kentän arvoksi haluamasi mukautuksen etuliite.
 6. Valitse **Tallenna ja sulje**.
  
## <a name="change-the-solution-publisher-prefix-for-any-publisher"></a>Minkä tahansa julkaisijan ratkaisujulkaisijan etuliitteen muuttaminen

Henkilöt, jotka jakavat ratkaisunsa, käsittelevät yleensä luomaansa ratkaisua **Common Data Services -oletusratkaisun** sijaan. Mukautuksen etuliite määritetään yleensä ratkaisun luomisen yhteydessä. Voit muuttaa käyttämäsi toisen hallitsemattoman ratkaisun mukautuksen etuliitteen seuraavasti: 

 1. Valitse PowerApps-portaalissa vasemmassa alakulmassa **Mallipohjainen**.
 2. Valitse vasemmalla olevassa siirtymistoiminnossa **Lisätiedot**, jolloin **Common Data Services -oletusratkaisu** avautuu
 3. Muokkaa sivun URL-osoitetta niin, että poistat kohdan `dynamics.com` jälkeiset merkit. Lataa sivu uudelleen.
 4. Siirry kohtaan **Asetukset** > **Mukautus** > **Mukautukset**. 
 5. Valitse **Julkaisijat**. Nyt voit nähdä käytettävissä olevien julkaisijoiden luettelon.
 6. Valitse poistettava julkaisija, jolloin julkaisijan lomake avautuu.
 7. Muokkaa **Etuliite**-kentän arvoksi haluamasi mukautuksen etuliite.
 6. Valitse **Tallenna ja sulje**.
  

---
title: Common Data Model -yleiskatsaus | Microsoft Docs
description: Lue, miten Common Data Model yhdistetään Common Data Service for Appsiin, joissa on Common Data Service for Analytics.
author: RobertBruckner
ms.service: powerapps
ms.topic: article
ms.date: 03/14/2018
ms.author: jdaly
ms.openlocfilehash: 4e9b929558de0b2451bb2df4add4b300d7115848
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34803234"
---
# <a name="common-data-model-overview"></a>Common Data Model -yleiskatsaus

**Common Data Model** (CDM) on avoimen lähdekoodin määritelmä vakioentiteeteille, jotka edustavat yleisiä liiketoiminta- ja sovellustoimialueissa käytettyjä käsitteitä ja toimintoja. Common Data Model tarjoaa *selkeästi määriteltyjä, modulaarisia ja laajennettavia* liiketoimintaentiteettejä, kuten Tili, Liiketoimintayksikkö, Tapaus, Yhteyshenkilö, Liidi, Mahdollisuus ja Tuote, sekä vuorovaikutusta ja suhteita myyjien, työntekijöiden ja asiakkaiden välille, kuten toimintoja ja palvelutasosopimuksia. 

Microsoftin [Common Data Service for Apps](../maker/common-data-service/data-platform-intro.md) ja Common Data Service for Analytics <!-- TODO add link when available  --> toteuttavat Common Data Modelia. Nämä palvelut säilyttävät tietoja, jotka noudattavat Common Data Model -määritystä. Kehittämällä näiden palveluiden pohjalta paketoidut sovellukset ja analysointiratkaisut voivat toimia tarkkarajaisten entiteettimuotojen kanssa ja jakaa tietoja riippumatta siitä, mistä tiedot ovat peräisin tai missä niitä käytettiin. Mukautetut liiketoiminta-aluesovellukset voivat hyödyntää samoja entiteettejä tietojen jakamiseen ja näin ollen tukevat erityistarpeita ja liiketoiminnan vaatimuksia. 

Microsoft ja sen kumppanit ovat sitoutuneet kehittämään sovelluksia Common Data Servicen pohjalta ja tallentamaan yritystietoja CDM-muodossa. Olemassa on *laajoja ja kasvavia ratkaisukokoelmia, jotka toimivat tehokkaasti yhdessä, kun tiedot tallennetaan CDM-muodossa*. Tämä tarkoittaa sitä, että voit nopeasti toteuttaa uusia liiketoimintaprosesseja ja saada tietoja liiketoiminnoistanne ilman kitkaa tai ongelmia. Seuraavassa kaaviossa esitetään Common Data Servicen pohjalta kehitettyjä sovelluksia, jotka hyödyntävät Common Data Model -entiteettejä.

![Common Data Model -entiteettejä hyödyntäviä sovelluksia Common Data Servicen pohjalta](media/cdm-overview.png)

Common Data Model yksinkertaistaa tietojen hallintahaasteita yhtenäistämällä tietoja tunnetussa muodossa noudattamalla *rakenteellista ja semanttista yhdenmukaisuutta eri sovelluksissa ja käyttöönotoissa*. Sen avulla voit integroida tietoja ja *tehdä yksiselitteisiä tiedoista*, jotka on kerätty mm. liiketoimintaprosesseista, digitaalisesta vuorovaikutuksesta, tuotetelemetriasta ja ihmisten keskinäisestä vuorovaikutuksesta. 

Common Data Service for Appsiin tallennetut tiedot *integroidaan helposti ja automaattisesti* Common Data Service for Analyticsiin asiakkaille, jotka käyttävät molempia palveluita. Voit aloittaa jo omistamistasi yritys- ja tapahtumatiedoista (kuten liidit, kampanjatiedot ja aiemmat asiakasostot) ja yhdistää tietoja muista lähteistä (kuten blogit tai tuotetelemetria) saaden yhdistetyn kuvan.

Common Data Model on myös *laajennettava*: voit lisätä kenttiä mihin tahansa mukautettaviin entiteetteihin, jotka toimitetaan CDM:n mukana, tai voit luoda omat mukautetut entiteetit. CDM-standardi määrittää yhteisen kielen liiketoimintaentiteeteille, jotka kattavat kaikki liiketoimintaprosessit aina myynnistä palveluihin, markkinointiin, toimintoihin, rahoitukseen, kykyihin ja kaupankäyntiin, sekä asiakas-, henkilö- ja tuote-entiteeteille yrityksen liiketoimintaprosessien ytimessä. Common Data Model helpottaa tietojen yhteentoimivuutta useiden kanavien, palvelutoteutusten ja toimittajien välillä.

Common Data Model ja Common Data Service tarjoavat monipuolisen ja tuottavan kehitysympäristön seuraavien ominaisuuksien kautta:

- **Vakioentiteettien määritys** – Common Data Model tarjoaa entiteettien määrityksen, joka edustaa yritys- ja tuotantosovelluksissa useimmiten käytettyjä entiteettejä. Julkista CDM GitHub-säilöä [(https://github.com/Microsoft/CDM) ](https://github.com/Microsoft/CDM) parannetaan jatkuvasti ydinentiteeteillä, jotka kattavat koko liiketoimintaprosessien ympäristön, vertikaalisen alan lisätietomallit ja kattavat resurssit, kuten kyselyt, hakukoneet ja tuotetelemetrian.
- **Tietojen integrointi** – Käytä Power Queryä sisäisenä verkko-ominaisuutena, joka tuo ja visuaalisesti muuntaa tietoja olemassa olevista järjestelmistä ja yhdistää tietoja verkosta ja paikallisista lähteistä ilman koodausta tai vähäisellä koodauksella. Käytät saumattomasti Excel- ja Power BI -tietojen muuntotaitojasi. Katso [Tietojen lisääminen Common Data Servicessä olevaan entiteettiin Power Queryn avulla](../maker/common-data-service/data-platform-cds-newentity-pq.md).
    
    Kun tuot tietoja Common Data Serviceen, voit kartoittaa sen Common Data Modelin vakioentiteetteihin tai luoda uusia entiteettejä ja kartoittaa niihin. Valmiit tietojen integroinnin ja kartoituksen mallit yksinkertaistavat yhteyden muodostamista yleisiin tietolähteisiin, kuten Salesforce. Nämä kartoitusmallit ovat täysin mukautettavissa ja laajennettavissa. Seuraavassa näyttökuvassa esitetään ulkoisten tietojen tuonti ja sen kartoittaminen vakioentiteetteihin Power Queryssä. 
    
    ![Tuo ulkoisia tietoja ja kartoita ne vakioentiteetteihin Power Queryssä ](media/cdm-mapping-entities.png)<br />

- **Laajennettavuus** – Voit laajentaa entiteettejä rikkomatta tietojenjakoa muiden sovellusten kanssa.
- **Luotettavuus** – Koska voit luottaa yleisiin entiteetteihin, voit luoda uudelleenkäytettäviä osia, jotka on sidottu entiteetteihin. Common Data Model tukee laajennettavuutta ja versiotietoja, jotka suojelevat kehityssijoitusta.
- **Entiteettien yhdenmukaisuus kaikissa käyttöönotoissa** – Ratkaisut voivat yhdistää tuottavuusympäristöjen tiedot yrityssovellusten tietojen kanssa. Voit esimerkiksi yhdistää kalenteritapaamisen tai Microsoft Outlook -tehtävän myyntimahdollisuuden kanssa. 

[Common Data Service for Apps](../maker/common-data-service/data-platform-intro.md) toteuttaa Common Data Modelia tarjoten seuraavat mahdollisuudet liiketoiminnan sovelluskehitykselle:

- **Pakattujen yrityssovellusten hyödyntäminen** – Dynamics 365:n markkinoinnin, myynnin, palvelun, kykyjen, rahoituksen ja toimintojen sovellukset sekä kolmannen osapuolen sovellukset hyödyntävät ja/tai on kehitetty Common Data Service for Appsin pohjalta.
- **Mukauta sovelluksia ja luo alkuperäisiä laajennuksia vastaamaan tarpeita** – Mukauttajat ja sovelluskehittäjät jakavat sovellusratkaisuja, joissa on tarkkarajainen sovelluselinkaari. Ratkaisujen avulla jaetaan sovelluksia ja laajennuksia. Katso [Ratkaisuihin tutustuminen](../developer/common-data-service/introduction-solutions.md).
- **Kehitä koodittomia / vähän koodia sisältäviä, mallipohjaisia ja pohjaan perustuvia WYSIWYG-sovelluksia PowerAppsilla** – Käytä samoja jaettuja entiteettejä, jotka paketoidut sovellukset tai muut kolmannen osapuolen sovellukset loivat ja joita nämä käyttivät sekä erillisiä lisäsovelluksia. Katso: 
    - [Luo mallipohjainen sovellus](../maker/model-driven-apps/model-driven-app-overview.md)
    - [Luo pohjaan perustuva sovellus](../maker/canvas-apps/getting-started.md) 
- **Automatisoi liiketoimintaprosesseja Flow’n avulla** – Käytä liiketoimintaprosessien kulkua määrittämään joukon vaiheita ja ohjeita, joilla saavutetaan haluttu tulos. Katso [Luo työnkulku, joka käyttää Common Data Serviceä](/flow/common-data-model-intro)
 
**Common Data Service for Analytics**in tulevassa julkisessa esittelyssä<!-- TODO add link when available  --> toteutetaan myös Common Data Modelia, joka tukee yritystietojen analysointia vakiomuodossa, mukaan lukien:

- **Pakatut ja mukautetut analyyttiset ratkaisut vakiotietojen entiteettien perusteella** – analyyttiset sovellukset, kuten Sales Insights, joka seuraa historiallista myynnin suorituskykyä, tarjoaa yhtenäisiä näkymiä riippumatta siitä, missä tietoja alun perin käytettiin, koska tietojen integroinnin käyttökokemus kartoittaa tiedot muista lähteistä (esimerkiksi Salesforce.com) Common Data Modelin entiteettimuotoihin. Tämä yksinkertaistaa analyyttista ratkaisua, jolloin voit keskittyä tarkkarajaisten entiteettien, kuten liidien ja mahdollisuuksien, tietosemantiikkaan.
- **Kooditonta / vähäistä koodausta sisältävää tietojen integrointia Power Queryssä** – Käytä valmista käyttökokemusta ja luo, täytä, muunna ja täydennä entiteettejä. 
- **Tuo oma Azure-tallennustilasi** – Hyödynnä Azure-tietopinoja, joiden avulla saat tietoja Common Data Service for Analyticsin käyttöön. Entiteetit tallennetaan samaan yleiseen tietojen mallimuotoon, jonka analyyttiset ratkaisut tunnistavat.


---
title: Entiteetit ja metatiedot Common Data Service for Apps -palvelussa | MicrosoftDocs
description: Lue lisätietoja Common Data Service for Apps -palvelun entiteeteistä ja metatiedoista
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
ms.assetid: 88b18946-474c-4c94-8e4c-27532f930757
caps.latest.revision: 28
ms.author: matp
manager: kvivek
ms.openlocfilehash: ef2f92865205fa7c97ada356edc70ac69a637e0f
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681657"
---
# <a name="entities-and-metadata-in-common-data-service-for-apps"></a>Common Data Service for Apps -palvelun entiteetit ja metatiedot

Common Data Service for Apps on suunniteltu siten, että voit luoda sovelluksellesi tietomallin nopeasti ja helposti. Yleensä sinun ei tarvitse huolehtia metatietojen yksityiskohdista, joita tässä ohjeartikkelissa käsitellään. Jos haluat kuitenkin ymmärtää paremmin, miten Common Data Service for Apps -palvelua käyttävät sovellukset toimivat, tai haluat arvioida mahdollisuuksia, Common Data Service for Apps -palvelun käyttämien metatietojen ymmärtämisestä voi olla hyötyä.

*Metatiedot* tarkoittavat tietoja tiedoista. CDS for Apps tarjoaa joustavan palvelun, jossa voit suhteellisen helposti muokata ympäristön käyttämien tietojen määritelmiä. CDS for Apps -palvelussa metatiedot ovat entiteettikokoelmia. Entiteetit kuvaavat sitä, millaisia tietoja tietokantaan tallennetaan.  Jokainen entiteetti vastaa tietokannan taulukkoa ja jokainen entiteetin kenttä (josta käytetään myös nimeä määrite) vastaa tämän taulukon saraketta. Entiteetin metatiedot määräävät sen, millaisia tietueita voit luoda ja millaisia toimintoja niille voi suorittaa. Kun luot tai muokkaat entiteettejä, kenttiä ja entiteettisuhteita mukautustyökaluilla, muokkaat näitä metatietoja. 
  
Eri asiakasohjelmat, joilla käyttäjät käyttävät ympäristösi tietoja, luottavat näihin entiteettien metatietoihin ja sopeutuvat metatietojen mukautuksiin. Nämä asiakkaat luottavat myös muihin tietoihin, joiden avulla hallitaan näytettäviä visuaalisia elementtejä, käytettävää mukautettua logiikkaa ja suojauksen toteutusta. Myös nämä järjestelmätiedot tallennetaan entiteetteihin, mutta entiteetit itsessään eivät ole muokattavissa.

Voit lukea lisätietoja CDS for Apps -palveluun oletusarvoisesti sisältyvistä vakioentiteeteistä, -määritteistä ja -entiteettisuhteista [entiteettejä käsittelevästä ohjeartikkelista](/powerapps/developer/common-data-service/reference/about-entity-reference).

> [!TIP]
> Metatietojen muokkaamiseen käytettävissä olevat suunnittelutyökalut eivät voi näyttää kaikkia metatietoihin sisältyviä yksityiskohtaisia tietoja. Voit asentaa malliin perustuvan **Metadata Browser** -sovelluksen, jolla voit tarkastella kaikkia järjestelmän entiteettejä ja metatieto-ominaisuuksia. Lisätiedot: [Ympäristön metatietojen selaaminen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/browse-your-metadata).
  
<a name="BKMK_CreateNewOrUseExistingMetadata"></a>

## <a name="create-new-metadata-or-use-existing-metadata"></a>Kannattaako sinun luoda uusia metatietoja vai käyttää olemassa olevia metatietoja?

CDS for Apps sisältää useita vakioentiteettejä, jotka tukevat liiketoimintasovellusten perustoimintoja. Esimerkiksi asiakkaiden ja mahdollisten asiakkaiden tiedot on tarkoitettu tallennetavaksi tilien tai yhteystietojen entiteetteihin.  
  
Kaikki nämä entiteetit sisältävät useita kenttiä: ne edustavat yleisiä tietoja, jotka järjestelmän täytyy ehkä tallentaa entiteeteille.  
  
Useimpien organisaatioiden kannattaa käyttää vakioentiteettejä ja -määritteitä niiden aiottuihin käyttötarkoituksiin. 
  
Jos asennat ratkaisun, voit olettaa, että sen kehittäjä on hyödyntänyt vakioentiteettejä ja -määritteitä. Jos luot uuden mukautetun entiteetin, joka korvaa järjestelmän entiteetin tai määritteen, käytettävissä olevat ratkaisut eivät ehkä toimi organisaatiollesi.  
  
Tästä syystä suosittelemme, että käytät vakioentiteettejä, -kenttiä ja -entiteettisuhteita, kun ne soveltuvat käyttötarkoituksiisi ja organisaatiollesi. Jos ne eivät sovellu tarkoituksiisi eikä niitä voi muokata tarpeisiisi, sinun kannattaa selvittää, täytyykö sinun luoda uusi entiteetti, kenttä tai entiteettisuhde. 

<!--  Can we say this yet? 
    
> [!NOTE]
> The [Common Data Model](/powerapps/common-data-model/overview) will provide a capability to add additional standard entities. 

-->

Muista, että voit muuttaa entiteettien näyttönimiä organisaatiosi nimeämiskäytäntöön sopiviksi. Käyttäjät vaihtavat esimerkiksi Tili-entiteetin nimeksi hyvin usein *Yritys* tai Yhteyshenkilö-entiteetin nimeksi *Yksilö*. Entiteettien ja määritteiden nimiä voi vaihtaa vaikuttamatta niiden toimintaan. Lue lisätietoja [entiteettien nimien vaihtamisesta](edit-entities.md#change-the-name-of-an-entity).
  
Et voi poistaa vakioentiteettejä, -kenttiä ja -entiteettisuhteita. Ne katsotaan osaksi järjestelmäratkaisua, joten jokaisella organisaatiolla tulee olla ne. Jos haluat piilottaa vakioentiteetin, muokkaa organisaatiosi käyttöoikeusroolien oikeuksia siten, että kyseisen entiteetin lukuoikeus poistetaan. Tämä poistaa entiteetin sovelluksen useimmista osista. Jos et tarvitse jotain järjestelmäkenttää, poista se lomakkeesta ja kaikista sitä käyttävistä näkymistä. Muokkaa **Haettavissa**-arvoa kentän ja entiteettisuhteen määritelmissä siten, että niitä ei näytetä erikoishaussa. 
  
<a name="BKMK_LimitationsOnMetadata"></a>   

## <a name="limitations-on-creating-metadata-items"></a>Metatietokohteiden luomisen rajoitukset  

Luotavien entiteettien määrä on rajoitettu. Saat lisätietoja enimmäismäärästä valitsemalla **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Hallinta** > **Käytössä olevat resurssit**. Jos tarvitset lisää mukautettuja entiteettejä, ota yhteyttä tekniseen tukeen. Rajoitusta on mahdollista muuttaa.  
  
Jokaisen entiteetin luotavien kenttien määrää on rajoitettu. Tämä rajoitus perustuu teknisiin rajoituksiin sille, kuinka paljon tietoa yhdelle tietokannan taulukon riville on mahdollista tallentaa. Tarkan rajoituksen antaminen on vaikeaa, koska erityyppiset kentät voivat käyttää eri määrän tilaa. Rajoitus riippuu entiteetin kaikkien kenttien yhteensä käyttämästä tilasta.  
  
Useimmat käyttäjät eivät luo niin paljon mukautettuja kenttiä, että rajoitus täyttyisi. Jos kuitenkin aiot lisätä entiteettiin satoja mukautettuja kenttiä, tätä kannattaa harkita uudelleen. Kuvaavatko kaikki suunnittelemasi kentät kyseisen entiteetin tietueen ominaisuuksia? Uskotko tosiaan, että organisaatiosi käyttäjät käyttävät mielellään lomaketta, jossa on näin paljon kenttiä? Lomakkeeseen lisäämiesi kenttien määrä lisää tietomäärää, joka täytyy siirtää aina, kun tietuetta muokataan. Tämä siis vaikuttaa järjestelmän suorituskykyyn. Ota nämä seikat huomioon, kun lisäät mukautettuja kenttiä entiteettiin.  
  
Asetusjoukkokentät tarjoavat joukon asetuksia, jotka näytetään lomakkeen avattavassa ohjausobjektissa tai valintaluettelo-ohjausobjektissa erikoishakua käytettäessä. Ympäristösi voi tukea tuhansia asetuksia asetusjoukossa, mutta tätä ei tule pitää rajoituksena tai suosituksena. Käytettävyystutkimusten mukaan käyttäjillä on vaikeuksia käyttää järjestelmää, jossa avattavat ohjausobjektit sisältävät suuren määrän vaihtoehtoja. Asetusjoukkoa kannattaa käyttää tietoluokkien määrittämiseen. Älä käytä asetusjoukkoja sellaisten luokkien valitsemiseen, jotka todellisuudessa edustavat erillisiä tietokohteita. Sinun ei kannata esimerkiksi luoda asetusjoukkoa, joka tallentaa sadat mahdolliset laitevalmistajat, vaan luoda entiteetti, joka tallentaa viittaukset kuhunkin valmistajaan ja käyttää sitten hakukenttää asetusjoukon asemesta.  
  
## <a name="next-steps"></a>Seuraavat vaiheet 

[Entiteettien (tietuetyyppien) luominen ja muokkaaminen](create-edit-entities.md)<br />
[Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)


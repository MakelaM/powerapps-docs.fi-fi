---
title: Entiteetit ja metatiedot Common Data Service sovelluksille -ratkaisussa | MicrosoftDocs
description: Lisätietoja entiteeteistä ja metatiedoista Common Data Service sovelluksille -ratkaisussa
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="entities-and-metadata-in-common-data-service-for-apps"></a>Entiteetit ja metatiedot Common Data Service sovelluksille -ratkaisussa

Common Data Service sovelluksille on suunniteltu niin, että voit luoda sovellukselle tietomallin nopeasti ja helposti. Yleensä käyttäjän ei tarvitse ottaa huomioon tämän ohjeaiheen sisältämiä metatietoja koskevat tietoja. Jos kuitenkin haluat ymmärtää enemmän CDS sovelluksille -ratkaisua käyttävien sovellusten toimintaa tai jos olet arvioimassa mahdollisia toimintoja, CDS sovelluksille -ratkaisun käyttämien metatietojen ymmärtäminen voi antaa tärkeitä tietoja.

*Metatiedoilla* tarkoitetaan tietoja koskevia tietoja. CDS sovelluksille on joustavan ympäristö, koska ympäristön käyttämiä tietojen määrityksiä on melko helppo muokata. CDS sovelluksille -ratkaisun metatiedot ovat kokoelma entiteettejä. Entiteetit kuvaavat millaisia tietoja on tallennettu tietokantaan.  Jokainen entiteetti vastaa tietokantataulukkoa ja jokainen kenttä (tunnettu myös määritteenä) entiteetin sisällä vastaa taulukon saraketta. Entiteetin metatiedot määrittävät millaisia tietueita voit luoda ja millaisia toimintoja voidaan suorittaa niissä. Kun käytät mukauttamistyökaluja entiteettien, kenttien ja entiteettisuhteiden luomisessa tai muokkaamisessa, muokkaat näitä metatietoja. 
  
Erilaiset asiakasohjelmat, joilla käyttäjät käyttävät ympäristön tietoja, tarvitsevat entiteetin metatietoja ja niiden on muututtava metatietojen mukauttamisen yhteydessä. Mutta nämä asiakkaat ovat riippuvaisia myös muista tiedoista, jotta he voivat hallita sitä, mitä visuaalisia elementtejä näytetään, mitä mukautettua logiikkaa käytetään ja kuinka suojausta käytetään. Nämä järjestelmätiedot on myös tallennettu entiteetteihin mutta itse entiteetit eivät ole mukautettavissa.

Saat lisätietoja CDS sovelluksille -ratkaisun oletusarvoisista vakioentiteeteistä, määritteistä ja entiteettisuhteista kohdasta [Entiteettisuhde](/powerapps/developer/common-data-service/reference/about-entity-reference).

> [!TIP]
> Sovelluskehittäjät, jotka voivat muokata metatietoja, eivät voi näyttää kaikkia niiden tietoja. Voit asentaa mallipohjaisen sovelluksen, jonka nimi on **Metadata Browser**. Sen avulla voit tarkastella järjestelmän kaikkien entiteettien ja metatietojen ominaisuuksia. Lisätietoja: [Metatietojen etsiminen selaamalla ympäristössä](https://docs.microsoft.com/dynamics365/customer-engagement/developer/browse-your-metadata).
  
<a name="BKMK_CreateNewOrUseExistingMetadata"></a>

## <a name="create-new-metadata-or-use-existing-metadata"></a>Luodaanko uusia metatietoja vai käytetäänkö olemassa olevia metatietoja?

CDS sovelluksille sisältää lukuisia vakioentiteettejä, jotka tukevat liiketoimintasovelluksen ydinominaisuuksia. Esimerkiksi tietoa asiakkaista tai potentiaalisista asiakkaista on tarkoitus tallentaa käyttäen asiakas- tai yhteyshenkilö-entiteettejä.  
  
Jokainen näistä entiteeteistä sisältää myös useita kenttiä, jotka esittävät yleisiä tietoja, jotka järjestelmän on ehkä tallennettava vastaavan entiteettiin.  
  
Useimmissa organisaatioissa kannattaa hyödyntää vakioentiteettejä ja määritteitä niihin tarkoituksiin, joihin ne on luotu. 
  
Jos asennat ratkaisun, voit olettaa, että ratkaisun kehittäjä on hyödyntänyt vakioentiteettejä ja määritteitä. Uuden mukautetun entiteetin luontia, joka korvaa järjestelmän entiteetin tai määritteen tarkoittaa, että käytettävissä olevat mahdolliset ratkaisut eivät välttämättä toimi organisaatiossasi.  
  
Näistä syistä suosittelemme, että etsit ja käytät vakioentiteettejä, kenttiä ja entiteettisuhteita, kun ne sopivat organisaatiosi tarpeisiin. Jos ne eivät sovi, eikä niitä voi muokata vastaamaan tarvetta, on arvioitava, onko uuden entiteetin, kentän tai entiteettisuhteen luonti välttämätöntä. 

<!--  Can we say this yet? 
    
> [!NOTE]
> The [Common Data Model](/powerapps/common-data-model/overview) will provide a capability to add additional standard entities. 

-->

Muista, että voit muuttaa entiteetin nimen siten, että se vastaa organisaatiosi nimikkeistöä. On esimerkiksi hyvin yleistä vaihtaa Asiakas-entiteetin näyttönimeksi *Yritys* tai Yhteyshenkilö-entiteetin nimeksi *Yksilö*. Tämä voidaan tehdä entiteeteille tai määritteille muuttamatta entiteetin toimintaa. Saat lisätietoja kohteiden nimeäminen uudelleen kohdasta [entiteetin nimen muuttaminen](edit-entities.md#change-the-name-of-an-entity).
  
Vakioentiteettejä, kenttiä tai entiteettisuhteita ei voi poistaa. Niitä pidetään osana järjestelmäratkaisua ja jokaisen organisaation on tarkoitus saada ne. Jos haluat piilottaa vakioentiteetin, vaihda organisaation käyttöoikeusrooleja poistaaksesi kyseisen entiteetin lukuoikeuden. Tämä poistaa kohteen sovelluksen useimmissa osissa. Jos et tarvitse järjestelmäkenttää, poista se lomakkeesta ja sitä käyttävät näkymät. Muuta kentän ja entiteettisuhteen **Haettavissa**-arvoa kentän määritelmässä niin, että ne eivät näy erikoishaussa. 
  
<a name="BKMK_LimitationsOnMetadata"></a>   

## <a name="limitations-on-creating-metadata-items"></a>Rajoitukset metatietojen kohteiden luomiseen  

Luotavien entiteettien määrä on rajoitettu: Voit etsiä tietoja enimmäismääristä kohdassa **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Hallinta** > **Käytössä olevat resurssit** -sivu. Jos tarvitset lisää mukautettuja entiteettejä, ota yhteyttä tekniseen tukeen. Tätä ylärajoitusta voi kuitenkin muuttaa.  
  
Kunkin kohteen sisällä on yläraja, kuinka monta kenttää voit luoda. Tämä rajoitus perustuu tietomäärän teknisiin rajoituksiin siitä, mitä voidaan tallentaa tietokannan taulukon riville. On vaikeaa antaa tiettyä lukua, koska kunkin kentän tyyppi voi käyttää eri määrän tilaa. Yläraja riippuu entiteetin kaikkien kenttien käyttämästä koko tilasta.  
  
Useimmat ihmiset eivät luo riittävästi mukautettuja kenttiä saavuttaakseen rajan, mutta jos löydät itsesi suunnittelemassa satojen mukautettujen kenttien lisäämistä entiteettiin, kannattaa miettiä onko tämä paras ratkaisu. kuvaavatko kaikki kentät, jotka haluat lisätä, kyseisen entiteetin tietueen ominaisuuksia? Oletatko todella, että organisaatiosi käyttäjät hallitsevat tällaisen suuren määrän kenttiä sisältävän lomakkeen? Lomakkeeseen lisättävien kenttien määrä kasvattaa tietomäärää, joka on siirrettävä aina, kun tietuetta muokataan ja vaikuttaa järjestelmän suorituskykyyn. Ota huomioon nämä tekijät, kun lisäät mukautettuja kenttiä kohteeseen.  
  
Asetusjoukkokentät takaavat joukon asetuksia, jotka näkyvät avattavan lomakkeen ohjausobjektissa tai valintaluettelon ohjausobjektissa, kun käytetään erikoishakua. Ympäristö voi tukea tuhansia asetuksia asetusjoukon sisällä, mutta sitä ei kannata pitää ylärajana. Käytettävyystutkimukset ovat osoittaneet, että ihmisillä on ongelmia käyttää järjestelmää, jossa avattava ohjausobjekti tarjoaa runsaasti vaihtoehtoja. Määritä tietoluokat asetusjoukko-kentän avulla. Älä käytä asetusjoukkokenttiä valitsemaan luokkia, jotka todellisuudessa edustavat eri tieto-osia. Esimerkiksi sen sijaan että säilytät asetusjoukkokentän, joka tallentaa jokaisen sadoista mahdollisista laitevalmistajista, kannattaa ehkä luoda entiteetti, joka sisältää viittauksia jokaiseen valmistajaan ja käyttää hakukenttää asetusjoukon sijasta.  
  
## <a name="next-steps"></a>Seuraavat vaiheet 

[Entiteettien (tietuetyyppien) luominen ja muokkaaminen](create-edit-entities.md)<br />
[Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)


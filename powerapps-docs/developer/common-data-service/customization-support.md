---
title: Common Data Service for Apps -palvelun sovellusten luontikäytännöt | MicrosoftDocs
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e9810433-224b-4bde-851a-e581cf5fb8a4
caps.latest.revision: 21
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1eda4b591a3296001ffa62b16e185b421a197e75
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865037"
---
# <a name="common-data-service-for-apps-supported-and-unsupported-app-building-practices"></a>Common Data Service for Apps -palvelun tuetut ja tukemattomat sovellusten luontikäytännöt

<!--
The way your organization works is unique. Some organizations have well-defined business processes that they apply using PowerApps apps. Others aren’t happy with their current business processes and use PowerApps to apply new data and processes to their business. Whatever situation you find yourself in, you’ll find a lot of customization capabilities in PowerApps so that it can work for your organization.  
  
 Of course you’re eager to get started, but please take a few minutes to read the content in this section. This will introduce you to important terms, give you some background about why things are done a certain way, and help you avoid potential problems in the future.  

## What is metadata and why should you care?  
 In the past, you may have customized business applications by editing the source code. This created complications because each organization had unique changes and it was very difficult, or extremely expensive, to upgrade. Then application developers started exposing application programming interfaces (APIs) so that other developers could interact with the application and add their own logic without touching the source code. This was moderately better because it means developers can extend the application without changing it. But it still requires a developer to write code.  -->
  
 Nykyaikaiset yrityssovellukset käyttävät metatietopohjaista arkkitehtuuria, jotta käyttäjät voivat luoda sovelluksia kirjoittamatta koodia. Metatiedot tarkoittavat tietoja tiedoista: ne määrittävät Common Data Service for Apps -palveluun tallennettujen tietojen rakenteen. Näiden metatietojen avulla sovellus saa selville muutokset tietojen rakenteeseen. Tämän ansiosta sovellus voi sopeutua tietorakenteen muutoksiin. Koska metatiedot tunnetaan, sovelluksiin voidaan sisällyttää lisätoimintoja, jotka ovat sidoksissa metatietoihin.  

Haluamallasi tavalla toimivien sovellusten luomista Common Data Service for Apps -komponentteja (esimerkiksi entiteetit, näkymät, kentät, kaaviot ja koontinäytöt) muuttamalla kutsutaan *mukauttamiseksi*.  
 
Kun luot ja mukautat sovelluksia PowerAppsin työkaluilla, lisäät tai päivität metatietoja tai tietoja, joita niitä edellyttävät toiminnot käyttävät. Koska tiedämme, millaisilla tiedoilla sovelluksia luodaan, voimme huomioida nämä tiedot ja lisätä Common Data Service for Apps -ympäristöön uusia toimintoja sovelluksia rikkomatta. <!-- This way you should always be able to apply an update rollup or upgrade to the latest version and enjoy the best new features.  -->

<!--  
> **Customize or Configure?**   
> Most people say they want to customize the application, so we use the word “customize” to describe changing the system to make it work the way you want. Some people prefer to use the word “configure” because it suggests that no code was required to make changes. Call it whatever you like, we just want to make it clear that you don’t need to be a developer to customize or create PowerApps apps.  -->
  
Sinun ei tarvitse olla kehittäjä voidaksesi luoda ja mukauttaa PowerApps-sovelluksia. PowerApps tarjoaa kuitenkin joukon verkkopalveluita ja ohjelmointirajapintoja, joilla kehittäjät voivat kirjoittaa koodia. Kun koodia kirjoitetaan tuetuilla menetelmillä, voit olettaa, että se toimii myös jatkossa, kun Common Data Service for Apps -ympäristöäsi päivitetään.  
  
<a name="BKMK_SupportedCust"></a>   
## <a name="what-kinds-of-customizations-are-supported"></a>Millaisia mukautuksia tuetaan?  
 Oletamme, että teet suurimman osan sovellusten luomisesta ja mukauttamisesta käytettävissä olevilla PowerApps-työkaluilla. Jos mukautustyökalut eivät vastaa tarpeitasi, voit asentaa ulkopuolisen palveluntarjoajan tarjoaman ratkaisun tai palkata kehittäjän koodaamaan sovelluksesi. Jos sinun täytyy investoida koodia edellyttävään ratkaisuun, varmista, että koodia kirjoitetaan vain tuetuilla ohjelmointirajapinnoilla. Tämä auttaa sinua suojaamaan investointejasi sekä sovelluksiin että hankkimiisi ratkaisuihin.  
  
 Kehittäjillä, jotka laajentavat PowerApps-sovelluksia, on velvollisuus noudattaa sääntöjä ja parhaita käytäntöjä, jotka on määritetty seuraavassa SDK:ssä: [Dynamics 365 Customer Engagementilla kehittämisen parhaat käytännöt](https://docs.microsoft.com/dynamics365/customer-engagement/developer/best-practices-sdk). Tämä SDK sisältää tiedot kehittäjien käytettävissä olevista ohjelmointirajapinnoista sekä ohjeet niiden käyttöön. Microsoft tukee vain SDK:ssä kuvattuja ohjelmointirajapintoja ja käytäntöjä. Saatat löytää Internetistä ohjeita jonkin ongelman ratkaisemiseen, mutta jos tämä ratkaisu ei hyödynnä SDK:ssä kuvattuja ohjelmointirajapintoja, Microsoft ei tue ratkaisua. Ennen kuin pyydät kehittäjää tekemään mitään muutoksia, varmista, että muutoksissa käytetään tuettuja menetelmiä.  
  
 Kun kehittäjät käyttävät SDK:ssä kuvattuja ohjelmointirajapintoja ja parhaita käytäntöjä, voimme testata varmasti, voivatko mitkään Common Data Service for Apps -palveluun tekemämme muutokset mahdollisesti rikkoa olemassa olevia mukautuksia. Tavoitteemme on, että tuetuilla menetelmillä kirjoitetut koodimukautukset toimivat myös jatkossa, kun Common Data Service for Apps -palvelusta julkaistaan uusia versioita tai kun sille julkaistaan päivityksiä. Hyödyt tästä, koska voit päivittää uusiin parempia toimintoja sisältäviin versioihin ilman, että kehittäjien täytyisi muuttaa koodia joka kerta.  
  
 Jos huomaamme Common Data Service for Apps -palvelun uudessa versiossa muutoksen, jonka johdosta tuettu mukautus ei enää toimi, dokumentoimme sen, mihin tämä vaikuttaa, ja tarjoamme ohjeet koodin muuttamiseen ongelman korjaamiseksi.  
  
<a name="BKMK_Unsupported"></a>   
## <a name="what-kinds-of-customizations-arent-supported"></a>Millaisia mukautuksia ei tueta?  
 Vaikka Microsoft ei tue tiettyjä ohjelmointirajapintoja ja ohjelmointikäytäntöjä, tämä ei tarkoita sitä, että ne eivät toimi. <!--  “Unsupported by Microsoft” means exactly what it says: you can’t get support about these APIs or programming practices from Microsoft. We don’t test them and we don’t know if something we change will break them. We can’t predict what will happen if someone changes code in our application.  --> Tukemattomia ohjelmointirajapintoja ja ohjelmointikäytäntöjä käyttävä kehittäjä on itse vastuussa koodinsa tukemisesta. Heidän täytyy testata koodinsa ja varmistaa sen toimivuus.  
  
 Jos päätät käyttää tukemattomia mukautuksia Common Data Service for Apps -ympäristössäsi, muista dokumentoida toimenpiteesi ja laatia strategia näiden mukautusten poistamiseksi, ennen kuin otat yhteyttä Microsoftin tekniseen tukeen. Jos tarvitset apua tukemattomiin mukautuksiin liittyen, ota yhteyttä mukautuksen valmistelleeseen kehittäjään tai organisaatioon.  
  
<a name="BKMK_CommonUnsupportedCustomizations"></a>   
### <a name="common-unsupported-customization-practices"></a>Yleisiä tukemattomien mukautusten käytäntöjä  
 Alla on luettelo yleisistä mukautuskäytännöistä, joita ei tueta. Tämä lista ei kata kaikkia mahdollisia tukemattomia käytäntöjä. Lisätietoja: [Dynamics 365:n tuetut laajennukset: mukautukset, joita ei tueta](https://docs.microsoft.com/dynamics365/customer-engagement/developer/supported-extensions#Unsupported). 
 
**Verkkosovellusten Document Object Model (DOM) -elementtien käyttö JavaScriptillä**  
 Minkä tahansa missä tahansa sovelluksessa käytettävien JavaScript-kirjastojen täytyy olla vuorovaikutuksessa vain dokumentoitujen ohjelmointirajapintojen kanssa. Kun JavaScript-kehittäjät työstävät sovelluksia, he käyttävät usein DOM-elementtejä tietyillä nimillä. Koska PowerApps-sovellukset ovat verkkosovelluksia, nämä tekniikat toimivat. Ne kuitenkin todennäköisesti lakkaavat toimimasta päivityksen yhteydessä, koska niiden elementtien nimet, joihin ne viittaavat, voivat muuttua milloin tahansa. Pidätämme oikeuden tehdä mitä tahansa tarvittavia muutoksia sovellukseen. Usein tämä tarkoittaa muutoksia siihen, miten sivu on jäsennelty tai rakennettu. Minkä tahansa sivun nykyisestä rakenteesta riippuvaisen muutoksen lisääminen tarkoittaa sitä, että sinun täytyy panostaa testaukseen ja ehkä muuttaa näiden komentosarjojen mukautettua koodia aina, kun otat päivityksen käyttöön sovelluksessasi.  
  
 jQuery on JavaScript-kehittäjien käyttämä hyvin yleinen kirjasto. jQueryn käytön suurin hyöty on se, että se tarjoaa kehittäjälle helpomman tavan käyttää ja luoda DOM-elementtejä. Juuri tätä emme kuitenkaan tue Common Data Service for Apps -sovellussivuilla. jQuerya suositellaan, kun kehittäjät luovat mukautettuja käyttöliittymiä HTML-verkkoresursseilla. PowerApps-sovellussivuilla tuetut ohjelmointirajapinnat eivät kuitenkaan edellytä jQueryn käyttöä.  
  
 **Minkä tahansa dokumentoimattoman objektin tai menetelmän käyttö JavaScriptillä**  
Common Data Service for Apps käyttää monia JavaScript-objekteja sivuilla. JavaScript-kehittäjä voi selvittää ne objektit suorittamalla sivun virheenkorjauksen ja käyttämällä sitten näitä objekteja uudelleen. Pidätämme oikeuden tehdä mitä tahansa tarvittavia muutoksia näihin objekteihin, mukaan lukien niiden poistaminen tai nimien vaihtaminen. Jos komentosarja viittaa tällaisiin objekteihin, komentosarja ei toimi, jos niitä ei löydy.  <a name="BKMK_Metadata"></a>   
 
<a name="BKMK_CombineCustomizations"></a>   
## <a name="combine-customization-capabilities"></a>Mukautustoimintojen yhdistäminen  
 Näissä osioissa kuvataan yksittäisiä mukautustoimintoja melko tarkasti. On kuitenkin tärkeää muistaa se, että ratkaisut liiketoiminnallisten tarpeidesi täyttämiseen käyttävät usein näitä toimintoja yhdessä muiden toimintojen kanssa.  
  
<a name="BKMK_ChooseTheRightCustomization"></a>   
### <a name="choose-the-right-customization-capability-for-the-job"></a>Tarkoitukseen soveltuvan mukautustoiminnon valitseminen  
 Koska PowerApps tarjoaa niin monia erilaisia mukautustoimintoja, voit joutua helposti tilanteeseen, jossa opettelet niistä hyvin vain yhden ja pyrit sitten ratkaisemaan jokaisen ongelman sen avulla. Kun tarkastelet liiketoiminnallisia ongelmia, joita haluat ratkaista, mieti lopputulosta, jonka haluat saavuttaa. Lähde sitten siitä taaksepäin ja analysoi, miten pääset tähän tulokseen.  
 
<a name="BKMK_changesinperformance"></a>   
## <a name="changes-that-affect-common-data-service-for-apps-environment-performance"></a>Common Data Service for Apps -ympäristön suorituskykyyn vaikuttavat muutokset  
 Ratkaisujen tuominen ja metatietojen muuttamiseen kykenevien mukautusten käyttöönotto voivat vaikuttaa Common Data Service for Apps -ympäristön suorituskykyyn. Järjestelmän normaaliin toimintaan voivat vaikuttaa esimerkiksi seuraavat toiminnot:  
  
-   entiteettien, vaihtoehtoisten avaimien, määritteiden ja suhteiden lisääminen, poistaminen sekä muuttaminen   
-   ratkaisujen tuominen
  
-   mukautusten julkaiseminen. 
  
Jos teet tällaisia muutoksia hyötykäytössä olevaan järjestelmään, suosittelemme, että teet nämä muutokset sellaisina ajankohtina, jolloin ne aiheuttavat mahdollisimman vähän häiriötä käyttäjille.   
  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
[Mitä PowerAppsin malliin perustuvat sovellukset ovat?](../../maker/model-driven-apps/model-driven-app-overview.md)


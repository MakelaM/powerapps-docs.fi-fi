---
title: Ratkaisujen käyttäminen PowerAppsissa | MicrosoftDocs
description: Lisätietoja sovellusten luomisesta ja muokkaamisesta ratkaisujen avulla
ms.custom: ''
ms.date: 10/29/2018
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
ms.assetid: 72bacfbb-96a3-4daa-88ff-11bdaaac9a3d
caps.latest.revision: 57
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-solutions-in-powerapps"></a>Ratkaisujen käyttäminen PowerAppsissa

 Voit tarkastella ratkaisuluetteloja PowerAppsissa valitsemalla vasemmassa siirtymisruudussa **Ratkaisut**. Voit sitten valita ratkaisun ja tarkastella sen kaikkia osia. 
 
> [!NOTE]
>  Ratkaisukokemus on käytettävissä vain verkossa, kun ympäristöversio on vähintään 9.1.0.267. Voit tarkistaa version valitsemalla [PowerAppsin hallintakeskuksessa](https://admin.powerapps.com/) Ympäristöt > ympäristön valinta > Tiedot-välilehti. Jos ratkaisun valitsee aiemmassa ympäristössä, se avautuu perinteisenä käyttökokemuksena. 

> [!div class="mx-imgBorder"]  
> ![Kaikki osat sisältävä esittelyratkaisu](media/solution-all-items-list.PNG "Kaikki osat sisältävä esittelyratkaisu")  
  
 
 Voit selata ratkaisun kaikkia osia kohteita vierittämällä. Jos luettelossa on yli 100 kohdetta, näet lisää kohteita valitsemalla **100 seuraavan kohteen lataaminen**. 
 
> [!div class="mx-imgBorder"]  
> ![Osia ladataan lisää](media/load-more.PNG "Osia ladataan lisää")  

 ## <a name="search-and-filter-in-a-solution"></a>Haku ja suodatus ratkaisussa
 
 Voit myös hakea tiettyä osaa osan nimellä. 
 
> [!div class="mx-imgBorder"]  
> ![Osan haku](media/solution-search-box.PNG "Osan haku")  
 
 Voit lisäksi suodattaa luettelon kaikkia kohteita osan tyypin mukaan.
  
> [!div class="mx-imgBorder"]  
> ![Osan suodatus tyypin mukaan](media/solution-filter.PNG "Osan suodatus tyypin mukaan")  
 
 ## <a name="contextual-commands"></a>Tilannekohtaiset komennot
 
 Kun valitset osan, komentopalkissa olevat toiminnot muuttuvat valitun osan tyypin mukaan. Toimintoihin vaikuttaa myös se, onko kyse oletusratkaisusta vai hallitusta ratkaisusta. 
 
> [!div class="mx-imgBorder"]  
> ![Osakohtaiset komennot](media/component-commands.PNG "Osakohtaiset komennot")  
 
 Jos et valitse mitään osaa, komentopalkin toiminnot liittyvät ratkaisuun. 
 
> [!div class="mx-imgBorder"]  
> ![Ratkaisukohtaiset komennot](media/solution-commands.PNG "Ratkaisukohtaiset komennot")  
 
 ## <a name="create-components-in-a-solution"></a>Osien luominen ratkaisussa
 Riippumatta siitä, onko kyse hallitsemattomasta ratkaisusta vai oletusratkaisusta, voit luoda erityyppisiä osia **Uusi**-komennolla. Käytettävä luontikokemus määräytyy valitun osatyypin mukaan. Kun olet luonut osan, se lisätään ratkaisuun. 
 
> [!div class="mx-imgBorder"]  
> ![Uuden osan luonti ratkaisussa](media/solution-new-component.PNG "Uuden osan luonti ratkaisussa")  
 
 ## <a name="add-an-existing-component-to-a-solution"></a>Aiemmin luodun osan lisääminen ratkaisuun
 
 Jos ratkaisu on hallitsematon eikä oletusratkaisu, voit tuoda **Lisää aiemmin luotu** -komennolla osia, joita ratkaisussa ei vielä ole.  
 
> [!div class="mx-imgBorder"]  
> ![Aiemmin luodun osan lisääminen ratkaisuun](media/solution-add-existing-component.PNG "Aiemmin luodun osan lisääminen ratkaisuun")  
  
 Hallituissa ratkaisuissa komentoja ei ole käytettävissä ja näytössä on seuraava sanoma. Osa on etsittävä **Oletusratkaisu**-nimisestä ratkaisusta, jossa voit yrittää muokata sitä tai lisätä sen toiseen luomaasi ei-hallittuun ratkaisuun. Osaa ei ehkä voi mukauttaa. Lisätietoja: [Hallitut ominaisuudet](solutions-overview.md#managed-properties)

> [!div class="mx-imgBorder"]  
> ![Hallittu ratkaisu](media/managed-solution.PNG "Hallittu ratkaisu")  

 Monet tehtävät mukautukset koskevat entiteettejä. Voit näyttää **Entiteetit**-suodattimen avulla luettelon kaikista nykyisessä ratkaisussa entiteeteistä, joita voi mukauttaa jollain tavalla. Kun poraudut entiteettiin, näkyviin tulee entiteettiin kuuluvat ratkaisun osat, kuten seuraavassa kuvassa oleva asiakasentiteetti. 
 
> [!NOTE]
>  Kun tällä hetkellä lisäät aiemmin luodun entiteetin ratkaisuun, järjestelmä lisää automaattisesti entiteettiin kuuluvat osat ratkaisuun. Jos et halua, että näin tapahtuu, siirry perinteiseen käyttökokemukseen valitsemalla **Siirry perinteiseen** ja lisää vain haluamasi osat. <!-- We will soon improve this experience from PowerApps and allow you to select only the specific component(s) under entity that you want to add into a solution. -->
  
> [!div class="mx-imgBorder"]  
> ![Esittelyratkaisu, jossa näkyy laajennettu asiakasentiteetti](media/solution-entity-account.PNG "Esittelyratkaisu, jossa näkyy laajennettu asiakasentiteetti")  

## <a name="classic-solution-explorer"></a>Perinteiden ratkaisunhallinta

Voit avata PowerAppsissa perinteisen ratkaisunhallinnan valitsemalla vasemmassa siirtymisruudussa **Ratkaisut** ja valitsemalla sitten komentopalkissa **Siirry perinteiseen**. Perinteinen ratkaisunhallinta oli aiemmin käytettävissä valitsemalla PowerAppsissa **Asetukset > Lisämukautukset**. Jos olet Dynamics 365 for Customer Engagement -käyttäjä, käsittelet ratkaisuja perinteisessä ratkaisunhallinnassa.  

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Hallitun ratkaisun poistaminen ei poista kaaviosovellusta PowerAppsista.
- Ratkaisussa ei voi käyttää mukautettuja yhdysohjelmia.
- Kaaviosovellus on avattava ratkaisun tuonnin jälkeen, jotta yhteyden päivittyvät.
- Lisätty aiemmin luotu SDK-kokoonpano ei näy ratkaisussa. 
- Jos kaaviosovellukset on pakattu hallittuun ratkaisuun, järjestelmänvalvojat voivat edelleen muokata niitä uudessa ympäristössä.
- Riippuvuuksia ei voi käyttää kaaviosovelluksissa.
- Hallitun ratkaisun poistaminen ei johda palautumiseen toiseen kaaviosovelluksen versioon. 
-   Kaaviosovelluksen käyttöoikeuksia (CRUD ja suojaus) hallitaan kokonaisuudessaan PowerApps-tietokannasta eikä Common Data Service -tietokannasta.
-   CDS-ohjelmointirajapinnat, joilla kaaviosovelluksia kutsutaan, on estetty eikä niiden kautta palauteta mitään. 
-   Ratkaisussa luotua kaaviosovellusta ei voi vielä jakaa rinnakkaisomistajana AAD-käyttöoikeusryhmälle.
-   Kaaviosovellukset eivät näy perinteisessä ratkaisunhallinnassa. 
-   Aiemmin luodut kaaviosovellukset eivät ole ratkaisukohtaisia. 

 Lisätietoja ratkaisun yksittäisten osien mukauttamisesta on seuraavissa ohjeaiheissa:  
  
-   Lisätietoja entiteetin, entiteettisuhteiden, kenttien ja sanomien mukauttamisesta on ohjeaiheessa [Metatiedot](create-edit-metadata.md).  
  
-   Lisätietoja entiteettilomakkeista on ohjeaiheessa [lomakkeet](../model-driven-apps/create-design-forms.md).  
  
-   Lisätietoja prosesseista on ohjeaiheessa [Prosessit](../model-driven-apps/guide-staff-through-common-tasks-processes.md).  
  
-   Saat tietoa Liiketoimintasäännöistä aiheesta [Liiketoimintasäännöt](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md).  

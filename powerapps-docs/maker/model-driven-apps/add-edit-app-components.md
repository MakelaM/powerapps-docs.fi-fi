---
title: 'Opastusohjelma, jossa kerrotaan mallipohjaisen sovelluksen osien lisäämisestä ja muokkaamisesta PowerAppsin avulla | MicrosoftDocs'
description: Osien lisääminen tai muokkaaminen PowerAppsin sovellusten suunnitteluohjelmassa
keywords: ''
ms.date: 03/30/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: be93b9d7-f1c2-4ee7-8d7c-0f5c34dfa5f7
ms.author: matp
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 17
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-add-or-edit-model-driven-app-components-in-the-powerapps-app-designer"></a>Opastusohjelma: Mallipohjaisen sovelluksen osien lisääminen ja muokkaaminen PowerAppsin avulla sovellusten suunnitteluohjelmassa

Tässä opetusohjelmassa kerrotaan, miten mallipohjaisessa sovellukseen lisätään ja poistetaan osia. 

Mallipohjainen sovellus koostuu eri osista. Sovellukseen voi lisätä kahden tyyppisiä osia: artefakteja ja entiteettiresursseja. Sovelluksen suunnitteluohjelmassa entiteetit, koontinäytöt ja liiketoimintaprosessit ovat sovelluksen artefakteja. Entiteettiresurssit koostuvat lomakkeista, näkymistä, kaavioista ja koontinäkymistä.  
  
Sovelluksen suunnitteluohjelma viittaa aiemmin määritettyihin metatietoihin oletusratkaisussa. Sen avulla voi luoda komponentteja, kuten lomakkeita, näkymiä, kaavioita ja koontinäyttöjä  
  
## <a name="app-designer-layout"></a>Sovelluksen suunnitteluohjelman asettelu  
 Sovelluksen suunnitteluohjelmassa on kaksi pääaluetta. Vasemmalla puolella on alusta, johon sovelluksen komponentit lisätään.  
  
![Sovelluksen suunnitteluohjelman kaavio](../model-driven-apps/media/app-designer-canvas-pane.png)

 Oikealla puolella ovat välilehdet, joita käytetään komponenttien valitsemisessa ja niiden ominaisuuksien määrittämisessä.  
 
 > [!div class="mx-imgBorder"]
 > ![Sovellusten suunnitteluohjelman komponentit](../model-driven-apps/media/app-designer-canvas-components-tab.png "Sovellusten suunnitteluohjelman komponentit")  
  
 Alustalla on sivustokartan, liiketoimintaprosessin, koontinäytön ja entiteettien alue. Kun valitset koontinäytön tai liiketoimintaprosessin tai määrität sivustokartan, sovelluksen suunnitteluohjelma lisää näissä komponenteissa käytettävät entiteetit automaattisesti. Kun entiteetit ovat paikoillaan, sinun on vain valittava kukin entiteetti ja lisättävä pakolliset entiteetin resurssit, kuten lomakkeet, näkymät ja kaaviot.
 
 Voit myös käyttää **Hae kaaviosta** hakeaksesi komponentteja kaaviosta. Kun valitset **Hae kaaviosta**, ponnahdusikkunahaku avautuu uuteen välilehteen oikealla puolella välilehden oikeanpuoleisessa ruudussa.   
 
 > [!div class="mx-imgBorder"]
 > ![Kaavion hakuvaihtoehto](media/app-designer-search-tab.png "Kaavion hakuvaihtoehto")

## <a name="open-an-app"></a>Sovelluksen avaaminen
1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/) -sovellukseen. 

2. Valitse **Mallipohjainen** > **Sovellukset** ja valitse sitten olemassa oleva sovellus tai **Luo sovellus** -kohta. Lisätietoja sovelluksen luomisesta on kohdassa [Mallipohjaisen sovelluksen luominen tai muokkaaminen sovellusten suunnitteluohjelmalla](create-edit-app.md#create-an-app).

## <a name="add-an-artifact-entity-dashboard-or-business-process-flow"></a>Artefaktin (entiteetti, koontinäyttö tai liiketoimintaprosessi) lisääminen  
 Kun lisäät sovellukseen koontinäytön tai liiketoimintaprosessin, niiden käyttämät entiteetit lisätään automaattisesti sovellukseen. Kun lisäät entiteetin, sen resurssien ruudut lisätään automaattisesti. Artefaktit voidaan lisätä suunnitteluohjelman pohjaan kahdella tavalla: komentopalkin **Lisää**-painikkeella ![Lisää suunnitteluohjelman painike](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Lisää suunnitteluohjelman painike") tai **Osat**-välilehden ruutujen avulla.  
  
 Koontinäyttö lisätään sovellukseen seuraavasti. Liiketoimintasovellus tai entiteetti lisätään samalla tavalla.  
  
1.  Napsauta sovelluksen suunnitteluohjelman pohjassa **Koontinäytöt**-ruutua.  
  
     Suunnitteluohjelman pohjan oikeassa ruudussa näkyvät ne koontinäytöt, jotka ovat käytettävissä oletusratkaisussa.  
  
    > [!TIP]
    >  Vaihtoehtoisesti voit toimia myös seuraavasti:  
    >   
    > - Valitse **Lisää** ![Lisää-painike suunnitteluohjelmassa](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Lisää-painike suunnitteluohjelmassa") ja valitse sitten **Koontinäytöt**.  
    > - Valitse **Komponentit**-välilehdessä **Artefaktit**-kohdassa **Koontinäytöt**.  
  
2.  Kirjoita **hakuruutuun** joitakin avainsanoja, jotka liittyvät etsittävään koontinäyttöön.  
  
     Koontinäyttöluettelo suodatetaan niin, että vain avainsanaa vastaavat tulokset näkyvät.  
  
3.  Jos haluat, että käyttäjät näkevät vain valitut koontinäytöt, valitse lisättävien koontinäyttöjen valintaruudut Voit valita seuraavista koontinäyttötyypeistä:
    - **Perinteiset koontinäytöt** näkyvät sekä Unified Interface -sovelluksessa että verkkosovelluksessa.
    - **Vuorovaikutteiset koontinäytöt** näkyvät vain Unified Interface -sovelluksessa. Jos olet valinnut asiakasohjelmatyypin sovellukseen verkkosovelluksena **vuorovaikutteisen koontinäytön** vaihtoehtoa ei näytetä.

     Kyseiset koontinäytöt lisätään sovelluksen suunnitteluohjelman pohjan **koontinäyttöruutuun**. **Koontinäyttöruudussa** näkyy myös sovellukseen lisättyjen koontinäyttöjen määrä. Jos et valitse koontinäyttöä, koontinäytön määrän sijaan näkyvissä on **kaikki** ja kaikki koontinäytöt ovat sovelluksen käyttäjien käytettävissä.  
  
     Kaikki entiteetit, jotka ovat koontinäytön käytössä, lisätään myös **Entiteettinäkymä**-alueelle. Jos lisäät esimerkiksi asiakaspalvelupäällikön koontinäytön, palvelupyyntö-, oikeus- ja jonokohde-entiteetti lisätään myös Entiteettinäkymä-alueelle. Lisäksi kunkin entiteetin resursseille lisätään ruudut. Voit käyttää näitä ruutuja lomakkeiden, näkymien ja kaavioiden lisäämiseen. Lisätietoja: [Sovelluksen osien lisääminen tai muokkaaminen PowerAppsin sovellusten suunnitteluohjelmassa](add-edit-app-components.md#bkmk_AddEntityAssets)   
  
    ![kohteen lisääminen sovellusten suunnitteluohjelman pohjaan](../model-driven-apps/media/add-entity-app-designer-canvas.png "kohteen lisääminen sovellusten suunnitteluohjelman pohjaan")  
  
4.  Jos oletusratkaisussa ei ole koontinäyttöä, jota haluat käyttää, luo koontinäyttö valitsemalla **Luo uusi** oikealla olevassa **Osat**-välilehdessä.  
  
     > [!div class="mx-imgBorder"]
     > ![Luo uusi sovellusten suunnitteluohjelman komponentit-välilehden linkki](../model-driven-apps/media/app-designer-components-tab-create-new.png "Luo uusi sovellusten suunnitteluohjelman komponentit-välilehden linkki")  
  
     Koontinäytön suunnitteluohjelma avautuu. Lisätietoja: [Koontinäyttöjen luominen ja muokkaaminen](create-edit-dashboards.md)  
  
    > [!NOTE]
    > - Kun lisäät uutta liiketoimintaprosessia tai entiteettiä, **Luo uusi** -vaihtoehto avautuu vastaavassa suunnitteluohjelmassa. Lisätietoja liiketoimintaprosessien ja entiteettien luomisesta on kohdissa [Liiketoimintaprosessin luominen](/flow/create-business-process-flow) ja [Mukautetun entiteetin luominen](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-create-entity).  
      
  
5.  Kun olet lisännyt tarvittavat artefaktit, valitse komentopalkissa **Tallenna**.  
  
<a name="bkmk_AddEntityAssets"></a>   
## <a name="add-entity-assets-forms-views-charts-or-dashboards"></a>Entiteetin resurssien (lomakkeiden, näkymien, kaavioiden tai koontinäyttöjen lisääminen)  
 Kun artefaktit ovat paikoillaan, voit lisätä sovellukseen entiteettien resursseja, kuten lomakkeita, näkymiä, kaavioita ja koontinäyttöjä.
Lisäksi käytettäessä Unified Interface -asiakasta voit myös lisätä koontinäytön entiteettiresurssit sovellukseen.  
  
 Tässä osassa kerrotaan, miten lomake lisätään sovellukseen. Samalla tavalla sovellukseen lisätään näkymä tai kaavio.  
  
1.  Napsauta sovelluksen suunnitteluohjelman pohjassa lomakkeeseen lisättävän entiteetin **Lomakkeet**-ruutua.  
  
     Entiteetin koko rivi valitaan sovelluksen suunnitteluohjelman pohjassa. Oikealla puolella näkyvät valitun entiteetin kaikki aiemmin luodut lomakkeet.  
  
    > [!NOTE]
    >  Vaihtoehtoisesti voit toimia myös seuraavasti:  
    >   
    > - Valitse **Lisää** ![Lisää-painike suunnitteluohjelmassa](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Lisää-painike suunnitteluohjelmassa") ja valitse sitten **Lomakkeet**.  
    > - Valitse **Komponentit**-välilehdessä **Entiteetin resurssit**-kohdassa **Lomakkeet**.  
  
    > [!TIP]
    >  Kaikilla valituilla entiteeteillä on **lisäasetukset**-painike (**...**), joka näkyy **Valitse entiteetit** -luettelossa **osat**-välilehdessä. Jos haluat lisätä kaikki valitun entiteetin resurssit, valitse **lisäasetukset** (**...**) ja valitse sitten **lisää kaikki resurssit**.  
  
2.  Jos haluat, että sovelluksen käyttäjät näkevät vain valitut lomakkeet, valitse lisättävien lomakkeiden valintaruudut. Lomakkeet määrittävät, miten käyttäjät näkevät sovelluksen tiedot ja käsittelevät niitä. 
 
     Valitun entiteetin lomakeruudussa näkyy lisättyjen lomakkeiden määrä.  
  
     ![Palvelupyyntöentiteetin lomakkeen toimintoruutu](../model-driven-apps/media/add-forms-entity.png "Palvelupyyntöentiteetin lomakkeen toimintoruutu")  
  
     Jos et valitse entiteetille lomaketta, kyseisen entiteetin kaikki lomakkeet näkyvät käyttäjille, kun he käyttävät sovellusta. Tämä toiminto on vastaava näkymille ja kaavioille myös, jos ei näkymää tai kaaviota ole valittuna. Näin voit luoda sovelluksia nopeasti, kun käsittelet kaikkia käytettävissä olevia komponentteja. Kutakin komponenttia ei siis tarvitse valita sovelluksen suunnitteluohjelmassa.  

     Jos koontinäyttöjä tai liiketoimintaprosesseja ei ole valittu, kaikki koontinäytöt ja liiketoimintaprosessit ovat käyttäjien käytettävissä, kun he käyttävät sovellusta.
  
    > [!NOTE]
    > Suoritettavan sovelluksen jokaisella lisätyllä entiteetillä on oltava vähintään yksi aktiivinen lomake. Jos olet valinnut useita lomakkeita, käytetään oletusratkaisussa ensimmäisenä näkyvää aktiivista lomaketta, kun käyttäjät suorittavat sovelluksen.  
  
3.  Jos haluat lisätä uuden lomakkeen, joka ei ole luettelossa, valitse **Luo uusi**.  
  
     Valitse avattavasta luettelosta luotavan lomakkeen tyyppi.  
  
    > [!NOTE]
    >  Avattava luettelo on käytettävissä vain lomakkeiden lisäämisen yhteydessä. Se ei ole käytettävissä näkymien ja kaavioiden lisäämisen yhteydessä.  
  
     Lomakkeen suunnitteluohjelma avautuu. Lisätietoja: [Lomakkeiden luominen ja suunnittelu](create-design-forms.md)  
  
     Kun lisäät näkymää tai kaaviota, **Luo uusi** -vaihtoehto avautuu vastaavassa suunnitteluohjelmassa. Lisätietoja: [Tietoja näkymistä](create-edit-views.md) ja [Järjestelmäkaavion luominen ja muokkaaminen](create-edit-system-chart.md)  
  
    > [!NOTE]
    >  Kun lisäät näkymän, voit viitata vain julkisiin näkymiin, jotka sijaitsevat ratkaisunhallinnan **Näkymät**-solmussa.  
  
4. Valitse alanuoli ![avattava kuvake](../model-driven-apps/media/drop-down-icon.png "alanuoli") ja laajenna ruutu ja nähdäksesi luettelo lomakkeista, jotka on lisätty.  
  
     ![Sovellusten suunnitteluohjelmassa laajennetaan lomakkeen komponenttiruutu](../model-driven-apps/media/app-designer-expanded-form-tile.png "Sovellusten suunnitteluohjelmassa laajennetaan lomakkeen komponenttiruutu")  
  
5.  Toista nämä vaiheet, kun haluat lisätä sovellukseen entiteetin näkymiä ja kaavioita.  
  
6.  Valitse **Tallenna**.  
  
## <a name="edit-or-remove-artifacts"></a>Artefaktien muokkaaminen tai poistaminen  
  
- Voit muokata koontinäyttöä tai yrityksen prosessin työnkulkua valitsemalla alanuolen ![avattava kuvake](../model-driven-apps/media/drop-down-icon.png "alanuoli") laajentaaksesi ruutua ja valitse sitten sivustokartan suunnitteluohjelman painike ![Avaa sivustokartan suunnitteluohjelma painike](../model-driven-apps/media/dynamics365-open-designer.PNG "Avaa sivustokartan suunnitteluohjelman painike"), joka vastaavat koontinäyttöä tai työprosessin työnkulkua, jota haluat muokata.  
  
     Valitun artefaktin suunnitteluohjelma avautuu.  
  
- Voit poistaa koontinäytön tai yrityksen prosessityönkulun valitsemalla alanuolen ![avattava kuvake](../model-driven-apps/media/drop-down-icon.png "alanuoli") laajentaaksesi ruudun ja valitsemalla sitten koontinäytön tai yrityksen prosessin työnkulun, jonka haluat poistaa. Valitse komentopalkissa **Poista**.  

    Toinen tapa poistaa koontinäyttö tai työ liiketoimintaprosessin työnkulkuja on poistaa valinta **osia** välilehden vastaavasta valintaruudusta.
  
- Voit muokata entiteettiä tai poistaa sen valitsemalla entiteettiruudun ja valitsemalla sitten komentopalkissa **Muokkaa** tai **Poista**. Kun muokkaat entiteettiä, ratkaisunhallinta avautuu. Voit muuttaa entiteettiä siellä.  
  
     Voit vaihtoehtoisesti poistaa osan valitsemalla koontinäytön tai liiketoimintaprosessin tai entiteetin ruudun Poista suunnitteluohjelmasta poistettavan artefaktin valintaruudun valinta **Komponentit**-väliehdestä.  
  
    > [!NOTE]
    >  Kun teet muutoksia entiteettiin, vaikkapa muutat entiteetin näyttönimeä tai kuvausta, muutokset eivät sovelluksen suunnitteluohjelmassa, ellei muutoksia julkaista ratkaisunhallinnassa.  
  
## <a name="edit-or-remove-entity-assets"></a>Entiteetin resurssien muokkaaminen tai poistaminen  

### <a name="edit-entity-assets"></a>Entiteetin resurssien muokkaaminen
  
1. Valitse alanuolta ![avattava kuvake](../model-driven-apps/media/drop-down-icon.png "alanuoli") Laajenna komponenttiruutu lomakkeita, näkymiä, kaavioita tai koontinäyttöjä varten.  
  
2. Valitse muokattava lomake, näkymä, kaavio tai koontinäyttö.  
  
3. Valitse komentopalkissa **Muokkaa**.

   tai

   Valitsemalla sivuston suunnitteluohjelman painikkeen ![Avaa sivustokartan suunnitteluohjelma -painike](../model-driven-apps/media/dynamics365-open-designer.PNG "Avaa sivustokartan suunnitteluohjelma -painike"), joka vastaa lomaketta, näkymää, kaaviota tai koontinäyttöä.  

### <a name="remove-entity-assets"></a>Entiteetin resurssien poistaminen  

1. Valitse alanuolta ![avattava kuvake](../model-driven-apps/media/drop-down-icon.png "alanuoli") Laajenna komponenttiruutu lomakkeita, näkymiä, kaavioita tai koontinäyttöjä varten.  
  
2. Valitse muokattava lomake, näkymä, kaavio tai koontinäyttö.

3. Valitse komentopalkissa **Poista**. 

Vaihtoehtoisesti voit valita lomakkeet, näkymät, kaaviot tai koontinäyttöruudun ja valita **Osat**-valintaruudussa poistaa valinnat resursseilta, jotka haluat poistaa suunnitteluohjelmasta.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Sovelluksen sivustokartan luominen](create-site-map-app.md) </br>  
 [Sovelluksen tarkistaminen ja julkaiseminen](validate-app.md)

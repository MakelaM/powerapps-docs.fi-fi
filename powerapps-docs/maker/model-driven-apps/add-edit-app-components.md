---
title: Opetusohjelma malliin perustuvan sovelluksen osien lisäämiseen tai muokkaamiseen PowerAppsilla | MicrosoftDocs
description: PowerAppsin sovellusten suunnitteluohjelman avulla voit lisätä tai muokata osia
keywords: ''
ms.date: 03/30/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
author: Mattp123
ms.assetid: be93b9d7-f1c2-4ee7-8d7c-0f5c34dfa5f7
ms.author: matp
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 17
topic-status: Drafting
ms.openlocfilehash: 87fec3bff3ad21a5c0474b67f001cca5c902d609
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679939"
---
# <a name="tutorial-add-or-edit-model-driven-app-components-in-the-powerapps-app-designer"></a>Opetusohjelma: Malliin perustuvan sovelluksen osien lisääminen tai muokkaaminen PowerAppsin sovellusten suunnitteluohjelmassa

Tässä opetusohjelmassa opit lisäämään osia sekä poistamaan niitä malliin perustuvasta sovelluksesta. 

Malliin perustuva sovellus koostuu eri osista. Voit lisätä sovellukseen kahdenlaisia osia: artefakteja ja entiteettiresursseja. Sovellusten suunnitteluohjelmassa entiteetit, koontinäyttö ja liiketoimintaprosessit ovat kaikki sovelluksen artefakteja. Entiteettiresurssit koostuvat lomakkeista, näkymistä, kaavioista ja koontinäytöistä.  
  
Sovellusten suunnitteluohjelma viittaa oletusratkaisujen olemassa oleviin metatietoihin. Sen avulla voit luoda osia, kuten lomakkeita, näkymiä, kaavioita ja koontinäyttöjä.  
  
## <a name="app-designer-layout"></a>Sovellusten suunnitteluohjelman asettelu  
 Sovellusten suunnitteluohjelmassa on kaksi pääaluetta. Vasemmalla puolella on pohja, johon voit lisätä sovelluksen osia.  
  
![Sovellusten suunnitteluohjelman pohja](../model-driven-apps/media/app-designer-canvas-pane.png)

 Oikealla puolella ovat välilehdet, joissa voit valita osia ja määrittää osien ominaisuuksia.  
  
 ![Sovellusten suunnitteluohjelman osat](../model-driven-apps/media/app-designer-canvas-components-tab.png "Sovellusten suunnitteluohjelman osat")  
  
 Pohjassa on näkyvissä sivustokartan, liiketoimintaprosessin, koontinäytön ja entiteettien alueet. Kun valitset koontinäytön tai liiketoimintaprosessin tai määrität sivustokartan, sovellusten suunnitteluohjelma lisää automaattisesti pohjaan entiteetit, joita käytetään näissä osissa. Kun entiteetit ovat paikallaan, sinun tarvitsee vain valita kukin entiteetti ja lisätä vaadittuja entiteettiresursseja, kuten lomakkeita, näkymiä ja kaavioita.
 
 Voit myös etsiä osia pohjasta **Hae pohjasta** -toiminnolla. Kun valitset **Hae pohjasta** -toiminnon, välilehtien oikealle puolelle oikeanpuolimmaiseen ruutuun aukeaa uusi hakuvälilehti.   
  
 ![Pohjan hakutoimintoa](media/app-designer-search-tab.png "Pohjan haku")

## <a name="open-an-app"></a>Sovelluksen avaaminen
1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com/). 

2. Valitse **Malliin perustuvat** > **sovellukset** ja valitse sitten olemassa oleva sovellus tai valitse **Luo sovellus**. Lisätietoja sovelluksen luomisesta on kohdassa [Malliin perustuvan sovelluksen luominen tai muokkaaminen sovellusten suunnitteluohjelmalla](create-edit-app.md#create-an-app).

## <a name="add-an-artifact-entity-dashboard-or-business-process-flow"></a>Lisää artefakti (entiteetti, koontinäyttö tai liiketoimintaprosessi)  
 Kun lisäät koontinäytön tai liiketoimintaprosessin sovellukseen, niiden käyttämät entiteetit lisätään automaattisesti sovellukseen. Kun entiteetti lisätään, sen resurssien ruudut lisätään automaattisesti. Voit lisätä artefakteja suunnittelutoiminnon pohjaan kahdella tavalla: käyttämällä **Lisää**-painiketta ![Suunnittelutoiminnon Lisää-painike](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Suunnittelutoiminnon Lisää-painike") komentopalkissa tai käyttämällä **Osat**-välilehden ruutuja.  
  
 Seuraavassa ovat ohjeet koontinäytön lisäämiseksi sovellukseen. Käytä samoja vaiheita liiketoimintaprosessin tai entiteetin lisäämiseen.  
  
1.  Valitse sovellusten suunnitteluohjelman pohjassa **Koontinäytöt**-ruutu.  
  
     Sovellusten suunnitteluohjelman pohjan oikeanpuolimmaisessa ruudussa ovat näkyvissä koontinäytöt, jotka ovat käytettävissä oletusratkaisussa.  
  
    > [!TIP]
    >  Vaihtoehtoisesti voit myös tehdä jonkin seuraavista:  
    >   
    > - Valitse **Lisää** ![Suunnittelutoiminnon Lisää-painike](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Suunnittelutoiminnon Lisää-painike") ja valitse sitten **Koontinäytöt**.  
    > - Valitse **Osat**-välilehdessä **Artefaktit**-kohdassa **Koontinäytöt**.  
  
2.  Kirjoita **haku**ruutuun muutama avainsana etsimäsi koontinäytön nimestä.  
  
     Koontinäytön luettelo suodatetaan näyttämään avainsanoja vastaavat tulokset.  
  
3.  Jos haluat käyttäjiesi käyttävän vain valittuja koontinäyttöjä, valitse valintaruutu lisättävien koontinäyttöjen kohdalla. Voit valita seuraavista koontinäyttöjen tyypeistä:
    - **Perinteiset koontinäytöt** näkyvät sekä verkkosovelluksessa että Unified Interface -sovelluksessa.
    - **Vuorovaikutteiset koontinäytöt** näkyvät vain Unified Interface -sovelluksessa. Jos olet valinnut sovelluksen asiakastyypiksi verkkosovellus, **Vuorovaikutteiset koontinäytöt** -vaihtoehto ei ole näkyvissä.

     Nämä koontinäytöt lisätään **Koontinäyttö**-ruutuun sovellusten suunnitteluohjelman pohjassa. **Koontinäyttö**-ruudussa näkyy myös sovellukseen lisättyjen koontinäyttöjen määrä. Jos et valitse koontinäyttöä, näkyvissä on **Kaikki** koontinäytön määrän sijaan, ja kaikki koontinäytöt ovat käytettävissä käyttäjille, kun he käyttävät sovellusta.  
  
     Kaikki koontinäytön käyttämät entiteetit lisätään myös **Entiteettinäkymä**-alueelle. Esimerkiksi jos lisäät Asiakaspalvelupäällikkö-koontinäytön, Palvelupyyntö-, Oikeudet- ja Jono-entiteetit lisätään Entiteettinäkymä-alueelle. Jokaista entiteettiä kohden lisätään myös sen resurssiruudut. Näiden ruutujen avulla voit lisätä lomakkeita, näkymiä ja kaavioita. Lisätietoja: [Sovelluksen osien lisääminen tai muokkaaminen PowerAppsin sovellusten suunnitteluohjelmassa](add-edit-app-components.md#bkmk_AddEntityAssets)   
  
    ![Entiteetin lisääminen sovellusten suunnitteluohjelman pohjaan](../model-driven-apps/media/add-entity-app-designer-canvas.png "Entiteetin lisääminen sovellusten suunnitteluohjelman pohjaan")  
  
4.  Jos haluamasi koontinäyttö ei ole oletusratkaisussa, voit luoda koontinäytön valitsemalla **Luo uusi** **Osat**-välilehdessä pohjan oikealla puolella.  
  
     ![Luo uusi -linkki sovellusten suunnitteluohjelman Osat-välilehdessä](../model-driven-apps/media/app-designer-components-tab-create-new.png "Luo uusi -linkki sovellusten suunnitteluohjelman Osat-välilehdessä")  
  
     Raporttinäkymät-ikkunan suunnittelusovellus avautuu. Lisätietoja: [Koontinäyttöjen luominen ja muokkaaminen](create-edit-dashboards.md)  
  
    > [!NOTE]
    > - Kun lisäät liiketoimintaprosessia tai entiteettiä, **Luo uusi** -vaihtoehto avaa vastaavan suunnittelusovelluksen. Lisätietoja liiketoimintaprosessien tai entiteettien luomisesta on kohdissa [Liiketoimintaprosessin luominen](/flow/create-business-process-flow) ja [Mukautetun entiteetin luominen](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-create-entity).  
      
  
5.  Kun olet lisännyt haluamasi artefaktit, valitse komentopalkissa **Tallenna**.  
  
<a name="bkmk_AddEntityAssets"></a>   
## <a name="add-entity-assets-forms-views-charts-or-dashboards"></a>Lisää entiteettiresursseja (lomakkeita, näkymiä, kaavioita tai koontinäyttöjä)  
 Kun artefaktit ovat paikoillaan, voit alkaa lisätä sovellukseen entiteettiresursseja, kuten lomakkeita, näkymiä, kaavioita ja koontinäyttöjä.
Lisäksi jos käytät Unified Interface -asiakasta, voit myös lisätä sovellukseen entiteetin koontinäyttöresursseja.  
  
 Tässä osassa kuvataan vaiheet lomakkeen lisäämiseksi sovellukseen. Samoja vaiheita käyttämällä voit lisätä sovellukseen näkymän tai kaavion.  
  
1.  Valitse sovellusten suunnitteluohjelman pohjassa **Lomakkeet**-ruutu sen entiteetin kohdalla, johon haluat lisätä lomakkeen.  
  
     Sovellusten suunnitteluohjelman pohjassa entiteetin koko rivi on valittuna. Näet kaikki valitun entiteetin olemassa olevat lomakkeet oikealla puolella.  
  
    > [!NOTE]
    >  Vaihtoehtoisesti voit myös tehdä jonkin seuraavista:  
    >   
    > - Valitse **Lisää** ![Suunnittelutoiminnon Lisää-painike](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Suunnittelutoiminnon Lisää-painike") ja valitse sitten **Lomakkeet**.  
    > - Valitse **Osat**-välilehdessä **Entiteettiresurssit**-kohdassa **Lomakkeet**.  
  
    > [!TIP]
    >  Kaikkien sovellukselle valittujen entiteettien kohdalla on näkyvissä **Lisää vaihtoehtoja** -painike (**...**) **Valitse entiteetit** -luettelossa **Osat**-välilehdessä. Jos haluat lisätä kaikki resurssit valitulle entiteetille, valitse **Lisää vaihtoehtoja** (**...**) ja valitse sitten **Lisää kaikki resurssit**.  
  
2.  Jos haluat sovelluksen käyttäjien käyttävän vain valittuja lomakkeita, valitse valintaruudut lisättävien lomakkeiden kohdalla. Lomakkeet määrittävät, miten käyttäjät voivat tarkastella ja käsitellä tietoja sovelluksessa. 
 
     Valitun entiteetin lomakeruutu näyttää lisättyjen lomakkeiden määrän.  
  
     ![Palvelupyyntöentiteetin lomakeruutu](../model-driven-apps/media/add-forms-entity.png "Palvelupyyntöentiteetin lomakeruutu")  
  
     Esimerkiksi, jos et valitse entiteetille yhtään lomaketta, kaikki kyseisen entiteetin lomakkeet näytetään käyttäjille, kun he käyttävät sovellusta. Toiminta on sama myös näkymien ja kaavioiden kohdalla, jos yhtään näkymää tai kaaviota ei valita. Tämän avulla voit luoda sovelluksia nopeasti, kun haluat käyttää kaikkia käytettävissä olevia osia. Jokaista osaa ei tarvitse valita sovelluksen suunnittelun aikana.  

     Jos yhtään koontinäyttöä tai liiketoimintaprosessia ei valita, kaikki koontinäytöt ja liiketoimintaprosessit ovat saatavana käyttäjille, kun he käyttävät sovellusta.
  
    > [!NOTE]
    > Jotta sovellus suoritetaan, jokaisella lisätyllä entiteetillä on oltava vähintään yksi aktiivinen lomake. Jos olet valinnut useita lomakkeita, ensimmäistä aktiivista oletusratkaisussa näkyvää lomaketta käytetään, kun käyttäjät suorittavat sovelluksen.  
  
3.  Jos haluat lisätä uuden lomakkeen, jota ei ole luettelossa, valitse **Luo uusi**.  
  
     Valitse avattavasta luettelosta luotavan lomakkeen tyyppi.  
  
    > [!NOTE]
    >  Avattava luettelo on käytettävissä vain lomakkeiden lisäämisen aikana. Se ei ole käytettävissä näkymissä tai kaavioissa.  
  
     Lomakkeen suunnitteluohjelma avautuu. Lisätietoja: [Lomakkeiden luonti ja suunnittelu](create-design-forms.md)  
  
     Kun lisäät näkymää tai kaaviota, **Luo uusi** -vaihtoehto avaa vastaavan suunnittelusovelluksen. Lisätietoja: [Tutustu näkymiin](create-edit-views.md) ja [Järjestelmäkaavioiden luonti tai muokkaus](create-edit-system-chart.md)  
  
    > [!NOTE]
    >  Kun lisäät näkymän, voit viitata vain julkisiin näkymiin, jotka on lueteltu **Näkymät**-solmussa ratkaisunhallinnassa.  
  
4. Napsauttamalla alanuolta ![Avattavan luettelon kuvake](../model-driven-apps/media/drop-down-icon.png "alanuoli") voit laajentaa ruudun ja tarkastella lisättyjen lomakkeiden luetteloa.  
  
     ![Lomakeruutu laajennettuna suunnitteluohjelmassa](../model-driven-apps/media/app-designer-expanded-form-tile.png "Lomakeruutu laajennettuna suunnitteluohjelmassa")  
  
5.  Voit lisätä sovellukseen entiteettinäkymiä ja kaavioita toistamalla nämä vaiheet.  
  
6.  Valitse **Tallenna**.  
  
## <a name="edit-or-remove-artifacts"></a>Artefaktien muokkaaminen tai poistaminen  
  
- Voit muokata koontinäyttöä tai liiketoimintaprosessia laajentamalla ruudun alanuolta ![Avattavan luettelon kuvake](../model-driven-apps/media/drop-down-icon.png "alanuoli") napsauttamalla. Valitse sitten sivustokartan suunnitteluohjelman painike ![Avaa sivustokartan suunnitteluohjelma -painike](../model-driven-apps/media/dynamics365-open-designer.PNG "Avaa sivustokartan suunnitteluohjelma -painike"), joka vastaa muokattavaa koontinäyttöä tai liiketoimintaprosessia.  
  
     Valitun artefaktin suunnitteluohjelma avautuu.  
  
- Voit poistaa koontinäytön tai liiketoimintaprosessin laajentamalla ruudun alanuolta ![Avattavan luettelon kuvake](../model-driven-apps/media/drop-down-icon.png "alanuoli") napsauttamalla. Valitse sitten poistettava koontinäyttö tai liiketoimintaprosessi. Valitse komentopalkissa **Poista**.  

    Toinen tapa poistaa koontinäyttö tai liiketoimintaprosessi on poistaa vastaavan valintaruudun valinta **Osat**-välilehdessä.
  
- Voit muokata tai poistaa entiteetin valitsemalla entiteettiruudun ja valitsemalla sitten komentopalkissa **Muokkaa** tai **Poista**. Kun muokkaat entiteettiä, ratkaisunhallinta avautuu, jossa voit tehdä muutoksia entiteettiin.  
  
     Toinen tapa poistaa osa on valita koontinäyttö, liiketoimintaprosessi tai entiteettiruutu. **Osat**-välilehdessä poista valintaruudun valinta niiden artefaktien kohdalla, jotka haluat poistaa suunnitteluohjelmasta.  
  
    > [!NOTE]
    >  Kun teet muutoksia entiteettiin,&mdash;kuten muutat entiteetin näyttönimeä tai kuvausta&mdash;, muutokset eivät näy sovellusten suunnitteluohjelmassa, ellei muutoksia julkaista ratkaisunhallinnassa.  
  
## <a name="edit-or-remove-entity-assets"></a>Entiteettiresurssien muokkaaminen tai poistaminen  

### <a name="edit-entity-assets"></a>Entiteettiresurssien muokkaaminen
  
1. Laajenna ruutu napsauttamalla alanuolta ![Avattavan luettelon kuvake](../model-driven-apps/media/drop-down-icon.png "alanuoli") tuodaksesi näkyviin lomakkeet, näkymät, kaaviot tai koontinäytöt.  
  
2. Valitse lomake, näkymä, kaavio tai koontinäyttö, jota haluat muokata.  
  
3. Valitse komentopalkissa **Muokkaa**.

   tai

   Valitse sivustokartan suunnitteluohjelman painike ![Avaa sivustokartan suunnitteluohjelma -painike](../model-driven-apps/media/dynamics365-open-designer.PNG "Avaa sivustokartan suunnitteluohjelma -painike"), joka vastaa lomaketta, näkymää, kaaviota tai koontinäyttöä.  

### <a name="remove-entity-assets"></a>Entiteettiresurssien poistaminen  

1. Laajenna ruutu napsauttamalla alanuolta ![Avattavan luettelon kuvake](../model-driven-apps/media/drop-down-icon.png "alanuoli") tuodaksesi näkyviin lomakkeet, näkymät, kaaviot tai koontinäytöt.  
  
2. Valitse lomake, näkymä, kaavio tai koontinäyttö, jota haluat muokata.

3. Valitse komentopalkissa **Poista**. 

Vaihtoehtoisesti voit valita lomakkeiden, näkymien, kaavioiden tai koontinäyttöjen ruudun ja sitten **Osat**-välilehdessä poistaa niiden resurssien valintaruutujen valinnan, jotka haluat poistaa suunnitteluohjelmasta.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Sovelluksen sivustokartan luominen](create-site-map-app.md) </br>  
 [Sovelluksen tarkistaminen ja julkaiseminen](validate-app.md)

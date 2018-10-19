---
title: Mallipohjaisen sovelluksen sivustokartan luominen PowerAppsissa | MicrosoftDocs
description: Tietoja sovelluksen sivustokartan luomisesta
keywords: ''
ms.date: 05/29/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 2461bd71-6cb4-46b7-8d1f-6a0aa3dca809
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 18
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-a-model-driven-app-site-map-for-an-app-using-the-site-map-designer"></a>Opetusohjelma: Mallipohjaisen sovelluksen sivustokartan luominen sovellukselle sivustokarttojen suunnitteluohjelman avulla

Tässä opetusohjelmassa suoritetaan useita sivustokarttatehtäviä, kuten uuden sivustokartan luominen ja lisääminen alueeseen, ryhmään ja alialueeseen.

Sivustokartat määrittävät sovelluksen siirtymisvaihtoehdot. Luo sovellukselle sivustokartta helposti ruutuun perustuvan sivustokartan suunnitteluohjelman avulla. Suunnitteluohjelman avulla voit vetää ja pudottaa osia suunnittelukaavioon, esikatsella työn ja julkaista sivustokartan heti. Järjestelmän mukauttajat ja vaaditut oikeudet omaavat käyttäjät voivat luoda sovelluksille sivustokarttoja nopeasti.  
  
Sivustokartan suunnitteluohjelman avulla voidaan myös määrittää alue, alialue ja ryhmän otsikko ympäristön tukemalla kielellä.  
  
Oletussivustokartta on käytettävissä. Sivustokartan suunnitteluohjelman avulla voit muokata tätä sivustokarttaa tai määrittää uusille sovelluksille sivustokartat. Sivustokartan suunnitteluohjelma on integroitu sovelluksen suunnitteluohjelman kanssa.  

## <a name="prerequisites"></a>Edellytykset
Varmista, että sinulla on Järjestelmänvalvoja- tai Järjestelmän mukauttaja -käyttöoikeusrooli tai vastaavat käyttöoikeudet.  Sovelluksia voivat luoda myös kaikki seuraavat oikeudet omaavat käyttäjät:  
-   Sovellusentiteetin luonti-, luku- ja kirjoitusoikeudet  
-   Mukautusentiteetin luku- ja kirjoitusoikeudet  
-   Ratkaisuentiteetin lukuoikeudet

Voit tarkastella näitä oikeuksia tai määrittää niitä käyttöoikeusroolin **Mukautus**-välilehdessä.
  
## <a name="create-a-site-map-for-an-app"></a>Sovelluksen sivustokartan luominen  
  
1. Sovellusten suunnitteluohjelman pohjassa- **sivustokartan** -alueessa valitse **Avaa sivustokartan suunnitteluohjelma** -painike ![Avaa sivustokartan suunnitteluohjelma -painike](media/dynamics365-open-designer.PNG "Avaa sivustokartan suunnitteluohjelma -painike").  
  
     Näyttöön avautuu sivustokartan suunnitteluohjelma, jonka pohjaan on täytetty valmiiksi yksi alue, ryhmä ja alialue. Valitse alueen, ryhmän tai aliryhmän ruutu ja muuta sen ominaisuuksia.  
  
    > [!NOTE]
    >  Kun painat **Avaa sivustokartan suunnitteluohjelma** -painiketta ![Avaa sivustokartan suunnitteluohjelma](media/dynamics365-open-designer.PNG "Avaa sivustokartan suunnitteluohjelma") sovelluksen suunnitteluohjelman kaaviosta, sivustokartta luodaan automaattisesti (jos sovelluksella ei ole sivustokarttaa). Sivustokartalle annetaan sovelluksen nimi ja sovelluksen yksilöivä nimi. 

   ![Valitse sivustokartta](media/app-designer-sitemap-location.png "Valitse sivustokartta") 
  
2.  [Alueen lisääminen sivustokarttaan](create-site-map-app.md#bkmk_AddArea)  
  
3.  [Ryhmän lisääminen sivustokarttaan](create-site-map-app.md#bkmk_AddGroup)  
  
4.  [Alialueen lisääminen ryhmään sivustokartassa](create-site-map-app.md#bkmk_AddSubarea).  
  
5.  Valitse **Tallenna**.  
  
    > [!NOTE]
    >  Uusi sivustokartta liitetään sovellukseen, kun palaat sovelluksen suunnitteluohjelmaan ja valitset **Tallenna**. Kun sivustokartta on määritetty, **määritetty** näkyy sivustokartan ruudussa. Muussa tapauksessa **ei ole määritetty** -ruutu tulee näkyviin.  Jos avaat sivustokartan suunnitteluohjelman sovelluksen suunnitteluohjelmassa ja määrität uuden sivustokartan sekä suljet selaimen ennen kuin liität sivustokartan sovellukseen, sivustokartta liitetään automaattisesti sovellukseen suunnitteluohjelman seuraavalla avauskerralla sovelluksen yksilöivän nimen perusteella.  
  
6.  Valitse **Julkaise**.  
  
## <a name="edit-the-default-site-map"></a>Oletussivustokartan muokkaaminen 

 Ympäristö sisältää oletussivustokartan.  
  
1. Avaa ratkaisunhallinta.  
  
2. Ratkaisuikkunassa kohdasta **Osat** valitse **Työasemaohjelman laajennukset**.  

3. Valitse osan työkaluriviltä **Lisää aiemmin luotu** > **Sivustokartta**.

4. Valitse ratkaisun osien luettelossa sivustokartta, jonka nimi on **Sivustokartta**, ja valitse sitten **OK**.
  
5.  Kaksoisnapsauta lisäämääsi sivustokarttaa, jonka näyttönimi on **Sivustokartta** ja tila **Hallittu**. Voit myös valita sivustokartan ja valita sitten työkalurivin **Muokkaa**-kohdan.  
  
     Sivustokartta avautuu sivustokartan suunnitteluohjelmassa.  
  
6.  [Alueen lisääminen sivustokarttaan](create-site-map-app.md#bkmk_AddArea)  
  
7.  [Ryhmän lisääminen sivustokarttaan](create-site-map-app.md#bkmk_AddGroup)  
  
8.  [Alialueen lisääminen ryhmään sivustokartassa](create-site-map-app.md#bkmk_AddSubarea).  
  
9. Valitse **Tallenna**.  
  
10. Valitse **Julkaise**.  
  
<a name="bkmk_AddArea"></a>   
## <a name="add-an-area-to-the-site-map"></a>Alueen lisääminen sivustokarttaan  
  
1.  Valitse **Lisää**-painike ![suunnitteluohjelman Lisää-painike](media/dynamics365-designer-addbutton.PNG "suunnitteluohjelman Lisää-painike") sivustokartan suunnitteluohjelman kuvapohjassa ja valitse sitten **alue**.  
  
     tai  
  
     Vedä ja pudota **Komponentit**-välilehdessä **Alue**-ruutu kaavion tyhjään laatikkoon. Tyhjä laatikko tulee näkyviin, kun siirrät ruudun pohjassa oikeaan paikkaan.  
  
2.  Valitse juuri lisäämäsi alue. **Ominaisuudet**-välilehti näkyy kaavion oikealla puolella ruudussa korostettuna.  
  
3.  Lisää alueen ominaisuudet tai muokkaa niitä seuraavasti.  
  
     Toimi kohdasta **Yleinen** seuraavasti:  
  
    - **Otsikko**: Anna alueen otsikko organisaation asennuskielellä.  
  
    - **Kuvake**: Valittuna on oletussovelluksen kuvake. Valitse ratkaisun käytettävissä olevien WWW-sovellusten luettelon alueelle toinen kuvake.  
  
    - **Tunnus**: Yksilöllinen tunnus luodaan automaattisesti. Voit kuitenkin syöttää halutessasi toisen tunnuksen. Suosittelemme annetun tunnuksen käyttämistä, koska jos tunnus ei ole yksilöllinen, käyttäjät voivat saada virheen, kun he käyttävät sovellusta, tai tämän sivustokartan sisältävän ratkaisun tuominen saattaa päättyä virheeseen.  
  
    - **Näytä ryhmät**: Valitse tämä valintaruutu, kun haluat, että siirtymisruudun alialueiden ryhmät näytetään.  
  
     Toimi kohdassa **Lisäasetukset** seuraavasti:  
  
    - **Lisää otsikkoja**: Jos organisaatiossasi on käytössä useita kieliä, valitse otsikkokieli (kieli), kirjoita nimi ja valitse **Lisää** ![sivustokartan suunnitteluohjelman Lisää-painike](media/add-icon-sitemap-designer.png "sivustokartan suunnitteluohjelman Lisää-painike"). Voit luoda, muokata tai poistaa otsikoita kaikilla organisaatiossa käytettävillä kielillä. Kielellä voi kuitenkin olla vain yksi otsikko.  
  
    - **Lisäkuvaus**: Jos organisaatiossasi on käytössä useita kieliä, valitse kuvauskieli (kieli), kirjoita kuvaus ja valitse **Lisää** ![sivustokartan suunnitteluohjelman Lisää-painike](media/add-icon-sitemap-designer.png "sivustokartan suunnitteluohjelman Lisää-painike"). Voit luoda, muokata tai poistaa kuvauksia kaikilla organisaatiossa käytettävillä kielillä. Kielellä voi kuitenkin olla vain yksi kuvaus.  
  
    - **URL-osoite**: Syötä hahmonnettava URL-osoite aluetta edustavan Dynamics 365 for Outlook -kansion esittämistä varten.  
  
<a name="bkmk_AddGroup"></a>   
## <a name="add-a-group-to-the-site-map"></a>Ryhmän lisääminen sivustokarttaan  
  
1.  Valitse sivustokartan suunnitteluohjelman kaaviosta alue, jonka haluat lisätä ryhmään.  
2.  Valitse **Lisää** ![Lisää-painike suunnitteluohjelmassa](media/dynamics365-designer-addbutton.PNG "Lisää-painike suunnitteluohjelmassa") ja valitse sitten **Ryhmä**.  
  
     tai  
  
     Vedä ja pudota **Komponentit**-välilehdessä **Ryhmä**-ruutu kaavion **Alue**-kohdan tyhjään laatikkoon. Tyhjä laatikko tulee näkyviin, kun siirrät ruudun kaaviossa oikeaan paikkaan.  
  
3.  Valitse juuri lisäämäsi ryhmä.  
  
4.  Lisää ryhmän ominaisuudet **Ominaisuudet**-välilehdessä tai muokkaa niitä välilehdessä seuraavasti:  
  
     Toimi kohdasta **Yleinen** seuraavasti:  
  
    - **Otsikko**: Anna ryhmän otsikko organisaation asennuskielellä.  
  
    - **Tunnus**: Yksilöllinen tunnus luodaan automaattisesti. Syötä tarvittaessa toinen tunnus. Suosittelemme automaattisen tunnuksen käyttämistä, koska jos tunnus ei ole yksilöllinen, tämän sivustokartan sisältävän ratkaisun tuominen saattaa päättyä virheeseen.  
  
     Toimi kohdassa **Lisäasetukset** seuraavasti:  
  
    - **Lisää otsikkoja**: Jos organisaatiossasi on käytössä useita kieliä, valitse otsikkokieli (kieli), kirjoita ryhmän nimi ja valitse **Lisää** ![Lisää-painike sivustokarttojen suunnitteluohjelmassa](media/add-icon-sitemap-designer.png "Lisää-painike sivustokarttojen suunnitteluohjelmassa"). Voit luoda, muokata tai poistaa otsikoita kaikilla organisaatiossa käytettävillä kielillä. Kielellä voi kuitenkin olla vain yksi otsikko.  
  
    - **Lisäkuvaus**: Jos organisaatiossasi on käytössä useita kieliä, valitse kuvauskieli (kieli), kirjoita ryhmän kuvaus ja valitse **Lisää**-painike ![sivustokartan suunnitteluohjelman Lisää-painike](media/add-icon-sitemap-designer.png "sivustokartan suunnitteluohjelman Lisää-painike"). Voit luoda, muokata tai poistaa kuvauksia kaikilla organisaatiossa käytettävillä kielillä. Kielellä voi kuitenkin olla vain yksi kuvaus.  
  
    - **URL-osoite**: Syötä hahmonnettava URL-osoite ryhmää edustavan Dynamics 365 for Outlook -kansion esittämistä varten.  
  
    - **Aseta profiiliksi**: Valitsemalla tämän valintaruudun voit määrittää, että tämä ryhmä edustaa työtehtävien käyttäjän valittavissa olevaa profiilia. Käyttäjän valittavissa olevaksi profiiliksi määritetty ryhmä on käytettävissä asetuksena henkilökohtaisissa asetuksissa. Tämä koskee vain **Työtehtävät**-alueen ryhmiä.  
  
<a name="bkmk_AddSubarea"></a>   
## <a name="add-a-subarea-to-a-group-in-the-site-map"></a>Alialueen lisääminen ryhmään sivustokartassa  
  
1.  Valitse **Lisää**-painike ![suunnitteluohjelman Lisää-painike](media/dynamics365-designer-addbutton.PNG "suunnitteluohjelman Lisää-painike") sivustokartan suunnitteluohjelman kuvapohjassa ja valitse sitten **Alialue**.  
  
     tai  
  
     Vedä ja pudota **Komponentit**-välilehdessä **Alialue**-ruutu kaavion **Ryhmä**-osan tyhjään laatikkoon. Tyhjä laatikko tulee näkyviin, kun siirrät ruudun kaaviossa oikeaan paikkaan.  
  
2.  Valitse juuri lisäämäsi alialue.  
  
3.  Lisää alialueen ominaisuudet **Ominaisuudet**-välilehdessä tai muokkaa niitä välilehdessä seuraavasti:  
  
     Toimi kohdasta **Yleinen** seuraavasti:  
  
    - **Tyyppi**: Määritä, onko lisäämäsi alialue koontinäyttö, entiteetti, WWW-resurssi vai URL-osoite.  
  
    - **Entiteetti**: Valitse entiteetti, jolle tämä alialue on tarkoitettu. Tämä kenttä ei ole käytössä, jos alialueen tyyppi on jokin muu kuin **Entiteetti** avattavassa **Tyyppi**-luettelossa.  
  
    - **URL**: Määritä sovelluksen pääsivulle URL-osoite, jonka avulla tämä alialue valitaan. Tämä kenttä poistetaan käytöstä, jos valitset **Entiteetti** avattavasta **Tyyppi**-luettelosta.  
  
    - **Oletuskoontinäyttö**: Valitse tässä alialueessa näytettävä oletuskoontinäyttö. Tämä kenttä poistetaan käytöstä, jos et ole valinnut **koontinäyttöä** avattavasta **Tyyppi**-luettelosta.  
  
    - **Otsikko**: Anna alialueen otsikko organisaation asennuskielellä.  
  
    - **Kuvake**: Valittuna on oletussovelluksen kuvake. Valitse ratkaisun käytettävissä olevien verkkosovellusten luettelon alialueelle toinen kuvake.  
  
    - **Tunnus**. Yksilöllinen tunnus luodaan automaattisesti. Syötä tarvittaessa toinen yksilöllinen tunnus.  
  
    - **Parametrin siirtäminen**. Valitse tämä valintaruutu, kun haluat välittää organisaation ja kielen kontekstin tiedot URL-osoitteeseen. Tämä valintaruutu valitaan vain, kun alialueen tyyppi on WWW-resurssi tai URL-osoitteeseen perustuva alialue.  
  
     Toimi kohdassa **Lisäasetukset** seuraavasti:  
 
    - **Käyttöoikeudet**: Määrittää, näkyykö alialue käyttäjälle delegoitujen käyttöoikeusroolien oikeuksien perusteella. Valitse entiteetin nimi, jonka oikeudet tarkistetaan ja valitse sitten valintaruudut määrittääksesi oikeudet. 
  
    - **Lisäotsikkoja**: Jos organisaatiossa käytetään useita kieliä, valitse otsikon kieli, anna alialueen otsikko ja napsauta sitten **Lisää**-painiketta. Voit luoda, muokata tai poistaa otsikoita kaikilla organisaatiossa käytettävillä kielillä. Kielellä voi kuitenkin olla vain yksi otsikko.  
  
    - **Lisäkuvaukset**: Jos organisaatiossa käytetään useita kieliä, valitse kuvauksen kieli, anna alialueen kuvaus ja napsauta sitten **Lisää**-painiketta. Voit luoda, muokata tai poistaa kuvauksia kaikilla organisaatiossa käytettävillä kielillä. Kielellä voi kuitenkin olla vain yksi kuvaus.  
  
    - **Varastointiyksiköt**: Valitse Dynamics 365 Customer Engagement -versio, joka näyttää tämän alialueen.  
  
    - **Asiakas**: Valitse sen työaseman tyyppi, jolla tämä alialue näkyy.  
  
    - **Outlook-pikavalinta**: Valitse kuvake, joka näytetään Dynamics 365 for Outlookissa.  
  
    - **Käytettävyys offline-tilassa**: Valitse tämä valintaruutu, kun haluat tämän alialueen olevan käyttäjien käytettävissä offline-tilassa Dynamics 365 for Outlookissa.  
  
## <a name="organize-areas-groups-and-subareas"></a>Alueiden, ryhmien ja alialueiden järjestäminen  
 Voit järjestää alueita, ryhmiä ja alialueita vetämällä ne uusiin kohtiin. Näkyviin tulee säilölaatikko, jonne ruudut voidaan pudottaa. Voit esimerkiksi  
  
-   siirtää alialueen uuteen kohtaan samassa ryhmässä tai saman alueen eri ryhmässä  
  
-   siirtää alialueen uuteen kohtaan eri alueen samassa ryhmässä  
  
-   siirtää ryhmän uuteen kohtaan samalla alueella  
  
-   siirtää ryhmän uuteen kohtaan eri alueella  
  
-   siirtää alueen uuteen kohtaan.  
  
## <a name="clone-a-component-in-a-site-map"></a>Sivustokartan komponentin kloonaaminen  
 Voit kopioida aiemmin määritetyn komponentin valitsemalla sen ja valitsemalla sitten toimintotyökalupalkin **Kloonaa**-kohdan.  Kloonatun komponentin tiedot ovat samat kuin peruskomponentin tiedot tunnusta ja otsikkoa lukuun ottamatta. Tunnus luodaan satunnaisesti. 
  
 Kloonattu alue lisätään kloonaamisen yhteydessä valittuna olevan alueen oikealle puolelle. Kloonattu ryhmä lisätään kloonaamisen yhteydessä valittuna olevan ryhmän oikealle puolelle. Kloonattu alialue lisätään kloonaamisen yhteydessä valittuna olevan alialueen alle.  
  
## <a name="delete-an-area-group-or-subarea-from-a-site-map"></a>Alueen, ryhmän tai alialueen poistaminen sivustokartasta  
 Voit poistaa sivustokartan komponentin valitsemalla komponenttiruudun ja valitsemalla sitten työkalurivin **Poista**-kohdan. Kun alue poistetaan, kaikki alueen ryhmät ja alialueet poistetaan myös. Vastaavasti ryhmän poistamisen yhteydessä poistetaan myös sen sisältämät ryhmät ja alialueet.  
  
## <a name="clients-supported"></a>Tuetut työasemat  
 Seuraavassa taulukossa kuvataan erilaisten sivustokarttojen tukemat työasemat.  
 
|Sivustokartat|Tuetut työasemat|  
|---------------|-----------------------|  
|Uudet sovellukset| Unified Interface ja Dynamics 365 Customer Engagement -WWW-sovellus |  
|Dynamics 365 - mukautettu sovellus, sivustokartta | Dynamics 365 Customer Engagement -WWW-sovellus ja Dynamics 365 for Outlook |  
|Oletusliiketoimintasovellukset (Sales, myyntikeskus, Customer Service, asiakaspalvelukeskukseen, Field Service, Project Service Automation)| Dynamics 365 Customer Engagement -WWW-sovellus ja Unified Interface|  
 
  
### <a name="next-steps"></a>Seuraavat vaiheet  
 [Sovelluksen luominen tai muokkaaminen](create-edit-app.md)   
 [Sovelluksen osien lisääminen tai muokkaaminen](add-edit-app-components.md)

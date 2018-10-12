---
title: Mallipohjaisen sovelluksen sivustokartan luominen PowerAppsissa | MicrosoftDocs
description: Opi luomaan sivustokartta sovelluksellesi
keywords: ''
ms.date: 05/29/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 2461bd71-6cb4-46b7-8d1f-6a0aa3dca809
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 18
topic-status: Drafting
ms.openlocfilehash: 2c3f1f4f22df6ed8b4824f1942e3fd202362ea9d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39676355"
---
# <a name="tutorial-create-a-model-driven-app-site-map-for-an-app-using-the-site-map-designer"></a>Opetusohjelma: Mallipohjaisen sovelluksen sivustokartan luominen sivustokartan suunnitteluohjelmalla

Tässä opetusohjelmassa teet useita sivustonkarttaan liittyviä tehtäviä, kuten uuden sivustokartan luominen sekä alueen, ryhmän ja alialueen lisääminen.

Sivustokartat määrittävät, kuinka sovelluksessa navigoidaan. Luo sovelluksellesi sivustokartta vaivattomasti ruutuihin perustuvalla sivustokartan suunnitteluohjelmalla. Suunnitteluohjelmassa voit vetää osia pohjaan, esikatsella työtäsi ja julkaista sivustokartan välittömästi. Järjestelmämukauttajat ja kaikki käyttäjät, joilla on tarvittavat oikeudet, voivat luoda sovelluksille sivustokarttoja helposti ja nopeasti.  
  
Sivustokartan suunnitteluohjelmassa voit myös määrittää alueen, alialueen tai ryhmän otsikot ympäristön tukemilla kielillä.  
  
Käytettävissä on oletusarvoinen sivustokartta. Voit muokata tätä sivustokarttaa tai määrittää sivustokartat uusille sovelluksille sivustokartan suunnitteluohjelmalla. Sivustokartan suunnitteluohjelma on integroitu sovellusten suunnitteluohjelmaan.  

## <a name="prerequisites"></a>Edellytykset
Varmista, että sinulla on järjestelmänvalvojan tai järjestelmämukauttajan käyttöoikeusrooli tai vastaavat oikeudet.  Kaikki käyttäjät, joilla on seuraavat oikeudet, voivat myös luoda sovelluksia:  
-   Sovellusentiteetin luonti-, luku- ja kirjoitusoikeudet  
-   Mukautetun entiteetin luku- ja kirjoitusoikeudet  
-   Ratkaisuentiteetin lukuoikeudet

Voit tarkastella ja määrittää näitä oikeuksia käyttöoikeusroolin **Mukauttaminen**-välilehdellä.
  
## <a name="create-a-site-map-for-an-app"></a>Sovelluksen sivustokartan luominen  
  
1. Valitse sovellusten suunnitteluohjelman pohjan **Sivustokartta**-alueelta **Avaa sivustokartan suunnitteluohjelma** ![Avaa sivustokartan suunnitteluohjelma -painike](media/dynamics365-open-designer.PNG "Avaa sivustokartan suunnitteluohjelma -painike ").  
  
     Sivustokartan suunnitteluohjelmaan avautuu pohja, jossa on valmiiksi yksi alue, yksi ryhmä ja yksi alialue. Valitse alueen, ryhmän tai alialueen ruutu sen ominaisuuksien muuttamiseksi.  
  
    > [!NOTE]
    >  Kun valitset sovellusten suunnitteluohjelman pohjassa **Avaa sivustokartan suunnitteluohjelma** ![Avaa sivustokartan suunnitteluohjelma -painikkeen](media/dynamics365-open-designer.PNG "Avaa sivustokartan suunnitteluohjelma -painikkeen"), ohjelma luo automaattisesti uuden sivustonkartan (jos aiempaa sivustokarttaa ei ole) ja antaa uudelle sivustokartalle saman nimen kuin sovelluksen nimi ja saman yksilöivän nimen kuin sovelluksen yksilöivä nimi. 

   ![Valitse sivustokartta](media/app-designer-sitemap-location.png "Valitse sivustokartta") 
  
2.  [Lisää alue sivustokarttaan](create-site-map-app.md#bkmk_AddArea).  
  
3.  [Lisää ryhmä sivustokarttaan](create-site-map-app.md#bkmk_AddGroup).  
  
4.  [Lisää alialue ryhmään sivustokartassa](create-site-map-app.md#bkmk_AddSubarea).  
  
5.  Valitse **Tallenna**.  
  
    > [!NOTE]
    >  Uusi sivustokartta liitetään sovellukseen, kun siirryt takaisin sovelluksen suunnittelutyökaluun ja valitset **Tallenna**. Kun sivustokartta on määritetty, sivustokarttaruudussa näkyy **Määritetty**; muussa tapauksessa ruudussa näkyy **Ei määritetty**.  Jos avaat sivustokartan suunnitteluohjelman sovellusten suunnitteluohjelmasta ja määrität uuden sivustokartan, mutta suljet selaimen ennen kuin liität sivustokartan sovellukseen, sivustokartta liitetään automaattisesti sovellukseen sovelluksen yksilöivän nimen perusteella, kun avaat sovelluksen suunnitteluohjelman seuraavan kerran.  
  
6.  Valitse **Julkaise**.  
  
## <a name="edit-the-default-site-map"></a>Muokkaa oletussivustokarttaa 

 Ympäristölläsi on oletusarvoinen sivustokartta.  
  
1. Avaa ratkaisunhallinta.  
  
2. Ratkaisu-ikkunan kohdassa **Osat**, valitse **Asiakaslaajennukset**.  

3. Valitse työkalurivillä **Lisää olemassa oleva** > **Sivustokartta**.

4. Valitse ratkaisun osien luettelosta sivustokartta nimeltä **Sivustokartta**, ja valitse sitten **OK**.
  
5.  Valitse kaksoisnapsauttamalla lisäämäsi sivustokartta, jolla on näyttönimi **Sivustokartta** ja jonka tila on **Hallittu**. Voit myös valita ensin sivustokartan ja sitten työkaluriviltä **Muokkaa**.  
  
     Sivustokartta avautuu sivustokartan suunnitteluohjelmassa.  
  
6.  [Lisää alue sivustokarttaan](create-site-map-app.md#bkmk_AddArea).  
  
7.  [Lisää ryhmä sivustokarttaan](create-site-map-app.md#bkmk_AddGroup).  
  
8.  [Lisää alialue ryhmään sivustokartassa](create-site-map-app.md#bkmk_AddSubarea).  
  
9. Valitse **Tallenna**.  
  
10. Valitse **Julkaise**.  
  
<a name="bkmk_AddArea"></a>   
## <a name="add-an-area-to-the-site-map"></a>Lisää alue sivustokarttaan  
  
1.  Valitse **Lisää** ![Lisää-painike suunnitteluohjelmassa](media/dynamics365-designer-addbutton.PNG "Lisää-painike suunnitteluohjelmassa") sivustokartan suunnitteluohjelman pohjassa ja valitse sitten **Alue**.  
  
     tai  
  
     Vedä **Osat**-välilehdessä **Alue**-ruutu pohjan ulkopuolella olevaan tyhjään kenttään. Näkyviin tulee tyhjä kenttä, kun siirrät ruudun oikeaan paikkaan pohjassa.  
  
2.  Valitse alue, jonka juuri lisäsit. **Ominaisuudet**-välilehti näkyy korostettuna pohjan oikealla puolella olevassa ruudussa.  
  
3.  Lisää tai muokkaa alueen ominaisuuksia.  
  
     Toimi seuraavasti kohdassa **Yleiset**:  
  
    - **Otsikko**: Anna alueelle otsikko organisaation oletuskielellä.  
  
    - **Kuvake**: Sovelluksen oletuskuvake on valittuna. Voit valita alueelle muun kuvakkeen ratkaisun verkkoresurssien luettelosta.  
  
    - **Tunnus**: Yksilöivä tunnus luodaan automaattisesti, mutta voit halutessasi syöttää toisen tunnuksen. Suosittelemme, että käytät annettua tunnusta, koska jos syöttämäsi tunnus ei ole yksilöivä, käyttäjät saattavat saada virhesanoman sovellusta käytettäessä tai näyttöön voi tulla virhesanoma, kun tuot ratkaisun, joka sisältää tämän sivustokartan.  
  
    - **Näytä ryhmät**: Valitse tämä valintaruutu, jos haluat näyttää alialueryhmät siirtymisruudussa.  
  
     Toimi seuraavasti kohdassa **Lisäasetukset**:  
  
    - **Lisää otsikoita**: Jos organisaatiosi käyttää useita kieliä, valitse kieli (kieliasetus) otsikolle, kirjoita otsikko ja valitse sitten **Lisää** ![Lisää-painike sivustokartan suunnitteluohjelmassa](media/add-icon-sitemap-designer.png " Lisää-painike sivustokartan suunnitteluohjelmassa"). Voit luoda, muokata tai poistaa otsikoita niin monelle kielelle kuin mitä organisaatiosi käyttää. Sinulla voi kuitenkin olla vain yksi otsikko kieltä kohden.  
  
    - **Lisää kuvauksia**: Jos organisaatiosi käyttää useita kieliä, valitse kieli kuvaukselle, kirjoita kuvaus ja valitse sitten **Lisää** ![Lisää-painike sivustokartan suunnitteluohjelmassa](media/add-icon-sitemap-designer.png " Lisää-painike sivustokartan suunnitteluohjelmassa"). Voit luoda, muokata tai poistaa kuvauksia niin monelle kielelle kuin mitä organisaatiosi käyttää. Sinulla voi kuitenkin olla vain yksi kuvaus kieltä kohden.  
  
    - **URL-osoite**: Anna URL-osoite Dynamics 365 for Outlook -kansion aluetta varten.  
  
<a name="bkmk_AddGroup"></a>   
## <a name="add-a-group-to-the-site-map"></a>Lisää ryhmä sivustokarttaan  
  
1.  Valitse sivustokartan suunnitteluohjelmassa alue, johon haluat lisätä ryhmän.  
2.  Valitse **Lisää** ![Lisää-painike suunnitteluohjelmassa](media/dynamics365-designer-addbutton.PNG "Lisää-painike suunnitteluohjelmassa") ja valitse sitten **Ryhmä**.  
  
     tai  
  
     Vedä **Osat**-välilehdessä **Ryhmä**-ruutu pohjan **Alue**-kohdassa olevaan tyhjään kenttään. Näkyviin tulee tyhjä kenttä, kun siirrät ruudun oikeaan paikkaan pohjassa.  
  
3.  Valitse ryhmä, jonka juuri lisäsit.  
  
4.  Lisää tai muokkaa ryhmän ominaisuuksia **Ominaisuudet**-välilehdessä:  
  
     Toimi seuraavasti kohdassa **Yleiset**:  
  
    - **Otsikko**: Anna ryhmälle otsikko organisaation oletuskielellä.  
  
    - **Tunnus**: Yksilöivä tunnus luodaan automaattisesti. Anna toinen tarvittaessa. On suositeltavaa käyttää automaattista tunnusta, koska jos antamasi tunnus ei ole yksilöivä, voit saada virheen tuodessasi ratkaisua, joka sisältää tämän sivustokartan.  
  
     Toimi seuraavasti kohdassa **Lisäasetukset**:  
  
    - **Lisää otsikoita**: Jos organisaatiosi käyttää useita kieliä, valitse kieli (kieliasetus) ryhmälle, kirjoita otsikko ja valitse sitten **Lisää** ![Lisää-painike sivustokartan suunnitteluohjelmassa](media/add-icon-sitemap-designer.png " Lisää-painike sivustokartan suunnitteluohjelmassa"). Voit luoda, muokata tai poistaa otsikoita niin monelle kielelle kuin mitä organisaatiosi käyttää. Sinulla voi kuitenkin olla vain yksi otsikko kieltä kohden.  
  
    - **Lisää kuvauksia**: Jos organisaatiosi käyttää useita kieliä, valitse kieli kuvaukselle, kirjoita ryhmän kuvaus ja valitse sitten **Lisää** ![Lisää-painike sivustokartan suunnitteluohjelmassa](media/add-icon-sitemap-designer.png " Lisää-painike sivustokartan suunnitteluohjelmassa"). Voit luoda, muokata tai poistaa kuvauksia niin monelle kielelle kuin mitä organisaatiosi käyttää. Sinulla voi kuitenkin olla vain yksi kuvaus kieltä kohden.  
  
    - **URL-osoite**: Anna URL-osoite Dynamics 365 for Outlook -kansion ryhmää varten.  
  
    - **Määritä profiiliksi**: Valitse tämä valintaruutu, jos tämä ryhmä edustaa käyttäjän valittavissa olevaa työpaikan profiilia. Käyttäjän valittavissa olevaksi profiiliksi määritetty ryhmä on käytettävissä henkilökohtaisissa asetuksissa. Tämä koskee vain ryhmiä **Työpaikka**-alueella.  
  
<a name="bkmk_AddSubarea"></a>   
## <a name="add-a-subarea-to-a-group-in-the-site-map"></a>Lisää alialue ryhmään sivustokartassa  
  
1.  Valitse **Lisää** ![Lisää-painike suunnitteluohjelmassa](media/dynamics365-designer-addbutton.PNG "Lisää-painike suunnitteluohjelmassa") sivustokartan suunnitteluohjelman pohjassa ja valitse sitten **Alialue**.  
  
     tai  
  
     Vedä **Osat**-välilehdessä **Alialue**-ruutu pohjan **Ryhmä**-kohdassa olevaan tyhjään kenttään. Näkyviin tulee tyhjä kenttä, kun siirrät ruudun oikeaan paikkaan pohjassa.  
  
2.  Valitse alialue, jonka juuri lisäsit.  
  
3.  Lisää tai muokkaa alialueen ominaisuuksia **Ominaisuudet**-välilehdessä:  
  
     Toimi seuraavasti kohdassa **Yleiset**:  
  
    - **Tyyppi**: Valitse, onko lisättävä alialue koontinäyttö, entiteetti, verkkoresurssi vai URL-osoite.  
  
    - **Entiteetti**: Valitse entiteetti, jota varten alialue on tehty. Tämä kenttä on poistettu käytöstä, jos alialueen tyyppi on muu kuin **Entiteetti** avattavassa **Tyyppi**-luettelossa.  
  
    - **URL-osoite**: Määritä URL-osoite sivulle, jonka sovellus näyttää, kun tämä alialue valitaan. Tämä kenttä ei ole käytössä, jos olet valinnut **Entiteetti**-vaihtoehdon avattavasta **Tyyppi**-luettelosta.  
  
    - **Oletusarvoinen koontinäyttö**: Valitse oletuskoontinäyttö, joka näytetään tälle alialueelle. Tämä kenttä ei ole käytössä, jos olet valinnut **Koontinäyttö**-vaihtoehdon avattavasta **Tyyppi**-luettelosta.  
  
    - **Otsikko**: Anna alialueelle otsikko organisaation oletuskielellä.  
  
    - **Kuvake**: Sovelluksen oletuskuvake on valittuna. Voit valita alialueelle muun kuvakkeen ratkaisun verkkoresurssien luettelosta.  
  
    - **Tunnus**. Yksilöivä tunnus luodaan automaattisesti. Anna toinen yksilöivä tunnus tarvittaessa.  
  
    - **Parametrin välitys**. Valitse tämä valintaruutu, jos haluat välittää tiedot organisaation ja kielen kontekstista URL-osoitteeseen. Tämä valintaruutu on valittuna vain, kun alialuetyyppi on verkkoresurssi tai URL-pohjainen alialue.  
  
     Toimi seuraavasti kohdassa **Lisäasetukset**:  
 
    - **Oikeudet**: Tämä määrittää, näytetäänkö alialue käyttäjälle määritettyjen käyttöoikeusroolien perusteella. Valitse sen entiteetin nimi, jota varten oikeudet tarkistetaan, ja määritä sitten oikeudet valintaruuduilla. 
  
    - **Lisää otsikoita**: Jos organisaatiosi käyttää useita kieliä, valitse kieli otsikolle, kirjoita alialueen otsikko ja valitse sitten **Lisää**. Voit luoda, muokata tai poistaa otsikoita niin monelle kielelle kuin mitä organisaatiosi käyttää. Sinulla voi kuitenkin olla vain yksi otsikko kieltä kohden.  
  
    - **Lisää kuvauksia**: Jos organisaatiosi käyttää useita kieliä, valitse kieli kuvaukselle, kirjoita kuvauksen otsikko ja valitse sitten **Lisää**. Voit luoda, muokata tai poistaa kuvauksia niin monelle kielelle kuin mitä organisaatiosi käyttää. Sinulla voi kuitenkin olla vain yksi kuvaus kieltä kohden.  
  
    - **SKU:t**: Valitse Dynamics 365 Customer Engagement -versiot, jotka näyttävät tämän alialueen.  
  
    - **Asiakas**: Valitse asiakastyyppi, joka näyttää tämän alialueen.  
  
    - **Outlook-pikakuvake**: Valitse kuvake, joka näytetään Dynamics 365 for Outlookissa.  
  
    - **Offline-käytettävyys**: Valitse tämä valintaruutu, jotta tämä alialue on käytettävissä käyttäjien ollessa offline-tilassa Dynamics 365 for Outlookissa.  
  
## <a name="organize-areas-groups-and-subareas"></a>Järjestä alueet, ryhmät ja alialueet  
 Voit järjestää alueita, ryhmiä ja alialueita vetämällä ne uusiin paikkoihin. Näyttöön ilmestyy säilökenttä, johon voit pudottaa ruutuja. Voit tehdä esimerkiksi seuraavia toimia:  
  
-   Siirrä alialue uuteen paikkaan samassa ryhmässä tai toiseen ryhmään samalla alueella.  
  
-   Siirrä alialue uuteen paikkaan ryhmässä eri alueella.  
  
-   Siirrä ryhmä uuteen paikkaan samalla alueella.  
  
-   Siirrä ryhmä uuteen paikkaan eri alueella.  
  
-   Siirrä alue uuteen paikkaan.  
  
## <a name="clone-a-component-in-a-site-map"></a>Sivustokartan osan kloonaaminen  
 Jos haluat kopioida nykyisen osan, valitse osa ja valitse sitten työkaluriviltä **Kloonaa**.  Kloonatun osan kaikki tiedot ovat samoja kuin alkuperäisen osan, lukuun ottamatta tunnusta ja otsikkoa. Tunnus luodaan satunnaisesti. 
  
 Kun kloonaat alueen, kloonattu alue lisätään tällä hetkellä valitun alueen oikealle puolelle. Kun kloonaat ryhmän, kloonattu ryhmä lisätään tällä hetkellä valitun ryhmän oikealle puolelle. Kun kloonaat alialueen, kloonattu alialue lisätään tällä hetkellä valitun alialueen alapuolelle.  
  
## <a name="delete-an-area-group-or-subarea-from-a-site-map"></a>Alueen, ryhmän tai alialueen poistaminen sivustokartasta  
 Jos haluat poista sivustokartan osan, valitse osan ruutu ja valitse sitten työkaluriviltä **Poista**. Kun poistat alueen, myös kaikki sen ryhmät ja alialueet poistetaan. Vastaavasti, kun poistat ryhmän, myös sen alialueet poistetaan.  
  
## <a name="clients-supported"></a>Tuetut asiakkaat  
 Seuraavassa taulukossa kuvataan eri sivustokarttojen tukemat asiakkaat.  
 
|Sivustokartat|Tuetut asiakkaat|  
|---------------|-----------------------|  
|Uudet sovellukset| Unified Interface ja Dynamics 365 Customer Engagement -verkkosovellus |  
|Mukautetun Dynamics 365 -sovelluksen sivustokartta | Dynamics 365 Customer Engagement -verkkosovellus ja Dynamics 365 for Outlook |  
|Perusyrityssovellukset (Sales, Sales Hub, Customer Service, Customer Service Hub, Field Service, Project Service Automation)| Dynamics 365 Customer Engagement -verkkosovellus ja Unified Interface|  
 
  
### <a name="next-steps"></a>Seuraavat vaiheet  
 [Sovelluksen luominen tai muokkaaminen](create-edit-app.md)   
 [Sovelluksen osien lisääminen tai muokkaaminen](add-edit-app-components.md)

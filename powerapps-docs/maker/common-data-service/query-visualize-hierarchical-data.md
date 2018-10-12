---
title: Kyselyn tekeminen hierarkkisista tiedoista ja tietojen visualisoiminen PowerAppsilla | MicrosoftDocs
description: Ohjeet kyselyn tekemiseen hierarkkisesti toisiinsa liittyvistä tiedoista ja niiden visualisoimiseen
ms.custom: ''
ms.date: 06/20/2018
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
ms.assetid: 0cf62817-5ff5-40bb-ad17-e1f6b0921720
caps.latest.revision: 42
ms.author: matp
manager: kvivek
ms.openlocfilehash: ec45f43266c1920d05301c92bdd67838b40b7734
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674992"
---
# <a name="query-and-visualize-hierarchically-related-data"></a>Kyselyn tekeminen hierarkkisista tiedoista ja tietojen visualisoiminen

Voit saada liiketoimintaan liittyviä arvokkaita tietoja visualisoimalla toisiinsa liittyviä tietoja hierarkkisesti. Hierarkkisista mallinnus- ja visualisoimistoiminnoista on paljon hyötyä:  
  
-   Voit tarkastella ja selailla monitasoisia hierarkkisia tietoja.  
  
-   Voit tarkastella suorituskykyilmaisimia hierarkian tilannekohtaisessa näkymässä.  
  
-   Voit analysoida verkossa ja tableteilla olevia tärkeimpiä tietoja.  
  
Joillekin entiteeteille, kuten tilille ja käyttäjälle, tarjotaan valmiita visualisointeja. Muissa entiteeteissä, kuten mukautetuissa entiteeteissä, voidaan ottaa hierarkia käyttöön ja niille voidaan luoda visualisoinnit. Käyttäjä voi valita tarpeidensa mukaan puunäkymän, jossa näkyy koko hierarkia, tai ruutunäkymän, joka esittää pienemmän osan hierarkiasta. Näkymät esitetään rinnakkain. Voit tutkia hierarkiaa laajentamalla ja kutistamalla hierarkiapuuta. Samat hierarkkiset asetukset määritetään visualisoinnille kerran, mutta ne koskevat sekä verkko- että mobiiliasiakkaita. Tableteissa visualisoinnit esitetään niille sopivassa muokatussa muodossa. Hierarkkisille visualisoinneille vaadittavat mukautettavat osat ovat ratkaisukohtaisia, joten ne voidaan siirtää organisaatiosta toiseen muiden mukautusten tavoin. Voit määrittää visualisoinnissa näytettävät määritteet mukauttamalla pikalomakkeen lomake-editorin avulla. Koodia ei tarvitse kirjoittaa.  
  
<a name="BKMK_Querydata"></a>   
## <a name="query-hierarchical-data"></a>Kyselyn tekeminen hierarkkisista tiedoista  
 Common Data Service for Appsissa hierarkkisia tietorakenteita tuetaan itseensä viittaavilla yksi moneen (1:N) -suhteilla niihin liittyvissä tietueissa. Aiemmin hierarkkisten tietojen tarkasteleminen edellytti toisiinsa liittyvien tietueiden toistuvia kyselyjä. Tällä hetkellä toisiinsa liittyvistä tiedoista voi tehdä kyselyn hierarkiana yhdessä vaiheessa. Voit tehdä kyselyjä tietueista käyttämällä **alle**- ja **ei alle** -logiikkaa. Hierarkkiset **alle-** ja **ei alle** -operaattorit näkyvät erikoishaussa ja työnkulkueditorissa. Lisätietoja näiden operaattoreiden käyttämisestä on kohdassa [Työnkulun vaiheiden määrittäminen](/flow/configure-workflow-steps). Lisätietoja erikoishausta on kohdassa [Erikoishaun luominen, muokkaaminen tai tallentaminen](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search).  
  
 Seuraavassa esimerkissä kuvataan eri skenaariot, joiden avulla hierarkioista voi tehdä kyselyn:  
  
 Kysely tekeminen tilihierarkiasta  
  
 ![Kyselyn tekeminen tilihierarkian tileistä](media/query-accounts.png "Kyselyn tekeminen tilihierarkian tileistä")  
  
 Kyselyn tekeminen tilihierarkiasta ja liittyvistä toiminnoista  
  
 ![Kyselyn tekeminen tilin liittyvistä toiminnoista](media/query-account-related-activities.png "Kyselyn tekeminen tilin liittyvistä toiminnoista")  
  
 Kyselyn tekeminen tilihierarkiasta ja liittyvistä mahdollisuuksista  
  
 ![Kyselyn tekeminen tilin liittyvistä mahdollisuuksista](media/query-account-related-opportunities.png "Kyselyn tekeminen tilin liittyvistä mahdollisuuksista")  
  
 Jos haluat tehdä kyselyn tiedoista hierarkiana, sinun on määritettävä jokin entiteetin itseen viittaava 1:N (yksi-moneen) -suhde hierarkkiseksi. Voit ottaa hierarkian käyttöön seuraavasti:  
  
1.  Avaa [ratkaisunhallinta](../model-driven-apps/advanced-navigation.md#solution-explorer). 
  
2.  Valitse haluamasi entiteetti, valitse **1:N-suhteet** valitse sitten (1:N)-suhde. 

3.  Valitse **Suhteen määritys** -kohdan **Hierarkkinen**-arvoksi **Kyllä**.  
  
> [!NOTE]
> - Joitakin valmiita 1:N-suhteita ei voi mukauttaa. Tämä estää asettamasta näitä suhteita hierarkkisiksi.  
> - Voit määrittää hierarkkisen suhteen järjestelmän itseensä viittaaville suhteille. Tämä sisältää järjestelmätyypin itseen viittaavat 1:N-suhteet, kuten contact_master_contact-suhteen.  
  
<a name="BKMK_Visualizedata"></a>   
## <a name="visualize-hierarchical-data"></a>Hierarkkisten tietojen visualisoiminen  
 Valmiita visualisointeja on seuraavilla järjestelmäentiteeteillä: `Account`, `Position`, `Product` ja `User`. Näiden entiteettien ruudukkonäkymässä on hierarkiakaaviokuvake tietueen nimen vasemmalla puolella. Hierarkiakuvake ei näy oletusarvoisesti kaikissa tietueissa. Kuvake näkyy tietueissa, joilla on pää- tai alitietue tai molemmat.  
  
 ![Aktiiviset tilit](media/cust-hs-active-account.png "Aktiiviset tilit")  
  
 Jos valitset hierarkiakuvakkeen, voit tarkastella hierarkiaa vasemmalla olevan puunäkymän tai oikealla näkyvän ruutunäkymän avulla alla kuvatulla tavalla:  
  
 ![Tilin puu- ja ruutunäkymä](media/hierachy-security-accounts-tile-view.png "Tilin puu- ja ruutunäkymä")  
  
 Hierarkiaa varten voi ottaa käyttöön muutaman muunkin valmiin järjestelmäentiteetin. Näitä entiteettejä ovat `Case`, `Contact`, `Opportunity`, `Order`, `Quote`, `Campaign` ja `Team`. Kaikki mukautetut kohteet voi ottaa käyttöön hierarkiassa.  
  
> [!TIP]
>  Jos entiteetin voi ottaa käyttöön hierarkiassa, toimi seuraavasti:  
>  Laajenna haluamasi entiteetti ratkaisunhallinnassa. Näkyviin tulee entiteetin osa nimeltä **Hierarkia-asetukset**. Entiteeteissä, joita ei voi ottaa käyttöön hierarkiassa, ei ole tätä osaa Dynamics 365 Customer Engagementin myyntialueen entiteettiä lukuun ottamatta. Vaikka myyntialueen entiteetti sisältää **Hierarkia-asetukset**-kohdan, entiteettiä ei voi ottaa käyttöön hierarkiassa.  
  
 Asioita, jotka on tärkeä muistaa visualisointien luonnin yhteydessä:  
  
-   Entiteetille voi määrittää hierarkkiseksi vain yhden itseen viittaavan (1:N)-suhteen. Tässä suhteessa ensisijaisella ja liittyvällä entiteetillä on oltava sama tyyppi, kuten account_parent_account tai new_new_widget_new_widget.  
  
-   Tällä hetkellä hierarkia ja visualisointi perustuvat vain yhteen entiteettiin. Tilihierarkia voidaan esittää niin, että se näyttää tilit useilla tasoilla. Tilejä ja yhteystietoja ei kuitenkaan voi näyttää samassa hierarkian visualisoinnissa.  
  
-   Ruudussa voi näyttää enintään neljä kenttää. Jos lisäät kenttiä ruutunäkymässä käytettävään pikalomakkeeseen, vain neljä ensimmäistä kenttää näytetään.  
  
### <a name="visualization-example"></a>Visualisointiesimerkki  
 Tarkastellaan esimerkkiä mukautetun entiteetin visualisoinnin luonnista. Luotiin mukautettu entiteetti nimeltä new_Widget ja itseen viittaava (1:N)-suhde **new_new_widget_new_widget**, ja se merkittiin hierarkkiseksi seuraavasti:  
  
 ![Pienoissovellussuhteen määritys](media/widget-relationship-definition.png "Pienoissovellussuhteen määritys")  
  
 Seuraavaksi **Hierarkia-asetukset**-ruudukkonäkymässä valittiin hierarkkinen suhde nimeltä **new_new_widget_new_widget**. Lomakkeen pakolliset kentät täytettiin. Jos (1:N)-suhdetta ei ole vielä merkitty hierarkkiseksi, voit siirtyä lomakkeen linkillä suhteen määrityslomakkeeseen ja merkitä siellä suhteen hierarkkiseksi.  
  
 **Pikalomake**-kohtaan luotiin pikalomake nimeltä **Pienoissovellushierarkiaruutu-lomake**. Tähän lomakkeeseen lisättiin neljä kenttää, jotka näkyvät kussakin ruudussa.  
  
 ![Luo pikalomake pienoissovellukselle](media/create-quickf-orm.png "Luo pikalomake pienoissovellukselle")  
  
 Määritysten jälkeen luotiin kaksi tietuetta: Standard Widget (vakiopienoissovellus) ja Premium Widget (premium-pienoissovellus). Kun premium-pienoissovelluksesta on tehty vakiopienoissovelluksen päätaso hakukentän avulla, uusi pienoissovellusruudukkonäkymä näyttää hierarkiakuvakkeet alla kuvatulla tavalla:  
  
 ![Pienoissovelluksen hierarkiaruudukko](media/widget-hierarchy-grid.png "Pienoissovelluksen hierarkiaruudukko")  
  
> [!TIP]
>  Hierarkiakuvakkeet näkyvät tietueruudukkonäkymässä vasta sitten, kun tietueille on muodostettu pää- ja alitason suhde.  
  
 Jos hierarkiakuvake valitaan, näkyviin tulee uusi kaksi tietuetta esittävä pienoissovellushierarkia, jonka vasemmalla puolella on puunäkymä ja oikealle puolella ruutunäkymä. Kukin ruutu sisältää neljä **Pienoissovellushierarkiaruutu-lomakkeessa** määritettyä kenttää.  
  
 ![Pienoissovelluksen puu- ja ruutunäkymät](media/widget-tree-tiles.png "Pienoissovelluksen puu- ja ruutunäkymät")  
  
## <a name="see-also"></a>Katso myös  
 [Video: Hierarkkinen suojausmallintaminen](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)   
 [Video: Hierarkian visualisointi](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)

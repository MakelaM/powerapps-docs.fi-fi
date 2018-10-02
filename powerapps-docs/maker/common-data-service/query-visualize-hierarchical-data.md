---
title: Kysele ja havainnollista hierarkkisia tietoja PowerAppsissa | MicrosoftDocs
description: 'Tietoja siitä, miten voit tehdä kyselyjä ja visualisoida hierarkiaan liittyviä tietoja'
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="query-and-visualize-hierarchically-related-data"></a>Hierarkkisesti järjestettyjen tietojen kysely ja tietojen visualisoiminen

Voit saada liiketoimintaan liittyviä arvokkaita tietoja visualisoimalla toisiinsa liittyviä tietoja hierarkkisesti. Hierarkkisista mallinnus- ja visualisoimistoiminnoista on paljon hyötyä.  
  
-   Voit tarkastella ja selailla monitasoisia hierarkkisia tietoja.  
  
-   Voit tarkastella tunnuslukuja hierarkian tilannekohtaisessa näkymässä.  
  
-   Voit analysoida verkossa ja taulutietokoneilla olevia tärkeimpiä tietoja.  
  
Joidenkin entiteettien, kuten asiakkaan ja käyttäjän, visualisoinnit ovat valmiita visualisointeja. Muissa entiteeteissä, kuten mukautetuissa entiteeteissä, voidaan ottaa hierarkia käyttöön ja niille voidaan luoda visualisoinnit. Käyttäjä voi valita tarpeidensa mukaan puunäkymän, jossa näkyy koko hierarkia, tai ruutunäkymän, joka esittää pienemmän osan hierarkiasta. Näkymät esitetään rinnakkain. Voit tutkia hierarkian laajentamalla ja supistamalla hierarkiapuuta. Visualisoinnin samat hierarkkiset asetuksen määritetään kerran, mutta niitä käytetään sekä :n WWW-sovelluksessa että mobiiliasiakasohjelmissa. Taulutietokoneissa visualisoinnit esitetään niille sopivassa muokatussa muodossa. Hierarkkisille visualisoinneille vaadittavat mukautettavat komponentit ovat ratkaisukohtaisia, jonka vuoksi ne voidaan siirtää organisaatiosta toiseen muiden mukautusten tavoin. Voit määrittää visualisoinnissa näytettävät määritteet mukauttamalla pikalomakkeen lomake-editorin avulla. Koodia ei tarvitse kirjoittaa.  
  
<a name="BKMK_Querydata"></a>   
## <a name="query-hierarchical-data"></a>Kyselyn tekeminen hierarkkisista tiedoista  
 Common Data Service sovelluksille tukee hierarkkisten tietorakenteiden liittyvien tietueiden itseen viittaavia yksi moneen (1:N) -suhteita. Aiemmin hierarkkisten tietojen tarkasteleminen vaati toisiinsa liittyvien tietueiden toistuvia kyselyjä. Tällä hetkellä liittyvistä tiedoista voi tehdä kyselyn hierarkiana yhdessä vaiheessa. Entiteetin tietueista voi tehdä kyselyn käyttämällä **alle**- ja **ei alle** -logiikkaa. Hierarkkisia **alle**- ja **ei alle** -operaattoreita ovat käytettävissä Erikoishaku-toiminnossa ja työnkulkueditorissa. Katso lisätietoja siitä, miten näitä operaattoreita käytetään kohdassa [työnkulun osavaiheiden määritys](/flow/configure-workflow-steps). Lisätietoja erikoishausta on artikkelissa [Erikoishaun luominen, muokkaaminen tai tallentaminen](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search).  
  
 Seuraavassa esimerkissä kuvataan eri skenaariot, joiden avulla hierarkioista voi tehdä kyselyn.  
  
 Kyselyn tekeminen asiakashierarkiasta  
  
 ![Tilihierarkian kyselyasiakkaat](media/query-accounts.png "Tilihierarkian kyselyasiakkaat")  
  
 Kyselyn tekeminen asiakashierarkiasta ja liittyvistä aktiviteeteista  
  
 ![Kyselyasiakkaan liittyvät aktiviteetit](media/query-account-related-activities.png "Kyselyasiakkaan liittyvät aktiviteetit")  
  
 Kyselyn tekeminen asiakashierarkiasta ja liittyvistä mahdollisuuksista  
  
 ![Kyselyasiakkaan liittyvät mahdollisuudet](media/query-account-related-opportunities.png "Kyselyasiakkaan liittyvät mahdollisuudet")  
  
 Jos haluat tehdä kyselyn tiedoista hierarkiana, sinun on määritettävä jokin entiteetin itseen viittaava 1:N (yksi-moneen) -suhde käyttöön hierarkkisena. Voit ottaa hierarkian käyttöön seuraavasti:  
  
1.  Avaa [ratkaisunhallinta](../model-driven-apps/advanced-navigation.md#solution-explorer). 
  
2.  Valitse entiteetti, valitse **1:N-suhteet** ja valitse sitten (1:N)-suhde. 

3.  Valitse **suhdemääritys**, aseta **Hierarkkinen** valinnaksi **Kyllä**.  
  
> [!NOTE]
> - Joitakin valmiita 1:N-suhteita ei voi mukauttaa. Tämä estää valitsemasta näitä suhteita hierarkkisiksi suhteiksi.  
> - Voit määrittää hierarkkisen suhteen järjestelmän itseen viittaaville suhteille. Tämä sisältää järjestelmätyypin 1:N:n itseen viittaavat suhteet, kuten "contact_master_contact"-suhteen.  
  
<a name="BKMK_Visualizedata"></a>   
## <a name="visualize-hierarchical-data"></a>Hierarkkisten tietojen visualisoiminen  
 Valmiita visualisointeja on seuraavilla järjestelmäentiteeteillä `Account`, `Position`, `Product` ja `User`. Näiden entiteettien ruudukkonäkymässä on hierarkiakaaviokuvake tietueen nimen vasemmalla puolella. Hierarkiakuvake ei näy oletusarvoisesti kaikissa tietueissa. Kuvake näkyy tietueissa, joilla on pää- tai alitietue tai molemmat.  
 
 > [!div class="mx-imgBorder"] 
 > ![Aktiiviset asiakkaat](media/cust-hs-active-account.png "Aktiiviset asiakkaat")  
  
 Jos valitset hierarkiakuvakkeen, voit tarkastella hierarkiaa vasemmalla olevan puunäkymän tai oikealla näkyvän ruutunäkymän avulla alla kuvatulla tavalla.  
  
> [!div class="mx-imgBorder"] 
> ![Tilipuu- ja ruutunäkymä](media/hierachy-security-accounts-tile-view.png "Tilipuu- ja ruutunäkymä")  
  
 Hierarkiaa varten voi ottaa käyttöön muutaman muunkin valmiin järjestelmäentiteetin. Näitä entiteettejä ovat `Case`, `Contact`, `Opportunity`, `Order`, `Quote`, `Campaign` ja `Team`. Kaikki mukautetut kohteet voi ottaa käyttöön hierarkiassa.  
  
> [!TIP]
>  Jos entiteetin voi ottaa käyttöön hierarkiassa, tee seuraavat toimet:  
>  Laajenna ratkaisunhallinnassa entiteetti, jonka haluat. Näkyviin tulee entiteettikomponentti nimeltä **Hierarkia-asetukset**. Entiteeteillä, joita ei voi ottaa käyttöön hierarkiassa, ei ole tätä komponenttia. Dynamics 365 customer engagementin myyntialueen entiteetti on kuitenkin poikkeus. Vaikka myyntialueen entiteetti sisältää **Hierarkia-asetukset**-kohdan, entiteettiä ei voi ottaa käyttöön hierarkiassa.  
  
 Seuraavassa luetellaan asioita, jotka on tärkeä muistaa visualisointien luonnin yhteydessä.  
  
-   Entiteetille voi määrittää hierarkkiseksi vain yhden itseen viittaavan 1:N-suhteen. Tässä suhteessa ensisijaisella ja liittyvällä entiteetillä on oltava sama tyyppi, kuten account_parent_account tai new_new_widget_new_widget.  
  
-   Tällä hetkellä hierarkia ja visualisointi perustuvat vain yhteen entiteettiin. Asiakkaan hierarkia voidaan esittää niin, että se näyttää asiakkaat useilla tasoilla. Asiakkaita ja yhteyshenkilöitä ei kuitenkaan voi näyttää samassa hierarkian visualisoinnissa.  
  
-   Ruudussa voi näyttää enintään neljä kenttää. Jos lisäät ruutunäkymässä käytettävään pikalomakkeeseen enemmän kenttiä, vain neljä ensimmäistä kenttää näytetään.  
  
### <a name="visualization-example"></a>Visualisointiesimerkki  
 Tarkastellaan esimerkkiä mukautetun entiteetin visualisoinnin luonnista. Loimme mukautetun entiteetin nimeltä new_Widget ja itseen viittaavan (1:N)-suhteen **new_new_widget_new_widget** ja merkitsimme sen hierarkkiseksi tässä kuvatulla tavalla:  
  
 ![Pienoissovelluksen suhdemääritys](media/widget-relationship-definition.png "Pienoissovelluksen suhdemääritys")  
  
 Seuraavaksi valitsimme **Hierarkia-asetukset**-ruudukkonäkymässä hierarkkisen suhteen nimeltä **new_new_widget_new_widget**. Täytimme lomakkeen pakolliset kentät. Jos 1:N-suhdetta ei ole vielä merkitty hierakkiseksi, voit siirtyä lomakkeen linkillä suhteen määrityslomakkeeseen ja merkitä siellä suhteen hierarkkiseksi.  
  
 Loimme **pikanäyttölomakkeeseen** pikalomakkeen nimeltä **Pienoissovellushierarkiaruutu-lomake**. Tähän lomakkeeseen lisättiin neljä kenttää, jotka näkyvät kussakin ruudussa.  
  
> [!div class="mx-imgBorder"] 
> ![Luo pikalomake pienoissovellusta varten](media/create-quickf-orm.png "Luo pikalomake pienoissovellusta varten")  
  
 Kun asetukset on tehty valmiiksi, luotiin kaksi tietuetta: Standard Widget (vakiopienoissovellus) ja Premium Widget (premium-pienoissovellus). Kun premium-pienoissovelluksesta on tehty vakiopienoissovelluksen päätaso valintakentän avulla, uusi pienoissovellusruudukkonäkymä näyttää hierarkiakuvakkeet alla kuvatulla tavalla.  
  
> [!div class="mx-imgBorder"] 
> ![Pienoissovelluksen hierarkiaruudukko](media/widget-hierarchy-grid.png "Pienoissovelluksen hierarkiaruudukko")  
  
> [!TIP]
>  Hierarkiakuvakkeet näkyvät tietueruudukkonäkymässä vasta sitten, kun tietueille on muodostettu pää- ja alitason suhde.  
  
 Jos hierarkiakuvake valitaan, näkyviin tulee uusi kaksi tietuetta esittävä pienoissovellushierarkia, jonka vasemmalla puolella on puunäkymä ja oikealle puolella ruutunäkymä. Kukin ruutu sisältää neljä **Pienoissovellushierarkiaruutu-lomakkeessa** määritettyä kenttää.  
 
 > [!div class="mx-imgBorder"] 
 > ![Pienoissovelluksen puu- ja ruutunäkymät](media/widget-tree-tiles.png "Pienoissovelluksen puu- ja ruutunäkymät")  
  
## <a name="see-also"></a>Katso myös  
 [Video: Hierarkkisen suojauksen mallinnus](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)   
 [Video: Hierarkian visualisointi](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)

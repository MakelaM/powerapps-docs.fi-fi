---
title: Mallipohjaisten sovellusten hierarkiatietojen visualisoiminen | MicrosoftDocs
description: 'Tietoja siitä, miten voit tehdä kyselyjä ja visualisoida hierarkiaan liittyviä tietoja'
ms.custom: ''
ms.date: 06/02/2018
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
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="visualize-hierarchical-data-with-model-driven-apps"></a>Mallipohjaisten sovellusten hierarkiatietojen visualisoiminen

> [!NOTE]
> Hierarkkisten tietojen visualisoinnit ovat käytettävissä vain **WWW**-asiakasohjelmalle määritetyissä mallipohjaisissa sovelluksissa. Visualisoinnit eivät ole käytettävissä **Unified Interface** -asiakasohjelmassa. Lisätietoja: [Mallipohjaisen sovelluksen luominen tai muokkaaminen sovellusten suunnitteluohjelmalla](../model-driven-apps/create-edit-app.md)

Kun entiteetti määritetään niin, että sillä on hierarkkinen itseensä viittaava suhde, voit määrittää visualisoinnit tämän hierarkian avulla. Lisätietoja: [Hierarkkisesti järjestettyjen tietojen määrittäminen ja kysely](../common-data-service/define-query-hierarchical-data.md)

Visualisointeja sisältävät entiteetit sisältävät oletusarvoisesti [asiakkaan](/powerapps/developer/common-data-service/reference/entities/account), [position](/powerapps/developer/common-data-service/reference/entities/position) ja [käyttäjän](/powerapps/developer/common-data-service/reference/entities/systemuser). Näiden entiteettien ruudukkonäkymässä on hierarkiakaaviokuvake tietueen nimen vasemmalla puolella. Hierarkiakuvake ei näy oletusarvoisesti kaikissa tietueissa. Niillä tietueilla, jotka on liitetty toisiinsa hierakkisen suhteen avulla, näkyy kuvake.  
  
 ![Asiakkaat, joilla on hierakia](media/account-list-with-hierarchy.png)  
  
 Jos valitset hierarkiakuvakkeen, voit tarkastella hierarkiaa vasemmalla olevan puunäkymän tai oikealla näkyvän ruutunäkymän avulla alla kuvatulla tavalla.  
  
> [!div class="mx-imgBorder"] 
> ![Asiakaspuu ja ruudun näkymä](media/hierachy-security-accounts-tile-view.png)  
  
 Joitakin muita entiteettejä voidaan ottaa käyttöön hierarkiassa. Nämä entiteetit ovat [yhteyshenkilö](/powerapps/developer/common-data-service/reference/entities/contact) ja [ryhmä](/powerapps/developer/common-data-service/reference/entities/team). Kaikki mukautetut kohteet voi ottaa käyttöön hierarkiassa.  
  
Seuraavassa luetellaan asioita, jotka on tärkeä muistaa visualisointien luonnin yhteydessä.  
  
- Entiteetille voi määrittää hierarkkiseksi vain yhden itseen viittaavan 1:N-suhteen. Itseensä viittaavassa suhteessa ensisijaisen entiteetin ja liittyvän entiteetin on oltava sama.  
- Hierarkia ja visualisointi perustuvat vain yhteen entiteettiin. Asiakkaan hierarkia voidaan esittää niin, että se näyttää asiakkaat useilla tasoilla. Asiakkaita ja yhteyshenkilöitä ei kuitenkaan voi näyttää samassa hierarkian visualisoinnissa. 
- Ruudussa voi näyttää enintään neljä kenttää. Jos lisäät ruutunäkymässä käytettävään pikalomakkeeseen enemmän kenttiä, vain neljä ensimmäistä kenttää näytetään. 

## <a name="hierarchy-settings"></a>Hierarkia-asetukset

Voit ottaa visualisoinnit käyttöön hierarkiassa muodostamalla yhteyden hierarkiasta pikalomakkeeseen. Tämä voidaan tehdä vain ratkaisunhallinnan avulla.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Hierarkia-asetukset liitetään entiteettiin ratkaisunhallinnassa. 

1. Valitse [entiteettien tarkastelemisen](../common-data-service/create-edit-entities-solution-explorer.md#view-entities) yhteydessä **Hierarkia-asetukset**.
2. Voit muokata olemassa olevan hierarkia-asetuksia, jos ne ovat käytettävissä. Luo muussa tapauksessa uusi hierarkia valitsemalla **Uusi**.
    
    > [!NOTE]
    > Jos hierarkian asetuksia ei ole, entiteetti ei ole käytössä määritetyssä hierarkiassa.
    >Hierarkia-asetuksia voi olla vain yksi 

1. Määritä tiedot seuraaviin kenttiin:

|Kenttä|Kuvaus|
|--|--|
|**Nimi**|*Pakollinen.* Lisää hierarkia-asetuksille yksilöllinen nimi. Se on yleensä yksinkertaisesti entiteetin nimi. Arvo sisältää ratkaisunjulkaisijan mukautuksen etuliitteen.|
|**Oletuspikalomake**|*Pakollinen.* Valitse olemassa oleva pikalomake tai valitse **Luo uusi**, jolloin avautuu pikalomake-editori, jossa voit luoda uuden pikalomakkeen.|
|**Hierarkkinen suhde**|*Pakollinen.* Jos entiteetin hierarkkinen suhde on jo määritetty, arvo määritetään tässä. Jos arvoa ei ole, valitse **Merkitse suhde käyttöönotetuksi hierarkioille**. Valitse näyttöön avautuvasta valintaikkunasta jokin käytettävissä olevista itseensä viittaavista suhteista.|
|**Kuvaus**|Sisällytä tämän hierarkian merkityksen kuvaus, jotta järjestelmää tulevaisuudessa mukauttavat henkilöt saavat tietoja siitä, miksi tämä on tehty.|
    

Visualisoinnin samat hierarkkiset asetuksen määritetään kerran, mutta niitä käytetään sekä :n WWW-sovelluksessa että mobiiliasiakasohjelmissa. Taulutietokoneissa visualisoinnit esitetään niille sopivassa muokatussa muodossa. Hierarkkisille visualisoinneille vaadittavat mukautettavat komponentit ovat ratkaisukohtaisia, jonka vuoksi ne voidaan siirtää organisaatiosta toiseen muiden mukautusten tavoin. Voit määrittää visualisoinnissa näytettävät määritteet mukauttamalla pikalomakkeen lomake-editorin avulla.
  
## <a name="visualization-walk-through"></a>Visualisoinnin opetusohjelma

Tarkastellaan esimerkkiä mukautetun entiteetin visualisoinnin luonnista. Loimme mukautetun entiteetin nimeltä `new_Widget` ja itseen viittaavan (1:N)-suhteen `new_new_widget_new_widget` ja merkitsimme sen hierarkkiseksi alla esitetyllä tavalla.  
  
![Pienoisohjelman suhteen määritys](media/widget-relationship-definition.png)  
  
Seuraavaksi valitsimme **Hierarkia-asetukset**-ruudukkonäkymässä hierarkkisen suhteen nimeltä `new_new_widget_new_widget`. Täytimme lomakkeen pakolliset kentät. Jos 1:N-suhdetta ei ole vielä merkitty hierakkiseksi, voit siirtyä lomakkeen linkillä suhteen määrityslomakkeeseen ja merkitä siellä suhteen hierarkkiseksi.  

> [!IMPORTANT]
> Kullakin kohteella voi olla vain yksi hierarkkinen suhde kerralla. Suhteen muuttamisella itseensä viittaavaksi suhteeksi voi olla seurauksia. Lisätietoja: [Hierarkkisten tietojen määrittäminen](../common-data-service/define-query-hierarchical-data.md#define-hierarchical-data)

> [!div class="mx-imgBorder"] 
> ![Hierarkia-asetukset](media/hierarchy-settings.png)  
  
Loimme **pikanäyttölomakkeeseen** pikalomakkeen nimeltä **Pienoissovellushierarkiaruutu-lomake**. Tähän lomakkeeseen lisättiin neljä kenttää, jotka näkyvät kussakin ruudussa.  

> [!div class="mx-imgBorder"] 
> ![Luo pienoisohjelman pikalomake](media/create-quickform.png)  
  
Kun asetukset on tehty valmiiksi, luotiin kaksi tietuetta: *vakiopienoissovellus* ja *premium-pienoissovellus*. Kun premium-pienoissovelluksesta on tehty vakiopienoissovelluksen päätaso valintakentän avulla, uusi `new_Widget`-ruudukkonäkymä näyttää hierarkiakuvakkeet alla kuvatulla tavalla.  

> [!div class="mx-imgBorder"] 
> ![Pienoissovelluksen hierarkiaruudukko](media/widget-hierarchy-grid.png)  
  
> [!NOTE]
>  Hierarkiakuvakkeet näkyvät tietueruudukkonäkymässä vasta sitten, kun tietueille on muodostettu hierarkkinen suhde.  
  
Jos hierarkiakuvake valitaan, näkyviin tulee uusi kaksi tietuetta esittävä `new_Widget`-hierarkia, jonka vasemmalla puolella on puunäkymä ja oikealle puolella ruutunäkymä. Kukin ruutu sisältää neljä **Pienoissovellushierarkiaruutu-lomakkeessa** määritettyä kenttää.  

> [!div class="mx-imgBorder"] 
> ![Pienoissovelluksen puu- ja ruutunäkymä](media/widget-tree-tiles.png)  

Käyttäjä voi valita tarpeidensa mukaan puunäkymän, jossa näkyy koko hierarkia, tai ruutunäkymän, joka esittää pienemmän osan hierarkiasta. Näkymät esitetään rinnakkain. Voit tutkia hierarkian laajentamalla ja supistamalla hierarkiapuuta. 

### <a name="see-also"></a>Katso myös 

[Hierarkkisesti järjestettyjen tietojen määrittäminen ja kysely](../common-data-service/define-query-hierarchical-data.md)<br />
[Video: Hierarkian visualisointi](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)

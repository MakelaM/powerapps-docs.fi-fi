---
title: Hierarkkisten tietojen visualisointi mallipohjaisilla sovelluksilla | MicrosoftDocs
description: Ohjeet kyselyn tekemiseen hierarkkisesti toisiinsa liittyvistä tiedoista ja niiden visualisoimiseen
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
ms.openlocfilehash: bed8662d7d9475215df8e92490702b68e36574e2
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680019"
---
# <a name="visualize-hierarchical-data-with-model-driven-apps"></a>Hierarkkisten tietojen visualisointi mallipohjaisilla sovelluksilla

> [!NOTE]
> Hierarkkisten tietojen visualisoinnit ovat käytettävissä vain mallipohjaisille sovelluksille, jotka on määritetty **verkko**asiakkaalle. Visualisoinnit eivät ole käytettävissä **Unified Interface** -asiakkaalle. Lisätietoja: [Malliin perustuvan sovelluksen luominen sovellusten suunnitteluohjelmalla](../model-driven-apps/create-edit-app.md)

Kun entiteetti on määritetty niin, että siinä on hierarkkinen itseensä viittaava suhde, voit määrittää visualisointeja käyttämällä kyseistä hierarkiaa. Lisätietoja: [Hierarkkisten tietojen määrittäminen ja kyselyjen tekeminen](../common-data-service/define-query-hierarchical-data.md)

Entiteetit, joissa on oletusarvoisesti käytettävissä visualisointeja, ovat [Tili](/powerapps/developer/common-data-service/reference/entities/account), [Sijainti](/powerapps/developer/common-data-service/reference/entities/position) ja [Käyttäjä](/powerapps/developer/common-data-service/reference/entities/systemuser). Näiden entiteettien ruudukkonäkymässä on hierarkiakaaviokuvake tietueen nimen vasemmalla puolella. Hierarkiakuvake ei näy oletusarvoisesti kaikissa tietueissa. Kuvake näkyy niissä tietueissa, jotka liittyvät hierarkkista suhdetta käyttämällä.  
  
 ![Tilit, joissa on hierarkia](media/account-list-with-hierarchy.png)  
  
 Jos valitset hierarkiakuvakkeen, voit tarkastella hierarkiaa vasemmalla olevan puunäkymän tai oikealla näkyvän ruutunäkymän avulla alla kuvatulla tavalla:  
  
 ![Tilipuu ja ruutunäkymä](media/hierachy-security-accounts-tile-view.png)  
  
 Muutama muu entiteetti voidaan ottaa käyttöön hierarkiassa. Näihin entiteetteihin kuuluu [Yhteyshenkilö](/powerapps/developer/common-data-service/reference/entities/contact) ja [Ryhmä](/powerapps/developer/common-data-service/reference/entities/team). Kaikki mukautetut kohteet voi ottaa käyttöön hierarkiassa.  
  
Asioita, jotka on tärkeä muistaa visualisointien luonnin yhteydessä:  
  
- Entiteetille voi määrittää hierarkkiseksi vain yhden itseen viittaavan (1:N)-suhteen. Itseen viittaavassa suhteessa ensisijaisen entiteetin ja liittyvän entiteetin on oltava samaa tyyppiä.  
- Hierarkia ja visualisointi perustuvat vain yhteen entiteettiin. Tilihierarkia voidaan esittää niin, että se näyttää tilit useilla tasoilla. Tilejä ja yhteystietoja ei kuitenkaan voi näyttää samassa hierarkian visualisoinnissa. 
- Ruudussa voi näyttää enintään neljä kenttää. Jos lisäät kenttiä ruutunäkymässä käytettävään pikalomakkeeseen, vain neljä ensimmäistä kenttää näytetään. 

## <a name="hierarchy-settings"></a>Hierarkia-asetukset

Ottaaksesi visualisoinnit käyttöön hierarkiassa, sinun on yhdistettävä hierarkia pikalomakkeeseen. Sen voi tehdä vain ratkaisunhallinnassa.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Hierarkia-asetukset liittyvät ratkaisunhallinnassa olevaa entiteettiin. 

1. [Entiteettien tarkastelun](../common-data-service/create-edit-entities-solution-explorer.md#view-entities) aikana valitse **Hierarkia-asetukset**.
2. Jos aiemmin luotu hierarkia-asetus on olemassa, voit muokata sitä. Muutoin luo uusi valitsemalla **Uusi**.
    
    > [!NOTE]
    > Jos hierarkia-asetusta ei ole, entiteetti ei ole kelvollinen hierarkian määrittämiseen.
    >Ainoastaan yksi hierarkia-asetus voi olla olemassa 

1. Määritä seuraavien kenttien tiedot:

|Kenttä|Kuvaus|
|--|--|
|**Nimi**|*Pakollinen.* Lisää hierarkia-asetusten yksilöivä nimi. Tämä on yleensä entiteetin nimi. Tämä arvo sisältää ratkaisun julkaisijan mukautuksen etuliitteen.|
|**Oletuspikalomake**|*Pakollinen.* Valitse olemassa oleva pikalomake tai luo uusi valitsemalla **Luo uusi**, jolloin pikalomake-editori avautuu.|
|**Hierarkkinen suhde**|*Pakollinen.* Jos hierarkkinen suhde on jo määritetty entiteetille, arvo määritetään tässä. Jos arvoa ei ole, valitse **Merkitse suhde käytössä olevaksi hierarkioille**, jolloin avautuvassa valintaikkunassa voit valita jonkin käytettävissä olevan itseen viittaavan suhteen.|
|**Kuvaus**|Sisällytä tarkoituksen kuvaus tälle hierarkialle, jotta järjestelmää myöhemmin mukauttavat henkilöt ymmärtävät, miksi tämä tehtiin.|
    

Samat hierarkkiset asetukset määritetään visualisoinnille kerran, mutta ne koskevat sekä verkko- että mobiiliasiakkaita. Tableteissa visualisoinnit esitetään niille sopivassa muokatussa muodossa. Hierarkkisille visualisoinneille vaadittavat mukautettavat osat ovat ratkaisukohtaisia, joten ne voidaan siirtää organisaatiosta toiseen muiden mukautusten tavoin. Voit määrittää visualisoinnissa näytettävät määritteet mukauttamalla pikalomakkeen lomake-editorin avulla.
  
## <a name="visualization-walk-through"></a>Visualisoinnin läpikäynti

Tarkastellaan esimerkkiä mukautetun entiteetin visualisoinnin luonnista. Luotiin mukautettu entiteetti nimeltä `new_Widget` ja itseen viittaava (1:N)-suhde `new_new_widget_new_widget`, ja se merkittiin hierarkkiseksi seuraavasti:  
  
![Pienoissovelluksen suhteen määritys](media/widget-relationship-definition.png)  
  
Seuraavaksi **Hierarkia-asetukset**-ruudukkonäkymässä valittiin hierarkkinen suhde nimeltä `new_new_widget_new_widget`. Lomakkeen pakolliset kentät täytettiin. Jos (1:N)-suhdetta ei ole vielä merkitty hierarkkiseksi, voit siirtyä lomakkeen linkillä suhteen määrityslomakkeeseen ja merkitä siellä suhteen hierarkkiseksi.  

> [!IMPORTANT]
> Jokaisella entiteetillä voi olla vain yksi hierarkkinen suhde kerrallaan. Tämän muuttamisella toiseksi itseen viittaavaksi suhteeksi voi olla seurauksia. Lisätietoja: [Hierarkkisten tietojen määrittäminen](../common-data-service/define-query-hierarchical-data.md#define-hierarchical-data)
  
![Hierarkia-asetukset](media/hierarchy-settings.png)  
  
**Pikalomake**-kohtaan luotiin pikalomake nimeltä **Pienoissovellushierarkiaruutu-lomake**. Tähän lomakkeeseen lisättiin neljä kenttää, jotka näkyvät kussakin ruudussa.  
  
![Pikalomakkeen luominen pienoissovellukselle](media/create-quickform.png)  
  
Määritysten jälkeen luotiin kaksi tietuetta: *Standard Widget* (vakiopienoissovellus) ja *Premium Widget* (premium-pienoissovellus). Kun premium-pienoissovelluksesta on tehty vakiopienoissovelluksen päätaso hakukentän avulla, `new_Widget`-ruudukkonäkymä näyttää hierarkiakuvakkeet alla kuvatulla tavalla:  
  
![Pienoissovelluksen hierarkiaruudukko](media/widget-hierarchy-grid.png)  
  
> [!NOTE]
>  Hierarkiakuvakkeet näkyvä tietueruudukkonäkymässä vasta sitten, kun tietueille on muodostettu hierarkkinen suhde.  
  
Jos hierarkiakuvake valitaan, näkyviin tulee uusi kaksi tietuetta esittävä `new_Widget`-hierarkia, jonka vasemmalla puolella on puunäkymä ja oikealle puolella ruutunäkymä. Kukin ruutu sisältää neljä **Pienoissovellushierarkiaruutu-lomakkeessa** määritettyä kenttää.  
  
![Pienoissovelluksen puu- ja ruutunäkymät](media/widget-tree-tiles.png)  

Käyttäjä voi valita tarpeidensa mukaan puunäkymän, jossa näkyy koko hierarkia, tai ruutunäkymän, joka esittää pienemmän osan hierarkiasta. Näkymät esitetään rinnakkain. Voit tutkia hierarkiaa laajentamalla ja kutistamalla hierarkiapuuta. 

### <a name="see-also"></a>Katso myös 

[Hierarkkisten tietojen määrittäminen ja kyselyjen tekeminen](../common-data-service/define-query-hierarchical-data.md)<br />
[Video: Hierarkian visualisointi](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
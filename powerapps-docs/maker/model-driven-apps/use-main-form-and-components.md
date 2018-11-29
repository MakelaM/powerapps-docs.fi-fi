---
title: Mallipohjaisen sovelluksen päälomakkeen ja sen osien käyttäminen PowerAppsissa | Microsoft Docs
description: Päälomakkeen ja sen osien käyttäminen Unified Interface -perusteisissa sovelluksissa
keywords: Päälomakkeet; Customer service; asiakaspalvelukeskus; Dynamics 365
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 43bfface-4dc2-411d-99a1-83e934646989
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-the-model-driven-app-main-form-and-its-components"></a>Mallipohjaisen sovelluksen päälomakkeen ja sen komponenttien käyttäminen

Unified Interface -pohjaisten sovellusten lomakkeet parantavat käyttökokemusta, mikä parantaa asiakaspalvelijan tuottavuutta ja auttaa säilyttämään asiayhteyden liittyviä tietueita käytettäessä. Näet ratkaisunhallinnassa olevat lomakkeet. Uusien lomakkeiden tyyppi on **Pää**.

Tässä ohjeaiheessa kerrotaan, miten lomakkeita muokataan lisäämällä tai muuttamalla lomakkeen eri elementtejä.

## <a name="open-the-form-editor"></a>Lomake-editorin avaaminen

Lomaketta voi muokata tai siihen lisätä uusia osia käyttämällä lomake-editoria. Voit muokata kaikkia Unified interface -pohjaisten sovellusten lomakkeita lomake-editorissa.

Käytä lomake-editoria seuraavien ohjeiden mukaisesti. 

> [!NOTE]
> Jos haluat luoda lomaketta muokattaessa ratkaisun osia, osien nimet käyttävät oletusratkaisussa ratkaisujulkaisijan mukautuksen etuliitettä ja kyseiset osat sisältyvät vain oletusratkaisuun. Jos haluat uusien ratkaisun osien sisältyvän tiettyyn ei-hallittuun ratkaisuun, avaa lomake-editori kyseisessä ei-hallitussa ratkaisussa.


### <a name="access-the-form-editor-through-app-designer-in-powerapps"></a>Lomake-editorin käyttäminen PowerAppsin sovellusten suunnitteluohjelmassa

1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  

2.  Valitse vasemmanpuoleisessa siirtymisruudussa **Sovellukset** ja valitse sitten haluamasi sovellus. Valitse työkaluriviltä **Muokkaa**.  

3. Valitse sovelluksen suunnitteluohjelman kaaviossa alanuoli ![Sovellusten suunnitteluohjelman alanuoli](media/down-arrow-app-designer.png) entiteetin vieressä, jolloin näet entiteetin käytettävissä olevat lomakkeet. 

4. Valitse Avaa suunnitteluohjelma -painike ![ja avaa suunnitteluohjelma,](media/site-map-designer.png)joka vastaa muokattavaa lomaketta.

   ![Sovellusten suunnitteluohjelma lomake-editori](media/app-designer-forms.png)
 
5. Tee valinnat lomakkeen suunnitteluohjelmassa. Tallenna muutokset valitsemalla **Tallenna** ja julkaise ne sovelluksen käytettäväksi valitsemalla **Julkaise**. 

> [!NOTE]
> Jos olet tehnyt muita muutoksia sovellukseen, julkaise ne käyttämällä sovellustason julkaisuvaihtoehtoa. Lisätietoja on kohdassa [Sovelluksen tarkistaminen ja julkaiseminen sovellusten suunnitteluohjelmalla](validate-app.md).

> [!NOTE]
> Verkkoasiakkaan päälomake on myös yhteensopiva asiakaspalvelukeskuksen kanssa ja sitä voi muokata sovellusten suunnitteluohjelmassa.


### <a name="access-the-form-editor-through-the-default-solution"></a>Lomake-editorin käyttö oletusratkaisussa

1.  Kirjaudu sisään [PowerApps](https:///?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti.  

3. Avaa lomakeluettelosta lomake, joka tyyppi on **Pää**.

### <a name="access-the-form-editor-for-an-unmanaged-solution"></a>Ei-hallitun ratkaisun lomake-editorin käyttäminen

1. Avaa [Ratkaisut](advanced-navigation.md#solutions).
2. Kaksoisnapsauta käsiteltävää ei-hallittua ratkaisua. Ratkaisun tyyppi, hallittu tai hallitsematon, näkyy **Pakkauksen tyyppi** -sarakkeessa.
3. Etsi osaluettelosta entiteetti, jolla on muokattava lomake. Jos entiteettiä ei ole, se on lisättävä.

#### <a name="add-an-entity-to-an-unmanaged-solution"></a>Entiteetin lisääminen ei-hallittuun ratkaisuun

1. Kun hallitsematon ratkaisu on avattu ratkaisunhallintaan, valitse **Entiteetit**-solmu ja valitse luettelon alla olevalta työkaluriviltä **Lisää aiemmin luotu**.

     > [!div class="mx-imgBorder"] 
     > ![Aiemmin luodun entiteetin lisääminen](media/add-existing-entity.png)

2. Varmista ensin, että **Valitse ratkaisun osat** -valintaikkunan **Osan tyyppi** -valitsimessa on valittu **Entiteetti**, napsauta sitten lisättävä entiteetti ja napsauta lopuksi **OK**.

3. Jos **Pakollisia osia puuttuu** -valintaikkuna avautuu, voit valita **Ei, älä lisää pakollisia osia**, jos et aio viedä tätä ei-hallittua ratkaisua toiseen organisaatioon. Jos et halua sisällyttää puuttuvia pakollisia osia nyt, voit lisätä ne myöhemmin. Ilmoitus näkyy uudelleen, jos viet ratkaisun myöhemmin.

4. Laajenna ratkaisunhallinnassa entiteetti, jonka lomaketta haluat muokata, ja valitse **Lomakkeet**.

5. Avaa lomakeluettelosta lomake, joka tyyppi on **Pää**.

#### <a name="publish-the-changes-for-use-in-the-app"></a>Muutosten julkaiseminen sovelluksessa käytettäväksi

Käyttöliittymään muutoksia tekevät mukautukset on julkaistava, ennen kuin käyttäjät näkevät ne sovelluksessa. Jos haluat julkaista tekemäsi mukautukset ratkaisunhallinnan työkalurivillä, valitse **Julkaise kaikki mukautukset**.

## <a name="form-editor-user-interface"></a>Lomake-editorin käyttöliittymä

Lisätietoja lomake-editorin käyttöliittymästä on kohdassa [Lomake-editorin käyttöliittymän yleiskatsaus](form-editor-user-interface-legacy.md).

## <a name="form-properties"></a>Lomakkeen ominaisuudet

Lisätietoja lomakkeen ominaisuuksista on kohdassa [Lomakkeen ominaisuudet](form-properties-legacy.md).

## <a name="visibility-options"></a>Näkyvyysasetukset  
 Monet lomake-elementtityypit voidaan oletusarvoisesti joko näyttää tai piilottaa. Tämä vaihtoehto on myös välilehdissä, osissa ja kentissä. Näiden elementtien näkyvyyttä voidaan hallita lomakkeen komentosarjoilla tai liiketoimintasäännöillä. Tällä tavoin voidaan luoda dynaaminen lomake, joka muodostaa lomakkeen tilan mukaan mukautuvan käyttöliittymän. 
  
> [!NOTE]
>  Lomake-elementtien piilottaminen ei ole suositeltava tapa suojata lomake. Käyttäjillä on useita tapoja, joilla he voivat tarkastella piilotettuja elementtejä käyttävän lomakkeen kaikkia elementtejä ja tietoja. Lisätietoja on kohdassa [Lomake-elementtien näyttäminen tai piilottaminen](visibility-options-legacy.md). 
  
## <a name="tab-properties"></a>Välilehden ominaisuudet  

Lomakkeen runko erotellaan vaakasuunnassa välilehtien avulla. Välilehdissä on otsikko, joka voidaan näyttää. Jos otsikko on näkyvissä, välilehdet voidaan laajentaa näyttämään sisältö tai tiivistää piilottamaan sisältö valitsemalla otsikko. Lisätietoja välilehden ominaisuuksista on kohdassa [Välilehden ominaisuudet](tab-properties-legacy.md).


## <a name="section-properties"></a>Osan ominaisuudet  

Lomakkeen osa käyttää välilehtisarakkeessa olevaa tilaa. Osilla on otsikko, joka voidaan näyttää, ja otsikon alapuolella voidaan näyttää viiva. Lisätietoja osan ominaisuuksista on kohdassa [Osan ominaisuudet](section-properties-legacy.md).
  
## <a name="timeline"></a>Aikajana  
 Tiettyyn entiteettiin liittyvät aktiviteetit näkyvät aikajanalla.  
  
 Seuraavanlaiset aktiviteetit ovat tuettuja: tehtävä, tapaaminen, puhelu, sähköposti, sosiaalinen aktiviteetti, mukautettu aktiviteetti.  
  
 Myös huomautukset sekä järjestelmän ja käyttäjän julkaisut näkyvät aikajanalla. Se näyttää aktiviteetit, joiden **Liittyy**-kenttään on määritetty tarkastelemasi entiteetti. Muistiinpanojen **Liittyy**-kenttä ei näy käyttäjälle. Se on implisiittinen aikajanasta luotaessa.  
  
 Jokaisella aikajanalla näkyvällä aktiviteetilla on samat pikatoiminnot, jotka olisivat saatavilla aktiviteetin komentorivillä.  

## <a name="common-field-properties"></a>Yleiset kentän ominaisuudet  

Lisätietoja yleisistä kentän ominaisuuksista on kohdassa [Yleiset kentän ominaisuudet](common-field-properties-legacy.md). 
  
## <a name="special-field-properties"></a>Erikoiskentän ominaisuudet  
 Kaikkien kenttien sisältämiä ominaisuuksia käsitellään kohdassa [yleiset kenttäominaisuudet](common-field-properties-legacy.md), mutta tietyillä kentillä on lisäominaisuuksia. Lisätietoja on kohdassa, [Erikoiskentän ominaisuudet](special-field-properties-legacy.md).

  
## <a name="sub-grid-properties"></a>Aliruudukon ominaisuudet  

Voit määrittää aliruudukon lomakkeessa näyttämään tietueluettelon tai kaavion. Lisätietoja aliruudukon ominaisuuksista on kohdassa [Aliruudukon ominaisuudet](sub-grid-properties-legacy.md).

## <a name="quick-view-control-properties"></a>Pikanäkymän ohjausobjektin ominaisuudet  

Lomakkeen pikanäkymän ohjausobjekti näyttää lomakkeen valintakentässä valitun tietueen. Lisätietoja pikanäkymän ohjausobjektin ominaisuuksista on kohdassa [Pikanäkymän ohjausobjektin ominaisuudet](quick-view-control-properties-legacy.md).
  
## <a name="web-resource-properties"></a>Verkkoresurssin ominaisuudet  

Voit lisätä tai muokata lomakkeen verkkoresursseja niin, että se on kiinnostavampi tai hyödyllisempi sovelluskäyttäjille. Lomakkeessa käyttöön otetut verkkoresurssit ovat kuvia, HTML-tiedostoja tai Silverlight-ohjausobjekteja. Lisätietoja verkkoresurssin ominaisuuksista. Siirry kohtaan [Verkkoresurssin ominaisuudet](web-resource-properties-legacy.md). 
  
## <a name="iframe-properties"></a>IFRAME-ominaisuudet  

Voit lisätä iFrame-kehyksen integroimaan toisen sivuston sisältöä lomakkeeseen. Lisätietoja IFRAME-ominaisuuksista on kohdassa [IFRAME-ominaisuudet](iframe-properties-legacy.md). 
  
## <a name="edit-navigation"></a>Siirtymisen muokkaaminen  
 Koska lomakkeessa voi siirtyä, käyttäjät voivat tarkastella liittyvien tietojen luetteloita. Kussakin entiteettisuhteessa on ominaisuuksia, joilla hallitaan sen näyttämistä. Lisätietoja: [Ensisijaisen entiteetin siirtymisruudun kohde](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)
  
 Näytettäviksi määritetyt entiteettisuhteet voidaan ohittaa lomake-editorissa.  
  
 Tarkat ohjeet on kohdassa [Lomakkeen siirtymisalueen lisääminen liittyviin entiteetteihin](add-edit-form-navigation-related-entities.md).
  
 Jos haluat ottaa siirtymisen muokkaamisen käyttöön, sinun on ensin valittava **Siirtyminen** **Koti**-välilehden **Valitse**-ryhmässä.  
  
 Voit käyttää **suhteiden hallinnassa** suodatukseen 1:N (yksi moneen)- tai N:N (monta moneen) -suhteita tai näyttää kaikki käytettävissä olevat suhteet. **Näytä vain käyttämättömät suhteet** -valintaruutu on poistettu käytöstä ja valittu. Niinpä voit lisätä kunkin suhteen vain kerran.  
  
 Jos haluat lisätä suhteen **suhteiden hallinnassa**, kaksoisnapsauta sitä, jolloin se lisätään siirtymisalueella valittuna olevan suhteen alapuolelle. Kaksoisnapsauta suhdetta siirtymisalueella. Voit nyt muuttaa otsikon **Näytä**-välilehdessä. **Nimi**-välilehdessä on tietoja suhteesta. Voit avata entiteetin määritelmän **Muokkaa**-painikkeella.  
  
 Siirtymisalueella on viisi ryhmää. Voit muuttaa niiden sijaintia vetämällä ja vaihtaa niiden otsikon kaksoisnapsauttamalla. Et voi kuitenkaan poistaa niitä. Nämä ryhmät näkyvät vain, kun niissä on sisältöä. Jos et halua ryhmän näkyvän, älä lisää siihen mitään.  
  
## <a name="configure-event-handlers"></a>Tapahtumakäsittelijöiden määrittäminen  

Tapahtumakäsittelijä sisältää viittauksen JavaScript-WWW-resurssiin ja toimintoon, joka on määritetty kyseisessä verkkoresurssissa ja joka suoritetaan tapahtuman tapahtuessa. Lisätietoja tapahtumakäsittelijöiden määrittämisestä on kohdassa [Tapahtumakäsittelijöiden määrittäminen](configure-event-handlers-legacy.md). 
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Luo ja suunnittele lomakkeita](create-design-forms.md)   
 [Luo ja muokkaa pikaluontilomakkeita nopeasti](create-edit-quick-view-forms.md)   
 [Luo ja muokkaa lomakkeita nopeasti](create-edit-quick-view-forms.md)

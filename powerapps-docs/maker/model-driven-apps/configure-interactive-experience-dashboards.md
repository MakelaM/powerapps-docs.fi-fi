---
title: Mallipohjaisen sovelluksen vuorovaikutteisen kokemuksen koontinäyttöjen määrittäminen PowerAppsissa | Microsoft Docs
description: Vuorovaikutteisen kokemuksen koontinäyttöjen PowerAppsissa
keywords: Vuorovaikutteiset koontinäytöt; Customer Service; Microsoft Dynamics 365; Vuorovaikutteinen palvelukeskus
author: Mattp123
ms.author: matp
manager: kvivek
ms.custom: ''
ms.date: 04/19/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: d1446a95-14bf-4b15-a905-72fce07f4c76
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="configure-model-driven-app-interactive-experience-dashboards"></a>Mallipohjaisen sovelluksen vuorovaikutteisen kokemuksen koontinäyttöjen määrittäminen

Vuorovaikutteisen kokemuksen koontinäytöt tuovat sovelluskäyttäjille, kuten palveluneuvojille, yhden keskitetyn pisteen, jossa he voivat tarkastella kuormitustietoja ja tehdä toimintoja. Koontinäytöt ovat täysin määritettävissä, käyttöoikeusrooliin perustuvia ja näyttävät kuormituksen tiedot reaaliajassa useista viestivirroista. Vuorovaikutteisen koontinäytön käyttäjien ei tarvitse etsiä sovelluksesta määrättyä tietuetta, koska ne voi suorittaa suoraan koontinäytöstä. 

 Vuorovaikutteisen kokemuksen koontinäytöillä on kaksi muotoa: Monen virran koontinäyttö ja Yhden virran koontinäyttö. Lisäksi Monen virran koontinäytöt voivat olla kotisivu tai entiteetin koontinäyttöjä. Entiteetin koontinäytöt on määritetty käyttöliittymän eri osissa ja osittain valmiiksi ladattu entiteetin määritystiedoilla.  
  
 Monen virran koontinäyttö näyttää tiedot reaaliajassa useista viestivirroista. Ei ole rajaa, kuinka monta viestivirtaa voit määrittää koontinäyttöön. Viestivirran tietojen perustana voidaan käyttää vain yhtä entiteettiä, mutta jokainen viestivirta voi perustua eri entiteettiin. Entiteetin koontinäytössä kaikki viestivirrat perustuvat samaan entiteettiin. Tiedot ovat peräisin eri näkymistä tai jonoista, kuten **Omat aktiviteetit**, **Omat palvelupyynnöt** tai **Pankkijonon palvelupyynnöt**. 
  
 Yhden virran koontinäyttö näyttää reaaliaikaisia tietoja yhdestä viestivirrasta entiteetin näkymän tai jonon mukaan. Ruudut on asemoitu koontinäyttöjen oikealla puolella, ja ne näkyvät aina. Yhden virran koontinäytöt ovat tyypillisesti hyödyllisiä Tier 2 -johtajille tai -päälliköille, jotka seuraavat vähemmän, mutta enemmän monimutkaisia tai eskaloituja tapauksia.  
  
 Monen virran koontinäyttö ja Yhden virran koontinäyttö sisältää vuorovaikutteisia kaavioita, jotka antavat asianmukaisten tietueiden määrän, kuten palvelupyynnöt prioriteetin mukaan tai tilan mukaan. Nämä kaaviot toimivat myös visuaalisina suodattimina. Visuaaliset suodattimet (vuorovaikutteisia kaavioita) perustuvat useisiin entiteetteihin, ja yhden virran koontinäytöissä viestivirran entiteetti määrittää visuaalisen suodattimen entiteetin.   
  
 Käyttäjä voi käyttää lisäsuodattimia yleisten suodattimien ja aikajaksosuodattimien lisäksi. Yleinen suodatin toimii kenttätasolla kaikissa kaavioissa ja myös virroissa ja ruuduiissa, jotka perustuvat suodattimen entiteettiin (voit määrittää suodattimen entiteetin määrittäessäsi visuaalisia suodattimia). 
  
> [!NOTE]
>  Vuorovaikutteiset koontinäytöt ovat ratkaisukohtaisia ja voidaan viedä ja tuoda sitten ratkaisuna ympäristöön. Kuitenkin jonot, joihin virrat ja ruudut perustuvat, eivät ole ratkaisukohtaisia. Ennen kuin tuot koontinäyttöratkaisun kohdejärjestelmään, jonot luodaan manuaalisesti kohdejärjestelmässä valinnalla **Asetukset** > **Palveluiden hallinta** > **Jonot**. Kun olet luonut jonot, tuo koontinäyttöratkaisu kohdejärjestelmään ja muokkaa viestivirtoja tai ruutuja, jotka perustuvat jonoihin, jotka delegoivat juuri luodut jonot asianmukaisesti.  
  
 Tässä aiheessa kuvat näyttävät Monen virran koontinäyttö ja Yhden virran koontinäyttö sekä otsikkoruudun. Otsikon alla näet Visuaaliset suodattimet ja Viestivirrat. Yhden virran koontinäytössä näkyvät myös ruudut. Jokaiselle koontinäyttötyypille voit valita useista asetteluista, jotka myös näytetään. Koontinäytön otsikossa näkyvät seuraavat komponentit ja napsautettavat kuvakkeet, vasemmalta oikealle: koontinäyttövalitsin, päivitys, visuaalinen suodatinkuvake, yleinen suodatuskuvake ja aikajakson suodatus.  
  
### <a name="multi-stream-dashboard-standard-view"></a>Monen virran koontinäyttö vakionäkymä  
 Monen virran koontinäytössä on Visuaaliset suodattimet rivin yläosassa ja alla tietovirtoja.  
 
![Monen viestivirran vuorovaikutteinen koontinäyttö](media/interactive-dashboards-multi-stream.png) 
   
### <a name="multi-stream-dashboard-tile-view"></a>Monen virran koontinäyttö ruutunäkymä  
 Sama koontinäyttö, vain ruutunäkymässä.  
  
 ![Usean viestivirran koontinäytön ruutunäkymä](media/interactive-dashboards-multi-stream-tiles.png "Usean viestivirran koontinäytön ruutunäkymä")  
  
### <a name="multi-stream-dashboard-layouts"></a>Monen virran koontinäyttö asettelut  
 Monen virran koontinäyttö voidaan valita neljästä eri asettelusta.  

 > [!div class="mx-imgBorder"] 
 > ![Usean viestivirran koontinäyttöjen asetteluja](media/interactive-dashboards-multi-stream-layout.png "Usean viestivirran koontinäyttöjen asetteluja")  
  
### <a name="multi-stream-entity-specific-dashboard"></a>Monen virran entiteettikohtainen koontinäyttö  
 Palvelupyyntö-entiteetin entiteettikohtainen koontinäyttö näkyy tässä.  
  
 ![Avointen palvelupyyntöjen koontinäyttö](media/interactive-dashboard-cases-entity-specific.png "Avointen palvelupyyntöjen koontinäyttö")  
  
### <a name="single-stream-dashboard"></a>Yhden virran koontinäyttö  
 Yhden virran koontinäyttö sisältää vasemmalla tietovirrat ja oikealla Visuaaliset suodattimet ja ruudut.  
  
 ![yhden viestivirran interaktiivisen palvelukeskuksen koontinäyttö](media/interactive-dashboards-single-stream.png "yhden viestivirran interaktiivisen palvelukeskuksen koontinäyttö")  
  
### <a name="single-stream-dashboard-layouts"></a>Yhden virran koontinäyttö asettelut  
 Yhden virran koontinäyttö voidaan valita neljästä eri asettelusta.  
 
 > [!div class="mx-imgBorder"] 
 > ![Yhden viestivirran koontinäyttöjen asetteluja](media/interactive-dashboards-single-stream-layout.png "Yhden viestivirran koontinäyttöjen asetteluja")  
  
<a name="BKMK_Enable"></a>   
## <a name="configure-fiter-fields-and-security-roles-for-the-interactive-dashboards"></a>Suodatuskenttien ja käyttöoikeusroolien määrittäminen vuorovaikutteisille koontinäytöille  
 Kun määrität vuorovaikutteiset koontinäytöt, ensimmäinen tehtävä on ottaa käyttöön suodatuskenttiä ja käyttöoikeusrooleja, jotta niille voidaan määrittää vuorovaikutteiset koontinäytöt. Huomaa, että vuorovaikutteiset koontinäytöt otetaan käyttöön oletusarvoisesti kaikille entiteeteille ja mukautetuille entiteeteille. 
  
### <a name="configure-filter-fields"></a>Suodatuskenttien määrittäminen  
 Sinun on määritettävä kaksi merkintää, jos haluat, että kenttä näkyy yleisessä suodatuksessa ja että sisällytetään tietovirran lajitteluun:

- Näkyy yleisessä suodatuksessa vuorovaikutteisessa kokemuksessa
- Lajiteltavissa vuorovaikutteisen kokemuksen koontinäytössä

Tässä esimerkissä **IsEscalated**-kentän palvelupyyntöentiteetissä on käytettävissä kaksi vuorovaikutteisen koontinäytön asetusta.  

 > [!div class="mx-imgBorder"] 
 > ![Ota käyttöön yleisen suodatuksen ja lajittelun kenttä käyttöön](media/enable-filter-sort.png "Ota käyttöön yleisen suodatuksen ja lajittelun kenttä käyttöön")  
  
### <a name="configure-the-appears-in-global-filter-in-interactive-experience-option"></a>Näkyy yleisessä suodatuksessa vuorovaikutteisessa kokemuksessa -vaihtoehdon määrittäminen

1. Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
2. Laajenna **Osat**-kohdasta **Entiteetit** ja laajenna sitten haluamasi entiteetti.
3. Valitse siirtymisruudussa **Kentät** ja kaksoisnapsauta ruudukossa kenttää, jonka haluat ottaa käyttöön.
4. Valitse **Yleinen**-välilehdessä **Näkyy yleisessä suodatuksessa vuorovaikutteisessa kokemuksessa** -valintaruutu. Valitse **Tallenna ja sulje**.
5. Valitse **Julkaise kaikki mukautukset**, jotta muutokset tulevat voimaan.
  
 Kentät, jotka otat käyttöön **Näkyvät yleisessä suodattimessa vuorovaikutteisessa** -käyttöympäristössä, näkyvät globaalissa suodattimen hajautusikkunassa, kun yleisen suodattimen kuvaketta napsautetaan koontinäytön otsikossa. Pikaikkunassa palveluneuvoja voi valita kentät, jotka haluavat suodattaa yleisesti, kaavioissa ja myös virroissa ja ruuduissa, jotka perustuvat suodattimen entiteettiin.   
  
 Yleisen suodatuksen pikaikkuna näytetään täällä:  
  
 ![Lisää kaksi yleisen suodatuksen kenttää](media/global-filter-escalated.png "Yleisen suodatuksen kentät")  
  
> [!TIP]
>  Kun määrität visuaalinen suodattimen kenttien, kuten prioriteetin tai tilan, mukaan, paras käytäntö on näiden kenttien (prioriteetti, tila) näkyminen otetaan käyttöön myös yleisessä suodatuksessa.  
  
### <a name="configure-the-sortable-in-interactive-experience-dashboard-option"></a>Lajiteltavissa vuorovaikutteisen kokemuksen koontinäytössä -vaihtoehdon määrittäminen
  
1. Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
2. Laajenna **Osat**-kohdasta **Entiteetit** ja laajenna sitten haluamasi entiteetti.
3. Valitse siirtymisruudussa Kentät ja kaksoisnapsauta ruudukossa kenttää, jonka haluat ottaa käyttöön.
4. Valitse **Yleinen**-välilehdessä **Lajiteltavissa vuorovaikutteisen kokemuksen koontinäytössä** -valintaruutu. Valitse **Tallenna ja sulje**.
5. Valitse **Julkaise kaikki mukautukset**, jotta muutokset tulevat voimaan.
  
Lajittelua varten määritetyt kentät näkyvät avattavan luettelon virran otsikossa. 

Seuraavassa kuvassa näkyy pikaikkuna, jossa on luettelo avattavassa luettelossa olevista lajittelussa käytettävistä kentistä. Oletuslajittelu määritetään aina **Muokattu**-kenttään.  
  
 ![Lajittele avattavasta luettelosta](media/sort-field.png "Lajittele avattavasta luettelosta")    
    
### <a name="enable-security-roles"></a>Ota käyttöön tietosuojaroolit  
 Valitse ja ota käyttöön käyttöoikeusroolit, jotka voivat tarkastella vuorovaikutteisia raporttinäkymiä.  
  
#### <a name="enable-security-roles-for-interactive-dashboards"></a>Ota käyttöön käyttöoikeusroolit interaktiivisille koontinäytöille

1. Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
  
2. Valitse **Osat**-kohdassa **Koontinäytöt**.  
  
3.  Valitse ruudukosta ensin haluamasi vuorovaikutteinen koontinäyttö ja sitten tehtäväpalkissa **Ota käyttöön käyttöoikeusroolit**.  
  
4.  Valitse **Määritä käyttöoikeusroolit** -valintaikkunassa **Näytä vain näille valituille käyttöoikeusrooleille** -vaihtoehto ja lisää sitten valintamerkki vain niille rooleille, joille haluat antaa käyttöoikeuden. Valitse **OK**.  
  
5.  Valitse **Julkaise kaikki mukautukset**, jotta muutokset tulevat voimaan.    
  
 ![Ota käyttöön käyttöoikeusroolit](media/security-roles.png "Ota käyttöön käyttöoikeusroolit")    
  
<a name="BKMK_Configure"></a>   
## <a name="configure-interactive-experience-dashboards"></a>Vuorovaikutteisen kokemuksen koontinäyttöjen määrittäminen  
 Seuraavissa osissa kuvataan, miten erilaisia vuorovaikutteisia koontinäyttöjä määritetään.  
  
### <a name="configure-a-multi-stream-interactive-dashboard-using-the-4-column-layout"></a>Määritä usean viestivirran koontinäytön 4 sarakkeen asettelua käyttäen.  
 
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen. 
  
2.  Valitse **Data** > **Entiteetit** > valitse haluamasi entiteetti. 

3.  Valitse **koontinäytöt**-välilehti ja valitse sitten työkaluriviltä **Lisää koontinäyttö**. 
  
4.  Valitse asettelu, 2, 3 tai 4 sarakeleveyttä.  
  
5.  Kun koontinäyttölomake avautuu, täytä suodattamista tiedot lomakkeen yläosassa seuraavasti.  
 
 > [!div class="mx-imgBorder"] 
 > ![Lisää visuaaliset suodattimet](media/interactive-dashboards-add-visual-filters.png "Lisää visuaaliset suodattimet")  
  
   - **Suodata entiteetti**: visuaaliset suodattimet ja yleisen suodatuksen määritteet perustuvat tähän entiteettiin.  
      
    - **Entiteettinäkymä**: visuaaliset suodattimet perustuvat tähän näkymään.  
      
    - **Suodatusperuste**: kenttä, johon aikavälisuodatinta käytetään.  
      
    - **Aikaväli**: aikavälisuodattimen oletusarvo **Suodatusperuste**-kenttään.  
      
 Kun olet määrittänyt tietoja suodattamista, käynnistä komponenttien lisääminen kaavioihin ja tietovirtoihin. Jos haluat lisätä osan, valitse elementti kaavion tai viestivirran keskellä, ja kun näyttöön tulee valintaikkuna, valitse tarvittavat tiedot avattavasta luettelosta seuraavassa kuvassa esitetyllä tavalla.  
  
 Lisää **Palvelupyynnöt prioriteetin mukaan** -rengaskaavio.
  
 > [!div class="mx-imgBorder"] 
 > ![Lisää rengaskaavio-osa.](media/interactive-dashboards-add-chart-circle.png "Lisää rengaskaavio-osa.")  
  
 Joissakin kaavioissa, kuten palkkikaavioissa tai ympyräkaavioita, tehdä järjestelmään tallennetut tiedot näytetään. Rengaskaaviot ja tunnistekaaviot latautuvat staattisina kuvina ja eivät näytä todellisten tietojen esikatselua.  
  
> [!NOTE]
>  Visuaalisille suodattimia määritetyt kaaviot voivat käyttää **Suodatin**-entiteettien sekä liittyvien entiteettien kenttiä. Kun käytät entiteetin kenttiin perustuvia kaavioita, asiakaspalvelijat voivat suodattaa kaavioita käyttämällä liittyvän entiteetin kenttiä. Liittyvään entiteettiin perustuvissa kentissä on yleensä seuraava muoto kaavion määritysikkunassa: "kenttänimi (kohteen nimi)", kuten **Muokkaaja (delegoitu käyttäjä)** -kenttä. Monientiteettikaavioita luotaessa pitää lisätä liittyvän entiteetin kenttiä kaikkiin näkymiin ja sitten käyttää näitä kenttiä kaavioita luotaessa.  
 
 > [!div class="mx-imgBorder"] 
 > ![Kaavioiden luominen visuaalisille suodattimille](media/interactive-dashboard-visual-charts-x-y-axes.PNG "Kaavioiden luominen visuaalisille suodattimille")  
  
 Seuraavaksi määritetään Viestivirrat. Valitse elementti viestivirtapaneelissa aivan kuten lisättäessä osia kaavioihin. Kun näyttöön tulee valintaikkuna, valitse **Tarkastele** tai **Jono** sen mukaan, mitä osaa haluat viestivirran käyttävän. Anna vaaditut tiedot kuten seuraavassa kuvassa.  
  
 **Käsiteltävissä olevat kohteet** -viestivirran määrittäminen näytetään seuraavaksi:  
  
 ![Lisää omien aktiivisten palvelupyyntöjen viestivirta.](media/add-stream-dashboard.png "Lisää omien aktiivisten palvelupyyntöjen viestivirta.")  

> [!NOTE]
>  **Jono**-asetus on käytettävissä valintaikkunassa vain entiteeteille, joissa jono on otettu käyttöön. Jos jono ei ole käytössä entiteetissä, **jono**-asetus ei näy valintaikkunassa entiteetin raporttinäkymille. Voit käyttää ainoastaan **Näytä-vaihtoehtoa** raporttinäkymän tietovirrassa entiteeteille, joissa jono ei ole käytössä.    
 
Seuraavassa kuvassa on esimerkki kokonaan määritetystä kaaviopaneelista ja viestivirtapaneelista:  
 
 > [!div class="mx-imgBorder"] 
 > ![Kokonaan määritetty koontinäyttö](media/example-stream-visual.png "Kokonaan määritetty koontinäyttö")  
  
 Kun olet suorittanut määrittänyt koontinäytön, tallenna se ja julkaista mukautukset, jotta muutokset tulevat voimaan.   
  
#### <a name="edit-or-delete-individual-streams-of-an-existing-dashboard"></a>Muokkaa tai poista yksittäisiä viestivirtoja koontinäytössä  
  
1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.   
  
2. Valitse **Data** > **Entiteetit** > valitse haluamasi entiteetti. Valitse **Koontinäytöt**-välilehti.  
  
     -TAI-  
   
   Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer), ja sitten **Komponentit**-kohdan alta valitse **Koontinäytöt**.
  
3.  Avaa muokattava vuorovaikutteinen koontinäyttö, jota haluat muokata.  
  
4.  Valitse ensin muokattava viestivirta ja sitten **Muokkaa osaa**.  
  
5.  Valitse sen mukaan, haluatko lisätä näkymän tai jonon viestivirtaan, viestivirran näkymän tai jonon tiedot ja valitse sitten **Määritä**.  
  
6.  Valitse **Tallenna**.  
  
 Voit myös poistaa yksittäisen viestivirran koontinäytöstä. Valitse ensin virta ja sitten komentopalkissa **Poista**.  
  
### <a name="configure-an-entity-specific-dashboard"></a>Määritä entiteettikohtainen koontinäyttö  
 Entiteettikohtainen koontinäyttö on monen virran koontinäyttö. Tämän koontinäytön määrittäminen on samanlainen kuin kotisivun määrittäminen Monen virran koontinäyttöön, mutta se tehdään käyttöliittymän eri paikassa ja siinä on muita vähäisiä eroja. 

Esimerkiksi sen sijaan, että valitaan entiteetti, jotkin kentät entiteettikohtaisessa koontinäytössä on asetettu valmiiksi entiteettiin, johonka koontinäyttöä luodaan.  
  
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.

2.  Valitse **Data** > **Entiteetit** > valitse haluamasi entiteetti. 

3.  Valitse **koontinäytöt**-välilehti ja valitse sitten työkaluriviltä **Lisää koontinäyttö**.  
4.  Valitse asettelu, 2, 3 tai 4 sarakeleveyttä.    
  
5.  Kun koontinäyttölomake avautuu, **Suodata entiteetti** on valmiiksi asetettu entiteettiin, jolle olet luomassa koontinäytön. **Entiteettinäkymän** avattava luettelo sisältää entiteetin käytettävissä olevat näkymät. Valitse näkymä ja Täytä loput tarvittavat tiedot sivulla.  
  
 Loput asetukset on hyvin samankaltainen kuin edellisessä kohdassa kuvatut kotisivun Monen virran koontinäyttö asetukset.  
  
### <a name="configure-a-single-stream-dashboard"></a>Yhden virran koontinäytön määrittäminen  
 Yhden virran koontinäyttö määrittäminen vastaa Monen virran koontinäyttöä. Kaikki Käyttöliittymän siirtymisen vaiheet ovat samat kuin Monen virran koontinäytössä. Voit valita asettelun, joka sisältää ruudut, tai rakenteen, joka ei sisällä ruutuja. Jos ruudut ovat mukana, ne näkyvät aina koontinäytössä. Määritä ruutu valitsemalla kuvake ruudun keskellä. Kun **Lisää ruutu**ikkuna avautuu, täytä tarvittavat tiedot. Seuraavassa kuvassa näkyy esimerkki ruudun määrittämisestä.  
  
 ![Lisää yhden viestivirran raporttinäkymiin ruutu](media/add-tile.png "Lisää yhden viestivirran raporttinäkymiin ruutu")  
  
<a name="BKMK_ConfigureColors"></a>   
## <a name="configure-dashboard-colors"></a>Määritä koontinäytön värit  
 Voit määrittää kaikille **Asetusjoukko**- ja **Kaksi asetusta** -tyyppisille kentille, kuten **Palvelupyyntö**-entiteetin **Palvelupyynnön tyyppi**, **IsEscalated** tai **Prioriteetti**, tietyn värin näkymään kaavioissa ja viestivirroissa tietyillä kentän arvoilla. Esimerkiksi tärkeät tapaukset voidaan näyttää punainen, Normaali prioriteetti tapaukset sinisenä ja matalan prioriteetin tapaukset vihreänä vuorovaikutteisissa kaavioissa. Viestivirroissa väri näkyy vasemmalla puolella työn kohteen kuvaus ohut pystysuora viiva.  
  
> [!NOTE]
>  Värikoodaus ei ole käytettävissä tunniste- ja rengaskaavioissa. Nämä kaaviot näkyvät koontinäyttö valkoisen, harmaan ja mustan sävyt.  
  
1.  Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
2.  Laajenna **Osat**-kohdasta **Entiteetit** ja laajenna sitten haluamasi entiteetti. Jos entiteetti ei ole näkyvissä, valitse **Lisää olemassa oleva** lisätäksesi sen.  
  
3.  Valitse siirtymisruudussa **Kentät**. Kaksoisnapsauta ruudussa kenttää, johonka haluat määrittää värin.  
  
4.  Valitse ensin **Yleinen**-välilehdessä **Tyyppi**-alialueella **Kyllä** ja sitten **Muokkaa**.  
  
5.  Kun **Muokkaa luetteloarvoa** valintaikkuna tulee näkyviin, määritä uusi arvo **väri** tekstiruudussa. Valitse **OK**.  
  
     Valitse **Tallenna ja sulje**.  
  
7.  Valitse **Julkaise**, jotta muutokset tulevat voimaan.  
  
Seuraavassa esimerkissä olemme muuttamassa väri **IsEscalated**-kenttään. **Muokkaa luetteloarvoa** -valintaikkuna **Muokkaa**-painikkeella:  
 
 > [!div class="mx-imgBorder"] 
 > ![Koontinäytön värin muuttaminen](media/edit-color.png "Koontinäytön värin muuttaminen")  
  
Kun **Muokkaa luetteloarvoa** -valintaikkuna avautuu, valitse väri seuraavalla tavalla:  
  
 ![Muokkaa koontinäytön väriä](media/modify-color.png "Muokkaa koontinäytön väriä")  

Jos vastaavasti muokkaat palvelupyynnön prioriteettiasetuksia **Prioriteetti**-kentässä, valitse väri **Yleiset**-välilehden **Asetukset**-alialueella, kuten seuraavassa kuvassa:

 ![Koontinäytön värin muokkaaminen](media/priority-color-modify.png "Vaihda koontinäytön väri palvelupyynnön prioriteettia varten")  
  
### <a name="see-also"></a>Katso myös  
 
[Koontinäyttöjen luominen tai muokkaaminen](create-edit-dashboards.md)
 


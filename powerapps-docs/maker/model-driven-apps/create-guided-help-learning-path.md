---
title: Oman oppimispolun luominen (oppimispolku) (Dynamics 365 for Customer Engagement -sovellukset) | MicrosoftDocs
description: ''
keywords: null
ms.date: 04/30/2019
ms.service: dynamics-365
ms.topic: article
applies_to:
  - Dynamics 365 for Customer Engagement (online)
ms.assetid: 8ee3c432-5f76-4086-b9cc-6cd467ae056b
author: Mattp123
ms.author: matp
manager: kvivek
topic-status: Drafting
search.audienceType:
  - customizer
search.app:
  - D365CE
---

# <a name="create-guided-help-learning-path-for-your-app"></a>Luo oma ohjattu ohje (Learning Path) sovelluksillesi

Anna käyttäjille oppimispolun avulla mukautettu sovellukseen sisältyvä ohjekokemus, joka on suunniteltu ympäristöä sekä organisaation käyttötapoja ja työnkulkuja vastaavaksi. Oppimispolku helpottaa oppimista ja sovellustesi ja organisaation prosessien käyttöönottoa. Se myös varmistaa, että tiedot annetaan ja että niitä tulkitaan yhdenmukaisesti, sekä vähentää virheitä ja käyttäjien tukipyyntöjä. [Katso lyhyt oppimispolkua käsittelevä video (1:50)](https://community.dynamics.com/crm/b/crmvideos/archive/2016/05/09/introducing-learning-path-for-dynamics-crm).  

<a name="CustomHelp"></a>   

## <a name="how-is-learning-path-different-from-customizable-help"></a>Miten oppimispolku eroaa mukautetusta ohjeesta?  
 Mukautetun ohjeen avulla voit korvata oletusarvoisen [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-sovellusten ohjeen ja ohjata organisaatiosi käyttäjät ohjeeseen eri URL-osoitteessa. Tai voit ohittaa ohjeen erittäin mukautetussa entiteetissä, jotta voit kuvata oman työnkulun paremmin. 

 Oppimispolun avulla voit lisätä mukautetun ohjeen, jonka käyttäjäsi näkevät sovelluksessa, kun he avaavat sivun, suorittavat toiminnon tai valitsevat Ohje-painikkeen (?).   

 Lisätietoja on mukautetusta ohjeesta on artikkelissa [Ohje-kokemuksen mukauttaminen](https://technet.microsoft.com/library/dn832079.aspx).  

<a name="Avail"></a>   
## <a name="prerequisites"></a>Edellytykset  

 Oppimispolun sisällön luonti:  

- PowerAppsin tai [!INCLUDE[pn_crm_online_shortest](../../includes/pn-crm-online-shortest.md)] -kohteen käyttäminen.  

- Anna suostumus osallistua oppimispolkuun. Tämä asetus on oletusarvoisesti käytössä, mutta se on voitu poistaa käytöstä.  

   Voit tarkistaa, onko oppimispolku otettu käyttöön valitsemalla siirtymispalkissa **Asetukset** ![Asetukset-kuvake](media/optionsbutton.png "Asetukset-kuvake") > **Anna suostumus osallistua oppimispolkuun**.  

   Lisätietoja: [Oppimispolun Käytössä/ei käytössä-valitsin (Avustava ohje)](/dynamics365/customer-engagement/admin/on-off-switch-for-learning-path-guided-help).  

- Järjestelmän mukauttaja- tai järjestelmänvalvoja-rooli tai jokin muu rooli, jolla on oppimispolun muokkausoikeus.  

- Ota oppimispolun laatiminen käyttöön. Tämän seurauksena luodaan [!INCLUDE[pn_Office_365](../../includes/pn-office-365.md)]:n oppimispolun tekijöiden käyttöoikeusryhmä.  

- Olet [!INCLUDE[pn_Office_365](../../includes/pn-office-365.md)]:n oppimispolun tekijöiden käyttöoikeusryhmän jäsen.  

  Voit tuottaa oppimispolkusisältöä verkkosovellusmoduuleille ja Unified Interface -sovellusmoduuleille. Myös [!include[](../../includes/pn-dyn-365-tablets.md)] sisältyy tähän.  

<a name="TurnOnLP"></a>   
## <a name="turn-on-learning-path-for-your-organization"></a>Ota käyttöön oppimispolku organisaatiossasi  
 Oppimispolku on valinnainen ominaisuus, joka voidaan ottaa käyttöön tai poistaa käytöstä organisaatiossasi. Voit näyttää [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:n mukana toimitetun oppimispolkusisällön, luoda käyttäjille omaa oppimispolkusisältöä tai tehdä molemmat.  

1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)iin tai [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] -sovellukseen järjestelmänvalvojan tilin avulla.  

2. Valitse **Asetukset** ja sitten **Hallinto**-kohdassa **Järjestelmä**. Lisätietoja: [Asetukset](/powerapps/maker/model-driven-apps/advanced-navigation#settings)

3. Valitse **Hallinto**-sivulla **Järjestelmäasetukset**.  

4. Valitse **Yleiset**-välilehdessä kohdassa **Määritä mukautetun ohjeen URL-osoite** **Kyllä** vaihtoehdolle **Oppimispolun ottaminen käyttöön** ja **Ota oppimispolun laatiminen käyttöön**.  

    Voit ottaa käyttöön oppimispolun tai mukautettavissa olevan ohjeen, mutta et molempia samanaikaisesti. Varmista, että asetuksien **Käytä mukautettua ohjetta mukautettuihin entiteetteihin** ja **Lisää parametrit URL-osoitteeseen** arvoiksi on määritetty **Ei**.  

     ![Järjestelmäasetukset-valintaikkunan asetukset, jotka valitsemalla oppimispolun laatiminen otetaan käyttöön](media/lp-system-settings.png "Järjestelmäasetukset-valintaikkunan asetukset, jotka valitsemalla oppimispolun laatiminen otetaan käyttöön")  

5. Valitse **OK**.  

<a name="ReqsAuth"></a>   
## <a name="add-a-user-to-the-office-365-learning-path-authors-security-group"></a>Lisää käyttäjä Office 365 -oppimispolun muokkaajat -suojausryhmään  
 Jos et ole [!INCLUDE[pn_Office_365](../../includes/pn-office-365.md)]:n oppimispolun laatijoiden käyttöoikeusryhmän jäsen, näet seuraavan virhesanoman, kun avaat oppimispolun sisältökirjaston.  

 ![Virhe, joka kertoo, että et ole Oppimispolku-käyttöoikeusryhmän jäsen](media/lp-o365-security-group.png "Virhe, joka kertoo, että et ole Oppimispolku-käyttöoikeusryhmän jäsen")  

#### <a name="add-a-user"></a>Käyttäjän lisääminen  

1. Siirry oman [!INCLUDE[pn_Office_365](../../includes/pn-office-365.md)] -vuokraajasi hallintaportaaliin valitsemalla **Siirry muihin sovelluksiin** -painike sivun vasemmassa yläkulmassa, kun olet kirjautunut [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:ään, ja valitse sitten **Hallinta**.  

    Sinua saatetaan pyytää antamaan salasanasi uudelleen.  

2. Valitse **hallintakeskuksessa** **Ryhmät**.  

3. Valitse **Ryhmät**-sivulla **Oppimispolun laatijat** -käyttöoikeusryhmä.  

4. Lisää jäseniä ryhmään valitsemalla **Jäsenet**-rivillä **Muokkaa**.  

5. Valitse **+ Lisää jäseniä** ja määritä tai etsi ryhmään lisättävät käyttäjät.  

6. Kun olet lisännyt käyttäjät, valitse **Tallenna**.  

> [!NOTE]
>  Ryhmän voi määrittää käyttäjätillin myös valitsemalla ensin **Käyttäjät** > **Aktiiviset käyttäjät**, sitten lisättävät käyttäjät ja valita lopuksi ryhmät, johon käyttäjä lisätään, valitsemalla **Muokkaa** **Ryhmien jäsenyydet** -kohdan vieressä.  

<a name="MultipleOrgs"></a>   
## <a name="how-does-learning-path-work-with-multiple-organizations"></a>Miten oppimispolku toimii useiden organisaatioiden kanssa?  
 Kun julkaiset oppimispolkusisältöä, voit hallita julkaisuympäristöjen avulla, mihin vuokraajaan liittyviin organisaatioihin sisältösi julkaistaan. Voit julkaista eri sisältöä eri organisaatioissa luomalla useita julkaisuympäristöjä ja lisäämällä kunkin organisaation niistä vähintään yhteen.  

<a name="SecurityRoles"></a>   
## <a name="learning-path-and-dynamics-365-for-customer-engagement-apps-security-roles"></a>Oppimispolku ja Dynamics 365 for Customer Engagement -sovellusten käyttöoikeusroolit  
 [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] määrittää käyttöoikeusroolien avulla, mikä oppimispolkusisältö näytetään, kun käyttäjä valitsee Ohje-painikkeen, siirtyy sivulle tai suorittaa määritetyn toiminnon [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:ssä.  

 Oppimispolussa käytettävät roolit ovat samat kuin [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] -organisaatiossasi käytettävät käyttöoikeuksiin ja tietojen käyttöön liittyvät roolit, mutta voit luoda oppimispolkusisältöä kaikille joko kaikille [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] -käyttöoikeusrooleille tai vain osalle niistä.  Yleensä oppimispolun suunnitteluohjelman käyttöoikeusroolien halutaan vastaavan oman [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] -esiintymän käyttöoikeusrooleja. Kuitenkin voit yksinkertaistaa suunnitteluohjelman käyttöliittymää piilottamalla joitakin [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-käyttöoikeusrooleja. Jos päätät myöhemmin, että haluat käyttää oppimispolusta poistamaasi käyttöoikeusroolia , voit synkronoida roolit oppimispolun ja [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:n välillä.  

 Jos organisaatiossasi on useita liiketoimintayksiköitä, käyttöoikeusrooleilla voi olla ylä-ja alatason yhteyksiä. Vain päätason liiketoimintayksikön käyttöoikeusroolit synkronoidaan.  

 Lisätietoja käyttöoikeusrooleista: [Käyttöoikeusroolit ja oikeudet](/dynamics365/customer-engagement/admin/security-roles-privileges)  

<a name="Precedence"></a>   
### <a name="learning-path-role-precedence"></a>Oppimispolun roolien ensisijaisuus  
 Jos organisaatiosi käyttäjälle on määritetty useita käyttöoikeusrooleja, ensisijaisuuden avulla määritetään, minkä määritetyn käyttöoikeusroolin avulla oppipolkusisältö näytetään. Jos oppipolkusisältö on liitetty käyttöoikeusrooliin, kuka tahansa käyttäjä, jolla on kyseinen rooli, näkee tämän oppimispolkusisällön, vaikka heille on määritetty sellainen korkeamman ensisijaisuuden käyttöoikeusrooli, jota ei ole liitetty oppimispolkusisältöön.  

 Kullakin oppipolun roolilla on numeerinen arvo. Luettelon ensimmäisellä roolilla on korkein ensisijaisuus ja sitä seuraavilla rooleilla on alempi ensisijaisuus. Kun käyttäjälle määritetään rooli, joka käynnistää oppipolkusisällön näyttämisen, käyttäjä näkee sisällön myös silloin, kun käyttäjälle on määritetty rooli, jonka ensisijaisuus on alhaisempi kuin sisältöön liittyvän roolin. Jos esimerkiksi käyttäjälle on määritetty rooli, jonka ensisijaisuus on 1, ja rooli, jonka ensisijaisuus on 20, käyttäjä näkee sen oppipolkusisällön, joka on määritetty ensisijaisuuden 1 roolille.  

 Jos luot eri sisältöä eri rooleille samalle [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-sivulle tai -näytölle, käyttäjät näkevät korkeamman ensisijaisuuden rooliin liittyvän sisällön.  

<a name="ManageRoles"></a>   
### <a name="manage-security-roles-and-precedence"></a>Hallitse käyttöoikeusrooleja ja tärkeysjärjestystä  
 Voit hallita, mitkä käyttöoikeusroolit ovat käytettävissä oppipolun suunnitteluohjelmassa, ja määrittää roolien ensisijaisuusjärjestyksen, kun oppimispolku suoritetaan. Jos käyttäjällä on kaksi roolia, ja näille rooleille jossakin tilanteessa on julkaistu eri sisältö, käyttäjä näkee sisällön roolille, joka on luettelossa ylempänä.  

<a name="ConfigureRoles"></a>   
#### <a name="configure-security-roles"></a>Määritä käyttöoikeusroolit  

1. Kirjaudu [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:een tilillä, jolla on oppimispolun muokkausoikeudet.  

2. Avaa **sisältökirjasto**.  

3. Valitse näytön yläreunassa **Määritys**.  

4. Voit synkronoida käyttöoikeusroolit [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:n käyttöoikeusroolien kanssa valitsemalla **Synkronoi roolit**.  

5. Määritä oppimispolun kanssa käytettyjen roolien ensisijaisuus siirtämällä roolia ylä- tai alanuolella ylemmäs tai alemmas luettelossa.  

    Ensisijaisuus määritetään tämän sivun rooliluettelon järjestyksen perusteella.  

6. Jos haluat, että roolia ei käytetä oppimispolun kanssa, poista se valitsemalla roolin vieressä **Poista**.  

   > [!NOTE]
   >  Tämä ei poista roolia [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:stä. Se poistaa roolin oppimispolun suunnitteluohjelmasta, joka määrittää, miten sisältö näkyy käyttäjille. Voit palauttaa piilotetun roolin valitsemalla **Synkronoi roolit**.  

7. Kun muutokset ovat valmiit, valitse **Tallenna**.  

8. Palaa sisältökirjastoon valitsemalla **Takaisin**.  

<a name="MobileApp"></a>   
## <a name="create-learning-path-controls-for-includepn_dyn_365_tabletsincludespn-dyn-365-tabletsmd"></a>Oppimispolun ohjausobjektien luominen [!INCLUDE[pn_dyn_365_tablets](../../includes/pn-dyn-365-tablets.md)] -sovelluksille  
 Voit luoda [!INCLUDE[pn_dyn_365_tablets](../../includes/pn-dyn-365-tablets.md)] -sovelluksen oppimispolun ohjausobjekteja samalla tavalla kuin niitä luodaan verkkoasiakasohjelmalle. Tämä edellyttää mobiilisovelluksen simulaattorin käyttämistä verkkoselaimessa ja mobiilisovelluksen käyttöliittymän käyttämistä oppimispolun ohjausobjektien kiinnittämisessä. Simulaattoria käytetään vain tähän tarkoitukseen.  


### <a name="display-the-mobile-app-interface-simulator-in-a-web-browser"></a>Mobiilisovelluksen käyttöliittymäsimulaattorin näyttäminen verkkoselaimessa  

1. Kirjaudu [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)].  

2. Kopioi [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] -organisaation palvelimen nimi selaimessa näkyvästä URL-osoitteesta, joka voi olla esimerkiksi *<https://contososales.crm.dynamics.com/>*.  

    Varmista, että .com-kohdan lopussa on vinoviiva (/).  

3. Määritä sille organisaatiolle (eli esiintymälle) yksilöllinen nimi, jolle oppimispolun ohjausobjektit luodaan. Voit hakea yksilöllisen nimen valitsemalla sivustokartassa ensin **Asetukset** > **Mukautukset** ja valitsemalla sitten **Mukauttaminen**-sivulla **Kehittäjien resurssit**. Kopioi **Ilmentymän viite** -osan **Yksilöllinen nimi** -kentän arvo.  

   ![Dynamics organisaation nimi näkyy käyttäjän tiedot-ruudussa](media/lp-org-name.png "Dynamics organisaation nimi näkyy käyttäjän tiedot-ruudussa")  

4. Liitä seuraava organisaation URL-osoitteen ensimmäiseen osaan niin, että \<organisaation nimi> korvataan edellisessä vaiheessa määritetyllä organisaation yksilöllisellä nimellä:  

    nga/main.htm?org=*\<organisaation nimi>*  

    URL-osoite joka näytetään pitäisi olla seuraavan näköinen: https://contososales.crm.dynamics.com/nga/main.htm?org=orgb557e46a  

5. Liitä seuraava edellisen vaiheen URL-osoitteeseen niin, että \<palvelimen nimi> korvataan tämän toimintosarjan ensimmäisessä vaiheessa käytetyllä palvelimen nimellä:  

    &server=*\<palvelimen nimi>*  

    URL-osoite joka näytetään pitäisi olla seuraavan näköinen: https://contososales.crm.dynamics.com/nga/main.htm?org=orgb557e46a&server=https://contososales.crm.dynamics.com/.  

6. Avaa uusi välilehti tai selainikkuna ja kopioi luomasi URL-osoite kokonaan. Liitä se uuteen välilehteen tai selainikkunaan ja paina Enter-näppäintä.  

    Kun muodostat yhteyden mobiilisovelluksen käyttöliittymään ensimmäisen kerran, näkyviin tulee Tervetuloa-näyttö. Järjestelmä käsittelee samalla metatietoja ja noutaa mukautuksia. Kun tämä on tehty, työtila tulee näkyviin.  

   > [!NOTE]
   >  Kun muodostat yhteyden käyttöliittymän mobiilisovellusversioon, todentamisessa käytetään verkkoliittymän kirjautumistietoja. Verkkoliittymä on jätettävä auki, jotta mobiilisovelluksen käyttöliittymän avaamisen yhteydessä ei anneta käyttö estetty -virheilmoitusta.  

7. Sulje työtila, kun haluat nähdä selaimessa mobiilisovelluksen käyttöliittymän kotisivun. Tämän jälkeen voit avata sisältökirjaston ja luoda oppimispolun ohjausobjekteja tai muokata niitä. Lisätietoja: [Sisältökirjastossa](#ContentLibrary).  


<a name="ContentLibrary"></a>   
## <a name="content-library"></a>Sisältökirjasto  
 Sisältökirjasto näyttää kaiken sisällön, joka on luotu organisaatiolle ja on organisaation käytössä. Se näyttää myös ohjausobjektien luomisessa, hallinnassa ja käsittelemisessä vaadittavat komennot. Voit luoda ja muokata oppimispolun ohjausobjekteja muodostamalla ensin yhteyden sen asiakasohjelman käyttöliittymään, jolle haluat luoda ohjausobjekteja, ja avaamalla sitten sisältökirjaston.  

**Voit avata sisältökirjaston oletusverkkoliittymästä seuraavasti:**  

-   Napsauta sivupalkissa **Sisältökirjasto**-painiketta.  

     ![Oppimispolun sivupalkissa näkyvä sisältökirjastokuvake](media/lp-sidebar-cl-icon.png "Oppimispolun sivupalkissa näkyvä sisältökirjastokuvake")  

-   Valitse sivustokartassa **koulutus**-ruutu ja valitse sitten **Sisältökirjasto**.  

     ![Dynamics 365 for Customer Engagement -sivustokartan Sisältökirjasto-kuvake](media/lp-sitemap-content-library.png "Dynamics 365 for Customer Engagement -sivustokartan Sisältökirjasto-kuvake")  

**Voit avata sisältökirjaston mobiilisovelluksen käyttöliittymäsimulaattorissa seuraavasti:**  

1.  Valitse näytön oikeassa alakulmassa olevan ympyrän sisällä oleva kolme pistettä -painike (...).  

    ![Oppimispolun kuvakkeet näyttävä kolme pistettä -painike](media/lp-cl-ellipses.png "Oppimispolun kuvakkeet näyttävä kolme pistettä -painike")  

2.  Valitse **Oppimispolun sisältökirjasto**.  

    ![Mobiilisovelluksen käyttöliittymässä näkyvät Oppimispolkupainikkeet](media/lp-mobile-lp-button.png "Mobiilisovelluksen käyttöliittymässä näkyvät Oppimispolkupainikkeet")  



> [!NOTE]
>  Jos kaikki nämä sarakkeet eivät ole näkyvissä sisältökirjastossa, syynä voi olla se, että selaimen näkymän zoomaus on suurempi kuin 100 %. Jos haluat nähdä kaikki sarakkeet, määrittää zoomauksen asetus 100 prosenttiin tai pienemmäksi.  

 Sisältökirjasto sisältää sarakkeet, joka on kuvattu seuraavassa taulukossa:  

|Sarake|Kuvaus|  
|------------|-----------------|  
|**Nimi**|Nimi, jota käytit luodessasi ohjatun tehtävän tai sivupalkin. Punainen lukko nimen vieressä ilmaisee, että sisältö on tällä hetkellä kuitattu ulos. Osoittamalla kuvaketta näet käyttäjän, joka on kuitannut sisällön ulos.<br /><br /> ![Punainen kuvake ilmaisee, että sisältö kuitattu ulos.](media/lp-cl-checked-out.png "Punainen kuvake ilmaisee, että sisältö kuitattu ulos.")<br /><br /> Punainen tähti nimen vieressä osoittaa juuri sisään kuitatun sisällön.<br /><br /> ![Punainen tähti, joka osoittaa juuri valittua sisältöä](media/lp-cl-new-check-in.png "Punainen tähti, joka osoittaa juuri valittua sisältöä")|  
|**Otsikko**|Otsikko, jonka annoit lisätessäsi sisältöä ohjattuun tehtävään tai sivupalkkiin. Sivupalkkien ja ohjattujen tehtävien otsikot näytetään sivupalkeissa, kun ne on lisätty linkkeinä tai kun ne palautetaan hakutuloksina.|  
|**Tyyppi**|Sisällön lajin ilmaiseva symboli: sivupalkki tai ohjattu tehtävä|  
|**Muoto**|Symbolit, jotka ilmaisevat luonnin yhteydessä tälle sisällölle valitun muodon, joka voi olla **pöytäkone** tai **taulutietokone**.<br /><br /> **Muoto**-sarake ei ole näkyvissä sisältökirjaston käyttämisen yhteydessä, kun yhteys on muodostettu mobiilisovelluksen käyttöliittymäsimulaattoriin tai vuorovaikutteiseen palvelukeskukseen.|  
|**Tunnisteet**|Näyttää kaikki tähän sisältöön käytetyt tunnisteet. Voit lisätä tunnisteita **Lisäasetukset**-valintaikkunassa. Tunnisteiden avulla voit suodattaa kirjastossa näkyvää sisältöä.|  
|**Sovelluksen versio**|Sen sovelluksen versio, jolle ohjausobjekti luotiin.|  
|**Tekijä**|Ohjausobjektin luoneen henkilön nimi.|  
|**Kielivaihtoehdot**|Numeerinen arvo, joka osoittaa niiden kielten määrän, joille ohjausobjekti on lokalisoitu.<br /><br /> Tämä sarake|  
|**Tila**|Näyttää **Julkaistu** , jos sisältö on tällä hetkellä julkaistu; muutoin tilana on **Luonnos**.|  
|**Käytössä**|Näyttää, onko sisältö käytössä vai poissa käytöstä.  Vain käytössä oleva sisältö näkyy käyttäjille.|  
|**Edellinen julkaisu**|Viimeisin päivämäärä, jolloin sisältö on julkaistu.|  

<a name="ContentTypes"></a>   
## <a name="learning-path-content-types-guided-tasks-and-sidebars"></a>Oppimispolun sisältötyypit: ohjatut tehtävät ja sivupalkit  
 Voit luoda kahdenlaista sisältöä oppimispolussa: ohjattuja tehtäviä ja sivupalkkeja.  

<a name="GT"></a>   
### <a name="guided-tasks"></a>Ohjatut tehtävät  
 Ohjattu tehtävä on yleensä sarja vaiheita, tosin se voi olla myös vain yksi vaihe. Käyttäjä voi käynnistää ohjatun tehtävän valitsemalla linkin sivupalkissa, siirtymällä sivulle tai valitsemalla linkin sivulla, jolle olet luonut sisältöä. Käyttäjä valitsee jokaisessa vaiheessa **Seuraava** tai suorittaa määritetyn toiminnon loppuun, jonka jälkeen hän voi siirtyä seuraavaan vaiheeseen tai päättää ohjatun tehtävän suorittamisen.  

 Ohjatut tehtävät ovat hyödyllisiä ohjattaessa käyttäjiä yhteisten tai uusien tehtävien suorittamisessa. Niiden avulla voidaan myös varmistaa, että tehtävät suoritetaan yhdenmukaisesti organisaatiossa tai että tiedot on kirjoitettu tietyllä tavalla. Tämä tukee organisaatiosi prosesseja ja työnkulkuja. Voit sisällyttää linkkejä, videoita ja muita tietoja ohjattuihin tehtäviin, jotta käyttäjäsi oppisivat sovelluksen käytön tai vaiheen viittaaman käyttöliittymän osan paremmin.  

<a name="Sidebar"></a>   
### <a name="sidebars"></a>Sivupalkit  
 Sivupalkki tulee näkyviin, kun käyttäjä valitsee Ohje-painikkeen, siirtyy sivulle tai valitsee linkin tai painikkeen sivulla, jolle olet luonut sisältöä. Voit myös luoda Aloitus-sivupalkkeja, jotka näkyvät käyttäjän avatessa sivun tai näytön tai valitessa sivupalkin aloituskuvakkeen.  

 ![sivupalkin kotisivun kuvake](media/sidebar-home.png "sivupalkin kotisivun kuvake")  

 Voit myös määrittää Virhe-sivupalkkeja, jotka näkyvät, jos aiotun sivupalkin näyttämisessä on ongelmia. Voit sisällyttää linkkejä, videoita ja muita tietoja sivupalkkeihin, jotta käyttäjäsi oppisivat näytetyn sivun tai lomakkeen paremmin. Voit sisällyttää myös toimintoja, joita he voivat tehdä sivulla tai lomakkeessa.  

<a name="CreateGT"></a>   
## <a name="create-a-guided-task"></a>Luo ohjattu tehtävä  

 Ohjatun tehtävän luomisessa on kaksi vaihetta:  

1.  Määritä, miten tehtävä käynnistetään, ja määritä roolit, joita sisältö koskee.  

2.  Prosessieditorin avulla voit lisätä vaiheita, jotka käyttäjät näkevät, kun he siirtyvät eteenpäin ohjatussa tehtävässä.  

### <a name="define-the-triggers-and-roles"></a>Määritä käynnistimet ja roolit  

1. Siirry sivulle, jolle haluat luoda ohjatun tehtävän.  

2. Avaa sisältökirjasto. Katso [sisältökirjastosta](#ContentLibrary) tietoja siitä, miten se tehdään.  

3. Valitse sisältökirjastossa **Ohjattu tehtävä**.  

    ![linkki, jolla voi luoda uuden ohjatun tehtävän Oppimispolun sisältökirjastoon](media/lp-content-library-gt.png "linkki, jolla voi luoda uuden ohjatun tehtävän Oppimispolun sisältökirjastoon")  

4. Anna nimi ja valitse muut ohjatun tehtävän asetukset. Tätä taulukkoa käytetään viitteenä.  


   |              Asetus               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      Kuvaus                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |    **Poista tämä ohjattu tehtävä käytöstä**    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          Ota ohjattu tehtävä pois käytöstä valitsemalla tämä valintaruutu. Kun se on poistettu käytössä, sitä ei näytetä käyttäjille.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   | **Tee tästä ohjatun tehtävän virhe** |                                                                                                                                                                                                                                                                                                                                                                                                                       Valitse tämä valintaruutu, jos haluat näyttää tämän ohjatun tehtävän vain, kun muissa ohjatuissa tehtävissä on virhe esimerkiksi käyttöoikeuksien puuttumisen tai muun sivun ohjattujen tehtävien näyttämiseen liittyvän ongelman vuoksi.                                                                                                                                                                                                                                                                                                                                                                                                                       |
   |              **Nimi**              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        Ohjatun tehtävän nimi, joka näkyy sisältökirjastossa.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
   |             **Asiakas.**             |                                                                                                                                                                               Asiakasohjelman arvo määritetään automaattisesti ympäristöön, jossa luot sisältöä. **varoitus:**  Jos muokkaat aiemmin luotua ohjausobjektia silloin, kun olet muodostanut yhteyden muuhun kuin ohjausobjektin luomisessa käytettyyn käyttöliittymään, asiakasohjelman asetus päivitetään nykyiseksi asiakasohjelmatyypiksi. Tällöin ohjausobjekti asetetaan tauolle eikä se toimi siinä asiakasohjelmassa, jolle ohjausobjekti alun perin luotiin. <br /><br /> Jos olet luomassa ohjausobjekteja verkkoliittymälle, näkyvissä on **WWW-asiakasohjelma**-kohta.<br /><br /> Jos olet muodostanut yhteyden mobiilisovelluksen käyttöliittymäsimulaattoriin, näkyvissä on **Mobiilisovellukset**-kohta.<br /><br /> Jos olet muodostanut yhteyden vuorovaikutteiseen palvelukeskukseen, näkyvissä on **Vuorovaikutteinen palvelukeskus**-kohta.                                                                                                                                                                               |
   |          **Muoto**           |                                                                                                                                                                       Näytettävä muoto riippuu siitä, mille käyttöliittymälle sisältöä luodaan. Jos käytössä on WWW-asiakasohjelman käyttöliittymä, näkyvissä ovat **Pöytäkone**- ja **Taulutietokone**-kohdat. Kun **Taulutietokone** valitaan WWW-asiakasohjelmalle, se viittaa selaimiin, joita käytetään taulutietokoneissa, ei mobiilisovelluksissa.<br /><br /> Jos olet luomassa ohjausobjekteja mobiilisovelluksen käyttöliittymälle, näkyvissä on **Taulutietokone**-kohta. Tämä viittaa laitteisiin, joissa on käytössä [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:n mobiilisovellus. Tuki koskee kuitenkin vain tabletteja.<br /><br /> Jos käytössä on vuorovaikutteinen palvelukeskus, näkyvissä on **Pöytäkone**-kohta. **Tärkeää:** [!INCLUDE[pn_crm_shortest](../../includes/pn-dyn-365-phones.md)] ei tue oppimispolkua..                                                                                                                                                                        |
   |     **Ohjattu tehtävä avautuu, kun**     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              Valitse, haluatko ohjatun tehtävän tulevan näkyviin, kun **sivu latautuu** vai kun sivupalkin **linkkiä napsautetaan**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
   |        **Elinkaaren vaihe**         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        Tämä asetus on tarkoitettu vain sisäiseen käyttöön.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
   |   **Dynamics 365 for Customer Engagement -sovellusten käyttöoikeusrooli**   |                                                                                                                                                                                                                                                                                                                                                                                                  Valitse käyttöoikeusroolit, joille haluat näyttää ohjatun tehtävän. Voit valita niin monta roolia kuin haluat. Jos käyttäjälle on määritetty useita rooleja, ohjattu tehtävä näytetään vain roolille, jolla on korkein ensisijaisuus, kuten kuvattiin aiemmin tässä ohjeaiheessa.                                                                                                                                                                                                                                                                                                                                                                                                   |
   |             **Tila**             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                Näyttää ohjatun tehtävän tilan. Tila on **Luonnos** ennen kuin julkaiset sen.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
   |        **Lisäasetukset**        | Tämä vaihtoehto on käytettävissä, kun olet tallentanut ohjatun tehtävän. Seuraavat asetukset ovat käytettävissä **lisäasetuksissa**:<ul><li>**Tee tästä ohjatun tehtävän virhe**: valitse tämä valintaruutu, jos haluat näyttää tämän ohjatun tehtävän vain, kun muissa ohjatuissa tehtävissä on virheitä.</li><li>**Tuetut kielet**: valitse kielet tälle ohjatulle tehtävälle sekä tuonnille ja viennille.</li><li>**Tekijä**: muuta tälle ohjatulle tehtävälle määritettyä tekijää.</li><li>**Tunnisteet**: lisää tai poista tähän ohjattuun tehtävään käytettyjä tunnisteita. Tunnisteiden avulla voit helpommin etsiä sisältöä sisältökirjastosta tai luokitella sisältöä.</li></ul><br />Voit määrittää myös seuraavat asetukset kohdassa **Julkaisun tiedot**:<ul><li>**Sovellusversio**: määritä sisältöön liitetty [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:n versio.</li><li>**Versio**: määritä luomasi sisällön versionumero.</li><li>**Sisällöntuottamisryhmä**: määritä luomallesi sisällölle sisällöntuottamisryhmä.</li><li>**Julkaisuryhmät**: valitse tämän sisällön julkaisuryhmät.</li></ul> |


5. Kun olet valmis, aloita prosessieditorin käyttö valitsemalla **Tallenna**.  

### <a name="add-steps-with-the-flow-editor"></a>Lisää vaihe prosessieditorin avulla  

1. Lisää otsikko kohtaan, jossa *ohjatun tehtävän otsikko* näkyy. Tämä on nimi, jonka käyttäjät näkevät.  

2. Valitse, näytetäänkö vain ohjausobjektit, joilla on kiinteä tunnus. Rekisteröidyt ohjausobjektit näytetään vihreinä ja rekisteröimättömät objektit sinisinä, kun kiinnität ruudun käyttöliittymään vetämällä. Jos kiinnität vaiheen ohjausobjektiin, jolla ei ole kiinteää tunnusta, [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:n tuleva päivitys voi vaikuttaa siihen. Päivitykset eivät vaikuta ohjausobjekteihin, joilla on kiinteät tunnukset.  

3. Valitse ensin **Lisää uusi vaihe** ja sitten vaihetyyppi, jota haluat käyttää ohjatun tehtävän ensimmäisessä vaiheessa.  

   |Painikkeen tyyppi|Kuvaus|  
   |-----------------|-----------------|  
   |**Osavaihe, jossa on Seuraava-painike**|Tässä vaiheessa on Seuraava-painike, jonka avulla voidaan siirtyä työnkulun seuraavaan vaiheeseen. Jos tämä on työnkulun viimeinen vaihe, Seuraava-painike ei näy. Vedä ruutua ja kiinnitä vaihe sopivaan kohtaan sovelluksessa.|  
   |**Osavaihe, jossa on käyttäjän toimi**|Tässä vaiheessa ei ole Seuraava-painiketta. Käyttäjää pyydetään valitsemaan käyttöliittymän osa, johon vaihe on kiinnitetty. Jos tämän valinnan seurauksena on sivun uudelleenohjaus tai käyttöliittymän tilan muutos, varmista, että seuraava vaihe kiinnitetään muuttuneeseen käyttöliittymän tilaan. Vedä ruutua ja kiinnitä vaihe sopivaan kohtaan sovelluksessa.<br /><br /> Kiinnitä tämän tyyppinen vaihe käyttöliittymän valittavaan ohjausobjektiin, kuten painikkeeseen tai linkkiin.|  
   |**Käyttäjän toimi Seuraava-painiketta napsautettaessa**|Tällä vaiheella on Seuraava-painike. Seuraava-painikkeen valitsemisella on sama vaikutus kuin sen käyttöliittymän osan valitsemisella, johon vaihe on kiinnitetty. Jos tämän valinnan seurauksena on sivun uudelleenohjaus tai käyttöliittymän tilan muutos, varmista, että seuraava vaihe kiinnitetään muuttuneeseen käyttöliittymän tilaan. Vedä ruutua ja kiinnitä vaihe sopivaan kohtaan sovelluksessa.|  
   |**Oppimisvaihe**|Tässä vaiheessa on mukautettava painike lopetustoimintona. Tämä vaihe voi olla vain ohjatun tehtävänkulun lopussa. Sen voi linkittää oppimispolun sivupalkkiin. Vedä ruutua ja kiinnitä vaihe sopivaan kohtaan sovelluksessa.|  

   > [!NOTE]
   >  Jos olet jo suunnitellut ulos ohjatun tehtävän ja tiedät, mitkä vaiheet haluat lisätä, voit lisätä ne kaikki nyt. Kaikki lisäämäsi vaiheet näkyvät prosessieditorissa lisäysjärjestyksessä. Voit muuttaa vaiheiden järjestystä lisäämisen jälkeen vetämällä niitä luettelossa ylös ja alas.  

4. Valitse lisättävän vaiheen tyyppi. Vedä sitten ruutu käyttöliittymään ja kiinnitä se ohjausobjektiin. Sinun pitää ehkä yrittää muutaman kerran, ennen kuin opit, miten saat vaiheen haluamaasi paikkaan.  

   > [!NOTE]
   >  Ruutua voi pitää kiinni enintään 15 sekuntia. Jos et kiinnitä sitä 15 sekunnin kuluessa, ruutu säilyy kiinnittämättömänä ja hiiren osoitin muuttuu takaisin normaaliksi osoittimeksi.  

   ![Ohjatun tehtävän työnkulun muokkausohjelma](media/lp-gt-flow-editor.png "Ohjatun tehtävän työnkulun muokkausohjelma")  

5. Kun olet sijoittanut vaiheen haluamaasi paikkaan, vapauta hiiripainike kiinnittääksesi kuplan ohjausobjektiin. Vaihe näkyy valitsemassasi sijainnissa. Jos haluat siirtää vaiheen, käytä **Vedä minua** -painiketta vaiheen vieressä olevassa paneelissa.  

   ![ohjatun tehtävän kuplan Vedä minut -kuvake](media/lp-gt-bubble-drag-me.png "ohjatun tehtävän kuplan Vedä minut -kuvake")  

6. Lisää sisältöä vaiheeseen käyttäen sen vieressä näkyviä työkaluja. Käytettävissä on seuraavat toiminnot:  

   - **Sisältötyyppi**: Lisää vaiheeseen tekstiä tai video. Valitse **Muokkaa**, jos haluat nähdä lisää asetuksia. Voit vaihtaa fontin kokoa, väriä ja tyyliä sekä lisätä videon pikkukuvan.  

   - **Sijoittelu**: Määritä vaiheen sijainti ohjausobjektissa, johon se on kiinnitetty. Vaihtoehdot: Automaattinen sijainti (oletusvalinta), Vasen yläreuna, Oikea yläreuna, Vasen alareuna, Oikea alareuna, Vasen yläreuna, Oikea yläreuna, Vasen alareuna, Oikea alareuna  

   - **Kopioi**: Luo vaiheesta sisällöltään vastaavan kopion, joka kiinnitetään samaan sijaintiin. Se lisätään ohjatun tehtävän kulkuun suoraan alkuperäisen vaiheen perään.  

7. Valitse **Tallenna**, kun olet sijoittanut vaiheen ja lisännyt siihen haluamasi sisällön. Voit sulkea vaiheen sen oikeassa yläkulmassa olevalla Sulje-painikkeella tai palata prosessieditoriin valitsemalla nuolen vasemmassa yläkulmassa.  

   > [!NOTE]
   >  Voit aina muokata vaihetta myöhemmin, joten älä huolestu, jos vahingossa suljet sen ennen kuin se on valmis.  

8. Voit lisätä ohjatun tehtävän seuraavaan vaiheeseen tai muokata sitä valitsemalla oikean nuolen ![Prosessieditorin palauttava nuolenkärkikuvake](media/lp-chevron.png "Prosessieditorin palauttava nuolenkärkikuvake") näytön vasemmassa yläkulmassa. Tämä nuoli avaa prosessieditorin.  

9. Lisää kaikki muut haluamasi vaiheet ohjattuun tehtävään varmistaen, että tallennat kunkin vaiheen sisällön lisäämisen jälkeen.  

    > [!NOTE]
    >  Jos siirrät vaiheen tai kopioit sen työkalurivin **Kopioi**-painikkeen avulla, vaiheen tallentamattomat muutokset menetetään. Muista tallentaa tekemäsi muutokset usein.  

10. Kun olet lisännyt kaikki vaiheet ohjattuun tehtävään, valitse **Tallenna**.  

11. Valitse **Esikatselu**, jos haluat testata ohjatun tehtävän ja nähdä, miten käyttäjät näkevät sen.  

    > [!NOTE]
    >  Ohjattu tehtävä on esikatseltava ennen julkaisua. Kun suljet vaiheen tai käytät esikatselutilan vasemman yläkulman nuolta, oppimispolun suunnitteluohjelman **Kuittaa sisään**- ja **Julkaise**-painikkeet ovat näkyvissä.  

12. Jos olet tyytyväinen muutoksiin, kuittaa ne sisään ja julkaise ohjattu tehtävä, tai julkaise sen myöhemmin sisältökirjastosta.  

<a name="CreateSidebar"></a>   
## <a name="create-a-sidebar"></a>Luo sivupalkki  

 Sivupalkin luomisessa on kaksi vaihetta:  

1.  Määritä sivupalkin ominaisuudet ja määritä roolit, joita se koskee.  

2.  Lisää sisältöä (tekstiä, kuvia, linkkejä ja painikkeita) sivupalkkiin.  

### <a name="set-the-sidebar-properties-and-roles"></a>Määritä sivupalkin ominaisuudet ja roolit  

1. Siirry sivulle, jolle haluat luoda sivupalkin.  

2. Avaa sisältökirjasto. Katso [sisältökirjastosta](#ContentLibrary) tietoja siitä, miten se tehdään.  

3. Valitse sisältökirjastossa **Sivupalkki**.  

   ![linkki, jolla voi luoda uuden sivupalkin Oppimispolun sisältökirjastoon](media/lp-content-library-sb.png "linkki, jolla voi luoda uuden sivupalkin Oppimispolun sisältökirjastoon")  

4. Anna nimi ja valitse muut sivupalkin asetukset. Tätä taulukkoa käytetään viitteenä.  


   |             Asetus             |                                                                                                                                                                                                                                                                                                                                                        Kuvaus                                                                                                                                                                                                                                                                                                                                                        |
   |---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |           **Poista käytöstä**           |                                                                                                                                                                                                                                                                                                                                       Ota sivupalkki pois käytöstä valitsemalla tämä valintaruutu.                                                                                                                                                                                                                                                                                                                                       |
   | **Tee tästä sivupalkkivirhe**  |                                                                                                                                                                                                                                         Valitse tämä valintaruutu, jos haluat näyttää tämän sivupalkin vain, kun muissa sivupalkeissa on virhe esimerkiksi käyttöoikeuksien puuttumisen tai muun sivun sivupalkkien näyttämiseen liittyvän ongelman vuoksi.                                                                                                                                                                                                                                          |
   |   **Tee tästä aloitussivupalkki**    |                                                                                                                                                                                                                                                                         Aloitussivupalkki näytetään, kun käyttäjä valitsee Aloitus-painikkeen tai jos sivulla ei ole sivupalkkia ja käyttäjä valitsee Ohje-painikkeen. Kullakin sivulla voi olla vain yksi aloitussivupalkki.                                                                                                                                                                                                                                                                         |
   |            **Nimi**             |                                                                                                                                                                                                                                                                                                                                    Nimi, joka näkyy sisältökirjastossa.                                                                                                                                                                                                                                                                                                                                     |
   |           **Asiakas.**            | Asiakasohjelman arvo määritetään automaattisesti ympäristöön, jossa luot sisältöä. **varoitus:**  Jos muokkaat aiemmin luotua ohjausobjektia silloin, kun olet muodostanut yhteyden muuhun kuin ohjausobjektin luomisessa käytettyyn käyttöliittymään, asiakasohjelman asetus päivitetään nykyiseksi asiakasohjelmatyypiksi. Tällöin ohjausobjekti asetetaan tauolle eikä se toimi siinä asiakasohjelmassa, jolle ohjausobjekti alun perin luotiin. <br /><br /> Jos olet luomassa ohjausobjekteja verkkoliittymälle, näkyvissä on **WWW-asiakasohjelma**-kohta.<br /><br /> Jos olet muodostanut yhteyden mobiilisovelluksen käyttöliittymäsimulaattoriin, näkyvissä on **Mobiilisovellukset**-kohta.<br /><br /> Jos olet muodostanut yhteyden vuorovaikutteiseen palvelukeskukseen, näkyvissä on **Vuorovaikutteinen palvelukeskus**-kohta. |
   |         **Muoto**         |                                                  Näytettävä muoto riippuu siitä, mille käyttöliittymälle sisältöä luodaan. Jos käytössä on WWW-asiakasohjelman käyttöliittymä, näkyvissä ovat **Pöytäkone**- ja **Taulutietokone**-kohdat. Kun **Taulutietokone** valitaan WWW-asiakasohjelmalle, se viittaa selaimiin, joita käytetään taulutietokoneissa, ei mobiilisovelluksissa.<br /><br /> Jos olet luomassa ohjausobjekteja mobiilisovelluksen käyttöliittymälle, näkyvissä on **Taulutietokone**-kohta. Tämä viittaa laitteisiin, joissa on käytössä [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:n mobiilisovellus. Tuki koskee kuitenkin vain tabletteja.<br /><br /> Jos käytössä on vuorovaikutteinen palvelukeskus, näkyvissä on **Pöytäkone**-kohta.                                                  |
   |     **Sivupalkki avautuu, kun**      |                                                                                                                                                                                                                                                                                               Valitse, haluatko sivupalkin avautuvan, kun sivu latautuu vai kun käyttäjä valitsee sivulla linkin tai painikkeen.                                                                                                                                                                                                                                                                                               |
   |       **Elinkaaren vaihe**       |                                                                                                                                                                                                                                                                                                                                              Tämä on tarkoitettu vain sisäiseen käyttöön.                                                                                                                                                                                                                                                                                                                                               |
   | **Dynamics 365 for Customer Engagement -sovellusten käyttöoikeusrooli** |                                                                                                                                                                                                                  Valitse rooli tai roolit, joille haluat näyttää sivupalkin. Voit valita niin monta roolia kuin haluat. Jos käyttäjälle on määritetty useita rooleja, sivupalkki näytetään vain roolille, jolla on korkein ensisijaisuus, kuten kuvattiin aiemmin tässä ohjeaiheessa.                                                                                                                                                                                                                   |
   |          **Malli**           |                                                                                                                                                                                                                                                                                       Valitse uudessa sivupalkissa käytettävä malli: **Yksi sarake** tai **Kaksi saraketta**. Oletusmalli on yhden sarakkeen sivupalkki.                                                                                                                                                                                                                                                                                        |
   |           **Tila**            |                                                                                                                                                                                                                                                                                                              Näyttää sivupalkin tilan. Tila on **Luonnos** ennen kuin julkaiset sivupalkin.                                                                                                                                                                                                                                                                                                              |
   |      **Lisäasetukset**       |                                                                         Tämä vaihtoehto ei ole käytettävissä, ennen kuin tallennat sivupalkin. Seuraavat asetukset ovat käytettävissä **lisäasetuksissa**:<ul><li>**Poista sivupalkin ylätunniste käytöstä**</li><li>**Poista sivupalkin otsikko käytöstä**</li><li>**Poista sivupalkin alatunniste käytöstä**</li><li>**Tekijä**: muuta tälle sivupalkille määritettyä tekijää.</li><li>**Tunnisteet**: lisää tai poista tähän sivupalkkiin käytettyjä tunnisteita. Tunnisteiden avulla voit helpommin etsiä sisältöä sisältökirjastosta tai luokitella sisältöä.</li><li>**Tuetut kielet**: valitse kielet tälle sivupalkille sekä tuonnille ja viennille.</li></ul>                                                                         |


5. Kun olet valmis, aloita sisällön lisääminen sivupalkkiin valitsemalla suunnitteluohjelmassa **Tallenna**.  

<a name="SidebarContent"></a>   

### <a name="add-content-to-your-sidebar"></a>Lisää sisältöä sivupalkkiin  

1.  Kun olet tallentanut sisältökirjastoon sivupalkin nimen ja ominaisuudet, suunnitteluohjelma avautuu.  

2.  Anna sivupalkin otsikko.  

3.  Lisää sisältöä, jonka haluat näyttää käyttäjille kun sivupalkki näytetään.  

4.  Voit lisätä uuden osan valitsemalla **Lisää osa**.  

5.  Voit poistaa mallin osan valitsemalla ensin poistettavan osan ja sitten **Poista**.  

6.  Kun et enää halua muokata sivupalkin sisältöä, tallenna muutokset valitsemalla **Tallenna**ja sulje sivupalkki valitsemalla **Sulje** oikeassa yläkulmassa, jonka jälkeen palaat sisältökirjastoon.  

7.  Valitse sivun yläreunassa ensin **Hallinta** ja sitten **Kuittaa sisään**. Muutokset tallennetaan, ja ne ovat nyt muiden sisältöä luovien käyttäjien käytettävissä.  

### <a name="add-links-to-your-sidebar"></a>Lisää linkkejä sivupalkkiin  
 Sivupalkin luomisen yhteydessä siihen voi lisätä linkkejä useilla eri tavoilla. Voit luoda linkin toiseen ohjattuun oppimispolun tehtävään tai sivupalkkiin, toiseen [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:n sivuun tai verkkosivuun. Voit jopa hakea linkitettäviä ohje- ja koulutusaiheita sivupalkin luomisen aikana. Kun sivupalkin ominaisuudet ja roolit on määritetty ja se on valmis sisällön lisäämistä varten, voit lisätä luomasi sivupalkin osaan linkkejä seuraavien vaiheiden avulla.  

1. Valitse **Linkkiluettelo**-kuvake siinä osassa, johon haluat lisätä linkkejä.  

   ![Oppimispolun polun sivupalkissa valittu linkkiluettelot-kuvake](media/lp-sidebar-links.png "Oppimispolun polun sivupalkissa valittu linkkiluettelot-kuvake")  

2. Lisää osan otsikko ja valitse **+ Lisää linkki**.  

   ![Lisää linkki-ruutu korostettuna Oppimispolun sivupalkin osassa](media/lp-sidebar-addlink.png "Lisää linkki-ruutu korostettuna Oppimispolun sivupalkin osassa")  

3. Valitse ensin lisättävän linkin tyyppi ja sitten **Seuraava**. Voit valita seuraavista vaihtoehdoista:  

   - **Ohjattu tehtävä**: Luo linkin aiemmin luotuun oppimispolun ohjattuun tehtävään. Tästä voi olla hyötyä annettaessa sivupalkin tehtävää koskevia tietoja ja linkitettäessä sen jälkeen ohjattu tehtävä, joka ohjaa käyttäjän [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-käyttöliittymän tehtävän läpi.  

   - **Sivupalkki**: Luo linkin aiemmin luodun oppimispolun sivupalkkiin. Voit linkittää sivupalkkiin  

   - **Sivu sovelluksessa**  

   - **Verkkosivu**  

<a name="Videos"></a>   
## <a name="use-videos-in-your-learning-path-controls"></a>Käytä videoita oppimispolun ohjausobjekteissa  
 Oppimispolun ohjausobjektit tukevat vain YouTube-videoita. Jos aiot käyttää videoita oppimispolun ohjausobjekteissa, sinulla on oltava YouTube-tili ja -kanava, johon videot ladataan. Videoita ei voi linkittää yksityiseksi määritetylle kanavalle, mutta niitä voi linkittää kanavalle, joka on määritetty julkiseksi tai piilotetuksi. Voit määrittää kanavan myös niin, että useat henkilöt voivat ylläpitää organisaation videosisältöä.  

 Voit halutessasi lisätä videot ohjausobjekteihin upottamalla ne. Jos haluat, että käyttäjät näkevät videot uudessa välilehdessä tai selainikkunassa, voit lisätä sivupalkkiin tekstiosan ja lisätä siihen linkin videoon.  

 Kun upotat videoita, jotka näkyvät sivupalkissa tai ohjatussa tehtävässä, käytä YouTuben määrittämää linkkiä. Oppimispolku päivittää linkin automaattisesti sekä upottaa ja muuttaa videon koon sivupalkkiin tai ohjatun tehtävän ruutuun sopivaksi. Käyttäjä voi valita **Koko näyttö** -vaihtoehdon, jos hän haluaa katsoa videon koko näytön tilassa. Jos käyttäjä pysäyttää toiston tai kun toisto päättyy, YouTube voi näyttää automaattisesti linkkejä muihin käyttäjää mahdollisesti kiinnostaviin videoihin. Voit estää tämän muokkaamalla ohjausobjektin linkkiä niin, että sen lopussa on **?rel=0**.  

 Esimerkissä olet luonut ja videon ja ladannut sen kanavallesi. Tämän jälkeen kopioit YouTuben videolle määrittämän URL-osoitteen, joka on **https://youtu.be/4TrYMB4pjyw**. Voit upottaa tämän videon ohjausobjektiin syöttämällä kyseisen URL-osoitteen ohjausobjektin **Kirjoita videon URL-osoite** -kenttään.  

 Kun tallennat ohjausobjektin, oppimispolku muuttaa URL-osoitteen osoitteeksi **https://www.youtube.com/embed/4TrYMB4pjyw**. Voit poistaa tauon aikana tai toiston päättymisen jälkeen tapahtuvan muiden videoiden linkkien näyttämisen käytöstä muokkaamalla URL-osoitetta niin, että osoitteen loppuun liitetään **?rel=0**. Tällöin URL-osoite on seuraavanlainen: **https://www.youtube.com/embed/4TrYMB4pjyw?rel=0**.  

Lisätietoja YouTuben käyttämisestä: [YouTuben ohjekeskus](https://go.microsoft.com/fwlink/?linkid=847120)  

<a name="PublishLP"></a>   
## <a name="publish-learning-path-content"></a>Oppimispolun sisällön julkaisu  
 Käyttäjät näkevät luomasi oppimispolkusisällön vasta julkaisemisen jälkeen. Voidaan julkaista vain sellainen sisältö, joka on kuitattu sisään.  

1.  Avaa sisältökirjasto.  

2.  Valitse valintaruutu niiden ohjattujen tehtävien ja sivupalkkien vierestä, jotka haluat julkaista. Varmista, että julkaistava ohjausobjekti on kuitattu sisään.  

3.  Valitse ensin sivun yläreunassa **Julkaise** ja sitten **Julkaise**.  

4.  Valitse **Julkaise ohjausobjektit** -sivulla ne julkaisuympäristöt, joihin haluat julkaista sisältöä. Valitse sitten **Julkaise**.  

<a name="PublishingGroup"></a>   
### <a name="about-publishing-groups"></a>Tietoja julkaisuryhmistä  
 Oppimispolkusisältö julkaistaan julkaisuryhmään. Kun otat oppimispolun käyttöön organisaatiossa, luotavalla julkaisuryhmällä on sama nimi kuin organisaatiolla. Voit tarvittaessa luoda muita julkaisuryhmiä. Voit lisätä useita organisaatioita julkaisuryhmään ja organisaatio voi olla jäsen useissa julkaisuryhmissä, jotta voit mukauttaa sisältöä ja julkaista sen helposti eri organisaatioissa.  

<a name="CreatePG"></a>   
### <a name="create-a-publishing-group"></a>Luo julkaisuryhmä  

1.  Avaa sisältökirjasto.  

2.  Valitse näytön yläreunassa **Määritys**.  

3.  Valitse **Julkaisun määritykset**.  

4.  Valitse **Julkaisun määritykset** -sivulla **Uusi julkaisuympäristö**.  

5.  Kirjoita nimi ja valinnainen kuvaus.  

6.  Valitse organisaatiot, jotka haluat sisällyttää julkaisuryhmään. Näet vain organisaatiot, joihin sinulla on käyttöoikeudet.  

7.  Valitse ensin **Tallenna** ja sitten **OK**.  

<a name="ExportandImport"></a>   
## <a name="export-and-import-learning-path-content"></a>Vie ja tuo oppimispolun sisältöä  
 Voit viedä luomaasi sisältöä, jos esimerkiksi haluat jakaa sen toisen organisaation tekijän kanssa tai jos haluat tehdä varmuuskopioita. Vientitoiminto luo pakatun .zip-tiedoston, joka sisältää oppimispolkusisällön .json-tiedostot. .zip-tiedostossa on yksi kansio jokaista valittua oppimispolun sivupalkkia ja ohjattua tehtävää varten.  

<a name="ExportProc"></a>   
### <a name="export-your-learning-path-content"></a>Vie oppimispolun sisältöä  

1.  Valitse sisältökirjastossa valintaruutu vietävän sisällön vieressä.  

     Voit viedä sisältöä kuittaamatta sitä sisään.  

2.  Valitse ensin sivun yläreunassa **Hallinta** ja sitten **Vie**.  

3.  Valitse luotua .zip-tiedoston tallentamisen tapa ja sitten tiedoston nimi ja sijainti.  

    > [!NOTE]
    >  .zip-tiedoston oletusnimi on vientitoiminnossa aina sama, joten kannattaa käyttää yksilöllistä nimeä, jotta aiemmin viedyt tiedostot eivät korvaudu.  

### <a name="import-your-learning-path-content"></a>Tuo oppimispolun sisältöä  

1.  Valitse sisältökirjastossa ensin **Hallinta** ja sitten **Tuo**.  

2.  Valitse tuotava aiemmin viety tiedosto **Selaa**-painikkeella tai vedä tiedosto valintaikkunan **Vedä ohjausobjektit tähän** -valintaikkunaan.  

    > [!CAUTION]
    >  Kun tuot ohjausobjektin, se korvaa kirjastossa jo olevan saman ohjausobjektin muut versiot, vaikka kyseinen ohjausobjekti olisi uudempi.  

3.  Vahvista, että näkyvä tiedostonimi vastaa tuotavaa tiedostoa, ja valitse sitten **Tuo**.  

4.  Valitse vahvistusikkunassa **OK**.  

<a name="Localize"></a>   
## <a name="localize-learning-path-controls"></a>Oppimispolun ohjausobjektien lokalisointi  
 Voit lokalisoida oppimispolussa luomiasi ohjausobjektien sisältöä siten, että käyttäjät näkevät ne sillä kielellä, jonka he ovat valinneet [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:ssä. Ohjausobjektit lokalisoidaan viemällä ne, lokalisoimalla kääntäjälle näkyvät merkkijonot ja tuomalla sitten lokalisoidun sisällön sisältävä ohjausobjekti. Voit tuoda ohjausobjektin samaan organisaatioon tai mihin tahansa valitsemaasi organisaatioon. Voit lokalisoida saman ohjausobjektin useilla kielillä ja tuoda sitten kielet niihin organisaatioihin, jotka tukevat kyseisen kielen valinneita käyttäjiä. Oppimispolun lokalisointituki käyttää OASIS XML Localisation Interchange File Format (XLIFF) 2.0 -standardia. Tämän yleisen muodon käyttämiseen liittyviä työkaluja ja opetusohjelmia on saatavana ilmaiseksi. Lisätietoja: [XLIFF Versio 2.0](http://docs.oasis-open.org/xliff/xliff-core/v2.0/os/xliff-core-v2.0-os.html).  

 Lisätietoja [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:n käyttäjien kieliasetuksista: [Henkilökohtaisten asetusten määrittäminen](/dynamics365/customer-engagement/basics/set-personal-options)  

1.  Valitse lokalisoitava ohjausobjekti sisältökirjastossa.  

2.  Valitse ensin **Lokalisoi** ja sitten **Vie**.  

    ![Oppimispolun lokalisointi-valikon vientipainike](media/lp-localize-export.png "Oppimispolun lokalisointi-valikon vientipainike")  

3.  Valitse luotua .zip-tiedoston tallentamisen tapa ja sitten tiedoston nimi ja sijainti.  

    > [!NOTE]
    >  .zip-tiedoston oletusnimi on vientitoiminnossa aina sama, joten kannattaa käyttää yksilöllistä nimeä, jotta aiemmin viedyt tiedostot eivät korvaudu.  

4.  Kun olet lokalisoinut sisällön, valitse sisältökirjastossa ensin **Lokalisoi** ja sitten **Tuo**.  

5.  Valitse tuotava aiemmin viety tiedosto **Selaa**-painikkeella tai vedä tiedosto valintaikkunan **Vedä ohjausobjektit tähän** -valintaikkunaan.  

    > [!CAUTION]
    >  Kun tuot ohjausobjektin, se korvaa kirjastossa jo olevan saman ohjausobjektin muut versiot, vaikka kyseinen ohjausobjekti olisi uudempi.  

6.  Vahvista, että näkyvä tiedostonimi vastaa tuotavaa tiedostoa, ja valitse sitten **Tuo**.  

7.  Valitse vahvistusikkunassa **OK**.  

8.  Julkaise lokalisoitu ohjausobjekti niissä julkaisuympäristöissä, joissa haluat lokalisoidun ohjausobjektin olevan käyttäjien käytettävissä. Lokalisoitu sisältö näytetään automaattisesti käyttäjille, jotka ovat valinneet saman kielen käyttöliittymän kieleksi.  



## <a name="includepn_crm_shortestincludespn-crm-shortestmd-apps-data-center-mapping-to-includepn-azure-shortestincludespn-azure-shortestmd-regions"></a>[!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-sovellusten palvelinkeskuksen ja [!INCLUDE[pn-azure-shortest](../../includes/pn-azure-shortest.md)]-alueiden yhdistäminen
Seuraavassa taulukossa on luettelo [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-sovellusten palvelinkeskusalueista ja niistä vastaavista [!INCLUDE[pn-azure-shortest](../../includes/pn-azure-shortest.md)]-alueista, joissa oppimispolku on käytettävissä.


| [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]:n palvelinkeskus | [!INCLUDE[pn-azure-shortest](../../includes/pn-azure-shortest.md)]-alue |
|------------------------------------------------------------------------|------------------------------------------------------------------------|
|                          Aasia ja Tyynenmeren alue (APAC)                           |                               Itä-Aasia                                |
|                              Kanada (CAN)                              |                             Kanada, keskinen                             |
|       Eurooppa, Lähi-itä, Afrikka ja Iso-Britannia (EMEA, GBR)       |                              Länsi-Eurooppa                               |
|                              Intia (ND)                               |                             Keski-Intia                              |
|                              Japani (JPN)                               |                               Itä-Japani                               |
|                          Pohjois-Amerikka (NAM)                           |                                Itäinen Yhdysvallat                                 |
|                             Oseania (OCE)                              |                             Itä-Australia                             |
|                          Etelä-Amerikka (SAM)                           |                              Brasilia, etelä                              |

## <a name="privacy-notice"></a>Tietosuojatiedot  
[!INCLUDE[cc_privacy_learning_path_authoring](../../includes/cc-privacy-learning-path-authoring.md)]

### <a name="see-also"></a>Katso myös  
 [Oppimispolun Käytössä/ei käytössä-valitsin (avustava ohje)](/dynamics365/customer-engagement/admin/on-off-switch-for-learning-path-guided-help)

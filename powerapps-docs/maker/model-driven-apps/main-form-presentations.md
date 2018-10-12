---
title: Mallipohjaisen sovelluksen päälomakkeen esitykset PowerAppsissa | MicrosoftDocs
description: Ota selvää, miten päälomakkeet näkyvät eri laitteissa näytettyinä.
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: da3ac59a-5413-46cb-b355-1987e42e3853
caps.latest.revision: 35
ms.author: matp
manager: kvivek
ms.openlocfilehash: b8dee40f6dbeba62128434b3eb122add9cb0b373
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674664"
---
# <a name="how-model-driven-app-main-forms-appear-on-different-devices"></a>Mallipohjaisen sovelluksen päälomakkeiden esitystavat eri laitteissa

Päälomaketta käyttävät kaikki mallipohjaisen sovelluksen asiakasohjelmat. Lomake tarjoaa yhdenmukaisen käyttökokemuksen riippumatta siitä, onko käytössä verkkoselain, Dynamics 365:n puhelin- tai tablettisovellus vai Dynamics 365 for Outlook.  
  
<a name="BKMK_MainFormPresentations"></a>   
## <a name="main-forms"></a>Päälomakkeet  
 Entiteetille luodut päälomakkeet ovat kaikki näytettävissä eri tavoin riippuen seuraavassa taulukossa olevista tekijöistä. Kun suunnittelet päälomakkeen, ota huomioon sen toiminta eri esityksissä.  
  
|Esitys|Kuvaus|  
|------------------|-----------------|  
|**Päivitetty**|Päivitetty lomake tarjoaa uuden käyttökokemuksen [päivitetyille ja perinteisille entiteeteille](create-design-forms.md#updated-versus-classic-entities) ja mahdollisille mukautetuille entiteeteille Dynamics 365:n verkko- ja paikallisessa versioissa. Näissä lomakkeissa on uudenlainen komentopalkin muotoilu, ja ne mahdollistavat tiettyjä lisäominaisuuksia, kuten automaattisen tallennuksen ja liiketoimintaprosessien työnkulkuja.|  
|**Dynamics 365 tableteille**| Dynamics 365 tableteille esittää päälomakkeen sisällön tavalla, joka on optimoitu tableteille.|  
|**Dynamics 365 puhelimille**| Dynamics 365 puhelimille esittää päälomakkeen sisällön tavalla, joka on optimoitu puhelimille.|  
|**Perinteinen**|Nämä lomakkeet on tarkoitettu entiteeteille, joita ei ole vielä päivitetty. Ne käyttävät valintanauhaa komentopalkin ja lomakkeen vasemmalla puolella olevan siirtymisruudun sijaan.<br /><br /> Näiden lomakkeiden asettelussa käytetään kahta saraketta.|  
  
<a name="BKMK_MainFormComponentsForUpdatedEntities"></a>   
## <a name="updated-forms"></a>Päivitetyt lomakkeet  
 Tässä kaaviossa näytetään yleisimmät komponentit, joita käytetään päivitetyissä entiteettilomakkeissa.  
  
 ![Kaaviossa näytetään Dynamics 365:n päivitetty entiteettilomakkeen rakenne](media/updated-form-diagram.png "Kaaviossa näytetään Dynamics 365:n päivitetty entiteettilomakkeen rakenne")  
  
 Päivitettyjen entiteettien lomakkeen asettelu toimii monenlaisten näyttöjen ja ikkunakokojen kanssa. Kun ikkunan leveys pienenee, välilehden sarakkeet siirtyvät alas, jolloin niitä voi käyttää vierittämällä alaspäin. Niitä ei siis tiivistetä, eikä käyttäjä joudu vierittämään oikealle.  
  
 Seuraavassa taulukossa on yhteenveto päivitetyissä entiteeteissä käytettävistä päälomakkeen osissa.  
  
|Osa|Yhteenveto|  
|---------------|-------------|  
|**Siirtymispalkki**|Siirtymispalkissa käytetään sivustokartan tietoja, jotta käyttäjä voi siirtyä sovelluksen eri alueille.<br /><br /> Perinteisissä lomakkeissa käytettyä siirtymisruutua ei ole mukana päivitetyssä lomakkeessa. Siirtymispalkki tarjoaa tietueen kontekstissa käyttöön liittyvien tietueiden näkymiä. Käyttäjän ei enää tarvitse siirtyä aiheeseen liittyviin tietueisiin siirtymisruudun tai siirtymispalkin avulla. Sen sijaan mukana on aliruudukoita, jotka on määritetty näyttämään käyttäjälle hyödyllisiä liittyviä tietueita. Tämä muodostaa useimmille käyttäjille entistä paremman käyttökokemuksen.|  
|**Komentopalkki**|Komentopalkissa käytetään valintanauhoille määritettyjä tietoja tietueeseen liittyvien komentojen tarjoamiseen.<br /><br /> Viiden ensimmäisen komennon vieressä on kolme pistettä (![Lisää komentoja -painike](media/not-available.gif "Lisää komentoja -painike")), joiden kautta voi valita kyseisiä lisäkomentoja.|  
|**Kuva**|Kun entiteetissä on kuvakenttä ja entiteetin **Ensisijainen kuva** -asetuksena on **Oletuskuva**, kuvan voi näyttää otsikossa, kun lomake on määritetty kuvan näyttämiseen.|  
|**Ylätunniste**|Ylätunnisteeseen sijoitetut kentät säilyvät näkyvissä, kun käyttäjä selaa lomakkeen runkoa alaspäin.<br /><br /> Ylätunnisteeseen voi sijoittaa enintään neljä kenttää. Ylätunnisteessa ei sallita useita tekstirivejä, verkkoresursseja tai iFrame-kehyksiä. Ylä- ja alatunnisteella on samoja ominaisuuksia osioiden kanssa.|  
|**Prosessin ohjausobjekti**|Kun entiteetissä on aktiivisia liiketoimintaprosessin työnkulkuja, prosessin ohjausobjekti näkyy ylätunnisteen alla. Lisätietoja: [Liiketoimintaprosessien työnkulut](/flow/business-process-flows-overview)|  
|**Runko**|Runko on lomakkeen vieritettävä osa, joka sisältää välilehdet.|  
|**Välilehdet**|Lomakkeen runko jaetaan vaakasuunnassa osiin välilehdillä. Välilehdillä on näytettävä otsikko. Jos otsikko näytetään, sen valitsemalla välilehtiä voi laajentaa tai kutistaa niiden sisällön näyttämiseksi tai piilottamiseksi.<br /><br /> Välilehti voi sisältää enintään kolme saraketta. Kunkin sarakkeen leveydeksi voi asettaa tietyn prosenttiosuuden kokonaisleveydestä. Kun luot uuden välilehden, jokaiseen sarakkeeseen täytetään osa valmiiksi.|  
|**Osat**|Osa täyttää välilehden sarakkeessa olevan tilan. Osilla on näytettävä otsikko, jonka alla voi näyttää viivan.<br /><br /> Osissa voi olla enintään neljä saraketta. Ne voivat sisältää vaihtoehtoja sille, miten osan kenttien otsikot näytetään.|  
|**Kentät**|Kentissä näytetään ohjausobjekteja, joiden avulla käyttäjät tarkastelevat tai muokkaavat entiteettitietueen tietoja. Kenttiä voi muotoilla siten, että ne kattavat jopa neljä saraketta osan sisällä.|  
|**Tyhjä väli**|Tyhjän välin avulla osan sarakkeeseen voi lisätä tyhjää tilaa.|  
|**Aliruudukot**|Aliruudukoilla lomakkeessa voi näyttää luetteloita. Päivitettyjen entiteettien lomakkeet eivät sisällä mahdollisuutta näyttää kaavioita aliruudukkojen avulla.|  
|**Pikalomakkeet**|Pikalomake näyttää tietueen tiedot, joihin on viitattu lomakkeen hakukenttää käyttämällä. Haun kohteena olevassa entiteetissä on oltava pikalomake, ennen kuin sellaisen voi lisätä lomakkeeseen. Lisätietoja: [Pikalomakkeiden luominen ja muokkaaminen](create-edit-quick-view-forms.md)|  
|**Verkkoresurssit**|Päälomakkeisiin voi lisätä HTML- ja Microsoft Silverlight -verkkoresursseja, mutta niitä ei näytetä, kun käytössä on Dynamics 365:n puhelin- ja tablettisovellus.|  
|**iFrame-kehykset**|iFrame (inline frame) on kehys, jonka voi määrittää näyttämään verkkosivun toisesta sivustosta. **Tärkeää:**  <ul><li>Kun iFrame-kehyksessä näytettävä sivu on peräisin toisesta toimialueesta, selaimet soveltavat siihen tavallista tiukempaa suojausta. Tämä saattaa mutkistaa iFrame-kehyksen sisällön ja lomakkeen tietojen välisen vuorovaikutuksen vaatimuksia.</li><li>Entiteettilomakkeen näyttämistä iFrame-kehyksessä, joka on upotettu toiseen entiteettilomakkeeseen, ei tueta. 
|**Bing Maps**|Kun tämä ohjausobjekti on päivitetyn entiteetin lomakkeessa ja **Ota Bing Maps käyttöön** -järjestelmäasetus on käytössä kelvollisen Bing Maps -avaimen kanssa, ohjausobjektia voi käyttää lomakkeessa kerran näyttämään yhden päivitetyssä entiteetissä olevan osoitteen sijainnin. Lisätietoja: [Bing Mapsin määrittäminen](configure-bing-maps-legacy.md)|  
|**Alatunniste**|Alatunnisteeseen voi lisätä minkä tahansa määrän kenttiä, verkkoresursseja tai iFrame-kehyksiä. Kentät ovat vain luku -tilassa, kun ne näytetään alatunnisteessa. Ylä- ja alatunnisteella on samoja ominaisuuksia osioiden kanssa.|  
|**Tilarivi**|Tilarivillä näkyvät tietueen tilakenttä, ilmoitusalue ja tallennuspainike.|  
  
<a name="BKMK_CRMforTabletsPresentation"></a>   
## <a name="dynamics-365-for-phones-and-tablets-forms"></a>Dynamics 365:n puhelin- ja tablettisovellusten lomakkeet  
 Useimmat järjestelmäentiteetit ja mukautetut entiteetit ovat käytettävissä Dynamics 365:n puhelin- ja tablettisovelluksissa. Näiden entiteettien päälomake muunnetaan esitykseksi, joka on optimoitu puhelimille tai tableteille.  
  
<a name="BKMK_EntitiesEnabledForCRMForTablets"></a>   
### <a name="entities-enabled-for-dynamics-365-for-phones-and-tablets"></a>Dynamics 365:n puhelin- ja tablettisovelluksissa käyttöönotetut entiteetit  
 Vain Dynamics 365:n puhelin- ja tablettisovelluksissa käyttöönotetut entiteetit käyttävät tätä päälomakkeen esitystä. Lisätietoja: [Dynamics 365:n puhelin- ja tablettisovelluksissa näytettävät entiteetit](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_CustomEntity)  
  
### <a name="form-design"></a>Lomakkeen rakenne  
 Dynamics 365:n puhelin- ja tablettisovelluksissa käytetään monia päälomakkeen elementtejä, jotka esitetään puhelimille tai tableteille optimoidulla tavalla. Seuraavissa kaavioissa näytetään, miten verkkosovellus juoksutetaan tabletti- ja puhelinsovelluksiin.  
  
 **Verkkosovellus**  
  
 ![Dynamics 365:n lomakkeen juoksutus verkkosovelluksesta](media/custon-reflow-web-app.png "Dynamics 365:n lomakkeen juoksutus verkkosovelluksesta")  
  
 **Tablettisovellus**  
  
 ![Dynamics 365:n lomakkeen juoksutus tablettisovelluksesta](media/reflow-tablet-app.png "Dynamics 365:n lomakkeen juoksutus tablettisovelluksesta")  
  
 **Puhelinsovellus**  
  
 ![Dynamics 365:n lomakkeen juoksutus puhelinsovelluksesta](media/custon-reflow-phone-app.png "Dynamics 365:n lomakkeen juoksutus puhelinsovelluksesta")  
  
 Dynamics 365:n tablettisovelluksessa lomakkeen elementit muutetaan leveäksi vaaka-asetteluksi, jossa käyttäjä voi pyyhkäisemällä muuttaa näkymäversion elementtejä. Dynamics 365:n puhelinsovelluksessa käyttäjä tuo näyttöä pyyhkäisemällä näkyviin eri sarakkeen tai elementtiruudun. Prosessiohjausobjekti näkyy jokaisen sarakkeen yllä.  
  
### <a name="view-port-element"></a>Näkymäversion elementit  
 Seuraavat kohteet näkyvät aina näkymäversiossa lomakkeen kontekstissa:  
  
 **Siirtymispalkki**  
 Navigointipalkki on sivustokartan kosketuskäyttöön optimoitu esitys. Lisätietoja: [Siirtymisasetusten muuttaminen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_NavigationOptions)  
  
 **Aloitus**  
 Aloituspainike vie käyttäjän koontinäyttöön, joka toimii Dynamics 365:n puhelin- ja tablettisovellusten aloitussivuna.  
  
 **Prosessin ohjausobjekti**  
 Jos entiteetissä on otettu käyttöön liiketoimintaprosessi, se näkyy Dynamics 365:n tablettisovelluksen oikeassa yläkulmassa haun ohjausobjektin vieressä ja Dynamics 365:n puhelinsovelluksessa näytön yläreunassa.  
  
 **Haku**  
 Haun ohjausobjektia napauttamalla avautuu näyttö tietueiden hakemista varten.  
  
 **Komentopalkki**  
 Oletusarvoisesti tietyt komennot, jotka näkyvät Dynamics 365:n selainversiossa, eivät näy sen puhelin- ja tablettisovelluksissa. Verkkosovelluksen tavoin komentopalkki on kontekstisidonnainen. Käytettävissä olevat komennot muuttuvat riippuen siitä, mitä kulloinkin katsotaan tai valitaan. Lisätietoja: [Komentojen muuttaminen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_ChangeCommands)  
  
### <a name="form-elements"></a>Lomakkeen elementit  
 Näytetyt lomakkeen elementit otetaan päälomakkeesta ja esitetään sarjana ruutuja, jotka käyttäjät näkevät näkymäversion kautta.  
  
 Dynamics 365:n tablettisovelluksessa ensimmäinen ruutu näyttää yhteystietoja tietueelle olemassa olevista suhteista. Dynamics 365:n puhelinsovelluksessa ensimmäinen ruutu näyttää lisäksi ylätunnistekentät lomakkeesta suhderuutujen yläpuolella.  
  
 ![Dynamics 365:n tablettisovelluksen suhderuutu](media/mobile-app-form-relationships.png "Dynamics 365:n tablettisovelluksen suhderuutu")  
  
 Yhteystieto- ja käyttäjälomakkeiden osalta ylin kohde näyttää tietueen viestintäkortin. Viestintäkortti sisältää painikkeita, joilla voi aloittaa viestinnän henkilön kanssa. Muiden entiteettien osalta viestintäkortti näytetään, jos päälomakkeeseen on upotettu yhteystietojen pikalomake.  
  
 Voit näyttää muita ruutuja riippuen entiteetin suhteista, mutta seuraavien entiteettien ruutuja ei voi mukauttaa:  
  
|Entiteetti|Ruudut|  
|------------|-----------|  
|Tili|Omistaja|  
|Yhteystiedot|Yrityksen nimi, omistaja|  
|Liidi|Omistaja|  
|Mahdollisuus|Tili, omistaja|  
  
 Muita ruutuja voi mukauttaa lomake-editorilla. Järjestys on kiinteä, mutta voit määrittää näkyvät elementit suhdepaneelissa.  
  
 Dynamics 365:n tablettisovelluksessa toinen ruutu alkaa lomakkeen ensimmäisen välilehden nimellä. Ylätunnisteeseen mahdollisesti kuuluvat kentät sisällytetään mukaan ensimmäisen välilehden sisällön ohella. Dynamics 365:n puhelinsovelluksessa ylätunnisteet näkyvät ensimmäisessä sarakkeessa.  
  
 ![CRM:n tablettisovelluksen lomakkeen ensimmäinen paneeli](media/mobile-app-form-first-panel.png "CRM:n tablettisovelluksen lomakkeen ensimmäinen paneeli")  
  
 Jos lomakkeelle on aktiivinen prosessin työnkulkua, kolmas välilehti näyttää prosessin nykyisen vaiheen tehtävät Dynamics 365:n tablettisovelluksessa. Dynamics 365:n puhelinsovelluksessa prosessin ohjausobjekti kelluu ruutujen yläpuolella. Se laajenee valittaessa käyttäjän nykyisen ruudun päälle sekä on aina näkyvissä ja käytettävissä.  
  
 Lomakkeen muut ruudut sisältävät lomakkeen välilehtien sisällön. Mahdolliset aliruudukot näytetään erillisenä paneelina.  
  
 Dynamics 365:n puhelin- ja tablettisovelluksen lomake näyttää aina välilehtien ja aliruudukoiden otsikot. **Näytä otsikko lomakkeessa** -asetusta ei käytetä.  
  
> [!NOTE]
>  Jotta suorituskyky pystyttäisiin optimoimaan mobiililaitteissa, objektien määrä on rajoitettu viiteen välilehteen, 75 kenttään ja kymmeneen aliruudukkoon.  
  
 Dynamics 365:n puhelin- ja tablettisovelluksen lomakkeet eivät tue seuraavia:  
   
-   Bing Maps  
  
-   Yammer
  
-   Toimintosyötteet  
  
-   Teemat  
  
 Lisäksi entiteetin kuvat näkyvät luettelonäkymissä ja yhteystietokorteissa mutta eivät varsinaisessa lomakkeessa.  
  
<a name="BKMK_MultipleForms"></a>   
### <a name="multiple-forms"></a>Useat lomakkeet  
 Dynamics 365:n puhelin- ja tablettisovellus tukee useita lomakkeita mutta ei sisällä mahdollisuutta vaihtaa lomakkeesta toiseen, vaikka käyttäjä voisi käyttää useita lomakkeita. Käyttäjät näkevät ensimmäisen lomakkeen siinä järjestyksessä, jossa heillä on niihin käyttöoikeus.  
  
 Jos sinulla on esimerkiksi seuraavat päälomakkeet mahdollisuusentiteetille ja olet saanut seuraavat käyttöoikeusroolit niistä jokaiselle, näet lomakkeet seuraavan taulukon järjestyksessä.  
  
|Lomakkeiden järjestys|Lomakkeen nimi|Käyttöoikeusroolit|  
|----------------|---------------|--------------------|  
|1|**Myyntilomake 1**|Myyjä|  
|2|**Myyntilomake 2**|Myyjä ja myyntipäällikkö|  
|3|**Myyntilomake 3**|Myyntipäällikkö|  
|4|**Myyntilomake 4**|Myynnin varajohtaja|  
  
-   Henkilöt, joilla on myyjän rooli, näkevät aina **myyntilomakkeen 1**.  
  
-   Henkilöt, joilla on myyntipäällikön rooli, näkevät aina **myyntilomakkeen 2**.  
  
-   Henkilöt, joilla on myynnin varajohtajan rooli, näkevät aina **myyntilomakkeen 4**.  
  
<a name="BKMK_ClassicPresentation"></a>   
## <a name="classic-forms"></a>Perinteiset lomakkeet  
 Seuraavassa kaaviossa näkyvät perinteissä esityksessä käytetyt päälomakkeen osat.  
  
 ![Päälomakkeen elementit](media/elements.png "Päälomakkeen elementit")  
  
 Päivitettyjen entiteettien lomakkeet ovat perineet useita osia perinteisistä lomakkeista, mutta niissä on merkittäviä eroja.  
  
 Perinteistä esitystä käyttävät lomakkeet eivät sisällä siirtymispalkkia, ja komentopalkin sijaan niissä käytetään valintanauhaa. Nämä lomakkeet eivät tue entiteetin kuvia, prosessin ohjausobjektia, pikalomakkeita, automaattista tallennusta tai Bing Mapsia. Ylätunnisteen kenttiä ei voi muokata.  
  
 Lomakeavustaja näytetään tietyille entiteeteille, jollainen on esimerkiksi `Article`.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Luo ja suunnittele lomakkeita](create-design-forms.md)   

 

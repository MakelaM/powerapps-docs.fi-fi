---
title: Mallipohjaisen sovelluksen päälomake-esitykset PowerAppsissa | MicrosoftDocs
description: 'Tietoja siitä, miten päälomakkeet näkyvät laitteissa'
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="how-model-driven-app-main-forms-appear-on-different-devices"></a>Mallipohjaisen sovelluksen päälomakkeiden ulkoasu eri laitteissa

Kaikki malliin perustuvat sovellusasiakkaat käyttävät päälomaketta. Tämä lomake sisältää yhdenmukaisen käyttäjäkokemuksen siitä huolimatta, onko käytössä verkkoselain, Dynamics 365 for phones, Dynamics 365 for tablets tai Dynamics 365 for Outlook.  
  
<a name="BKMK_MainFormPresentations"></a>   
## <a name="main-forms"></a>Päälomakkeet  
 Kaikki entiteetin päälomakkeet voivat näkyä eri tavoilla seuraavassa taulukossa olevien tekijöiden perusteella. Ota päälomakkeen suunnittelussa huomioon, miten se toimii kussakin esityksessä.  
  
|Esitys|Kuvaus|  
|------------------|-----------------|  
|**Päivitetty**|Päivitetyn lomakkeen käyttökokemus on erilainen Dynamics 365 (online)- ja Dynamics 365 on-premises -ohjelmassa sen mukaan, ovatko kyseessä [päivitetyt entiteetit ja perinteiset entiteetit](create-design-forms.md#updated-versus-classic-entities) vai mukautetut entiteetit. Näissä lomakkeissa on uudempi komentopalkin rakenne, jossa on käytössä lisätoimintoja, kuten automaattinen tallentaminen ja liiketoimintaprosesseja.|  
|**Dynamics 365 for tablets**| Dynamics 365 for tablets -versioissa päälomakkeen sisältö esitetään tabletille optimoidulla tavalla.|  
|**Dynamics 365 for phones**| Dynamics 365 for phones -versioissa päälomakkeen sisältö esitetään puhelimelle optimoidulla tavalla.|  
|**Perinteinen**|Nämä lomakkeet ovat entiteeteille joita ei ole päivitetty. Ne käyttävät valintanauhaa, eivätkä komentopalkkia ja siirtymisruutu on lomakkeen vasemmalla puolella.<br /><br /> Näissä lomakkeissa käytetään kaksisarakkeista asettelua.|  
  
<a name="BKMK_MainFormComponentsForUpdatedEntities"></a>   
## <a name="updated-forms"></a>Päivitetyt lomakkeet  
 Tämä kaavio sisältää päivitettyjen entiteettilomakkeiden yhteiset osat.  
  
 ![Kaaviossa näkyy Dynamics 365:n entiteettilomakkeen päivitetty rakenne](media/updated-form-diagram.png "Kaaviossa näkyy Dynamics 365:n entiteettilomakkeen päivitetty rakenne")  
  
 Päivitettyjen entiteettien lomakeasettelu toimii monenlaisissa näytöissä ja erikokoisissa ikkunoissa. Kun ikkunan leveys pienenee, välilehden sarakkeet siirtyvät alaspäin ja voit käyttää niitä vierittämällä alaspäin. Sarakkeita ei siis tiivistetä eikä niitä tarvitse vierittää oikealle.  
  
 Seuraavassa taulukossa on yhteenveto päivitettyjen entiteettien päälomakkeessa käytettävistä osista.  
  
|Osa|Yhteenveto|  
|---------------|-------------|  
|**Siirtymispalkki**|Mahdollistaa siirtymisen sovelluksen muiden alueille sivustokartan tietojen avulla.<br /><br /> Päivitetyssä lomakkeessa ei ole perinteisissä lomakkeissa käytettyä siirtymisruutua. Tietuekontekstissa siirtymispalkin avulla voi tarkastella liittyvien tietueiden näkymiä. Sen sijaan että liittyviin tietueisiin siirryttäisiin siirtymisruudusta tai siirtymispalkin avulla, useimpien käyttäjien käyttökokemusta voi parantaa lisäämällä aliruudukkoja, jotka on määritetty näyttämään hyödyllisiä liittyviä entiteettitietueita.|  
|**Komentopalkki**|Tietueeseen liittyvät komennot annetaan valintanauhoja varten määritettyjen tietojen avulla.<br /><br /> Näkyvissä on viisi ensimmäistä komentoa. Lisäkomentoja voi valita napsauttamalla kolmen pisteen (![Lisäkomentoja-painiketta](media/not-available.gif "Lisäkomentoja-painiketta")), jotka avaavat pikaikkunan.|  
|**Kuva**|Kun entiteetissä on kuvakenttä ja entiteetin **Ensisijainen kuva** -asetukseksi on valittu **Oletuskuva**, kuva voidaan näyttää ylätunnisteessa silloin, kun lomake on määritetty näyttämään kuva.|  
|**Ylätunniste**|Ylätunnisteeseen sijoitetut kentät näkyvät, kun käyttäjät vierittävät lomakkeen runkoa alaspäin.<br /><br /> Ylätunnisteeseen voidaan sijoittaa enintään neljä kenttää. Ylätunnisteessa ei voi käyttää useita tekstirivejä, verkkoresursseja eikä iFrame-kehyksiä. Ylä- ja alatunnisteet jakavat joitakin ominaisuuksia osien kanssa.|  
|**Prosessinhallinta**|Kun entiteetissä on aktiivisia liiketoimintaprosesseja, prosessinhallinta näkyy ylätunnisteen alapuolella. Lisätietoja: [Liiketoimintaprosessit](/flow/business-process-flows-overview)|  
|**Teksti**|Runko on lomakkeen välilehdet sisältävä vieritettävä osa.|  
|**Välilehdet**|Lomakkeen runko erotellaan vaakasuunnassa välilehtien avulla. Välilehdissä on otsikko, joka voidaan näyttää. Jos otsikko on näkyvissä, välilehdet voidaan laajentaa näyttämään sisältö tai tiivistää piilottamaan sisältö valitsemalla otsikko.<br /><br /> Välilehdissä on enintään kolme saraketta, ja kunkin sarakkeen leveys voidaan määrittää kokonaisleveyden prosenttiosuutena. Kun luot uuden välilehden, jokaiseen sarakkeeseen lisätään valmiiksi osa.|  
|**Osat**|Osa käyttää välilehtisarakkeessa olevaa tilaa. Osilla on otsikko, joka voidaan näyttää, ja otsikon alapuolella voidaan näyttää viiva.<br /><br /> Osissa voi olla enintään neljä saraketta, ja ne sisältävät asetukset, joilla määritetään osan kenttien otsikoiden näyttäminen.|  
|**Kentät**|Ohjausobjektit, joilla käyttäjät tarkastelevat tai muokkaavat entiteettitietueen tietoja, näkyvät kentissä. Kentät voidaan muotoilla käyttämään neljää osan saraketta.|  
|**Tyhjä väli**|Osasarakkeeseen voidaan lisätä tyhjä väli.|  
|**Aliruudukot**|Aliruudukot mahdollistavat luettelon näyttämisen lomakkeessa. Päivitettyjen entiteettien lomakkeissa ei ole mahdollista käyttää aliruudukoita kaavioiden näyttämiseen.|  
|**Pikalomake**|Pikalomake näyttää lomakkeen valintakentässä viitatun tietueen tiedot. Valintakentän kohteena olevassa entiteetissä on oltava pikalomake, ennen kuin se voidaan lisätä lomakkeeseen. Lisätietoja: [Pikalomakkeiden luominen ja muokkaaminen](create-edit-quick-view-forms.md)|  
|**WWW-resurssit**|HTML ja Microsoft Silverlight -verkkoresurssit voidaan lisätä päälomakkeisiin, mutta niitä ei näytetä Dynamics 365 for phones- ja Dynamics 365 for tablets -sovelluksissa.|  
|**iFrame**|Sisäinen kehys, joka on määritetty näyttämään toisen sivuston verkkosivu. **Tärkeää:**  <ul><li>Kun iFrame-kehyksessä näytetään toisen toimialueen sivu, selaimet käyttävät korkeampaa tietoturvatasoa. Tämä saattaa asettaa lisävaatimuksia tavalle, jolla iFrame-kehyksen sisältö voi kommunikoida lomakkeessa olevien tietojen kanssa.</li><li>Toiseen entiteettilomakkeeseen upotetussa iFrame-kehyksessä olevan entiteettilomakkeen näyttämistä ei tueta. 
|**Bing-kartat**|Kun ohjausobjekti on päivitetyn entiteetin lomakkeessa ja järjestelmäasetus **Ota Bing Maps käyttöön** on otettu käyttöön kelvollisella Bing Maps -avaimella, ohjausobjektia voi käyttää lomakkeessa kerran näyttämään yhden päivitetyn entiteetin osoitteen sijainnin. Lisätietoja: [Bing Mapsin määrittäminen](configure-bing-maps-legacy.md)|  
|**Alatunniste**|Alatunnisteeseen lisättävien kenttien, verkkoresurssien tai iFrame-kehysten määrää ei ole rajoitettu. Alatunnisteessa näkyvät kentät ovat vain luku -muotoisia. Ylä- ja alatunnisteet jakavat joitakin ominaisuuksia osien kanssa.|  
|**Tilarivi**|Tilarivi näyttää tietueen tilakentän, ja siinä on myös ilmaisinalue ja tallennuspainike.|  
  
<a name="BKMK_CRMforTabletsPresentation"></a>   
## <a name="dynamics-365-for-phones-and-tablets-forms"></a>Dynamics 365 puhelimet ja tabletit -lomakkeet  
 Suurin osa järjestelmäentiteeteistä ja mukautetuista entiteeteistä on käytettävissä Dynamics 365 for phones- ja Dynamics 365 for tablets -sovelluksissa. Näiden entiteettien päälomake on muunnettu puhelimille tai taulutietokoneille optimoiduksi esitykseksi.  
  
<a name="BKMK_EntitiesEnabledForCRMForTablets"></a>   
### <a name="entities-enabled-for-dynamics-365-for-phones-and-tablets"></a> Dynamics 365 puhelimille ja tableteille -ratkaisun käyttöön soveltuvat entiteetit  
 Vain entiteetit, joiden käyttö on mahdollista Dynamics 365 for phones- ja Dynamics 365 for tablets -sovelluksissa, esittävät päälomakkeen tässä muodossa. Lisätietoja: [Dynamics 365 for phones- ja Dynamics 365 for tablets -sovelluksissa näytettävät entiteetit](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_CustomEntity)  
  
### <a name="form-design"></a>Lomakkeen asettelu  
 Dynamics 365 for phones- ja Dynamics 365 for tablets -sovellukset esittävät päälomakkeen elementit puhelimille ja taulutietokoneille optimoituina. Seuraavissa kaavioissa näytetään verkkosovelluksen ja taulutietokone- ja puhelinsovelluksen väliset siirtymät.  
  
 **Verkkosovellus**  
  
 ![Dynamics 365:n lomakkeiden siirtymä verkkosovelluksesta](media/custon-reflow-web-app.png "Dynamics 365:n lomakkeiden siirtymä verkkosovelluksesta")  
  
 **Taulutietokonesovellus**  
  
 ![Dynamics 365:n lomakkeiden siirtymä tablettisovellukseen](media/reflow-tablet-app.png "Dynamics 365:n lomakkeiden siirtymä tablettisovellukseen")  
  
 **Puhelinsovellus**  
  
 ![Dynamics 365:n lomakkeiden siirtymä puhelinsovellukseen](media/custon-reflow-phone-app.png "Dynamics 365:n lomakkeiden siirtymä puhelinsovellukseen")  
  
 Lomake-elementit muunnetaan leveäksi panoraama-asetteluksi Dynamics 365 for tablets -sovelluksessa, jossa käyttäjät voivat muuttaa näyttöikkunassa näkyviä tietoja näyttöä sipaisemalla. Dynamics 365 for phones -sovelluksessa käyttäjät saavat eri sarakkeen tai elementtiruudun näkyviin sipaisemalla näyttöä. Jokaisessa sarakkeessa näkyy prosessin ohjausobjekti.  
  
### <a name="view-port-element"></a>Näyttöikkunaelementti  
 Seuraavat kohteet näkyvät aina näyttöikkunassa lomakekontekstissa:  
  
 **Siirtymispalkki**  
 Siirtymispalkki on kosketuskäyttöön optimoitu sivukartan esitys. Lisätietoja: [Siirtymisasetusten muuttaminen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_NavigationOptions)  
  
 **Aloitus**  
 Kotisivupainikkeen avulla käyttäjät voivat palata takaisin Dynamics 365 for phones- ja Dynamics 365 for tablets -sovellusten aloitussivun koontinäyttöön.  
  
 **Prosessinhallinta**  
 Jos liiketoimintaprosessi on otettu käyttöön entiteetissä, se näkyy Dynamics 365 for tablets -sovelluksen oikeassa yläkulmassa hakuohjausobjektin vieressä ja Dynamics 365 for phones -sovelluksen näytön yläosassa.  
  
 **Hae**  
 Käyttäjät voivat avata hakunäytön ja hakea tietueita napauttamalla hakuohjausobjektia.  
  
 **Komentopalkki**  
 Oletusarvoisesti jotkin verkkoselaimen sovelluksessa näkyvät komennot eivät näy Dynamics 365 for phones- ja Dynamics 365 for tablets -sovelluksissa. Samoin kuin verkkosovelluksessa komentopalkki on tilannekohtainen, joten käytettävissä olevat komennot muuttuvat sen mukaan, mitä juuri sillä hetkellä katsotaan tai valitaan. Lisätietoja: [Komentojen muuttaminen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_ChangeCommands)  
  
### <a name="form-elements"></a>Lomake-elementit  
 Näkyvät lomake-elementit haetaan päälomakkeesta ja esitetään käyttäjien näyttöikkunassa näkeminä ruutusarjoina.  
  
 Dynamics 365 for tablets -sovelluksessa ensimmäinen ruutu sisältää tietueen suhteiden yhteystiedot. Dynamics 365 for phones -sovelluksessa ensimmäinen ruutu sisältää myös suhderuutujen yläpuolella olevan lomakkeen otsikkokentät.  
  
 ![Dynamics 365 taulutietokoneille -yhteysruutu](media/mobile-app-form-relationships.png "Dynamics 365 taulutietokoneille -yhteysruutu")  
  
 Yhteystieto- ja käyttäjälomakkeissa on ylimpänä tietueen viestintäkortti. Viestintäkortissa on painikkeita, joilla voi aloittaa viestinnän henkilön kanssa. Muissa entiteeteissä viestintäkortti on näkyvissä, jos päälomakkeeseen on upotettu yhteyshenkilöpikalomake.  
  
 Entiteettisuhteiden perusteella näyttöön saadaan lisää ruutuja. Seuraavien entiteettien ruutuja ei kuitenkaan voi mukauttaa:  
  
|Entiteetti|Ruudut|  
|------------|-----------|  
|Tili|Omistaja|  
|Yhteyshenkilö|Yrityksen nimi, omistaja|  
|Liidi|Omistaja|  
|Mahdollisuus|Asiakas, omistaja|  
  
 Jäljellä olevat ruudut voi mukauttaa lomake-editorin avulla. Järjestys on ennalta määrätty, mutta voit määrittää, mitkä elementit näkyvät suhdepaneelissa.  
  
 Dynamics 365 for tablets -sovelluksen toisessa ruudussa on ensimmäisenä lomakkeen ensimmäisen välilehden nimi. Mukana ovat kaikki ylätunnisteessa olevat välilehdet samoin kuin välilehden sisältö. Dynamics 365 for phones -sovelluksessa ylätunnisteet näkyvät ensimmäisessä sarakkeessa.  
  
 ![CRM taulutietokoneille -lomakkeen ensimmäinen ruutu](media/mobile-app-form-first-panel.png "CRM taulutietokoneille -lomakkeen ensimmäinen ruutu")  
  
 Jos lomakkeessa on aktiivinen prosessi, kolmannessa välilehdessä mainitaan Dynamics 365 for tablets -sovelluksen prosessin meneillään olevan vaiheen tehtävät. Dynamics 365 for phones -sovelluksen prosessin ohjausobjekti kelluu ruutujen yläpuolella ja laajenee käyttäjän ruutuun, kun se valitaan. Se on aina näkyvissä ja käytettävissä.  
  
 Lomakkeen jäljellä olevat ruudut sisältävät lomakkeen välilehtien sisällön. Mahdolliset aliruudukot näkyvät omassa ruudussaan.  
  
 Dynamics 365 for phones- ja Dynamics 365 for tablets -sovellusten -lomake näyttää aina välilehtien ja aliruudukoiden otsikot. **Näytä otsikko lomakkeessa** -asetusta ei käytetä.  
  
> [!NOTE]
>  Kohteiden määrä rajataan 5 välilehteen tai 75 kenttään ja 10 aliruudukkoon, jotta suorituskyky saadaan optimoitua mobiililaitteita varten.  
  
 Dynamics 365 for phones- ja Dynamics 365 for tablets -sovellusten lomakkeet eivät tue seuraavia kohteita:  
   
-   Bing-kartat  
  
-   Yammer
  
-   Aktiviteettisyötteet  
  
-   Teemat  
  
 Lisäksi entiteettikuvat näkyvät luettelonäkymissä ja yhteystietokorteissa, mutta eivät itse lomakkeessa.  
  
<a name="BKMK_MultipleForms"></a>   
### <a name="multiple-forms"></a>Useita lomakkeita  
 Vaikka Dynamics 365 for phones- ja Dynamics 365 for tablets -sovellukset tukevat useita lomakkeita, käyttäjät eivät voi vaihtaa lomakkeiden välillä, jos heillä on käytössä useita lomakkeita. Käyttäjät näkevät lomakejärjestyksessä ensimmäisen lomakkeen, jonka käyttöoikeus heillä on.  
  
 Jos sinulla on esimerkiksi seuraavat mahdollisuus-entiteetin päälomakkeet ja olet delegoinut kullekin seuraavat käyttöoikeusroolit, näet seuraavassa taulukossa olevan lomakejärjestyksen.  
  
|Lomakejärjestys|Lomakkeen nimi|Käyttöoikeusroolit|  
|----------------|---------------|--------------------|  
|1|**Myyntilomake 1**|Myyjä|  
|2|**Myyntilomake 2**|Myyjä ja myyntipäällikkö|  
|3|**Myyntilomake 3**|Myynnin päällikkö|  
|4|**Myyntilomake 4**|Myynnin varajohtaja|  
  
-   Käyttäjä, jolla on myyjän rooli, näkee aina **myyntilomakkeen 1**.  
  
-   Käyttäjä, jolla on myyntipäällikön rooli, näkee aina **myyntilomakkeen 2**.  
  
-   Käyttäjä, jolla on myynnin varajohtajan rooli, näkee aina **myyntilomakkeen 4**.  
  
<a name="BKMK_ClassicPresentation"></a>   
## <a name="classic-forms"></a>Perinteiset lomakkeet  
 Seuraavassa kaaviossa näytetään perinteisessä esityksessä käytetyn päälomakkeen osat.  
  
 ![Tärkeimmät lomake-elementit](media/elements.png "Tärkeimmät lomake-elementit")  
  
 Päivitettyjen entiteettien lomakkeet ovat perineet monia perinteisten lomakkeiden osia mutta niissä on myös merkittäviä eroja.  
  
 Perinteistä esitystä käyttävissä lomakkeissa ei ole siirtymispalkkia. Lisäksi komentopalkin sijasta käytetään valintanauhaa. Lomakkeet eivät tue entiteettikuvia, prosessinhallintaa, pikalomakkeita, automaattista tallennusta tai Bing Maps -sovellusta. Ylätunnisteen kenttiä ei voi muokata.  
  
 Tietyt entiteetit, kuten `Article`, näyttävät lomakeavustajan.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Luo ja suunnittele lomakkeita](create-design-forms.md)   

 

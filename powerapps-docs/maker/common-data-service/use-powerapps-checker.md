---
title: Sovellusten tarkistaminen PowerAppsissa ratkaisun tarkistustoiminnolla | Microsoft Docs
description: Tarkista ratkaisu ratkaisun tarkistustoiminnon avulla.
author: Mattp123
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: article
ms.date: 12/04/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="use-solution-checker-to-validate-your-model-driven-apps-in-powerapps"></a>Mallipohjaisten sovellusten tarkistaminen PowerAppsissa ratkaisun tarkistustoiminnolla

Kun mallipohjaisten sovellusten kehittäjät luovat yrityksen toiveita vastaavan ratkaisun, tuloksena on usein erittäin kehittyneitä ratkaisuja, jotka mukauttavat ja laajentavat Common Data Service (CDS) sovelluksille -ympäristöä. Tällaisiin toteutuksiin liittyy usein riski, että ratkaisun suorituskyky, vakaus ja luotettavuus kärsivät, mikä voi vaikuttaa kielteisesti käyttäjäkokemukseen. Tällaisten ongelmien havaitseminen ja niiden ratkaiseminen voi olla hankalaa ja viedä paljon aikaa. Ratkaisun tarkistustoiminnon avulla voi tehdä monipuolisen staattisen analyysin, jossa ratkaisun käyttöä verrataan parhaiden käytäntöjen mukaisiin sääntöihin. Tällä tavoin ongelmalliset kohdat havaitaan nopeasti. Saat tarkistuksen valmistumien jälkeen yksityiskohtaisen raportin havaituista ongelmista, osista ja koodista, joihin nämä ongelmat vaikuttavat, sekä linkin kunkin ongelman ratkaisuohjeisiin.

Ratkaisun tarkistustoimintoa analysoi seuraavat ratkaisun osat. 
- CDS sovelluksille -laajennukset
- Mukautetut CDS sovelluksille -työnkulkuaktiviteetit 
- CDS -sovelluksille verkkoresurssit (HTML ja JavaScript)
- CDS sovelluksille -määritykset, kuten SDK-viestin osavaiheet 

Ratkaisun tarkistustoimintoa voi käyttää sellaisissa hallitsemattomissa ratkaisuissa, jotka voidaan viedä ympäristöstä. Ratkaisun tarkistustoimintoa ei voi käyttää seuraavissa ratkaisuissa: 
- Järjestelmän oletusratkaisut (oletusratkaisu ja Common Data Services -oletusratkaisu).
- Ratkaisut, joissa JavaScript käyttää versiota ECMAScript 6 (2015) tai sitä uudempaa versiota. Jos havaitaan, että JavaScript käyttää jotakin näistä versioista, verkkoresurssin JS001-syntaksiongelma ilmoitetaan.

> [!NOTE]
> Ominaisuus on tällä hetkellä esiversiossa ja käytössä vain Pohjois-Amerikan alueella. 
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]


## <a name="enable-the-solution-checker"></a>Ratkaisun tarkistustoiminnon ottaminen käyttöön
Ratkaisun tarkistustoiminto on käytettävissä PowerAppsin Ratkaisut-alueella sen jälkeen, kun PowerAppsin tarkistustoimintoratkaisu on asennettu. Huomaa, että se ei löydy selaamalla eikä hakemalla Microsoft Appsourcesta. Se on asennettava seuraavasti:  

1. Kirjaudu [PowerAppsiin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja valitse Common Data Service -ympäristö, jossa haluat ottaa ratkaisun tarkistustoiminnon käyttöön. 
2. Valitse vasemmassa siirtymisruudussa **Ratkaisut**.
3. Valitse työkalurivillä ensin **Ratkaisun tarkistustoiminto** ja sitten **Asenna**. Microsoft AppSource -sivu avautuu. Ponnahdusikkunat on sallittava, jos selain estää sivun avautumisen. 

   ![Ratkaisun tarkistustoiminnon asentaminen](media/solution-checker-install.png)

4. Valitse **Ilmainen kokeiluversio** AppSource-sivulla. 
5. Hyväksy ehdot ja valitse ympäristö, johon PowerAppsin tarkistustoimintoratkaisu asennetaan. 
6.  Kun asennus on valmis, päivitä **Ratkaisu**-luettelo PowerApps-sivustossa. Tällä tavoin voit varmistaa, että ratkaisun tarkistustoiminto on käytettävissä.  
7. Tarkista ratkaisu [suorittamalla ratkaisun tarkistustoiminto](#run-the-solution-checker).


<!-- ### Components created with the PowerApps checker
When you install the PowerApps checker these solution specific components are created. 
- Entities: The entities that are created are required to store the results of solution analysis and the status of analysis jobs in your environment.
   - Analysis Component
   - Analysis Job
   - Analysis Result
- System job: A system job is created so admins can remove solution analysis data from the environment. The job contains a configuration value, currently set to remove the solution analysis data after 60 days, which an administrator can override. 
- Security Roles: Two security roles, **Export Customizations**, and **Solution Checker** are created. These roles are required to export the solution for analysis, and storing the analysis results to the entities in your environment.
- User principle: The **PowerApps Advisor** user is created that allows the checker to authenticate with your CDS for Apps environment and assign the two security roles, Export Customizations and Solution Checker. The PowerApps Advisor is an application user and does not consume a license.  -->

## <a name="run-the-solution-checker"></a>Ratkaisun tarkistustoiminnon suorittaminen
Kun PowerAppsin tarkistustoiminto on asennettu ympäristöön, **Ratkaisun tarkistustoiminto** on valittavissa valikossa, kun valitset hallitsemattoman ratkaisun PowerAppsin **Ratkaisut**-alueella. 

1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen. 
2. Valitse vasemmassa ruudussa **Ratkaisut**. 
3. Valitse sen hallitsemattoman ratkaisun vieressä, jonka haluat analysoida, **...**, osoita**Ratkaisun tarkistustoiminto** -kohtaa ja valitse **Suorita**. 

   ![Ratkaisun tarkistustoimintokomennon suorittaminen](media/solution-checker-run.png)

4.  **Ratkaisut**-sivun oikeassa yläkulmassa on tilaruutu, jossa on teksti **Ratkaisun tarkistus on käynnissä**. 

    ![Ratkaisun tarkistustoiminnon tila](media/solution-checker-status.png)
   
     Huomaa seuraavat asiat:
       - Voi kestää muutamia minuutteja, kun ratkaisun tarkistustoiminto viimeistelee analyysin. 
    
       - Tänä aikana **Käynnissä…**-tila näkyy **Ratkaisu**-luettelon **Ratkaisun tarkistus** -sarakkeessa. 
    
       - Kun tarkistus on valmis, saat siitä sähköposti-ilmoituksen. Lisäksi PowerApps-sivuston **Ilmoitukset**-alueella on ilmoitus.  

5.  [Tarkastele raporttia,](#reviewing-the-solution-checker-report) kun tarkistus on valmis.

## <a name="cancel-a-check"></a>Tarkistuksen peruuttaminen

Lähetetty ratkaisun ympäristötarkistus voidaan peruuttaa tilaruudussa, joka on **Ratkaisut**-sivun oikeassa yläkulmassa. 

Kun tarkistus peruutetaan, ratkaisun tarkistus keskeytetään ja ratkaisun tarkistustila palautuu edelliseen tilaan. 

## <a name="solution-checker-states"></a>Ratkaisun tarkistustoiminnon tilat
Kun ratkaisun tarkistustoiminto asennetaan ympäristöön, **Ratkaisun tarkistus** -sarake on käytettävissä **Ratkaisut**-luettelossa. Tässä sarakkeessa näkyy ratkaisun analysointitilat. 

|Osavaltio  |Kuvaus  |
|---------|---------|
|Ei ole suoritettu    | Ratkaisua ei ole koskaan analysoitu.        |
|Käynnissä     | Ratkaisua analysoidaan.       |
|Ei voitu suorittaa loppuun     |  Ratkaisun analysointia pyydettiin mutta analyysia ei onnistunut.       |
|Tulokset alkaen *päivämäärä ja aika*   | Ratkaisun analysointi on tehty ja tulokset voi ladata.      |
| Ei voitu suorittaa loppuun. Tulos alkaen *päivämäärä ja aika*     | Viimeisintä analyysipyyntöä ei voitu suorittaa loppuun. Viimeiset onnistuneet tulokset voidaan ladata.         |
|Microsoft tarkistanut     | Tämä on Microsoftin hallittu ratkaisu. Ratkaisun analyysia ei voi tehdä näissä ratkaisuissa.         |
|Julkaisija tarkistanut     |  Tämä on kolmannen osapuolen hallittu ratkaisu. Ratkaisun analyysia ei voi tällä hetkellä käyttää näissä ratkaisuissa.        |


## <a name="review-the-solution-checker-report"></a>Ratkaisun tarkistustoiminnon raportin tarkasteleminen
Kun ratkaisun tarkistus on valmis, analyysiraportin voi ladata selaimessa. Raportti on [!INCLUDE [pn-excel-short](../../includes/pn-excel-short.md)]-muotoinen, ja siinä on useita visualisointeja ja sarakkeita, jotka auttavat tunnistamaan jokaisen ratkaisussa havaitun ongelman vaikutuksen, tyypin ja sijainnin. Siinä on myös linkki yksityiskohtaiseen ohjeeseen, jolla ongelma voidaan ratkaista. 

1. Valitse vasemmassa ruudussa **Ratkaisut**.
2. Valitse sen hallitsemattoman ratkaisun vieressä, jonka ratkaisun tarkistustoiminnon raportin haluat ladata, **…**, osoita **Ratkaisun tarkistustoiminto** -kohtaa ja valitse sitten **Lataa viimeisimmät tulokset palvelimesta**.  
3. Ratkaisun tarkistustoiminnon zip-tiedosto ladataan selaimen määrittämään kansioon.

Yhteenveto raportin sarakkeista:

|Raporttikenttä |Kuvaus  |Koskee osia   |
|---------|---------|---------|
|Ongelma     |   Ratkaisun havaitseman ongelman otsikko.      | Kaikki        |
|Luokka     | Havaitun ongelman luokitus, kuten **suorituskyky**, **käyttö** tai **tuettavuus**.      |  Kaikki       |
|Vakavuusaste     | Osoittaa havaitun ongelman mahdollisen vaikutuksen. Käytettävissä on seuraavat vaikutustyypit: **Korkea**, **Keskisuuri**, **Alhainen**, **Tiedoksi**.         |  Kaikki       |
|Ohjeet     |  Linkki artikkeliin, jossa käsitellään ongelmaa, sen vaikutusta ja suositeltua ratkaisua. toimintoja.       |  Kaikki       |
|Osa     |  Ratkaisun osa, jossa ongelma havaittiin.        |   Kaikki      |
|Location     |  Sen osan sijainti ja/tai lähdetiedosto, jossa havaittu ongelma tapahtui. Se voi olla esimerkiksi kokoonpano tai JavaScript-tiedoston nimi.        |  Kaikki       |
|Rivinumero     |  Ongelman rivinumeroviittaus siinä verkkoresurssiosassa, jota ongelma koskee.       |  WWW-resurssit       |
|Moduuli     | Sen moduulin nimi, jossa ongelma havaittiin kokoonpanossa.     |   Laajennus tai mukautettu työnkulun aktiviteetti      |
|Tyyppi     | Kokoonpanossa havaitun ongelman tyyppi.        | Laajennus tai mukautettu työnkulun aktiviteetti        |
|Jäsen     |  Kokoonpanossa havaitun ongelman jäsen.      | Laajennus tai mukautettu työnkulun aktiviteetti        |
|Lauseke     | Koodilauseke tai määritys, joka aiheutti ongelman.        |  Kaikki       |
|Kommentit     | Tietoja ongelmasta mukaan lukien tarkasta ratkaisuohjeet.         |  Kaikki       |



## <a name="best-practice-rules-used-by-solution-checker"></a>Ratkaisun tarkistustoiminnon käyttämät parhaiden käytäntöjen säännöt


|Ratkaisun osa  |Säännön nimi  |Säännön kuvaus  |
|---------|---------|---------|
|Laajennus tai työnkulun aktiviteetti   | [il-specify-column](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-specify-column&client=PAChecker&source=featuredocs)  | Älä valitse kaikki sarakkeita Dynamics 365 for Customer Engagement -kyselyn ohjelmointirajapinnoilla.     |
|Laajennus tai työnkulun aktiviteetti   | [meta-remove-dup-reg](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-remove-dup-reg&client=PAChecker&source=featuredocs)     | Älä tee Dynamics 365 for Customer Engagement -laajennuksen rekisteröintejä kahdesti.     |
|Laajennus tai työnkulun aktiviteetti   | [il-turn-off-keepalive](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-turn-off-keepalive&client=PAChecker&source=featuredocs)   | Määritä KeepAlive-arvoksi epätosi, kun käytössä on Dynamics 365 for Customer Engagement -laajennuksen ulkoiset isännät.     |
|Laajennus tai työnkulun aktiviteetti   | [il-avoid-unpub-metadata](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-avoid-unpub-metadata&client=PAChecker&source=featuredocs)   | Älä nouda julkaisemattomia Dynamics 365 for Customer Engagement -metatietoja.     |
|Laajennus tai työnkulun aktiviteetti   | [il-avoid-batch-plugin](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-avoid-batch-plugin&client=PAChecker&source=featuredocs)   | Älä käytät eräpyyntötyyppejä Dynamics 365 Customer Engagementin laajennuksissa ja työnkulun aktiviteeteissa.    |
|Laajennus tai työnkulun aktiviteetti   | [meta-avoid-reg-no-attribute](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-avoid-reg-no-attribute&client=PAChecker&source=featuredocs)  | Sisällytä suodatusmääritteet Dynamics 365 for Customer Engagement -laajennuksen rekisteröinteihin.    |
|Laajennus tai työnkulun aktiviteetti   | [meta-avoid-reg-retrieve](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-avoid-reg-retrieve&client=PAChecker&source=featuredocs)  | Ole varovainen, kun käytät Retrieve- ja RetrieveMultiple-sanomille rekisteröityjä Dynamics 365 for Customer Engagement -laajennuksia.    |
|Laajennus tai työnkulun aktiviteetti   | [meta-remove-inactive](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-remove-inactive&client=PAChecker&source=featuredocs)    | Poista Dynamics 365 for Customer Engagementin passiiviset määritykset.    |
|Laajennus tai työnkulun aktiviteetti   | [Avoid using window.top](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-window-top&client=PAChecker&source=featuredocs)   | Älä käytä window.topia.    |
|Laajennus tai työnkulun aktiviteetti   | [il-meta-avoid-crm2011-depr-message](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-avoid-crm2011-depr-message&client=PAChecker&source=featuredocs)  | Älä käytä Microsoft Dynamics CRM 2011:n vanhentuneita sanomia.     |
|Laajennus tai työnkulun aktiviteetti   | [meta-avoid-crm4-event](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-avoid-crm4-event&client=PAChecker&source=featuredocs) | Älä käytä Microsoft Dynamics CRM 4.0 -laajennuksen rekisteröintivaihetta.    |
|Laajennus tai työnkulun aktiviteetti   | [il-avoid-specialized-update-ops](http://go.microsoft.com/fwlink/?LinkID=398563&error=il-avoid-specialized-update-ops&client=PAChecker&source=featuredocs)  | Älä käytä erityisiä päivitystoimintopyyntöjä Dynamics 365 for Customer Engagementissa.        |
|WWW-resurssit  | [web-use-async](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-async&client=PAChecker&source=featuredocs)  |  Käsittele HTTP- ja HTTPS-resursseja asynkronisesti.   |
|WWW-resurssit  | [meta-remove-invalid-form-handler](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-remove-invalid-form-handler&client=PAChecker&source=featuredocs)  | Korjaa tai poista virheelliset Dynamics 365 for Customer Engagementin lomaketapahtumarekisteröinnit.   |
|WWW-resurssit  | [meta-remove-orphaned-form-element](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-remove-orphaned-form-element&client=PAChecker&source=featuredocs)  | Korjaa tai poista yhteydettömät Dynamics 365 for Customer Engagementin lomaketapahtumarekisteröinnit.   |
|WWW-resurssit  | [web-avoid-modals](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-modals&client=PAChecker&source=featuredocs)  | Älä käytä modaalisia valintaikkunoita.   |
|WWW-resurssit  | [web-avoid-crm2011-service-odata](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-crm2011-service-odata&client=PAChecker&source=featuredocs)   | Älä käytä kohteena Microsoft Dynamics CRM 2011 OData 2.0 -päätepistettä.     |
|WWW-resurssit  | [web-avoid-crm2011-service-soap](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-crm2011-service-soap&client=PAChecker&source=featuredocs)  | Älä käytä kohteena Microsoft Dynamics CRM 2011 -SOAP-palveluja.   |
|WWW-resurssit  | [web-avoid-browser-specific-api](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-browser-specific-api&client=PAChecker&source=featuredocs) | Älä käytä Internet Explorerin vanhoja ohjelmointirajapintoja tai selainlaajennuksia.   |
|WWW-resurssit  | [web-avoid-2011-api](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-2011-api&client=PAChecker&source=featuredocs)  | Älä käytä vanhentunutta Microsoft Dynamics CRM 2011 -objektimallia.  |
|WWW-resurssit  | [web-use-relative-uri](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-relative-uri&client=PAChecker&source=featuredocs)   | Älä käytä absoluuttisia CDS sovelluksille -päätepisteen URL-osoitteita.    |
|WWW-resurssit  | [web-use-client-context](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-client-context&client=PAChecker&source=featuredocs)  | Käytä asiakasohjelmakonteksteja.   |
|WWW-resurssit  | [web-use-dialog-api-param](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-dialog-api-param&client=PAChecker&source=featuredocs)   | Käytä valintaikkunan ohjelmointirajapinnan parametreja.   |
|WWW-resurssit  | [web-use-org-setting](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-org-setting&client=PAChecker&source=featuredocs)   | Käytä organisaation asetuksia.   |
|WWW-resurssit  | [web-use-grid-api](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-use-grid-api&client=PAChecker&source=featuredocs)   | Käytä ruudukon ohjelmointirajapintoja.    |
|WWW-resurssit  | [web-avoid-isActivityType](http://go.microsoft.com/fwlink/?LinkID=398563&error=web-avoid-isActivityType&client=PAChecker&source=featuredocs)   | Korvaa Xrm.Utility.isActivityType-menetelmä uudella Xrm.Utility.getEntityMetadata-menetelmällä äläkä käytä valintanauhasääntöjä.    |
|WWW-resurssit  | [meta-avoid-silverlight](http://go.microsoft.com/fwlink/?LinkID=398563&error=meta-avoid-silverlight&client=PAChecker&source=featuredocs)   | Silverlight-verkkoresurssin käyttö on vanhentunut.   |


## <a name="see-also"></a>Katso myös
[PowerAppsin kokeellisten ja esiversion ominaisuuksien esittely](../canvas-apps/working-with-experimental.md) <br/>
[PowerApps-ratkaisujen ohjeet ja parhaat käytännöt](https://docs.microsoft.com/dynamics365/customer-engagement/guidance/)

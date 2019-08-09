---
title: Ratkaisun tarkistustoimintoon liittyvät yleiset ongelmat ja niiden ratkaisut | Microsoft Docs
description: ' Luettelo ratkaisun tarkistustoiminnossa olevista yleisistä ongelmista ja niiden ratkaisuista'
keywords: ''
ms.date: 02/11/2019
ms.service: powerapps
ms.custom:
  - ''
ms.topic: article
ms.assetid: caa4e3f2-9700-49b8-87ed-8a68e8878b02
author: jowells1
ms.author: jowells
manager: austinj
ms.reviewer: null
robots: 'noindex,nofollow'
search.audienceType:
  - developer
search.app:
  - PowerApps
  - D365CE
---
# <a name="common-issues-and-resolutions-for-solution-checker"></a>Ratkaisun tarkistustoimintoon liittyvät yleiset ongelmat ja niiden ratkaisut

Tässä artikkelissa on luettelo yleisistä ongelmista, joita voi esiintyä ratkaisun tarkistustoimintoa käytettäessä. Niihin annetaan mahdollisuuksien mukaan myös ratkaisuehdotuksia.

## <a name="youre-unable-to-use-solution-checker-to-run-analysis-or-download-results"></a>Ratkaisun tarkistusta ei voi käyttää analyysin suorittamiseen tai tulosten lataamiseen

Pian sen jälkeen, kun ratkaisun tarkistusohjelma on lähettänyt pyynnön suorittaa analyysi tai ladata tulokset, toiminto ei ole valmis ja näkyviin tulee virhesanoma, kuten:

> *"**[Ratkaisun nimi]** -ratkaisun tarkistusta ei voitu suorittaa. Yritä uudelleen."*

Ratkaisun tarkistus yrittää aina, kun mahdollista, palauttaa tietyn virhesanoman ja linkin mahdollisiin syy- ja ratkaisuvaiheisiin. Jos haluat lisätietoja, valitse **Lue lisää**.

![Virhesanomapalkki](media/solution-checker-missing-roles-error.png)

Analyysin taustakäsittelyn aikana ilmenevät epäonnistumiset eivät onnistu **Ei voitu suorittaa loppuun** -tilassa ja palauttavat virhe sanoman PowerApps-portaalissa sekä lähettävät sähköposti-ilmoituksen pyytäjälle. 

![Virheen tila](media/solution-checker-exception-status.png)

Portaali-ilmoituksen valitseminen linkittyy tähän yleisten ongelmien sivuun lisävianmääritystä varten. Jos jokin näistä yleisistä ongelmista ei ratkaise ongelmaa, myös viitenumero palautetaan. Anna tämä viite Microsoft-tukeen lisätutkimuksia varten.

![Virheilmoitus](media/solution-checker-failure-notification.png)

## <a name="solution-checker-fails-due-to-unsupported-version-of-powerapps-checker"></a>Ratkaisun tarkistustoiminnossa on vika tukemattoman PowerApps-tarkistuksen version vuoksi

Ratkaisun tarkistustoiminto on otettu käyttöön PowerApps-tarkistussovelluksella.  Jos käytössäsi on PowerApps-tarkistussovelluksen versio **1.0.0.47** tai sitä aikaisempi versio, ratkaisun tarkistustoimintoa ei suoriteta loppuun saakka. Päivitä PowerApps-tarkistuksen versio. Käytä [!INCLUDE [pn-dyn-365-admin-center](../../includes/pn-dyn-365-admin-center.md)]ta. 

Jos asennettuna on kuitenkin PowerApps-tarkistuksen versiota **1.0.0.45** edeltävä versio, ratkaisu kannattaa poistaa ja asentaa sitten uudelleen. Äskettäisten rakenteiden muutosten vuoksi päivitys voi epäonnistua, jos PowerApps-tarkistuksen päivitettävä versio on **1.0.0.45** tai sitä aikaisempi versio.

Jos haluat säilyttää ratkaisun tarkistustoiminnon aikaisemmat tulokset, vie edellisen ajon tulokset tai kaikki ratkaisun tarkistustoiminnon tiedot [Tietojen vieminen Exceliin](../../user/export-data-excel.md) -toiminnot. Tällä tavoin voidaan viedä seuraavien entiteettien tiedot:

- Analyysin komponentti
- Analyysityö
- Analyysitulos
- Analyysin tulostieto

### <a name="how-to-uninstall-powerapps-checker"></a>PowerApps-tarkistussovelluksen asennuksen poistaminen

PowerApps-tarkistusratkaisun asennuksen poistaminen:

1. Avaa PowerApps-portaali järjestelmänvalvojana tai järjestelmän mukauttajana siirtymällä osoitteeseen https://web.powerapps.com/environments.
2. Valitse **ratkaisut**.
3. Valitse **PowerApps-tarkistus** ja valitse sitten ratkaisujen työkalurivillä **Poista**.

### <a name="how-to-install-powerapps-checker"></a>PowerApps-tarkistussovelluksen asentaminen

Voit asentaa PowerApps-tarkistuksen takaisin Common Data Service -ympäristöön seuraavasti:

1. Avaa PowerApps-portaali järjestelmänvalvojana tai järjestelmän mukauttajana siirtymällä osoitteeseen https://web.powerapps.com/environments.
2. Valitse **ratkaisut**.
3. Valitse ensin ratkaisujen työkalurivillä **Ratkaisun tarkistustoiminto** ja sitten **Asenna**.

## <a name="solution-checker-cant-access-organizations-in-administration-mode"></a>Ratkaisun tarkistamista ei voi käyttää organisaation hallintatilassa

[Hallintatilaan](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/manage-sandbox-instances#administration-mode) sijoitetut organisaatiot rajoittavat pääsyn tarkoituksellisesti vain sellaisille käyttäjille, joilla on järjestelmänvalvojan ja järjestelmän mukauttajan roolit. Koska PowerApps-tarkistussovelluksen identiteettiä ei ole määritetty oletusarvoisesti, se ei voi käyttää tässä tilassa toimivia organisaatioita.

Jotta voisit käyttää ratkaisun tarkistusta tässä organisaatiossa, hallintatila on poistettava käytöstä.

### <a name="how-to-disable-administration-mode"></a>Miten hallintatila poistetaan käytöstä

Organisaation ilmentymän hallintatilan poistaminen käytöstä:

1. Avaa Dynamics 365 for Customer Engagement -sovelluksen esiintymän valitsimeen: https://port.crm.dynamics.com/G/Instances/InstancePicker.aspx.
2. Valitse organisaation esiintymä, jossa ratkaisun tarkistustoiminnon suorittamisessa oli ongelmia.
3. Valitse **JÄRJESTELMÄNVALVOJA**.<br/>
![Esiintymän järjestelmänvalvoja](media/solution-checker-instance-admin.png)

4. Tyhjennä **Ota hallintatila käyttöön** ja valitse sitten **Tallenna**.<br/>
![Järjestelmänvalvojan tilan poistaminen käytöstä](media/solution-checker-instance-disable-admin-mode.png)

5. Suorita ratkaisun tarkistustoiminto uudelleen.

## <a name="solution-checker-fails-due-to-missing-security-roles"></a>Ratkaisun tarkistaminen epäonnistuu puuttuvien käyttöoikeusroolien vuoksi

Ratkaisun tarkistussovelluksen käyttäjän on määritettävä kaksi käyttöoikeusroolia, jotta he voivat antaa tarvittavat oikeudet kommunikoida Common Data Service -organisaation kanssa. Jos kumpaakaan näistä rooleista ei ole määritetty **PowerApps-tarkistus**-käyttäjäksi, analysointi- ja lataustulosten suorittaminen sekä peruutuksen suorittaminen epäonnistuu. Näin tapahtuu useimmiten silloin, kun asiakkaiden käytössä on automaatio, joka poistaa käyttöoikeusroolit odottamattomilta käyttäjiltä. Seuraavat käyttöoikeusroolit sisältävät vähintään pakolliset oikeudet:

- Vie mukautukset
- Ratkaisun tarkistustoiminto

### <a name="how-to-assign-missing-security-roles"></a>Puuttuvien turvallisuusroolien määrittäminen

Puuttuvien käyttöoikeusroolien määrittäminen PowerApps-tarkistuksen käyttäjälle:

1. Avaa Common Data Service -organisaatio ja siirry kohtaan **Asetukset** > **Suojaus** > **Käyttäjät**.
2. Valitse **PowerApps-tarkistus**-käyttäjä käyttäjien luettelosta.
3. Valitse komentopalkissa **ROOLIEN HALLINTA**.
4. Valitse **Vie mukautukset**- ja **Ratkaisun tarkistus** -roolien valintaruudut ja valitse sitten **OK**.<br/>
![Pakolliset käyttöoikeusroolit](media/solution-checker-required-roles.png)

5. Suorita ratkaisun tarkistustoiminto uudelleen.

## <a name="solution-checker-fails-due-to-restricted-access-mode"></a>Ratkaisun tarkistus epäonnistuu rajoitettujen käyttöoikeuksien vuoksi

Ratkaisun tarkistuksen sovelluskäyttäjä edellyttää **ei-vuorovaikutteista** tai **luku-kirjoitus**-käyttöoikeustilaa, jotta se voisi olla yhteydessä Common Data Service -organisaatioon. Jos käyttötila on muutettu toiseksi arvoksi, kuten **Hallinnollinen**, yritys suorittaa analyysi, ladata tuloksia ja suorittaa peruutus epäonnistuu.

Voit ratkaista ongelman päivittämällä **PowerApps-tarkistus**-sovelluksen käyttäjän, jolla on ei-vuorovaikutteinen käyttötila.

### <a name="how-to-update-user-access-mode"></a>Käyttöoikeustilan päivittäminen

Voit päivittää PowerApps-tarkistuspalvelun käyttötilan seuraavasti:

1. Avaa Common Data Service -organisaatio ja siirry kohtaan **Asetukset** > **Suojaus** > **Käyttäjät**.
2. Valitse **PowerApps-tarkistus**-käyttäjä käyttäjien luettelosta ja avaa sitten käyttäjälomake kaksoisnapsauttamalla.
3. Siirry lomakkeen **Hallinta** > **Asiakasohjelman käyttöoikeuden (CAL) tiedot** -osaan.
4. Valitse avattavasta valikosta **Ei-vuorovaikutteinen** **Käyttötila**.<br/>
![Käyttöoikeus](media/solution-checker-access-mode.png)

5. Tallenna ja sulje käyttäjälomake.
6. Suorita ratkaisun tarkistustoiminto uudelleen.

## <a name="solution-checker-fails-due-to-disabled-first-party-application-in-aad"></a>Ratkaisun tarkistaminen epäonnistuu, koska ensimmäisen osapuolen sovellus on poistettu käytöstä AAD:ssä.

Ratkaisun tarkistuksen käyttämää ensimmäisen osapuolen yrityssovelluksen identiteettiä (PowerApps-Advisor) ei tule poistaa käytöstä Azure Active Directory (AAD). Jos käyttäjä ei ole käytössä, hän ei voi todentaa pyytäessään Common Data Service -siirtotietunnuksia ja muita tarvittavia resurssitoimittajia pyynnön esittäneen käyttäjän puolesta. 

Tarkista alla olevien ohjeiden mukaisesti, että sovelluksen tunnistetietoja ei ole poistettu käytöstä AAD:ssä ja ota sovellus tarvittaessa käyttöön.

### <a name="how-to-verify-andor-modify-application-enabled-status"></a>Sovelluksen käytössä-tilan tarkistaminen ja/tai muokkaaminen

PowerApps-Advisor Enterprise Application Identity -tilan tarkistaminen ja/tai muokkaaminen

1. Voit käyttää vuokraajaasi [Azure Active Directory (AAD)-portaalissa](https://aad.portal.azure.com/).
2. Siirry **Enterprise-sovelluksiin**.
3. Valitse **Kaikki sovellukset** ja hae **PowerApps-Advisor**.<br/>
![Haku PowerApps-Advisor-sovelluksesta](media/solution-checker-search-advisor-app.png)

4. Voit tarkastella sovelluksen tietoja valitsemalla **PowerApps-Advisor**.
5. Valitse **Ominaisuudet**.
6. Tarkista tila, jossa **käyttäjät voivat sisäänkirjautua**. Jos **Ei**, sovellus on poistettu käytöstä.<br/>
![Käytöstä poistettu Enterprise-sovellus](media/solution-checker-disabled-app.png)

7. Valitse radio-ohjausobjekti, jos haluat vaihtaa arvoksi **Kyllä**. Tämä ottaa sovelluksen käyttöön.<br/>
![Ota käyttöön PowerApps-Advisor-sovellus](media/solution-checker-enable-app.png)

8. Valitse **Tallenna**. Sovellus on nyt käytössä. Sinun on ehkä odotettava muutama minuutti, ennen kuin muutos etenee.
9. Suorita ratkaisun tarkistustoiminto uudelleen.

> [!IMPORTANT]
> Jos haluat muokata yrityssovelluksia Azure Active Directoryssa (AAD), sinulla on oltava järjestelmänvalvojan oikeudet.

## <a name="solution-checker-fails-to-export-solutions-with-draft-business-process-flow-components"></a>Ratkaisun tarkistus ei vie ratkaisuja, joissa on luonnos liiketoimintaprosessien vuon osista

Jos ratkaisu sisältää luonnostilassa olevan liiketoimintaprosessin vuon osan, jota ei ole aiemmin aktivoitu, ratkaisun tarkistus ei vie ratkaisua analysoitavaksi. Tämä virhe ei ole ainutlaatuinen ratkaisun tarkistukselle, ja se johtuu liiketoimintaprosessivirrasta, joka on riippuvainen taustayhteyden (mukautetun) kokonaisuuden komponentista, joka ei synny, ennen kuin liiketoimintaprosessivirta aktivoidaan ensimmäistä kertaa. Tämä ongelma voi ilmetä myös, jos liiketoimintaprosessin virtaus aktivoidaan Ratkaisunhallinnasta.

Viittaus tieto [Tietämyskannan artikkeli #4337537: Virheellinen vienti - Liiketoimintaprosessientiteetti puuttui](https://support.microsoft.com/en-hk/help/4337537/invalid-export-business-process-entity-missing) tietoja ongelmasta ja ratkaistavista vaiheista.

## <a name="solution-checker-fails-to-export-patched-solutions"></a>Ratkaisun tarkistus ei voi viedä paikattuja ratkaisuja

Jos ratkaisussa on käytetty [korjaustiedostoa](https://docs.microsoft.com/powerapps/developer/common-data-service/create-patches-simplify-solution-updates), ratkaisun tarkistustoiminto ei vie ratkaisua analysoitavaksi. Kun ratkaisussa käytetään korjaustiedostoa, alkuperäinen ratkaisu lukitaan. Sitä ei voi silloin muuttaa eikä viedä niin kauan kuin organisaatiossa on riippuvaisia korjaustiedostoja, jotka tunnistavat ratkaisun pääratkaisuksi.

Voit ratkaista tämän ongelman kloonaamalla ratkaisun siten, että kaikki ratkaisuun liittyvät korjaustiedostot siirretään juuri luotuun ratkaisuun. Tämä avaa ratkaisun ja sallii ratkaisun viennin järjestelmästä.  Lisätietoja on kohdassa [Ratkaisun kloonaaminen](use-segmented-solutions-patches-simplify-updates.md#clone-a-solution).

## <a name="solution-checker-will-not-analyze-empty-solutions"></a>Ratkaisun tarkistustoiminto ei analysoi tyhjiä ratkaisuja

Jos ratkaisun tarkistus vie ratkaisun, joka ei sisällä analysoitavia osia, se lopettaa jatkokäsittelyn ja harkitsee virheen suorittamista. Varmista, että ratkaisun tarkistus -analyysiin lähetetty valittu ratkaisu sisältää vähintään yhden osan.

## <a name="solution-checker-fails-to-export-large-solutions"></a>Ratkaisun tarkistus ei voi viedä suuria ratkaisuja

Pääskenaario suuren ratkaisun viennin epäonnistumisesta Common Data Service -ympäristöstä sisältää aikakatkaisun poikkeuksen vientipyynnössä. Tämä tapahtuu, jos pyyntö ylittää 20 minuuttia. Suuria ratkaisuja, kuten oletusratkaisuja, ei ehkä ehditä viedä tämän aikarajan kuluessa eikä tarkistusta suoriteta loppuun saakka. Jos ratkaisun tarkistus havaitsee aikakatkaisun viennin aikana, se yrittää käsitellä työn kolme kertaa ennen epäonnistumista, joten voi kestää yli tunnin, ennen kuin saat virheilmoituksen.

Ongelma kierretään luomalla pienempiä ratkaisuja, joissa on vähemmän analysoitavia osia. Jos ratkaisun suuri tiedostokoko johtuu useista laajennuskokoonpanon osista, katso lisätietoja ohjeesta [Mukautetun kokoonpanon kehityksen optimointi](../../developer/common-data-service/best-practices/business-logic/optimize-assembly-development.md). 

> [!IMPORTANT]
> Voit vähentää virheellisten esiintymien määrää varmistamalla, että olet lisännyt riippuvaiset mukautukset. Kun luot ratkaisun ja lisäät nämä osat, sisällytä seuraavat:
> - Kun lisäät laajennuksia, sisällytä laajennuksen SDK-viestin käsittelyvaiheet.
> - Kun lisäät entiteettilomakkeita, sisällytä lomaketapahtumiin liitetyt JavaScript-verkkoresurssit.  
> - Kun lisäät JavaScript-verkkoresursseja, sisällytä mahdolliset riippuvaiset JavaScript-verkkoresurssit.
> - Kun lisäät HTML-verkkoresursseja, sisällytä mahdolliset HTML-verkkoresurssissa määritetyt riippuvaiset komentosarjat.
> - Kun lisäät mukautettuja työnkulkuja, sisällytä työnkulussa käytetty kokoonpano.

## <a name="line-number-references-for-issues-in-html-resources-with-embedded-javascript-are-not-correct"></a>Rivinumeroviittaukset upotettua JavaScriptiä sisältäviin HTML-resursseihin ovat virheellisiä 

Kun HTML-verkkoresursseja käsitellään ratkaisun tarkistustoiminnolla, HTML-verkkoresurssi käsitellään erillään HTML-verkkoresurssiin sisältyvästä JavaScriptistä. Tämän vuoksi HTML-verkkoresurssin `<script>`-osassa olevan rikkomuksen rivinumero on virheellinen.

## <a name="web-unsupported-syntax-issue-for-web-resources"></a>Verkkoresurssin web-unsupported-syntax-ongelma

Ratkaisun tarkistustoiminto ei tue versiota ECMAScript 6 (2015) ja sitä uudempia versioita. Kun ratkaisun tarkistustoiminto analysoi JavaScriptiä, jossa on käytössä ECMAScript 6 tai sitä uudempi versio, verkkoresurssin web-supported-syntax-ongelma ilmoitetaan.  

## <a name="multiple-violations-reported-for-plug-ins-and-workflow-activities-based-on-call-scope"></a>Laajennuksille ja työnkulun aktiviteeteille raportoitiin useita virheitä kutsun vaikutusalueen perusteella

Ratkaisun tarkistustoiminto aloittaa analyysin IPlugin-liittymän käyttöönotosta laajennuksen ja työnkulun aktiviteetin säännöille, joissa virhe koskee vain kutsun kontekstia. Tarkistustoiminto kulkee kutsukaavion läpi ja havaitsee kyseisen käyttöönoton vaikutusalueen virheet.  Joissakin tapauksissa virheen havaitsemissijaintiin vie useita kutsupolkuja.  Koska ongelma koskee kutsun vaikutusaluetta, työkalu voi raportoida kyseisen vaikutusalueen perusteella. Näin saadaan parempi kuva vaikutuksesta erillisten sijaintien sijaan. Tulos voi olla, että useat virheet viittaavat yhteen sijaintiin, joka on korjattava.

## <a name="see-also"></a>Katso myös
[Parhaat käytännöt ja ohjeet Common Data Serviceen](../../developer/common-data-service/best-practices/index.md)<br/>
[Mallipohjaisten sovellusten parhaat käytännöt ja ohjeet](../../developer/model-driven-apps/best-practices/index.md)<br/>

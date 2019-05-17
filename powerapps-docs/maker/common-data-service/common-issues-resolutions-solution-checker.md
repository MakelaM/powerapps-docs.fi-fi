---
title: Ratkaisun tarkistustoimintoon liittyvät yleiset ongelmat ja niiden ratkaisut | Microsoft Docs
description: ' Luettelo ratkaisun tarkistustoiminnossa olevista yleisistä ongelmista ja niiden ratkaisuista'
keywords: ''
ms.date: 02/11/2019
ms.service:
  - powerapps
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

## <a name="solution-checker-runs-fail-due-to-powerapps-checker-version-installed"></a>Ratkaisun tarkistustoiminnossa on vika asennetun PowerApps-tarkistuksen version vuoksi
Ratkaisun tarkistustoiminto sisältyy PowerApps-tarkistusratkaisuun.  Jos käytössäsi on PowerApps-tarkistuksen versio 1.0.0.47 tai sitä aikaisempi versio, ratkaisun tarkistustoimintoa ei suoriteta loppuun saakka. Päivitä PowerApps-tarkistuksen versio. Käytä [!INCLUDE [pn-dyn-365-admin-center](../../includes/pn-dyn-365-admin-center.md)]ta. 

Jos asennettuna on kuitenkin PowerApps-tarkistuksen versiota 1.0.0.45 edeltävä versio, ratkaisu kannattaa poistaa ja asentaa sitten uudelleen. Äskettäisten rakenteiden muutosten vuoksi päivitys voi epäonnistua, jos PowerApps-tarkistuksen päivitettävä versio on 1.0.0.45 tai sitä aikaisempi versio.

Jos haluat säilyttää ratkaisun tarkistustoiminnon aikaisemmat tulokset, vie edellisen ajon tulokset tai kaikki ratkaisun tarkistustoiminnon tiedot [Tietojen vieminen Exceliin](../../user/export-data-excel.md) -toiminnot. Tällä tavoin voidaan viedä seuraavien entiteettien tiedot:

- Analyysin komponentti
- Analyysityö
- Analyysitulos
- Analyysin tulostieto

### <a name="delete-powerapps-checker"></a>PowerApps-tarkistuksen poistaminen

PowerApps-tarkistusratkaisun poistaminen:

1. Avaa PowerApps-portaali järjestelmänvalvojana tai järjestelmän mukauttajana siirtymällä osoitteeseen https://web.powerapps.com/environments.
2. Valitse **ratkaisut**.
3. Valitse **PowerApps-tarkistus** ja valitse sitten ratkaisujen työkalurivillä **Poista**.

### <a name="add-powerapps-checker"></a>PowerApps-tarkistuksen lisääminen

PowerApps-tarkistuksen lisääminen takaisin Common Data Service -ympäristöön:

1. Avaa PowerApps-portaali järjestelmänvalvojana tai järjestelmän mukauttajana siirtymällä osoitteeseen https://web.powerapps.com/environments.
2. Valitse **ratkaisut**.
3. Valitse ensin ratkaisujen työkalurivillä **Ratkaisun tarkistustoiminto** ja sitten **Asenna**.

## <a name="runs-on-large-solutions-fail"></a>Suurten ratkaisujen ajot epäonnistuvat

Jos ratkaisu on liian suuri seurauksena voi olla pari skenaariota. Skenaarioita käsitellään tarkemmin jäljempänä. Kummankin skenaarion ratkaisu on luoda pienempiä ratkaisuja, joissa on vähemmän analysoitavia osia. Jos ratkaisun suuri tiedostokoko johtuu laajennuskokoonpanon osista, katso lisätietoja ohjeesta [Mukautetun kokoonpanon kehityksen optimointi](../../developer/common-data-service/best-practices/business-logic/optimize-assembly-development.md).

Ratkaisun tarkistustoiminto ei tarkista ratkaisuja seuraavissa skenaarioissa:
- Ratkaisun tiedostokoon rajoittaminen kiinteästi 30 megatavuun.  
- 10 minuutin aikakatkaisuraja vietäessä ratkaisua Common Data Service -ympäristöstä. Suuria ratkaisuja, kuten oletusratkaisuja, ei ehkä ehditä viedä tämän aikarajan kuluessa eikä tarkistusta suoriteta loppuun saakka. Ratkaisun tarkistustoiminto yrittää käsitellä työn kolme kertaa ennen epäonnistumista, joten voi kestää yli 30 minuuttia, ennen kuin saat virheilmoituksen.

Voit ratkaista nämä ongelmat luomalla tai tarkistamalla pienempiä analysoitavia ratkaisuja. Voit vähentää virheellisten esiintymien määrää varmistamalla, että olet lisännyt riippuvaiset mukautukset. Kun luot ratkaisun ja lisäät nämä osat, sisällytä seuraavat:

- Kun lisäät laajennuksia, sisällytä laajennuksen SDK-viestin käsittelyvaiheet.
- Kun lisäät entiteettilomakkeita, sisällytä lomaketapahtumiin liitetyt JavaScript-verkkoresurssit.  
- Kun lisäät JavaScript-verkkoresursseja, sisällytä mahdolliset riippuvaiset JavaScript-verkkoresurssit.
- Kun lisäät HTML-verkkoresursseja, sisällytä mahdolliset HTML-verkkoresurssissa määritetyt riippuvaiset komentosarjat.
- Kun lisäät mukautettuja työnkulkuja, sisällytä työnkulussa käytetty kokoonpano.

## <a name="solution-checker-run-or-download-results-dont-complete"></a>Ratkaisun tarkistustoiminnon ajo tai tulosten lataus keskeytyy 
Pian sen jälkeen kun ratkaisun tarkistustoiminto keskeytyy, näkyviin tulee sanoma, jonka mukaan<br />
*RATKAISUN NIMI* -ratkaisun tarkistusta ei voitu suorittaa ja sen suorittamista on yritettävä uudelleen. <br />
![Seuraavaa ratkaisua ei voitu suorittaa:](media/solution-checker-werent-able-to-run.png)

Tämän ongelman syynä on se, että organisaatio on **järjestelmänvalvojan tilassa**, eikä ratkaisun tarkistustoiminto voi tarkistaa käyttäjän käyttöoikeuksia pyynnön suorituksen aikana. Voit ratkaista tämän ongelman poistamalla järjestelmänvalvojan tilan käytöstä. 

### <a name="disable-administration-mode-for-an-instance"></a>Esiintymän järjestelmänvalvojan tilan poistaminen käytöstä
1. Siirry Dynamics 365 for Customer Engagement -esiintymän valitsimeen: https://port.crm.dynamics.com/G/Instances/InstancePicker.aspx.
2. Valitse esiintymä, jossa ratkaisun tarkistustoiminnon suorittamisessa oli ongelmia.
3. Valitse **JÄRJESTELMÄNVALVOJA**.<br />
![Esiintymän järjestelmänvalvoja](media/solution-checker-instance-admin.png)

4. Poista **Ota järjestelmänvalvojan tila käyttöön** -asetuksen valinta. <br />
![Järjestelmänvalvojan tilan poistaminen käytöstä](media/solution-checker-instance-disable-admin-mode.png)

5. Suorita ratkaisun tarkistustoiminto uudelleen.

## <a name="solution-checker-will-not-process-patched-solutions"></a>Ratkaisun tarkistustoiminto ei käsittele korjaustiedostoja sisältäviä ratkaisuja

Jos ratkaisussa on käytetty [korjaustiedostoa](https://docs.microsoft.com/powerapps/developer/common-data-service/create-patches-simplify-solution-updates), ratkaisun tarkistustoiminto ei vie ratkaisua analysoitavaksi. Kun ratkaisussa käytetään korjaustiedostoa, alkuperäinen ratkaisu lukitaan. Sitä ei voi silloin muuttaa eikä viedä niin kauan kuin organisaatiossa on riippuvaisia korjaustiedostoja, jotka tunnistavat ratkaisun pääratkaisuksi.

Voit ratkaista tämän ongelman kloonaamalla ratkaisun siten, että kaikki ratkaisuun liittyvät korjaustiedostot siirretään juuri luotuun ratkaisuun. Tämä avaa ratkaisun ja sallii ratkaisun viennin järjestelmästä. Lisätietoja: [Ratkaisun kloonaaminen](use-segmented-solutions-patches-simplify-updates.md#clone-a-solution)

## <a name="line-number-references-for-issues-in-html-resources-with-embedded-javascript-are-not-correct"></a>Rivinumeroviittaukset upotettua JavaScriptiä sisältäviin HTML-resursseihin ovat virheellisiä 

Kun HTML-verkkoresursseja käsitellään ratkaisun tarkistustoiminnolla, HTML-verkkoresurssi käsitellään erillään HTML-verkkoresurssiin sisältyvästä JavaScriptistä. Tämän vuoksi HTML-verkkoresurssin `<script>`-osassa olevan rikkomuksen rivinumero on virheellinen.

## <a name="web-unsupported-syntax-issue-for-web-resources"></a>Verkkoresurssin web-unsupported-syntax-ongelma

Ratkaisun tarkistustoiminto ei tue versiota ECMAScript 6 (2015) ja sitä uudempia versioita. Kun ratkaisun tarkistustoiminto analysoi JavaScriptiä, jossa on käytössä ECMAScript 6 tai sitä uudempi versio, verkkoresurssin web-supported-syntax-ongelma ilmoitetaan.  

## <a name="multiple-violations-reported-for-plug-ins-and-workflow-activities-based-on-call-scope"></a>Laajennuksille ja työnkulun aktiviteeteille raportoitiin useita virheitä kutsun vaikutusalueen perusteella

Ratkaisun tarkistustoiminto aloittaa analyysin IPlugin-liittymän käyttöönotosta laajennuksen ja työnkulun aktiviteetin säännöille, joissa virhe koskee vain kutsun kontekstia. Tarkistustoiminto kulkee kutsukaavion läpi ja havaitsee kyseisen käyttöönoton vaikutusalueen virheet.  Joissakin tapauksissa virheen havaitsemissijaintiin vie useita kutsupolkuja.  Koska ongelma koskee kutsun vaikutusaluetta, työkalu voi raportoida kyseisen vaikutusalueen perusteella. Näin saadaan parempi kuva vaikutuksesta erillisten sijaintien sijaan. Tulos voi olla, että useat virheet viittaavat yhteen sijaintiin, joka on korjattava.

## <a name="see-also"></a>Katso myös
[Common Data Servicen parhaat käytännöt ja ohjeet](../../developer/common-data-service/best-practices/index.md)<br />
[Mallipohjaisten sovellusten parhaat käytännöt ja ohjeet](../../developer/model-driven-apps/best-practices/index.md)<br />

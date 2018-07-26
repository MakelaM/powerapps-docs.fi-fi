---
title: Common Data Service (CDS) for Appsin asiakastietoihin kohdistuviin DSR-pyyntöihin vastaaminen | Microsoft Docs
description: Ohjeet Common Data Service (CDS) for Appsin asiakastietoihin kohdistuviin DSR-pyyntöihin vastaamiseen
author: jamesol-msft
ms.reviewer: paulliew
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 04/23/2018
ms.author: jamesol
ms.openlocfilehash: b550d5fe7e36c36177fff017adcf9d9034c93dd4
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218046"
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-common-data-service-for-apps-customer-data"></a>Common Data Service for Appsin asiakastietoihin kohdistuviin DSR-pyyntöihin vastaaminen

## <a name="introduction-to-dsr-requests"></a>Johdanto DSR-pyyntöihin
Euroopan unionin (EU) yleinen tietosuoja-asetus (GDPR) antaa ihmisille (joita kutsutaan *asetuksessa rekisteröidyiksi*) oikeudet hallita henkilötietoja, joita työnantaja tai muu organisaatio tai virasto (jota kutsutaan *henkilötietorekisterinpitäjäksi* tai vain *rekisterinpitäjäksi*) on heistä kerännyt. GDPR määrittää henkilötiedoiksi hyvin yleisesti mitkä tahansa tiedot, jotka liittyvät tunnistettuun tai tunnistettavissa olevaan luonnolliseen henkilöön. GPDR antaa rekisteröidyille oikeuden seuraaviin toimiin heidän henkilökohtaisiin tietoihinsa liittyen:

* Kopion saaminen
* Korjausten pyytäminen
* Käsittelyn rajoittaminen
* Poistaminen
* Tietojen saaminen sähköisessä muodossa niin, että ne voidaan siirtää toiselle rekisterinpitäjälle

Rekisteröidyn rekisterinpitäjälle tekemää virallista pyyntöä ryhtyä toimiin henkilötietoihin liittyen kutsutaan rekisteröidyn tietopyynnöksi (Data Subject Rights, DSR).

Tässä asiakirjassa kerrotaan, miten Microsoft valmistautuu yleiseen tietosuoja-asetukseen. Annamme myös esimerkkejä toimenpiteistä, joihin voit ryhtyä täyttääksesi yleisen tietosuoja-asetuksen vaatimukset, kun käytät PowerApps-sovelluksia, Microsoft Flow’ta ja Common Data Service for Appsia. Opit, miten Microsoftin tuotteet, palvelut ja hallintatyökalut auttavat rekisterinpitäjiä etsimään Microsoftin pilvipalveluissa olevia henkilötietoja ja suorittamaan niille toimintoja rekisteröityjen tietopyyntöihin vastaamiseksi.

Tässä artikkelissa käsitellään seuraavia toimintoja:

* **Etsiminen**: Haku- ja etsintätyökalulla voit etsiä helpommin asiakastietoja, jotka saattavat olla rekisteröidyn tietopyynnön kohteena. Kun mahdollisesti oleelliset tiedostot on kerätty, voit suorittaa niille alla kuvattuja rekisteröidyn tietopyynnön toimintoja, jotta voit vastata pyyntöön. Voit myös tulla siihen tulokseen, että pyyntö ei täytä organisaatiosi vaatimuksia rekisteröidyn tietopyyntöön vastaamiselle.

* **Tarkistaminen**: hae Microsoftin pilvipalveluihin tallennetut henkilötiedot ja ota niistä pyydettäessä kopio, jonka voit toimittaa rekisteröidylle.

* **Korjaaminen**: tee henkilötietoihin muutoksia tai suorita niille muita pyydettyjä toimintoja soveltuvin osin.

* **Rajoittaminen**: Rajoita henkilötietojen käsittelyä joko poistamalla erilaisten verkkopalveluiden käyttöoikeuksia tai poistamalla halutut palvelut käytöstä, jos se on mahdollista. Voit poistaa tietoja Microsoftin pilvipalveluista ja tallentaa ne paikallisesti tai muuhun sijaintiin.

* **Poistaminen**: poista Microsoftin pilvipalveluihin tallennetut henkilötiedot pysyvästi.

* **Vieminen**: toimita rekisteröidyn henkilötietojen kopio sähköisessä (koneluettavassa) muodossa rekisteröidylle.

## <a name="cds-for-apps-customer-data"></a>Apps-asiakastietojen CDS

> [!IMPORTANT]
> Koskee sekä CDS for Appsia että aiempaa Common Data Service -versiota

CDS for Appsissa ja aiemmassa Common Data Service (CDS) -versiossa on erilliset prosessit henkilötietojen käsittelyyn.

Voit tunnistaa käyttämäsi CDS-ympäristön kirjautumalla sisään [PowerAppsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja suorittamalla seuraavat vaiheet:

1. Valitse ympäristösi avattavasta **Ympäristö**-luettelosta.
2. Napsauta tai napauta siirtymisruudussa **Tiedot** ja valitse sitten **Entiteetit**.

    Ympäristösi on CDS for Apps, jos luettelossa on seuraavat entiteetit:

    ![PowerApps-entiteettien luettelo](./media/common-data-service-gdpr-dsr-guide/powerapps-entities-list.png)

    Ympäristösi on CDS:n aiempi versio, jos luettelossa on seuraavat entiteetit:

    ![PowerAppsin vanhojen entiteettien luettelo](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-list.png)

Kun olet selvittänyt, minkä tyyppinen CDS-ympäristö sinulla on, noudata seuraavia vaiheita henkilötietojen tunnistamiseksi.

> [!NOTE]
> Käytössäsi voi olla tiettyjä ympäristöjä CDS for Appsissa ja muita ympäristöjä CDS:n aiemmassa versiossa, joten sinun on toistettava alla kuvattu prosessi jokaiselle organisaatiosi ympäristölle.

## <a name="user-personal-data-in-cds-for-apps"></a>Käyttäjän henkilötiedot CDS for Appsissa

### <a name="prerequisites"></a>Edellytykset
Sinun on luotava käyttäjät Office 365 -hallintakeskuksessa ja määritettävä heille asianmukaiset käyttöoikeudet ja suojausroolit, ennen kuin he voivat käyttää CDS for Appsia.

Office 365 -hallintakeskuksessa säilytetään ja ylläpidetään tiettyjä käyttäjän perushenkilötietoja, joita ovat esimerkiksi käyttäjänimi, käyttäjätunnus, puhelin, sähköposti ja osoite. Järjestelmänvalvoja voi päivittää näitä henkilötietoja vain Office 365 -hallintakeskuksessa. Nämä määritteet synkronoidaan sen jälkeen automaattisesti CDS for Appsiin. Järjestelmänvalvoja voi myös luoda mukautettuja määritteitä käyttäjien muiden henkilötietojen taltioimiseksi CDS for Apps -järjestelmän käyttäjäentiteettiin. Näitä määritteitä voidaan ylläpitää ja hallita manuaalisesti.

Kun käyttäjä poistetaan Office 365 -hallintakeskuksesta, käyttäjätietuetta ei poisteta automaattisesti CDS for Apps -järjestelmän käyttäjäentiteetistä. Näin estetään häiriöiden aiheuttaminen liiketoimintasovelluksiin, jotka voivat olla kriittisiä organisaation toiminnan jatkumisen kannalta. Käyttäjän tila CDS for Appsissa on Ei käytössä, mutta CDS for Apps -järjestelmänvalvojan tulee etsiä ja poistaa käyttäjän henkilötiedot CDS for Appsista sovelluksessa.

Alla luetellut etsintä-, korjaamis-, vienti- ja poistotoiminnot voi suorittaa vain käyttäjä, jolla on Office 365:n yleisen järjestelmänvalvojan rooli ja CDS-järjestelmänvalvojan rooli.

### <a name="discover"></a>Etsintä
Järjestelmänvalvojat voivat luoda useita CDS for Apps -esiintymiä. Näitä esiintymiä voi käyttää kokeiluun, kehitykseen ja tuotantoon. Jokaisessa esiintymässä on kopio järjestelmän käyttäjäentiteetistä ja mahdollisista järjestelmänvalvojan lisäämistä mukautetuista määritteistä sekä käyttäjän henkilötiedot, jotka on synkronoitu Office 365 -hallintakeskuksesta.

Järjestelmänvalvoja voi nähdä luettelon kaikista CDS for Apps -esiintymistä siirtymällä Dynamics 365 -hallintakeskukseen PowerApps-hallintakeskuksen kautta.

Tee seuraavat toiminnot [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1. Napsauta tai napauta siirtymisruudun kohtaa **Ympäristöt** ja valitse sitten ympäristö luettelosta.

3.  Napsauta tai napauta **Dynamics 365 -hallintakeskusta**.

    ![PowerApps-ympäristön tiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-environment-details.png)

    Näet luettelon kaikista esiintymistä.

    ![PowerApps-esiintymän valitsin](./media/common-data-service-gdpr-dsr-guide/powerapps-instance-picker.png)

Voit etsiä henkilötietoja CDS for Appsissa seuraavista resursseista:

|Resurssi | Tarkoitus | Sivuston käyttö | Ohjelmallinen käyttö
| --- | --- | --- | ---
| Entiteettitietue | Tämä on järjestelmän käyttäjäentiteetti, johon käyttäjän henkilötietoja tallennetaan. | [PowerApps-hallintakeskus](https://admin.powerapps.com) | [Verkon ohjelmointirajapinnan](https://docs.microsoft.com/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update) kautta
| Seurantahistoria | Tämän avulla asiakkaat voivat tunnistaa resursseja, joita käyttävät ovat luoneet, käyttäneet, muuttaneet tai poistaneet entiteettitasolla. | [PowerApps-hallintakeskus](https://admin.powerapps.com) | [Verkon ohjelmointirajapinnan](https://docs.microsoft.com/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update) kautta

#### <a name="user"></a>Käyttäjä
Käyttäjän henkilötiedot tallennetaan Azure Active Directoryyn ja ne synkronoidaan automaattisesti kaikkiin CDS for Apps -ympäristöihin. Järjestelmänvalvoja ei voi päivittää näitä henkilötietoja suoraan CDS for Appsissa, kun käyttäjä on aktiivinen&mdash;, vaan ne on päivitettävä Office 365 -hallintakeskuksessa. Järjestelmänvalvoja voi lisätä henkilötietoja (esimerkiksi mukautettuja määritteitä) suoraan CDS for Appsiin, mutta kyseisiä tietoja on hallittava manuaalisesti.

Etsi käyttäjä ja hänen henkilötietonsa siirtymällä [PowerApps-hallintakeskuksen](https://admin.powerapps.com/) ja toimimalla seuraavasti:

1. Napsauta tai napauta siirtymisruudun kohtaa **Ympäristöt** ja valitse sitten ympäristö luettelosta.

2. Napsauta tai napauta **Dynamics 365 -hallintakeskusta**, valitse ympäristö luettelosta ja napsauta tai napauta **Avaa**.

3. Valitse **Asetukset**  >  **Suojaus**  >  **Käyttäjät**.

4. Kirjoita käyttäjän nimi **hakuruutuun** ja napsauta tai napauta **Hae**.

5. Voit tarkastella käyttäjän henkilötietoja kaksoisnapsauttamalla tai kaksoisnapauttamalla käyttäjän nimeä.

    ![PowerApps-käyttäjälomake](./media/common-data-service-gdpr-dsr-guide/powerapps-user-form.png)

#### <a name="audit-history"></a>Seurantahistoria
Kun entiteetin [seuranta on käytössä](https://docs.microsoft.com/dynamics365/customer-engagement/admin/audit-data-user-activity) CDS for Appsissa, käyttäjän henkilötiedot kirjataan seurantahistoriaan yhdessä niiden tapahtumien kanssa, joita käyttäjä suorittaa.

### <a name="rectify"></a>Korjaaminen
Jos rekisteröity pyytää sinua korjaamaan henkilötietoja, joita organisaatiosi tietoihin sisältyy, sinun ja organisaatiosi täytyy päättää, onko pyynnön toteuttaminen asianmukaista. Tietojen korjaaminen saattaa tarkoittaa henkilötietojen muokkaamista ja poistamista tiedostossa tai muussa kohteessa.

Azure Active Directoryn avulla voit hallita CDS for Appsissa olevia loppukäyttäjiesi käyttäjätietoja (henkilötietoja). Yritysasiakkaat voivat hallita rekisteröityjen korjauspyyntöjä esimerkiksi tietyn Microsoft-palvelun rajoitetuilla muokkaustoiminnoilla. Rekisterinpitäjänä Microsoft ei tarjoa mahdollisuutta korjata järjestelmän luomia lokeja, sillä ne kuvaavat faktapohjaisia toimintoja ja täten Microsoftin palveluiden tapahtumien historiatietoja. Lisätietoja on ohjeaiheessa [GDPR: rekisteröityjen tietopyynnöt (DSR-pyynnöt)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

Kun käyttäjätietue on poistettu Azure Active Directorysta, järjestelmänvalvojat voivat poistaa kaikista esiintymistä käyttäjän kaikki jäljellä olevat henkilötiedot, kuten mukautetut määritteet.  

### <a name="export"></a>Vieminen

#### <a name="system-user"></a>Järjestelmäkäyttäjä
Voit viedä järjestelmän käyttäjäentiteettiin tallennetut käyttäjän henkilötiedot Exceliin hallintakeskuksen käyttäjäluettelosta.

Tee seuraavat toiminnot [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1. Napsauta tai napauta siirtymisruudun kohtaa **Ympäristöt** ja valitse sitten ympäristö luettelosta.

2. Napsauta tai napauta **Dynamics 365 -hallintakeskusta**, valitse ympäristö luettelosta ja napsauta tai napauta **Avaa**.

3. Siirry kohtaan **Asetukset** > **Suojaus**, ja valitse sitten **Aktivoidut käyttäjät -näkymä**.

4. Napsauta **Vie Exceliin**.

#### <a name="audit-history"></a>Seurantahistoria
Voit ottaa näyttökuvia seurantahistoriasta hallintakeskuksessa.

Tee seuraavat toiminnot [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1. Napsauta tai napauta siirtymisruudun kohtaa **Ympäristöt** ja valitse sitten ympäristö luettelosta.

2. Napsauta tai napauta **Dynamics 365 -hallintakeskusta**, valitse ympäristö luettelosta ja napsauta tai napauta **Avaa**.

3. Siirry kohtaan **Asetukset** > **Seuranta**, ja valitse sitten **Seurantayhteenvedon näkymä**.

    ![PowerApps-seurantahistorian valikko](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-menu.png)

4. Etsi käyttäjän seurantatietue ja ota sitten käyttökuva painamalla Alt + PrtScn.

    ![PowerApps-seurantahistorian tiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-details.png)

5. Tallenna näyttökuva tiedostona, jotta voit lähettää sen DSR-pyynnön tekijälle.

### <a name="delete"></a>Poistaminen

#### <a name="user"></a>Käyttäjä
Kun käyttäjä poistetaan Office 365 -hallintakeskuksesta, käyttäjätietuetta ei poisteta automaattisesti CDS for Apps -järjestelmän käyttäjäentiteetistä. Näin estetään häiriöiden aiheuttaminen liiketoimintasovelluksiin, jotka voivat olla kriittisiä organisaation toiminnan jatkumisen kannalta. Käyttäjän tila CDS for Appsissa on Ei käytössä, mutta CDS for Apps -järjestelmänvalvojan tulee etsiä ja poistaa käyttäjän henkilötiedot CDS for Appsista sovelluksessa.

#### <a name="remove-a-users-personal-data-from-the-users-summary-page"></a>Käyttäjän henkilötietojen poistaminen käyttäjän yhteenvetosivulta
Kun käyttäjätietue poistetaan Azure Active Directorysta, käyttäjän yhteenvetosivulla näytetään seuraava sanoma:

*Tämän käyttäjän tietoja ei hallita enää Office 365:ssä. Voit päivittää tämän tietueen vastauksena DSR-pyyntöihin poistamalla tai korvaamalla kaikki tähän käyttäjään liittyvät henkilötiedot.*

Tee seuraavat toiminnot [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1. Napsauta tai napauta siirtymisruudun kohtaa **Ympäristöt** ja valitse sitten ympäristö luettelosta.

2. Napsauta tai napauta **Dynamics 365 -hallintakeskusta**, valitse ympäristö luettelosta ja napsauta tai napauta **Avaa**.

3. Siirry kohtaan **Asetukset** > **Suojaus** > **Käyttäjät**, ja valitse sitten **Käytöstä poistetut käyttäjät -näkymä**.

4. Kirjoita käyttäjän nimi **hakuruutuun** ja napsauta tai napauta **Hae**.

9. Kaksoisnapsauta käyttäjänimeä hakutuloksissa.

10. Poista kaikki henkilötiedot käyttäjän yhteenvetosivulla ja napsauta tai napauta **Tallenna**.

#### <a name="remove-a-users-personal-data-by-using-excel"></a>Käyttäjän henkilötietojen poistaminen Excelin avulla
Tee seuraavat toiminnot [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1. Napsauta tai napauta siirtymisruudun kohtaa **Ympäristöt** ja valitse sitten ympäristö luettelosta.

2. Napsauta tai napauta **Dynamics 365 -hallintakeskusta**, valitse ympäristö luettelosta ja napsauta tai napauta **Avaa**.

3. Siirry kohtaan **Asetukset** > **Suojaus** > **Käyttäjät**, ja valitse sitten **Käytöstä poistetut käyttäjät -näkymä**.

4. Luo ja lataa Excel-mallitiedosto käyttäjän henkilötiedoista. Vaiheittaiset ohjeet ovat artikkelissa [Uuden Excel-mallin luominen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/analyze-your-data-with-excel-templates#create-a-new-excel-template).

8. Avaa ladattu Excel-mallitiedosto, poista käyttäjän henkilötiedot ja tallenna sitten tiedosto.

9. Palaa **Käytöstä poistetut käyttäjät** -näkymään ja napsauta tai napauta **Tuo tiedot**.

10. Valitse Excel-mallitiedosto **Lataa datatiedosto** -valintaikkunassa ja tee tarvittavat muutokset **Yhdistä kentät** -ikkunassa.

12. Napsauta tai napauta **Seuraava**, ja sitten napsauta tai napauta **Lähetä**.

#### <a name="remove-audit-history-from-the-audit-summary-view-page"></a>Seurantahistorian poistaminen Seurantayhteenvedon näkymä -sivulla
Tee seuraavat toiminnot [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1. Napsauta tai napauta siirtymisruudun kohtaa **Ympäristöt** ja valitse sitten ympäristö luettelosta.

2. Napsauta tai napauta **Dynamics 365 -hallintakeskusta**, valitse ympäristö luettelosta ja napsauta tai napauta **Avaa**.

3. Siirry kohtaan **Asetukset** > **Seuranta**, ja valitse sitten **Seurantayhteenvedon näkymä**.

4. Etsi käyttäjän muutoshistoria, napsauta tai napauta rivi(e)n vieressä olevaa valintaruutua ja napsauta tai napauta **Poista muutoshistoria**.

## <a name="personal-data-stored-in-databases-of-cds-for-apps"></a>CDS for Apps -tietokantoihin tallennetut henkilötiedot

### <a name="prerequisites"></a>Edellytykset
Olet mahdollisesti tallentanut yksityishenkilöiden, kuten omien asiakkaittesi, henkilötietoja CDS for Apps -entiteetteihin.  

CDS-järjestelmänvalvoja on vastuussa henkilötietojen tallennuspaikkahakemiston ylläpidosta eri entiteeteissä, jotta hän osaa paikantaa tarvittavat henkilötiedot DSR-pyyntöihin vastaamiseksi.  

Henkilötietoja voi sitten viedä, korjata tai poistaa entiteetissä käyttämällä tuotteen sisäistä toimintoa.  

### <a name="discover"></a>Etsintä
Kun CDS-järjestelmänvalvoja vastaanottaa DSR-pyynnön yksityishenkilöltä, järjestelmänvalvojan täytyy tunnistaa, mitkä ympäristöt tai CDS-esiintymät sisältävät tämän henkilön henkilötietoja. Henkilötiedot tallennetaan yleensä avainentiteetteihin (esimerkiksi tili, yhteyshenkilö, liidi, mahdollisuus jne.), mutta on sinun vastuullasi laatia hakemistoon liittyvät käytännöt ja toimintatavat, jotka varmistavat, että yksityishenkilöiden henkilötiedot ovat löydettävissä DSR-pyyntöihin vastaamiseksi.

Hakemiston avulla CDS-järjestelmänvalvojat voivat määrittää haun entiteetit ja kentät ja käyttää sitten CDS for Apps - ympäristöä henkilötietojen löytämiseen. Lisätietoja on kohdassa [Määritä osuvuushaku](https://go.microsoft.com/fwlink/?linkid=872506).

Tee seuraavat toiminnot [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1. Napsauta tai napauta siirtymisruudun kohtaa **Ympäristöt** ja valitse sitten ympäristö luettelosta.

2. Napsauta tai napauta **Dynamics 365 -hallintakeskusta**, valitse ympäristö luettelosta, napsauta tai napauta hakupainiketta ja napsauta tai napauta **Osuvuushaku**.

    ![PowerAppsin osuvuushakuvalikko](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3. Kirjoita hakukenttään henkilön henkilötieto ja napsauta tai napauta **Haku**-painiketta.

    ![PowerAppsin osuvuushaun tulokset](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

### <a name="rectify"></a>Korjaaminen
CDS-järjestelmänvalvoja voi päivittää yksityishenkilöjen henkilötietoja käyttämällä osuvuushaun hakutulosluetteloa. Yksityishenkilöiden henkilötietoja voidaan tallentaa myös muihin mukautettuihin entiteetteihin. CDS-järjestelmänvalvojan vastuulla on ylläpitää näiden mukautettujen entiteettien hakemistoa ja tehdä tarvittavat päivitykset henkilöjen henkilötietoihin.

Tee seuraavat toiminnot osuvuushaun tuloksissa:

1. Napsauta tai napauta kohdetta, joka sisältää henkilön henkilötietoja.

2. Päivitä henkilön henkilötietoja tarvittaessa ja napsauta tai napauta **Tallenna**.

    ![PowerApps-tilitiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-account-details.png)

### <a name="export"></a>Vieminen
Voit ottaa tiedoista näyttökuvan ja jakaa sen DSR-pyynnön tekijälle.

Tee seuraavat toiminnot [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1. Napsauta tai napauta siirtymisruudun kohtaa **Ympäristöt** ja valitse sitten ympäristö luettelosta.

2. Napsauta tai napauta **Dynamics 365 -hallintakeskusta**, valitse ympäristö luettelosta, napsauta tai napauta hakupainiketta ja napsauta tai napauta **Osuvuushaku**.

    ![PowerAppsin osuvuushakuvalikko](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3. Kirjoita hakukenttään henkilön henkilötieto ja napsauta tai napauta **Haku**-painiketta.

    ![PowerAppsin osuvuushaun tulokset](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

4. Kaksoisnapsauta kohdetta hakutulosten luettelossa.

5. Ota näyttökuva painamalla Alt + PrtScn.

6. Tallenna näyttökuva tiedostona, jotta voit lähettää sen DSR-pyynnön tekijälle.

### <a name="delete"></a>Poistaminen
CDS-järjestelmänvalvoja voi poistaa yksityishenkilön henkilötietoja tietueista, joihin ne on tallennettu.  CDS-järjestelmänvalvoja voi joko poistaa tietueen, johon henkilötietoja on tallennettu, tai poistaa henkilötietojen sisällön tietueesta.  

> [!NOTE]
> CDS-järjestelmänvalvoja voi mukauttaa ympäristöä siten, että tietueen poistamisen entiteetistä estetään. Jos ympäristö määritetään näin, henkilötietojen sisältö on poistettava tietueesta itse tietueen poistamisen sijaan.

Tee seuraavat toiminnot osuvuushaun tuloksissa:

1. Napsauta tai napauta kohdetta, joka sisältää henkilön henkilötietoja.

2. Napsauta tai napauta Valintanauhassa olevaa **Poista**-painiketta. (Huomaa, että **Poista**-painike ei ole käytettävissä, jos tietuetta ei voi poistaa).

    ![PowerApps-tilin poistaminen](./media/common-data-service-gdpr-dsr-guide/powerapps-account-delete.png)

## <a name="personal-data-stored-in-databases-of-the-previous-version-of-cds"></a>Aiemman CDS -version tietokantoihin tallennetut henkilötiedot

### <a name="prerequisites"></a>Edellytykset
Olet mahdollisesti tallentanut yksityishenkilöiden, kuten omien asiakkaittesi, henkilötietoja CDS-entiteetteihin.  

CDS-järjestelmänvalvoja on vastuussa henkilötietojen tallennuspaikkahakemiston ylläpidosta eri entiteeteissä, jotta hän osaa paikantaa tarvittavat henkilötiedot DSR-pyyntöihin vastaamiseksi.  

Henkilötietoja voi sitten viedä, korjata tai poistaa entiteetissä käyttämällä tuotteen sisäistä toimintoa.  

### <a name="discover"></a>Etsintä
Kun CDS-järjestelmänvalvoja vastaanottaa DSR-pyynnön yksityishenkilöltä, järjestelmänvalvojan täytyy tunnistaa, mitkä ympäristöt tai CDS-esiintymät sisältävät tämän henkilön henkilötietoja. Henkilötiedot tallennetaan yleensä avainentiteetteihin (esimerkiksi tili, yhteyshenkilö, liidi, mahdollisuus jne.), mutta on sinun vastuullasi laatia hakemistoon liittyvät käytännöt ja toimintatavat, jotka varmistavat, että yksityishenkilöiden henkilötiedot ovat löydettävissä DSR-pyyntöihin vastaamiseksi.

Voit etsiä aiemman CDS-version käyttäjien henkilötietoja seuraavista resursseista:

|Resurssi | Tarkoitus | Sivuston käyttö |  Ohjelmallinen käyttö
| --- | --- | --- | ---
|Entiteetin tietueet | Tämän avulla liiketoimintatapahtumat taltioidaan vastaavaan liiketoimintaentiteettiin. | [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) |    Ei

#### <a name="entity-records"></a>Entiteetin tietueet
Yksityishenkilöiden henkilötietoja voidaan tallentaa mihin tahansa liiketoimintaentiteettiin.

Tämä CDS-versio sisältää oman tietokantarakenteensa ja infrastruktuurinsa. Sillä on oma entiteetit, joita hallitaan [PowerAppsissa](http://web.powerapps.com/).

Näet entiteettiluettelon seuraavasti:

1. Valitse ympäristösi avattavasta **Ympäristö**-luettelosta.

2. Napsauta tai napauta siirtymisruudussa **Tiedot** ja valitse sitten **Entiteetit**.

    ![PowerAppsin vanhat entiteetit](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

3. Napsauta tai napauta luettelossa olevaa entiteettiä (esimerkiksi Tili-entiteettiä) alla kuvatulla tavalla.

    ![PowerAppsin vanhojen entiteettien tietoluettelo](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

4. Napsauta tai napauta **Tiedot**-välilehteä. Näet luettelon entiteetin tietueista.

    ![PowerAppsin vanhan tilin tiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

5. Napsauta tai napauta **Vie tiedot**.

6. Kun vienti on valmis, napsauta tai napauta **Avaa Excelissä**, ja napsauta tai napauta **Ota muokkaus käyttöön**.

7. Napsauta tai napauta hakupainiketta, kirjoita hakukenttään henkilön henkilötieto ja napsauta tai napauta **Haku**-painiketta.

8. Toista yllä olevat vaiheet kullekin liiketoimintaentiteetille käyttämällä hakemistoa entiteeteistä, joihin henkilötiedot on tallennettu.

### <a name="rectify"></a>Korjaaminen
Jos rekisteröity pyytää sinua korjaamaan henkilötietoja, joita organisaatiosi tietoihin sisältyy, sinun ja organisaatiosi täytyy päättää, onko pyynnön toteuttaminen asianmukaista. Tietojen korjaaminen saattaa tarkoittaa henkilötietojen muokkaamista ja poistamista tiedostossa tai muussa kohteessa.

Azure Active Directoryn avulla voit hallita CDS:n aiemmassa versiossa olevia loppukäyttäjiesi käyttäjätietoja (henkilötietoja). Yritysasiakkaat voivat hallita rekisteröityjen korjauspyyntöjä esimerkiksi tietyn Microsoft-palvelun rajoitetuilla muokkaustoiminnoilla. Rekisterinpitäjänä Microsoft ei tarjoa mahdollisuutta korjata järjestelmän luomia lokeja, sillä ne kuvaavat faktapohjaisia toimintoja ja täten Microsoftin palveluiden tapahtumien historiatietoja. Lisätietoja on ohjeaiheessa [GDPR: rekisteröityjen tietopyynnöt (DSR-pyynnöt)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

CDS-ympäristössä sijaitsevien henkilötietojen korjaaminen tapahtuu viemällä entiteetin tiedot Excel-laskentataulukkoon, päivittämällä tiedot taulukossa ja tuomalla päivitykset takaisin tietokantaan.

CDS-järjestelmänvalvojan vastuulla on tunnistaa kaikki entiteetit, joihin yksityishenkilöiden henkilötietoja sisältyy, ja toistaa seuraavat vaiheet jokaiselle entiteeteistä.

Tee [PowerAppsissa](http://web.powerapps.com/) seuraavat toiminnot:

1. Napsauta tai napauta siirtymisruudussa **Tiedot** ja valitse sitten **Entiteetit**.

    ![PowerAppsin vanhat entiteetit](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. Napsauta tai napauta luettelossa olevaa entiteettiä (esimerkiksi Tili-entiteettiä) alla kuvatulla tavalla.

    ![PowerAppsin vanhojen entiteettien tietoluettelo](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. Napsauta tai napauta **Tiedot**-välilehteä. Näet luettelon entiteetin tietueista.

    ![PowerAppsin vanhan tilin tiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. Napsauta tai napauta **Vie tiedot**.

5. Kun vienti on valmis, napsauta tai napauta **Avaa Excelissä**, ja napsauta tai napauta **Ota muokkaus käyttöön**.

6. Napsauta tai napauta valikkorivillä olevaa **Tiedosto**-kohtaa, napsauta tai napauta **Tallenna nimellä** ja valitse sitten sijainti, johon haluat tallentaa tiedoston.

7. Tee tarvittavat päivitykset henkilötietoihin ja tallenna laskentataulukko.

10. Siirry PowerAppsissa takaisin **Tiedot**-välilehdelle ja napsauta tai napauta **Tuo tiedot**.

11. Napsauta **Haku**-painiketta ja valitse ja avaa Excel-laskentataulukko, jonka olet juuri päivittänyt.

12. Napsauta kohtaa **Tuo**.

### <a name="export"></a>Vieminen
Voit viedä kunkin entiteetin henkilötiedot Excel-laskentataulukkoon ja tarkastella sitä.

Tee [PowerAppsissa](http://web.powerapps.com/) seuraavat toiminnot:

1. Napsauta tai napauta siirtymisruudussa **Tiedot** ja valitse sitten **Entiteetit**.

    ![PowerAppsin vanhat entiteetit](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. Napsauta tai napauta luettelossa olevaa entiteettiä, jonka haluat viedä ja näyttää (esimerkiksi Tili-entiteettiä), alla kuvatulla tavalla.

    ![PowerAppsin vanhojen entiteettien tietoluettelo](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. Napsauta tai napauta **Tiedot**-välilehteä. Näet luettelon entiteetin tietueista.

    ![PowerAppsin vanhan tilin tiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. Napsauta tai napauta **Vie tiedot**.

    Vienti suoritetaan taustatoimintona, ja saat ilmoituksen, kun se on valmis.

5. Voit tarkastella vietyjä tietoja napsauttamalla **Avaa Excelissä**.

### <a name="delete"></a>Poistaminen
Voit poistaa entiteetteihin tallennettuja henkilötietoja käyttämällä tietojen vienti- ja tuontitoimintoa.

CDS-järjestelmänvalvojan vastuulla on tunnistaa kaikki entiteetit, joihin yksityishenkilöiden henkilötietoja sisältyy, ja toistaa seuraavat vaiheet jokaiselle entiteeteistä.

Tee [PowerAppsissa](http://web.powerapps.com/) seuraavat toiminnot:

1. Napsauta tai napauta siirtymisruudussa **Tiedot** ja valitse sitten **Entiteetit**.

    ![PowerAppsin vanhat entiteetit](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. Napsauta tai napauta luettelossa olevaa entiteettiä, josta haluat poistaa henkilötietoja (esimerkiksi Tili-entiteettiä), alla kuvatulla tavalla.

    ![PowerAppsin vanhojen entiteettien tietoluettelo](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. Napsauta tai napauta **Tiedot**-välilehteä. Näet luettelon entiteetin tietueista.

    ![PowerAppsin vanhan tilin tiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. Napsauta tai napauta **Vie tiedot**.

5. Kun vienti on valmis, napsauta tai napauta **Avaa Excelissä**, ja napsauta tai napauta **Ota muokkaus käyttöön**.

6. Napsauta tai napauta valikkorivillä olevaa **Tiedosto**-kohtaa, napsauta tai napauta **Tallenna nimellä** ja valitse sitten sijainti, johon haluat tallentaa tiedoston.

7. Poista rivit, jotka sisältävät entiteetistä poistettavat henkilötiedot, ja tallenna laskentataulukko.

10. Siirry PowerAppsissa takaisin **Tiedot**-välilehdelle ja napsauta tai napauta **Tuo tiedot**.

11. Napsauta **Haku**-painiketta ja valitse ja avaa Excel-laskentataulukko, jonka olet juuri päivittänyt.

12. Napsauta kohtaa **Tuo**.
---
title: Opas asiakkaiden luomien tietojen rekisteröityjen tietopyynnöille | Microsoft Docs
description: 'PowerApps: PowerApps: opas asiakkaiden luomien tietojen rekisteröityjen tietopyynnöille'
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/17/2018
ms.author: paulliew
ms.openlocfilehash: cff822e24f1384833caa0baa945a7d3d07a8ee9b
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/20/2018
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-customer-data-in-common-data-service-for-apps"></a>Common Data Service for Appsin asiakastietoihin kohdistuviin rekisteröityjen tietopyyntöihin vastaaminen

## <a name="introduction-to-dsr-requests"></a>Johdanto DSR-pyyntöihin
Osana pyrkimyksiämme auttaa sinua täyttämään yleiseen tietosuoja-asetuksen (GDPR) vaatimukset olemme luoneet tämän asiakirjan, jolla voit valmistautua asetuksen voimaantuloon. Tässä asiakirjassa kerrotaan, miten valmistaudumme yleiseen tietosuoja-asetukseen. Annamme myös esimerkkejä toimenpiteistä, joihin voit ryhtyä jo tänään Microsoftin tuella täyttääksesi yleisen tietosuoja-asetuksen vaatimukset, kun käytät PowerApps-sovelluksia, Microsoft Flow’ta ja Common Data Service for Appsia.

GDPR antaa ihmisille (joita kutsutaan asetuksessa rekisteröidyiksi) oikeuden hallita henkilötietoja, joita työnantaja, muu organisaatio tai virasto (jota kutsutaan rekisterinpitäjäksi) on heistä kerännyt. GDPR määrittää henkilötiedoiksi hyvin yleisesti mitkä tahansa tiedot, jotka liittyvät tunnistettuun tai tunnistettavissa olevaan luonnolliseen henkilöön. GDPR antaa rekisteröidyille tietyt oikeudet henkilötietoihinsa. Näitä oikeuksia ovat oikeus tarkistaa henkilötiedot, oikeus pyytää henkilötietojen korjaamista, oikeus rajoittaa henkilötietojen käsittelyä, oikeus pyytää henkilötietojen poistamista ja oikeus vastaanottaa henkilötiedot sähköisessä muodossa, jotta ne voidaan siirtää toiselle rekisterinpitäjälle. Rekisteröidyn rekisterinpitäjälle tekemää virallista pyyntöä ryhtyä toimiin henkilötietoihin liittyen kutsutaan rekisteröidyn tietopyynnöksi.

Tässä oppaassa käsitellään sitä, miten Microsoftin tuotteet, palvelut ja hallintatyökalut auttavat rekisterinpitäjiä etsimään henkilötietoja ja suorittamaan niille toimintoja, jotta ne voivat vastata rekisteröityjen tietopyyntöihin. Erityisesti käsittelemme sitä, miten voit etsiä ja käyttää Microsoftin pilvipalveluihin tallennettuja henkilötietoja sekä suorittaa niille toimenpiteitä. Alla on lyhyt yleiskuvaus tässä oppaassa käsiteltävistä prosesseista:

1. **Etsiminen**: Haku- ja etsintätyökalulla voit etsiä helpommin asiakastietoja, jotka saattavat olla rekisteröidyn tietopyynnön kohteena. Kun mahdollisesti oleelliset tiedostot on kerätty, voit suorittaa niille rekisteröidyn tietopyynnön toimintoja, jotka kuvataan seuraavissa vaiheissa ja joilla voit vastata pyyntöön. Voit myös tulla siihen tulokseen, että pyyntö ei täytä organisaatiosi vaatimuksia rekisteröidyn tietopyyntöön vastaamiselle.

2. **Tarkistaminen**: hae Microsoftin pilvipalveluihin tallennetut henkilötiedot ja ota niistä pyydettäessä kopio, jonka voit toimittaa rekisteröidylle.

3. **Korjaaminen**: tee henkilötietoihin muutoksia tai suorita niille muita pyydettyjä toimintoja soveltuvin osin.

4. **Rajoittaminen**: Rajoita henkilötietojen käsittelyä joko poistamalla erilaisten verkkopalveluiden käyttöoikeuksia tai poistamalla halutut palvelut käytöstä, jos se on mahdollista. Voit poistaa tietoja Microsoftin pilvipalveluista ja tallentaa ne paikallisesti tai muuhun sijaintiin.

5. **Poistaminen**: poista Microsoftin pilvipalveluihin tallennetut henkilötiedot pysyvästi.

6. **Vieminen**: toimita rekisteröidyn henkilötietojen kopio sähköisessä (koneluettavassa) muodossa rekisteröidylle.

Kussakin tämän oppaan osiossa esitellään tekniset toimintatavat, joilla rekisterinpitäjäorganisaatio voi reagoida rekisteröidyn henkilötietopyyntöön Microsoftin pilvipalvelussa.

## <a name="common-data-service-customer-data"></a>Common Data Service -asiakastiedot

> [!IMPORTANT]
> Koskee sekä Common Data Service for Appsia että Common Data Serviceä (aiempi versio)

Common Data Service -palveluja (CDS) on kaksi eri tyyppiä: Common Data Service for Apps ja Common Data Servicen edellinen versio. Henkilötietojen käsittelyprosessit poikkeavat versioissa toisistaan.

Voit tunnistaa käyttämäsi CDS-ympäristön suorittamalla seuraavat vaiheet [PowerApps-sivustossa](https://web.powerapps.com):

1.  Valitse avattavasta Ympäristö-luettelosta **Ympäristö**.
2.  Valitse **Tiedot**  >  **Entiteetit**.

    Ympäristösi on Common Data Service for Apps, jos nämä entiteetit näkyvät:

    ![PowerApps-entiteettien luettelo](./media/common-data-service-gdpr-dsr-guide/powerapps-entities-list.png)

    Ympäristösi on Common Data Servicen edellinen versio, jos nämä entiteetit näkyvät:

    ![PowerAppsin vanhojen entiteettien luettelo](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-list.png)

Kun olet selvittänyt, mikä CDS-ympäristön tyyppi on käytössäsi, voit tunnistaa henkilökohtaiset tiedot tämän asiakirjan vastaavien osioiden avulla.

> [!NOTE]
> Käytössäsi voi olla tiettyjä ympäristöjä CDS for Appsissa ja muita ympäristöjä CDS:ssä (aiempi versio), joten sinun on toistettava alla kuvattu prosessi jokaiselle organisaatiosi ympäristölle.

## <a name="user-personal-data-in-common-data-service-for-apps"></a>Käyttäjän henkilötiedot Common Data Service for Appsissa

### <a name="prerequisites"></a>Edellytykset
Käyttäjä on luotava Office 365 -hallintakeskuksessa, ja hänelle on määritettävä tarvittava Common Data Service -käyttöoikeus Common Data Servicen käyttämistä varten.  Tarvitaan myös käyttöoikeusrooli, ennen kuin käyttäjä voi käyttää Common Data Serviceä.

Käyttäjän henkilötiedot tallennetaan Office 365 -hallintakeskukseen ja CDS-järjestelmän käyttäjäentiteettiin.  Office 365 -hallintakeskuksessa säilytetään ja ylläpidetään tiettyjä käyttäjän perushenkilötietoja, joita ovat esimerkiksi käyttäjänimi, käyttäjätunnus, puhelin, sähköposti ja osoite. Nämä käyttäjän henkilötiedot synkronoidaan CDS-järjestelmän käyttäjäentiteettiin kaikissa ympäristöissä.  Järjestelmänvalvoja voi päivittää näitä henkilötietoja vain Office 365 -hallintakeskuksessa. Nämä määritteet synkronoidaan sen jälkeen automaattisesti CDS for Appsiin. Järjestelmänvalvoja voi myös luoda mukautettuja määritteitä muiden henkilötietojen taltioimiseksi CDS-järjestelmän käyttäjäentiteettiin.  Mukautettuja määritteitä ylläpidetään ja hallitaan CDS-järjestelmässä manuaalisesti järjestelmänvalvojan toimesta.

Kun käyttäjä poistetaan Office 365 -hallintakeskuksesta, käyttäjätietuetta ei poisteta automaattisesti CSD-järjestelmän käyttäjäentiteetistä. Sillä tavoin estetään häiriöiden aiheuttaminen liiketoimintasovelluksiin, jotka voivat olla kriittisiä organisaation toiminnan jatkumisen kannalta.  CDS-järjestelmänvalvojan on etsittävä ja poistettava käyttäjän henkilötiedot CDS:stä sovellusta käyttämällä.

Alla luetellut etsintä-, korjaamis-, vienti- ja poistotoiminnot voi suorittaa vain käyttäjä, jolla on Office 365:n yleisen järjestelmänvalvojan rooli ja CDS-järjestelmänvalvojan käyttöoikeusrooli.

### <a name="discover"></a>Etsintä

Järjestelmänvalvojat voivat luoda useita CDS-esiintymiä.  Näitä esiintymiä voi käyttää kokeiluun, kehitykseen ja tuotantoon.   Jokaisessa esiintymässä on kopio järjestelmän käyttäjäentiteetistä ja mahdollisista järjestelmänvalvojan lisäämistä mukautetuista määritteistä sekä käyttäjän henkilötiedot, jotka on synkronoitu Office 365 -hallintakeskuksesta.

Järjestelmänvalvoja voi nähdä luettelon kaikista CDS-esiintymistä siirtymällä Dynamics 365 -hallintakeskukseen PowerApps-hallintakeskuksen kautta.

[PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1.  Siirry Ympäristöt-välilehdelle.
2.  Valitse Ympäristöt-luettelosta ympäristö.
3.  Napsauta Dynamics 365 -hallintakeskuksen linkkiä.

    ![PowerApps-ympäristön tiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-environment-details.png)

    Näet luettelon kaikista esiintymistä.

    ![PowerApps-esiintymän valitsin](./media/common-data-service-gdpr-dsr-guide/powerapps-instance-picker.png)

CDS-järjestelmän käyttäjien henkilötietoja voi olla seuraavissa kohteissa:

|Henkilötietoja sisältävät resurssit | Tarkoitus | Sivuston käyttö | Ohjelmallinen käyttö
| --- | --- | --- | ---
| Entiteettitietue | Järjestelmän käyttäjäentiteetti | [PowerApps-hallintakeskus](https://admin.powerapps.com) | [Verkon ohjelmointirajapinnan kautta](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)
| Seurantahistoria | Tämän avulla asiakkaat voivat tunnistaa resursseja, joita käyttävät ovat luoneet, käyttäneet, muuttaneet tai poistaneet entiteettitasolla. | [PowerApps-hallintakeskus](https://admin.powerapps.com) | [Verkon ohjelmointirajapinnan kautta](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)

#### <a name="user"></a>Käyttäjä
Office 365 -hallintakeskuksessa ylläpidettävät ja hallittavat käyttäjien henkilötiedot on tallennettu Azure Active Directoryyn.  Näitä henkilötietoja hallitaan Office 365 -hallintakeskuksessa, ja ne synkronoidaan automaattisesti kaikkiin CDS-ympäristöihin.  Järjestelmänvalvoja ei voi päivittää näitä henkilötietoja suoraan CDS-järjestelmään, kun käyttäjä on aktiivinen, vaan ne on päivitettävä suoraan Office 365 -hallintakeskuksessa.  Muita henkilötietoja, kuten mukautettuja määritteitä, voidaan lisätä suoraan CDS:ään, jolloin järjestelmänvalvojan on ylläpidettävä ja hallittava niitä manuaalisesti.

CDS-järjestelmänvalvoja voi etsiä tietyn käyttäjän ja tähän liittyvät henkilötiedot seuraavasti:

[PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1.  Siirry Ympäristöt-välilehdelle.
2.  Valitse Ympäristöt-luettelosta ympäristö.
3.  Napsauta Dynamics 365 -hallintakeskuksen linkkiä.
4.  Napsauta ympäristön nimeä.
5.  Valitse **Avaa**-painike.
6.  Valitse **Asetukset**  >  **Suojaus**.
7.  Valitse **Käyttäjät**.
8.  Kirjoita käyttäjän nimi **Haku**-ruutuun.
9.  Valitse **Hae**-painike.
10. Kaksoisnapsauta käyttäjää.

    ![PowerApps-käyttäjälomake](./media/common-data-service-gdpr-dsr-guide/powerapps-user-form.png)

#### <a name="audit-history"></a>Seurantahistoria
Kun Common Data Servicen entiteetin [seuranta on käytössä](https://docs.microsoft.com/dynamics365/customer-engagement/admin/audit-data-user-activity), käyttäjän henkilötiedot kirjataan seurantahistoriaan yhdessä niiden tapahtumien kanssa, joita käyttäjä oli suorittamassa.

### <a name="rectify"></a>Korjaaminen

Jos rekisteröity pyytää sinua korjaamaan henkilötietoja, joita organisaatiosi tietoihin sisältyy, sinun ja organisaatiosi täytyy päättää, hyväksyttekö pyynnön.  Tietojen korjaaminen saattaa tarkoittaa henkilötietojen muokkaamista ja poistamista tiedostossa tai muussa kohteessa.

Azure Active Directoryn avulla voit hallita Common Data Service for Appsissa olevia loppukäyttäjiesi käyttäjätietoja (henkilötietoja). Yritysasiakkaat voivat hallita rekisteröityjen korjauspyyntöjä, esimerkiksi rajoitetuilla muokkaustoiminnoilla tietyn Microsoft-palvelun luoteen mukaisesti.  Rekisterinpitäjänä Microsoft ei tarjoa mahdollisuutta korjata järjestelmän luomia lokeja, sillä ne kuvaavat faktapohjaisia toimintoja ja täten Microsoftin palveluiden tapahtumien historiatietoja. Lisätietoja on ohjeaiheessa [GDPR: rekisteröityjen tietopyynnöt (DSR-pyynnöt)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

Kun käyttäjätietue on poistettu Azure Active Directorysta, järjestelmänvalvojat voivat poistaa kaikista esiintymistä käyttäjän kaikki jäljellä olevat henkilötiedot, kuten mahdollisesti lisätyt mukautetut määritteet.  

### <a name="export"></a>Vieminen

#### <a name="system-user"></a>Järjestelmäkäyttäjä
Järjestelmän käyttäjäentiteettiin tallennetut käyttäjän henkilötiedot voidaan viedä Excel-tiedostoon portaalin käyttäjäluettelosta.

[PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):

1.  Siirry Ympäristöt-välilehdelle.
2.  Valitse Ympäristöt-luettelosta ympäristö.
3.  Napsauta Dynamics 365 -hallintakeskuksen linkkiä.
4.  Napsauta ympäristön nimeä.
5.  Valitse Avaa-painike ja sitten Asetukset > Suojaus.
6.  Valitse Aktivoidut käyttäjät -näkymä.
7.  Valitse Vie Exceliin -painike.

#### <a name="audit-history"></a>Seurantahistoria
Seurantahistorian näyttökuvia voi siepata ja kopioida sovelluksesta alla olevien ohjeiden avulla.
[PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):
1.  Siirry Ympäristöt-välilehdelle.
2.  Valitse Ympäristöt-luettelosta ympäristö.
3.  Napsauta Dynamics 365 -hallintakeskuksen linkkiä.
4.  Napsauta ympäristön nimeä.
5.  Valitse Avaa-painike.
6.  Valitse Asetukset > Seuranta.

    ![PowerApps-seurantahistorian valikko](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-menu.png)

7.  Valitse Seurantayhteenvedon näkymä.
8.  Etsi käyttäjän seurantatietue.

    ![PowerApps-seurantahistorian tiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-details.png)

9.  Sieppaa näyttökuva painamalla Alt + PrtScn.
10. Tallenna näyttökuva tiedostoon.
11. Voit lähettää tiedoston sitten DSR-pyytäjälle.

### <a name="delete"></a>Poistaminen

#### <a name="user"></a>Käyttäjä
Kun käyttäjä poistetaan Office 365 -hallintakeskuksesta, käyttäjän tilaksi asetetaan CSD-järjestelmässä Ei käytössä. Käyttäjän henkilötietoja ei kuitenkaan poisteta automaattisesti. Sillä tavoin estetään häiriöiden aiheuttaminen liiketoimintasovelluksiin, jotka voivat olla kriittisiä organisaation toiminnan jatkumisen kannalta.
Käyttäjän henkilötietojen poistaminen CDS-järjestelmästä edellyttää, että järjestelmänvalvoja poistaa käytöstä poistetun käyttäjän henkilötiedot manuaalisesti.

#### <a name="remove-user-personal-data-via-user-form"></a>Käyttäjän henkilötietojen poistaminen käyttäjälomakkeen kautta
Kun käyttäjätietue poistetaan Azure Active Directorysta, käyttäjälomakkeessa näytetään seuraava sanoma.
Tämän käyttäjän tietoja ei hallita enää Office 365:ssä. Voit päivittää tämän tietueen vastauksena DSR-pyyntöihin poistamalla tai korvaamalla kaikki tähän käyttäjään liittyvät henkilötiedot.

[PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):
1.  Siirry Ympäristöt-välilehdelle.
2.  Valitse Ympäristöt-luettelosta ympäristö.
3.  Napsauta Dynamics 365 -hallintakeskuksen linkkiä.
4.  Napsauta ympäristön nimeä.
5.  Valitse **Avaa**-painike.
6.  Valitse **Asetukset**  >  **Suojaus**  >  **Käyttäjät**.
7.  Valitse **Käytöstä poistetut käyttäjät** -näkymä.
8.  Kirjoita käyttäjänimi **Hae tietueita** -ruutuun ja valitse **Hae**-painike.
9.  Kaksoisnapsauta käyttäjänimeä hakutuloksissa.
10. Poista kaikki henkilötiedot ja valitse **Tallenna**.

#### <a name="remove-user-personal-data-via-excel-importexport"></a>Käyttäjän henkilötietojen poistaminen Excelin tuonti- ja vientitoiminnolla
1.  Valitse **Asetukset**  >  **Suojaus**  >  **Käyttäjät**.
2.  Valitse **Käytöstä poistetut käyttäjät** -näkymä.
3.  Luo Excel-malli, joka sisältää sarakkeet kaikille päivitettäville käyttäjän henkilötiedoille.
4.  Valitse **Lataa tiedosto**.
5.  Avaa ladattu Excel-tiedoston, tee tarvittavat päivitykset ja tallenna tiedosto.
6.  Palaa Käytöstä poistetut käyttäjät -näkymään ja valitse Tuo tiedot.
7.  Valitse päivitetty Excel-tiedostosi Lataa datatiedosto -valintaikkunasta.
8.  Tee tarvittavat muutokset Yhdistä kentät -ikkunassa.
9.  Valitse Seuraava ja Lähetä.

Lisätietoja Excel-mallien käyttämisestä on ohjeaiheessa [Lisätietoja Excelistä](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/analyze-your-data-with-excel-templates).


#### <a name="remove-audit-history-via-the-audit-summary-view-form"></a>Seurantahistorian poistaminen Seurantayhteenvedon näkymä -lomakkeella

[PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):
1.  Siirry Ympäristöt-välilehdelle.
2.  Valitse Ympäristöt-luettelosta ympäristö.
3.  Napsauta Dynamics 365 -hallintakeskuksen linkkiä.
4.  Napsauta ympäristön nimeä.
5.  Valitse Avaa-painike.
6.  Valitse Asetukset > Seuranta.
7.  Valitse Seurantayhteenvedon näkymä.
8.  Käyttäjän tekemien muutosten muutoshistorian etsiminen
9.  Valitse tarvittavien rivien valintaruudut.
10. Napsauta Poista muutoshistoria -kuvaketta.

## <a name="personal-data-stored-in-common-data-service-for-apps-databases"></a>Common Data Service for Apps -tietokantoihin tallennetut henkilötiedot

### <a name="prerequisites"></a>Edellytykset
Olet mahdollisesti tallentanut yksityishenkilöiden, kuten omien asiakkaittesi, henkilötietoja CDS-entiteettien sisältöön.  

Jos yksityishenkilö lähettää organisaatiollesi DSR-pyynnön, CDS-järjestelmänvalvojan on etsittävä kaikki entiteetit, joissa henkilöön sovelluksessasi viitataan.  CDS-järjestelmänvalvojan vastuulla on ylläpitää hakemistoa siitä, minne henkilötietoja tallennetaan erilaisissa käyttämissäsi entiteeteissä, jotta voit vastata yksityishenkilöjen DSR-pyyntöihin.

Sisällössäsi olevia henkilötietoja voi sitten viedä, korjata tai poistaa entiteetissä käyttämällä tuotteen sisäistä toimintoa.  

### <a name="discover"></a>Etsintä
Kun CDS-järjestelmänvalvoja vastaanottaa DSR-pyynnön yksityishenkilöltä, järjestelmänvalvojan täytyy tunnistaa, mitkä ympäristöt tai CDS-esiintymät sisältävät tämän henkilön henkilötietoja.  Organisaatiossasi tulisi kehittää käytäntöjä ja menettelytapoja, joilla ylläpidetään hakemistoa yksityishenkilöiden henkilötietojen tallentamiseen käytettävistä ympäristöistä, esiintymistä ja entiteeteistä. Siten pystyt tunnistamaan sisältöösi tallennetut henkilötiedot.

Käyttämällä hakemistoa henkilötietojen tallentamiseen käytettävistä ympäristöistä, esiintymistä ja entiteeteistä voit määrittää CDS-hakukoneen henkilötietojen hakemiseen.  CDS-järjestelmänvalvoja voi määrittää hakuentiteetit ja -kentät. Lisätietoja on ohjeaiheessa [Määritä osuvuushaku](https://go.microsoft.com/fwlink/?linkid=872506).
Sen jälkeen CDS-järjestelmänvalvoja käyttää CDS-ympäristöä ja suorittaa haun.

1.  Valitse **Haku**-kuvaketta.
2.  Valitse **Osuvuushaku**.

    ![PowerAppsin osuvuushakuvalikko](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3.  Kirjoita hakukenttään henkilön henkilötieto.
4.  Napsauta hakukuvaketta.

    ![PowerAppsin osuvuushaun tulokset](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

Sisällössäsi olevat henkilötiedot tallennetaan yleensä keskeisiin entiteetteihin, joita ovat esimerkiksi tilit, yhteystiedot, liidit ja mahdollisuudet. On silti omalla vastuullasi ylläpitää hakemistoa yksityishenkilöiden henkilötietojen tallennussijainneista.

### <a name="rectify"></a>Korjaaminen
CDS-järjestelmänvalvoja voi päivittää yksityishenkilöjen henkilötietoja käyttämällä osuvuushaun hakutulosluetteloa.  Käyttäjien henkilötietoja on kuitenkin saatettu tallentaa myös muihin mukautettuihin entiteetteihin.  CDS-järjestelmänvalvojan vastuulla on ylläpitää näiden mukautettujen entiteettien hakemistoa ja tehdä tarvittavat päivitykset henkilöjen henkilötietoihin.

Osuvuushaun tuloksissa:

1.  Napsauta kohdetta, josta henkilön henkilötietoja löytyi.
2.  Päivitä tiedot tarvittavilta osiltaan.
3.  Valitse Tallenna.

    ![PowerApps-tilitiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-account-details.png)

### <a name="export"></a>Vieminen
Voit taltioida näyttökuvan ja jakaa sen DSR-pyytäjälle seuraamalla alla olevia ohjeita.

[PowerApps-hallintakeskuksessa](https://admin.powerapps.com/):
1.  Siirry Ympäristöt-välilehdelle.
2.  Valitse Ympäristöt-luettelosta ympäristö.
3.  Napsauta Dynamics 365 -hallintakeskuksen linkkiä.
4.  Napsauta ympäristön nimeä.
5.  Valitse **Haku**-kuvaketta.
6.  Valitse Osuvuushaku.
7.  Kirjoita hakukenttään henkilön henkilötieto.
8.  Napsauta hakukuvaketta.
9.  Etsi kohde ja kaksoisnapsauta sitä.
10. Sieppaa näyttökuva painamalla <alt> + <PrtScn>.
11. Tallenna näyttökuva tiedostoon.
12. Voit lähettää tiedoston sitten DSR-pyytäjälle.

### <a name="delete"></a>Poistaminen

CDS-järjestelmänvalvoja voi poistaa yksityishenkilön henkilötietoja tietueista, joihin ne on tallennettu.  CDS-järjestelmänvalvoja voi joko (1) poistaa tietueen, johon henkilötietoja on tallennettu, tai (2) poistaa henkilötietojen sisällön tietueesta.  

> [!NOTE]
> CDS-järjestelmänvalvoja voi mukauttaa ympäristöä siten, että tietueen poistamisen entiteetistä estetään. Jos ympäristö määritetään näin, henkilötietojen sisältö on poistettava tietueesta itse tietueen poistamisen sijaan.

Osuvuushaun tuloksissa:
1.  Napsauta kohdetta, josta henkilön henkilötietoja löytyi.
2.  Napsauta valintanauhan Poista-kuvaketta (huomautus: tämä kuvake ei ole käytössä, jos tietuetta ei voi poistaa).

    ![PowerApps-tilin poistaminen](./media/common-data-service-gdpr-dsr-guide/powerapps-account-delete.png)

## <a name="personal-data-stored-in-common-data-service-previous-version-databases"></a>Common Data Service (aiempi versio) -tietokantoihin tallennetut henkilötiedot

### <a name="prerequisites"></a>Edellytykset

Olet mahdollisesti tallentanut yksityishenkilöiden, kuten omien asiakkaittesi tai käyttäjiesi, henkilötietoja CDS-entiteettien sisältöön.  

Jos yksityishenkilö lähettää organisaatiollesi DSR-pyynnön, CDS-järjestelmänvalvojan on etsittävä kaikki entiteetit, joissa henkilöön sovelluksessasi viitataan.  CDS-järjestelmänvalvojan vastuulla on ylläpitää hakemistoa siitä, minne henkilötietoja tallennetaan erilaisissa käyttämissäsi entiteeteissä, jotta voit vastata yksityishenkilöjen DSR-pyyntöihin.

Sisällössäsi olevia henkilötietoja voi sitten viedä, korjata tai poistaa entiteetissä käyttämällä tuotteen sisäistä toimintoa.  

### <a name="discover"></a>Etsintä
Kun CDS-järjestelmänvalvoja vastaanottaa DSR-pyynnön yksityishenkilöltä, järjestelmänvalvojan täytyy tunnistaa, mitkä ympäristöt tai CDS-esiintymät sisältävät tämän henkilön henkilötietoja.  Organisaatiossasi tulisi kehittää käytäntöjä ja menettelytapoja, joilla ylläpidetään hakemistoa yksityishenkilöiden henkilötietojen tallentamiseen käytettävistä ympäristöistä, esiintymistä ja entiteeteistä. Siten pystyt tunnistamaan sisältöösi tallennetut henkilötiedot.

Yksityishenkilöjen henkilötietoja voi olla seuraavissa kohteissa:

|Henkilötietoja sisältävät resurssit | Tarkoitus | Sivuston käyttö |    Ohjelmallinen käyttö
| --- | --- | --- | ---
|Entiteetin tietueet | Tämän avulla liiketoimintatapahtumat taltioidaan vastaavaan liiketoimintaentiteettiin. | PowerApps Maker Portal |    Ei

#### <a name="entity-records"></a>Entiteetin tietueet
Yksityishenkilöiden henkilötietoja voidaan tallentaa mihin tahansa liiketoimintaentiteettiin.
Tämä Common Data Servicen versio sisältää oman tietokantarakenteensa ja infrastruktuurinsa.  Sillä on myös omat entiteettinsä, joiden hallinta tapahtuu käyttämällä [PowerApps-sivustoa](http://web.powerapps.com/).

Näet entiteettiluettelon seuraavasti:

1.  Valitse ympäristö.

    ![PowerAppsin vanhat entiteetit](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2.  Valitse **Tiedot**  >  **Entiteetit**-välilehti.
3.  Valitse entiteetti, kuten tilin entiteetti.

    ![PowerAppsin vanhojen entiteettien tietoluettelo](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

4.  Napsauta entiteettiä.
5.  Valitse **Tiedot**-välilehti. Näet luettelon entiteetin tietueista.

    ![PowerAppsin vanhan tilin tiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

6.  Napsauta **Vie tiedot** -kuvaketta.
7.  Avaa Excel-laskentataulukko, kun vienti on valmis.
8.  Valitse Ota muokkaaminen käyttöön -ruutu.
9.  Napsauta hakukuvaketta.
10. Kirjoita haettava henkilötieto.
Sisällössäsi olevat henkilötiedot tallennetaan yleensä keskeisiin entiteetteihin, joita ovat esimerkiksi tilit, yhteystiedot, liidit, mahdollisuudet tai työntekijät. On silti omalla vastuullasi ylläpitää hakemistoa yksityishenkilöiden henkilötietojen tallennussijainneista.
11. **Hae yksityishenkilön henkilötiedot toistamalla yllä olevat vaiheet kullekin liiketoimintaentiteetille** käyttämällä hakemistoa entiteeteistä, joihin henkilötiedot on tallennettu.

### <a name="rectify"></a>Korjaaminen
Jos rekisteröity pyytää sinua korjaamaan henkilötietoja, joita organisaatiosi tietoihin sisältyy, sinun ja organisaatiosi täytyy päättää, hyväksyttekö pyynnön.  Tietojen korjaaminen saattaa tarkoittaa henkilötietojen muokkaamista ja poistamista tiedostossa tai muussa kohteessa.

Azure Active Directoryn avulla voit hallita Common Data Service for Appsissa olevia loppukäyttäjiesi käyttäjätietoja (henkilötietoja). Yritysasiakkaat voivat hallita rekisteröityjen korjauspyyntöjä, esimerkiksi rajoitetuilla muokkaustoiminnoilla tietyn Microsoft-palvelun luoteen mukaisesti.  Rekisterinpitäjänä Microsoft ei tarjoa mahdollisuutta korjata järjestelmän luomia lokeja, sillä ne kuvaavat faktapohjaisia toimintoja ja täten Microsoftin palveluiden tapahtumien historiatietoja.  

Lisätietoja on ohjeaiheessa [GDPR: rekisteröityjen tietopyynnöt (DSR-pyynnöt)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

CDS-ympäristössä sijaitsevien henkilötietojen korjaaminen tapahtuu viemällä entiteetin tiedot Excel-laskentataulukkoon, päivittämällä tiedot taulukossa ja tuomalla päivitykset takaisin tietokantaan.
CDS-järjestelmänvalvojan vastuulla on tunnistaa kaikki entiteetit, joihin yksityishenkilöiden henkilötietoja on tallennettu, ja toistaa alla olevat vaiheet jokaiselle näistä entiteeteistä.

[PowerApps-sivustossa](http://web.powerapps.com/):

1.  Valitse **Tiedot**  >  **Entiteetit**.
2.  Napsauta entiteettiä, kuten tiliä.
3.  Valitse **Tiedot**-vaihtoehto.
4.  Napsauta **Vie tiedot** -kuvaketta.
5.  Napsauta **Avaa Excelissä** -kuvaketta, kun vienti on valmis.
6.  **Ota muokkaaminen käyttöön** Excel-laskentataulukossa ja päivitä henkilötiedot.
7.  **Tallenna** päivitetty laskentataulukko. Valitse **Tallenna nimellä**, niin näet tiedoston sijainnin.

    ![PowerAppsin vanhan tilin tiedot](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

8.  Tee tarvittavat päivitykset henkilötietoihin.
9.  Tallenna päivitykset.
10. Valitse Tiedot > Entiteetit > Tili ja napsauta lomakkeen Tuo tiedot -kuvaketta.
11. Napsauta Haku-ruutua.
12. Valitse tiedosto, joka sisältää tekemäsi päivitykset.
13. Napsauta Avaa-ruutua.
14. Napsauta Tuo-painiketta.

### <a name="export"></a>Vieminen

Voit tarkastella jokaisen entiteetin henkilötietoja ja viedä niitä Excel-laskentataulukkoon.

[PowerApps-sivustossa](http://web.powerapps.com/):

1.  Valitse **Tiedot**  >  **Entiteetit**.
2.  Valitse **entiteetti**, jonka tietoja haluat tarkastella ja viedä.
3.  Valitse **Tiedot**-vaihtoehto.
4.  Napsauta **Vie tiedot** -kuvaketta. Vienti tapahtuu taustatoimintona, ja saat ilmoituksen, kun se on valmis.
5. Voit tarkastella vietyjä tietoja napsauttamalla Avaa Excelissä -kuvaketta.

### <a name="delete"></a>Poistaminen
Voit poistaa entiteetteihin tallennettuja henkilötietoja käyttämällä tietojen vienti- ja tuontitoimintoa.

CDS-järjestelmänvalvojan vastuulla on tunnistaa kaikki entiteetit, joihin yksityishenkilöiden henkilötietoja sisältyy, ja toistaa seuraavat vaiheet jokaiselle entiteeteistä.

[PowerApps-sivustossa](http://web.powerapps.com/):

1.  Valitse **Tiedot**  >  **Entiteetit**.
2.  Vieritä **entiteettiluetteloa** alaspäin ja etsi entiteetti, jonka henkilötiedot haluat poistaa.
3.  Napsauta entiteettiä.
4.  Valitse **Tiedot**-vaihtoehto.
5.  Napsauta **Vie tiedot** -kuvaketta.
6.  Napsauta **Avaa Excelissä** -kuvaketta, kun vienti on valmis.
7.  **Ota muokkaaminen käyttöön** Excel-laskentataulukossa.
8.  **Tallenna** päivitetty laskentataulukko. Valitse Tallenna nimellä, niin näet tiedoston sijainnin.
9.  Poista poistettavien henkilötietotietueiden rivit.
10. Tallenna päivitykset.
11. Napsauta **Entiteetit**-lomakkeen **Tuo tiedot** -kuvaketta.
12. Napsauta **Haku**-ruutua.
13. Valitse tiedosto, joka sisältää tekemäsi päivitykset.
14. Napsauta **Open**-ruutua.
15. Napsauta Tuo-painiketta.

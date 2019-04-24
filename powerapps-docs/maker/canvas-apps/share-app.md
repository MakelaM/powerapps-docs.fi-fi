---
title: Pohjaan perustuvan sovelluksen jakaminen | Microsoft Docs
description: Jaa pohjaan perustuva sovelluksesi antamalla käyttäjille käyttöoikeus sen suorittamiseen tai muokkaamiseen
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 11/28/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 34cf740bb029440480618a180ac45bc094c061d5
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61539861"
---
# <a name="share-a-canvas-app-in-powerapps"></a>Pohjaan perustuvan sovelluksen jakaminen PowerAppsissa

Kun olet luonut pohjaan perustuvan sovelluksen, joka vastaa liiketoiminnan tarpeiseen, määritä organisaatiosi käyttäjät, jotka voivat suorittaa sovelluksen, muokata sitä ja jopa jakaa sen uudelleen. Määrittä kukin käyttäjä nimen perusteella tai määritä käyttöoikeusryhmä Azure Active Directoryssä. Jos kaikki hyötyisivät sovelluksestasi, määritä, että koko organisaatio voi suorittaa sen.

> [!IMPORTANT]
> Jaettu sovelluksen toimisi haluamallasi tavalla, on myös hallita käyttöoikeuksia tietolähteeseen tai tietolähteisiin, johon sovellus perustuu, kuten [Common Data Service-](#common-data-service) tai [Excel](share-app-data.md). Voit myös joutua jakamaan sovelluksen perustana toimivia [muita resursseja](share-app-resources.md), kuten työnkulkuja, yhdyskäytäviä tai yhteyksiä.

## <a name="prerequisites"></a>Edellytykset

Ennen kuin jaat sovelluksen, tallenna sen pilvipalveluun (ei paikallisesti) ja julkaise se sitten.

- Anna sovelluksellesi kuvaava nimi ja selkeä kuvaus niin, että käyttäjät tietävät, mitä sovellus tekee ja se on helposti löydettävissä luettelossa. Valitse PowerApps Studiossa **Tiedosto**-valikko, valitse valikosta **Sovellusasetukset**, määritä nimi ja kirjoita tai liitä kuvaus.

- Aina, kun olet tehnyt muutoksia, sinun täytyy tallentaa ja julkaista sovellus uudelleen, jos haluat, että muut näkevät muutoksesi.

## <a name="share-an-app"></a>Sovelluksen jakaminen

1. [Kirjaudu](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerAppsiin ja valitse **Sovellukset** lähellä vasenta reunaa.

    ![Näytä sovellusluettelo](./media/share-app/file-apps.png)

1. Valitse sovellus, jonka haluat jakaa valitsemalla sen kuvake.

    ![Valitse sovellus](./media/share-app/select-app.png)

1. Valitse nauhan, **Jaa**.

    ![Avaa jakonäyttö](./media/share-app/banner-share.png)

1. Määritä nimi tai alias käyttäjän tai käyttöoikeusryhmän nimi Azure Active Directory, joiden kanssa haluat jakaa sovelluksen.

    - Salli koko organisaation suorittaa sovelluksen (mutta ei muokata tai jakaa sen), kirjoita **kaikki** jakamisen paneelin.
    - Voit jakaa sovelluksen ja aliaksia, kutsumanimi tai näistä yhdistelmää luettelo (esimerkiksi **Jane Doe &lt; jane.doe@contoso.com>**) Jos kohteita on erotettu toisistaan puolipisteellä. Jos useampi kuin yksi henkilö on sama nimi, mutta eri aliaksia, ensimmäisen löydetyn henkilön lisätään luetteloon. Työkaluvihje tulee näkyviin, jos nimi tai alias on jo määritetty, tai ei voi ratkaista. 
    
    ![Määritä käyttäjät ja muiden omistajien](./media/share-app/share-everyone.png)

    > [!NOTE]
    > Et voi jakaa sovelluksen jakeluryhmän organisaatiosi tai käyttäjän tai ryhmän organisaatiosi ulkopuolella.

1. Jos haluat sallia, joille jaat sovelluksen muokata ja jakaa sen (lisäksi käynnissä sen), valitse **toinen omistaja** valintaruutu.

    Et voi myöntää **toinen omistaja** oikeuksia suojaus ryhmän, jos voit [luoda sovelluksen ratkaisu](add-app-solution.md).
    
    > [!NOTE]
    > Oikeuksia kaksi kukaan voit muokata sovellusta samaan aikaan. Jos yksi henkilö avaa sovellus muokkaamista varten, muut voivat suorittaa sen, mutta ei muokata.

1. Jos sovelluksesi muodostaa yhteyden tietoihin, jonka käyttäjät tarvitsevat käyttöoikeudet, määritä ne.

    Sovelluksesi saattaa esimerkiksi yhdistää entiteetin Common Data Service-tietokannassa. Kun jaat olevan sovelluksen, jakamisen paneelin kehottaa kyseisen entiteetin suojauksen hallinta.

    ![Käyttöoikeuksien määrittäminen](./media/share-app/set-permissions.png)

    Katso lisätietoja entiteetin suojauksen hallinta [entiteetin käyttöoikeuksien hallinta](share-app.md#manage-entity-permissions) jäljempänä tässä aiheessa.

1. Jos haluat löytää sovelluksesi, valitse ihmisten **lähettää sähköpostikutsun uusille käyttäjille** valintaruutu.

1. Jaa paneelin alareunasta Valitse **jakaa**.

    Kaikille, joille jaoit sovelluksen sitä voi käyttää PowerApps Mobilessa mobiililaitteessa tai appsourcessa [Dynamics 365](https://home.dynamics.com) selaimessa. Muiden omistajien voit muokata ja jakaa sovelluksen [Powerappsin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    Jos lähetit sähköpostikutsun, kaikille, joille jaoit sovelluksen suorittaa sen valitsemalla linkki kutsussa.

    - Jos käyttäjä valitsee olevaa linkkiä mobiililaitteessa, sovellus avautuu PowerApps Mobilessa.
    - Jos käyttäjä valitsee pöytäkone linkkiä, sovellus avautuu selaimessa.

    Muiden omistajien, jotka saavat kutsun saada toisen linkki, joka avaa PowerApps Studio sovelluksen muokkaamista varten.

Voit muuttaa käyttäjän tai käyttöoikeusryhmän käyttöoikeuksia valitsemalla hänen nimensä ja suorittamalla sitten jommankumman seuraavista toimista:

- Suorita sovellus, mutta ei enää muokata tai jakaa sen muiden omistajien, poista **toinen omistaja** valintaruutu.
- Lopettaa sovelluksen jakaminen kyseisen käyttäjän tai ryhmän, valitse Poista (x)-kuvaketta.

## <a name="security-group-considerations"></a>Käyttöoikeusryhmän huomioon otettavia seikkoja

- Jos jaat sovelluksen käyttöoikeusryhmän kanssa, kaikki ryhmään kuuluvat ja siihen myöhemmin liittyvät jäsenet saavat käyttöoikeudet, jotka olet kyseiselle ryhmälle määrittänyt. Kaikki ryhmästä poistuvat menettävät käyttöoikeutensa, paitsi jos he kuuluvat toiseen ryhmään, jolla on käyttöoikeudet, tai annat heille käyttöluvan yksittäisinä käyttäjinä.
- Jokaisella käyttöoikeusryhmän jäsenellä on samat käyttöoikeudet sovellukseen kuin ryhmällä yleensä. Voit kuitenkin halutessasi määrittää yhdelle tai useammalle ryhmän jäsenelle laajemmat käyttöoikeudet. Esimerkiksi antaa käyttöoikeusryhmälle A oikeuksia suorittaa sovelluksen, mutta voit myös antaa käyttäjälle B kuuluu ryhmään, **toinen omistaja** käyttöoikeus. Jokainen käyttöoikeusryhmän jäsen voi suorittaa sovelluksen, mutta vain käyttäjä B voi muokata sitä. Jos annat käyttöoikeusryhmälle A **toinen omistaja** käyttöoikeuden ja käyttäjälle B oikeuksia suorittaa sovelluksen, kyseinen käyttäjä voi yhä muokata sovellusta.

## <a name="manage-entity-permissions"></a>Entiteetin käyttöoikeuksien hallinta

### <a name="common-data-service"></a>Common Data Service

Jos luot sovelluksen Common Data Service-perusteella, sinun on myös varmistettava, että käyttäjät, joille jaat sovelluksen entiteetin tai entiteetit, joita sovellus hyödyntää tarvittavia käyttöoikeuksia. Tarkemmin sanottuna käyttäjille, jotka on kuuluttava käyttöoikeusrooli, joka suorittaa tehtäviä, kuten luominen, lukeminen, kirjoittaminen ja tietueiden poistaminen. Monissa tapauksissa haluat luoda tarkka käyttöoikeuksilla voit suorittaa sovelluksen käyttäjät tarvitsevat vähintään yksi mukautettu käyttöoikeusrooli. Voit määrittää roolin sitten kukin käyttäjä tarpeen mukaan.

> [!NOTE]
> Tätä kirjoitettaessa Määritä käyttöoikeusroolit yksittäisten käyttäjien, mutta ei käyttöoikeusryhmiä.

#### <a name="prerequisite"></a>Edellytys

Seuraavat kaksi toimintojen suorittamista, sinulla on oltava **järjestelmänvalvojaan** Common Data Service-tietokannan käyttöoikeuksia.

#### <a name="create-a-security-role"></a>Käyttöoikeusroolin luominen

1. Valitse jakamisen paneelin **käyttöoikeudet** kohdassa **tietojen käyttöoikeudet**, ja valitse sitten **käyttöoikeusrooleja** linkki.

    ![Avaa käyttöoikeusroolit](media/share-app/security-roles.png)

1. Valitse **Kaikki roolit**, valitse sitten **Uusi** ja kirjoita tai liitä luotavan roolin nimi.

    ![Luo käyttöoikeusrooli](media/share-app/new-role.png)

1. Valitse yksi tai useita välilehtiä löytääksesi entiteetin tai entiteetit, joita sovellus käyttää, valitse sitten käyttöoikeudet, jotka haluat myöntää käyttöoikeusroolille.

    Esimerkiksi Tässä kaaviossa näkyy, **tärkeimmät tietueiden** välilehti sisältää **tilit** entiteetin ja käyttäjät, joihin tämä käyttöoikeusrooli on määritetty voi luoda, lukea, kirjoittaa ja poistaa tietueiden kyseisen entiteetin .

    ![Määritä käyttöoikeudet](media/share-app/grant-access.png)

1. Valitse **Tallenna ja sulje**.

#### <a name="assign-a-user-to-a-role"></a>Roolin määrittäminen käyttäjälle

1. Valitse jakamisen paneelin **käyttöoikeudet** kohdassa **tietojen käyttöoikeudet**, ja valitse sitten **käyttäjät** linkki.

    ![Käyttäjät-linkki](media/share-app/open-users.png)

1. Kirjoita tai liitä käyttäjä nimi, jolle haluat roolin määrittää, oikeaan yläkulmaan ja valitse sitten haku-kuvake.

    ![Käyttäjien hakeminen](media/share-app/search-users.png)

1. Osoita hakutuloksissa haluttuun tulokseen ja valitse sitten ilmestyvä valintaruutu.

1. Valitse yläpalkista **roolien hallinta**.

1. Valitse tulevassa valintaikkunassa valintaruudut **Common Data Service-käyttäjän** ja käyttäjä tarvitsee sovelluksen roolin ja valitse sitten **OK.**

    ![Roolin määrittäminen käyttäjälle](media/share-app/assign-users.png)

### <a name="common-data-service-previous-version"></a>Common Data Service (aiempi versio)

Kun jaat sovelluksen, joka perustuu Common Data Service-vanhemman version, sinun täytyy jakaa palvelun suorituksenaikainen käyttöoikeus erikseen. Jos sinulla ei ole lupaa jakamiseen, ota yhteyttä ympäristön järjestelmänvalvojaan.

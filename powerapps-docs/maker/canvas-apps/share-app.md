---
title: Sovelluksen jakaminen | Microsoft Docs
description: Jaa sovelluksesi antamalla käyttäjille käyttöoikeus sen suorittamiseen tai muokkaamiseen
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 07/11/2018
ms.author: anneta
ms.openlocfilehash: 197eb5223c0945a7cb80d8b187aaf44c871e798c
ms.sourcegitcommit: 79a58f1b6880cbc512b64cde71a4d532cebe5bed
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/18/2018
ms.locfileid: "39137018"
---
# <a name="share-an-app-in-powerapps"></a>Sovelluksen jakaminen PowerAppsissa

Kun olet luonut sovelluksen, joka vastaa liiketoiminnan tarpeiseen, määritä organisaatiosi käyttäjät, jotka voit suorittaa sovelluksen ja muokata ja jopa uudelleenjakaa sen. Määrittä kukin käyttäjä nimen perusteella tai määritä käyttöoikeusryhmä Azure Active Directoryssä. Jos kaikki hyötyisivät sovelluksestasi, määritä, että koko organisaatio voi suorittaa sen.

> [!IMPORTANT]
> Jotta jaettu sovellus toimisi haluamallasi tavalla, sinun on myös hallittava tietolähteiden käyttöoikeuksia tai niiden lähteiden, joihin sovellus perustuu, kuten [Common Data Service for Apps -palvelun](#common-data-service-for-apps) tai [Excelin](share-app-data.md) käyttöoikeuksia. Voit myös joutua jakamaan sovelluksen perustana toimivia [muita resursseja](share-app-resources.md), kuten työnkulkuja, yhdyskäytäviä tai yhteyksiä.

## <a name="prerequisites"></a>Edellytykset

Ennen kuin jaat sovelluksen, tallenna sen pilvipalveluun (ei paikallisesti) ja julkaise se sitten.

- Anna sovelluksellesi kuvaava nimi ja selkeä kuvaus niin, että käyttäjät tietävät, mitä sovellus tekee ja se on helposti löydettävissä luettelossa. Valitse PowerApps Studiossa **Tiedosto**-valikko, valitse valikosta **Sovellusasetukset**, määritä nimi ja kirjoita tai liitä kuvaus.

- Aina, kun olet tehnyt muutoksia, sinun täytyy tallentaa ja julkaista sovellus uudelleen, jos haluat, että muut näkevät muutoksesi.

## <a name="share-an-app"></a>Sovelluksen jakaminen

1. [Kirjaudu](https://web.powerapps.com) PowerAppsiin ja valitse **Sovellukset** lähellä vasenta reunaa.

    ![Näytä sovellusluettelo](./media/share-app/file-apps.png)

1. Valitse kolmea pistettä (...) sen sovelluksen kohdalla, jonka haluat jakaa ja valitse sitten **Jaa**.

    ![Avaa jakonäyttö](./media/share-app/ellipsis-share.png)

1. Määritä, keiden käyttäjien tai Azure Active Directory -käyttöoikeusryhmien kanssa haluat jakaa sovelluksen.

    > [!NOTE]
    > Et voi jakaa sovelluksia organisaatiosi jakeluryhmän tai organisaatiosi ulkopuolisten käyttäjien tai ryhmien kanssa.

    ![Määritä käyttäjät](./media/share-app/share-list.png)

    Voit myös jakaa sovelluksen koko organisaation kesken niin, että kaikki voivat käyttää sitä mutta eivät muokata tai jakaa sitä.

1. (valinnainen) Auttaaksesi käyttäjiä löytämään sovelluksesi, valitse valintaruutu lähettääksesi heille sähköpostikutsun.

    Kutsun sisältää linkin, jonka avulla käyttäjät voivat suorittaa sovelluksen.

    - Jos käyttäjä valitsee linkin pöytätietokoneessa, sovellus avautuu [Dynamics 365](http://home.dynamics.com):ssa.
    - Jos käyttäjä valitsee linkin mobiililaitteessa, sovellus avautuu PowerApps Mobilessa.

    Jos annat käyttäjille oikeuden muokata sovellusta, viesti sisältää myös erillisen linkin, joka avaa sovelluksen PowerApps Studiossa muokkaamista varten.

    Riippumatta siitä, lähetätkö kutsun, käyttäjät voivat suorittaa sovelluksen [Dynamics 365:n](http://home.dynamics.com) AppSourcesta. Käyttäjät, joilla oikeus **muokata** sovellusta, voivat tehdä niin myös [Powerappsin](http://web.powerapps.com) kautta.

1. Määritä kunkin käyttäjän tai käyttöoikeusryhmän käyttöoikeudet ja valitse sitten **Tallenna**.

    - **Voivat käyttää**: käyttäjät voivat käyttää, mutta eivät jakaa sovellusta.
    - **Voivat muokata**: käyttäjät voivat suorittaa sovelluksen, muokata sitä ja jakaa mukautetun version muiden käyttäjien kanssa.

        ![Määritä käyttöoikeudet](./media/share-app/edit-use.png)

    Voit muuttaa käyttäjän tai käyttöoikeusryhmän käyttöoikeuksia valitsemalla käyttäjän tai ryhmän vieressä olevan alaspäin osoittavan nuolen ja määrittämällä sitten eri käyttöoikeudet.

    Jos haluat poistaa kaikki käyttäjän tai ryhmän käyttöoikeudet, valitse**x**-kuvake kyseisen käyttäjän tai ryhmän kohdalla.

## <a name="security-group-considerations"></a>Käyttöoikeusryhmän huomioon otettavia seikkoja

- Jos jaat sovelluksen käyttöoikeusryhmän kanssa, kaikki ryhmään kuuluvat ja siihen myöhemmin liittyvät jäsenet saavat käyttöoikeudet, jotka olet kyseiselle ryhmälle määrittänyt. Kaikki ryhmästä poistuvat menettävät käyttöoikeutensa, paitsi jos he kuuluvat toiseen ryhmään, jolla on käyttöoikeudet, tai annat heille käyttöluvan yksittäisinä käyttäjinä.
- Jokaisella käyttöoikeusryhmän jäsenellä on samat käyttöoikeudet sovellukseen kuin ryhmällä yleensä. Voit kuitenkin halutessasi määrittää yhdelle tai useammalle ryhmän jäsenelle laajemmat käyttöoikeudet. Voit esimerkiksi antaa käyttöoikeusryhmälle A **Voivat käyttää** -käyttöoikeuden, mutta voit myös antaa tähän ryhmään kuuluvalle käyttäjälle B **Voivat muokata** -käyttöoikeuden. Jokainen käyttöoikeusryhmän jäsen voi suorittaa sovelluksen, mutta vain käyttäjä B voi muokata sitä. Jos annat käyttöoikeusryhmälle A **Voivat muokata** -käyttöoikeuden ja käyttäjälle B **Voivat käyttää** -käyttöoikeuden, kyseinen käyttäjä voi yhä muokata sovellusta.

## <a name="manage-entity-permissions"></a>Entiteetin käyttöoikeuksien hallinta

### <a name="common-data-service-for-apps"></a>Microsoft Common Data Service for Apps

Jos luot Common Data Service for Apps -palveluun perustuvan sovelluksen, sinun on varmistettava, että sitä suorittavilla käyttäjille on sovelluksen hyödyntämälle entiteetille tai entiteeteille tarvittavat käyttöoikeudet. Kyseisten käyttäjien on siis kuuluttava käyttöoikeusrooliin, joka voi suorittaa sellaisia tehtäviä kuin luominen, lukeminen, kirjoittaminen ja/tai asianmukaisten tietueiden poistaminen. Jos sinulla on kyseisen ympäristön tietokannan **järjestelmänvalvojan** tai **järjestelmämukauttajan** käyttöoikeudet, voit luoda mukautetun roolin ja lisätä siihen käyttäjiä.

#### <a name="create-a-security-role"></a>Käyttöoikeusroolin luominen

1. [Kirjaudu sisään PowerAppsiin](https://web.powerapps.com) ja varmista, että olet samassa ympäristössä kuin sovellus, jonka haluat jakaa.

1. Valitse oikeasta yläkulmasta hammaspyöräkuvake ja valitse sitten **lisämukautukset**.

    ![Avaa lisämukautukset-ruutu](media/share-app/advanced-customizations.png)

1. Valitse **Käyttöoikeusroolit**-linkki.

    ![Avaa käyttöoikeusroolit](media/share-app/security-roles.png)

1. Valitse **Kaikki roolit**, valitse sitten **Uusi** ja kirjoita tai liitä luotavan roolin nimi.

    ![Luo käyttöoikeusrooli](media/share-app/new-role.png)

1. Valitse yksi tai useita välilehtiä löytääksesi entiteetin tai entiteetit, joita sovellus käyttää, valitse sitten käyttöoikeudet, jotka haluat myöntää käyttöoikeusroolille.

    Tässä kuvassa näkyy esimerkiksi, että käyttöoikeusrooli voi luoda, lukea, kirjoittaa ja poistaa tietueita Tili-entiteetissä, joka on näkyvillä **Ydintietueiden**-välilehdellä.

    ![Määritä käyttöoikeudet](media/share-app/grant-access.png)

1. Valitse **Tallenna ja sulje**.

#### <a name="assign-a-user-to-a-role"></a>Määritä käyttäjälle rooli

1. Avaa **Lisämukautukset**-ruutu edellä kuvatun tavan mukaisesti ja valitse sitten **Käyttäjät**-linkki.

    ![Käyttäjät-linkki](media/share-app/open-users.png)

1. Kirjoita tai liitä käyttäjä nimi, jolle haluat roolin määrittää, oikeaan yläkulmaan ja valitse sitten haku-kuvake.

    ![Käyttäjien hakeminen](media/share-app/search-users.png)

1. Osoita hakutuloksissa haluttuun tulokseen ja valitse sitten ilmestyvä valintaruutu.

1. Valitse yläpalkista **roolien hallinta**.

1. Valitse näyttöön avautuvasta valintaikkunasta**Common Data Service -käyttäjän** ja sovelluksesi edellyttämän roolin valintaruudut käyttäjälle ja valitse sitten **OK.**

    ![Roolin määrittäminen käyttäjälle](media/share-app/assign-users.png)

### <a name="common-data-service-previous-version"></a>Common Data Service (aiempi versio)

Kun jaat sovelluksen, joka perustuu Common Data Servicen vanhempaan versioon, sinun täytyy jakaa palvelun suorituksenaikainen käyttöoikeus erikseen. Jos sinulla ei ole lupaa jakamiseen, ota yhteys ympäristön järjestelmänvalvojaan.
---
title: Sovelluksen jakaminen | Microsoft Docs
description: Jaa sovelluksesi antamalla käyttäjille käyttöoikeus sen suorittamiseen tai muokkaamiseen
services: ''
suite: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 22950d866ed8e61dd0824701ef8af86f5bed2dc6
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="share-an-app-in-powerapps"></a>Sovelluksen jakaminen PowerAppsissa
Sovellusten luominen liiketoiminnan tarpeisiin on hienoa, mutta PowerAppsin todellisena etuna on sovellusten jakaminen muille. Tässä aiheessa kerrotaan, miten jaat sovelluksia tietyille käyttäjille, käyttöoikeusryhmille tai koko organisaatiolle.

## <a name="specify-an-app"></a>Sovelluksen määritys
1. Kirjaudu PowerAppsiin ja napsauta tai napauta sitten vasemman reunan lähellä olevaa kohtaa **Sovellukset**.

    ![Näytä sovellusluettelo](./media/share-app/file-apps.png)

1. Napsauta tai napauta kolmea pistettä (...) sen sovelluksen kohdalla, jonka haluat jakaa, ja napsauta tai napauta **Jaa**.

    ![Avaa jakonäyttö](./media/share-app/ellipsis-share.png)

## <a name="share-an-app"></a>Sovelluksen jakaminen
1. Määritä, keiden Azure Active Directory -käyttäjien tai -käyttöoikeusryhmien kanssa sovellus jaetaan ja lähetetäänkö heille tästä ilmoitus sähköpostilla.

    Voit myös jakaa sovelluksen koko organisaation kesken niin, että kaikki voivat käyttää sitä mutta eivät muokata tai jakaa sitä.

    ![Määritä käyttäjät](./media/share-app/share-list.png)

1. Määritä käyttöoikeustasot ja napsauta tai napauta sitten **Tallenna**.

    * **Voivat käyttää**: Käyttäjät tai ryhmät voivat käyttää, mutta eivät jakaa sovellusta.
    * **Voivat muokata**: Käyttäjät tai ryhmät voivat käyttää sovellusta ja mukauttaa sitä sekä jakaa sen mukautetun version muiden käyttäjien kanssa.

        ![Määritä käyttöoikeudet](./media/share-app/edit-use.png)

Jos haluat muuttaa käyttäjän tai ryhmän käyttöoikeuksia, toista tämän menettelyn vaihe 1 ja määritä kyseiselle käyttäjälle tai ryhmälle eri asetus käyttöoikeusluettelosta. Jos haluat poistaa kaikki käyttäjän tai ryhmän käyttöoikeudet, napsauta tai napauta **x**-kuvaketta kyseisen käyttäjän tai ryhmän kohdalla.

### <a name="send-email-notification"></a>Lähetä sähköposti-ilmoitus
Kun jaat sovelluksen, voit valita, ilmoitetaanko jakamisesta käyttäjille tai käyttöoikeusryhmälle sähköpostitse. Jos valitset tämän vaihtoehdon, käyttäjälle, käyttäjille tai käyttöoikeusryhmille lähetetään ilmoitus sähköpostitse. Sähköpostiviesti sisältää linkin, jonka kautta käyttäjät voivat käyttää sovellusta. Tarvittaessa käyttäjiä kehotetaan rekisteröitymään ja lataamaan PowerApps.

Ilmoitus sisältää erityyppisen linkin määrittämäsi käyttöoikeuden mukaan:

- Kun jaat **Voivat käyttää** -käyttöoikeudellisen sovelluksen, sähköpostiviesti sisältää linkin sovelluksen suorittamiseen.
- Kun jaat **Voivat muokata** -käyttöoikeudellisen sovelluksen, sähköpostiviesti sisältää linkin sovelluksen suorittamiseen tai muokkaamiseen.

### <a name="how-do-my-users-see-the-app-i-shared"></a>Miten käyttäjät näkevät jakamani sovelluksen?
Kun olet jakanut sovelluksen yhden tai useamman käyttäjän tai käyttöoikeusryhmän kanssa, tapa, jolla he näkevät sovelluksen, vaihtelee jaetun käyttöoikeuden mukaan.

##### <a name="if-you-shared-an-app-with-user-permission"></a>Jos sovellus on jaettu *Käyttäjä*-käyttöoikeudella
Henkilöt, joille jaat sovelluksen saavat sähköposti-ilmoituksen, jos valitsit kyseisen valintaruudun sovelluksen jakamisnäytössä. Sähköpostiviestissä on linkki, jota napsauttamalla tai napauttamalla käyttäjä voi suorittaa sovelluksen [Dynamics 365](http://home.dynamics.com):ssä. Lisäämme pian tuen universaaleille linkeille. Tämän jälkeen sovellus aukeaa PowerApps Studiossa tai PowerApps Mobilessa, jos jompikumpi niistä on asennettuna.

Käyttäjät voivat myös löytää sovelluksen [Dynamics 365](http://home.dynamics.com):n AppSourcesta (jos et esimerkiksi lähettänyt sähköpostiviestiä). [Lue lisää](../../user/app-source.md) siitä, miten käyttäjät voivat ladata sovelluksia AppSourcen kautta.

##### <a name="if-you-shared-an-app-with-contributor-permission"></a>Jos sovellus on jaettu *Osallistuja*-käyttöoikeudella
Henkilöt, joille jaat sovelluksen saavat sähköposti-ilmoituksen, jos valitsit kyseisen valintaruudun sovelluksen jakamisnäytössä. Sähköpostiviestissä on linkki, jota napsauttamalla tai napauttamalla käyttäjä voi suoraan avata sovelluksen muokkaamista varten käyttämällä verkon PowerApps Studiota. Sähköpostiviestissä on myös linkki, joka suorittaa sovelluksen [Dynamics 365](http://home.dynamics.com):ssä. Lisäämme pian tuen universaaleille linkeille. Tämän jälkeen sovellus aukeaa PowerApps Studiossa tai PowerApps Mobilessa, jos jompikumpi niistä on asennettuna.

Käyttäjät voivat myös löytää sovelluksen osoitteesta [powerapps.com](http://web.powerapps.com) (jos et esimerkiksi lähettänyt sähköpostiviestiä). Kyseessä on sovellusten luojien koti, jossa he voivat selata luomiaan sovelluksia tai sovelluksia, jotka on jaettu heille **Osallistuja**-käyttöoikeudella. [Dynamics 365](http://home.dynamics.com) on sen sijaan paikka, jossa käyttäjät voivat suorittaa nopeasti sovelluksia PowerAppsista ja muista yrityssovelluksista.

## <a name="other-things-to-know"></a>Muita tärkeitä tietoja
* Jos haluat jakaa sovelluksen, se täytyy tallentaa pilveen, ei paikallisesti.
* Ennen sovelluksen jakamista on hyvä miettiä, keille käyttäjille tai käyttöoikeusryhmille haluat sen jakaa ja millä rooleilla: **Voivat muokata** vai **Voivat käyttää**. Jos jaat sovelluksen ryhmän kanssa, kaikki ryhmään kuuluvat ja siihen myöhemmin liittyvät jäsenet saavat käyttöoikeudet, jotka olet määrittänyt. Jos jäsen poistuu ryhmästä, hän menettää käyttöoikeutensa, paitsi jos hän kuuluu myös toiseen ryhmään, jolle olet antanut käyttöoikeudet, tai jos annat hänelle erikseen käyttöoikeuden.
* Jokaisella ryhmän jäsenellä on samat käyttöoikeudet sovellukseen kuin ryhmällä yleensä. Voit kuitenkin halutessasi määrittää yhdelle tai useammalle ryhmän jäsenelle laajemmat käyttöoikeudet. Voit esimerkiksi antaa käyttöoikeusryhmälle A **Voivat käyttää** -käyttöoikeuden, mutta voit myös antaa tähän ryhmään kuuluvalle käyttäjälle B **Voivat muokata** -käyttöoikeuden. Jokainen käyttöoikeusryhmän jäsen voi suorittaa sovelluksen, mutta vain käyttäjä B voi muokata sitä. Jos annat käyttöoikeusryhmälle A **Voivat muokata** -käyttöoikeuden ja käyttäjälle B **Voivat käyttää** -käyttöoikeuden, kyseinen käyttäjä voi yhä muokata sovellusta.
* Voit jakaa sovelluksen koko organisaatiolle, mutta harkitse tarkkaan, tarvitseeko jokainen käyttöoikeutta sovellukseen.
* Ota huomioon, että jaettuun sovellukseen tekemäsi muutokset päivittyvät henkilöille, joille jaoit sovelluksen heti, kun teet muutokset. Jos kehität sovellusta, kaikki hyötyvät. Jos vioitat sovellusta, se vaikuttaa kaikkiin.
* Ennen kuin jaat sovelluksen, anna sille merkityksellinen nimi ja kuvaus, jotta ihmiset tietävät sovelluksen tarkoituksen ja voivat helposti valita sen luettelosta. Napsauta tai napauta PowerApps Studion **Tiedosto**-valikosta **Sovelluksen asetukset** ja kirjoita kuvaus.

### <a name="app-sharing-and-the-resources-the-app-uses"></a>Sovelluksen jakaminen ja sen käyttämät resurssit
Suurin osa sovelluksista on riippuvaisia vähintään yhdestä seuraavista resurssityypistä:

* yhteys tietolähteeseen
* paikallinen tietoyhdyskäytävä
* mukautettu liitin
* Excelin työkirja tai muu palvelu
* työnkulku

Käyttäjät ja osallistujat tarvitsevat käyttöoikeudet tietoyhteyksiin ja yhdyskäytäviin, joita sovellus käyttää. Jotkin käyttöoikeudet saadaan sovelluksen mukana, mutta jotkin täytyy nimenomaisesti antaa. Lisätietoja saat kohdasta [Sovelluksen resurssien jakaminen](share-app-resources.md).

Kun jaat Common Data Servicen vanhempaa versiota käyttävän sovelluksen, sinun täytyy jakaa Common Data Servicen suorituksenaikainen käyttöoikeus erikseen. Jos sinulla ei ole lupaa jakamiseen, ota yhteys ympäristön järjestelmänvalvojaan. Kun jaat sovelluksen, joka käyttää Common Data Servicen uusinta versiota, sinun on luotava mukautettu rooli ja määritettävä käyttäjiä sille. [Lue lisää](../../administrator/database-security.md) Common Data Servicen suojauksesta.

### <a name="what-isnt-supported"></a>Mitä ei tueta?
* Voit jakaa käyttöoikeusryhmälle, mutta et jakeluryhmälle.
* Voit jakaa sovelluksia organisaation käyttäjille, mutta et toisen vuokraajan käyttäjille.
* Voit jakaa sovelluksen uudelleen, jos sinulla on**Voivat muokata** -käyttöoikeus (ei **Voivat käyttää**) kyseiseen sovellukseen.

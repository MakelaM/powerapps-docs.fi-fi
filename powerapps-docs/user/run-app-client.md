---
title: Pohjaan perustuvan sovelluksen suorittaminen mobiililaitteessa | Microsoft Docs
description: Opi suorittamaan pohjaan perustuva sovellus mobiililaitteessa.
author: Mattp123
ms.service: powerapps
ms.component: pa-user
ms.topic: quickstart
ms.date: 11/16/2018
ms.author: matp
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 9f951167f56ffd3d211182a89a21d54916ee6b6e
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/19/2019
ms.locfileid: "61531900"
---
# <a name="run-a-canvas-app-on-a-mobile-device"></a>Pohjaan perustuvan sovelluksen suorittaminen mobiililaitteessa
Kun luot sovelluksen tai joku jakaa sovelluksen kanssasi, voit suorittaa sovelluksen Windows-, iOS- tai Android-laitteessa tai verkkoselaimessa. Tässä ohjeaiheessa opimme suorittamaan pohjaan perustuvan sovelluksen mobiililaitteessa. Sovellukset, jotka toimivat mobiililaitteessa, voivat hyödyntää laitteen ominaisuuksia, kuten sijaintipalveluja ja kameraa.

Jotta voit noudattaa tätä ohjeaihetta, mutta et ole kirjautunut PowerAppsiin, [rekisteröidy ilmaiseksi](https://web.powerapps.com/signup?redirect=marketing&email=) ennen kuin aloitat, ja lataa sitten PowerApps [App Storesta](https://itunes.apple.com/app/powerapps/id1047318566?mt=8) tai [Google Playsta](https://play.google.com/store/apps/details?id=com.microsoft.msapps) iPhoneen, iPadiin tai Android-laitteeseen, jossa on [tuettu käyttöjärjestelmä](../maker/canvas-apps/limits-and-config.md) käytössä. Varmista myös, että sinulla on käyttöoikeus luomaasi pohjaan perustuvaan sovellukseen tai että joku muu loi sen ja jakoi sen kanssasi.

## <a name="open-powerapps-and-sign-in"></a>Avaa PowerApps ja kirjaudu sisään
Avaa PowerApps mobiililaitteessa ja kirjaudu sisään Azure Active Directory -tunnistetiedoilla.

![Kirjautuminen](./media/run-app-client/run-client-login.png)

Jos sinulla on Microsoft Authenticator -sovellus asennettuna mobiililaitteessa, sinun tarvitsee antaa vain käyttäjänimesi pyydettäessä ja hyväksyä sitten laitteeseen lähetetty ilmoitus.

## <a name="find-the-app"></a>Etsi sovellus
Voit helpottaa sovelluksen löytämistä avaamalla **PowerApps**-valikon ja valitsemalla sitten suodattimen.

![Sovellussuodattimet](./media/run-app-client/filter-menu.png)

Seuraavat suodattimet ovat käytettävissä:

* **Kaikki sovellukset**: Näyttää kaikki sovellukset, joihin sinulla on käyttö oikeus, mukaan lukien luomasi sovellukset ja muiden kanssasi jakamat sovellukset.

* **Omat sovellukset**: Näyttää sovellukset, jotka olet suorittanut vähintään kerran.

* **Esimerkki sovellukset**: Näyttää Microsoftin esimerkki sovellukset, jotka esittelevät todellisia sovellus tilanteita, joissa on kuvitteellisia tietoja, joiden avulla voit tutustua suunnittelu mahdollisuuksiin.

* **Suosikit**: Näyttää sovellukset, jotka olet merkinnyt napauttamalla sovellus ruudun kolmea pistettä (...) ja napauttamalla sitten **suosikki**. Voit poistaa sovelluksen tästä luettelosta napauttamalla sovelluksen ruudun kolmea pistettä (...) ja napauttamalla sitten **Poista suosikeista**.

    ![Merkitse suosikiksi](./media/run-app-client/favorite.png)

Suodatettuasi sovellukset voit lajitella suodatettua luetteloa sen päivämäärän mukaan, jolloin sovellukset avattiin tai niitä muokattiin viimeksi, tai aakkosjärjestyksessä nimen mukaan. Nämä asetukset tallennetaan, kun PowerApps suljetaan ja avataan uudelleen.

![Lajitteluvalikko](./media/run-app-client/sort-menu.png)

Jos tiedät käytettävän sovelluksen nimen, voit napauttaa PowerAppsin yläosassa olevaa hakukuvaketta ja kirjoittaa sitten osan sen nimestä hakuruutuun.

![Search](./media/run-app-client/search.png)

Jos suodatit sovellukset, suodatettu luettelo käydään ensin läpi.

## <a name="run-an-app"></a>Suorita sovellus
Suorita pohjaan perustuva sovellus mobiililaitteella napauttamalla sovelluksen ruutua. Jos joku muu loi pohjaan perustuvan sovelluksen ja jakoi sen sähköpostitse, voit suorittaa sovelluksen napauttamalla sähköpostiviestissä olevaa linkkiä.

Jos tämä on ensimmäinen PowerAppsin käyttökertasi, näyttöön tulee pyyhkäisyele, jolla sovellus voidaan sulkea.

![Käynnistä sovellus](./media/run-app-client/run-client-app.png)

## <a name="give-consent"></a>Anna suostumus
Jos sovellus vaatii yhteyden tietolähteeseen tai luvan käyttää laitteen ominaisuuksia (kuten kameraa tai sijaintipalveluja), sinun on annettava suostumus, ennen kuin voit käyttää sovellusta. Tavallisesti pyyntö esitetään vain ensimmäisellä kerralla.

![Yhteys](./media/run-app-client/app-connection.png)

## <a name="pin-an-app-to-the-home-screen"></a>Kiinnitä sovellus aloitusnäyttöön
Voit kiinnittää sovelluksen laitteen aloitusnäyttöön, josta se on nopea avata. Napauta sovelluksen ruudun kolmea pistettä (...) ja sitten **Kiinnitä aloitusnäyttöön** ja noudata näyttöön tulevia ohjeita.

![Kiinnitä sovellus](./media/run-app-client/run-client-pin.png)

## <a name="close-an-app"></a>Sulje sovellus
Sulje sovellus pyyhkäisemällä sormella sovelluksen vasemmasta reunasta oikealle. Android-laitteissa voit myös painaa Takaisin-painiketta ja sitten vahvistaa, että haluat sulkea sovelluksen.

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä ohjeaiheessa opit suorittamaan pohjaan perustuvan sovelluksen mobiililaitteessa. Voit suorittaa myös mallipohjaisia sovelluksia mobiililaitteessa.

> [!div class="nextstepaction"]
> [Suorita mallipohjainen sovellus mobiililaitteella](run-app-client-model-driven.md)

---
title: Pikaopas pohjaan perustuvan sovelluksen suorittamiseen mobiililaitteessa | Microsoft Docs
description: Tässä pikaoppaassa opit suorittamaan pohjaan perustuvan sovelluksen mobiililaitteessa.
author: Mattp123
ms.service: powerapps
ms.component: pa-user
ms.topic: quickstart
ms.date: 07/09/2018
ms.author: matp
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
ms.openlocfilehash: a80042065a830bb9d34007131cccbd995279e3dd
ms.sourcegitcommit: bcfefb30b12cf94815dd9a0fd8cad29a8272d96e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/09/2018
ms.locfileid: "37925704"
---
# <a name="quickstart-run-a-canvas-app-on-a-mobile-device"></a>Pikaopas: Suorita pohjaan perustuva sovellus mobiililaitteessa
Kun luot sovelluksen tai joku jakaa sovelluksen kanssasi, voit suorittaa sovelluksen Windows-, iOS- tai Android-laitteessa tai verkkoselaimessa. Tässä pikaoppaassa opimme suorittamaan pohjaan perustuvan sovelluksen mobiililaitteessa. Sovellukset, jotka toimivat mobiililaitteessa, voivat hyödyntää laitteen ominaisuuksia, kuten sijaintipalveluja ja kameraa.

Jotta voit noudattaa tätä pikaopasta, mutta et ole kirjautunut PowerAppsiin, [rekisteröidy ilmaiseksi](https://web.powerapps.com/signup?redirect=marketing&email=) ennen kuin aloitat, ja lataa sitten PowerApps [App Storesta](https://itunes.apple.com/app/powerapps/id1047318566?mt=8) tai [Google Playsta](https://play.google.com/store/apps/details?id=com.microsoft.msapps) iPhoneen, iPadiin tai Android-laitteeseen, jossa on [tuettu käyttöjärjestelmä](../maker/canvas-apps/limits-and-config.md) käytössä. Varmista myös, että sinulla on käyttöoikeus luomaasi pohjaan perustuvaan sovellukseen tai että joku muu loi sen ja jakoi sen kanssasi.

## <a name="open-powerapps-and-sign-in"></a>Avaa PowerApps ja kirjaudu sisään
Avaa PowerApps mobiililaitteessa ja kirjaudu sisään Azure Active Directory -tunnistetiedoilla.

![Kirjautuminen](./media/run-app-client/run-client-login.png)

Jos sinulla on Microsoft Authenticator -sovellus asennettuna mobiililaitteessa, sinun tarvitsee antaa vain käyttäjänimesi pyydettäessä ja hyväksyä sitten laitteeseen lähetetty ilmoitus.

## <a name="find-the-app"></a>Etsi sovellus
Voit helpottaa sovelluksen löytämistä avaamalla **PowerApps**-valikon ja valitsemalla sitten suodattimen.

![Sovellussuodattimet](./media/run-app-client/filter-menu.png)

Seuraavat suodattimet ovat käytettävissä:

* **Kaikki sovellukset**: Näyttää kaikki sovellukset, joihin sinulla on käyttöoikeus, mukaan lukien luomasi sovellukset ja muiden kanssasi jakamat sovellukset.

* **Omat sovellukset**: Näyttää sovellukset, joita olet käyttänyt ainakin yhden kerran.

* **Esimerkkisovellukset**: Näyttää Microsoftin esimerkkisovellukset, jotka esittelevät todellisia sovellustilanteita ja sisältävät kuvitteellisia tietoja. Ne auttavat tutustumaan suunnittelumahdollisuuksiin.

* **Suosikit**: Näyttää sovellukset, jotka olet merkinnyt napauttamalla sovelluksen ruudun kolmea pistettä (...) ja sitten kohtaa **Suosikit**. Voit poistaa sovelluksen tästä luettelosta napauttamalla sovelluksen ruudun kolmea pistettä (...) ja napauttamalla sitten **Poista suosikeista**.

    ![Merkitse suosikiksi](./media/run-app-client/favorite.png)

Suodatettuasi sovellukset voit lajitella suodatettua luetteloa sen päivämäärän mukaan, jolloin sovellukset avattiin tai niitä muokattiin viimeksi, tai aakkosjärjestyksessä nimen mukaan. Nämä asetukset tallennetaan, kun PowerApps suljetaan ja avataan uudelleen.

![Lajitteluvalikko](./media/run-app-client/sort-menu.png)

Jos tiedät käytettävän sovelluksen nimen, voit napauttaa PowerAppsin yläosassa olevaa hakukuvaketta ja kirjoittaa sitten osan sen nimestä hakuruutuun.

![Haku](./media/run-app-client/search.png)

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
Tässä pikaoppaassa opimme suorittamaan pohjaan perustuvan sovelluksen mobiililaitteessa. Voit suorittaa myös mallipohjaisia sovelluksia mobiililaitteessa.

> [!div class="nextstepaction"]
> [Suorita mallipohjainen sovellus mobiililaitteella](run-app-client-model-driven.md)

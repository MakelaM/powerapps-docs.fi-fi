---
title: Sovelluksen luonti PowerAppsissa Common Data Service for Apps -palvelua varten (pikaopas)| Microsoft Docs
description: Luo PowerAppsissa automaattisesti sovellus Common Data Service for Apps -palvelun tietojen hallintaan
services: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/10/2018
ms.author: anneta
ms.openlocfilehash: 78429fc5d0220b5cc9e8dc726583c2e9e543f85a
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-for-generating-an-app-in-powerapps-for-the-common-data-service-for-apps"></a>Pikaopas sovelluksen luomiseksi PowerAppsissa Common Data Service for Apps -palvelua varten

Tässä pikaoppaassa käytetään PowerAppsia ensimmäisen sovelluksen luomiseen [Common Data Service for Apps](../common-data-service/data-platform-intro.md) -palvelun esimerkkitilien luettelon pohjalta. Tässä sovelluksessa voit selata kaikkia tilejä, tarkastella yksittäisen tilin tietoja sekä luoda, päivittää tai poistaa tilin.

Tämän pikaoppaan noudattamiseksi sinun tulee siirtyä [ympäristöön](working-with-environments.md), johon on luotu Common Data Servicen tietokanta, joka sisältää tietoja. Jos tällaista ympäristöä ei ole olemassa ja sinulla on järjestelmänvalvojan käyttöoikeudet, voit [luoda ympäristön](../../administrator/environments-administration.md#create-an-environment), joka täyttää tämän vaatimuksen.

Jos sinulla ei ole PowerApps-käyttöoikeutta, voit [rekisteröityä ilmaiseksi](../signup-for-powerapps.md).

## <a name="generate-an-app"></a>Sovelluksen luominen
1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com).

    ![PowerAppsin aloitussivu](./media/data-platform-create-app/sign-in.png)

1. Vie osoitin kohdan **Tee tämän kaltaisia sovelluksia** kohtaan **Aloita tiedoista** ja valitse **Tee tämä sovellus**.

    ![Asetus sovelluksen luomiseksi](./media/data-platform-create-app/make-this-app.png)

1. Valitse oikealle osoittava nuoli kohdan **Aloita omilla tiedoilla** alta.

    ![Nuolikuvake](./media/data-platform-create-app/right-arrow.png)

1. Valitse Common Data Servicen yhteys kohdassa **yhteydet**.

1. Kirjoita hakukenttään (lähellä oikeaa reunaa) **Accounts**, valitse **Accounts** kohdassa **Valitse taulukko** ja valitse **Yhdistä**.

    ![Entiteetin valinta](./media/data-platform-create-app/select-entity.png)

Muutaman minuutin päästä sovelluksesi avautuu selausnäyttöön, jossa näytetään luettelo tileistä. Lähellä ruudun yläosaa on otsikkorivi, jolla näytetään kuvakkeet luettelon päivittämiseen ja lajitteluun sekä tilin luontiin. Otsikkopalkin alla oleva hakukenttä mahdollistaa luettelon suodattamisen kirjoittamasi tai liittämäsi tekstin perusteella. 

Luettelossa näytetään oletuksena kuva, sähköpostiosoite, kaupunki ja tilin tunnus. Voit kuitenkin mukauttaa luetteloa (jota kutsutaan valikoimaksi) näyttämään eri tietotyyppejä.

![Selaa-näyttö](./media/data-platform-create-app/browse-screen.png)

## <a name="save-the-app"></a>Sovelluksen tallentaminen
Luultavasti haluat tehdä sovellukseen lisää muutoksia ennen kuin käytät sitä tai jaat sen muille. Suosittelemme tallentamaan tähän asti tehdyt työt ennen jatkamista.

1. Napsauta tai napauta **Tiedosto**-välilehteä vasemman yläkulman lähellä.

1. Aseta **Sovelluksen asetukset** -sivulla sovelluksen nimeksi **AppGen**, vaihda taustaväriksi syvä punainen ja vaihda kuvake valintamerkiksi.

    ![Sovelluksen asetussivu](./media/data-platform-create-app/app-settings.png)

1. Napsauta tai napauta vasemman reunan lähellä kohtaa **Tallenna**.

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä pikaoppaassa luotiin sovellus, jolla hallitaan tilien näytetietoja Common Data Service for Apps -palvelussa. Seuraavaksi voit mukauttaa oletusselausnäyttöä sopimaan paremmin tarpeisiisi.

> [!div class="nextstepaction"]
> [Oletusselausnäytön mukauttaminen](customize-layout-sharepoint.md).

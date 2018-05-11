---
title: Pikaopas – sovelluksen luominen Common Data Service for Apps -palvelussa | Microsoft Docs
description: Luo PowerAppsissa automaattisesti sovellus Common Data Service for Apps -palvelun tietojen hallintaan
author: AFTOwen
ms.service: powerapps
ms.topic: conceptual
ms.component: canvas
ms.date: 03/10/2018
ms.author: anneta
ms.openlocfilehash: a70145ee3db44b4ce5d58be2d7804bffb5a56369
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-generate-an-app-from-common-data-service-for-apps-in-powerapps"></a>Pikaopas: sovelluksen luominen PowerAppsin Common Data Service for Apps -palvelussa

Tässä pikaoppaassa käytetään Microsoft PowerAppsia sovelluksen luomiseen [Common Data Service for Apps](../common-data-service/data-platform-intro.md) -palvelun esimerkkitilien luettelon pohjalta. Tässä sovelluksessa voit selata kaikkia tilejä, tarkastella yksittäisen tilin tietoja sekä luoda, päivittää tai poistaa tilin.

Tämän pikaoppaan noudattamiseksi sinun tulee siirtyä [ympäristöön](working-with-environments.md), johon on luotu Common Data Service for Apps -tietokanta, joka sisältää tietoja ja sallii päivitykset. Jos tällaista ympäristöä ei ole olemassa ja sinulla on järjestelmänvalvojan käyttöoikeudet, voit [luoda ympäristön](../../administrator/environments-administration.md#create-an-environment), joka täyttää tämän vaatimuksen.

Jos sinulla ei ole PowerApps-käyttöoikeutta, voit [rekisteröityä ilmaiseksi](../signup-for-powerapps.md).

## <a name="generate-an-app"></a>Luo sovellus
1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com) ja vaihda tarvittaessa ympäristö noudattamalla tässä aiheessa annettuja ohjeita.

    ![PowerAppsin aloitussivu](./media/data-platform-create-app/sign-in.png)

1. Vie osoitin kohdan **Tee tämän kaltaisia sovelluksia** kohtaan **Aloita tiedoista** ja valitse **Tee tämä sovellus**.

    ![Asetus sovelluksen luomiseksi](./media/data-platform-create-app/make-this-app.png)

1. Valitse **Common Data Service** -ruudussa **Puhelinasettelu**.

    ![Yhteysruutu](./media/data-platform-create-app/connection-tile.png)

1. Valitse **Valitse taulukko** -kohdassa **Tilit** ja valitse sitten **Yhdistä**.

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

Sovelluksesi avautuu Selaa-näyttöön, jossa näytetään luettelo tileistä. Lähellä ruudun yläosaa on otsikkorivi, jolla näytetään kuvakkeet luettelon päivittämiseen ja lajitteluun sekä tilin luontiin. Otsikkopalkin alla oleva hakukenttä mahdollistaa luettelon suodattamisen kirjoittamasi tai liittämäsi tekstin perusteella. 

Luettelossa näytetään oletuksena sähköpostiosoite, kaupunki ja tilin tunnus. Voit kuitenkin mukauttaa luetteloa (jota kutsutaan valikoimaksi) näyttämään eri tietotyyppejä.

![Selaa-näyttö](./media/data-platform-create-app/browse-screen.png)

## <a name="save-the-app"></a>Sovelluksen tallentaminen
Luultavasti haluat tehdä sovellukseen lisää muutoksia ennen kuin käytät sitä tai jaat sen muille. Suosittelemme tallentamaan tähän asti tehdyt työt ennen jatkamista.

1. Valitse vasemman yläkulman lähellä oleva **Tiedosto**-välilehti.

1. Aseta **Sovelluksen asetukset** -sivulla sovelluksen nimeksi **AppGen**, vaihda taustaväriksi syvä punainen ja vaihda kuvake valintamerkiksi.

    ![Sovelluksen asetussivu](./media/data-platform-create-app/app-settings.png)

1. Valitse vasemman reunan lähellä **Tallenna** ja valitse sitten vasemmassa alakulmassa **Tallenna**.

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä pikaoppaassa luotiin sovellus, jolla hallitaan tilien näytetietoja Common Data Service for Apps -palvelussa. Seuraavaksi voit mukauttaa valikoimaa ja oletusselausnäytön muita osia sopimaan paremmin tarpeisiisi.

> [!div class="nextstepaction"]
> [Mukauta valikoima](customize-layout-sharepoint.md).

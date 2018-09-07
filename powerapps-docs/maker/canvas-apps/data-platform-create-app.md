---
title: Pohjaan perustuvan sovelluksen luominen Common Data Service for Apps -palvelussa | Microsoft Docs
description: Luo PowerAppsissa automaattisesti pohjaan perustuva sovellus Common Data Service for Apps -palvelun tietojen hallintaan
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: quickstart
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/06/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: bf19983217afad23b75a0f0dbd1e307e6539d3f5
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42825944"
---
# <a name="generate-a-canvas-app-from-common-data-service-for-apps-in-powerapps"></a>Pohjaan perustuvan sovelluksen luominen Common Data Service for Apps -palvelussa PowerAppsissa

Luo Microsoft PowerAppsissa automaattisesti pohjaan perustuva sovellus [Common Data Service for Apps](../common-data-service/data-platform-intro.md) -palvelun esimerkkitilien luettelon pohjalta. Tässä sovelluksessa voit selata kaikkia tilejä, tarkastella yksittäisen tilin tietoja sekä luoda, päivittää tai poistaa tilin.

Jos et ole rekisteröitynyt PowerAppsiin, [rekisteröidy ilmaiseksi](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ennen aloittamista.

## <a name="prerequisites"></a>Edellytykset

Tämän pikaoppaan noudattamiseksi sinun tulee siirtyä [ympäristöön](working-with-environments.md), johon on luotu Common Data Service for Apps -tietokanta, joka sisältää tietoja ja sallii päivitykset. Jos tällaista ympäristöä ei ole olemassa ja sinulla on järjestelmänvalvojan käyttöoikeudet, voit [luoda ympäristön](../../administrator/environments-administration.md#create-an-environment), joka täyttää tämän vaatimuksen.

## <a name="generate-an-app"></a>Sovelluksen luominen

1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja vaihda tarvittaessa ympäristö noudattamalla tässä aiheessa annettuja ohjeita.

    ![PowerAppsin aloitussivu](./media/data-platform-create-app/sign-in.png)

1. Vie osoitin kohdan **Tee tämän kaltaisia sovelluksia** kohtaan **Aloita tiedoista** ja valitse **Tee tämä sovellus**.

    ![Sovelluksen luontiasetus](./media/data-platform-create-app/make-this-app.png)

1. Valitse **Common Data Service** -ruudussa **Puhelinasettelu**.

    ![Yhteysruutu](./media/data-platform-create-app/connection-tile.png)

1. Valitse **Valitse taulukko** -kohdassa **Tilit** ja valitse sitten **Yhdistä**.

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

Sovelluksesi avautuu Selaa-näyttöön, jossa näytetään luettelo tileistä Valikoima-nimisessä ohjausobjektissa. Lähellä näytön yläreunaa olevalla otsikkorivillä näkyy kuvakkeita, joilla voidaan päivittää valikoiman tiedot, lajitella valikoiman tiedot aakkosjärjestykseen ja lisätä tietoja valikoimaan. Otsikkorivin alla oleva hakukenttä mahdollistaa valikoiman tietojen suodattamisen kirjoittamasi tai liittämäsi tekstin perusteella. 

Valikoimassa näytetään oletuksena sähköpostiosoite, kaupunki ja tilin nimi. Kuten näet [seuraavissa vaiheissa](data-platform-create-app.md#next-steps), voit mukauttaa valikoiman muuttamaan tietojen näkymistapaa ja jopa näyttämään muita tietoja.

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

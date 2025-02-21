---
title: Kangas sovelluksen luominen Common Data Service | Microsoft Docs
description: Luo Powerappsissa automaattisesti kangas sovellus, jolla hallitaan Common Data Service tietoja
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: quickstart
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/06/2018
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f9dedc515ee130a950c1dc12793751d43aa3804f
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993088"
---
# <a name="generate-a-canvas-app-from-common-data-service-in-powerapps"></a>Kangas sovelluksen luominen Common Data Service Powerappsissa

Luo Powerappsissa automaattisesti pohjaan perustuva sovellus [Common Data Service](../common-data-service/data-platform-intro.md)malli tili luettelon perusteella. Tässä sovelluksessa voit selata kaikkia tilejä, tarkastella yksittäisen tilin tietoja sekä luoda, päivittää tai poistaa tilin.

Jos et ole rekisteröitynyt PowerAppsiin, [rekisteröidy ilmaiseksi](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ennen aloittamista.

## <a name="prerequisites"></a>Edellytykset

Jotta voit noudattaa tätä Pikaopasta, sinun on oltava määritettynä [ympäristön](https://docs.microsoft.com/power-platform/admin/database-security#predefined-security-roles) tekijän käyttö oikeus rooliin, ja sinun on [siirryttävä ympäristöön](working-with-environments.md) , jossa Common Data Service tieto kanta on luotu, joka sisältää tietoja ja joka sallii päivitykset. Jos tällaista ympäristöä ei ole olemassa ja sinulla on järjestelmänvalvojan käyttöoikeudet, voit [luoda ympäristön](https://docs.microsoft.com/power-platform/admin/environments-administration#create-an-environment), joka täyttää tämän vaatimuksen.

## <a name="generate-an-app"></a>Luo sovellus

1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja vaihda tarvittaessa ympäristö noudattamalla tässä aiheessa annettuja ohjeita.

1. Vie hiiren osoitin **Tee oma sovelluksesi** -osiossa **Aloita tiedoista** -kohdan päälle ja valitse **Tee tämä sovellus**.

    ![Sovelluksen luontiasetus](./media/data-platform-create-app/start-from-data.png)

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
Tämän Pikaoppaan avulla loit sovelluksen, jonka avulla voit hallita Common Data Service asiakkaiden malli tietoja. Seuraavaksi voit mukauttaa valikoimaa ja oletusselausnäytön muita osia sopimaan paremmin tarpeisiisi.

> [!div class="nextstepaction"]
> [Mukauta valikoima](customize-layout-sharepoint.md).

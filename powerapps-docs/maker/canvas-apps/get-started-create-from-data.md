---
title: Pohjaan perustuvan sovelluksen luominen Excelistä | Microsoft Docs
description: PowerAppsin käyttäminen pohjaan perustuvan sovelluksen luomiseen automaattisesti käyttämällä pilvitallennustiliin tallennettua Excel-tiedostoa
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/14/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 576e61e6e4ea1aad317fdec8f49f76bfcd1e0b6a
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71990257"
---
# <a name="generate-a-canvas-app-from-excel-in-powerapps"></a>Pohjaan perustuvan sovelluksen luominen Excelistä PowerAppsissa

Tämän aiheen avulla luot automaattisesti ensimmäisen pohjaan perustuvan sovelluksesi PowerAppsissa käyttämällä Excel-taulukon tietoja. Valitset Excel-tiedoston, luot sovelluksen ja suoritat sitten luomasi sovelluksen. Jokainen luotu sovellus sisältää näytöt tietueiden selaamiseen, tietueiden tietojen näyttämiseen ja tietueiden luomiseen ja päivittämiseen. Luomalla sovelluksen saat luotua nopeasti toimivan, Excel-tietoja käyttävän sovelluksen, ja voit sitten mukauttaa sovellusta omien tarpeidesi mukaan. 

Excel-tiedoston tulee olla pilvitallennustilissä, kuten OneDrive, Google Drive tai Dropbox. Tässä aiheessa käytetään OneDrive for Businessia.

Jos sinulla ei ole PowerApps-käyttöoikeutta, voit [rekisteröityä ilmaiseksi](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Edellytykset

Jotta voit noudattaa tämän aiheen ohjeita tarkasti, lataa [Flooring Estimates](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx) -tiedosto Excelissä ja tallenna se [pilvitallennustiliisi](connections/cloud-storage-blob-connections.md).

> [!IMPORTANT]
> Voit käyttää omaa Excel-tiedostoasi, jos tiedot on muotoiltu taulukoksi. Lisätietoja on artikkelissa [Taulukon muotoileminen](how-to-excel-tips.md). 

## <a name="generate-the-app"></a>Luo sovellus

1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Vie hiiren osoitin **Tee oma sovelluksesi** -osiossa **Aloita tiedoista** -kohdan päälle ja valitse **Tee tämä sovellus**.

    ![Sovelluksen luontiasetus](./media/get-started-create-from-data/start-from-data.png)

1. Napsauta tai napauta **Aloita tiedoillasi** -kohdassa **Puhelinasettelu** pilvitallennustilisi ruudussa.

    ![Sovelluksen luontiasetus](./media/get-started-create-from-data/odfb-tile.png)

1. Napsauta tai napauta **Yhdistä** ja anna kyseisen tilin tunnistetietosi, jos niitä pyydetään.

1. Siirry kohdassa **Valitse Excel-tiedosto** tiedostoon **FlooringEstimates.xlsx** ja napsauta tai napauta sitä. 

1. Napsauta tai napauta **Valitse taulukko** -kohdassa **FlooringEstimates** ja sitten **Yhdistä**.

    ![Sovelluksen luontiasetus](./media/get-started-create-from-data/choose-table.png)

## <a name="run-the-app"></a>Sovelluksen suorittaminen

1. Avaa esikatselu painamalla F5-näppäintä (tai napsauttamalla tai napauttamalla toistokuvaketta oikean yläkulman läheltä).

    ![Esikatselun avaaminen](./media/get-started-create-from-data/open-preview.png)

1. Vaihda lajittelujärjestystä napsauttamalla tai napauttamalla lajittelukuvaketta oikean yläkulman lähellä.

    ![Lajittelukuvake](./media/get-started-create-from-data/sort-icon.png)

1. Suodata luettelo kirjoittamalla tai liittämällä yksi tai useampi merkki hakukenttään.

    Voit esimerkiksi kirjoittaa tai liittää **hunajaa** näyttämään vain tietueen, jonka merkki jono näkyy tuotteen nimessä, luokassa tai yleiskatsauksessa.

    ![Suodatin esimerkki](./media/get-started-create-from-data/filter-example.png)

1. Lisää tietue:

    1. Valitse Plus-kuvake.

        ![Plus-kuvake](./media/get-started-create-from-data/plus-icon.png)

    1. Lisää haluamasi tiedot ja tallenna muutoksesi valitsemalla valinta merkki kuvake.

        ![Tallenna kuvake](./media/get-started-create-from-data/save-icon.png)

1. Muokkaa tietuetta:

    1. Valitse muokattavan tietueen nuoli.

        ![Seuraava-nuoli](./media/get-started-create-from-data/next-arrow.png)

    1. Valitse kynä kuvake.

        ![Kynäkuvake](./media/get-started-create-from-data/pencil-icon.png)

    1. Päivitä vähintään yksi kenttä ja tallenna muutoksesi valitsemalla valinta merkki kuvake.

        ![Tallenna kuvake](./media/get-started-create-from-data/save-icon.png)

        Valitse vaihtoehtoisesti Peruuta-kuvake, jos haluat hylätä tekemäsi muutokset.

1. Poista tietue:

    1. Valitse poistettavan tietueen seuraava nuoli.

        ![Seuraava-nuoli](./media/get-started-create-from-data/next-arrow.png)

    1. Valitse roska kori kuvake.

        ![Roskakorikuvake](./media/get-started-create-from-data/trash-icon.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Mukauta oletusselausnäyttö sopimaan paremmin tarpeisiisi. Voit esimerkiksi lajitella ja suodattaa listaa vain tuote nimen, ei luokan tai yleiskuvauksen mukaan.

> [!div class="nextstepaction"]
> [Oletusselausnäytön mukauttaminen](customize-layout-sharepoint.md).

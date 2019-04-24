---
title: Pohjaan perustuvan sovelluksen luominen Excelistä | Microsoft Docs
description: PowerAppsin käyttäminen pohjaan perustuvan sovelluksen luomiseen automaattisesti käyttämällä pilvitallennustiliin tallennettua Excel-tiedostoa
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/14/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7ab85f09ebf88c30b35c963242895cd74ca6a966
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61554949"
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

    Esimerkiksi, kirjoita tai liitä **hunaja** näyttääksesi vain tietueen, jonka tuotteen nimi, luokka tai yleiskatsaus esiintyy merkkijono.

    ![Suodata Esimerkki](./media/get-started-create-from-data/filter-example.png)

1. Lisää tietue:

    1. Valitse plus-kuvake.

        ![Plus-kuvake](./media/get-started-create-from-data/plus-icon.png)

    1. Lisää haluamasi tiedot ja valitse sitten Tallenna muutokset valintamerkkikuvaketta.

        ![Tallennus-kuvake](./media/get-started-create-from-data/save-icon.png)

1. Tietueen muokkaaminen:

    1. Valitse nuoli tietueen, jota haluat muokata.

        ![Seuraava-nuoli](./media/get-started-create-from-data/next-arrow.png)

    1. Valitse kynäkuvaketta.

        ![Kynäkuvake](./media/get-started-create-from-data/pencil-icon.png)

    1. Päivitä yksi tai useampi kenttä ja valitse sitten Tallenna muutokset valintamerkkikuvaketta.

        ![Tallennus-kuvake](./media/get-started-create-from-data/save-icon.png)

        Vaihtoehtona valitse Peruuta-kuvaketta hylätä tekemäsi muutokset.

1. Poista tietue:

    1. Valitse, Haluatko varmasti poistaa tietueen seuraava-nuolta.

        ![Seuraava-nuoli](./media/get-started-create-from-data/next-arrow.png)

    1. Valitse Roskakorin kuvaketta.

        ![Roskakorikuvake](./media/get-started-create-from-data/trash-icon.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Mukauta oletusselausnäyttö sopimaan paremmin tarpeisiisi. Voit esimerkiksi lajitella ja suodattaa luettelon tuotenimen vain, ei luokan tai yleiskatsaus.

> [!div class="nextstepaction"]
> [Oletusselausnäytön mukauttaminen](customize-layout-sharepoint.md).

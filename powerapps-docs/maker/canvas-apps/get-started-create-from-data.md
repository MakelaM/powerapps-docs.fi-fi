---
title: Sovelluksen luominen Excelistä | Microsoft Docs
description: PowerAppsin käyttäminen sovelluksen luomiseen automaattisesti käyttämällä pilvitallennustiliin tallennettua Excel-tiedostoa
services: ''
suite: powerapps
documentationcenter: na
author: AFTOWen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.custom: mvc
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: a2bbcead313961e064a57d2ea567b5596ece4f7a
ms.sourcegitcommit: 078ba325480147e6e4da61e319ed53219f1c5cfc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/06/2018
---
# <a name="generate-an-app-from-excel-in-powerapps"></a>Sovelluksen luominen Excelistä PowerAppsissa
Tässä aiheessa luot automaattisesti ensimmäisen sovellukseksi PowerAppsissa käyttämällä Excel-taulukon tietoja. Valitset Excel-tiedoston, luot sovelluksen ja suoritat sitten luomasi sovelluksen. Jokainen luotu sovellus sisältää näytöt tietueiden selaamiseen, tietueiden tietojen näyttämiseen ja tietueiden luomiseen ja päivittämiseen. Luomalla sovelluksen saat luotua nopeasti toimivan, Excel-tietoja käyttävän sovelluksen, ja voit sitten mukauttaa sovellusta omien tarpeidesi mukaan. 

Excel-tiedoston tulee olla pilvitallennustilissä, kuten OneDrive, Google Drive tai Dropbox. Tässä aiheessa käytetään OneDrive for Businessia.

Jos sinulla ei ole PowerApps-käyttöoikeutta, voit [rekisteröityä ilmaiseksi](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Edellytykset ##
Jotta voit noudattaa tämän aiheen ohjeita tarkasti, lataa [Flooring Estimates](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx) -tiedosto Excelissä ja tallenna se [pilvitallennustiliisi](connections/cloud-storage-blob-connections.md).

> [!IMPORTANT]
> Voit käyttää omaa Excel-tiedostoasi, jos tiedot on muotoiltu taulukoksi. Lisätietoja on artikkelissa [Taulukon muotoileminen](how-to-excel-tips.md). 

## <a name="generate-the-app"></a>Luo sovellus
1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com).

    ![PowerAppsin aloitussivu](./media/get-started-create-from-data/sign-in.png)

1. Vie osoitin kohdan **Tee tämän kaltaisia sovelluksia** kohtaan **Aloita tiedoista** ja valitse **Tee tämä sovellus**.

    ![Asetus sovelluksen luomiseksi](./media/get-started-create-from-data/make-this-app.png)

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

1. Lisää tietue napsauttamalla tai napauttamalla plus-kuvaketta, lisää haluamasi tiedot ja tallenna muutokset napsauttamalla tai napauttamalla valintamerkin kuvaketta.

1. Napsauta tai napauta lisäämäsi tietueen seuraava-nuolta, muokkaa tietuetta napsauttamalla tai napauttamalla kynäkuvaketta, päivitä yksi tai useampi kenttä ja tallenna muutokset napsauttamalla tai napauttamalla valintamerkin kuvaketta.

1. Napsauta tai napauta lisäämäsi tietueen seuraava-nuolta, muokkaa tietuetta napsauttamalla tai napauttamalla kynäkuvaketta, päivitä yksi tai useampi kenttä ja hylkää muutokset napsauttamalla tai napauttamalla peruuta-kuvaketta.

1. Napsauta tai napauta lisäämäsi tietueen seuraava-nuolta ja poista tietue napsauttamalla tai napauttamalla roskakorin kuvaketta.

## <a name="next-steps"></a>Seuraavat vaiheet
Mukauta oletusselausnäyttö sopimaan paremmin tarpeisiisi. Voit esimerkiksi lajitella ja suodattaa luettelon tuotenimen mukaan luokan sijaan.

> [!div class="nextstepaction"]
> [Oletusselausnäytön mukauttaminen](customize-layout-sharepoint.md).
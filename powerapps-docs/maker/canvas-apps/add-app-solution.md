---
title: Luo pohjaan perustuvan sovelluksen ratkaisu | Microsoft Docs
description: Powerappsissa Luo ratkaisussa kangas-sovellus, jotta voit ottaa sovelluksen käyttöön toiseen ympäristöön
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: ''
ms.date: 10/23/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: dcb6a9c69e602b739d58afde2242d18b60e6f477
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61540434"
---
# <a name="create-a-canvas-app-from-within-a-solution"></a>Luo kangas-sovellus ratkaisun

Luo sovellus ratkaisun Jos esimerkiksi haluat ottaa sovelluksen käyttöön eri ympäristöön. Ratkaisut voivat sisältää vain sovelluksia, mutta myös mukautetut entiteetit, asetusjoukkoja ja muiden osien. Voit mukauttaa ympäristön eri tavoin nopeasti luomalla sovelluksia ja muita komponentteja ratkaisu, ratkaisun vientiä ja ne tuodaan toiseen ympäristöön.

Ratkaisuja on rakennettu samaa alustaa kuin Dynamics 365 for Customer Engagementin. Jos haluat lisätietoja, katso [ratkaisuja yleiskatsaus](../common-data-service/solutions-overview.md).

## <a name="prerequisite"></a>Edellytys

Noudattamalla tämän aiheen ohjeita, siirry ympäristö, joka sisältää Common Data Service-tietokannan.

## <a name="create-a-solution"></a>Ratkaisun luominen

Voit ohittaa tämän vaiheen, jos sinulla on jo ratkaisu, johon haluat luoda sovelluksen tai jotka haluat linkittää sovelluksen.

1. [Kirjaudu sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerapps- ja sitten (tarvittaessa) Vaihda haluamasi ympäristöön:

    - Jos haluat luoda sovelluksen ratkaisun, siirry missä tahansa ympäristössä, joka sisältää Common Data Service-tietokannan.
    - Jos haluat linkittää olemassa olevan sovelluksen ratkaisu, Vaihda ympäristöön, joka sisältää sovelluksen.

1. Valitse vasemmassa siirtymispalkissa **ratkaisuja**.

    > [!div class="mx-imgBorder"]
    > ![Ratkaisuja vaihtoehto vasemmassa siirtymispalkissa](./media/add-app-solution/left-nav.png "ratkaisuja vaihtoehto vasemmassa siirtymispalkissa")

1. Valitse otsikkorivin alapuolella palkin **uusi ratkaisu**.

    > [!div class="mx-imgBorder"]
    > ![Uusi ratkaisu vaihtoehto palkista](./media/add-app-solution/banner-new-solution.png "nauhan vaihtoehto uusi ratkaisu")

1. Määritä näyttönimi, julkaisijan ja ratkaisusi versio tulevassa ikkunassa.

    > [!div class="mx-imgBorder"]
    > ![Ratkaisun asetuksia](./media/add-app-solution/configure-new-solution.png "ratkaisun asetuksia")

    Nimi (ilman välilyöntejä) luodaan automaattisesti, jotka määrität nimen perusteella, mutta voit mukauttaa luotu nimi, jos haluat. Voit määrittää oletusarvon publisher-ympäristön ja **1.0** versio, jos sinulla ei ole erityistarpeita näillä alueilla.

1. Valitse vasemman yläkulman lähellä **Tallenna ja sulje**.

    > [!div class="mx-imgBorder"]
    > ![Tallenna uusi ratkaisu](./media/add-app-solution/save-new-solution.png "Tallenna uusi ratkaisu")

## <a name="create-a-canvas-app-in-a-solution"></a>Luo pohjaan perustuvan sovelluksen ratkaisu

Voit luoda tyhjä kangas-sovellus ratkaisun. Ei voi automaattisesti kolmen näytön sovelluksen tai Mukauta mallin tai mallin sovellus-ratkaisun.

1. [Kirjaudu sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin.

1. Tarvittaessa Vaihda ympäristöön, joka sisältää ratkaisu, jossa haluat luoda pohjaan perustuvan sovelluksen.

1. Valitse vasemmassa siirtymispalkissa **ratkaisuja**.

    > [!div class="mx-imgBorder"]
    > ![Ratkaisuja vaihtoehto vasemmassa siirtymispalkissa](./media/add-app-solution/left-nav.png "ratkaisuja vaihtoehto vasemmassa siirtymispalkissa")

1. Valitse ratkaisu, jossa haluat luoda pohjaan perustuvan sovelluksen ratkaisuja luettelo.

1. Valitse otsikkorivin alapuolella palkin **uusi** > **sovelluksen** > **pohjaan perustuvan sovelluksen**, ja valitse sitten sovelluksen laitemuoto (puhelimessa tai tabletissa), joka haluat luoda.

    > [!div class="mx-imgBorder"]
    > ![Luo sovelluksen ratkaisu](./media/add-app-solution/new-option.png "asetukset, voit luoda sovelluksen ratkaisu")

    PowerApps Studio avautuu tyhjä pohja toinen selaimen välilehdessä.

1. Luo sovelluksesi (tai vähintään yksi muutoksen), ja tallenna sitten muutokset.

1. Selaimen välilehti, jossa ratkaisusi on valittuna, valitse **valmis** Päivitä ratkaisusi-osia.

    > [!div class="mx-imgBorder"]
    > ![Painikkeen](./media/add-app-solution/done-button.png "valmis-painike")

    Uusi sovellus näkyy kyseisen ratkaisun osien luetteloa. Jos tallennat sovellukseen muutoksia, ne näkyvät versioksi, joka on ratkaisu.

## <a name="link-an-existing-canvas-app-to-a-solution"></a>Linkitä aiemmin luodun pohjaan perustuvan sovelluksen ratkaisu

Jos haluat linkittää sovelluksen ratkaisu, molempien on oltava samassa ympäristössä ja sovelluksen on oltava luotu ratkaisun.

1. [Kirjaudu sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin.

1. Tarvittaessa Vaihda ympäristöön, joka sisältää, johon haluat linkittää sovelluksen ratkaisu.

1. Valitse vasemmassa siirtymispalkissa **ratkaisuja**.

    > [!div class="mx-imgBorder"]
    > ![Ratkaisuja vaihtoehto vasemmassa siirtymispalkissa](./media/add-app-solution/left-nav.png "ratkaisuja vaihtoehto vasemmassa siirtymispalkissa")

1. Valitse ratkaisu, johon haluat linkittää sovelluksen ratkaisuja luettelo.

1. Valitse otsikkorivin alapuolella palkin **Lisää olemassa oleva** > **sovelluksen** > **pohjaan perustuvan sovelluksen**.

    > [!div class="mx-imgBorder"]
    > ![Banneria, jos haluat linkittää olemassa olevan sovelluksen asetukset](./media/add-app-solution/add-existing.png "Banneria, jos haluat linkittää olemassa olevan sovelluksen asetukset")

    Näkyviin tulee luettelo pohjaan perustuvat sovellukset, jotka on luotu ratkaisun tässä ympäristössä.

1. Valitse sovellukset-luettelosta sovellus, jonka haluat linkittää ratkaisu ja valitse sitten **Lisää**.

    > [!div class="mx-imgBorder"]
    > ![Lisää painike](./media/add-app-solution/add-button.png "Lisää-painike")

## <a name="known-limitations"></a>Tunnetut rajoitukset

Tunnetut rajoitukset, lisätietoja [käyttää ratkaisuja powerappsissa](../common-data-service/use-solution-explorer.md#known-limitations). 

## <a name="next-steps"></a>Seuraavat vaiheet

- Luo tai linkittää lisää sovelluksia ja [muita komponentteja](../common-data-service/use-solution-explorer.md), kuten entiteettien, työnkulkujen ja koontinäytöt, ratkaisusi.
- [Vie ratkaisusi](../common-data-service/import-update-export-solutions.md) niin, että voit ottaa sen käyttöön toiseen ympäristöön appsourcessa, ja niin edelleen.

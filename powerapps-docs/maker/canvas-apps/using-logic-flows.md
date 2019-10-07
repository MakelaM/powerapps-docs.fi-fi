---
title: Käynnistä työnkulku pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Luo työnkulku, joka suorittaa yhden tai useamman tehtävän pohjaan perustuvassa sovelluksessa ilmenneen tapahtuman jälkeen, kuten käyttäjän painettua painiketta.
author: stepsic-microsoft-com
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/07/2018
ms.author: stepsic
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1e5c90fcc6e4f8d4c8e1d73eadc9a31fdbfe48ef
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71988316"
---
# <a name="start-a-flow-in-a-canvas-app"></a>Käynnistä työnkulku pohjaan perustuvassa sovelluksessa

Microsoft Flow’n avulla voit luoda logiikan, joka suorittaa yhden tai useamman tehtävän, kun pohjaan perustuvassa sovelluksessa ilmenee tapahtuma. Voit esimerkiksi määrittää painikkeen siten, että kun käyttäjä valitsee sen, kohde luodaan SharePoint-luetteloon, sähköpostiviesti tai kokouspyyntö lähetetään, tiedosto lisätään pilveen tai jokaisen näistä. Voit määrittää minkä tahansa ohjausobjektin sovelluksessa aloittamaan työnkulun, joka jatkaa suorittamista, vaikka sulkisit PowerAppsin.

> [!NOTE]
> Kun käyttäjä suorittaa työn kulun sovelluksesta, käyttäjällä on oltava oikeudet suorittaa työn kulussa määritetyt tehtävät. Muussa tapa uksessa työn kulku epäonnistuu.

## <a name="prerequisites"></a>Edellytykset

- [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin.
- Lue, miten [ohjausobjekti määritetään](add-configure-controls.md).

## <a name="create-a-flow"></a>Työnkulun luominen

1. Kirjaudu sisään [PowerAppsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Valitse vasemmasta siirtymis palkista **liiketoiminta logiikka**ja valitse sitten työn **kulut.**

1. Valitse **Omat** työn kulut-sivun vasemmasta yläkulmasta **Uusi**ja valitse sitten **Luo tyhjästä**.

    ![Vaihtoehto työnkulun luomiseen ilman mallia](./media/using-logic-flows/create-from-blank.png)

1. Valitse näkyviin tulevan sivun alareunasta **Hae satoja yhteyksiä ja käynnistimiä**.

1. Kirjoita haku ruutuun **powerapps**ja valitse sitten **powerapps** -kuvake.

    ![Luo PowerApps-käynnistin](./media/using-logic-flows/set-trigger.png)
    
1. Valitse seuraavalla sivulla PowerApps-kuvake uudelleen ja valitse sitten **uusi vaihe**.

1. Määritä **haku liittimet ja toiminnot**-ruudussa työn kulullesi toiminto, kuten tässä esimerkissä:

   1. Kirjoita ruutuun **SharePoint** ja valitse sitten **toiminnot**-kohdan luettelosta **Luo kohde** .

       ![SharePoint-kohteen luontivaihtoehto](./media/using-logic-flows/create-sharepoint-item.png)

   1. Jos näyttöön tulee kehote, anna tunnistetiedot yhteyden muodostamiseksi SharePointiin.

   1. Kirjoita tai liitä luettelon sisältävän SharePoint Online -sivuston URL-osoite **Sivuston osoite** -ruutuun.

       > [!NOTE]
       > Älä liitä luettelon nimeä URL-osoitteeseen.

   1. Määritä luettelo **nimi** -ruutuun luettelo, jota haluat käyttää.
   
       ![Määritä lista](./media/using-logic-flows/list-fields.png)

   1. Valitse syöte ruutu luettelossasi olevalle kentälle (kuten **title**), valitse dynaamisen sisällön ruudussa **Näytä lisää** ja valitse sitten **Kysy powerappsissa**. 

       ![Lisää Otsikko-kenttään Kysy PowerAppsissa -parametri](./media/using-logic-flows/ask-in-powerapps.png)

1. valinnainen Määritä vähintään yksi lisä vaihe, kuten hyväksymis viestin lähettäminen osoitteeseen, jonka määrität tai joka luo liittyvän merkinnän toiseen tieto lähteeseen.

1. Kirjoita tai liitä työn kulkusi nimi lähelle vasenta yläkulmaa ja valitse sitten **Tallenna** lähellä oikeaa yläkulmaa.

## <a name="add-a-flow-to-an-app"></a>Lisää työnkulku sovellukseen
1. Valitse vasemmassa siirtymis palkissa **Luo**.

1. Vie hiiren osoitin **piirto** alusta-sovelluksen päälle tyhjästä ruudusta ja valitse sitten **Tee tämä sovellus**.

1. Lisää **[Tekstisyöte](controls/control-text-input.md)** -ohjausobjekti ja anna sille nimi **RecordTitle**.

1. Lisää **[Painike](controls/control-button.md)** -ohjausobjekti ja siirrä se ohjausobjektin **RecordTitle** alle.

1. Kun **[Painike](controls/control-button.md)** -ohjausobjekti on valittuna, valitse **Toiminnot**-välilehdestä **Työnkulut**.

    ![Työnkulut-valinta Toiminto-välilehdessä](./media/using-logic-flows/action-tab.png)

1. Valitse avautuvassa ruudussa työnkulku, jonka loit edellisessä toimenpiteessä.

    > [!NOTE]
   > Jos luomasi työnkulku ei ole käytettävissä, vahvista onko PowerApps määritetty ympäristöön, jossa loit työnkulun.

    ![Lisää työnkulku mukautusruudusta](./media/using-logic-flows/add-flow-from-pane.png)

1. Kirjoita tai liitä kaavariville **RecordTitle.Text)** automaattisesti lisätyn kaavan loppuun.

    ![OnSelect-ominaisuus, joka sisältää työnkulun](./media/using-logic-flows/onselect-with-flow.png)

## <a name="test-the-flow"></a>Testaa työnkulku
1. Kaksoisnapsauta **teksti syöte** -ohjaus objektia ja kirjoita tai liitä siihen tekstiä.

1. Pidä Alt-näppäintä painettuna ja valitse **[painike](controls/control-button.md)** -ohjaus objekti.

    SharePoint-kohde luodaan luetteloksi, jonka määritit otsikoksi määrittämäsi tekstin kanssa. Jos luettelo oli avoinna, kun työnkulku suoritettiin, saatat joutua päivittämään selainikkunan, jotta muutokset tulevat näkyviin.

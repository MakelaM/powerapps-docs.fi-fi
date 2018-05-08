---
title: Sovelluksen lisääminen Microsoft Teamsiin | Microsoft Docs
description: Lisää sovellus Microsoft Teams -kanavaan, jotta ihmiset, joiden kanssa olet jakanut sovelluksen, voivat avata sen kyseisessä kanavassa.
services: ''
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: quickstart
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/18/2018
ms.author: mblythe
ms.openlocfilehash: 02248cc3e98f256df36bb6a57fac6e66c684a8bf
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-add-an-app-to-microsoft-teams"></a>Pikaopas: Sovelluksen lisääminen Microsoft Teamsiin

Microsoft Teams on keskustelupohjainen yhteistyöalusta, joka perustuu Office 365 -teknologioihin. Voit mukauttaa Teams-käyttökokemusta lisäämällä pohjaan perustuvia PowerApps-sovelluksia Teams-kanavoihisi. Tässä pikaoppaassa kerrotaan, miten voit lisätä tuote-esittelyn esimerkkisovellukset Teams-kanavaan ja avata sitten sovelluksen siitä kanavasta. 

![Microsoft Teamsissa upotettu sovellus](./media/open-app-embedded-in-teams/embedded-app.png)

Jos et ole rekisteröitynyt PowerAppsiin, [rekisteröidy ilmaiseksi](https://web.powerapps.com/signup?redirect=marketing&email=) ennen aloittamista.

## <a name="prerequisites"></a>Edellytykset

Jotta voit suorittaa tämän pikaoppaan vaiheet, sinulla on oltava [Office 365 -tilaus](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1) ja [Teams-kanava](https://www.youtube.com/watch?v=he2f1quaR7M).

## <a name="sign-in-to-powerapps"></a>Kirjautuminen PowerAppsiin

Kirjaudu sisään PowerAppsiin osoitteessa [https://web.powerapps.com]([https://web.powerapps.com).

## <a name="add-an-app"></a>Sovelluksen lisääminen

1. Valitse Microsoft Teamsissa ryhmä ja kanava kyseiselle ryhmälle. Tässä esimerkissä se on **Yleinen** kanava **Liiketoiminnan kehittäminen** -ryhmän alla.

    ![](./media/open-app-embedded-in-teams/teams-select-channel.png)

2. Lisää välilehti valitsemalla **+**.

    ![](./media/open-app-embedded-in-teams/teams-add-tab.png)

3. Valitse **Lisää välilehti** -valintaikkunassa **PowerApps**.

    ![](./media/open-app-embedded-in-teams/add-a-tab.png)

4. Valitse **Esimerkkisovellukset** > **Tuote-esittely** > **Tallenna**.

    ![](./media/open-app-embedded-in-teams/select-an-app.png)

    Sovellus on nyt käytettävissä kanavassa.

    ![](./media/open-app-embedded-in-teams/app-in-channel.png)

> [!NOTE]
> Sinun täytyy [jakaa](../maker/canvas-apps/share-app.md) omat sovelluksesi, ennen kuin lisäät ne Teamsiin (esimerkkisovellukset jaetaan oletuksena).

## <a name="open-an-app"></a>Sovelluksen avaaminen

1. Valitse Microsoft Teamsissa ryhmä ja kanava, jossa sovellus sijaitsee.

    ![](./media/open-app-embedded-in-teams/teams-select-channel.png)

2. Valitse **Tuote-esittely** -välilehti.

    ![](./media/open-app-embedded-in-teams/open-tab.png)

    Sovellus avautuu kanavaan.

    ![](./media/open-app-embedded-in-teams/app-in-channel.png)

## <a name="known-issues"></a>Tunnetut ongelmat

Microsoft Teams työpöytäsovelluksessa:

* Sovellusten on ladattava sisältö, kuten kuvat ja .pdf-tiedostot suojatun yhteyden (https) kautta.
* Kaikkia tunnistimia, kuten **kiihtyvyysanturia**, **kompassia** ja **sijaintia** ei tueta.
* Vain seuraavia äänimuotoja tuetaan: AAC, H264, OGG Vorbis ja WAV.

## <a name="clean-up-resources"></a>Puhdista resurssit

Jos haluat poistaa sovelluksen kanavasta, valitse **Tuote-esittely** -välilehti > **Poista**.

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä pikaoppaassa käytiin läpi, miten voit lisätä tuote-esittelyn esimerkkisovellukset Teams-kanavaan ja avata sitten sovelluksen siitä kanavasta. Lue lisää PowerAppsista jatkamalla PowerApps-opetusohjelmiin.

> [!div class="nextstepaction"]
> [PowerApps-opetusohjelmat](../maker/canvas-apps/get-started-create-from-blank.md)

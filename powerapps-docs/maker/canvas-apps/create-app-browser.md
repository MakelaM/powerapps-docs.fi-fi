---
title: Sovellusten luominen tai muokkaaminen selaimessa | Microsoft Docs
description: Luo tai muokkaa sovelluksia selaimessa käyttämällä Verkon PowerApps Studiota.
services: powerapps
suite: powerapps
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/08/2018
ms.author: sharik
ms.openlocfilehash: 5d120cd0a754b2aa6ad45c5cc81435810e382c61
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="create-or-edit-apps-in-powerapps-studio-for-web"></a>Luo tai muokkaa sovelluksia Verkon PowerApps Studiossa
Luo ja muokkaa sovelluksia Verkon PowerApps Studiossa, joka avautuu selainikkunassa Windowsissa tai muussa käyttöympäristössä.

## <a name="prerequisites"></a>Edellytykset
* [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin.
* Varmista, että käytät [tuettua selainta](limits-and-config.md#supported-browsers-for-powerapps-studio-for-web).

## <a name="open-powerapps-studio-for-web"></a>Avaa Verkon PowerApps Studio
1. Kirjaudu sisään sivustoon [powerapps.com](http://go.microsoft.com/fwlink/p/?LinkId=708209).
2. Napsauta tai napauta vasemmassa alakulmassa **Uusi sovellus**.

    ![Uusi sovellus vasemmassa siirtymispalkissa](./media/create-app-browser/left-nav.png)

Verkon PowerApps Studio avautuu selaimen uudessa välilehdessä. Voit luoda ja muokata sovelluksia samalla tavalla kuin Windowsin PowerApps Studiossa.

## <a name="known-limitations"></a>Tunnetut rajoitukset
1. **Luo yhteys.**

    [Luo yhteys](add-manage-connections.md) tietolähteeseen, joka edellyttää palvelun todentamista sivuston [powerapps.com](https://web.powerapps.com) avulla ja [lisää yhteys](add-data-connection.md) sovellukseen Verkon PowerApps Studiossa.
2. **Muokkaa sovellusta ja tallenna se paikallisesti**.

    Saat parhaat tulokset muokkaamalla sovelluksia ja tallentamalla ne paikallisesti Windowsin PowerApps Studiolla. Et voi tallentaa muutoksia paikalliseen sovellukseen selaimessa. Sinun on tallennettava uusi tiedosto sen sijaan, että korvaisit avaamasi tiedoston.
3. **Käytä signaalifunktioita.**

    **[Acceleration- ja Compass](functions/signals.md)**-funktiot palauttavat julkaistussa sovelluksessa tarkat arvot, mutta kun luot sovelluksen tai muokkaat sitä selaimessa, ne palauttavat nolla-arvot.
4. **Vie ja tuo tietoja.**

    Voit [viedä ja tuoda tietoja](controls/control-export-import.md) julkaistussa sovelluksessa mutta et luodessasi tai muokatessasi sovellusta selaimessa.
5. **Kopioi ohjausobjekti kahden istunnon välillä.**

    Et voi kopioida ohjausobjekteja yhdestä Verkon PowerApps Studio -istunnosta toiseen Verkon PowerApps Studio -istuntoon.

## <a name="next-steps"></a>Seuraavat vaiheet
* Luo sovellus automaattisesti esimerkiksi [Excelin](get-started-create-from-data.md) tai [SharePointin](app-from-sharepoint.md) tiedoistasi.
* Lue, kuinka voit [lisätä ohjausobjektin ja asettaa ominaisuudet](add-configure-controls.md), jotka määrittelevät sovelluksen ulkoasun ja toiminnot.
* Käytä luovuutta [luomalla sovellus tyhjästä](get-started-create-from-blank.md).

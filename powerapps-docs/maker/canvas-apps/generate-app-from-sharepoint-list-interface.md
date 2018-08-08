---
title: Pohjaan perustuvan sovelluksen luominen SharePoint-luettelosta | Microsoft Docs
description: Luo kolmen ruudun pohjaan perustuva sovellus kohteiden hallitsemiseksi SharePoint-luettelosta, oli se sitten paikallinen tai pilvessä.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 9230c96c1b1c5e07ea5129f73a8edd95772aad84
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/02/2018
ms.locfileid: "39471416"
---
# <a name="generate-a-canvas-app-from-within-sharepoint-by-using-powerapps"></a>Pohjaan perustuvan sovelluksen luominen SharePointista PowerAppsilla

Voit luoda PowerAppsissa automaattisesti pohjaan perustuvan sovelluksen, jonka kautta käyttäjät voivat hallita mukautetun SharePoint Online -luettelon kohteita. Sovelluksessa on kolme ruutua, joiden kautta käyttäjät voivat

* selata kaikkia luettelon tietueita (**BrowseScreen1**)
* tarkastella kaikkia tietyn tietueen kenttiä (**DetailsScreen1**)
* luoda tai muokata tietuetta (**EditScreen1**).

Jos luot mukautetun luettelon sovelluksen SharePoint Online -komentopalkin kautta, sovellus näytetään kyseisen luettelon näkymänä. Voit verkkoselaimen ohella suorittaa sovelluksen myös iOS- tai Android-laitteella.

> [!IMPORTANT]
> PowerApps ei tue kaikkia SharePoint-tietotyyppejä. Katso lisätietoja kohdasta [Tunnetut ongelmat](connections/connection-sharepoint-online.md#known-issues).

## <a name="generate-an-app"></a>Luo sovellus
1. Avaa SharePoint Onlinessa mukautettu luettelo, napsauta tai napauta komentopalkin kohtaa **PowerApps** ja napsauta tai napauta **Luo sovellus**.

    ![Luo sovellus](./media/generate-app-from-sharepoint-list-interface/generate-new-app.png)

2. Kirjoita näkyviin tulevaan paneeliin sovelluksesi nimi ja napsauta tai napauta **Luo**.

    ![Nimeä sovellus](./media/generate-app-from-sharepoint-list-interface/app-name.png)

    Verkkoselaimeesi avautuu uusi välilehti, jolla näytetään SharePoint-luetteloosi pohjautuva automaattisesti luotu sovellus. Sovellus näkyy PowerApps Studiossa, jossa voit mukauttaa sitä.

    ![Oletussovellus](./media/generate-app-from-sharepoint-list-interface/default-app.png)  
3. Napsauta tai napauta selaimessasi SharePoint-luettelon välilehteä ja napsauta tai napauta **Avaa**.

> [!NOTE]
> Selainikkuna on ehkä päivitettävä (esimerkiksi painamalla F5-näppäintä) ennen kuin sovellus avautuu.

Sovellus avautuu erilliseen välilehteen.

## <a name="manage-the-app"></a>Sovelluksen hallinta
![Komentopalkki](./media/generate-app-from-sharepoint-list-interface/command-bar.png)

* Jos valitset **Muokkaa PowerAppsissa**, sovellus avautuu erilliseen selaimen välilehteen, jossa voit päivittää sovellusta PowerApps Studiossa.

* Jos napsautat tai napautat kohtaa **Tee tämä näkymä julkiseksi**, muut organisaatiosi käyttäjät voivat tarkastella sitä. Oletuksena vain sinä voit tarkastella luomiasi näkymiä. Jos haluat sallia muiden käyttäjien muokata sovellustasi, sinun täytyy [jakaa se heidän kanssaan](share-app.md) ja antaa heille **Voit muokata** -käyttöoikeudet.

* Jos napsautat tai napautat kohtaa **Poista tämä näkymä**, näkymä poistetaan SharePointista, mutta sovellus säilyy PowerAppsissa ellet [poista sitä](delete-app.md).

## <a name="next-steps"></a>Seuraavat vaiheet
* Mukauta oletus[valikoimaa](customize-layout-sharepoint.md), -[lomakkeita](customize-forms-sharepoint.md) ja -[kortteja](customize-card.md).

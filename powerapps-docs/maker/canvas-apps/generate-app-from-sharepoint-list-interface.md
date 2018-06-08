---
title: Sovelluksen luominen SharePoint-luettelosta | Microsoft Docs
description: Luo kolmen ruudun sovellus kohteiden hallitsemiseksi SharePoint-luettelosta, oli se sitten paikallinen tai pilvessä.
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 51a13472407c5483eed7cc2c202e46855905157d
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "32329406"
---
# <a name="generate-an-app-from-within-sharepoint-using-powerapps"></a>Sovelluksen luominen SharePointista PowerAppsilla

Voit luoda PowerAppsissa automaattisesti sovelluksen, jonka kautta käyttäjät voivat hallita mukautetun SharePoint Online -luettelon kohteita. Sovelluksessa on kolme ruutua, joiden kautta käyttäjät voivat

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

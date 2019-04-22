---
title: Tietoyhteyden lisääminen pohjaan perustuvaan sovellukseen | Microsoft Docs
description: Tietoyhteyden lisääminen olemassa olevaan pohjaan perustuvaan sovellukseen tai tyhjään sovellukseen
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/06/2018
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 43832847f447a9af8a05d149b0d6f3b564b770e1
ms.sourcegitcommit: 0267e58b305f9fb0a4b32130fb149cd6e34b3354
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/22/2019
ms.locfileid: "59993799"
---
# <a name="add-a-data-connection-to-a-canvas-app-in-powerapps"></a>Tietoyhteyden lisääminen pohjaan perustuvaan sovellukseen PowerAppsissa

Lisää PowerAppsissa tietoyhteys olemassa olevaan pohjaan perustuvaan sovellukseen tai sovellukseen, jonka olet luonut alusta alkaen. Sovelluksesi voi yhdistää SharePointiin, Salesforceen, OneDriveen ja [moneen muuhun tietolähteeseen](connections-list.md).

Tämän artikkelin jälkeen [seuraava vaihe](#next-steps) on näyttää ja hallita tietoyhteydestä saatuja tietoja sovelluksessasi, kuten näissä esimerkeissä:

* Yhdistä OneDriveen ja hallinnoi Excel-työkirjan tietoja sovelluksessasi.
* Yhdistä Twilioon ja lähetä tekstiviesti sovelluksestasi.
* Yhdistä SQL Serveriin ja päivitä taulukko sovelluksestasi.

## <a name="prerequisites"></a>Edellytykset

[Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.

## <a name="open-a-blank-app"></a>Avaa tyhjä sovellus

1. Valitse **aloitus** -välilehden **pohjaan perustuva sovellus tyhjästä**.

1. Määritä sovelluksen nimi ja valitse sitten **Luo**.

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

## <a name="add-data-source"></a>Tietolähteen lisääminen

1. Valitse keskimmäisessä ruudussa **tietoihin yhdistäminen** avaamiseen **tietojen** ruudussa.

    Jos tämä on olemassa olevan sovelluksen ja näytön sisältää jo ohjausobjektin, valitse **Näytä** > **tietolähteet** Avaa samassa ruudussa.

1. Valitse **tietolähde**.

1. Jos yhteysluettelossa on se, jota haluat, valitse Lisää se sovellukseen. Muussa tapauksessa siirry seuraavaan vaiheeseen.

    ![Valitse olemassa oleva yhteys](./media/add-data-connection/choose-existing-connection.png)

1. Valitse **uusi yhteys** Näytä yhteyksien luettelo.

    ![Yhteyden lisääminen](./media/add-data-connection/add-connection.png)

1. Hakukenttään Kirjoita tai liitä ensimmäiset kirjaimet yhteyttä ja valitse yhteys, kun se tulee näkyviin.

    ![Yhteyden haku](./media/add-data-connection/search-connections.png)

1. Luo yhteys ja lisää se sovellukseesi valitsemalla **Luo**.

    Jotkin liittimet, kuten **Office 365 Outlook**, eivät vaadi lisävaiheita, ja voit näyttää niiltä saatuja tietoja välittömästi. Jotkin muut liittimet pyytävät sinua antamaan tunnistetietoja, määrittämään tiettyjä tietoja tai suorittamaan muita vaiheita. Esimerkiksi [SharePoint](connections/connection-sharepoint-online.md) ja [SQL Server](connections/connection-azure-sqldatabase.md) tarvitsevat lisätietoja, ennen kuin voit käyttää niitä.

## <a name="identify-or-change-a-data-source"></a>Tietolähteen tunnistaminen tai muuttaminen
Sovellusta päivitettäessä voi olla tarpeen tunnistaa valikoimassa, lomakkeessa tai muussa ohjausobjektissa esiintyvien tietojen lähde tai muuttaa sitä. Sinun on esimerkiksi tunnistaa tietolähteeseen, kun päivität sovelluksen jonkun muun luoman tai luonut kauan sitten.

1. Valitse ohjausobjekti, esimerkiksi valikoima, jonka haluat tunnistaa tai muuttaa tietolähteeseen.

    Tietolähteen nimi näkyy oikeanpuoleisen ruudun **Ominaisuudet**-välilehdessä.

    ![Tunnista yhteys](./media/add-data-connection/identify-connection.png)

1. Tietolähteen lisätietojen näyttämiseksi tai muuttaa sitä, napsauta alanuolta, sen nimen vieressä.

    Lisätietoja nykyinen tietolähde tulee näkyviin ja voit valita tai luomalla toisen lähteen.

    ![Muuttaa yhteyden](./media/add-data-connection/change-connection.png)

## <a name="next-steps"></a>Seuraavat vaiheet

* Tietojen näyttämiseksi tai päivittämiseksi lähteessä, kuten Excel, SharePoint tai SQL Server, [lisää valikoima](add-gallery.md) ja [lisää lomake](add-form.md).
* Käytä muita tietolähteitä varten liitinkohtaisia funktioita, kuten [Office 365 Outlookin](connections/connection-office365-outlook.md), [Twitterin](connections/connection-twitter.md) ja [Microsoft Translatorin](connections/connection-microsoft-translator.md) kanssa käytettävissä olevia funktioita.

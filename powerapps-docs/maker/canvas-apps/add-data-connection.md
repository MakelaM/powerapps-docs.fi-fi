---
title: Tietoyhteyden lisääminen pohjaan perustuvaan sovellukseen | Microsoft Docs
description: Tietoyhteyden lisääminen olemassa olevaan pohjaan perustuvaan sovellukseen tai tyhjään sovellukseen
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/06/2018
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 2ce09240aa30c1f98926fb109a57f63c230e8d4b
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987643"
---
# <a name="add-a-data-connection-to-a-canvas-app-in-powerapps"></a>Tietoyhteyden lisääminen pohjaan perustuvaan sovellukseen PowerAppsissa

Lisää PowerAppsissa tietoyhteys olemassa olevaan pohjaan perustuvaan sovellukseen tai sovellukseen, jonka olet luonut alusta alkaen. Sovelluksesi voi muodostaa yhteyden SharePointiin, Common Data Service, Salesforceen, OneDriveen tai [moniin muihin tieto lähteisiin](connections-list.md).

Tämän artikkelin jälkeen [seuraava vaihe](#next-steps) on näyttää ja hallita tietoyhteydestä saatuja tietoja sovelluksessasi, kuten näissä esimerkeissä:

* Yhdistä OneDriveen ja hallinnoi Excel-työkirjan tietoja sovelluksessasi.
* Yhdistä Twilioon ja lähetä tekstiviesti sovelluksestasi.
* Muodosta yhteys Common Data Service ja Päivitä entiteetti sovelluksestasi.
* Yhdistä SQL Serveriin ja päivitä taulukko sovelluksestasi.

## <a name="prerequisites"></a>Edellytykset

[Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.

## <a name="open-a-blank-app"></a>Avaa tyhjä sovellus

1. Valitse **Aloitus** -väli lehdeltä **kangas sovellus**tyhjästä.

1. Määritä sovellukselle nimi ja valitse sitten **Luo**.

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

## <a name="add-data-source"></a>Tietolähteen lisääminen

1. Avaa **tiedot** -ruutu valitsemalla keskimmäisessä ruudussa **Yhdistä tietoihin** .

    Jos tämä oli olemassa oleva sovellus ja näyttö sisältää jo ohjaus objektin, valitse **näytä** > **tieto lähteet** , jos haluat avata saman ruudun.

1. Valitse **Lisää tieto lähde**.

1. Jos yhteys luettelo sisältää haluamasi, valitse se, jos haluat lisätä sen sovellukseen. Muussa tapauksessa siirry seuraavaan vaiheeseen.

    ![Valitse aiemmin luotu kytkentä](./media/add-data-connection/choose-existing-connection.png)

1. Näytä yhteyksien luettelo valitsemalla **Uusi yhteys** .

    ![Yhteyden lisääminen](./media/add-data-connection/add-connection.png)

1. Kirjoita tai liitä haku palkkiin haluamasi yhteydestä muutama ensimmäinen kirjain ja valitse sitten haluamasi kytkentä, kun se tulee näkyviin.

    ![Hae yhteyksiä](./media/add-data-connection/search-connections.png)

1. Luo yhteys ja lisää se sovellukseesi valitsemalla **Luo**.

    Jotkin liittimet, kuten **Office 365 Outlook**, eivät vaadi lisävaiheita, ja voit näyttää niiltä saatuja tietoja välittömästi. Jotkin muut liittimet pyytävät sinua antamaan tunnistetietoja, määrittämään tiettyjä tietoja tai suorittamaan muita vaiheita. Esimerkiksi [SharePoint](connections/connection-sharepoint-online.md) ja [SQL Server](connections/connection-azure-sqldatabase.md) tarvitsevat lisätietoja, ennen kuin voit käyttää niitä. [Common Data Service](connections/connection-common-data-service.md)avulla voit muuttaa ympäristöä, ennen kuin valitset entiteetin.

## <a name="identify-or-change-a-data-source"></a>Tietolähteen tunnistaminen tai muuttaminen
Sovellusta päivitettäessä voi olla tarpeen tunnistaa valikoimassa, lomakkeessa tai muussa ohjausobjektissa esiintyvien tietojen lähde tai muuttaa sitä. Saatat esimerkiksi joutua tunnistamaan tieto lähteen, kun päivität jonkun muun luoman tai kauan sitten luomasi sovelluksen.

1. Valitse ohjaus objekti, kuten valikoima, jolle haluat määrittää tieto lähteen tai muuttaa sitä.

    Tietolähteen nimi näkyy oikeanpuoleisen ruudun **Ominaisuudet**-välilehdessä.

    ![Tunnista kytkentä](./media/add-data-connection/identify-connection.png)

1. Jos haluat nähdä lisä tietoja tieto lähteestä tai muuttaa sitä, valitse alaspäin osoittava nuoli sen nimen vierestä.

    Näkyviin tulee lisä tietoja nykyisestä tieto lähteestä, ja voit valita tai luoda toisen lähteen.

    ![Muuta yhteyksiä](./media/add-data-connection/change-connection.png)

## <a name="next-steps"></a>Seuraavat vaiheet

* Jos haluat näyttää ja päivittää tietoja lähteessä, kuten Excelissä, SharePointissa, Common Data Service tai SQL Server, [Lisää valikoima](add-gallery.md)ja [Lisää lomake](add-form.md).
* Käytä muita tietolähteitä varten liitinkohtaisia funktioita, kuten [Office 365 Outlookin](connections/connection-office365-outlook.md), [Twitterin](connections/connection-twitter.md) ja [Microsoft Translatorin](connections/connection-microsoft-translator.md) kanssa käytettävissä olevia funktioita.

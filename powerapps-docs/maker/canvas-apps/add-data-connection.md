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
ms.openlocfilehash: bf53c71a5dfbbfecbf6a094f26c9866e7f94f84d
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/02/2018
ms.locfileid: "39471048"
---
# <a name="add-a-data-connection-to-a-canvas-app-in-powerapps"></a>Tietoyhteyden lisääminen pohjaan perustuvaan sovellukseen PowerAppsissa

Lisää PowerAppsissa tietoyhteys olemassa olevaan pohjaan perustuvaan sovellukseen tai sovellukseen, jonka olet luonut alusta alkaen. Sovelluksesi voi yhdistää SharePointiin, Salesforceen, OneDriveen ja [moneen muuhun tietolähteeseen](connections-list.md).

Tämän artikkelin jälkeen [seuraava vaihe](#next-steps) on näyttää ja hallita tietoyhteydestä saatuja tietoja sovelluksessasi, kuten näissä esimerkeissä:

* Yhdistä OneDriveen ja hallinnoi Excel-työkirjan tietoja sovelluksessasi.
* Yhdistä Twilioon ja lähetä tekstiviesti sovelluksestasi.
* Yhdistä SQL Serveriin ja päivitä taulukko sovelluksestasi.

## <a name="prerequisites"></a>Edellytykset

[Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.

## <a name="add-a-data-source"></a>Lisää tietolähde
1. **Aloitus**-välilehdellä siirrä osoitin **Aloita tyhjästä**-ruudun päälle ja valitse sitten **Tee tämä sovellus.**

    ![Sovelluksen luominen alusta alkaen](./media/add-data-connection/blank-app-tile.png)

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

3. Napsauta tai napauta keskimmäisellä ruudulla **Yhdistä tietoihin**.

4. Jos **Tiedot**-ruudun yhteysluettelossa on haluamasi yhteys, lisää se sovellukseen valitsemalla sen. Muussa tapauksessa siirry seuraavaan vaiheeseen.

    ![Tietolähteen lisääminen](./media/add-data-connection/choose-existing-connections.png)

5. Avaa luettelo liittimistä valitsemalla **Uusi yhteys**.

    ![Yhteyden lisääminen](./media/add-data-connection/new-connection.png)

6. Selaa luetteloa ja valitse yhteys, jonka haluat luoda (esimerkiksi **Office 365 Outlook**).

    ![Yhteyden valinta](./media/add-data-connection/choose-connection.png)

7. Luo yhteys ja lisää se sovellukseesi valitsemalla **Luo**.

    Jotkin liittimet, kuten **Office 365 Outlook**, eivät vaadi lisävaiheita, ja voit näyttää niiltä saatuja tietoja välittömästi. Jotkin muut liittimet pyytävät sinua antamaan tunnistetietoja, määrittämään tiettyjä tietoja tai suorittamaan muita vaiheita. Esimerkiksi [SharePoint](connections/connection-sharepoint-online.md) ja [SQL Server](connections/connection-azure-sqldatabase.md) tarvitsevat lisätietoja, ennen kuin voit käyttää niitä.

## <a name="add-another-data-source"></a>Lisää toinen tietolähde
1. Lisää ohjausobjekti, johon haluat lisätä tietolähteen.

    Ohjausobjektilla on oltava **Kohteet**-ominaisuus, kuten valikoimilla ja luetteloruuduilla, tai **Kohde**-ominaisuus, kuten lomakkeilla.

1. **Tiedot**-ruudussa (joka avautuu automaattisesti) avaa luettelo kohdassa **Tietolähde** ja valitse sitten **Lisää tietolähde**.

1. Noudata edellä olevia ohjeita, alkaen vaiheesta 4.

## <a name="identify-or-change-a-data-source"></a>Tietolähteen tunnistaminen tai muuttaminen
Sovellusta päivitettäessä voi olla tarpeen tunnistaa valikoimassa, lomakkeessa tai muussa ohjausobjektissa esiintyvien tietojen lähde tai muuttaa sitä. Tietolähteitä voi haluta tunnistaa esimerkiksi päivitettäessä jonkun muun luomaa sovellusta tai sovellusta, jonka käyttäjä on itse luonut kauan sitten.

1. Valitse ohjausobjekti, jonka tietolähteen haluat tunnistaa tai muuttaa.

    Valitse esimerkiksi valikoima (eikä valikoiman sisältämää ohjausobjektia) napsauttamalla tai napauttamalla sitä näyttöjen ja ohjausobjektien hierarkkisessa luettelossa lähellä vasenta reunaa.

    Tietolähteen nimi näkyy oikeanpuoleisen ruudun **Ominaisuudet**-välilehdessä.

2. Muuta tietolähde tai näytä siitä enemmän tietoja valitsemalla se.

    ![Tietoruutu](./media/add-data-connection/data-pane.png)

3. Muuta tietolähde avaamalla luettelo tietolähteistä ja valitsemalla tai luomalla toisen lähteen.

     ![Tietoruutu](./media/add-data-connection/datasource-list.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* Tietojen näyttämiseksi tai päivittämiseksi lähteessä, kuten Excel, SharePoint tai SQL Server, [lisää valikoima](add-gallery.md) ja [lisää lomake](add-form.md).
* Käytä muita tietolähteitä varten liitinkohtaisia funktioita, kuten [Office 365 Outlookin](connections/connection-office365-outlook.md), [Twitterin](connections/connection-twitter.md) ja [Microsoft Translatorin](connections/connection-microsoft-translator.md) kanssa käytettävissä olevia funktioita.

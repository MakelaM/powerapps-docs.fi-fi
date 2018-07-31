---
title: Liitinten yleiskatsaus | Microsoft Docs
description: Yleiskatsaus kaikista yhteyksistä, joita voit käyttää sovellusten rakentamiseen
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: lanced
ms.openlocfilehash: 15da6ed2ce6b44c17645ac11d1b049b95e157703
ms.sourcegitcommit: 47be38a23c96ba7478fd777065f5db41181af40b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/20/2018
ms.locfileid: "39164744"
---
# <a name="overview-of-connectors-for-powerapps"></a>PowerAppsin liittimien yleiskatsaus
Tietojenkäsittely on useimpien sovellusten keskiössä, myös PowerAppsissa luotujen. Tiedot varastoidaan *tietolähteeseen* ja tiedot haetaan sovellukseesi luomalla *yhteys*. Yhteys käyttää tiettyä *liitintä* tietolähteen kanssa kommunikointiin. PowerAppsissa on liittimet useille suosituille palveluille ja paikallisille tietolähteille, kuten SharePoint, SQL Server, Office 365, Salesforce ja Twitter. Katso aloitusopas tietojen lisäämiseksi sovellukseen kohdasta [Tietoyhteyden lisääminen PowerAppsissa](add-data-connection.md).

Seuraavassa taulukossa on linkit suosituimpien liitinten lisätietoihin. Katso luettelo kaikista liittimistä kohdasta [Kaikki liittimet](#all-connectors).

| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |
| --- | --- | --- | --- | --- |
| ![Common Data Service](./media/connections-list/cdm.png) |[**Common Data Service**](../common-data-service/data-platform-intro.md) |&nbsp; |![Office 365 Outlook](./media/connections-list/office365.png) |[**Office 365 Outlook**](connections/connection-office365-outlook.md) |
| ![SharePoint](./media/connections-list/sharepoint.png) |[**SharePoint**](connections/connection-sharepoint-online.md) |&nbsp; |![Excel](./media/connections-list/excel.png) |[**Excel**](connections/connection-excel.md) |
| ![SQL Server](./media/connections-list/sql.png) |[**SQL Server**](connections/connection-azure-sqldatabase.md) |&nbsp; |![OneDrive for Business](./media/connections-list/onedrive.png) |[**OneDrive for Business**](connections/cloud-storage-blob-connections.md) |
| ![Dynamics 365](./media/connections-list/dynamics-365.png) |[**Dynamics 365**](connections/connection-dynamics-crmonline.md) |&nbsp; |![OneDrive](./media/connections-list/onedrive.png) |[**OneDrive**](connections/cloud-storage-blob-connections.md) |
| ![Office 365 -käyttäjät](./media/connections-list/office365.png) |[**Office 365 -käyttäjät**](connections/connection-office365-users.md) |&nbsp; |![Dropbox](./media/connections-list/dropbox.png) |[**Dropbox**](connections/cloud-storage-blob-connections.md) |

## <a name="types-of-connectors"></a>Liitintyypit
PowerAppsissa on kahden eri tyypin liittimiä: *vakioliittimet*, kuten yllä luetellut, sekä *mukautetut liittimet*. Jos aiot luoda yhteyden tietolähteeseen, jota PowerApps tukee vakioliittimellä, käytä kyseistä liitintä. Jos tarvitset yhteyden eri lähteeseen, kuten itse rakentamaasi palveluun, katso [Mukautettujen liitinten rekisteröinti ja käyttö](../canvas-apps/register-custom-api.md).

Vakioliittimet toimivat eri tavoin riippuen niiden käyttämästä tietolähteestä ja siitä, kuinka kyseinen tietolähde palauttaa tietoja:

* Jotkin liittimet toimivat taulukkomuotoisten tietolähteiden, kuten SharePointin, SQL Serverin ja Excelin, kanssa. Kun näitä tietolähteitä käytetään, tiedot palautetaan PowerAppsille taulukkona. PowerApps käyttää omia funktioitaan, kuten [Patch()](functions/function-patch.md), [Collect()](functions/function-clear-collect-clearcollect.md), [Update()](functions/function-update-updateif.md) ja niin edelleen tietojen kanssa työskentelyyn. Taulukkomuotoisia tietoja voidaan myös käyttää helposti lomakkeissa ja valikoimissa, joissa taulukon kenttä näytetään valikoiman tai lomakkeen kenttänä. Katso lisätietoja seuraavista artikkeleista:

    [Tutustu tietolähteisiin PowerAppsissa](working-with-data-sources.md)

    [Sovelluksen luominen Excel-tiedoista](get-started-create-from-data.md)

    [Sovelluksen luominen alusta alkaen](get-started-create-from-blank.md)

    > [!NOTE]
  > Exceliin yhdistämistä varten tarvitaan pilvipohjaisessa palvelussa, kuten OneDrivessa, isännöity työkirja. Katso lisätietoja aiheesta [Pilvitallennustiliin yhdistäminen PowerAppsista](connections/cloud-storage-blob-connections.md).

* Muut liittimet toimivat funktiopohjaisten tietolähteiden kanssa, kuten Twitter, Facebook ja Office 365 Outlook. Kun työskentelet näiden tietolähteiden kanssa, PowerAppsiin palautettavat tiedot pohjautuvat palvelun tiettyjen funktioiden kutsumiseen. Esimerkiksi Twitter-liittimellä voit kutsua funktion `Twitter.MyFollowers()`, jolloin saat paluuarvona luettelon seuraajistasi. Voit edelleen käyttää näitä tietoja lomakkeessa tai valikoimassa, mutta se on hieman monimutkaisempaa kuin taulukkomuotoisten tietojen käyttäminen. Katso lisätietoja aiheesta [Twitteriin yhdistäminen PowerAppsista](connections/connection-twitter.md).

## <a name="all-connectors"></a>Kaikki liittimet
Luettelo kaikista liittimistämme löytyy [Microsoft Connectorin viitteestä](https://docs.microsoft.com/connectors/). Premium-liittimet vaativat PowerAppsin palvelupaketin 1 tai 2. Lisätietoja saat [PowerAppsin palvelupakettisivulta](https://powerapps.microsoft.com/pricing/).


Jos sinulla on kysyttävää tietystä liittimestä, käytä [PowerApps-keskustelupalstoja](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1). Jos sinulla on uusi liitinehdotus tai parannusehdotuksia, käytä [PowerApps Ideas -keskustelupalstaa](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).

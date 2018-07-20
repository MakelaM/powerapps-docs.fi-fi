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
ms.openlocfilehash: 6ca9b6d873d4d5266486bc1c7b8b876e4f08574a
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39020925"
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
Seuraavassa luettelossa on kaikki liittimet. Katso lisätietoja liittimistä kohdasta [Microsoft-liitinten viittaus](https://docs.microsoft.com/connectors/). Premium-liittimet vaativat PowerAppsin palvelupaketin 1 tai 2. Lisätietoja saat [PowerAppsin palvelupakettisivulta](https://powerapps.microsoft.com/pricing/).

| &nbsp; | &nbsp; |
| --- | --- |
| 10to8 Appointment Scheduling<br>Act!<br>Adobe Creative Cloud ![Premium-liitin](./media/connections-list/premium.png)<br>Adobe Sign<br>Amazon Redshift ![Premium-liitin](./media/connections-list/premium.png)<br>Apache Impala ![Premium-liitin](./media/connections-list/premium.png)<br>AppFigures<br>Approvals<br>Asana<br>AWeber ![Premium-liitin](./media/connections-list/premium.png)<br>Azure AD<br>Azure Application Insights<br>Azure Automation<br>Azure Blob Storage<br>Azure Cosmos DB<br>Azure Data Lake<br>Azure Event Grid<br>Azure Event Grid Publish<br>Azure File Storage<br>Azure Log Analytics<br>Azure Log Analytics Data Collector<br>Azure Queues<br>Azure Resource Manager<br>Azure Table Storage<br>Basecamp 2<br>Basecamp 3<br>Benchmark Email ![Premium-liitin](./media/connections-list/premium.png)<br>Bing Maps<br>Bing Search<br>Bitbucket ![Premium-liitin](./media/connections-list/premium.png)<br>Bitly<br>Bizzy (H3 Solutions, Inc.)<br>Blogger<br>Box<br>bttn<br>Buffer<br>Calendly ![Premium-liitin](./media/connections-list/premium.png)<br>Campfire<br>Capsule CRM ![Premium-liitin](./media/connections-list/premium.png)<br>Chatter ![Premium-liitin](./media/connections-list/premium.png)<br>Cognito Forms<br>Common Data Service ![Premium-liitin](./media/connections-list/premium.png)<br>Computer Vision API<br>Content Conversion<br>Content Moderator<br>DB2 ![Premium-liitin](./media/connections-list/premium.png)<br>Disqus<br>DocFusion365 – SP ![Premium-liitin](./media/connections-list/premium.png)<br>DocuSign ![Premium-liitin](./media/connections-list/premium.png)<br>Dropbox<br>Dynamics 365<br>Dynamics 365 for Financials<br>Dynamics for Operations<br>Dynamics NAV<br>Easy Redmine ![Premium-liitin](./media/connections-list/premium.png)<br>Elastic Forms<br>Event Hubs<br>Eventbrite ![Premium-liitin](./media/connections-list/premium.png)<br>Excel<br>Face API<br>Facebook<br>File System<br>Flic<br>FlowForma ![Premium-liitin](./media/connections-list/premium.png)<br>FreshBooks ![Premium-liitin](./media/connections-list/premium.png)<br>Freshdesk<br>Freshservice ![Premium-liitin](./media/connections-list/premium.png)<br>FTP<br>GitHub<br>Gmail<br>Google Calendar<br>Google Contacts<br>Google Drive<br>Google Sheets<br>Google Tasks<br>GoToMeeting ![Premium-liitin](./media/connections-list/premium.png)<br>GoToTraining ![Premium-liitin](./media/connections-list/premium.png)<br>GoToWebinar ![Premium-liitin](./media/connections-list/premium.png)<br>Harvest ![Premium-liitin](./media/connections-list/premium.png)<br>HelloSign ![Premium-liitin](./media/connections-list/premium.png)<br>HipChat<br>HTTP with Azure AD ![Premium-liitin](./media/connections-list/premium.png)<br>Informix ![Premium-liitin](./media/connections-list/premium.png)<br>Infusionsoft ![Premium-liitin](./media/connections-list/premium.png) |Inoreader<br>Insightly<br>Instagram<br>Instapaper<br>Intercom<br>JIRA ![Premium-liitin](./media/connections-list/premium.png)<br>JotForm ![Premium-liitin](./media/connections-list/premium.png)<br>LeanKit ![Premium-liitin](./media/connections-list/premium.png)<br>LinkedIn<br>LiveChat ![Premium-liitin](./media/connections-list/premium.png)<br>LUIS<br>Mail<br>MailChimp ![Premium-liitin](./media/connections-list/premium.png)<br>Mandrill ![Premium-liitin](./media/connections-list/premium.png)<br>Medium<br>Microsoft Forms<br>Microsoft StaffHub<br>Microsoft Teams<br>Microsoft Translator<br>MSN Weather<br>Muhimbi PDF<br>MySQL ![Premium-liitin](./media/connections-list/premium.png)<br>Nexmo ![Premium-liitin](./media/connections-list/premium.png)<br>Notifications<br>Office 365 Bookings<br>Office 365 Groups<br>Office 365 Outlook<br>Office 365 -käyttäjät<br>Office 365 Video<br>OneDrive<br>OneDrive for Business<br>OneNote (Business)<br>Oracle Database ![Premium-liitin](./media/connections-list/premium.png)<br>Outlook Customer Manager<br>Outlook Tasks<br>Outlook.com<br>PagerDuty<br>Parserr<br>Paylocity ![Premium-liitin](./media/connections-list/premium.png)<br>Pinterest<br>Pipedrive ![Premium-liitin](./media/connections-list/premium.png)<br>Pitney Bowes Data Validation ![Premium-liitin](./media/connections-list/premium.png)<br>Pivotal Tracker<br>Planner<br>Plivo ![Premium-liitin](./media/connections-list/premium.png)<br>PostgreSQL ![Premium-liitin](./media/connections-list/premium.png)<br>Power BI<br>PowerApps Notification ![Premium-liitin](./media/connections-list/premium.png)<br>Project Online<br>Redmine<br>RSS<br>Salesforce ![Premium-liitin](./media/connections-list/premium.png)<br>SendGrid<br>Palveluväylä<br>SFTP<br>SharePoint<br>Skype for Business<br>Slack<br>SmartSheet<br>SMTP<br>SparkPost<br>SQL Server<br>Stripe ![Premium-liitin](./media/connections-list/premium.png)<br>SurveyMonkey ![Premium-liitin](./media/connections-list/premium.png)<br>Teamwork Projects ![Premium-liitin](./media/connections-list/premium.png)<br>Teradata ![Premium-liitin](./media/connections-list/premium.png)<br>Text Analytics<br>Todoist<br>Toodledo<br>Trello<br>Twilio<br>Twitter<br>TypeForm<br>UserVoice ![Premium-liitin](./media/connections-list/premium.png)<br>Video Indexer<br>Vimeo<br>Visual Studio Team Services<br>WebMerge<br>WordPress<br>Wunderlist<br>Yammer<br>YouTube<br>Zendesk ![Premium-liitin](./media/connections-list/premium.png) |

Jos sinulla on kysyttävää tietystä liittimestä, käytä [PowerApps-keskustelupalstoja](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1). Jos sinulla on uusi liitinehdotus tai parannusehdotuksia, käytä [PowerApps Ideas -keskustelupalstaa](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).

---
title: Kangassovellusten liitinten yleiskatsaus | Microsoft Docs
description: Yleiskatsaus kaikista yhteyksistä, joita voit käyttää kangassovellusten rakentamiseen
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 05d02dca1afe6eba0864e7a1da6281998f62b398
ms.sourcegitcommit: 39b32abb19ad9fae98ca986ded6974bcbbb3cea7
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/24/2019
ms.locfileid: "68473995"
---
# <a name="overview-of-canvas-app-connectors-for-powerapps"></a>PowerAppsin kangassovellusten liitinten yleiskatsaus
Tietojenkäsittely on useimpien sovellusten keskiössä, myös PowerAppsissa luotujen. Tiedot varastoidaan *tietolähteeseen* ja tiedot haetaan sovellukseesi luomalla *yhteys*. Yhteys käyttää tiettyä *liitintä* tietolähteen kanssa kommunikointiin. PowerApps sisältää liittimet useille suosituille palveluille ja paikallisille tietolähteille, kuten SharePoint, SQL Server, Office 365, Salesforce ja Twitter. Katso aloitusopas tietojen lisäämiseksi kangassovellukseen kohdasta [Tietoyhteyden lisääminen PowerAppsissa](add-data-connection.md).

Liitin voi tarjota tieto**taulukoita** tai **toimintoja**. Jotkin liittimet tarjoavat vain taulukoita, jotkin vain toimintoja ja jotkin molempia. Lisäksi liitin voi olla joko vakio- tai mukautettu liitin.

## <a name="tables"></a>Taulukot

Jos liitin tarjoaa taulukoita, voit lisätä tietolähteesi ja valita sitten tietolähteen taulukon, jota haluat hallita. PowerApps sekä noutaa taulukkotiedot sovellukseesi että päivittää tietolähteessä olevat tiedot puolestasi. Voit esimerkiksi lisätä taulukon sisältävän tietolähteen nimeltä **Oppitunnit** ja sitten määrittää ohjausobjektin, kuten gallerian tai lomakkeen, **Kohteet**-ominaisuudeksi tämän arvon kaavarivillä:

 ![Tavallisen tietolähteen Kohteet-ominaisuus](./media/connections-list/ItemPropertyPlain.png)

Voit määrittää tiedot, jotka sovelluksesi noutaa mukauttamalla tiedot sisältävän ohjaus objektin **Items** -ominaisuuden. Edellisen esimerkin perusteella voisit siis lajitella tai suodattaa **Oppitunnit**-taulukon tietoja käyttämällä kyseistä nimeä argumenttina **Hae**- ja **SortByColumn**-funktioissa. Tässä kuvassa kaava, johon **Kohteet**-ominaisuus on asetettu, määrittää ne tiedot, jotka lajitellaan ja suodatetaan **TextSearchBox1**:ssä olevan tekstin perusteella. 

 ![Laajennetun tietolähteen Kohteet-ominaisuus](./media/connections-list/ItemPropertyExpanded.png)

Jos haluat lisä tietoja siitä, miten voit mukauttaa kaavaa taulu koilla, tutustu seuraaviin aihe isiin:

  [Tutustu tietolähteisiin PowerAppsissa](working-with-data-sources.md)<br> 
  [Sovelluksen luominen Excel-tiedoista](get-started-create-from-data.md)<br> 
  [Sovelluksen luominen alusta alkaen](get-started-create-from-blank.md)<br>
  [Tutustu taulukkoihin ja tietueisiin PowerAppsissa](working-with-tables.md)

  > [!NOTE]
  > Jos haluat muodostaa yhteyden Excel-työkirjassa oleviin tietoihin, työkirjan tulee olla isännöity pilvipohjaisessa palvelussa, kuten OneDrivessa. Katso lisätietoja aiheesta [Pilvitallennustiliin yhdistäminen PowerAppsista](connections/cloud-storage-blob-connections.md).

## <a name="actions"></a>Toiminnot

Jos liittimesi tarjoaa toimintoja, sinun on silti valittava tietolähde kuten aiemminkin. Mutta sen sijaan, että valitsisit taulukon seuraavassa vaiheessa, sinun tuleekin manuaalisesti yhdistää ohjausobjekti toimintoon muokkaamalla tietoja näyttävän ohjausobjektin **Kohteet**-ominaisuutta. Kaava, johon määrität **Kohteet**-ominaisuuden, määrittää toiminnon, joka noutaa tietoja. Sovellus ei esimerkiksi nouda yhtään tietoja, jos muodostat yhteyden Yammeriin ja määrität sitten **Kohteet**-ominaisuudeksi tietolähteen nimen. Täyttääksesi ohjausobjektin tiedoilla määritä toiminto kuten **GetMessagesInGroup(5033622).messages**.

![Toiminnon tietolähteen Kohteet-ominaisuus](./media/connections-list/ItemPropertyAction.png)

Jos haluat käsitellä mukautettuja tietopäivityksiä toimintoliittimissä, luo **Patch**-funktion sisältävän kaavan. Määritä kaavassa toiminto ja kentät, jotka sidotaan toimintoon.  

Lisä tietoja mukautettujen päivitysten kaavan mukauttamisesta on seuraavissa ohje aiheissa:

[Patch](functions/function-patch.md)<br>[Collect](functions/function-clear-collect-clearcollect.md)<br>[Päivitä](functions/function-update-updateif.md)

> [!NOTE]
>  **Powerapps ei toimi dynaamisen rakenteen kanssa**. Lauseke dynaaminen rakenne viittaa mahdollisuuteen, että sama toiminto voi palauttaa eri taulukon, jolla on eri sarakkeet. Ehdot, jotka saattavat aiheuttaa taulu koiden sarakkeiden poikkeavan, ovat toiminnon syöte parametreja, käyttäjän tai roolin, joka suorittaa toiminnon, ja ryhmän, jossa käyttäjä työskentelee. Esimerkiksi SQL Server tallennetut toiminto sarjat saattavat palauttaa eri sarakkeita, jos ne suoritetaan eri syöttein. Jos kyseessä on dynaaminen rakenne, liittimen dokumentaatio ilmaisee, **että tämän toiminnon tulokset ovat dynaamisia.** Paluu arvona. Sen sijaan Microsoft Flow toimii dynaamisen rakenteen kanssa, ja se saattaa tarjota sinulle työskenaarion.

## <a name="popular-connectors"></a>Suositut liittimet

Tämä taulukko sisältää linkit suosituimpien liitinten lisätietoihin. Katso luettelo kaikista liittimistä kohdasta [Kaikki liittimet](https://docs.microsoft.com/connectors/).

| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |
| --- | --- | --- | --- | --- |
| ![Common Data Service](./media/connections-list/cdm.png) |[**Common Data Service**](../common-data-service/data-platform-intro.md) |&nbsp; |![Office 365 Outlook](./media/connections-list/office365.png) |[**Office 365 Outlook**](connections/connection-office365-outlook.md) |
| ![SharePoint](./media/connections-list/sharepoint.png) |[**SharePoint**](connections/connection-sharepoint-online.md) |&nbsp; |![Excel](./media/connections-list/excel.png) |[**Excel**](connections/connection-excel.md) |
| ![SQL Server](./media/connections-list/sql.png) |[**SQL Server**](connections/connection-azure-sqldatabase.md) |&nbsp; |![OneDrive for Business](./media/connections-list/onedrive.png) |[**OneDrive for Business**](connections/cloud-storage-blob-connections.md) |
| ![Dynamics 365](./media/connections-list/dynamics-365.png) |[**Dynamics 365**](connections/connection-dynamics-crmonline.md) |&nbsp; |![OneDrive](./media/connections-list/onedrive.png) |[**OneDrive**](connections/cloud-storage-blob-connections.md) |
| ![Office 365 -käyttäjät](./media/connections-list/office365.png) |[**Office 365 -käyttäjät**](connections/connection-office365-users.md) |&nbsp; |![Dropbox](./media/connections-list/dropbox.png) |[**Dropbox**](connections/cloud-storage-blob-connections.md) |

## <a name="standard-and-custom-connectors"></a>Vakio- ja mukautetut liittimet
PowerApps tarjoaa *vakio*liittimiä moniin yleisesti käytettyihin tietolähteisiin, kuten esimerkiksi yllä esitettyihin lähteisiin. Jos PowerApps sisältää vakioliittimen tietolähteeseen, jota haluat käyttää, suosittelemme käyttämään kyseistä liitintä. Jos haluat muodostaa yhteyden muuntyyppisiin tietolähteisiin, kuten itse rakentamaasi palveluun, katso [Mukautettujen liittimien rekisteröiminen ja käyttäminen](../canvas-apps/register-custom-api.md).

## <a name="all-standard-connectors"></a>Kaikki vakioliittimet
Luettelo kaikista vakioliittimistä löytyy [Microsoft Connectorin viitteestä](https://docs.microsoft.com/connectors/). Premium-liittimet vaativat PowerAppsin palvelupaketin 1 tai 2. Lisätietoja saat [PowerAppsin palvelupakettisivulta](https://powerapps.microsoft.com/pricing/).

Jos sinulla tiettyyn liittimeen liittyviä kysymyksiä, tutustu [PowerApps-keskustelupalstoihin](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1). Voit myös antaa ehdotuksesi uusista liittimistä tai muista parannuksista [PowerApps-ideasivulla](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).

---
title: Pohjaan perustuvien sovellusten yhteyksien lisääminen ja hallinta | Microsoft Docs
description: Lisää, poista ja päivitä yhteyksiä pohjaan perustuvista sovelluksista tietolähteisiin, kuten SharePoint, SQL Server ja OneDrive for Business
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/09/2017
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ad7f01da3217faa1cd4c55b1d33acd03953434f5
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987330"
---
# <a name="manage-canvas-app-connections-in-powerapps"></a>Pohjaan perustuvien sovellusten yhteyksien hallinta PowerAppsissa
[Powerapps.comissa](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) voit luoda yhteyden yhteen tai useampaan tietolähteeseen, poistaa yhteyden tai päivittää sen tunnistetietoja.

Pohjaan perustuvan sovelluksesi tietoyhteys voi yhdistää SharePointiin, SQL Serveriin, Office 365:een, OneDrive for Businessiin, Salesforceen, Exceliin ja moniin muihin [tietolähteisiin](connections-list.md).

Tämän artikkelin jälkeen seuraava vaihe on näyttää ja hallita tietoyhteydestä saatuja tietoja sovelluksessasi, kuten näissä esimerkeissä:

* Yhdistä OneDrive for Businessiin ja hallinnoi Excel-työkirjan tietoja sovelluksessasi.
* Päivitä SharePoint-sivuston luettelo.
* Yhdistä SQL Serveriin ja päivitä taulukko sovelluksestasi.
* Lähetä sähköpostia Office 365:ssä.
* Lähetä twiitti.
* Yhdistä Twilioon ja lähetä tekstiviesti sovelluksestasi.

## <a name="prerequisites"></a>Edellytykset
1. [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin.
2. Kirjaudu sisään osoitteeseen [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla joilla rekisteröidyit.

## <a name="background-on-data-connections"></a>Taustatietoja tietoyhteyksistä
Useimmat PowerApps-sovellukset käyttävät ulkoisia tietoja eli **tietolähteitä**, jotka on tallennettu pilvipalveluihin. Yleinen esimerkki on taulukko Excel-tiedostossa, joka on tallennettu OneDrive for Businessiin. Sovellukset voivat käyttää näitä tietolähteitä käyttämällä **yhteyksiä**.

Yleisin tietolähde on taulukko, jota voit käyttää tiedon hakemiseen ja tallentamiseen. Voit käyttää yhteyksiä tietolähteisiin tietojen lukemiseksi ja kirjoittamiseksi Microsoft Excel -työkirjoihin, SharePoint-luetteloihin, SQL-taulukoihin ja moniin muihin muotoihin, jotka voidaan tallentaa pilvipalveluihin, kuten OneDrive for Business, DropBox ja SQL Server.

On muitakin tieto lähteitä, jotka eivät ole taulu koita, kuten sähkö posti, kalenterit, Twitter ja ilmoitukset.

Käyttämällä **[Valikoima](controls/control-gallery.md)** -, **[Näytä lomake](controls/control-form-detail.md)** - ja **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekteja on helppoa luoda sovellus, joka lukee ja kirjoittaa tietoa tietolähteestä. Pääset alkuun lukemalla artikkelin [Tutustu tietolomakkeisiin](working-with-forms.md).

Voit luoda ja hallita yhteyksiä osoitteessa [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Tämän lisäksi luot yhteyksiä, kun suoritat näitä tehtäviä:

* Sovelluksen automaattinen luominen [tiedoista](app-from-sharepoint.md), kuten mukautetusta SharePoint-luettelosta
* Olemassa olevan sovelluksen päivittäminen tai uuden luominen alusta alkaen, kuten aiheessa [yhteyden lisääminen](add-data-connection.md) kuvataan.
* Toisen käyttäjän luoman ja [sinulle jaetun](share-app.md) sovelluksen avaaminen.

> [!NOTE]
> Jos haluat sen sijaan käyttää PowerApps Studiota, avaa **Tiedosto**-valikko ja napsauta tai napauta kohtaa **Yhteydet**, niin [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) avautuu ja voit luoda ja hallita yhteyksiä siellä.

## <a name="create-a-new-connection"></a>Uuden yhteyden luominen
1. Kirjaudu sisään osoitteessa [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), jos et ole jo tehnyt niin.
2. Napsauta tai napauta vasemmassa siirtymispalkissa kohtaa **Yhteydet**.
   
    ![Yhteyksien hallinta](./media/add-manage-connections/open-connections.png)
3. Napsauta tai napauta oikean yläkulman kohtaa **Uusi yhteys**.
   
    ![Yhteyden lisääminen](./media/add-manage-connections/add-connection.png)
4. Napsauta tai napauta avautuvassa luettelossa liitintä ja noudata ohjeita.
   
   ![Yhteyden lisääminen](./media/add-manage-connections/choose-connection.png)
5. Napsauta tai napauta **Luo**-painiketta.
   
   ![Yhteyden lisääminen](./media/add-manage-connections/create-connection.png)
6. Noudata ohjeita. Jotkin liittimet pyytävät sinua antamaan tunnistetietoja, määrittämään tiettyjä tietoja tai suorittamaan muita vaiheita. Toiset, kuten **Microsoft Translator**, eivät.
   
   Esimerkiksi seuraavat liittimet tarvitsevat lisätietoja, ennen kuin voit käyttää niitä.
   
   * [SharePoint](connections/connection-sharepoint-online.md)
   * [SQL Server](connections/connection-azure-sqldatabase.md)

Uusi liitin näytetään kohdan **Yhteydet** alla, ja voit [lisätä sen sovellukseen](add-data-connection.md).

## <a name="update-or-delete-a-connection"></a>Yhteyden päivittäminen tai poistaminen
Etsi yhteysluettelosta yhteys, jonka haluat päivittää tai poistaa, ja napsauta tai napauta kolmea pistettä yhteyden oikealla puolella.

![Yhteyden päivittäminen](./media/add-manage-connections/auth-or-delete.png)

* Päivitä yhteyden tunnistetiedot napsauttamalla tai napauttamalla avainkuvaketta ja syötä tunnistetiedot yhteyttä varten.
* Poista yhteys napsauttamalla tai napauttamalla roskakorikuvaketta.
* Tarkastele yhteys tietoja napsauttamalla tai napauttamalla tiedot-kuvaketta.


---
title: Tietoyhteyden lisääminen sovellukseen | Microsoft Docs
description: Tietoyhteyden lisääminen olemassa olevaan tai tyhjään sovellukseen
services: ''
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/02/2017
ms.author: archanan
ms.openlocfilehash: 2134aa28f1b842614e1f4b82acaca2f100126120
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="add-a-data-connection-in-powerapps"></a>Tietoyhteyden lisääminen PowerAppsissa
Lisää PowerAppsissa tietoyhteys olemassa olevaan sovellukseen tai sovellukseen, jonka olet luonut alusta alkaen. Tässä aiheessa käytetään PowerApps Studiota, mutta voit myös käyttää [powerapps.com](https://web.powerapps.com)-sivustoa, kuten kuvataan aiheessa [Yhteyksien hallinta](add-manage-connections.md).

Sovelluksesi tietoyhteys voi yhdistää SharePointiin, Salesforceen, OneDriveen tai [johonkin useista muista tietolähteistä](connections-list.md).

Tämän artikkelin jälkeen [seuraava vaihe](#next-steps) on näyttää ja hallita tietoyhteydestä saatuja tietoja sovelluksessasi, kuten näissä esimerkeissä:

* Yhdistä OneDriveen ja hallinnoi Excel-työkirjan tietoja sovelluksessasi.
* Yhdistä Twilioon ja lähetä tekstiviesti sovelluksestasi.
* Yhdistä SQL Serveriin ja päivitä taulukko sovelluksestasi.

## <a name="prerequisites"></a>Edellytykset
[Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin, [asenna](http://aka.ms/powerappsinstall) ja avaa se ja kirjaudu sitten sisään samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.

## <a name="background-on-data-connections"></a>Taustatietoja tietoyhteyksistä
Useimmat PowerApps-sovellukset käyttävät ulkoisia tietoja eli **tietolähteitä**, jotka on tallennettu pilvipalveluihin. Yleinen esimerkki on taulukko Excel-tiedostossa, joka on tallennettu OneDrive for Businessiin. Sovellukset voivat käyttää näitä tietolähteitä käyttämällä **liittimiä**.

Yleisimmät tietolähteet ovat taulukoita, joita voit käyttää tiedon hakemiseen ja tallentamiseen. Voit käyttää tietolähteiden liittimiä tietojen lukemiseen ja kirjoittamiseen Microsoft Excel -työkirjoihin, SharePoint-luetteloihin, SQL-taulukoihin ja moniin muihin muotoihin, jotka voidaan tallentaa pilvipalveluihin, kuten OneDrive for Business, DropBox, SQL Server ja niin edelleen.

Taulukoita sisältämättömiin tietolähteisiin kuuluvat sähköposti, kalenterit, Twitter ja ilmoitukset.

Käyttämällä **[Valikoima](controls/control-gallery.md)**-, **[Näytä lomake](controls/control-form-detail.md)**- ja **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekteja on helppoa luoda sovellus, joka lukee ja kirjoittaa tietoa tietolähteestä. Pääset alkuun lukemalla artikkelin [Tutustu tietolomakkeisiin](working-with-forms.md).

## <a name="add-a-connection"></a>Yhteyden lisääminen
1. Napsauta tai napauta **Tiedosto**-valikon (lähellä vasenta reunaa) kohtaa **Uusi**.

    ![Tiedosto-valikon Uusi-vaihtoehto](./media/add-data-connection/file-new.png)

2. Napsauta tai napauta **Tyhjä sovellus** -ruudun kohtaa **Puhelinasettelu**.

    ![Sovelluksen luominen alusta alkaen](./media/add-data-connection/blank-app.png)

3. Napsauta tai napauta keskimmäisellä ruudulla **Yhdistä tietoihin**.

4. Jos **Tiedot**-ruudun yhteysluettelossa on haluamasi yhteys, lisää se sovellukseen napsauttamalla tai napauttamalla sitä. Muussa tapauksessa siirry seuraavaan vaiheeseen.

    ![Tietolähteen lisääminen](./media/add-data-connection/choose-existing-connections.png)

5. Avaa yhteysluettelo napsauttamalla tai napauttamalla **Uusi yhteys** -kohtaa.

    ![Yhteyden lisääminen](./media/add-data-connection/new-connection.png)

6. Selaa yhteysluetteloa ja etsi yhteys, jonka haluat luoda (esimerkiksi **Office 365 Outlook**) ja napsauta tai napauta sitä.

    ![Yhteyden valinta](./media/add-data-connection/choose-connection.png)

7. Luo yhteys ja lisää se sovellukseesi napsauttamalla tai napauttamalla **Luo**.

    Jotkin yhteydet, kuten **Microsoft Translator**, eivät vaadi lisävaiheita ja voit näyttää niiltä saatuja tietoja välittömästi. Jotkin muut liittimet pyytävät sinua antamaan tunnistetietoja, määrittämään tiettyjä tietoja tai suorittamaan muita vaiheita. Esimerkiksi [SharePoint](connections/connection-sharepoint-online.md) ja [SQL Server](connections/connection-azure-sqldatabase.md) tarvitsevat lisätietoja, ennen kuin voit käyttää niitä.

## <a name="view-or-change-a-data-source"></a>Tietolähteen tarkastelu tai muuttaminen
Sovellusta päivitettäessä tietolähdettä, jolla on **Kohde**-ominaisuus, voi olla tarpeen muuttaa valikoimassa, lomakkeessa tai muussa ohjausobjektissa tai se on ehkä tunnistettava. Voit esimerkiksi työskennellä jonkun muun luoman sovelluksen parissa tai voit haluta etsiä tietolähteen, jonka määritit aiemmin.

1. Valitse ohjausobjekti, jolle haluat määrittää tietolähteen.

    Valitse esimerkiksi valikoima (eikä valikoiman sisältämää ohjausobjektia) napsauttamalla tai napauttamalla sitä näyttöjen ja ohjausobjektien hierarkkisessa luettelossa lähellä vasenta reunaa.

    Tietolähteen nimi näkyy oikeanpuoleisen ruudun **Ominaisuudet**-välilehdessä.

    ![Tietolähde Ominaisuudet-välilehdessä](./media/add-data-connection/properties-tab.png)

2. Tietolähteen lisätietojen näyttämiseksi tai lähteen muuttamiseksi napsauta tai napauta oikeanpuoleisen ruudun kohtaa **Tiedot**.

    ![Tietoruutu](./media/add-data-connection/data-pane.png)

3. Muuta tietolähdettä napsauttamalla tai napauttamalla tietoruudun viereistä alaspäin osoittavaa nuolta ja valitse tai luo uusi tietolähde.

## <a name="next-steps"></a>Seuraavat vaiheet
* Tietojen näyttämiseksi tai päivittämiseksi lähteessä, kuten Excel, SharePoint tai SQL Server, [lisää valikoima](add-gallery.md) ja [lisää lomake](add-form.md).
* Käytä muita tietolähteitä varten liitinkohtaisia funktioita, kuten [Office 365 Outlookin](connections/connection-office365-outlook.md), [Twitterin](connections/connection-twitter.md) ja [Microsoft Translatorin](connections/connection-microsoft-translator.md) kanssa käytettävissä olevia funktioita.

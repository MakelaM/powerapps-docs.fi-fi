---
title: Paikallisen tietoyhdyskäytävän hallitseminen | Microsoft Docs
description: Paikallisen tietoyhdyskäytävän ja sen yhteyksien hallitseminen
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
ms.date: 10/30/2016
ms.author: archanan
ms.openlocfilehash: 61ea6c88d8f7365e0fa022ad5edb7598b243ec3f
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="manage-an-on-premises-data-gateway-in-powerapps"></a>Paikallisen tietoyhdyskäytävän ja sen yhteyksien hallitseminen PowerAppsissa
Asenna paikallinen tietoyhdyskäytävä, jotta voit siirtää tietoja nopeasti ja turvallisesti PowerAppsin ja tietolähteen, joka ei ole pilvipalvelussa, kuten paikallinen SQL Server -tietokanta tai paikallinen SharePoint-sivusto, välillä. Tarkastele kaikkia yhdyskäytäviä, joihin sinulla on järjestelmänvalvojan oikeudet ja hallitse käyttöoikeuksia ja näiden yhdyskäytävien yhteyksiä.

Yhdyskäytävän avulla voit muodostaa yhteyden paikallisiin tietoihin seuraavien yhteyksien kautta:

* SharePoint
* SQL Server
* Oracle
* Informix
* Filesystem
* DB2

## <a name="prerequisites"></a>Edellytykset
* Käyttäjänimi ja salasana, jota käytit PowerAppsiin [rekisteröitymistä](../signup-for-powerapps.md) varten.
* Yhdyskäytävän järjestelmänvalvojan oikeudet. (Sinulla on nämä oikeudet oletusarvoisesti jokaiselle asentamallesi yhdyskäytävälle. Toisen yhdyskäytävän järjestelmänvalvoja voi myöntää sinulle käyttöoikeudet kyseiseen yhdyskäytävään.)
* Käyttöoikeus, joka tukee paikallisten tietojen käyttämistä paikallisen yhdyskäytävän kautta. Lisätietoja on [Hinnoittelu](https://powerapps.microsoft.com/pricing/)-sivun kohdassa ”yhteydet”.
* Yhdyskäytäviä ja paikallisia yhteyksiä voi luoda ja käyttää vain käyttäjän [oletusympäristössä](working-with-environments.md).

## <a name="install-a-gateway"></a>Yhdyskäytävän asentaminen
1. Napsauta tai napauta [powerapps.comin](https://web.powerapps.com) vasemmassa siirtymispalkissa **Yhdyskäytävät**.

    ![Yhdyskäytävät vasemmassa siirtymispalkissa](./media/gateway-management/manage-gateway.png)

2. Jos sinulla ei ole järjestelmänvalvojan oikeuksia yhdyskäytävään, napsauta tai napauta kohtaa [Asenna yhdyskäytävä nyt](http://go.microsoft.com/fwlink/?LinkID=820931) (tai **Uusi yhdyskäytävä** oikeassa yläkulmassa) ja noudata sitten näkyviin tulevaa ohjattua toimintoa.

    ![Yhdyskäytävien asennus](./media/gateway-management/no-gateway-installed.png)

    Lisätietoja siitä, miten voit asentaa yhdyskäytävän, on kohdassa[Tutustu paikallisiin tietoyhdyskäytäviin](gateway-reference.md).

## <a name="view-and-manage-gateway-permissions"></a>Tarkastele ja hallitse yhdyskäytävän käyttöoikeuksia
1. Napsauta tai napauta [powerapps.comin](https://web.powerapps.com) vasemmassa siirtymispalkissa **Yhdyskäytävät** ja napsauta tai napauta sitten yhdyskäytävää.

2. Lisää yhdyskäytävään käyttäjä napsauttamalla tai napauttamalla kohtaa **Users**, jonka avulla määritetään käyttäjä tai ryhmä sekä käyttöoikeustaso:

   * **Can use**: Käyttäjät, jotka voivat laatia yhteyksiä yhdyskäytävässä sovelluksia ja työnkulkuja varten mutta eivät voi jakaa yhdyskäytävää. Käytä tätä käyttöoikeutta käyttäjille, jotka suorittavat sovelluksia mutta eivät jaa niitä.
   * **Can use + share**: Käyttäjät, jotka voivat laatia yhteyksiä yhdyskäytävässä sovelluksia ja työnkulkuja varten ja jakaa yhdyskäytävän automaattisesti jakaessaan sovelluksen. Käytä tätä käyttöoikeutta, jos käyttäjä haluaa jakaa sovelluksia muiden käyttäjien tai organisaation kanssa.
   * **Admin**: Järjestelmänvalvojat, joilla on yhdyskäytävän täysi käyttöoikeus, mukaan lukien käyttäjien lisääminen, käyttöoikeuksien määrittäminen, yhteyksien luominen kaikille käytössä oleville tietolähteille ja yhdyskäytävän poistaminen.

Valitse **Can use**- ja **Can use + share** -käyttöoikeustasoille tietolähteet, joihin käyttäjä voi muodostaa yhteyden yhdyskäytävän kautta.

## <a name="view-and-manage-gateway-connections"></a>Yhdyskäytävän yhteyksien tarkasteleminen ja hallitseminen
1. Napsauta tai napauta [powerapps.comin](https://web.powerapps.com) vasemmassa siirtymispalkissa **Yhdyskäytävät** ja napsauta tai napauta sitten yhdyskäytävää.

2. Napsauta tai napauta kohtaa **Yhteydet** ja napsauta tai napauta yhteyttä, jotta voit tarkastella sen tietoja, muokata asetuksia tai poistaa sen.

3. Jaa yhteys napsauttamalla tai napauttamalla kohtaa **Share** ja lisäämällä tai poistamalla käyttäjiä.

    > [!NOTE]
> Voit jakaa vain tietyn tyyppisiä yhteyksiä, kuten SQL Server. Lisätietoja saat kohdasta [Sovelluksen resurssien jakaminen](share-app-resources.md).

Katso lisätietoja yhteyksien hallinnasta kohdasta [Yhteyksien hallinta](add-manage-connections.md).

## <a name="troubleshooting-and-advanced-configuration"></a>Vianmääritys ja lisäasetusten määrittäminen
Lisätietoja ongelmien, jotka liittyvät yhdyskäytäviin tai yhdyskäytäväpalvelun määrittämiseen verkkoosi, vianmäärityksestä on kohdassa [Opi lisää paikallisista tietoyhdyskäytävistä](gateway-reference.md).

## <a name="next-steps"></a>Seuraavat vaiheet
* Luo sovellus, joka muodostaa yhteyden paikalliseen tietolähteeseen, kuten [SQL Server-](connections/connection-azure-sqldatabase.md) tai [SharePoint](connections/connection-sharepoint-online.md).
* [Jaa sovellus](share-app.md), joka muodostaa yhteyden paikalliseen tietolähteeseen.

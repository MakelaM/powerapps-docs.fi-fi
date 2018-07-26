---
title: Paikallisen tietoyhdyskäytävän hallitseminen | Microsoft Docs
description: Paikallisen tietoyhdyskäytävän ja sen yhteyksien hallitseminen
author: archnair
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/30/2016
ms.author: archanan
ms.openlocfilehash: fb561ca5458a22880d93c712aa2e2b2ada884605
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/22/2018
ms.locfileid: "39194877"
---
# <a name="manage-an-on-premises-data-gateway-in-powerapps"></a>Paikallisen tietoyhdyskäytävän hallitseminen PowerAppsissa
Asenna paikallinen tietoyhdyskäytävä, jonka avulla voit siirtää tietoja nopeasti ja turvallisesti PowerAppsin ja muualla kuin pilvipalvelussa olevan tietolähteen, kuten paikallisella SQL-palvelimella olevan tietokannan tai paikallisen SharePoint-sivuston, välillä. Tarkastele yhdyskäytäviä, joihin sinulla on järjestelmänvalvojan oikeudet, ja hallitse näiden yhdyskäytävien käyttöoikeuksia ja yhteyksiä.

Yhdyskäytävän avulla voit muodostaa yhteyden paikallisiin tietoihin seuraavien yhteyksien kautta:

* SharePoint
* SQL Server
* Oracle
* Informix
* Filesystem
* DB2

## <a name="prerequisites"></a>Edellytykset
* Käyttäjänimi ja salasana, joita käytit [rekisteröityessäsi](../signup-for-powerapps.md) PowerAppsiin.
* Yhdyskäytävän järjestelmänvalvojan oikeudet. (Saat nämä oikeudet oletusarvoisesti, aina kun asennat yhdyskäytävän, ja muiden yhdyskäytävien oikeudet myöntää kyseisen yhdyskäytävän järjestelmänvalvoja.)
* Käyttöoikeus, joka tukee paikallisten tietojen käyttämistä paikallisen yhdyskäytävän kautta. Lisätietoja on [Hinnoittelu](https://powerapps.microsoft.com/pricing/)-sivun kohdassa "yhteydet".
* Yhdyskäytäviä ja paikallisia yhteyksiä voi luoda ja käyttää vain käyttäjän [oletusympäristössä](working-with-environments.md).

## <a name="install-a-gateway"></a>Yhdyskäytävän asentaminen
1. Napsauta tai napauta [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivun vasemmassa siirtymispalkissa olevaa kohtaa **Yhdyskäytävät**.

    ![Vasemmassa siirtymispalkissa näkyvät yhdyskäytävät](./media/gateway-management/manage-gateway.png)

2. Jos sinulla ei ole järjestelmänvalvojan oikeuksia yhdyskäytävään, napsauta tai napauta kohtaa [Asenna yhdyskäytävä nyt](http://go.microsoft.com/fwlink/?LinkID=820931) (tai valitse oikeasta yläkulmasta **Uusi yhdyskäytävä**), ja noudata näyttöön tulevaa ohjattua toimintoa.

    ![Yhdyskäytävien asentaminen](./media/gateway-management/no-gateway-installed.png)

    Lisätietoja yhdyskäytävän asentamisesta on kohdassa[Tutustu paikallisiin tietoyhdyskäytäviin](gateway-reference.md).

## <a name="view-and-manage-gateway-permissions"></a>Tarkastele ja hallitse yhdyskäytävän käyttöoikeuksia
1. Napsauta tai napauta [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivun vasemmassa siirtymispalkissa olevaa kohtaa **Yhdyskäytävät**, ja napsauta tai napauta yhdyskäytävää.

2. Lisää yhdyskäytävään käyttäjä napsauttamalla tai napauttamalla kohtaa **Käyttäjät**, jonka avulla määritetään käyttäjä tai ryhmä sekä käyttöoikeustaso:

   * **Can use**: Käyttäjille, jotka voivat käyttää yhdyskäytävää yhteyksien luomiseksi sovelluksia ja työnkulkuja varten, mutta eivät voi jakaa yhdyskäytävää. Käytä tätä käyttöoikeutta käyttäjille, jotka suorittavat sovelluksia, mutta eivät jaa niitä.
   * **Can use + share**: Käyttäjille, jotka voivat luoda yhdyskäytävässä yhteyksiä sovelluksia ja työnkulkuja varten ja jakaa yhdyskäytävän automaattisesti, kun sovellus jaetaan. Käytä tätä käyttöoikeutta, jos käyttäjä haluaa jakaa sovelluksia muiden käyttäjien tai organisaation kanssa.
   * **Admin**: Järjestelmänvalvojille, joilla on täydet käyttöoikeudet yhdyskäytävään, mukaan lukien käyttäjien lisääminen, käyttöoikeuksien määrittäminen, yhteyksien luominen kaikkiin saatavana oleviin tietolähteisiin sekä yhdyskäytävän poistaminen.

Valitse **Can use**- ja **Can use + share** -käyttöoikeustasoille tietolähteet, joihin käyttäjä voi muodostaa yhteyden yhdyskäytävän kautta.

## <a name="view-and-manage-gateway-connections"></a>Yhdyskäytävän yhteyksien tarkasteleminen ja hallitseminen
1. Napsauta tai napauta [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivun vasemmassa siirtymispalkissa olevaa kohtaa **Yhdyskäytävät**, ja napsauta tai napauta yhdyskäytävää.

2. Napsauta tai napauta kohtaa **Yhteydet**, ja napsauta tai napauta yhteyttä, jotta voit tarkastella sen tietoja, muokata asetuksia tai poistaa sen.

3. Jaa yhteys napsauttamalla tai napauttamalla kohtaa **Jaa** ja lisäämällä tai poistamalla käyttäjiä.

    > [!NOTE]
   > Voit jakaa vain tietyn tyyppisiä yhteyksiä, kuten SQL Serverin. Lisätietoja saat kohdasta [Sovelluksen resurssien jakaminen](share-app-resources.md).

Katso lisätietoja yhteyksien hallinnasta kohdasta [Yhteyksien hallinta](add-manage-connections.md).

## <a name="troubleshooting-and-advanced-configuration"></a>Vianmääritys ja lisäasetusten määrittäminen
Jos tarvitset lisää tietoa yhdyskäytävistä tai siitä, miten yhdyskäytäväpalvelu määritetään omaan verkkoosi, lue kohta [Opi lisää paikallisista tietoyhdyskäytävistä](gateway-reference.md).

## <a name="next-steps"></a>Seuraavat vaiheet
* Luo sovellus, joka muodostaa yhteyden paikalliseen tietolähteeseen, kuten [SQL Server](connections/connection-azure-sqldatabase.md) tai [SharePoint](connections/connection-sharepoint-online.md).
* [Jaa sovellus](share-app.md), joka muodostaa yhteyden paikalliseen tietolähteeseen.

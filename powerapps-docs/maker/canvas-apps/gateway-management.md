---
title: Kangassovelluksen paikallisen tietoyhdyskäytävän hallitseminen | Microsoft Docs
description: Paikallisen tietoyhdyskäytävän ja sen yhteyksien hallitseminen
author: arthiriyer
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/16/2019
ms.author: arthii
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 90a0bd777e808bb3aaab10b249d4fd765fbad654
ms.sourcegitcommit: 6984ce43cc5653ccb957219d2a687907ebb5520c
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/18/2019
ms.locfileid: "72560930"
---
# <a name="manage-an-on-premises-data-gateway-in-powerapps"></a>Paikallisen tietoyhdyskäytävän hallitseminen PowerAppsissa

Asenna paikallinen tietoyhdyskäytävä, jonka avulla voit siirtää tietoja nopeasti ja turvallisesti PowerAppsissa rakennetun kangassovelluksen ja muualla kuin pilvipalvelussa olevan tietolähteen, kuten paikallisella SQL-palvelimella olevan tietokannan tai paikallisen SharePoint-sivuston, välillä. Tarkastele yhdyskäytäviä, joihin sinulla on järjestelmänvalvojan oikeudet, ja hallitse näiden yhdyskäytävien käyttöoikeuksia ja yhteyksiä.

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

Jos haluat asentaa yhdyskäytävän, noudata [paikallisen tietoyhdyskäytävän asentaminen-](/data-integration/gateway/service-gateway-install)kohdan ohjeita. Asenna yhdyskäytävä vakio tilaan, koska _Paikallinen tietoyhdyskäytävä (henkilökohtainen tila)_ on käytettävissä vain Power BI.

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

Lisä tietoja yhdyskäytävien ongelmien vian määrityksestä on kohdassa [paikallisen tietoyhdyskäytävän vian määritys](/data-integration/gateway/service-gateway-tshoot). Lisä tietoja määrityksistä on Ohje aiheessa [paikallisen tietoyhdyskäytäväsovelluksen käyttäminen](/data-integration/gateway/service-gateway-app).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Asenna paikallinen tietoyhdyskäytävä](/data-integration/gateway/service-gateway-install).
* Luo sovellus, joka muodostaa yhteyden paikalliseen tietolähteeseen, kuten [SQL Server](connections/connection-azure-sqldatabase.md) tai [SharePoint](connections/connection-sharepoint-online.md).
* [Jaa sovellus](share-app.md), joka muodostaa yhteyden paikalliseen tietolähteeseen.

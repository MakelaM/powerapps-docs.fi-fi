---
title: Pohjaan perustuvassa sovelluksessasi käytettävien resurssien jakaminen | Microsoft Docs
description: Tietoa pohjaan perustuvan sovelluksesi käyttämien resurssien jakamisesta PowerAppsissa
author: archnair
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/28/2016
ms.author: archanan
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4f303cdfba474448321d230bb61b698e8f959e5f
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61535924"
---
# <a name="share-canvas-app-resources-in-powerapps"></a>Pohjaan perustuvan sovelluksen resurssien jakaminen PowerAppsissa

Ennen kuin voit [jakaa pohjaan perustuvan sovelluksen](share-app.md), ota huomioon resurssityypit, joita se hyödyntää, kuten yhtä tai useampia seuraavista:

* Common Data Service-entiteettejä

    Lisätietoja oikeuksien antamisesta näiden tietojen käyttämiseen on ohjeaiheessa [Entiteetin käyttöoikeuksien hallinta](share-app.md#manage-entity-permissions).
    
* yhteys tietolähteeseen
* paikallinen tietoyhdyskäytävä
* mukautettu liitin
* Excelin työkirja tai muu palvelu
* työnkulku

Jotkin näistä resursseista jaetaan automaattisesti, kun jaat sovelluksen. Muut resurssit edellyttävät, että sinä tai henkilöt, joiden kanssa jaat sovelluksen, suorittavat lisätoimia, jotta sovellus toimii haluamallasi tavalla.

Voit jakaa yhteyksiäsi, mukautettuja liittimiä ja paikallisia tietoyhdyskäytäviä myös koko organisaation kanssa.

## <a name="connections"></a>Yhteydet

Jotkin yhteystyypit, kuten SQL Server, jaetaan automaattisesti, mutta muut edellyttävät, että käyttäjät luovat omia yhteyksiään tietolähteeseen tai sovelluksessa oleviin lähteisiin.

Osoitteessa [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) voit määrittää, jaetaanko yhteys automaattisesti, ja voit päivittää jakamisoikeudet. Napsauta tai napauta vasemmalla olevassa siirtymispalkissa kohtaa **Hallitse**, napsauta tai napauta kohtaa **Yhteydet** ja napsauta tai napauta yhteyttä. Jos **Jaa**-välilehti tulee näkyviin, yhteys jaetaan automaattisesti.

  ![Jaa-välilehti yhteyden tietosivulla](./media/share-app-resources/shared-connections.png)

## <a name="on-premises-data-gateways"></a>Paikalliset tietoyhdyskäytävät
Jos luot ja jaat sovelluksen, joka sisältää tietoja paikallisesta lähteestä, kyseinen [paikallinen tietoyhdyskäytävä](gateway-management.md) sekä tietyntyyppiset yhteydet tähän yhdyskäytävään jaetaan automaattisesti. Voit jakaa manuaalisesti jokaisen yhteyden, jota ei jaeta automaattisesti, kuten edellisessä osiossa näytettiin. Voit myös antaa sovelluksen lähettää sanoman, jossa käyttäjiä kehotetaan luomaan omat yhteydet. Niiden yhteyksien, joilla yhdyskäytävä on määritetty, näyttäminen:

1. Avaa [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), napsauta tai napauta vasemmalla olevassa siirtymispalkissa **Hallitse** ja napsauta tai napauta **Yhdyskäytävät**.
2. Napsauta tai napauta yhdyskäytävää ja napsauta tai napauta **Yhteydet**-välilehteä.

> [!NOTE]
> Jos jaat yhden tai useamman yhteyden manuaalisesti, voit joutua jakamaan sen uudelleen seuraavissa tilanteissa:

* Jos lisäät paikallisen tietoyhdyskäytävän sovellukseen, jonka olet jo jakanut.
* Jos vaihdat henkilöitä tai ryhmiä, joiden kanssa olet jakanut sovelluksen, jolla on paikallinen tietoyhdyskäytävä.

## <a name="custom-connectors"></a>Mukautetut liittimet
Kun jaat sovelluksen, joka käyttää mukautettua liitintä, se jaetaan automaattisesti, mutta käyttäjien täytyy luoda siihen omat yhteytensä.

Osoitteessa [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) voit tarkastella tai päivittää mukautettujen liittimien käyttöoikeuksia. Napsauta tai napauta vasemmalla olevassa siirtymispalkissa **Hallitse**, napsauta tai napauta **Yhteydet** ja napsauta tai napauta sen jälkeen **Uusi yhteys** (oikeassa yläkulmassa). Napsauta tai napauta kohtaa **Mukautettu**, ja napsauta tai napauta mukautettua liitintä saadaksesi sen tiedot näkyviin.

## <a name="excel-workbooks"></a>Excel-työkirjat
Jos jaettu sovellus käyttää tietoja, joihin kaikilla käyttäjillä ei ole pääsyä (esimerkiksi Excel-työkirja pilvitallennuspalvelun tilissä), [jaa tiedot](share-app-data.md).

## <a name="flows"></a>Työnkulut
Jos jaat sovelluksen, joka sisältää työnkulun, sovelluksen käyttäjiä pyydetään vahvistamaan tai päivittämään kaikki yhteydet, joita työnkulku hyödyntää. Lisäksi vain työnkulun luonut henkilö voi mukauttaa sen parametreja. Voit esimerkiksi luoda työnkulun, joka lähettää sähköpostia määrittämääsi osoitteeseen, mutta muut käyttäjät eivät voi muuttaa tätä osoitetta.


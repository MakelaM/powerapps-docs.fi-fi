---
title: Sovelluksessasi käytettyjen resurssien jakaminen | Microsoft Docs
description: Opi lisää siitä, miten sovelluksesi käyttämät resurssit jaetaan, kun sovellus on jaettu
documentationcenter: na
author: archnair
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 06/28/2016
ms.author: archanan
ms.openlocfilehash: f7943c5204dcab7c59e922bfb096f70d05b94e9b
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="share-app-resources"></a>Sovelluksen resurssien jakaminen
Ennen kuin voit [jakaa sovelluksen](share-app.md), ota huomioon resurssityypit, joita se hyödyntää, kuten yhtä tai useampia seuraavista:

* yhteys tietolähteeseen
* paikallinen tietoyhdyskäytävä
* mukautettu liitin
* Excelin työkirja tai muu palvelu
* työnkulku

Jotkin näistä resursseista jaetaan automaattisesti, kun jaat sovelluksen. Muut resurssit edellyttävät, että sinä tai henkilöt, joiden kanssa jaat sovelluksen, suorittavat lisätoimia, jotta sovellus toimii haluamallasi tavalla.

Voit myös jakaa yhteyksiäsi, mukautettuja liittimiä ja paikallisia tietoyhdyskäytäviä koko organisaation kanssa.

## <a name="connections"></a>Yhteydet
Jotkin yhteystyypit, kuten SQL Server, jaetaan automaattisesti, mutta muut edellyttävät, että käyttäjät luovat omia yhteyksiään tietolähteeseen tai sovelluksessa oleviin lähteisiin.

Osoitteessa [powerapps.com](https://web.powerapps.com) voit määrittää, jaetaanko yhteys automaattisesti, ja voit päivittää jakamisoikeudet. Napsauta tai napauta vasemman siirtymispalkin kohtaa **Hallitse**, napsauta tai napauta kohtaa **Yhteydet** ja napsauta tai napauta yhteyttä. Jos **Jaa**-välilehti tulee näkyviin, yhteys jaetaan automaattisesti.

  ![Jaa-välilehti yhteyden tiedot -sivulla](./media/share-app-resources/shared-connections.png)

## <a name="on-premises-data-gateways"></a>Paikalliset tietoyhdyskäytävät
Jos luot ja jaat sovelluksen, joka sisältää tietoja paikallisesta lähteestä, kyseinen [paikallinen tietoyhdyskäytävä](gateway-management.md) sekä tietyntyyppiset yhteydet tähän yhdyskäytävään jaetaan automaattisesti. Voit jakaa manuaalisesti jokaisen yhteyden, jota ei jaeta automaattisesti, kuten edellisessä osiossa näytettiin. Voit myös sallia sovelluksen näyttää käyttäjille kehotteen omien yhteyksien luomisesta. Niiden yhteyksien, joilla yhdyskäytävä on määritetty, näyttäminen:

1. Mene osoitteeseen [powerapps.com](https://web.powerapps.com), napsauta tai napauta vasemman siirtymispalkin kohtaa **Hallitse** ja napsauta tai napauta kohtaa **Yhdyskäytävät**.
2. Napsauta tai napauta yhdyskäytävää ja napsauta tai napauta **Yhteydet**-välilehteä.

> [!NOTE]
> Jos jaat yhden tai useamman yhteyden manuaalisesti, voit joutua jakamaan sen uudelleen seuraavissa tilanteissa:

* Lisäät paikallisen tietoyhdyskäytävän sovellukseen, jonka olet jo jakanut.
* Muutat henkilöitä tai ryhmiä, joiden kanssa olet jakanut sovelluksen, jolla on paikallinen tietoyhdyskäytävä.

## <a name="custom-connectors"></a>Mukautetut liittimet
Kun jaat sovelluksen, joka käyttää mukautettua liitintä, se jaetaan automaattisesti, mutta käyttäjien täytyy luoda siihen omat yhteytensä.

Osoitteessa [powerapps.com](https://web.powerapps.com) voit tarkastella tai päivittää mukautettujen liittimien käyttöoikeuksia. Napsauta tai napauta vasemman siirtymispalkin kohtaa **Hallitse**, napsauta tai napauta kohtaa **Yhteydet** ja napsauta tai napauta sitten kohtaa **Uusi yhteys** (oikeassa yläkulmassa). Napsauta tai napauta kohtaa **Mukautettu** ja napsauta tai napauta mukautettua liitintä saadaksesi sen tiedot näkyviin.

## <a name="excel-workbooks"></a>Excel-työkirjat
Jos jaettu sovellus käyttää tietoja, joihin kaikilla käyttäjillä ei ole käyttöoikeuksia (esimerkiksi Excel-työkirja pilvitallennuspalvelun tilissä), [jaa tiedot](share-app-data.md).

## <a name="flows"></a>Työnkulut
Jos jaat sovelluksen, joka sisältää työnkulun, sovelluksen käyttäjiä pyydetään vahvistamaan tai päivittämään kaikki yhteydet, joita työnkulku hyödyntää. Lisäksi vain työnkulun luonut henkilö voi mukauttaa sen parametreja. Voit esimerkiksi luoda työnkulun, joka lähettää sähköpostia määrittämääsi osoitteeseen, mutta muut käyttäjät eivät voi muuttaa tätä osoitetta.


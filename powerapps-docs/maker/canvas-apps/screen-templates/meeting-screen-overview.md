---
title: Koko uksen näyttö malli | Microsoft Docs
description: Tutustu siihen, miten kangas sovellusten koko uksen näyttö malli toimii, ja laajenna näyttöä omiin käyttö tapauksiisi
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/30/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c53857acfdcb44faa26b2ec3e04b904e25c09aee
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995640"
ms.PowerAppsDecimalTransform: true
---
# <a name="overview-of-the-meeting-screen-template-for-canvas-apps"></a>Kangas sovellusten koko uksen näytön mallin yleiskatsaus

Lisää kangas sovelluksessa Kokous näyttö, jonka avulla käyttäjät voivat luoda ja lähettää Kokous pyyntöjä Office 365 Outlook-tiliinsä. Käyttäjät voivat etsiä osallistujia organisaatiossaan ja lisätä ulkoisia Sähkö posti osoitteita. Jos vuokraajallasi on Outlookiin sisäisiä Kokous huoneita, käyttäjät voivat valita myös sijainnin.

Voit myös lisätä muita mallipohjaisia näyttöjä, jotka näyttävät eri tietoja Office 365-tieto koneesta, kuten [sähkö postista](email-screen-overview.md), organisaation [henkilöistä](people-screen-overview.md) ja käyttäjän [kalenterista](calendar-screen-overview.md).

Tässä yleiskatsauksessa opit näytön korkean tason toiminnot.

Lisä tietoja tämän näytön oletus toiminnoista saat katsomalla [koko uksen näytön viitta](meeting-screen-reference.md)uksen.

## <a name="prerequisite"></a>Edellytys

Perehtyneisyys näyttöjen ja muiden ohjaus objektien lisäämiseen ja määrittämiseen [, kun luot sovelluksen Powerappsissa](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Oletus toiminto

Kokous näytön lisääminen mallista:

1. [Kirjaudu sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin ja luo sitten sovellus tai Avaa olemassa oleva sovellus PowerApps Studio.

    Tässä ohje aiheessa näytetään Puhelin sovellus, mutta samat käsitteet koskevat myös Tablet-sovellusta.

1. Valitse valinta nauhan **Aloitus** -väli lehdeltä **Uusi näyttö** > -**Kokous**.

  Kun tämä on täytetty, Kokous näytön molemmat väli lehdet muistuttavat seuraavaa:

  ![Koko uksen näyttö, molemmat väli lehdet](media/meeting-screen/meeting-screen-full-both.png)

Muutama hyödyllinen Huomautus:

* Koko uksen näytön avulla sovelluksen käyttäjä voi luoda koko uksen Outlookissa.
  Käyttäjät voivat hakea ja lisätä osallistujia ja vaihtoehtoisesti lisätä Kokous huoneen koko ukseen.
* Jos haluat hakea käyttäjää organisaatiollesi, ala kirjoittaa nimensä teksti syöte-ruutuun kohdassa osallistujat.
* Kun haet henkilöitä, palautetaan vain 15 parasta tulosta.
* Jos haluat lisätä Sähkö posti osoitteita organisaatiosi ulkopuolisille osanottajille, kirjoita täydellinen, kelvollinen Sähkö posti osoite ja valitse +-kuvake, joka näkyy Sähkö posti osoitteen oikealla puolella.
* Jotta voit luoda koko uksen, sinun on lisättävä vähintään yksi henkilö osallistujaksi, annettava aihe ja valittava koko uksen aika **ajoitus** -väli lehdestä.
* Kun olet lähettänyt Kokous pyynnön, kaikki kyseisen koko uksen tiedot tyhjennetään.
* Lähetys kuvakkeen (oikean yläkulman) **onselect** -lauseke sisältää seuraavan kaavan:
    ```powerapps-comma
    Set( _myCalendarName; 
        LookUp( 'Office365'.CalendarGetTables().value; DisplayName = "Calendar" ).Name 
    );;
    ```
* "Calendar" on useimpien Office-käyttäjien kalenterien oletusarvoinen näyttö nimi, mutta organisaatiosi saattaa poiketa siitä. Jos näin on, voit muuttaa "kalenteri"-kohdetta organisaatiosi asianmukaiseksi termiksi.
* Saat virhe ilmoituksen, jos yrität ajoittaa kokousta, joka tapahtuu menneisyydessä, tai lisätä koko ukseen yli 20 henkeä.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Näytä tämän näytön viite asiakirjat](./meeting-screen-reference.md).
* [Lue lisä tietoja Office 365 Outlook Connectorista](../connections/connection-office365-outlook.md).
* [Lue lisä tietoja Office 365-käyttäjien liittimestä](../connections/connection-office365-users.md).

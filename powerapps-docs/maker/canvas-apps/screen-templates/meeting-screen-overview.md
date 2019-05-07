---
title: Kokouksen näytön malli | Microsoft Docs
description: Tutustu pohjaan perustuvat sovellukset kokouksen näytön malli toiminnasta ja laajenna oman käyttötapauksissa näytön
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/30/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 24f04ff9ce95f603f5f7d4dc7d217146b9eebef8
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61535970"
ms.PowerAppsDecimalTransform: true
---
# <a name="overview-of-the-meeting-screen-template-for-canvas-apps"></a>Pohjaan perustuvat sovellukset kokouksen näytön-mallin yleiskatsaus

Lisää kangas-sovellus, jonka avulla käyttäjät voivat luoda ja Lähetä kokous Office 365 Outlook-tilinsä kokouksen näyttö. Käyttäjät voivat etsiä niiden organisaation osallistujat ja Lisää ulkoinen sähköpostiosoitteet. Jos vuokraaja on rakennettu Outlook kokouksen huoneet, käyttäjät voivat valita myös sijainti.

Voit myös lisätä malliin perustuvan muun, joka näyttää eri Office 365: stä kuten [sähköpostin](email-screen-overview.md), [ihmiset](people-screen-overview.md) ja organisaation käyttäjän [kalenterin](calendar-screen-overview.md).

Tästä yleiskatsauksesta opetetaan tietoja näytön korkean tason toiminnoista.

Katso tarkemmin tarkemmin tässä näytössä oletusarvon toimintoja [kokouksen näytön viittaus](meeting-screen-reference.md).

## <a name="prerequisite"></a>Edellytys

Miten voit lisätä ja määrittää näyttöjä ja muita ohjausobjekteja sinuna tuntee [sovelluksen luominen powerappsin](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Default-toiminnot

Lisää näyttö kokouksen mallista:

1. [Kirjaudu sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin, ja luo sovellus tai avaa olemassa olevaa sovellusta PowerApps Studio.

    Tässä aiheessa näytetään puhelinsovelluksen, mutta samat käsitteet koskevat tablettisovellusta.

1. Valitse **aloitus** Valitse valintanauhan välilehti **uuden näytön** > **kokouksen**.

  Kun täyttää molemmista välilehdistä kokouksen näytön näyttää tältä:

  ![Kokouksen näytön molemmista välilehdistä](media/meeting-screen/meeting-screen-full-both.png)

Joitakin hyödyllisiä Huomautuksia:

* Kokouksen näytön avulla sovelluksen käyttäjä luo kokouksen Outlookissa.
  Käyttäjät voivat etsiä ja lisätä osallistujia ja, voit lisätä Kokoushuone kokouksen.
* Etsi käyttäjä organisaatiossasi, ala kirjoittaa nimensä ”osallistujat” Tekstisyöte-ruudusta.
* Kun etsit henkilöitä, vain 15 parhaat tulokset palautetaan.
* Lisää sähköpostiosoitteet osallistujien organisaatiosi ulkopuolella, kirjoita ulos koko, kelvollinen sähköpostiosoite ja valitse ”+”-kuvakkeen, joka näkyy oikealla puolella sähköpostiosoite.
* Kokouksen luomiseen on Lisää vähintään yksi henkilö osallistuja, anna aihe ja valitse kokouksen ajan **aikataulun** välilehti.
* Kun olet lähettänyt kokouspyyntö, kaikki tiedot kyseiseen kokoukseen on poistettu.
* **OnSelect** Lähetä-kuvake (oikeassa yläkulmassa)-lause sisältää tämä kaava:
    ```powerapps-comma
    Set( _myCalendarName; 
        LookUp( 'Office365'.CalendarGetTables().value; DisplayName = "Calendar" ).Name 
    );;
    ```
* ”Kalenterin” on useimpien Office-käyttäjien kalenterien oletusarvon näyttönimi, mutta organisaatiosi saattaa vaihdella. Jos näin on, voit muuttaa ”kalenterin”-org. asianmukainen termi
* Näkyviin tulee virhe, jos yrität kokouksen, joka on jo mennyt tai lisää yli 20 ihmisiä kokoukseen.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Näytä tämä näyttö ohjeessa](./meeting-screen-reference.md).
* [Lue lisätietoja Office 365 Outlook-liittimessä](../connections/connection-office365-outlook.md).
* [Lue lisätietoja Office 365-käyttäjät-liittimen](../connections/connection-office365-users.md).

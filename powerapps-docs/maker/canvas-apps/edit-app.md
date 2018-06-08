---
title: Sovelluksen muokkaaminen | Microsoft Docs
description: Vaiheittaiset ohjeet sovellusten muokkaamiseen ja istunnon lukitustilanteisiin.
documentationcenter: na
author: karthik-1
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 05/19/2017
ms.author: sharik
ms.openlocfilehash: d6c857a75a21123cdd0e826682fc595a503d67fd
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "32328785"
---
# <a name="edit-an-app-in-powerapps"></a>Sovelluksen muokkaaminen PowerAppsissa
Muokkaa mitä tahansa sovellusta, jonka olet luonut tai johon sinulla on **voi muokata** -käyttöoikeudet. Voit muokata sovellusta PowerApps Studiossa. Jos yrität muokata sovellusta, joka on avoimena muokkausta varten muualla, viesti kertoo, onko se jo sinulla avattuna, vai onko se toisella käyttäjällä.

## <a name="verify-your-permissions"></a>Tarkista oikeutesi
1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com) ja napsauta tai napauta kohtaa **Sovellukset** **Tiedosto**-valikossa (vasemmassa reunassa).
   
    ![Tiedosto-valikon Sovellukset-vaihtoehto](./media/edit-app/file-apps.png)

2. Klikkaa tai napauta sovellusluokan valitsimessa **Sovellukset, joita voin muokata**.

    Voit muokata mitä tahansa esiin tulevassa luettelossa olevaa sovellusta. Voit myös etsiä sovellusta kirjoittamalla yhden tai useamman merkin hakukenttään oikean yläkulman lähellä.

    > [!NOTE]
    > Jos et vieläkään näe sovellusta, jota haluat muokata, varmista, että olet valinnut oikean ympäristön oikean yläkulman lähellä.
   
    ![Ympäristöluettelo](./media/edit-app/environment-list.png)

1. Napsauta tai napauta kolmea pistettä (...) sen sovelluksen kohdalla, jota haluat muokata, ja napsauta tai napauta kohtaa **Muokkaa**.

## <a name="collaborate-on-an-app"></a>Sovelluksen yhteiskäyttö
Kuka tahansa, jolla on sovellukseen **voi muokata** -käyttöoikeudet, voi muokata sitä, mutta vain yksi henkilö voi muokata sovellusta kerrallaan. Jos yrität muokata sovellusta, jota joku muu on jo muokkaamassa, tämä sanoma tulee näkyviin. Et voi jatkaa ennen kuin toinen henkilö sulkee sovelluksen (tai ennen kuin tämän henkilön istunto aikakatkaistaan).

![](./media/edit-app/applock-otheruser.png)

Lisäksi tämä sanoma tulee näyttöön, jos avaat sovelluksen muokattavaksi ja yrität sitten avata sen toisessa laitteessa tai toisessa selainikkunassa. Voit ohittaa edellisen istunnon, mutta saatat menettää muutoksia, joita et ole tallentanut.

![](./media/edit-app/applock-selfuser.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Opi lisää siitä, miten voit lisätä [näytön](add-screen-context-variables.md), [ohjausobjektin](add-configure-controls.md) tai [tietoyhteyden](add-data-connection.md).


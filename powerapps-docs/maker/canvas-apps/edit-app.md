---
title: Sovelluksen muokkaaminen | Microsoft Docs
description: Vaiheittaiset ohjeet sovellusten muokkaamiseen ja istunnon lukitustilanteisiin.
services: ''
suite: powerapps
documentationcenter: na
author: karthik-1
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/19/2017
ms.author: sharik
ms.openlocfilehash: a71aa71ec80a60f2aec4ce179abcade3f9eef964
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="edit-an-app-in-powerapps"></a>Sovelluksen muokkaaminen PowerAppsissa
Muokkaa mitä tahansa sovellusta, jonka olet luonut tai johon sinulla on **voi muokata** -käyttöoikeudet. Voit muokata sovellusta PowerApps Studiossa joko verkossa tai Windowsissa. Jos yrität muokata sovellusta, joka on avoimena muokkausta varten muualla, viesti kertoo, onko se jo sinulla avattuna, vai onko se toisella käyttäjällä.

## <a name="verify-your-permissions"></a>Tarkista oikeutesi
1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com) ja napsauta tai napauta kohtaa **Sovellukset** **Tiedosto**-valikossa (vasemmassa reunassa).
   
    ![Tiedosto-valikon Sovellukset-vaihtoehto](./media/edit-app/file-apps.png)
2. Avaa sovellusluokan valitsin ja napsauta tai napauta kohtaa **Omistamani sovellukset** tai **Sovellukset, joiden laatimiseen olen osallistunut**.
   
    ![Sovellusluokan valitsin](./media/edit-app/app-category.png)
   
    Voit muokata mitä tahansa esiin tulevassa luettelossa olevaa sovellusta. Voit myös etsiä sovellusta kirjoittamalla yhden tai useamman merkin hakukenttään oikean yläkulman lähellä.
   
    > [!NOTE]
> Jos et vieläkään näe sovellusta, jota haluat muokata, varmista, että olet valinnut oikean ympäristön oikean yläkulman lähellä.
   
    ![Ympäristöluettelo](./media/edit-app/environment-list.png)

## <a name="edit-an-app-in-powerapps-studio-for-web"></a>Muokkaa sovellusta PowerApps Studiossa verkossa
1. Etsi sovellus, jota haluat muokata, edellisten ohjeiden mukaisesti.
2. Napsauta tai napauta sovelluksen tiedot -kuvaketta lähellä oikeaa reunaa.
   
    ![Tiedot-kuvake](./media/edit-app/app-edit.png)
3. Napsauta tai napauta **Muokkaa**-kuvaketta lähellä oikeaa yläkulmaa ja napsauta tai napauta sitten kohtaa **Muokkaa verkossa**.
   
    ![Muokkaa-kuvake](./media/edit-app/edit-icon.png)

## <a name="edit-an-app-in-powerapps-studio-for-windows"></a>Muokkaa sovellusta PowerApps Studiossa Windowsissa
1. Avaa PowerApps Studio for Windows.
2. Valitse oletuksena näkyviin tulevalla sivulla sovellus, jota haluat muokata.
   
    Voit etsiä sovelluksen helpommin napsauttamalla tai napauttamalla oikean yläkulman lähellä olevaa hakukuvaketta ja kirjoittamalla sitten yhden tai useamman merkin sovelluksen nimestä. Voit myös lajitella luettelon nimen, viimeisimmän muokkauspäivämäärän tai viimeisimmän avauspäivämäärän perusteella. Jos haluamaasi sovellusta ei vieläkään näy, varmista, että olet oikeassa PowerApps-ympäristössä, kuten ensimmäisessä toimintosarjassa kuvataan.
   
    ![](./media/edit-app/sort-filter.png)
3. Napsauta tai napauta muokattavan sovelluksen kynäkuvaketta, joka sijaitsee lähellä oikeaa reunaa.
   
    Voit muokata mikä tahansa sovellusta, jonka kynäkuvake on musta, ei harmaa.
   
    ![](./media/edit-app/app-editstudio.png)

## <a name="collaborate-on-an-app"></a>Sovelluksen yhteiskäyttö
Kuka tahansa, jolla on sovellukseen **voi muokata** -käyttöoikeudet, voi muokata sitä, mutta vain yksi henkilö voi muokata sovellusta kerrallaan. Jos yrität muokata sovellusta, jota joku muu on jo muokkaamassa, tämä sanoma tulee näkyviin. Ei voi jatkaa ennen kuin toinen henkilö sulkee sovelluksen (tai ennen kuin tämän henkilön istunto aikakatkaistaan).

![](./media/edit-app/applock-otheruser.png)

Lisäksi tämä sanoma tulee näyttöön, jos avaat sovelluksen muokattavaksi ja yrität sitten avata sen toisessa laitteessa tai toisessa selainikkunassa. Voit ohittaa edellisen istunnon, mutta saatat menettää muutoksia, joita et ole tallentanut.

![](./media/edit-app/applock-selfuser.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Opi lisää siitä, miten voit lisätä [näytön](add-screen-context-variables.md), [ohjausobjektin](add-configure-controls.md) tai [tietoyhteyden](add-data-connection.md).


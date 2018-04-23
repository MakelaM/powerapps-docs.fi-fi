---
title: Pikaohje ympäristöissäsi ladattujen sovellusten luettelon lataamiseksi | Microsoft Docs
description: Tämän pikaoppaan avulla opit lataamaan ympäristöissäsi luotujen sovellusten luettelon
services: powerapps
suite: powerapps
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: quickstart
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: sharik
ms.openlocfilehash: debe9dd0ab3aa948537820cccd3304a6b4225c54
ms.sourcegitcommit: c5e3991e0e4e9f22a1e094d699f35adabfb97c6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/03/2018
---
# <a name="quickstart-download-a-list-of-apps-created-in-your-environments"></a>Pikaopas: lataa ympäristöissäsi luotujen sovellusten luettelo
Jos olet ympäristön järjestelmänvalvoja, voit tarkastella ja ladata luettelon sovelluksista, jotka on luotu ympäristöissä, joita hallitset. Jos olet 365:n yleinen järjestelmänvalvoja tai Azure Active Directory -vuokraajan järjestelmänvalvoja, voit tarkastella ja ladata luettelon sovelluksista, jotka on luotu kaikissa organisaatiosi ympäristöissä.

Tässä pikaoppaassa opetetaan, miten ladataan yhdessä ympäristössä luotujen sovellusten luettelo .csv-tiedostoon ja tarkastellaan tätä luetteloa Excelissä.

## <a name="prerequisites"></a>Edellytykset
 Tämän pikaoppaan noudattamista varten tarvitaan seuraavat kohteet:
 * PowerAppsin palvelupaketin 2 tai Microsoft Flow -palvelupaketin 2 käyttöoikeus. Vaihtoehtoisesti voit rekisteröityä [ilmaisen PowerAppsin palvelupaketin 2 kokeiluversion](https://web.powerapps.com/signup?redirect=marketing&email=) käyttäjäksi.
 * PowerApps-ympäristön järjestelmänvalvojan, Office 365:n yleisen järjestelmänvalvojan tai Azure Active Directory vuokraajan järjestelmänvalvojan oikeudet. Lisätietoja on artikkelissa [ympäristöjen hallinta PowerAppsissa](environments-administration.md).

## <a name="sign-in-to-the-powerapps-admin-center"></a>Kirjaudu sisään PowerApps-hallintakeskukseen
Kirjaudu sisään hallintakeskukseen osoitteessa [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="download-the-list-of-apps"></a>Lataa luettelo sovelluksista
1. Napsauta tai napauta siirtymisruudussa kohtaa**Ympäristöt** ja napsauta tai napauta ympäristöä, jonka sovellusten luettelon haluat ladata.

    ![Tiedosto ja jakaminen](./media/admin-view-apps/environment.png)
2. Napsauta tai napauta **Resurssit**-välilehdellä kohtaa **Sovellukset** ja napsauta tai napauta kohtaa **Lataa sovellusten luettelo**.

    ![Tiedosto ja jakaminen](./media/admin-view-apps/resources-app.png)

    Sovellusten luettelo ladataan .csv-tiedostoon. Tämä voi kestää useita minuutteja. Varmista, että et sulje ikkunaa, ennen kuin luettelo on latautunut kokonaan, tai joudut ehkä käynnistämään prosessin uudelleen.

## <a name="view-the-list"></a>Luettelon tarkasteleminen
Kun .csv-tiedosto on luotu, avaa se Excelissä. Luettelo sisältää sovelluksen näyttönimen, sovelluksen omistajan, kaikki yhdistimet, joita sovellus käyttää muodostaessaan yhteyden tietolähteisiin ja muita tietoja.

![Tiedosto ja jakaminen](./media/admin-view-apps/excel-view.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä pikaoppaassa sinulle opetettiin, miten lataat organisaatiosi ympäristössä luotujen sovellusten luettelon ja tarkastelet sitä. Seuraavaksi opit hallinnoimaan organisaatiossasi luotuja sovelluksia.

> [!div class="nextstepaction"]
> [Hallitse organisaatiossasi luotuja sovelluksia](admin-manage-apps.md)

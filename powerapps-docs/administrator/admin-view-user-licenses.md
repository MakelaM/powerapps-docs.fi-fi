---
title: Vuokraajasi aktiivisten käyttäjien luettelon lataaminen | Microsoft Docs
description: Tämän pikaoppaan avulla opit lataamaan luettelon vuokraajasi aktiivisista käyttäjistä
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/21/2018
ms.author: jimholtz
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 41f557b7b4def385a505e3bc3047354add81955e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42832444"
---
# <a name="download-a-list-of-active-users-in-your-tenant"></a>Lataa luettelo vuokraajasi aktiivisista käyttäjistä
Jos olet 365:n yleinen järjestelmänvalvoja tai Azure Active Directory -vuokraajan järjestelmänvalvoja, voit ladata vuokraajasi aktiivisten käyttäjien luettelon. Näin voit nähdä PowerAppsin, Microsoft Flow’n tai molempien käyttäjien lisäksi myös näille käyttäjille määritetyt käyttöoikeudet.

Tässä aiheessa opetetaan, miten aktiivisten käyttäjien luettelo ladataan .csv-tiedostoon ja tätä luetteloa tarkastellaan Excelissä.

Jotta voit käyttää näitä vaiheita, tarvitset Office 365:n yleisen järjestelmänvalvojan tai Azure Active Directory -vuokraajan järjestelmänvalvojan oikeudet.

## <a name="sign-in-to-the-powerapps-admin-center"></a>PowerApps-hallintakeskukseen kirjautuminen
Kirjaudu sisään hallintakeskukseen osoitteessa [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="download-the-list-of-users"></a>Lataa käyttäjien luettelo
Napsauta tai napauta siirtymisruudussa **Käyttöoikeudet** ja napsauta tai napauta sitten **Lataa aktiivisten käyttöoikeuksien luettelo**.

![Tiedosto ja jakaminen](./media/admin-view-user-licenses/download-list.png)

Käyttäjäluettelo ladataan .csv-tiedostoon. Tämä voi kestää useita minuutteja. Varmista, että et sulje ikkunaa, ennen kuin luettelo on latautunut kokonaan, tai joudut ehkä käynnistämään prosessin uudelleen.

## <a name="view-the-list"></a>Luettelon tarkasteleminen
Kun .csv-tiedosto on luotu, avaa se Excelissä. Luettelo sisältää kunkin käyttäjän nimen, sähköpostiosoitteen käyttöoikeustyypin ja muita tietoja.

Jos käyttäjä on käyttänyt tuotetta vähintään kerran, häntä pidetään *aktiivisena käyttäjänä*. Koska tämä on aktiivisten käyttäjien luettelo, se ei sisällä käyttäjiä, joilla on käyttöoikeudet PowerAppsiin ja Microsoft Flow’hun, mutta eivät ole koskaan käyttänyt niitä. Voit tarkastella kaikkien käyttäjien käyttöoikeuksia [Office 365 -hallintakeskuksessa](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

Seuraavassa esimerkissä on kaksi käyttäjää, joilla on käyttöoikeudet sekä PowerAppsiin että Microsoft Flow’hun. Tiina Lassilalla on käyttöoikeus Office 365 -tilauksen kautta, ja Jussi Lassilalla on kunkin tuotteen kokeiluversion käyttöoikeus.

![Tiedosto ja jakaminen](./media/admin-view-user-licenses/table2.png)

Jos käyttäjä on lähtenyt organisaatiosta, luettelossa näkyy **Tuntematon** **Käyttäjänimi**- ja **Sähköpostiosoite**-sarakkeissa. Jos luettelossa näkyy **Tuntematon**, mutta kukaan ei on lähtenyt organisaatiosta, odota muutama minuutti ja lataa luettelo sitten uudelleen.

Voit lisätä käyttöoikeuksia avaamalla [Office 365 -hallintakeskuksen](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä aiheessa opimme lataamaan luettelon vuokraajasi aktiivisista käyttäjistä ja tarkastelemaan sitä. Siirry seuraavaan aiheeseen, jotta opit lataamaan ympäristöissäsi luotujen sovellusten luettelon.

> [!div class="nextstepaction"]
> [Lataa ympäristöissäsi luotujen sovellusten luettelo](admin-view-apps.md)

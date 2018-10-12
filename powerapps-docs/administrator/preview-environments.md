---
title: Ympäristöjen esikatselu | Microsoft Docs
description: Ota toimintoja käyttöön ennen virallista julkaisua osallistumalla PowerAppsin esiversio-ohjelmaan
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 08/29/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: e2c4c735827941b32ce5e019eb8d71e4328e4a7a
ms.sourcegitcommit: b8eee36e680036accb0e7d9fc7a434906af1c4d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/30/2018
ms.locfileid: "43297906"
---
# <a name="powerapps-preview-program"></a>PowerAppsin esiversio-ohjelma
PowerApps päivittää ympäristön ja sen toiminnot muutaman päivän tai viikon välein. PowerAppsin esiversio-ohjelman avulla pääset käyttämään tulevia toimintoja ja päivityksiä jo ennen kuin ne tulevat saataville muilla alueilla (kun asiakastuotantosovellukset otetaan käyttöön). 

PowerAppsin esiversio-ohjelman ominaisuudet:
- **Kokeile, opettele ja arvioi tulevia toimintoja**: Monet toiminnot julkaistaan ensin esikatseluun muutaman päivän ajaksi palautteen saamiseksi. Osallistumalla esiversio-ohjelmaan saat tietoa uusista toiminnoista muita ennen ja voit antaa palautetta. Lisäksi voit hyödyntää uusia toimintoja heti, kun ne saapuvat alueille, joissa tuotantosovellukset luodaan.
- **Mahdollista liiketoiminnan jatkuvuus varmistamalla, että nykyiset sovellukset toimivat edelleen** PowerAppsin tulevissa julkaisuissa (vNext).

## <a name="what-in-powerapps-is-available-for-preview"></a>Mikä PowerAppsissa on käytettävissä esikatselussa?
PowerAppsin esikatselutoimintojen käyttäminen edellyttää esikatseluympäristön käyttämistä. Lisätietoja esikatseluympäristöstä on seuraavassa osiossa.
Tällä hetkellä esikatselu otetaan käyttöön seuraavissa PowerAppsin skenaarioissa:
1. **Sovellusten luominen**: Voit luoda pohjaan perustuvia sovelluksia käyttämällä PowerAppsin seuraavaa versiota. Tämä tehdään luomalla sovellukset esikatseluympäristössä. Nykyisin rajoituksena on muun muassa se, että mallipohjaisia sovelluksia ei voi luoda esiversio-ohjelmassa. Tilanne pyritään korjaamaan.
2. **Sovellusten hallinta**: Voit hallita ja jakaa sovelluksia käyttämällä [PowerAppsin verkkoportaalia][2]. Esikatselutoimintojen käyttämiseen tarvitaan esikatseluympäristö. Sen kautta pääset [PowerAppsin verkkoportaalin][3] esikatseluversioon.
3. **Sovellusten toistaminen**: Sovellukset on toistettava esikatseluympäristössä verkkosoittimella. Kun teet sen, sinut siirretään automaattisesti [verkkosoittimen esikatseluversioon][4]. Sovellukset toistuvat PowerAppsin verkkosoittimen vNext-versiossa. Nykyisin rajoituksena on muun muassa se, että iOS:n, Androidin ja Windowsin PowerApps Mobile -versiot eivät ole tällä hetkellä käytettävissä esikatselua varten. First Release -ympäristössä luotujen sovellusten toistaminen ei välttämättä toimi. Tilanne pyritään korjaamaan.
4. **PowerAppsin hallinta**: Hallintakäyttökokemukset ovat käytettävissä esikatselua varten käyttämällä [PowerApps-hallintakeskuksen esikatseluversiota][1].

## <a name="how-to-get-early-access-to-the-upcoming-updates"></a>Miten pääsen käyttämään tulevia päivityksiä ennen niiden virallista julkaisua?
PowerAppsissa kaikki sovellukset ja niihin liittyvät resurssit tallennetaan ympäristöön. Pääsy kaikkiin esikatselutoimintoihin ennen virallista julkaisua on myös käytettävissä ympäristössä, joka on luotu alueella, jossa vNext (esikatselu) on otettu käyttöön. Nyt alueita on vain yksi, **Esikatselu (Yhdysvallat)**, kuten alla olevassa kuvassa näkyy:

![](./media/preview-environment/env3-preview.png)

Valitse ympäristölle alue **Esikatselu (Yhdysvallat)** ja hyväksy esiversio-ohjelmaan osallistumisen ehdot. Sen jälkeen voit luoda ympäristön, jonka kautta pääset käyttämään PowerAppsin seuraavaa versiota (vNext).
Kaikki tässä ympäristössä luodut sovellukset ja muut resurssit ovat ympäristön vNext-versiossa (SAAS).

## <a name="how-to-learn-about-the-latest-updates"></a>Miten uusimmista päivityksistä saa tiedon?
Saat tiedon esikatseluun käytettävissä olevista uusista toiminnoista artikkelista [PowerAppsin uudet ominaisuudet][5]. Toiminnoissa, jotka ovat käytettävissä vain esikatseluun, on Esikatselu-tunniste.

## <a name="key-scenarios-to-test-with-the-preview-program"></a>Tärkeimmät esiversio-ohjelmassa testattavat skenaariot
1. **Tuotantosovellusten vahvistaminen tulevilla PowerApps-päivityksillä (vNext)**

   Tuotantosovellukset kannattaa ehkä vahvistaa sen varmistamiseksi, että ne toimivat seuraavissa PowerAppsin tulevissa päivityksissä. Voit [kopioida][6] sovellukset tuotantoympäristöstä First Release -julkaisun ympäristöön ja testata skenaarioita toistamalla sovellukset. Huomaa, että kaikki muut tarvittavat resurssit, kuten CustomAPI, Flow jne., on myös siirrettävä sovelluksen mukana. Tämän pitäisi vain luoda uusi kopio sovelluksista ja tarvittavista resursseista. Voit aloittaa uudempien päivitysten testaamisen sovelluksen toistamisen lisäksi myös sovellusten muokkaamisen ja hallinnan yhteydessä.
   
2. **Esikatselussa käytettävissä olevien uusien toimintojen kokeileminen**

   Julkaisemme useita uusia toimintoja ensin **Esikatselu (Yhdysvallat)** -alueella. Voit kokeilla uusia toimintoja ennen niiden julkaisua muilla alueilla (mikä saattaa vaikuttaa tuotantoympäristösi).

## <a name="how-to-provide-feedback-to-the-product-team"></a>Miten tuotantotiimille annetaan palautetta?
Voit antaa palautetta [PowerApps-keskustelupalstalla][8] ja/tai ottamalla yhteyttä [tukeen][9].

## <a name="what-are-the-known-issues-and-limitations"></a>Mitä ovat tunnetut ongelmat ja rajoitukset?
1. **PowerAppsin portaalit ja asiakkaat, jotka eivät ole käytettävissä esikatselussa** 

   Tietyt toiminnot, palvelut ja portaalit ovat käytettävissä esikatselussa:
   
   ![](./media/preview-environment/table.png)

2. **First Release -ympäristössä luotujen sovellusten käyttäminen Windowsin Desktop Studiossa**

   Kuten aiemmin mainittiin, Windowsin Desktop Studio ei ole käytettävissä esikatselussa. Näin ollen sovellusten luominen tai muokkaaminen esikatseluympäristössä ei välttämättä ole yhteensopiva Desktop Studion kanssa ja seuraava virhesanoma voi tulla näkyviin:
   
   ![](./media/preview-environment/error2.jpg)

   Tällaisessa tapauksessa on suositeltavaa käyttää Web Studiota sovelluksen luomiseen tai muokkaamiseen esikatseluympäristössä.

3. **Tietokantaa ei voi luoda esikatselualueella**

   Tällä hetkellä Common Data Service for Appsilla ei voi luoda tietokantaa ympäristössä Esikatselu (Yhdysvallat) -alueella. Tilanne pyritään korjaamaan.


<!--Reference links in article-->
[1]: https://preview.admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://preview.web.powerapps.com
[4]: https://preview.web.powerapps.com/webplayer
[5]: https://docs.microsoft.com/powerapps/maker/canvas-apps/release-notes
[6]: https://docs.microsoft.com/powerapps/administrator/environment-and-tenant-migration
[7]: https://preview.create.powerapps.com
[8]: https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1
[9]: https://powerapps.microsoft.com/support/


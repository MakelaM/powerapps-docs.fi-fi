---
title: Pikaopas tietojen menetyksen estämiskäytännön luomiseen | Microsoft Docs
description: Tämän pikaoppaan avulla opit luomaan tietojen menetyksen estämiskäytännön PowerAppsissa
services: powerapps
suite: powerapps
documentationcenter: na
author: SKjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: quickstart
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/30/2018
ms.author: sharik
ms.openlocfilehash: d349c9743349ca9daeedc5a6c3268ff07c8b12de
ms.sourcegitcommit: c5e3991e0e4e9f22a1e094d699f35adabfb97c6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/03/2018
---
# <a name="quickstart-create-a-data-loss-prevention-dlp-policy"></a>Pikaopas: Tietojen menetyksen estämiskäytännön luominen
Jotta tietoturva voidaan taata organisaatiossa, PowerApps antaa mahdollisuuden luoda ja valvoa käytäntöjä jotka määrittävät, minkä kuluttajaliitinten kanssa tietyt yritystiedot voidaan jakaa. Näitä tietojen jakamista määrittäviä käytäntöjä kutsutaan tietojen menetyksen estämiskäytännöiksi (DLP-käytännöt). DLP-käytännöt varmistavat, että tietoa hallitaan yhtenäisellä tavalla koko organisaatiossa. Käytännöt estävät tärkeän yritystiedon tahattoman julkaisun liittimiin, kuten sosiaalisen median sivustoihin.

Tässä pikaoppaassa opit luomaan DLP-käytännön yksittäiseen ympäristöön, joka estää Common Data Service- ja SharePoint-tietokantoihin tallennettujen tietojen julkaisun Twitterissä.

## <a name="prerequisites"></a>Edellytykset
Tämän pikaoppaan noudattamista varten tarvitaan **yksi** seuraavista kohteista:
* Azure Active Directory -vuokraajan järjestelmänvalvojan oikeudet
* Office 365:n yleisen järjestelmänvalvojan oikeudet
* PowerApps-ympäristöjärjestelmänvalvojan oikeudet sekä PowerApps-paketti 2, Microsoft Flow -paketti 2 tai [PowerApps-paketin 2 kokeiluversio](https://web.powerapps.com/signup?redirect=marketing&email=)

Lisätietoja on kohdassa [Ympäristöjen hallinta PowerAppsissa](environments-administration.md).

## <a name="sign-in-to-the-powerapps-admin-center"></a>PowerApps-hallintakeskukseen kirjautuminen
Kirjaudu sisään hallintakeskukseen osoitteessa [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="create-a-dlp-policy"></a>DLP-käytännön luominen
1. Napsauta tai napauta siirtymisruudussa **Tietokäytännöt** ja napsauta tai napauta **Uusi käytäntö**.

    ![](./media/create-dlp-policy/new-data-policy.png)
2. **Tietokäytännön nimi** -kenttä täytetään automaattisesti nimellä, joka perustuu käytännön luontiaikaan ja -päivämäärään. Muuta nimeksi **Secure Data Access for Contoso**.

    ![](./media/create-dlp-policy/policy-name.png)
3. **Ympäristöt**-välilehden valinnat vaihtelevat sen mukaan, oletko ympäristön järjestelmänvalvoja vai vuokraajan järjestelmänvalvoja. Jos olet ympäristön järjestelmänvalvoja, valitse ympäristö avattavasta luettelosta ja napsauta tai napauta **Jatka**.

    ![](./media/create-dlp-policy/select-environment.png)

    Jos olet vuokraajan järjestelmänvalvoja, voit luoda DLP-käytäntöjä, jotka koskevat yhtä tai useampaa ympäristöä tai kaikkia vuokraajan ympäristöjä (mukaan lukien kokeilukäyttöoikeutta käyttämällä luodut ympäristöt). Napsauta tai napauta tässä pikaoppaassa **Käytä VAIN valittuihin ympäristöihin**, valitse ympäristö avattavasta luettelosta ja napsauta tai napauta **Jatka**.

    ![](./media/create-dlp-policy/select-environment-tenant.png)

    Huomaa, että ympäristön DLP-käytännöt eivät voi korvata vuokraajan kaikenkattavia DLP-käytäntöjä.
4. Napsauta tai napauta **Tietoryhmät**-välilehden **Vain yritystiedot** -kohdassa **Lisää**.

    ![](./media/create-dlp-policy/data-groups.png)
5. Valitse **Lisää liittimiä** -ikkunassa **Common Data Service** ja **SharePoint** (voit joutua vierittämään näyttöä tai hakemaan ne) ja napsauta tai napauta sitten **Lisää liittimiä** lisätäksesi ne **Vain yritystiedot** -tietoryhmään.

    ![](./media/create-dlp-policy/add-connectors.png)

    Liittimet voivat olla vain yhdessä tietoryhmässä kerrallaan, ja ne lisätään oletuksena **Yritystietoja ei sallita** -ryhmään. Siirtämällä Common Data Servicen ja SharePointin **Vain yritystiedot** -ryhmään estät käyttäjiä luomasta työnkulkuja ja sovelluksia, jotka yhdistävät nämä kaksi liitintä jollain **Yritystietoja ei sallita** -ryhmän liittimellä.

6. Napsauta **Tallenna käytäntö**.

    ![](./media/create-dlp-policy/save-policy.png)

Secure Data Access for Contoso -käytäntö luodaan, ja se näkyy tietojen menetyksen estämiskäytäntöjen luettelossa. Koska Twitter-liitin on **Yritystietoja ei sallita** -tietoryhmässä, tämä käytäntö varmistaa, että Common Data Service ja SharePoint eivät jaa tietoja Twitterin kanssa.

Järjestelmänvalvojien kannattaa jakaa luettelo DLP-käytännöistä organisaation kanssa, jotta käyttäjät ovat tietoisia käytännöistä ennen sovellusten luomista.

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä pikaoppaassa olet oppinut luomaan DLP-käytännön yksittäiseen ympäristöön estääksesi tärkeiden yritystietojen tahattoman julkaisun liittimiin, kuten Twitteriin. Saat lisätietoja DLP-käytännöistä tutustumalla niiden hallintaa koskevaan artikkeliin.

> [!div class="nextstepaction"]
> [Tietojen menetyksen estämiskäytäntöjen hallinta](prevent-data-loss.md)

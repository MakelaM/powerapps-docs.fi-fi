---
title: Ympäristön luominen | Microsoft Docs
description: Tämän pikaoppaan avulla opit luomaan ympäristön
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/21/2018
ms.author: jimholtz
ms.openlocfilehash: eefcd30e4f5e6ec7441147c157cbb46864ebf718
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/30/2018
ms.locfileid: "39349244"
---
# <a name="create-an-environment"></a>Ympäristön luominen
Ympäristö on tila, jossa voit tallentaa, hallita ja jakaa organisaatiosi yritystietoja, sovelluksia ja työnkulkuja. Lisäksi sitä käytetään säilönä erillisille sovelluksille, joilla voi olla eri rooleja, suojausvaatimuksia tai kohdekäyttäjäryhmiä. PowerApps luo jokaiselle vuokraajalle automaattisesti yhden oletusympäristön, joka jaetaan kaikille käyttäjille kyseisessä vuokraajassa.

Jokaisella ympäristöllä voi olla enintään yksi Common Data Service -tietokanta, joka tarjoaa tallennustilaa sovelluksille. Käyttäjien ympäristössä luoma sovellus voi muodostaa yhteyden mihin tahansa tietolähteeseen, kuten yhteyksiin, yhdyskäytäviin ja työnkulkuihin. Sovellus saa kuitenkin muodostaa yhteyden vain samassa ympäristössä oleviin Common Data Service -tietokantoihin. Ympäristöjen hyödyntämistapa riippuu organisaatiosta ja kehitettävistä sovelluksista. Lisätietoja on kohdassa [Ympäristöjen yleiskatsaus](environments-overview.md).

Tämän aiheen avulla opit luomaan ympäristön ja sille tarkoitetun tietokannan.

## <a name="prerequisites"></a>Edellytykset
 Tämän aiheen noudattamista varten tarvitaan seuraavat kohteet:
 * PowerAppsin palvelupaketin 2 tai Microsoft Flow -palvelupaketin 2 käyttöoikeus. Vaihtoehtoisesti voit rekisteröityä [ilmaisen PowerAppsin palvelupaketin 2 kokeiluversion](https://web.powerapps.com/signup?redirect=marketing&email=) käyttäjäksi.
 * PowerApps-ympäristön järjestelmänvalvojan, Office 365:n yleisen järjestelmänvalvojan tai Azure Active Directory vuokraajan järjestelmänvalvojan oikeudet. Lisätietoja on kohdassa [Ympäristöjen hallinta PowerAppsissa](environments-administration.md).

## <a name="sign-in-to-the-powerapps-admin-center"></a>PowerApps-hallintakeskukseen kirjautuminen
Kirjaudu sisään hallintakeskukseen osoitteessa [https://admin.powerapps.com](https://admin.powerapps.com).

## <a name="create-an-environment-and-database"></a>Ympäristön ja tietokannan luominen
1. Napsauta tai napauta siirtymisruudun kohtaa **Ympäristöt** ja valitse sitten **Uusi ympäristö**.

    ![Tiedosto ja jakaminen](./media/create-environment/new-environment.png)
2. Anna **Uusi ympäristö** -valintaruudussa ympäristön nimi ja valitse sitten avattavista luetteloista alue ja ympäristön tyyppi. Alueen oletuksena Azure Active Directory -vuokraajan kotialue, mutta voit valita avattavasta luettelosta minkä tahansa alueen. Aluetta ei voi muuttaa, kun ympäristö on luotu. Kun olet valmis, valitse **Luo ympäristö**.

    ![Tiedosto ja jakaminen](./media/create-environment/new-environment-dialog.png)
3. Kun ympäristö on luotu, näyttöön tulee vahvistusviestin sisältävä valintaikkuna ja sinua pyydetään luomaan tietokanta. Valitse **Luo tietokanta**, jotta voit jatkossa käyttää Common Data Serviceä.

    **Huomautus:** tällä hetkellä voit luoda tietokannan vain Azure Active Directory -vuokraajan kotialueella.

    ![Tiedosto ja jakaminen](./media/create-environment/create-database-dialog.png)
4. Valitse tietokantaan tallennettavien tietojen valuutta ja kieli. Valuuttaa tai kieltä ei voi muuttaa, kun tietokanta on luotu. Kun olet valmis, valitse **Luo ympäristö**.

    ![Tiedosto ja jakaminen](./media/create-environment/create-database-dialog2.png)

    Common Data Service -tietokannan luominen voi kestää useita minuutteja. Kun tietokanta on luotu, uusi ympäristö näkyy **Ympäristöt**-sivun ympäristöjen luettelossa.

    ![Tiedosto ja jakaminen](./media/create-environment/new-environment-created.png)

    Jos haluat tarkastella ympäristön tietoja, napsauta tai napauta ympäristöä.

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä aiheessa käsiteltiin ympäristön ja sille tarkoitetun tietokannan luomista. Seuraavaksi opit hallinnoimaan ympäristöjä organisaatiossasi.

> [!div class="nextstepaction"]
> [Ympäristöjen hallinta PowerAppsissa](environments-administration.md)

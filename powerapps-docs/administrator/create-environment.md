---
title: Ympäristön luomisen pikaopas | Microsoft Docs
description: Tämän pikaoppaan avulla opit luomaan ympäristön
author: skjerland
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/21/2018
ms.author: sharik
ms.openlocfilehash: 50a3819d4a659d48e1372487c5b50dc8295ee398
ms.sourcegitcommit: f236364ecb06dd86244cd9a607c31e0d716912e2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/22/2018
ms.locfileid: "34445794"
---
# <a name="quickstart-create-an-environment"></a>Pikaopas: ympäristön luominen
Ympäristö on tila, jossa voit tallentaa, hallita ja jakaa organisaatiosi yritystietoja, -sovelluksia ja -työnkulkuja. Lisäksi sitä käytetään säilönä erillisille sovelluksille, joilla voi olla eri rooleja, suojausvaatimuksia tai kohdekäyttäjäryhmiä. PowerApps luo jokaiselle vuokraajalle automaattisesti yhden oletusympäristön, joka jaetaan kaikille käyttäjille kyseisessä vuokraajassa.

Jokaisella ympäristöllä voi olla enintään yksi Common Data Service -tietokanta, joka tarjoaa tallennustilaa sovelluksille. Käyttäjien ympäristössä luoma sovellus voi muodostaa yhteyden mihin tahansa tietolähteeseen, kuten yhteyksiin, yhdyskäytäviin ja työnkulkuihin. Sovellus saa kuitenkin muodostaa yhteyden vain samassa ympäristössä oleviin Common Data Service -tietokantoihin. Ympäristöjen hyödyntämistapa riippuu organisaatiosta ja kehitettävistä sovelluksista. Lisätietoja on kohdassa [Ympäristöjen yleiskatsaus](environments-overview.md).

Tämän pikaoppaan avulla opit luomaan ympäristön ja sille tarkoitetun tietokannan.

## <a name="prerequisites"></a>Edellytykset
 Tämän pikaoppaan noudattamista varten tarvitaan seuraavat kohteet:
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
Nyt tiedät, miten ympäristö ja sille tarkoitettu tietokanta luodaan. Seuraavaksi opit hallinnoimaan ympäristöjä organisaatiossasi.

> [!div class="nextstepaction"]
> [Ympäristöjen hallinta PowerAppsissa](environments-administration.md)

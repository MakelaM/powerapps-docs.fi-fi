---
title: Tietojen menetyksen estämiskäytäntöjen hallinta | Microsoft Docs
description: Vaiheittaiset ohjeet tietojen menetyksen estämiskäytäntöjen hallintaan PowerAppsissa.
author: manasmams
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 158abc3969090e081df41b6b52036d71b6949150
ms.sourcegitcommit: f236364ecb06dd86244cd9a607c31e0d716912e2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/22/2018
ms.locfileid: "34445702"
---
# <a name="manage-data-loss-prevention-dlp-policies"></a>Tietojen menetyksen estämiskäytäntöjen hallinta | Microsoft Docs
Organisaation tiedot ovat sen menestykselle erittäin tärkeitä. Tietojen on oltava päätöksenteossa helposti käytettävissä, mutta riittävän suojatut. Niitä ei saa jakaa asiattomien tahojen käyttöön. Jotta tietoturva voidaan taata, PowerApps antaa mahdollisuuden luoda ja valvoa tietojen menetyksen estämiskäytäntöjä (DLP, Data Loss Prevention). Ne määrittävät, minkä kuluttajaliitinten kanssa tietyt yritystiedot voidaan jakaa. PowerAppsia käyttävä organisaatio ei ehkä esimerkiksi halua, että sen SharePointiin tallennetut yritystiedot julkaistaan automaattisesti organisaation Twitter-syötteessä.

Jotta voit luoda, muokata tai poistaa DLP-käytäntöjä, sinulla on oltava ympäristön järjestelmänvalvojan tai Azure Active Directory -vuokraajan järjestelmänvalvojan oikeudet. Lisätietoja on kohdassa [Ympäristöjen hallinta PowerAppsissa](environments-administration.md).

DLP-käytännön luomisohjeet ovat kohdassa [Pikaopas: luo tietojen menetyksen estämisen (DLP) käytäntö](create-dlp-policy.md).

## <a name="find-a-dlp-policy"></a>DLP-käytännön etsiminen
1. Kirjaudu sisään hallintakeskukseen osoitteessa [https://admin.powerapps.com]([https://admin.powerapps.com).
2. Valitse siirtymisruudussa **Tietokäytännöt**. Jos käytäntöjen luettelo on pitkä, etsi tietyt DLP-käytännöt **hakukentän** avulla.

    ![](./media/prevent-data-loss/data-policies.png)

## <a name="edit-a-dlp-policy"></a>DLP-käytännön muokkaaminen
1. Napsauta tai napauta DLP-käytäntöjen luettelossa kynäkuvaketta, joka on muokattavan käytännön vieressä.

    ![Kirjaudu sisään.](./media/prevent-data-loss/3.png)
2. Tee haluamasi muutokset ja valitse sitten **Tallenna käytäntö**.

    > [!NOTE]
    > Ympäristön DLP-käytännöt eivät voi korvata vuokraajan kaikenkattavia DLP-käytäntöjä.
    >
    >

    Jos haluat tarkastella muutoksia, etsi DLP-käytäntö tietojen menetyksen estämiskäytäntöjen luettelosta ja tarkista sen tiedot napsauttamalla tai napauttamalla sitä.

## <a name="delete-a-dlp-policy"></a>DLP-käytännön poistaminen
1. Napsauta tai napauta DLP-käytäntöjen luettelossa kynäkuvaketta, joka on poistettavan käytännön vieressä.

    ![Kirjaudu sisään.](./media/prevent-data-loss/3-delete.png)
4. Valitse vahvistusvalintaikkunassa **Poista**.

    Käytäntö poistetaan, eikä se enää näy tietojen menetyksen estämiskäytäntöjen luettelossa.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Lue lisätietoja ympäristöistä](environments-administration.md)
* [Lue lisätietoja Microsoft PowerAppsista](../maker/canvas-apps/getting-started.md)

---
title: Asetusjoukon luominen | Microsoft Docs
description: Vaiheittaiset ohjeet asetusjoukon luomiseen.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: b2b472ae33bd16761d25fc965f24afc6bb9b957e
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218414"
---
# <a name="create-an-option-set"></a>Asetusjoukon luominen

Asetusjoukkojen avulla voit liittää kiinteiden arvojen avattavan luettelon sovelluksesi käyttäjään tietojen yhtenäisyyden varmistamiseksi. Näitä kutsutaan joskus valintaluetteloiksi tai vaihtoehtokentiksi muissa sovelluksissa. Kuten entiteettien kyseessä ollessa voit käyttää vakioasetusjoukkoja tai luoda mukautettuja asetusjoukkoja sovelluksessasi käytettäväksi.

Asetusjoukkoja voi luoda kahdella tavalla: joko portaalin asetusjoukkoluettelosta tai suoraan entiteetistä kentän luomisen aikana. Lisätietoja entiteetin luomisesta on kohdassa [Luo entiteetti](data-platform-create-entity.md).

## <a name="creating-an-option-set-while-adding-a-field"></a>Asetusjoukon luominen kenttää lisättäessä.

1. Suurenna [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa.

    ![Entiteetin tiedot](./media/data-platform-cds-create-entity/entitylist.png "entiteettiluettelo")

2. Napsauta tai napauta olemassa olevaa entiteettiä tai [Luo uusi entiteetti](data-platform-create-entity.md)

3. Lisää uusi kenttä entiteettiin napsauttamalla kohtaa **Lisää kenttä**.

4. Anna kentälle uusi kenttä -ruudussa **Näyttönimi**. **Nimi**-kenttä täyttyy automaattisesti, ja sitä käytetään kentän yksilöivänä nimenä. **Näyttönimi** näkyy kentän käyttäjille, ja **Nimi**-kentän nimeä käytetään sovelluksen luomiseen liittyvissä lausekkeissa ja kaavoissa.

    ![Uusi kenttä](./media/data-platform-cds-create-entity/newfieldpanel.png "Uusi kenttäpaneeli")

5. Valitse avattava **tietotyyppi**-valikko ja valitse **asetusjoukko** tai **monivalinta-asetusjoukko**.

6. Valitse avattava **asetusjoukko** -valikko ja valitse **uusi asetusjoukko**

    > [!NOTE]
    > Jos entiteetille voidaan käyttää olemassa olevaa asetusjoukkoa, voit valita sen tästä luettelosta luomatta uutta.

    ![Asetusjoukkoluettelo](./media/data-platform-cds-newoptionset/fieldpanel-1.png "Asetusjoukkoluettelo")

7. Uusi-valikko avautuu asetusjoukon luomista varten. **Näyttönimi** ja **Nimi** määritetään oletusarvoisesti kentän nimen mukaan, mutta niitä voi muuttaa tarvittaessa. Aloita asetusjoukkosi luominen valitsemalla **Lisää uusi kohde**. Toista tätä vaihetta, kunnes kaikki kohteet on luotu.

    ![Uusi asetusjoukko](./media/data-platform-cds-newoptionset/field-optionsetpanel.png "Uusi asetusjoukko")

8. Kun olet lisännyt kohteet, valitse **Tallenna**, jolloin asetusjoukkosi luodaan.

    ![Uusi asetusjoukko](./media/data-platform-cds-newoptionset/field-optionsetpanel-values.png "Uusi asetusjoukko")

9. Sulje kenttäpaneeli napsauttamalla **Valmis**. Tallenna sitten entiteetti Common Data Serviceen napsauttamalla **Tallenna entiteetti**.

    > [!NOTE]
    > Voit valita jonkin kohteista tämän kentän **oletus**kohteeksi. Se on oletusarvoisesti valittuna, kun käyttäjät luovat uusia tietueita entiteettiisi.

    ![Uusi kenttä] ja (./media/data-platform-cds-newoptionset/fieldpanel-2.png "Uusi kenttäpaneeli")

## <a name="creating-an-option-set-from-the-option-set-list"></a>Asetusjoukon luominen asetusjoukkoluettelosta

1. Suurenna [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Asetusjoukot**-kohtaa.

    ![Asetusjoukot](./media/data-platform-cds-newoptionset/optionsetlist.png "Asetusjoukkoluettelo")

2. Napsauta kohtaa **Uusi asetusjoukko**

3. Asetusjoukon luomista varten avautuu uusi paneeli. Kirjoita **Näyttönimi** ja **Nimi**. Aloita asetusjoukkosi luominen valitsemalla **Lisää uusi kohde**. Toista tätä vaihetta, kunnes kaikki kohteet on luotu.

    ![Asetusjoukon luominen](./media/data-platform-cds-newoptionset/optionset-create.png "Asetusjoukon luominen")

4. Kun olet lisännyt kohteet, valitse **Tallenna**, jolloin asetusjoukkosi luodaan.

    ![Uusi asetusjoukko](./media/data-platform-cds-newoptionset/optionset-create-values.png "Uusi asetusjoukko")

5. Voit nyt käyttää tätä asetusjoukkoa luomalla uuden kentän entiteettiin.

## <a name="global-and-local-option-sets"></a>Yleiset ja paikalliset asetusjoukot

Oletusarvoisesti asetusjoukot luodaan yleisinä asetusjoukkoina, mikä mahdollistaa niiden käyttämisen uudelleen useissa entiteeteissä. Kun luot uutta asetusjoukkoa, voit valita kohdassa **Näytä lisää**, tehdäänkö asetusjoukosta **paikallinen**. Tämä asetus on käytettävissä, vain kun asetusjoukkoa luodaan kenttää lisättäessä, mutta ei asetusjoukkoluettelon kautta. Paikallisia asetusjoukkoja voidaan käyttää vain entiteeteissä ja kentissä, joihin ne on luotu. Niitä ei voi käyttää uudelleen muissa entiteeteissä. Tätä tapaa suositellaan vain kokeneille käyttäjille, jotka tarvitsevat jostakin syystä paikallista asetusjoukkoa.

> [!IMPORTANT]
> Kun asetusjoukko on luotu paikallisena tai yleisenä, tätä asetusta ei voi muuttaa.
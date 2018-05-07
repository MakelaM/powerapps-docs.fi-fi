---
title: Pikaopas ensimmäisen mallipohjaisen sovelluksesi luomiseen alusta alkaen PowerAppsin avulla | Microsoft Docs
description: Opi luomaan yksinkertainen mallipohjainen sovellus
services: ''
suite: powerapps
documentationcenter: ''
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.workload: na
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 04/18/2018
ms.author: matp
ms.openlocfilehash: 23521a1512a971e5f298c944fc8219cef5f7fadd
ms.sourcegitcommit: d7ed5144f96d1ecc17084c30ed0e2ba3c6b03c26
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/19/2018
---
# <a name="quickstart-build-your-first-model-driven-app-from-scratch"></a>Pikaopas: Luo ensimmäinen mallipohjainen sovelluksesi alusta alkaen
Mallipohjainen sovelluskehitys on komponenttikeskeinen sovelluskehitystapa. Tässä pikaoppaassa kerrotaan, miten voit helposti luoda mallipohjaisen sovelluksen käyttämällä [!INCLUDE [powerapps](../../includes/powerapps.md)]-ympäristössäsi saatavilla olevia perusentiteettejä. 

> [!IMPORTANT]
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]

## <a name="sign-in-to-powerapps"></a>PowerAppsiin kirjautuminen
Kirjaudu sisään [PowerAppsiin](https://web.powerapps.microsoft.com/). Jos sinulla ei ole vielä [!INCLUDE [powerapps](../../includes/powerapps.md)]-tiliä, napsauta tai napauta **Aloita maksutta** -linkkiä. 

## <a name="create-your-model-driven-app"></a>Mallipohjaisen sovelluksen luominen

1.  Valitse haluamasi ympäristö tai luo uusi siirtymällä [PowerAppsin hallintakeskukseen](https://admin.powerapps.microsoft.com/).
2.  Valitse vasemmassa siirtymisruudussa **Mallipohjainen**. 

    ![Mallipohjainen](media/build-first-model-driven-app/choose-design-mode.png)

3. Valitse vasemmassa ruudussa **Sovellukset** ja sitten **Luo sovellus**.

4.  Anna **Luo uusi sovellus** -sivulla seuraavat tiedot ja valitse sitten **Valmis**: 
  - **Nimi**: kirjoita sovellukselle nimi, kuten *Ensimmäinen sovellukseni*. 
  - **Kuvaus**: kirjoita lyhyt kuvaus siitä, mikä sovellus on tai mitä se tekee, kuten *Tämä on ensimmäinen sovellukseni*.
Katso lisätietoja sovelluksen muista ominaisuuksista kohdasta [Sovelluksen luominen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-app#create-an-app).
 
    ![Uuden-sovelluksen-luominen](media/build-first-model-driven-app/create-new-app.png)

## <a name="add-components-to-your-app"></a>Komponenttien lisääminen sovellukseen
Sovellusten suunnitteluohjelmassa voit lisätä sovellukseesi komponentteja.
1.  Avaa sivustokartan suunnitteluohjelma valitsemalla **Avaa sivustokartan suunnitteluohjelma** -nuoli. 

    ![Uuden-sivustokartan-luominen](media/build-first-model-driven-app/new-sitemap.png)

2.  Valitse sivustokartan suunnitteluohjelmassa **Uusi alialue** ja oikeanpuoleisessa ruudussa **Ominaisuudet**-välilehti ja sen jälkeen seuraavat ominaisuudet.
  - **Tyyppi**: Entiteetti
  - **Entiteetti**: Tili

    ![Komponenttien lisääminen sivustokarttaan](media/build-first-model-driven-app/sitemap.png)

3.  Valitse **Tallenna ja sulje**.
4.  Valitse sovellusten suunnitteluohjelman kaaviossa **Lomakkeet** ja sitten oikeanpuoleisen ruudun **Päälomakkeet**-ryhmässä **Tili**-lomake.

    ![Tili-päälomake](media/build-first-model-driven-app/main-form.png)

5.  Valitse sovellusten suunnitteluohjelman kaaviossa **Näkymät** ja sitten **Aktiiviset tilit**-, **Kaikki tilit**- ja **Omat aktiiviset tilit** -näkymät.

    ![Tili-näkymät](media/build-first-model-driven-app/views.png)

6. Valitse sovellusten suunnitteluohjelman kaaviossa **Kaaviot** ja sitten **Tilit toimialan mukaan** -kaavio.
7. Valitse sovellusten suunnitteluohjelman työkalurivillä **Tallenna**.

    ![Sovellusten suunnitteluohjelman työkalurivi tallenna](media/build-first-model-driven-app/app-designer-toolbar.png)
 
<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## <a name="publish-your-app"></a>Sovelluksen julkaiseminen
Valitse sovelluksen suunnitteluohjelman työkalurivillä **Julkaise**.

Sovelluksen julkaisemisen jälkeen se on valmis käytettäväksi tai jaettavaksi muille.

![Yksinkertainen tilientiteettisovellus](media/build-first-model-driven-app/accounts-quickstart-app.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Tämän pikaoppaan avulla loit yksinkertaisen mallipohjaisen sovelluksen. Jos haluat nähdä, miltä sovelluksesi näyttää käytännössä, katso [Pikaopas: Mallipohjaisen sovelluksen käyttäminen mobiililaitteessa](../../user/run-app-client-model-driven.md).
Jos haluat oppia jakamaan sovelluksesi, siirry opetusohjelmaan [Mallipohjaisen sovelluksen jakaminen](share-model-driven-app.md).

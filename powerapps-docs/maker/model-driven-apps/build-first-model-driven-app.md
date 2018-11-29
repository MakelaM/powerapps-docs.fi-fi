---
title: Ensimmäisen mallipohjaisen sovelluksen luominen alusta PowerAppsin avulla | Microsoft Docs
description: Tietoja yksinkertaisen mallipohjaisen sovelluksen luomisesta
documentationcenter: ''
author: Mattp123
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 10/15/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="build-your-first-model-driven-app-from-scratch"></a>Ensimmäisen mallipohjaisen sovelluksen luominen alusta
Mallipohjaisen sovelluksen suunnittelu on sovelluskehityksen osaan perustuva toimintamalli. Tässä ohjeaiheessa luodaan mallipohjainen sovellus yksinkertaisesti käyttämällä yhtä vakioentiteettiä, joka on käytettävissä PowerApps-ympäristössä.

> [!TIP]
> Lisätietoja mallipohjaisten sovellusten luomisesta on täällä: [Tietoja mallipohjaisen sovelluksen osista](model-driven-app-components.md). 

## <a name="sign-in-to-powerapps"></a>Kirjaudu sisään PowerApps -sovellukseen
Kirjaudu sisään [PowerApps](https://web.powerapps.com/) -sovellukseen. Jos sinulla ei vielä ole [!INCLUDE [powerapps](../../includes/powerapps.md)]-tiliä, valitse **Aloita ilmaiseksi** -linkki. 

## <a name="create-your-model-driven-app"></a>Mallipohjaisen sovelluksen luominen

1.  Valitse haluamasi ympäristö tai siirry [PowerApps-hallintakeskukseen](https://admin.powerapps.com/) ja luo uusi.

  > [!IMPORTANT]
  > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment).   

2. Valitse **aloitussivulla** mallipohjaisen sovelluksen **Aloita tyhjästä** -asetus.
![Start-from-blank_model](media/build-first-model-driven-app/start-from-blank-model-driven.png)

3.  Kirjoita **Luo uusi sovellus** -sivulla seuraavat tiedot ja valitse **Valmis**: 
  - **Nimi**: Anna sovellukselle nimi, kuten *Ensimmäinensovellukseni*. 
  - **Kuvaus**: Kirjoita lyhyt kuvaus siitä, mikä sovellus on ja on tai mitä se tekee, kuten *Tämä on ensimmäinen sovellukseni*.
Lisätietoja sovelluksen lisäominaisuuksista on kohdassa [Sovelluksen luominen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-app#create-an-app).
 
    ![Uuden sovelluksen luominen](media/build-first-model-driven-app/create-new-app.png)

## <a name="add-components-to-your-app"></a>Osien lisääminen sovellukseen
Lisää osia sovellukseen sovellusten suunnitteluohjelmassa.
1.  Valitse **Avaa sivustokartan suunnitteluohjelma** -nuoli, jolloin sivustokartan suunnitteluohjelma avautuu. 

    ![Uuden sivustokartan luominen](media/build-first-model-driven-app/new-sitemap.png)

2.  Valitse sivustokartan suunnitteluohjelmassa **Uusi alialue** ja valitse sitten oikeanpuoleisessa ruudussa **Ominaisuudet**-välilehti. Valitse sitten seuraavat ominaisuudet.
  - **Tyyppi**: Entiteetti
  - **Entiteetti**: Asiakas

    ![Osien lisääminen sivustokarttaan](media/build-first-model-driven-app/sitemap.png)

3.  Valitse **Tallenna ja sulje**.
4.  Valitse sovellusten suunnitteluohjelman kaaviossa **Lomakkeet** ja valitse sitten **Päälomakkeet**-ryhmän oikeanpuoleisessa ruudussa **Asiakas**-lomake.

    ![Asiakkaan päälomake](media/build-first-model-driven-app/main-form.png)

5.  Valitse sovelluksen suunnitteluohjelman kaaviossa **Näkymät** ja valitse sitten **Aktiiviset asiakkaat**-, **Kaikki asiakkaat**- ja **Omat aktiiviset asiakkaat** -näkymät.

    ![Asiakasnäkymät](media/build-first-model-driven-app/views.png)

6. Valitse sovellusten suunnitteluohjelman kaaviossa **Kaaviot** ja valitse sitten **Asiakkaat toimialan mukaan** -kaavio.
7. Valitse sovellusten suunnitteluohjelman työkalurivillä **Tallenna**.

    ![Sovellusten suunnitteluohjelman työkalurivin tallentaminen](media/build-first-model-driven-app/app-designer-toolbar.png)
 
<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## <a name="publish-your-app"></a>Sovelluksen julkaiseminen
Valitse sovellusten suunnitteluohjelman työkalurivillä **Julkaise**.

Kun sovellus on julkaistu, se on valmis suoritettavaksi ja jaettavaksi muiden kanssa.

![Yksinkertainen Asiakas-entiteetin sovellus](media/build-first-model-driven-app/accounts-quickstart-app.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä ohjeaiheessa luodaan yksinkertainen mallipohjainen sovellus. 
- Lisätietoja siitä, miltä sovellus näyttää suorittamisen aikana, on kohdassa [Mallipohjaisen sovelluksen käyttäminen mobiililaitteessa](../../user/run-app-client-model-driven.md).
- Lisätietoja sovelluksen jakamisesta on kohdassa [Mallipohjaisen sovelluksen jakaminen](share-model-driven-app.md).
- Lisätietoja mallipohjaisten sovellusten käytön aloittamisesta ja ominaisuuksista on kohdassa [Tietoja mallipohjaisen sovelluksen osista](model-driven-app-components.md)

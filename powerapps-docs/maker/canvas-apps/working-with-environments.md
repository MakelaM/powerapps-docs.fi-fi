---
title: Ympäristöjen kanssa työskentely | Microsoft Docs
description: Vaihda ympäristöjä ja opi ymmärtämään, miten sivujesi sisältö muuttuu.
documentationcenter: na
author: linhtranms
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/14/2016
ms.author: litran
ms.openlocfilehash: 4bf196041853e9f88c97aabcd3ff1c234b2608be
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/03/2018
---
# <a name="working-with-environments-and-microsoft-powerapps"></a>Ympäristöjen ja Microsoft PowerAppsin kanssa työskentely
PowerAppsin avulla voit työskennellä eri ympäristöissä ja siirtyä helposti niiden välillä. Katso yleiskatsaus ympäristöistä kohdassa [Ympäristöjen yleiskatsaus](../../administrator/environments-overview.md), jossa selitetään yksityiskohtaisesti, miksi ympäristöjä käytetään ja miten voit luoda ja hallita niitä. Tämä artikkeli kattaa seuraavat ympäristöä koskevat ohjeaiheet:

* ympäristön vaihtaminen powerapps.comissa
* miten luodaan sovellus oikeaan ympäristöön
* miten tarkastellaan sovellusta oikeassa ympäristössä

## <a name="switch-the-environment"></a>Ympäristön vaihtaminen
Kun rekisteröidyt ja kirjaudut ensimmäisen kerran powerapps.comiin, päädyt todennäköisesti oletusympäristöön. Voit tarkistaa asian katsomalla sivun oikeaa yläkulmaa.

![Oletusympäristö](./media/working-with-environments/env-dropdown.png)

*Oletusympäristö* on kaikille helppokäyttöinen. Voit aloittaa sovellusten luomisen tässä ympäristössä ja jakaa sovelluksiasi muiden käyttäjien kanssa. Sinulla voi myös olla käyttöoikeus muihin ympäristöihin, kuten niihin, jotka [olet luonut itse](../../administrator/environments-administration.md) tai muiden luomiin ympäristöihin, joihin sinulla on kuitenkin käyttöoikeus. Voit vaihtaa ympäristöjä napsauttamalla oikeassa yläkulmassa olevaa ympäristön avattavaa valikkoa ja valitsemalla eri ympäristön. Tässä esimerkissä näytetään vaihtaminen *oletusympäristöstä* *ympäristöön 1*.

![Ympäristön vaihtaminen](./media/working-with-environments/switch-env.png)

Kun siirryt toiseen ympäristöön (kuten ympäristöön 1), näet kaikki luomasi sovellukset tai sovellukset, joita voit käyttää tässä uudessa ympäristössä.

## <a name="create-apps-in-the-right-environment"></a>Sovelluksen luominen oikeaan ympäristöön
Voit luoda sovelluksia itse luomassasi ympäristössä tai ympäristössä, johon olet saanut käyttöoikeudet. Oman ympäristön luominen edellyttää kuitenkin [tarkkaa suunnitelmaa](../../administrator/pricing-billing-skus.md). Ennen kuin luot sovelluksen, **varmista aina, että olet valinnut ympäristön, jossa haluat sovelluksen olevan**. Muussa tapauksessa joudut siirtämään sovelluksia eri ympäristöjen välillä.

Luo sovellus oikeassa ympäristössä tekemällä jokin seuraavista:

- Jos PowerApps Studio ei ole avoinna, [kirjaudu sisään](http://web.powerapps.com), valitse ympäristö, jossa haluat luoda sovelluksen, valitse **Sovellukset** lähellä vasenta reunaa ja valitse sitten **Luo sovellus**.

- Jos PowerApps Studio on avattu, valitse ympäristö uudelleen oikeassa yläkulmassa.

5. Valitse **Tilin**-sivulla **Vaihda** nykyisen ympäristön nimen vierestä.

6. Valitse ympäristö, johon haluat luoda sovelluksen.

    ![Ympäristön vaihtaminen Studiossa](./media/working-with-environments/studio-env-dropdown2.PNG)

7. Aloita sovelluksen luominen valitsemalla **Uusi**. Sovelluksesi sijaitsee nyt vaiheessa 6 valitussa ympäristössä.

    ![Ympäristön vaihtaminen Studiossa](./media/working-with-environments/new-app.PNG)

## <a name="view-apps-in-the-right-environment"></a>Tarkastele sovellusta oikeassa ympäristössä
Riippumatta siitä, työskenteletkö [powerapps.comissa](http://web.powerapps.com) tai PowerApps Studiossa, luettelo näkemistäsi sovelluksista, yhteyksistä jne. suodatetaan aina avattavasta valikosta valitun ympäristön perusteella. Jos et näe etsimiäsi sovelluksia, varmista aina, että oikea ympäristö on valittuna.

Katso lisätietoja ympäristöistä [tästä yleiskatsauksesta](../../administrator/environments-overview.md).

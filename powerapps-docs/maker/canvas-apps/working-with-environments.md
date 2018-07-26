---
title: Työskentely eri ympäristöissä | Microsoft Docs
description: Vaihda ympäristöjä ja opi ymmärtämään, miten sivujesi sisältö muuttuu.
author: linhtranms
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/14/2016
ms.author: litran
ms.openlocfilehash: 865e5f419d5ff318ce232fff16b9240039129a29
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/22/2018
ms.locfileid: "39194986"
---
# <a name="working-with-environments-and-microsoft-powerapps"></a>Microsoft PowerAppsin käyttäminen eri ympäristöissä
PowerAppsin avulla voit työskennellä eri ympäristöissä ja siirtyä helposti niiden välillä. Lue ympäristöjen yleiskuvaus kohdasta [Ympäristöjen yleiskuvaus](../../administrator/environments-overview.md), jossa selitetään yksityiskohtaisesti, miksi ympäristöjä käytetään ja miten voit luoda ja hallita niitä. Tämä artikkeli kattaa seuraavat ympäristöä koskevat ohjeaiheet:

* ympäristön vaihtaminen powerapps.comissa
* sovelluksen luominen oikeaan ympäristöön
* sovelluksen tarkasteleminen oikeassa ympäristössä

## <a name="switch-the-environment"></a>Ympäristön vaihtaminen
Kun rekisteröidyt ja kirjaudut ensimmäisen kerran powerapps.comiin, päädyt todennäköisesti oletusympäristöön. Voit tarkistaa asian katsomalla sivun oikeaa yläkulmaa.

![Oletusympäristö](./media/working-with-environments/env-dropdown.png)

*Oletusympäristö* on kaikille helppokäyttöinen. Voit aloittaa sovellusten luomisen tässä ympäristössä ja jakaa sovelluksiasi muiden käyttäjien kanssa. Sinulla voi myös olla käyttöoikeus muihin ympäristöihin, kuten niihin, jotka [olet luonut itse](../../administrator/environments-administration.md), tai muiden luomiin ympäristöihin, joihin sinulla on käyttöoikeus. Voit vaihtaa ympäristöjä napsauttamalla oikeassa yläkulmassa olevaa avattavaa ympäristövalikkoa ja valitsemalla toisen ympäristön. Tässä esimerkissä näytetään vaihtaminen *oletusympäristöstä* *ympäristöön 1*.

![Ympäristön vaihtaminen](./media/working-with-environments/switch-env.png)

Kun vaihdat ympäristöä (esimerkiksi ympäristöön 1), huomaat, että kaikki sovellukset, jotka olet luonut tai joihin sinulla on käyttöoikeus, näkyvät myös uudessa ympäristössä.

## <a name="create-apps-in-the-right-environment"></a>Sovelluksen luominen oikeaan ympäristöön
Voit luoda sovelluksia itse luomassasi ympäristössä tai ympäristössä, johon olet saanut käyttöoikeudet. Oman ympäristön luominen edellyttää kuitenkin [tarkkaa suunnitelmaa](../../administrator/pricing-billing-skus.md). Ennen kuin luot sovelluksen, **varmista aina, että olet valinnut ympäristön, jossa haluat sovelluksen olevan**. Muussa tapauksessa joudut siirtämään sovelluksia eri ympäristöjen välillä.

Luo sovellus oikeassa ympäristössä tekemällä jokin seuraavista:

- Jos PowerApps Studio ei ole avoinna, [kirjaudu sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), valitse ympäristö, jossa haluat luoda sovelluksen, valitse **Sovellukset** lähellä vasenta reunaa ja valitse sitten **Luo sovellus**.

- Jos PowerApps Studio on avattu, valitse ympäristö uudelleen oikeassa yläkulmassa.

5. Siirry **Tili**-sivulle ja valitse tällä hetkellä käytössä olevan ympäristön nimen vieressä oleva **Vaihda**-painike.

6. Valitse ympäristö, johon haluat luoda sovelluksen.

    ![Ympäristön vaihtaminen Studiossa](./media/working-with-environments/studio-env-dropdown2.PNG)

7. Aloita sovelluksen luominen valitsemalla **Uusi**. Sovelluksesi sijaitsee nyt siinä ympäristössä, jonka valitsit vaiheessa 6.

    ![Ympäristön vaihtaminen Studiossa](./media/working-with-environments/new-app.PNG)

## <a name="view-apps-in-the-right-environment"></a>Sovelluksen tarkasteleminen oikeassa ympäristössä
Riippumatta siitä, työskenteletkö [powerapps.comissa](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) tai PowerApps Studiossa, luettelo näkemistäsi sovelluksista, yhteyksistä jne. suodatetaan aina avattavasta valikosta valitun ympäristön perusteella. Jos et näe etsimiäsi sovelluksia, varmista aina, että oikea ympäristö on valittuna.

Katso lisätietoja ympäristöistä [tästä yleiskatsauksesta](../../administrator/environments-overview.md).

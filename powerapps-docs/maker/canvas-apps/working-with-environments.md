---
title: Ympäristöjen kanssa työskentely | Microsoft Docs
description: Vaihda ympäristöjä ja opi ymmärtämään, miten sivujesi sisältö muuttuu.
services: ''
suite: powerapps
documentationcenter: na
author: linhtranms
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/14/2016
ms.author: litran
ms.openlocfilehash: 09fdc09e305a0de9cdbc1f7d936db444dbeda321
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="working-with-environments-and-microsoft-powerapps"></a>Ympäristöjen ja Microsoft PowerAppsin kanssa työskentely
PowerAppsin avulla voit työskennellä eri ympäristöissä ja siirtyä helposti niiden välillä. Katso yleiskatsaus ympäristöistä kohdassa [Ympäristöjen yleiskatsaus](../../administrator/environments-overview.md), jossa selitetään yksityiskohtaisesti, miksi ympäristöjä käytetään ja miten voit luoda ja hallita niitä. Tämä artikkeli kattaa seuraavat ympäristöä koskevat ohjeaiheet:

* ympäristön vaihtaminen powerapps.comissa
* miten luodaan sovellus oikeaan ympäristöön
* miten tarkastellaan sovellusta oikeassa ympäristössä

## <a name="switch-the-environment"></a>Ympäristön vaihtaminen
Kun rekisteröidyt ja kirjaudut ensimmäisen kerran powerapps.comiin, päädyt todennäköisesti oletusympäristöön. Voit tarkistaa asian katsomalla sivun oikeaa yläkulmaa.

![Oletusympäristö](./media/working-with-environments/env-dropdown.png)

*Oletusympäristö* on kaikille helppokäyttöinen. Voit aloittaa sovellusten luomisen tässä ympäristössä ja jakaa sovelluksiasi muiden käyttäjien kanssa. Sinulla voi myös olla käyttöoikeus muihin ympäristöihin, kuten niihin, jotka [olet luonut itse](../../administrator/environments-administration.md) tai muiden luomiin ympäristöihin, joihin sinulla on kuitenkin käyttöoikeus. Voit vaihtaa ympäristöjä napsauttamalla oikeassa yläkulmassa olevaa ympäristön avattavaa valikkoa ja valitsemalla eri ympäristön. Tässä esimerkissä vaihdan *oletusympäristöstä* ja *ympäristöön 1*.

![Ympäristön vaihtaminen](./media/working-with-environments/switch-env.png)

Kun siirryt toiseen ympäristöön (kuten ympäristöön 1), näet kaikki luomasi sovellukset tai sovellukset, joita voit käyttää tässä uudessa ympäristössä.

## <a name="create-apps-in-the-right-environment"></a>Sovelluksen luominen oikeaan ympäristöön
Voit luoda sovelluksia olemassa olevissa ympäristöissä, joihin sinulla on käyttöoikeus, tai uudessa ympäristössä. Oman ympäristön luominen edellyttää kuitenkin tarkkaa suunnitelmaa. Lisätietoja on [tässä ohjeaiheessa](../../administrator/pricing-billing-skus.md). Ennen kuin luot sovelluksen, **varmista aina, että olet valinnut ympäristön, jossa haluat sovelluksen olevan**. Muussa tapauksessa joudut siirtämään sovelluksia eri ympäristöjen välillä.

1. Jos olet [powerapps.comissa](http://web.powerapps.com), valitse ympäristö, johon haluat luoda sovelluksesi. Jos olet *PowerApps Studiossa* tai *PowerApps Studio for webissä*, siirry vaiheeseen 4.

2. Valitse **+ Uusi sovellus**.

3. Valitse **Avaa PowerApps Studio** tai **PowerApps Studio for web**.

4. Kun *PowerApps Studio* tai *PowerApps Studio* for web avautuu, valitse ympäristö uudelleen oikeassa yläkulmassa. Parannamme tätä käyttökokemusta tulevaisuudessa, mutta nykyisessä versiossa sinun täytyy valita tämä aina, kun haluat luoda sovelluksen uuteen ympäristöön.

    ![Ympäristön vaihtaminen Studiossa](./media/working-with-environments/studio-switch-env.PNG)

5. Valitse **Tilin**-sivulla **Vaihda** nykyisen ympäristön nimen vierestä.

    ![Ympäristön vaihtaminen Studiossa](./media/working-with-environments/studio-env-dropdown.PNG)

6. Valitse ympäristö, johon haluat luoda sovelluksen.

    ![Ympäristön vaihtaminen Studiossa](./media/working-with-environments/studio-env-dropdown2.PNG)

7. Aloita sovelluksen luominen valitsemalla **Uusi**. Sovelluksesi sijaitsee nyt vaiheessa 6 valitussa ympäristössä.

    ![Ympäristön vaihtaminen Studiossa](./media/working-with-environments/new-app.PNG)

## <a name="view-apps-in-the-right-environment"></a>Tarkastele sovellusta oikeassa ympäristössä
Riippumatta siitä, työskenteletkö [powerapps.comissa](http://web.powerapps.com), PowerApps Studio for Windowsissa tai PowerApps Studio for webissä, luettelo näkemistäsi sovelluksista, yhteyksistä jne. suodatetaan aina avattavasta valikosta valitun ympäristön perusteella. Jos et näe etsimiäsi sovelluksia, varmista aina, että oikea ympäristö on valittuna.

Vielä kerran, ympäristön vaihtaminen [powerapps.comissa](http://web.powerapps.com):

![Ympäristön vaihtaminen](./media/working-with-environments/switch-env.png)

Ympäristön vaihtaminen PowerApps Studio for Windowsissa tai PowerApps Studio for webissä:

![Ympäristön vaihtaminen Studiossa](./media/working-with-environments/studio-switch-env.PNG)

Katso lisätietoja ympäristöistä [tästä yleiskatsauksesta](../../administrator/environments-overview.md).

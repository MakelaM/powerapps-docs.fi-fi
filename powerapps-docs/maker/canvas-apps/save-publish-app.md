---
title: Kangassovelluksen tallentaminen ja julkaiseminen| Microsoft Docs
description: Vaiheittaiset ohjeet kangassovellusten tallentamiseen ja julkaisemiseen sovellusten tekijöille
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 09/14/2017
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 19d793b879d42e9446cc8ad366bc08879162185d
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995771"
---
# <a name="save-and-publish-a-canvas-app-in-powerapps"></a>Kangassovelluksen tallentaminen ja julkaiseminen PowerAppsissa
Kun tallennat kangassovellukseen muutoksia, julkaiset ne automaattisesti itsellesi ja muille, joilla on käyttöoikeus sovelluksen muokkaamiseen. Kun muutokset on tehty, ne pitää julkaista erikseen. Tällöin myös muut käyttäjät, joille sovellus on jaettu, saavat muutokset käyttöönsä.

Saat lisätietoa sovelluksen jakamisesta kohdasta [Jaa sovellus](share-app.md).

## <a name="save-changes-to-an-app"></a>Tallenna muutokset sovellukseen
Valitse **Tallenna** PowerApps Studion **Tiedosto**-valikossa (vasemmassa reunassa) ja suorita jompikumpi seuraavista toimenpiteistä:

* Jos et ole tallentanut sovellusta aiemmin, anna sille nimi ja valitse **Tallenna**.

    ![Tallenna uusi sovellus](./media/save-publish-app/save-as.png)
* Jos sovellus on tallennettu aiemmin, valitse **Tallenna**.  

    ![Tallenna päivitetty sovellus](./media/save-publish-app/save-app.png)

PowerApps voi tallentaa sovelluksen kahden minuutin välein. Jos olet tallentanut sovelluksen kerran, PowerApps jatkaa sovelluksen version tallentamista säännöllisesti. Käyttäjän ei tarvitse painaa tai napauttaa Tallenna-toimintoa. Tekijät voivat ottaa **Automaattinen tallentaminen** -asetuksen käyttöön tai poistaa sen käytöstä **Tiedosto**-valikon **Tili**-välilehdestä.

![Automaattinen tallentaminen -asetus](./media/save-publish-app/autosave.png)

## <a name="publish-an-app"></a>Julkaise sovellus
1. Valitse **Tallenna** PowerApps Studion **Tiedosto**-valikossa (vasemmassa reunassa) ja napsauta tai napauta **Julkaise tämä versio** -painiketta.

    ![Julkaise sovellus](./media/save-publish-app/publish-app.png)
2. Julkaise sovellus kaikille käyttäjille, joille sovellus on jaettu, napauttamalla tai napsauttamalla **Julkaise**-valintaikkunan **Julkaise tämä versio** -painiketta.

   ![Tarkista julkaisu](./media/save-publish-app/publish-review.png)

   > [!NOTE]
   > Aina kun julkaiset kaaviosovelluksen, sovelluksesi päivitetään PowerAppsin viimeisimpään versioon, mikä tarkoittaa, että se hyötyy kaikista uusimmista ominaisuuksista ja suorituskyvyn päivityksistä, jotka olemme lisänneet viime julkaisusi jälkeen. Jos et ole julkaissut päivitystä useaan kuukauteen, näet todennäköisesti välittömän kasvun suorituskyvyssä uudelleenjulkaisun jälkeen.

## <a name="identify-the-live-version"></a>Tunnista reaaliaikainen versio
Siirry osoitteeseen [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja valitse **Tiedosto**-valikosta (vasen reuna) kohta **Sovellukset**. Napsauta tai napauta sitten sovelluksen tietokuvaketta ja valitse **Versiot**-välilehti.

**Reaaliaikainen** versio julkaistaan kaikille, joille sovellus on jaettu. Sovelluksen uusinta versiota voivat käyttää vain ne, joilla on käyttöoikeus sen muokkaamiseen.

![Julkaise portaalista](./media/save-publish-app/publish-portal.png)

Julkaise uusin versio valitsemalla **Julkaise tämä versio** ja napsauta tai napauta **Julkaise**-valintaikkunan **Julkaise tämä versio** -painiketta.

## <a name="next-steps"></a>Seuraavat vaiheet
* Etsi ja suorita sovellus [selaimessa](../../user/run-app-browser.md) tai [puhelimessa](../../user/run-app-client.md).
* [Nimeä sovellus uudelleen](set-name-tile.md) osoitteesta powerapps.com.
* [Palauta sovellus](restore-an-app.md), jos sinulla on useita versioita sovelluksesta.

---
title: Alueiden yleiskatsaus | Microsoft Docs
description: Lue lisätietoja alueista PowerAppsissa
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 7cf52b8f21c5188b799904175f473210fa1b45b4
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/30/2018
ms.locfileid: "39348876"
---
# <a name="regions-overview-in-powerapps"></a>PowerAppsin alueiden yleiskatsaus
## <a name="how-do-i-find-out-where-my-app-is-deployed"></a>Miten saan tietää, missä sovellukseni otetaan käyttöön?
Sovellus otetaan käyttöön ympäristöä isännöivällä alueella. Esimerkiksi, jos ympäristö luodaan Euroopan alueella, sovellus otetaan käyttöön Euroopan palvelinkeskuksissa.

Jos olet järjestelmänvalvoja, voit määrittää jokaisen ympäristön alueen PowerApps-hallintakeskuksessa.

* Siirry [hallintakeskukseen](https://admin.powerapps.com) ja kirjaudu sisään työpaikan tilillä.
  
    Kaikki olemassa olevat ympäristöt luetellaan hallintakeskuksen **Ympäristöt**-välilehdellä. Luettelo osoittaa myös sovelluksen **käyttöönottoalueen**:
  
   ![Ympäristöt-välilehti](./media/regions-overview/environment-list.png)

## <a name="what-regions-are-available"></a>Mitkä alueet ovat käytettävissä?
* Yhdysvallat
* Kanada
* Eurooppa
* Aasia
* Australia
* Intia
* Japani
* Yhdistynyt kuningaskunta

## <a name="what-features-are-specific-to-a-given-region"></a>Mitkä ominaisuudet ovat aluekohtaisia?
Ympäristöjä luodaan eri alueilla, ja ne ovat aina sidoksissa kyseiseen sijaintiin. Tietyssä ympäristössä luotu sovellus otetaan käyttöön kyseisen maantieteellisen alueen palvelinkeskuksissa. Tämä koskee kaikkia kyseisessä ympäristössä luotuja kohteita, kuten Common Data Service -palvelun tietokantoja, sovelluksia, yhteyksiä, yhdyskäytäviä ja mukautettuja liittimiä.

Jos käyttäjät ovat esimerkiksi Euroopassa, kannattaa luoda ympäristö Eurooppa-alueella ja käyttää sitä siellä. Siten takaat parhaan mahdollisen toimivuuden. Jos käyttäjät ovat Yhdysvalloissa, luo ja käytä ympäristöä Yhdysvalloissa.

> [!NOTE]
> Tällä hetkellä voit luoda tietokannan vain sellaisessa tuotanto- tai kokeiluympäristössä, joka on Azure Active Directory- tai Office 365 -vuokraajan kotialueen kanssa samalla alueella. Pyrimme siihen, että tulevaisuudessa tietokantoja voisi luoda myös vuokraajan kotialueen ulkopuolella luoduissa ympäristöissä. Tällä hetkellä et voi myöskään luoda tietokantaa oletusympäristössä tai yksilöllisessä ympäristössä (luotu PowerAppsin yhteisön palvelupaketilla).

> [!NOTE]
> Paikalliset tietoyhdyskäytävät eivät ole käytettävissä Intian alueella tai mukautetuissa ympäristöissä. Yhdyskäytävät on luotava oletusympäristössä.


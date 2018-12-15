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
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: a3ea651fd507bb257a3b778be4421454197733b9
ms.sourcegitcommit: eec10beaee913e01fe488c839661b20bbb1e1cfc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/13/2018
ms.locfileid: "53329271"
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
> Paikalliset tietoyhdyskäytävät eivät ole käytettävissä Intian alueella tai mukautetuissa ympäristöissä. Yhdyskäytävät on luotava oletusympäristössä.


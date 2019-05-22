---
title: Yhdistä Common Data Service-| Microsoft Docs
description: Lue, miten voit muodostaa yhteyden Common Data Service-ja käyttää sitä sovellusten luomiseen powerappsissa.
author: aftowen
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: ''
ms.date: 04/22/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c521fd5961bc9b8d940a374383baca1aeef0cbe4
ms.sourcegitcommit: 93096dfa1aadba77159db1e5922f3d5528eecb7a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/21/2019
ms.locfileid: "65986434"
---
# <a name="connect-to-common-data-service"></a>Yhdistä Common Data Service

Voit turvallisesti tallentaa yrityksen tietoja Common Data Service-ja rakentaa monipuolisia sovelluksia powerappsissa, niin, että käyttäjät voivat hallita tiedot. Tiedot voidaan integroida ratkaisuja, jotka sisältävät Microsoft Flow-, Power BI-ja Dynamics 365-tiedot.

Oletusarvon mukaan Common Data Service-yhdistin muodostaa yhteyden sovelluksen nykyisen environmnent. Jos sovellus siirtyy toiseen ympäristöön, kytkentä muodostaa yhteyden uuteen ympäristöön. Tämä ongelma toimii hyvin yhdessä ympäristössä tai sovelluksen, joka noudattaa ALM isäntäprosessin siirtämisestä kehityksen Test tuotantoon avulla.

Kun lisäät tietolähteen Common Data Service-liittimellä, voit muuttaa ympäristön ja valitse vähintään yksi entiteetti. Oletusarvon mukaan sovellus muodostaa yhteyden tietoihin nykyisessä ympäristössä ja Käyttöliittymän näyttää **(nykyinen)** entiteettien luettelon kautta.

> [!div class="mx-imgBorder"]
> ![Oletusympäristö](media/connection-common-data-service/common-data-service-connection-change-environment.png)

Jos valitset **muuta**, voit määrittää eri ympäristöön tietojen siitä lisäksi nykyisessä ympäristössä tai sen sijaan.

> [!div class="mx-imgBorder"]
> ![Muihin ympäristöihin](media/connection-common-data-service/common-data-service-connection-select-environment.png)

Valitun ympäristön nimi näkyy hakukentän alapuolella.

> [!div class="mx-imgBorder"]
> ![Uusia ympäristöjä](media/connection-common-data-service/common-data-service-connection-after-change-environment.png)

Common Data Service-liitin on tehokkaampi kuin Dynamics 365-liitin ja lähestyy ominaisuus pariteetin.

Lisätietoja: [Mikä on Common Data Service?](../../common-data-service/data-platform-intro.md)

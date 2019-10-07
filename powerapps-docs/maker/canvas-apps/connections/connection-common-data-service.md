---
title: Muodosta yhteys Common Data Service | Microsoft Docs
description: Opi muodostamaan yhteys Common Data Service ja käyttämään sitä sovellusten luomiseen Powerappsissa.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: ''
ms.date: 04/22/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fcadc4d214494380f50f712e453554d41d08eabe
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994012"
---
# <a name="connect-to-common-data-service"></a>Muodosta yhteys Common Data Service

Voit turvallisesti tallentaa yritys tiedot Common Data Service ja luoda monipuolisia sovelluksia Powerappsissa, jotta käyttäjät voivat hallita näitä tietoja. Voit myös integroida nämä tiedot ratkaisuihin, jotka sisältävät Microsoft Flow, Power BI ja tietoja Dynamics 365.

Oletus arvon mukaan Common Data Service-kytkentä muodostaa yhteyden sovelluksesi nykyisessä ympäristössä oleviin tietoihin. Jos sovelluksesi siirtyy toiseen ympäristöön, yhdistin muodostaa yhteyden uuden ympäristön tietoihin. Tämä toiminta sopii hyvin sovellukselle, joka käyttää yhtä ympäristöä tai sovellusta, joka seuraa ALM-prosessia siirtymästä kehityksestä testaukseen tuotantoon.

Kun lisäät tieto lähteen Common Data Service-liittimessä, voit muuttaa ympäristöä ja valita yhden tai useamman entiteetin. Oletus arvon mukaan sovellus muodostaa yhteyden nykyisen ympäristön tietoihin, ja käyttö liittymä osoittaa **(nykyisen)** entiteettiluettelon luettelossa.

> [!div class="mx-imgBorder"]
> ![Oletus ympäristö @ no__t-1

Jos valitset **Muuta**, voit määrittää eri ympäristön, joka noutaa tiedot nykyisestä ympäristöstä tai sen lisäksi.

> [!div class="mx-imgBorder"]
> ![Muut ympäristöt @ no__t-1

Valitun ympäristön nimi näkyy haku ruudun alla.

> [!div class="mx-imgBorder"]
> ![Uudet ympäristöt @ no__t-1

Common Data Service-liitin on vakaampi kuin Dynamics 365-liitin ja lähestyy ominaisuuksien pariteettia.

Lisätietoja: [Mikä on Common Data Service?](../../common-data-service/data-platform-intro.md)

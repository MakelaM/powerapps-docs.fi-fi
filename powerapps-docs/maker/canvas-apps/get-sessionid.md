---
title: Istuntotunnuksen tai pohjaan perustuvan sovelluksen tunnuksen hakeminen | Microsoft Docs
description: Istuntotunnuksen tai pohjaan perustuvan sovelluksen tunnuksen hakeminen PowerAppsissa vianmääritystä varten
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/18/2018
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 11f749f241f978ebd94e460833e98cca894fe7fa
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71990188"
---
# <a name="get-a-session-id-or-a-canvas-app-id"></a>Istuntotunnuksen tai pohjaan perustuvan sovelluksen tunnuksen hakeminen
Jos kohtaat ongelman PowerAppsilla luodussa pohjaan perustuvassa sovelluksessa, voit auttaa Microsoftia ongelman vianmäärityksessä tehokkaammin, jos sinulla on ongelmaan liittyvä istuntotunnus, sovellustunnus tai molemmat.

## <a name="get-the-session-id"></a>Hae istuntotunnus

### <a name="when-editing-an-app"></a>Sovellusta muokatessasi
1. Valitse vasemmasta yläkulmasta **Tiedosto**.

1. Valitse **Tili**.

1. Kohdasta **Diagnostiikka**, valitse **Istunnon tiedot**.

    ![Hae istuntotunnus PowerApps Studiosta](media/get-sessionid/studio.png)

### <a name="when-running-an-app-in-a-browser"></a>Suoritettaessa sovellusta selaimessa
1. Valitse rataskuvake oikeasta yläkulmasta.

1. Valitse **Istunnon tiedot**.

    ![Hae istunnon tunnus selaimesta](media/get-sessionid/browser.png)

### <a name="when-running-an-app-on-a-phone-or-a-tablet"></a>Suoritettaessa sovellusta puhelimella tai tabletilla
1. Pyyhkäise oikealle.

1. Napauta **Istunnon tietoja**.

    ![Hae istunnon tunnus selaimesta](media/get-sessionid/mobile.png)

### <a name="when-running-an-embedded-app-or-form"></a>Suoritettaessa upotettua sovellusta tai lomaketta
1. Suorita jokin seuraavista:

    - Pidä Alt-näppäintä pohjassa ja napsauta sovellusta tai lomaketta hiiren kakkospainikkeella.
    - Napauta sovellusta tai lomaketta kahdella sormella 1 – 2 sekunnin ajan ja sitten vapauta.

1. Valitse **Istunnon tiedot**.

    ![Hae istuntotunnus upotetusta sovelluksesta](media/get-sessionid/embedded.png)

## <a name="get-an-app-id"></a>Hae sovellustunnus
1. [Kirjaudu sisään PowerAppsiin](https://powerapps.microsoft.com).

1. Valitse vasemmasta reunasta **Sovellukset**.

1. Valitse kolme pistettä ( **. . .** ) sovelluksen vianmääritystä varten ja valitse sitten **Tiedot**.

    ![Siirry sovelluksen tietoihin](./media/get-sessionid/details.png)

    Sovellustunnus näkyy kyseisen sovelluksen **Tiedot**-ruudun alareunassa.

    ![Kopioi sovellustunnus tiedoista](./media/get-sessionid/app-id.png)

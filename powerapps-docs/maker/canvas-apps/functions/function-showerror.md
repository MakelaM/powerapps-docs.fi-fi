---
title: ShowError-toiminto | Microsoft Docs
description: ShowError-toiminnon viitetietoja PowerAppsissa mukaan lukien syntaksi ja esimerkkejä
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: gregli
ms.openlocfilehash: 7c1d5a8c7b35d316a2720d564977170029e28359
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/28/2018
---
# <a name="showerror-function-in-powerapps"></a>ShowError-toiminto PowerAppsissa
Näyttää virheen käyttäjälle.

## <a name="description"></a>Kuvaus
**ShowError**-toiminto näyttää virheen käyttäjälle.  Sanomat näkyvät, kun kehität sovellustasi ja kun käyttäjät käyttävät sovellustasi.

**ShowError**-toimintoa voidaan käyttää vain [toimintokaavoissa](../working-with-formulas-in-depth.md).

**ShowError** palauttaa aina arvon *true*.

**ShowError** voidaan yhdistää [**IfError**](function-iferror.md)-toiminnon kanssa havaitsemaan virheitä ja ilmoittamaan niistä mukautetulla virhesanomalla.

## <a name="syntax"></a>Syntaksi
**ShowError**( *Sanoma* )

* *Sanoma* – Pakollinen.  Sanoma, joka näytetään käyttäjälle. 

## <a name="examples"></a>Esimerkkejä

### <a name="step-by-step"></a>Vaihe vaiheelta

1. Lisää **painike**-ohjausobjekti näyttöön.

2. Määritä **painikkeen** **OnSelect**-ominaisuudeksi:

    **ShowError (”Hei maailma”)**

3. Napsauta tai paina painiketta.  

    Aina kun painiketta napsautetaan, käyttäjä näkee sanoman **Hei maailma**.

    ![Kehitysympäristö, jossa painike näkyvillä.OnSelect kutsuu ShowError-toimintoa ja tuo näyttöön tuloksena saatavan Hei maailma -sanoman punaisena ilmoitussanomana käyttäjälle](media/function-showerror/hello-world.png)

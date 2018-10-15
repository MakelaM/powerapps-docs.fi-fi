---
title: Poista mallipohjainen sovellus | MicrosoftDocs
description: Lue, miten voit poistaa mallipohjaisen sovelluksen PowerApps-ympäristöstä.
keywords: ''
ms.date: 05/31/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 9
topic-status: Drafting
ms.openlocfilehash: 9512c0b1c13f408b92c0c18f08946ea9afa1e62b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679888"
---
# <a name="delete-a-model-driven-app"></a>Poista mallipohjainen sovellus

Poistaa sovelluksia, jotka ovat vanhentuneet ympäristössäsi.

1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com/).
2. Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer). 
3. Ratkaisu-ikkunan kohdassa **Osat**, valitse **Sovellukset**.
4. Valitse sovellus, jonka haluat poistaa ja valitse sitten komentopalkista **Poista**.

    ![Sovelluksen poistaminen](media/app-module-solution-window.png "Sovelluksen poistaminen")

5. Valitse esiin tulevasta vahvistussanomasta **Poista**.

   Sovellus poistetaan ympäristöstäsi.
  
Jos osalla on riippuvuussuhteita (kuten suhteita), sinun on poistettava riippuvuudet, ennen kuin voit poistaa sovelluksen. Näet sovelluksen riippuvuudet valitsemalla sovelluksen ja sitten komentopalkista **Näytä riippuvuudet**.

> [!NOTE]
> Kun poistat sovelluksen, suosittelemme, että poistat siihen liittyvän sivustokartan. Jos et poista siihen liittyvää sivustokarttaa, sivustokartan suunnitteluohjelma näyttää virhettä, kun ensimmäisen kerran yrität luoda toista sovellusta, jolla on sama nimi. Voit kuitenkin ohittaa virheen, eikä virhe tule enää näkyviin, kun yrität luoda sovelluksen uudelleen.



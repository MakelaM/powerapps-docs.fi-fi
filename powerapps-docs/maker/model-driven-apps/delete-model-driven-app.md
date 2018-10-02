---
title: Mallipohjaisen sovelluksen poistaminen | MicrosoftDocs
description: Tietoja mallipohjaisen sovelluksen poistamisesta PowerApps-ympäristöstä.
keywords: ''
ms.date: 05/31/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 9
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="delete-a-model-driven-app"></a>Mallipohjaisen sovelluksen poistaminen

Poista ympäristön sovellukset, jotka ovat vanhentuneet.

1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/) -sovellukseen.
2. Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer). 
3. Valitse Ratkaisu-ikkunan **Komponentit**-kohdassa **Sovellukset**.
4. Valitse poistettava sovellus ja valitse sitten komentopalkissa **Poista**.

    ![Poista sovellus](media/app-module-solution-window.png "Poista sovellus")

5. Valitse avautuvassa vahvistussanomassa **Poista**.

   Sovellus poistetaan ympäristöstä.
  
Jos komponentilla on riippuvuuksia, kuten suhteita, ne täytyy poistaa ennen sovelluksen poistamista. Saat sovelluksen riippuvuudet näkyviin valitsemalla sovelluksen ja valitsemalla sitten **Näytä riippuvuudet** komentopalkista.

> [!NOTE]
> Kun poistat sovelluksen, on suositeltavaa poistaa sen liitetty sivustokartta. Jos et poista liittyvää sivustokarttaa, sivustokartan suunnitteluohjelma tuottaa virheen, kun yrität ensimmäisen kerran luoda toisen sovelluksen, jolla on sama nimi. Voit ohittaa virheen, jolloin virhe ei tulee näkyviin, kun yrität luoda sovelluksen uudelleen.



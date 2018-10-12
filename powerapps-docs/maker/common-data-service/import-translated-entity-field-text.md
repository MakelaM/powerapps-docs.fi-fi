---
title: Entiteettien ja kenttien käännettyjen tekstien tuominen PowerAppsissa | MicrosoftDocs
description: Lue ohjeet entiteettien ja kenttien käännettyjen tekstien tuomiseen
ms.custom: ''
ms.date: 06/19/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 3d77d149-819b-45e6-8e70-1fbe54d5c153
caps.latest.revision: 19
ms.author: matp
manager: kvivek
ms.openlocfilehash: e2417f7ad75e327fdfc54d4cd4fdd3f62395326b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681559"
---
# <a name="import-translated-entity-and-field-text-back-into-an-app"></a>Entiteettien ja kenttien käännettyjen tekstien tuominen takaisin sovellukseen

Jos olet mukauttanut entiteettien tai kenttien tekstiä, esimerkiksi kenttien selitteitä tai avattavan valikon arvoja, voit tarjota nämä mukautetut tekstit organisaatiosi käyttäjille, jotka eivät käytä ympäristösi peruskieliversiota, heidän omalla kielellään. Tämä edellyttää, että viet ensin kaikkien mukautustesi tekstimerkkijonot, jotta ne voidaan kääntää organisaatiosi käyttäjien kielille.  
  
 Kun ne on käännetty, sinun täytyy tuoda käännetyt tekstimerkkijonot ympäristöösi, jotta käyttäjät voivat käyttää niitä.  
  
> [!IMPORTANT]
> - Tuotavan tiedoston täytyy olla pakattu tiedosto, joka sisältää juuressaan tiedostot CrmTranslations.xml ja [Content_Types].xml.  
> - Et voi tuoda käännettyjä tekstejä, jotka ovat yli 500 merkkiä pitkiä. Jos käännöstiedostosi sisältää kohteita, jotka ovat yli 500 merkkiä pitkiä, tuontiprosessi epäonnistuu. Jos tuontiprosessi epäonnistuu, tarkista tiedostosta virheen aiheuttanut rivi, pienennä sen merkkimäärää ja yritä sitten tuontia uudelleen. Ota huomioon myös se, että käännettyjen tekstien tuomisen jälkeen sinun täytyy julkaista mukautuksesi uudelleen.  
  
1. Avaa [ratkaisunhallinta](../model-driven-apps/advanced-navigation.md#solution-explorer).  
  
2. Valitse ratkaisunhallinnan Toiminnot-työkaluriviltä **Tuo käännökset**.  
3.  Määritä **Käännetyn tekstin tuominen** -valintaikkunassa tiedosto, joka sisältää käännetyt teksti, ja valitse sitten **Tuo**.  
  
4.  Kun tuonti on valmis, valitse **Sulje**.  
  
> [!NOTE]
>  Mukautusten julkaiseminen voi häiritä järjestelmän normaalia toimintaa. Suosittelemme, että julkaiset sellaisena ajankohtana, jolloin käyttäjille aiheutuu mahdollisimman vähän häiriöitä.  

## <a name="community-tools"></a>Yhteisön työkalut

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) on XrmToolBox-yhteisön kehittämä työkalu Dynamics 365 Customer Engagementille. Easy Translatorilla voit viedä ja tuoda käännöksiä yhdessä kontekstitiedon kanssa. 

> [!NOTE]
> Microsoft ei tue yhteisön kehittämiä työkaluja. Jos sinulla on kysyttävää työkalusta, ota yhteyttä sen julkaisijaan. Lisätiedot: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Seuraavat vaiheet  
 [Mukautettujen entiteettien ja kenttien tekstien vieminen käännettäväksi](export-customized-entity-field-text-translation.md)

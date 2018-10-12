---
title: Ratkaisunhallinnan käyttäminen PowerAppsissa | MicrosoftDocs
description: Opi luomaan ja mukauttamaan sovelluksia ratkaisunhallinnan avulla
ms.custom: ''
ms.date: 06/18/2018
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
ms.assetid: 72bacfbb-96a3-4daa-88ff-11bdaaac9a3d
caps.latest.revision: 57
ms.author: matp
manager: kvivek
ms.openlocfilehash: 6abbe701a6207e68ac367fbe80495a7d04a6e682
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675467"
---
# <a name="use-the-solution-explorer"></a>Ratkaisunhallinnan käyttäminen

 Ratkaisunhallinnassa voit liikkua työkalun vasemmalla puolella olevan siirtymisruudun avulla solmujen hierarkiassa, kuten seuraavassa näyttökuvassa on esitetty:  
  
 ![Oletusratkaisu, jossa entiteetit on kutistettu](media/crm-itpro-cust-defaultsolutionentitiescollapsed.PNG "Oletusratkaisu, jossa entiteetit on kutistettu")  
  
> [!NOTE]
>  Käytä ratkaisunhallinnan mukautustyökaluja hiiren ja näppäimistön avulla. Tämä osa sovellusta ei ole optimoitu kosketuksella käytettäväksi.  
  
 Valitse kukin solmu, niin näet luettelon ratkaisun osista. Komentopalkissa käytettävissä olevat toiminnot muuttuvat valitsemasi solmun mukaan. Niihin vaikuttaa myös se, onko ratkaisu oletusratkaisu vai hallittu ratkaisu. Hallitsemattomissa ratkaisuissa, jotka eivät ole oletusratkaisuja, voit käyttää **Lisää olemassa oleva** -komentoa tuodaksesi ratkaisuun osia, jotka eivät vielä ole ratkaisussa.  
  
Hallittuja ratkaisuja varten käytettävissä ei ole komentoja ja näkyviin tulee viesti:  

> [!NOTE]
> Et voi muokata suoraan hallitun ratkaisun osia. Jos hallitun ratkaisun osien mukautukset on sallittu, voit muokata niitä PowerAppsin suunnittelutyökalulla tai toisesta hallitsemattomasta ratkaisusta.    
  
 Sinun on etsittävä ratkaisun osa oletusratkaisusta ja muokattava sitä siellä, tai voit lisätä sen toiseen hallitsemattomaan ratkaisuun, jonka olet luonut. Ratkaisun osaa ei ehkä voi mukauttaa. Lisätietoja: [Hallitut ominaisuudet](solutions-overview.md#managed-properties)
  
 Moniin mukautuksiin, joita haluat tehdä, liittyy entiteettejä. Voit laajentaa **Entiteetit**-solmun näyttääksesi luettelon järjestelmän kaikista entiteeteistä, joita voidaan mukauttaa jollakin tavalla. Voit laajentaa kunkin entiteetin nähdäksesi entiteettiin kuuluvat ratkaisun osat, kuten seuraavan näyttökuvan Tili-entiteetissä:  
  
 ![Oletusratkaisu, jossa on esillä laajennettu Tili-entiteetti](media/crm-itpro-cust-defaultsolution.PNG "Oletusratkaisu, jossa on esillä laajennettu Tili-entiteetti")  
  
 Lisätietoja ratkaisun osien mukauttamisesta ratkaisunhallinnassa on seuraavissa ohjeaiheissa:  
  
-   Entiteetit, entiteettien väliset suhteet sekä kentän ja viestin mukautukset, katso [Metatiedot](create-edit-metadata.md).  
  
-   Entiteettilomakkeet, katso [Lomakkeet](../model-driven-apps/create-design-forms.md).  
  
-   Prosessit, katso [Prosessit](../model-driven-apps/guide-staff-through-common-tasks-processes.md).  
  
-   Liiketoimintasäännöt, katso [Liiketoimintasäännöt](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md).  

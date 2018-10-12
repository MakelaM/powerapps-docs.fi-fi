---
title: Yleiskatsaus mallipohjaisen sovelluksen luomisesta PowerAppsin avulla | Microsoft Docs
description: Vaiheittaiset ohjeet entiteetin luomiseen ja määrittämiseen PowerApps-sovelluksessa käyttämistä varten.
documentationcenter: na
author: Mattp123
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 08/09/2018
ms.author: matp
ms.openlocfilehash: f6434e6a9248586c05fa0b56b8934d910af3087a
ms.sourcegitcommit: 2a61989be5880fede31510c5dab1593a6f42a741
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/09/2018
ms.locfileid: "39723842"
---
# <a name="what-are-model-driven-apps-in-powerapps"></a>Mitä PowerAppsin malliin perustuvat sovellukset ovat?

Mallipohjainen sovelluskehitys on komponenttikeskeinen sovelluskehitystapa. Mallipohjaisessa sovelluskehityksessä ei tarvitse käyttää koodia, ja luodut sovellukset voivat olla joko yksinkertaisia tai sitten hyvin monimutkaista.  Toisin kuin pohjaan perustuvat sovellukset, joissa suunnittelijalla on täydet oikeudet sovelluksen ulkoasuun, mallipohjaisissa sovelluksissa asettelu, jonka määrittävät pitkälti sovellukseen lisäämäsi osat, on määritetty puolestasi. 

![Mallipohjaisen sovelluksen esimerkki](media/model-driven-app-overview/model-app-sample.png)

Mallipohjaiset sovellukset tarjoavat seuraavat edut:
- monipuoliset, komponenttikeskeiset, koodittomat kehitysympäristöt 
- luo monipuolisia, hyvin reagoivia sovelluksia, joissa on samanlainen käyttöliittymä työpöydältä mobiililaitteisiin
- kehitysominaisuudet vastaavat Dynamics 365:ssä käytettävissä olevaa asiakkaan osallistumisen ympäristöä 
- sovellus voidaan jakaa ratkaisuna.
 
## <a name="the-approach-to-model-driven-app-making"></a>Mallipohjaisten sovellusten tekeminen
Periaatteessa mallipohjaisten sovellusten tekemisessä on kolme keskeistä aluetta.

- yritystietojen mallinnus 
- liiketoimintaprosessien määrittäminen 
- sovelluksen muodostaminen.

### <a name="modeling-business-data"></a>Yritystietojen mallinnus
Yritystietojen mallinnuksessa määrität, mitä tietoja sovelluksesi tarvitsee ja miten nämä tiedot liittyvät muihin tietoihin. Mallipohjaisessa suunnittelussa käytetään metatietopohjaista arkkitehtuuria, jotta suunnittelijat voivat mukauttaa sovelluksen koodia kirjoittamatta. Metatiedot tarkoittavat ”tietoja tiedoista”, ja ne määrittävät järjestelmään tallennettujen tietojen rakenteen. [Opetusohjelma: Luo komponentteja sisältävä mukautettu entiteetti PowerAppsissa](../common-data-service/create-custom-entity.md)

### <a name="defining-business-processes"></a>Liiketoimintaprosessien määrittäminen
Yhdenmukaisten liiketoimintaprosessien määrittäminen ja ottaminen pakotetusti käyttöön on mallipohjaisten sovellusten keskeinen osa. Yhdenmukaiset prosessit auttavat käyttäjiä keskittymään työtehtäviinsä sen sijaan, että he joutuisivat muistelemaan työnkulkuun liittyviä manuaalisia vaiheita. Prosessit voivat olla yksinkertaisia tai monimutkaisia ja muuttua usein ajan myötä. Jos haluat luoda prosessin, valitse PowerApps.comin malliperusteisten alueella ![Asetukset](media/powerapps-gear.png) > **Kehittyneet mukautukset** > **Avaa ratkaisunhallinta**. Valitse sitten ratkaisunhallinnan vasemmanpuoleisesta siirtymisruudusta **Prosessit** ja sitten **Uusi**. Lisätiedot: [Liiketoimintaprosessien yleiskatsaus](/flow/business-process-flows-overview) ja [Liiketoimintalogiikan käyttö Common Data Service for Apps -palvelun avulla](../common-data-service/cds-processes.md). 

### <a name="composing-the-model-driven-app"></a>Mallipohjaisen sovelluksen muodostaminen
Kun tietojen mallinnus ja prosessien määrittäminen on tehty, luo sovelluksesi valitsemalla ja määrittämällä tarvitsemasi osat sovelluksen suunnittelutoiminnolla.

![Sovelluksen suunnittelutoiminto](media/model-driven-app-overview/app-designer.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Ensimmäisen malliin perustuvan sovelluksen luominen](build-first-model-driven-app.md)

[Malliin perustuvan sovelluksen osat](model-driven-app-components.md)


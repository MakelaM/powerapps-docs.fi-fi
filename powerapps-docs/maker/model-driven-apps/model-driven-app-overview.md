---
title: Yleiskatsaus mallipohjaisen sovelluksen luomisesta PowerAppsin avulla | Microsoft Docs
description: PowerApps-sovelluksessa käytettävän entiteetin luomisen ja määrittämisen vaiheittaiset ohjeet.
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="what-are-model-driven-apps-in-powerapps"></a>Mitä PowerAppsin mallipohjaiset sovellukset ovat?

Mallipohjaisen sovelluksen suunnittelu on sovelluskehityksen osaan perustuva toimintamalli. Mallipohjaisen sovelluksen rakenne ei edellytä koodia. Tekemäsi sovellukset voivat olla yksinkertaisia tai erittäin monimutkaisia.  Mallipohjaisten sovellusten asettelun määrittävät suurelta osin sovellukseen lisättävät komponentit toisin kuin kaaviosovellusten kehitystyö, jossa suunnittelija vastaa kokonaan sovelluksen asettelusta. 

![Mallipohjaiset esimerkkisovellus](media/model-driven-app-overview/model-app-sample.png)

Mallipohjaisen sovelluksen rakenne sisältää seuraavat edut:
- Monipuoliset osaan perustuvat suunnitteluympäristöt, joissa ei tarvita koodia 
- Samanlaisen käyttöliittymän eri laitteissa (esimerkiksi pöytätietokoneessa ja mobiililaitteessa) sisältävien monimutkaisten responsiivisten sovellusten luominen
- Samanlainen suunnitteluominaisuus kuin Dynamics 365 Customer Engagement -ympäristössä 
- Sovellus voidaan jakaa ratkaisuna
 
## <a name="the-approach-to-model-driven-app-making"></a>Mallipohjaisen sovelluksen tekemisen toimintamalli
Perustasolla mallipohjaisen sovelluksen tekeminen sisältää kolme tärkeää aluetta.

- Liiketoimintatietojen mallintaminen 
- Liiketoimintaprosessien määrittäminen 
- Sovelluksen luominen

### <a name="modeling-business-data"></a>Liiketoimintatietojen mallintaminen
Jos haluat mallintaa liiketoimintatiedot, määritä, mitä tietoja sovelluksessa tarvitaan ja miten tiedot liittyvät muihin tietoihin. Mallipohjaisessa suunnittelussa käytetään metatietoihin perustuvia arkkitehtuureja, joten suunnittelijat voivat mukauttaa sovellusta kirjoittamatta koodia. Metatieto tarkoittaa tietoja koskevia tietoja ja se määrittää rakenteen, jolla tiedot tallennetaan järjestelmään. [Opetusohjelma: Osia sisältävän mukautetun entiteetin luominen PowerAppsissa](../common-data-service/create-custom-entity.md)

### <a name="defining-business-processes"></a>Liiketoimintaprosessien määrittäminen
Yhdenmukaisten liiketoimintaprosessien määrittäminen ja käyttäminen on tärkeä osa mallipohjaisen sovelluksen suunnittelua. Yhdenmukaisten prosessien avulla varmistat, että sovelluksen käyttäjät keskittyvät töihinsä eivätkä manuaalisten vaiheiden suorittamisen muistamiseen. Prosessit voivat olla yksinkertaisia tai monimutkaisia. Ne myös usein muuttuvat ajan mittaan. Voit luoda prosessin valitsemalla PowerApps.com-sivuston mallipohjaiselta alueelta ![Asetukset](media/powerapps-gear.png) > **Lisämukautukset** > **Avaa ratkaisunhallinta**. Valitse ratkaisunhallinnan vasemmanpuoleisessa siirtymisruudussa **Prosessit** ja valitse sitten **Uusi**. Lisätietoja: [Liiketoimintaprosessin yleiskatsaus](/flow/business-process-flows-overview) ja [Liiketoimintalogiikan käyttäminen Common Data Servicen avulla](../common-data-service/cds-processes.md). 

### <a name="composing-the-model-driven-app"></a>Mallipohjaisen sovelluksen luominen
Kun tiedot on mallinnettu ja prosessit määritetty, voit luoda sovelluksen valitsemalla ja määrittämällä tarvittavat osat sovelluksen suunnitteluohjelmassa.

![Sovellusten suunnitteluohjelma](media/model-driven-app-overview/app-designer.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Ensimmäisen mallipohjaisen sovelluksen luominen](build-first-model-driven-app.md)

[Tietoja mallipohjaisen sovelluksen osista](model-driven-app-components.md)


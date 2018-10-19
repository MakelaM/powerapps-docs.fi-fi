---
title: Käännettyjen entiteetti- ja kenttätekstin tuominen PowerAppsin avulla | MicrosoftDocs
description: Opettele käännetyn entiteetti- ja kenttätekstin tuominen
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="import-translated-entity-and-field-text-back-into-an-app"></a>Käännetyn entiteetti- ja kenttätekstin tuominen takaisin sovellukseen

Jos olet mukauttanut entiteetin tai kentän tekstiä, esimerkiksi kentän otsikkoa tai avattavan luettelon arvoja, haluat ehkä tuoda mukauttamasi tekstit myös niiden organisaatioosi kuuluvien henkilöiden käyttöön, jotka eivät käytä oman ympäristösi asennuskielistä versiota. Voit viedä kaikkien tekemiesi mukautusten tekstit ulos järjestelmästä käännettäväksi organisaatiossa käytetyille kielille.  
  
 Käännöksen jälkeen sinun täytyy tuoda käännetyt tekstimerkkijonot omaan ympäristöösi ennen kuin käyttäjät voivat hyödyntää muutokset.  
  
> [!IMPORTANT]
> - Tuotavan tiedoston on oltava pakattu tiedosto, joka sisältää CrmTranslations.xml- ja [Content_Types].xml-tiedoston juuressa.  
> - Et voi tuoda käännettyä tekstiä, jonka pituus on yli 500 merkkiä. Jos käännöstiedostossa on yli 500 merkin pituisia kohteita, tuonti epäonnistuu. Jos tuonti epäonnistuu, tarkista tiedostosta virheen aiheuttanut rivi, vähennä merkkien määrää ja yritä suorittaa tuonti uudelleen. Huomaa, että kun olet tuonut käännetyn tekstin, julkaise mukautukset uudelleen.  
  
1. Avaa [ratkaisunhallinta](../model-driven-apps/advanced-navigation.md#solution-explorer).  
  
2. Valitse ratkaisunhallinnassa Toiminnot-työkaluriviltä **Tuo käännökset**.  
3.  Määritä **Käännetyn tekstin tuominen** -valintaikkunassa tiedosto, joka sisältää käännetyn tekstin, ja valitse sitten **Tuo**-painiketta.  
  
4.  Kun tuonti on valmis, napsauta **Sulje**.  
  
> [!NOTE]
>  Mukautusten julkaiseminen saattaa häiritä järjestelmän normaalikäyttöä. On suositeltavaa ajoittaa ratkaisun julkaiseminen ajankohtaan, jolloin siitä on vähiten häiriötä käyttäjille.  

## <a name="community-tools"></a>Yhteisön työvälineet

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) on XrmToolbox-yhteisön Dynamics 365 Customer Engagement -sovellusta varten kehittämä työkalu. Easy Translatorin avulla voit viedä ja tuoda käännökset järjestelmään tilannekohtaiset tietojen kanssa 

> [!NOTE]
> Microsoft ei tue yhteisön työkaluja. Jos sinulla on kysymyksiä työkalusta, ota yhteyttä julkaisijaan. Lisätietoja: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Seuraavat vaiheet  
 [Mukautetun entiteetti- ja kenttätekstin vieminen käännettäväksi](export-customized-entity-field-text-translation.md)

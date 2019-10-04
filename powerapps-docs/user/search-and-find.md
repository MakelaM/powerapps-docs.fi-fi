---
title: Haku asetukset ja vaihto ehdot Common Data Service | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/02/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: c7192b98d3f97a4aba57f58c52b02245cb71b155
ms.sourcegitcommit: 7c46e7ce889e2f1c5352ed2e705b0bb8968f2a89
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/04/2019
ms.locfileid: "71950883"
---
# <a name="compare-search-and-find-options-in-common-data-service"></a>Vertaa haku-ja etsintä asetuksia Common Data Service

Common Data Service tietoja voi etsiä neljällä eri tavalla:

-   Osuvuushaku  
  
-   Tekstimuotoinen pikahaku (yksientiteetti tai Multi-entiteetti)  
  
-   Pikahaku (yksientiteetti tai Multi-entiteetti)  

-   Erikoishaku

> [!NOTE]
> Monientiteetin pikahakua kutsutaan myös luokiteltuna Hakueksi. 
  
Seuraavassa taulukossa on lyhyt vertailu neljästä käytettävissä olevasta vaihto ehdosta.

|Toimintoja|[Osuvuus haku](search-records.md#relevance-search)|[Tekstimuotoinen pikahaku](search-records.md#start-a-search)|[Pikahaku](search-records.md#start-a-search)|[Erikoishaku](create-edit-or-save-advanced-find-search.md)|  
|-------------------|----------------------|---------------------------|----------------|-------------------|  
|Oletus arvon mukaan käytössä?|Ei. Järjestelmänvalvojan on otettava se käyttöön manuaalisesti.|Ei. Järjestelmänvalvojan on otettava se käyttöön manuaalisesti.|Kyllä|Kyllä|  
|Yhden entiteetin haku alue|Ei käytettävissä entiteettiruudukossa. Voit suodattaa haku tulokset tulos sivun entiteetin mukaan.|Käytettävissä entiteettiruudukossa.|Käytettävissä entiteettiruudukossa.|Käytettävissä entiteettiruudukossa.|  
|Usean entiteetin haku alue|Haussa käytettävien entiteettien enimmäismäärä ei ole rajoitettu. **Huomautus:**  Kun käytettävissä olevien entiteettien enimmäismäärä ei ole rajoitettu, tietue tyyppi suodatin tuo näkyviin vain kymmenen entiteetin tiedot.|Hakee enintään 10 entiteettiä, jotka on ryhmitelty entiteetin mukaan.|Hakee enintään 10 entiteettiä, jotka on ryhmitelty entiteetin mukaan.|Usean entiteetin haku ei ole käytettävissä.|  
|Haku käyttäytyminen|Etsii vastineita mistä tahansa haku termin sanasta entiteetin missä tahansa kentässä.|Etsii haku termin kaikkien sanojen vastaavuudet entiteetin yhdestä kentästä. sanat voidaan kuitenkin täsmätä missä tahansa-kentän järjestyksessä.|Etsii vastaavu uksia SQL-kyselystä, jossa on like-lausekkeita. Sinun on käytettävä haku termin yleismerkkiä, jotta voit hakea merkki jonosta. Kaikkien vastaavu uksien on oltava täsmähakutermin vastaavuus.|Kyselyn muodostin, jossa voit määrittää valitulle tietue tyypille haku ehdot. Voidaan myös käyttää tietojen valmistelemiseen Office Exceliin viemistä varten, jotta voit analysoida, tiivistää tai koostaa tietoja tai luoda pivot-taulu koita, joiden avulla voit tarkastella tietojasi eri näkö kulmista.|  
|Haettavat kentät|Teksti kentät, kuten yksi teksti rivi, useita teksti rivejä, hakuja ja asetus joukkoja. Ei tue etsimistä kentissä, joiden tieto tyyppi on numeric tai Date.|Kaikki haettavat kentät.|Kaikki haettavat kentät.|Kaikki haettavat kentät.|  
|Haku tulokset|Palauttaa haku tulokset tärkeys järjestykseen yksittäisessä listassa.|Jos kyseessä on yksittäinen entiteetti, palauttaa haku tulokset entiteettiruudukossa. Jos kyseessä on Multi-entiteetti, palauttaa haku tulokset luokkien mukaan ryhmiteltyinä, kuten asiakkuudet, yhteys henkilöt tai liidit.|Jos kyseessä on yksittäinen entiteetti, palauttaa haku tulokset entiteettiruudukossa. Jos kyseessä on Multi-entiteetti, palauttaa haku tulokset luokkien mukaan ryhmiteltyinä, kuten asiakkuudet, yhteys henkilöt tai liidit.|Palauttaa valitun tietue tyypin haku tulokset määrittämiesi sarakkeiden mukaan määritetyssä lajittelu järjestyksessä.|
|Yleismerkit (*)|Tekstin lopussa oleva yleismerkki on tuettu.|Johtavaa yleismerkkiä tuetaan. Oletus arvon mukaan lisätty lopussa oleva yleismerkki.|Johtavaa yleismerkkiä tuetaan. Oletus arvon mukaan lisätty lopussa oleva yleismerkki.|Ei tueta.|  

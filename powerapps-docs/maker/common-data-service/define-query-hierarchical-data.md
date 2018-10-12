---
title: Määritä hierarkkisia tietoja ja tee niistä kyselyjä Common Data Service for Appsin avulla | MicrosoftDocs
description: Ota selvää, miten voit määrittää hierarkkisia tietoja ja tehdä niistä kyselyjä.
ms.custom: ''
ms.date: 06/02/2018
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
ms.assetid: 0cf62817-5ff5-40bb-ad17-e1f6b0921720
caps.latest.revision: 42
ms.author: matp
manager: kvivek
ms.openlocfilehash: 4dad7da635156350d104d68108ac4acfbb991862
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674539"
---
# <a name="define-and-query-hierarchically-related-data"></a>Hierarkkisten tietojen määrittäminen ja kyselyjen tekeminen

Voit saada arvokasta merkityksellistä liiketoimintatietoa määrittämällä hierarkkisesti rakentuvia tietoja ja tekemällä niistä kyselyjä. Hierarkkisen mallintamisen ja visualisoinnin ominaisuuksista on useita hyötyjä:  
  
- Voit tarkastella ja tutkia monimutkaisia hierarkkisia tietoja.  
- Voit tarkastella suorituskykyilmaisimia (KPI) hierarkian kontekstuaalisessa näkymässä.  
- Voit analysoida tärkeitä tietoja visuaalisesti verkossa ja tabletilla.  
  
Joihinkin vakioentiteetteihin on määritetty hierarkioita valmiiksi. Hierarkioita voi ottaa käyttöön myös muissa kohteissa, kuten mukautetuissa entiteeteissä, ja luoda niistä visualisointeja. 

## <a name="define-hierarchical-data"></a>Hierarkkisten tietojen määrittäminen

Common Data Service for Appsissa hierarkkisia tietorakenteita tuetaan *itseensä viittaavilla* yksi moneen (1:N) -suhteilla niihin liittyvissä tietueissa. 

> [!NOTE]
> *Itseensä viittaava* tarkoittaa, että entiteetti liittyy itseensä. Esimerkiksi tilientiteetissä on hakukenttä, jolla se liittyy tietueen toiseen tilientiteettiin.

Kun itseensä viittaava yksi moneen (1:N) -suhde on olemassa, suhteen määrityksessä **Hierarkkinen**-asetus on asetettavissa arvoksi **Kyllä**.

![Hierarkkinen-asetus suhteen määrityksessä](media/self-referential-relationship-car-solution-explorer.png)

Jotta voit tehdä tiedoista kyselyjä hierarkiana, yksi entiteetin itseensä viittaavista yksi moneen (1:N) -suhteista on asetettava hierarkkiseksi. Sen voi tehdä vain Ratkaisunhallinnassa.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Hierarkian ottaminen käyttöön:  
  
1. Kun [tarkastelet 1:N-suhteita](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships), valitse muokattava itsensä viittaava suhde.
2. Aseta **Suhteen määritys** -kohdassa **Hierarkkinen**-asetuksen arvoksi **Kyllä**.  
  
> [!NOTE]
> - Tiettyjä valmiita 1:N-suhteita ei voi mukauttaa. Näitä suhteita ei voi asettaa hierarkkisiksi.  
> - Voit määrittää hierarkkiseksi järjestelmän itseensä viittaavia suhteita. Tähän sisältyvät järjestelmätyyppiset itseensä viittaavat 1:N-suhteet, kuten contact_master_contact-suhde.  

> [!IMPORTANT]
> Itseensä viittaavia suhteita voi olla useita, mutta hierarkkiseksi suhteeksi voi määrittää vain yhden suhteen per entiteetti. Jos yrität muuttaa kertaalleen käyttöön otettua asetusta, näet varoituksen:
>
> - **Käytöstä poistettaessa:** Jos poistat hierarkia-asetuksen käytöstä tässä suhteessa, tätä hierarkiaa käyttävät koosteen määritykset, prosessit ja näkymät eivät toimi. Haluatko jatkaa? 
> - **Käyttöön otettaessa:** Jos otat hierarkia-asetuksen käyttöön tässä suhteessa, kaikki olemassa olevaa hierarkiaa käyttävät koosteen määritykset muuttuvat virheellisiksi. Haluatko jatkaa?
>
> Jos et ole varma, onko nykyisessä hierarkiassa muita riippuvuuksia, tarkista asia käyttöönottodokumentaatiosta tai kysy asiasta muilta mukauttajilta, jotta olet hyvin perillä nykyisen hierarkkisen suhteen käyttämisestä ennen jatkamista.

<a name="BKMK_Querydata"></a> 
  
## <a name="query-hierarchical-data"></a>Kyselyjen tekeminen hierarkkisista tiedoista  

Ilman määritettyä hierarkiaa hierarkkisten tietojen noutaminen edellyttää liittyvien tietueiden iteratiivista kyselyä. Kun hierarkia on määritetty, voit kysellä liittyviä tietoja hierarkiana vain yhdellä vaiheella. Voit tehdä kyselyjä tietueisiin käyttämällä **Alle**- ja **Ei alle** -logiikkaa. Hierarkkiset **Alle-** ja **Ei alle** -operaattorit näkyvät erikoishaussa ja työnkulkueditorissa. Lisätietoja näiden operaattoreiden käyttämisestä on ohjeaiheessa [Työnkulun vaiheiden määrittäminen](/flow/configure-workflow-steps#setting-conditions-for-workflow-actions). Lisätietoja erikoishausta on ohjeaiheessa [Erikoishaun luominen, editoiminen tai tallentaminen](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search).  

> [!NOTE]
> Kehittäjät voivat käyttää näitä operaattoreita myös koodissa. Lisätietoja: [Kehittäjädokumentaatio: Kyselyjen tekeminen hierarkkisista tiedoista](/dynamics365/customer-engagement/developer/org-service/query-hierarchical-data)
  
Seuraavissa esimerkeissä kuvataan hierarkkisten kyselyjen skenaarioita:  
  
### <a name="query-account-hierarchy"></a>Kysely tilihierarkiasta  
  
![Kysely tilihierarkian tileistä](media/query-accounts.png)  
  
### <a name="query-account-hierarchy-including-related-activities"></a>Kysely tilihierarkiasta liittyvät toiminnot mukaan lukien  
  
![Kysely tiliin liittyvistä toiminnoista](media/query-account-related-activities.png)  
  
###  <a name="query-account-hierarchy-including-related-opportunities"></a>Kysely tilihierarkiasta liittyvät mahdollisuudet mukaan lukien  
  
![Kysely tiliin liittyvistä mahdollisuuksista](media/query-account-related-opportunities.png)  
  
## <a name="see-also"></a>Katso myös 
[1:N (yksi moneen)- tai N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen](create-edit-1n-relationships.md)<br />
[1:N (yksi moneen)- tai N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen Ratkaisunhallinnalla](create-edit-1n-relationships-solution-explorer.md)<br />
[Hierarkkisten tietojen visualisointi mallipohjaisilla sovelluksilla](visualize-hierarchical-data.md)<br />
[Video: Hierarkkinen suojausmallintaminen](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)<br />
[Video: Hierarkian visualisointi](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)

---
title: Hierarkkisten tietojen määrittäminen ja kysely Common Data Servicen avulla | MicrosoftDocs
description: Tietoja hierarkkisesti järjestettyjen tietojen määrittämisestä ja kyselystä
ms.custom: ''
ms.date: 06/02/2018
ms.reviewer: ''
ms.service: powerapps
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-and-query-hierarchically-related-data"></a>Hierarkkisesti järjestettyjen tietojen määrittäminen ja kysely

Voit saada liiketoimintaan liittyviä arvokkaita tietoja määrittämällä toisiinsa liittyviä tietoja hierarkkisesti ja tekemällä niistä kyselyjä. Hierarkkisista mallinnus- ja visualisoimistoiminnoista on paljon hyötyä.  
  
- Voit tarkastella ja selailla monitasoisia hierarkkisia tietoja.  
- Voit tarkastella tunnuslukuja hierarkian tilannekohtaisessa näkymässä.  
- Voit analysoida verkossa ja taulutietokoneilla olevia tärkeimpiä tietoja.  
  
Joillekin vakioentiteeteille on jo määritetty hierarkiat. Muissa entiteeteissä, kuten mukautetuissa entiteeteissä, voidaan ottaa hierarkia käyttöön ja niille voidaan luoda visualisoinnit. 

## <a name="define-hierarchical-data"></a>Hierarkkisten tietojen määrittäminen

Common Data Service tukee hierarkkisten tietorakenteiden liittyvien tietueiden *itseen viittaavia* yksi moneen (1:N) -suhteita. 

> [!NOTE]
> *Itseen viittaava* tarkoittaa sitä, että entiteetti liittyy siihen itseensä. Esimerkiksi asiakasentiteetillä on hakukenttä, joka liittää sen toiseen asiakasentiteettitietueeseen.

Kun itseen viittaava yksi moneen (1:N) suhde on olemassa, suhteen määrityksen **Hierarkkinen**-asetuksen arvoksi voi määrittää **Kyllä**.

![Suhteen määrityksen Hierarkkinen-asetus](media/self-referential-relationship-car-solution-explorer.png)

Jos haluat tehdä kyselyn tiedoista hierarkiana, sinun on määritettävä jokin entiteetin itseen viittaava 1:N (yksi-moneen) -suhde käyttöön hierarkkisena. Tämä voidaan tehdä vain ratkaisunhallinnan avulla.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Voit ottaa hierarkian käyttöön seuraavasti:  
  
1. Valitse [1:N-suhteiden tarkastelemisen](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships) yhteydessä muokattava itseen viittaava suhde.
2. Valitse **suhdemääritys**, aseta **Hierarkkinen** valinnaksi **Kyllä**.  
  
> [!NOTE]
> - Joitakin valmiita 1:N-suhteita ei voi mukauttaa. Tämä estää valitsemasta näitä suhteita hierarkkisiksi suhteiksi.  
> - Voit määrittää hierarkkisen suhteen järjestelmän itseen viittaaville suhteille. Tämä sisältää järjestelmätyypin 1:N:n itseen viittaavat suhteet, kuten "contact_master_contact"-suhteen.  

> [!IMPORTANT]
> Itseen viittaavia suhteita voi olla useita, mutta vain yksi entiteetin suhde voidaan määrittää hierakkiseksi suhteeksi. Jos yrität muuttaa asetusta sen jälkeen, kun se on otettu käyttöön, näyttöön tulee seuraava varoitus:
>
> - **Käytöstäpoiston yhteydessä:** Jos poistat hierarkia-asetuksen käytöstä tässä suhteessa, tätä hierarkiaa käyttävät koosteen määritykset, prosessit ja näkymät eivät toimit. Haluatko jatkaa? 
> - **Käyttöönoton yhteydessä:** Jos otat hierarkia-asetuksen käyttöön tässä suhteessa, kaikki olemassa olevaa hierarkiaa käyttävät koosteen määritykset muuttuvat virheellisiksi. Haluatko jatkaa?
>
> Joe et ole aivan varma siitä, että olemassa olevalla hierarkialla ei ole muita riippuvuuksia, tarkista kaikki käyttöönottoa koskevat dokumentaatiot tai anna muille mukauttajille tietoja siitä, miten olemassa olevia hierarkkisia suhteita käytetään, ennen kuin jatkat.

<a name="BKMK_Querydata"></a> 
  
## <a name="query-hierarchical-data"></a>Kyselyn tekeminen hierarkkisista tiedoista  

Jos hierarkiaa ei ole määritetty ja haluat hakea hierarkkisia tietoja, liittyvistä tietueista on tehtävä toistuvia kyselyjä. Kun hierarkia on määritetty, liittyvistä tiedoista voi tehdä kyselyn hierarkiana yhdessä vaiheessa. Entiteetin tietueista voi tehdä kyselyn käyttämällä **alle**- ja **ei alle** -logiikkaa. Hierarkkisia **alle**- ja **ei alle** -operaattoreita ovat käytettävissä Erikoishaku-toiminnossa ja työnkulkueditorissa. Katso lisätietoja siitä, miten näitä operaattoreita käytetään kohdassa [työnkulun osavaiheiden määritys](/flow/configure-workflow-steps#setting-conditions-for-workflow-actions). Lisätietoja erikoishausta on artikkelissa [Erikoishaun luominen, muokkaaminen tai tallentaminen](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search).  

> [!NOTE]
> Sovelluskehittäjät voivat voi käyttää näitä operaattoreita myös koodissa. Lisätietoja [Sovelluskehittäjän dokumentaatio: Kyselyn tekeminen hierarkkisista tiedoista](/dynamics365/customer-engagement/developer/org-service/query-hierarchical-data)
  
Seuraavassa esimerkissä kuvataan skenaariot, joiden avulla hierarkioista voi tehdä kyselyn.  
  
### <a name="query-account-hierarchy"></a>Kyselyn tekeminen asiakashierarkiasta  
  
![Tilihierarkien tilikysely](media/query-accounts.png)  
  
### <a name="query-account-hierarchy-including-related-activities"></a>Kyselyn tekeminen asiakashierarkiasta ja liittyvistä aktiviteeteista  
  
![Asiakkaaseen liittyvien aktiviteettien kysely](media/query-account-related-activities.png)  
  
###  <a name="query-account-hierarchy-including-related-opportunities"></a>Kyselyn tekeminen asiakashierarkiasta ja liittyvistä mahdollisuuksista  
  
![Asiakkaaseen liittyvien mahdollisuuksien kysely](media/query-account-related-opportunities.png)  
  
## <a name="see-also"></a>Katso myös 
[1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteen luominen ja muokkaaminen](create-edit-1n-relationships.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-1n-relationships-solution-explorer.md)<br />
[Mallipohjaisten sovellusten hierarkiatietojen visualisoiminen](visualize-hierarchical-data.md)<br />
[Video: Hierarkkisen suojauksen mallinnus](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)<br />
[Video: Hierarkian visualisointi](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)

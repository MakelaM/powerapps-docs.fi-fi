---
title: Yhteenveto monta moneen -entiteettisuhteiden luomisesta Common Data Service sovelluksille -ratkaisussa | MicrosoftDocs
description: Tietoja monta moneen -suhteiden luomisesta
ms.custom: ''
ms.date: 05/29/2018
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
ms.assetid: 248cecfd-c9e8-430b-b4b0-860669866084
caps.latest.revision: 33
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-many-to-many-entity-relationships-overview"></a>Monta-moneen-entiteetin suhteiden yleiskatsaus

Yksi moneen (1:N) -entiteettisuhteet luovat tietueiden välisen hierarkian. Monta moneen (N:N) -suhteilla ei ole eksplisiittistä hierarkiaa. Valintakenttiä tai toimintamalleja ei tarvitse määrittää. Monta moneen -suhteiden avulla luodut tietueet ovat samanarvoisia ja suhde on kaksisuuntainen.  
  
Monta moneen -suhteiden avulla suhteet (tai intersect-entiteetti) tallentaa tiedot, jotka liittävät entiteetit. Tällä entiteetillä on yksi moneen -entiteettisuhde molempiin liittyviin entiteetteihin. Se tallentaa vain vaadittavat tunnisteet, jotka määrittävät suhteen. Suhteen entiteettiin ei voi lisätä mukautettuja kenttiä eikä se koskaan ole näkyvissä käyttöliittymässä. 
  
Monta moneen -suhteen luominen edellyttää kahden suhteeseen osallistuvan entiteetin valintaa. Mallipohjaisissa sovelluksissa voi päättää, miten vastaavat luettelot ovat käytettävissä kunkin entiteetin siirtymisessä. Nämä ovat samoja asetuksia, joita käytetään 1:N-suhteen ensisijaiselle entiteetille. Lisätietoja: [Ensisijaisen entiteetin siirtymisruudun kohde](create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)
  
Kaikki entiteetit eivät ole sopivia monta moneen--suhteisiin. Jos entiteettiä ei voi valita suunnitteluohjelmassa, et voi luoda entiteetille monta moneen -suhdetta. Lisätietoja: [Sovelluskehittäjän dokumentaatio: Entiteettisuhteen kelpoisuus](https://docs.microsoft.com/dynamics365/customer-engagement/developer/entity-relationship-eligibility)

1:N (yksi moneen)- tai N:1 (monta yhteen) -suhteita voi luoda ja muokata kahden seuraavan suunnitteluohjelman avulla:

|Suunnittelija| Kuvaus|
|--|--|
|[PowerApps-portaali](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Tarjoaa helpon ja nopean käyttökokemuksen, mutta jotkin erityisasetukset eivät ole käytettävissä.<br />Lisätietoja: [Monta moneen -entiteettisuhteiden luominen Common Data Service sovelluksille -ratkaisussa PowerApps-portaalin avulla](create-edit-nn-relationships-portal.md)|
|Ratkaisunhallinta|Tämä ei ole niin helppo tapa, mutta tarjoaa enemmän joustavuutta vähemmän yleisille vaatimuksille.<br />Lisätietoja: [N:N (monta moneen) -entiteettisuhteiden luominen Common Data Service sovelluksille -ratkaisussa ratkaisunhallinnan avulla](create-edit-nn-relationships-solution-explorer.md) |

> [!NOTE]
> Voit luoda myös uuden monta moneen (N:N) -entiteettisuhteen ympäristössä seuraavasti:
> - Tuo ratkaisu, joka sisältää suhteiden määrityksen. Lisätietoja: [Ratkaisujen tuominen. päivittäminen ja vieminen](import-update-export-solutions.md)
> - Sovelluskehittäjä voi käyttää [metatietopalveluita](../../developer/common-data-service/metadata-services.md) ohjelman kirjoittamisessa entiteettisuhteiden luomista ja päivittämistä varten. Lisätietoja: [Sovelluskehittäjän dokumentaatio: Entiteettisuhteen metatietojen mukauttaminen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)

Tämän ohjeaiheen tietojen avulla voit valita käytettävän suunnitteluohjelman. 

Käytä PowerApps-portaalia monta moneen (N:N) -entiteettisuhteiden luomiseen ja muokkaamiseen, jos seuraavia vaatimuksia ei tarvitse ottaa huomioon:

- Siirtymisruudun asetusten määrittäminen mallipohjaisille sovelluksille.
- Piilota suhde erikoishaulta mallipohjaisissa sovelluksissa.

## <a name="see-also"></a>Katso myös

[Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)<br />
[Monta moneen -entiteettisuhteiden luominen Common Data Service sovelluksille -ratkaisussa PowerApps-portaalin avulla](create-edit-nn-relationships-portal.md)<br />
[N:N (monta moneen) -entiteettisuhteiden luominen Common Data Service sovelluksille -ratkaisussa ratkaisunhallinnan avulla](create-edit-nn-relationships-solution-explorer.md)<br />
[Sovelluskehittäjän dokumentaatio: Entiteettisuhteen metatietojen mukauttaminen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)<br />
[Sovelluskehittäjän dokumentaatio: Entiteettisuhteen kelpoisuus](https://docs.microsoft.com/dynamics365/customer-engagement/developer/entity-relationship-eligibility)

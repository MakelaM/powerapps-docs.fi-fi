---
title: Common Data Service for Appsin entiteetit | Microsoft Docs
description: Tutustu Common Data Service for Appsissa käytettävissä oleviin entiteetteihin.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: f40c05c3bdab521cb1230be15cefc5dbb58eac18
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42844222"
---
# <a name="common-data-service-for-apps-entities"></a>Common Data Service for Apps -entiteetit

Tallennustilan tarjoaminen tiedoille on Common Data Service for Appsin tärkein toiminto. Common Data Service sisältää perusjoukon entiteettejä, jotka antavat rakenteen yrityssovellusten käyttämille tiedoille. 

Voit tarkastella entiteettien perusjoukkoa [Common Data Service for Apps -entiteettiviitteessä](reference/about-entity-reference.md).

## <a name="modify-entities"></a>Entiteettien muokkaaminen

Voit muokata entiteettien metatietoja useilla eri tavoilla.

### <a name="use-designers"></a>Suunnittelutyökalujen käyttäminen

Entiteettien metatietoja voidaan muokata monella eri tavalla suunnittelutyökalujen avulla.


|Suunnittelutyökalu  |Kuvaus  |
|---------|---------|
|powerapps.com|Helpoin ja yleisin tapa muokata rakennetta on tiettyyn ympäristöön liittyvän Common Data Service -palvelun muokkaaminen [powerapps.com](https://web.powerapps.com/)-sivuston avulla. Siellä käyttöön otettavat muutokset tehdään hallitsemattoman Common Data Service -oletusratkaisun kontekstissa. <!-- TODO: Add link to topic that describes this -->|
|Common Data Service -oletusratkaisun hallinta|[powerapps.com](https://web.powerapps.com/)-sivustossa on käytettävissä myös toinen suunnittelutyökalu Common Data Service -palvelun muokkaamiseen. Näytön vasemmassa alakulmassa olevalla **Lisäasetukset**-painikkeella avataan Common Data Service -oletusratkaisun ratkaisunhallinta. |
|Oman ratkaisun ratkaisunhallinta |Jos aiot jakaa ratkaisusi, sinun tulee luoda mahdolliset uudet entiteetit, määritteet tai suhteet sen hallitsemattoman ratkaisun kontekstissa, jota käytät oman ratkaisusi kehittämiseen. <br /> Lisätietoja: [Ratkaisun julkaisijan ja ratkaisun luominen](introduction-solutions.md#create-a-solution-publisher-and-solution)|
|Lomake-editorista|Jos muokkaat malliin perustuvan sovelluksen lomaketta entiteettiä varten, voit napsauttaa **Uusi kenttä** -painiketta **Kenttien hallinta** -ruudussa. Jos luot hakukentän, luot myös sitä tukevan uuden entiteettisuhteen.|

### <a name="import-a-solution"></a>Ratkaisun tuominen

Ratkaisu voi sisältää entiteetin metatiedot ja muita mukautettuja komponentteja. Hallitun tai hallitsemattoman ratkaisun tuonti Common Data Service for Apps -vuokraajaan pitää sisällään kyseiset entiteetit tai laajentaa olemassa olevia entiteettejä niiden sisältämillä uusilla entiteetin metatiedoilla.

### <a name="from-a-data-source-using-power-query"></a>Tietolähteestä Power Queryn avulla

Voit luoda uusia entiteettejä ja täyttää ne tiedoilla Power Queryn avulla. Lisätietoja: [Tietojen lisääminen Common Data Servicessä olevaan entiteettiin Power Queryn avulla](../../maker/common-data-service/data-platform-cds-newentity-pq.md)

### <a name="use-metadata-services"></a>Metatietopalvelujen käyttäminen

Common Data Service -palvelussa näytetyt verkkopalvelut sisältävät ominaisuuksia entiteetin metatietojen luomista, lukemista, kirjoittamista ja poistamista varten. Näitä palveluja käytetään useimmiten metatietojen lukemiseen, koska tiedot voivat informoida koodia suorituksen aikana siitä, miten ympäristö on mukautettu.

Lisätietoja: [Metatietopalvelut](use-web-services.md#metadata-services)

## <a name="entity-metadata"></a>Kohteiden metatiedot

Tietomalli määritetään metatietoina, jotka tallennetaan Common Data Service -palveluun. Näitä rakennetta koskevia tietoja kutsutaan *entiteetin metatiedoiksi*. 

- [EntityMetadata Class](/dotnet/api/microsoft.xrm.sdk.metadata.entitymetadata) määrittää nämä tiedot organisaatiopalvelun tapauksessa. 
- [EntityMetadata EntityType](/dynamics365/customer-engagement/web-api/entitymetadata) määrittää nämä tiedot WWW-ohjelmointirajapinnan tapauksessa. 

Entiteetin metatiedot sisältävät seuraavat tiedot:


|Tiedot  |Kuvaus  |
|---------|---------|
|Entiteetin ominaisuudet|Jokaisella entiteetillä on lähes 100 ominaisuutta, jotka kuvaavat, kuinka entiteetti tunnistetaan ja mitä sillä voidaan tehdä.  Lisätietoja: [Entiteetin metatiedot](entity-metadata.md)|
|Määritteet|Entiteetin `Attributes`-ominaisuus on kokoelma määritteitä. Jokaisella määritteellä on noin 50 ominaisuutta, jotka kuvaavat, kuinka määrite tunnistetaan, minkä tyyppisiä tietoja se sisältää, kuinka se on muotoiltu ja mitä sillä voidaan tehdä. Lisätietoja: [Määritteiden metatiedot](entity-attribute-metadata.md)|
|Suhteet|Entiteetin ominaisuuksista kolme on entiteettien välisten suhteiden kokoelmia. Nämä kokoelmat sisältävät erityyppisiä suhteita: monta-moneen, monta yhteen ja yksi-moneen. Lisätietoja: [Määritesuhteiden metatiedot](entity-relationship-metadata.md)|
|Oikeudet|Entiteetin ominaisuuksista yksi on kokoelma. Se sisältää 0–8 oikeutta, jotka identifioivat kyseisessä entiteetissä suoritettavissa olevien tietotoimintojen tyypit kuhunkin toimintoon liitetyllä yksilöivällä tunnisteella. Tällaisia toimintoja ovat: *Lisää*, *Lisää kohteeseen*, *Määritä*, *Luo*, *Poista*, *Lue*, *Jaa* ja *Kirjoita*.|
|Avaimet|Jokaisella entiteetillä on oletusarvoisesti yksi GUID-määrite (yksilöivä tunnus) ja `Keys`-ominaisuus on tyhjä kokoelma. Voit lisätä entiteettiin vaihtoehtoisia avaimia. Lisätietoja: [Entiteettiavaimet](entity-metadata.md#entity-keys)|

> [!TIP]
> Jos ymmärrät entiteetin metatietojen merkityksen järjestelmässä, voit ymmärtää helpommin, miten Common Data Service toimii. Monet ominaisuuksista myös säätelevät sitä, mitä entiteetit voivat tehdä malliin perustuvissa sovelluksissa. Metatietojen muokkaamiseen käytettävissä olevat suunnittelutyökalut eivät voi näyttää kaikkia metatietoihin sisältyviä yksityiskohtaisia tietoja. Voit asentaa malliin perustuvan Metadata Browser -sovelluksen, jonka avulla voit tarkastella kaikkia järjestelmässä olevia piilotettuja entiteettejä ja metatieto-ominaisuuksia. Lisätietoja: [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Organisaation metatietojen selaaminen](/dynamics365/customer-engagement/developer/browse-your-metadata)

### <a name="see-also"></a>Katso myös

[Common Data Service for Apps Developer -palvelun yleiskatsaus](overview.md)



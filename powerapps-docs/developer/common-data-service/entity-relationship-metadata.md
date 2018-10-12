---
title: Entiteettisuhteiden metatiedot | Microsoft Docs
description: Tutustu entiteettisuhteiden metatietojen käyttöön Common Data Service for Appsissa.
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
ms.date: 03/12/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: ea59e1eea1c0a85c2de1f2d654c10ed687ffe858
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863513"
---
# <a name="entity-relationship-metadata"></a>Entiteettisuhteiden metatiedot

Kun tarkastelet ratkaisunhallintaa tai `EntityMetadata`n kolmea suhdekokoelmaa, saatat ajatella, että on olemassa kolmentyyppisiä entiteettisuhteita. Itse asiassa niitä on vain kaksi, kuten seuraavassa taulukossa esitetään.

|Suhteen tyyppi|Kuvaus|
|--|--|
|Yksi moneen<br />[OneToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.onetomanyrelationshipmetadata)|Entiteettisuhde, jossa yksi **ensisijaisen entiteetin** entiteettitietue voidaan liittää useisiin muihin **liittyvän entiteetin** tietueisiin liittyvässä entiteetissä olevan hakukentän ansiosta.<br />Kun tarkastelet ensisijaisen entiteetin tietuetta, näet luettelon siihen yhdistetyistä liittyvän entiteetin tietueista.|
|Monta moneen<br />[ManyToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.manytomanyrelationshipmetadata)|Tämä entiteettisuhde on riippuvainen erityisestä *Suhde-entiteetistä*, jota kutsutaan toisinaan *Leikkaa*-entiteetiksi. Siten yhden entiteetin useita tietueita voidaan liittää useisiin toisen entiteetin tietueisiin.<br />Kun tarkastelet kumman tahansa monta-moneen-suhteessa olevan entiteetin tietueita, näet luettelon niihin mahdollisesti liittyvistä toisen entiteetin tietueista.|

`EntityMetadata`n `ManyToOneRelationships`-kokoelma sisältää [OneToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.onetomanyrelationshipmetadata)-tyyppejä. Entiteettien välillä on yksi-moneen-tyyppisiä suhteita, jotka viittaavat kumpaankin entiteettiin joko *ensisijaisena entiteettinä* tai *liittyvänä entiteettinä*. Liittyvässä entiteetissä, jota kutsutaan toisinaan *alientiteetiksi*, on hakumäärite, jonka avulla voidaan tallentaa viittaus tietueeseen ensisijaisesta entiteetistä, jota kutsutaan myös *pääentiteetiksi*. Monta-yhteen-suhde on vain yksi-moneen-suhde tarkasteltuna liittyvän entiteetin näkökulmasta.

> [!NOTE]
> Vaikka liittyviä entiteettejä kutsutaan toisinaan *alientiteeteiksi*, niitä ei tule sekoittaa niihin [alientiteetteihin](entity-metadata.md#child-entities), jotka viittaavat suojauksen käyttöön liittyvissä entiteeteissä.

Lisätietoja:
- [Dynamics 365 asiakkaalle suunnattu mukautusopas: Entiteettien välisten suhteiden luominen ja muokkaaminen](/dynamics365/customer-engagement/customize/create-edit-entity-relationships)
- [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Entiteettisuhteiden metatietojen mukauttaminen](/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)

## <a name="cascade-configuration"></a>Porrastuvat määritykset

Entiteettien välisen yksi-moneen-suhteen tapauksessa on olemassa porrastuvia toimintatapoja, jotka voidaan määrittää tietojen eheyden säilyttämiseksi ja liiketoimintaprosessien automatisoimiseksi.

Lisätietoja:

- [Dynamics 365 asiakkaalle suunnattu mukautusopas: 1:N (yksi moneen)- tai N:1 (monta yhteen) -suhteiden luominen > Suhteiden toiminta](/dynamics365/customer-engagement/customize/create-and-edit-1n-relationships#relationship-behavior)
- [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Suhteiden toiminta](/dynamics365/customer-engagement/developer/entity-relationship-behavior)


## <a name="create-a-hierarchy-of-entities"></a>Entiteettien hierarkian luominen

Voit määrittää hierarkian itseensä viittaavan yksi-moneen-suhteen sisällä valitsemalla `IsHierarchical`-ominaisuudelle asetuksen `true`.

Malliin perustuvien sovellusten tapauksessa tämä mahdollistaa käyttökokemuksen, jossa voit tarkastella ja käsitellä hierarkiaa. 

Kehittäjille tämä mahdollistaa uudenlaisten hierarkiaan perustuvien kyselytyyppien käytön operaattorien `Under` ja `Not Under` avulla.

Lisätietoja: [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Hierarkkisesti toisiinsa liittyvien tietojen haku ja visualisointi](/dynamics365/customer-engagement/customize/query-visualize-hierarchical-data)

### <a name="see-also"></a>Katso myös

[Common Data Service for Apps -entiteetit](entities.md)

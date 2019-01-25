---
title: 'Kehittäjät: Parhaat käytännöt ja ohjeita metatietojen käsittelemiseen Common Data Service for Appsille | Microsoft Docs'
description: Parhaat käytännöt ja ohjeita metatietojen käsittelemiseen Common Data Service for Appsin kehittäjille.
services: ''
suite: powerapps
documentationcenter: na
author: jowells
manager: austinj
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/12/2018
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 938d3ea2337137b1c78a1f4849191a261ac7a30a
ms.sourcegitcommit: 11486fb4c16095e3fef785126003cac3e3e06c0d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/14/2019
ms.locfileid: "54271372"
---
# <a name="best-practices-and-guidance-while-working-with-metadata-for-the-common-data-service-for-apps"></a>Parhaat käytännöt ja ohjeita metatietojen käsittelemiseen Common Data Service for Appsille

Tässä alla olevassa luettelossa on kaikki ohjeet ja parhaat käytännöt, jotka liittyvät metatietojen käsittelemiseen Common Data Services for Appsissa.


|Paras käytäntö  |Kuvaus  |
|---------|---------|
|[Nouda julkaistut metatiedot](retrieve-published-metadata.md)     |Julkaisemattomien metatietojen hakeminen ei vain lisää rasitetta itse pyynnön käsittelemiseen, mikä saa sen suoriutumaan hitaammin, se voi myös palauttaa metatietoja, joita pyytäjä ei odota.         |
|[Nouda tietyt sarakkeet entiteetille kyselyiden ohjelmointirajapintojen kautta](retrieve-specific-columns-entity-via-query-apis.md)     |Kyselyiden, jotka on lähetetty tietojen noutamista varten, tulee sisältää tietyt kyselyyn liittyvän ColumnSet-esiintymän sarakkeet kaikkien sarakkeiden asemesta.         |

# <a name="see-also"></a>Katso myös
[Tietoja käyttävien metatietojen käsitteleminen](../../metadata-services.md)<br />
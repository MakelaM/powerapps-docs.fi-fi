---
title: 'Kehittäjät: Parhaat käytännöt ja ohjeita metatietojen käsittelemiseen Common Data Servicelle | Microsoft Docs'
description: Parhaat käytännöt ja ohjeita metatietojen käsittelemiseen PowerAppsin Common Data Servicen kehittäjille.
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
ms.openlocfilehash: 35e07c87e515759a6e61a0c0a027c190b11bef53
ms.sourcegitcommit: 5b2b70c3fc7bcba5647d505a79276bbaad31c610
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2019
ms.locfileid: "58358008"
---
# <a name="best-practices-and-guidance-while-working-with-metadata-for-the-common-data-service"></a>Parhaat käytännöt ja ohjeita metatietojen käsittelemiseen Common Data Servicelle

Tässä alla olevassa luettelossa on kaikki ohjeet ja parhaat käytännöt, jotka liittyvät metatietojen käsittelemiseen Common Data Servicessa.


|Paras käytäntö  |Kuvaus  |
|---------|---------|
|[Nouda julkaistut metatiedot](retrieve-published-metadata.md)     |Julkaisemattomien metatietojen hakeminen ei vain lisää rasitetta itse pyynnön käsittelemiseen, mikä saa sen suoriutumaan hitaammin, se voi myös palauttaa metatietoja, joita pyytäjä ei odota.         |
|[Nouda tietyt sarakkeet entiteetille kyselyiden ohjelmointirajapintojen kautta](retrieve-specific-columns-entity-via-query-apis.md)     |Kyselyiden, jotka on lähetetty tietojen noutamista varten, tulee sisältää tietyt kyselyyn liittyvän ColumnSet-esiintymän sarakkeet kaikkien sarakkeiden asemesta.         |

# <a name="see-also"></a>Katso myös
[Tietoja käyttävien metatietojen käsitteleminen](../../metadata-services.md)<br />
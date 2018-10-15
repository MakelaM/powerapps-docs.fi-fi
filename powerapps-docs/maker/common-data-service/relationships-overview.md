---
title: PowerAppsin entiteetin yleiskatsaus | MicrosoftDocs
description: Lue tietoja siitä, miten voit luoda ja muokata entiteettejä PowerApps-portaalin avulla
ms.custom: ''
ms.date: 07/25/2018
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
ms.assetid: ''
caps.latest.revision: 0
ms.author: matp
manager: kvivek
ms.openlocfilehash: 1c45941a7b00e9393aab429d2573b2e48964a4de
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679811"
---
# <a name="entity-relationships-overview"></a>Entiteettisuhteiden yleiskatsaus

Entiteettisuhteet määrittävät, miten entiteetin tietueet voidaan liittää muiden entiteettien tai saman entiteetin tietueisiin. Entiteettisuhteita on kahdenlaisia.
- **Yksi moneen -suhteet**. Yksi-moneen -entiteettisuhteessa monta viittaavaa (liittyvää) entiteettitietuetta voidaan liittää yhteen viitattuun (ensisijaiseen) entiteettitietueeseen. Viitattua entiteettitietuetta kutsutaan joskus nimellä ”pääkohde” ja viittaavan entiteetin tietueita nimellä ”alikohteet”.  Monta yhteen -suhde on siis vain yksi-moneen -suhde alikohteen näkökulmasta.
- **Monta moneen -suhde**. Monta-moneen -entiteettisuhteessa useita entiteettitietueita voidaan liittää useaan eri entiteettitietueeseen. Tietueet, jotka liittyvät toisiinsa monta-moneen -suhteen kautta, voidaan pitää toistensa vertaisina ja niiden välinen suhde on vastavuoroinen. 

## <a name="see-also"></a>Katso myös
[Luo entiteettien välinen suhde](data-platform-entity-lookup.md) <br/>
[Monta-moneen -entiteettisuhteiden luominen Common Data Service for Appsissa PowerApps-portaalin avulla](create-edit-nn-relationships-portal.md)
---
title: Komponentin toteutus Kirjasto | Microsoft Docs
description: Luo koodi komponentteja JavaScriptin tai TypeScript-koodin avulla
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d100dc3-bd82-4b45-964c-d90eaebc0735
ms.openlocfilehash: 31b7d2b30a1ef83ca4400011d50854713cb260f6
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72347241"
---
# <a name="component-implementation-library"></a>Komponentin toteutus Kirjasto

Komponentti kirjaston toteuttaminen on yksi tärkeimmistä vaiheista, kun kehität koodi komponentteja PowerApps Component Frameworkin avulla. Kehittäjät voivat käyttää komponentti kirjastoa käyttäen TypeScript-kohdetta. Jokaisella koodi osalla on oltava Kirjasto, joka sisältää sellaisen funktio määrityksen, joka palauttaa objektin, joka toteuttaa koodi komponentti liittymässä kuvatut menetelmät. 

Objekti toteuttaa seuraavat menetelmät:

- [init](reference/control/init.md) (pakollinen)
- [Updateview](reference/control/updateview.md) (pakollinen)
- [Gettuotokset](reference/control/getoutputs.md) (valinnainen)
- [tuhoa](reference/control/destroy.md) (pakollinen)

Nämä menetelmät ohjaavat koodi komponentin elin kaarta.


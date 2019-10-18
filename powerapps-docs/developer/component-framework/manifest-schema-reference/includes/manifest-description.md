---
title: Luettelo | Microsoft Docs
description: ''
keywords: ''
ms.author: nabuthuk
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
ms.assetid: 31af2963-b4ca-4347-98f6-4a3f6277f43a
ms.openlocfilehash: 22750956cea12e1ed17bbc1ee8d4f015cf0ce2c1
ms.sourcegitcommit: 63ea15e2f861d43333aacda19230cd8922d7bdfd
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/01/2019
ms.locfileid: "72338915"
---
Luettelotiedosto on metatietotiedosto, joka määrittää osan. Se on `XML` tiedosto, joka kuvaa seuraavaa:

- Komponentin nimi tila.
- Niiden tietojen tyyppi, jotka se voidaan määrittää, joko kenttä tai tieto joukko.
- Ominaisuudet, jotka voidaan määrittää sovelluksessa, kun osa lisätään.
- Luettelo resurssi tiedostoista, joita komponentti tarvitsee. 
  - Toisen niistä on oltava JavaScript-verkko resurssi. Tämän JavaScript-kohteen tulee sisältää funktio, joka alustaa objektin. Näin toteutetaan liittymä, joka paljastaa komponentin toimintaan tarvittavat metodit. Tätä kutsutaan osan toteutuskirjastoksi.
- Component toteutus Library-osan JavaScript-funktioiden nimi, joka palauttaa objektin, joka käyttää vaadittua komponentti liittymää.

Kun käyttäjä määrittää mukautetun komponentin pohjaan perustuvassa sovelluksessa tai mallipohjaisessa sovelluksessa, luettelo suodattaa käytettävissä olevat osat niin, että vain kontekstin kelvolliset osat ovat käytettävissä määritystä varten. Komponentin luettelossa määritetyt ominaisuudet hahmonnetaan määritys kenttinä, jotta komponentin määrittävä käyttäjä voi määrittää arvoja. Nämä ominaisuus arvot ovat sitten käytettävissä Component-funktiolla suorituksen aikana.

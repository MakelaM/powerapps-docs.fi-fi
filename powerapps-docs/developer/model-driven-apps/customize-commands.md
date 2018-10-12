---
title: Komentojen muokkaaminen malliin perustuvilla sovelluksilla | Microsoft Docs
description: Lue ohjeet komentojen muokkaamiseen malliin perustuvilla sovelluksilla
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
ms.date: 03/17/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 4721ba49fe227d31f539eabd863b50842e7515b6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836250"
---
# <a name="customize-commands-with-model-driven-apps"></a>Komentojen muokkaaminen malliin perustuvilla sovelluksilla 

Lomakkeessa tai luettelon komentopalkissa näytettävät komennot ovat muokattavissa. Komennot perustuvat Office-valintanauhoissa käytettäviin XML-rakenteisiin, joten käytämme edelleen termiä *valintanauha*. Kun luot komennon, määrität kolme elementtiä:

- *Näyttösäännöt* tarkistetaan lomakkeen tai luettelon lataamisen yhteydessä. Niiden perusteella päätetään, näytetäänkö komento tai komentoryhmä.
- *Käyttöönottosäännöt* määrittävät, onko komento käytössä. Tämä perustuu useisiin ehtoihin, esimerkiksi nykyiseen valittuun kohteeseen käyttöliittymässä.
- Kunkin komennon *toiminto* määrittää, mitä komento tekee, kun se valitaan. Komento voi olla esimerkiksi URL-osoitteen avaaminen tai JavaScript-verkkoresurssissa määritetyn funktion suorittaminen.

Mukautettujen komentojen sijainti perustuu olemassa oleviin komentoihin. Sinun täytyy määrittää *mukautettu toiminto*, joka määrittää, mikä muutos suoritetaan olemassa olevalle komentojoukolle. 

Komennoille ei tarjota suunnittelutyökalua. Onneksi yhteisöstä löytyy kuitenkin työkaluja. [Ribbon Workbench](http://www.develop1.net/public/rwb/ribbonworkbench.aspx) tarjoaa graafisen käyttöliittymän. Se on käytetyin työkalu komentojen muokkaamiseen.

Lisätietoja: [Dynamics 365 Customer Engagementin kehittäjän opas: komentojen ja valintanauhan muokkaaminen](/dynamics365/customer-engagement/developer/customize-dev/customize-commands-ribbon)



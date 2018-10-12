---
title: Sovella liiketoimintalogiikkaa koodin avulla | Microsoft Docs
description: Tutustu siihen, miten kehittäjät voivat käyttää koodia liiketoimintalogiikan soveltamiseen Common Data Service for Appsissa.
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
ms.date: 02/26/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 9abcbf25d2376e28f83988ceb3797d3891ca53bc
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42843333"
---
# <a name="apply-business-logic-with-code"></a>Sovella liiketoimintalogiikkaa koodin avulla

Sinun kannattaa käyttää yhtä monista määrittävistä prosessivalinnoista aina kun se on mahdollista, jos johonkin vaatimukseen sisältyy liiketoimintalogiikan määrittäminen. Katso [Dynamics 365 asiakkaalle suunnattu mukautusopas: Mukautetun liiketoimintalogiikan luominen prosessien kautta](/dynamics365/customer-engagement/customize/guide-staff-through-common-tasks-processes)

Jos jokin määrittävä prosessi ei vastaa vaatimusta, sinulla on kehittäjänä käytettävissä useita vaihtoehtoja. Tässä ohjeaiheessa esitellään yleisiä koodin kirjoittamisen vaihtoehtoja.

## <a name="create-a-workflow-extension"></a>Työnkulun laajennuksen luominen

Voit lisätä prosessin suunnittelutyökalussa uusia vaihtoehtoja kirjoittamalla .NET-kokoonpanon. Tämä menetelmä tarjoaa työnkulun suunnittelutyökalun käyttäjille uuden vaihtoehdon tietyn ehdon soveltamista tai uuden toiminnon suorittamista varten. Käyttäjät, jotka eivät ole kehittäjiä, voivat sitten soveltaa logiikkaa koodiin käyttämällä työnkulun laajennusta uudelleen.

Lisätietoja: [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Mukautetut työnkulun toiminnot (työnkulun kokoonpanot)](/dynamics365/customer-engagement/developer/custom-workflow-activities-workflow-assemblies)

## <a name="create-a-plug-in"></a>Laajennuksen luominen

Voit soveltaa liiketoimintalogiikkaa palvelimessa kirjoittamalla .NET-kokoonpanon laajennukseksi tietotapahtumavirtaan. Common Data Service for Appsiin liittyy erityinen sovelluskehys, jota voit käyttää tiettyjen tapahtumien rekisteröintiin suorittaaksesi koodin, joka on määritetty tietyn kokoonpanon tietyn luokan puitteissa. Kyseinen luokka perii erityisen liittymän, joka näyttää [Suorita-menetelmän](/dotnet/api/microsoft.xrm.sdk.iplugin.execute). Kun rekisteröity tapahtuma toteutuu, `Execute`-menetelmä käynnistyy kyseisessä luokassa ja siihen välitetään tilannekohtaisia tietoja tapahtumasta.

Kokoonpanojen rekisteröintiin käytetään *laajennuksen rekisteröintityökalua*.

Voit käyttää SDK-kokoonpanoissa määritettyä objektimallia `Execute`-menetelmän puitteissa tilannekohtaisten tapahtumatietojen arviointiin ja asianmukaisten toimien suorittamiseen seuraavia tarkoituksia varten:
- Voit määrittää, peruutetaanko toiminto virheen tapahtuessa.
- Voit muuttaa Suorita-menetelmään välitettyjä tilannekohtaisia tietoja.
- Voit suorittaa lisätoimintoja prosessien automatisoimiseksi organisaatiopalvelun avulla.

### <a name="synchronous-and-asynchronous-plug-ins"></a>Synkroniset ja asynkroniset laajennukset
Laajennukset voidaan rekisteröidä suoritettaviksi synkronisesti tapahtuman sisällä tai lykättäviksi ja lähetettäväksi jonoon, joka soveltaa logiikkaa sellaisella hetkellä, jona sillä on pienempi vaikutus palvelimeen. Tästä syystä on suositeltavaa käyttää asynkronisia laajennuksia.

Kun rekisteröit laajennuksen suoritettavaksi synkronoidusti tietyn tapahtuman osalta, voit valita eri vaihtoehdoista, milloin haluat suorittaa koodin. Vaiheita on kolme:

|Tapahtuma  |Kuvaus  |
|---------|---------|
|Esitarkistus|Tapahtuu ennen tietokantatapahtuman alkamista. Tämä on hyvä vaihe soveltaa liiketoimintalogiikkaa sen määrittämiseen, pitäisikö toiminto peruuttaa ennen tapahtuman alkamista, jotta vältettäisiin tapahtuman keskeyttämisestä aiheutuva suorituskyvyn heikentyminen.|
|Esitoiminto|Tapahtuu tietokantatapahtuman alkamisen jälkeen. Toiminnon peruuttaminen tässä vaiheessa johtaa väistämättä tapahtuman keskeyttämiseen.|
|Jälkitoiminto|Tapahtuu tietokantatapahtuman aikana päätietotoiminnon suorittamisen jälkeen. Sisältää mahdolliset muutokset, jotka on otettu käyttöön aiemmissa tapahtumissa, mutta aiheuttaa vieläkin merkittävämpää haittaa, jos toiminto peruutetaan.|

> [!NOTE]
> Synkronisilla laajennuksilla on rajoituksia sen suhteen, kuinka paljon järjestelmäresursseja ne voivat käyttää. Jos laajennus ylittää raja-arvot tai lopettaa vastaamisen, tapahtuu poikkeus, joka peruuttaa toiminnon.

Lisätietoja: [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Laajennusten kirjoittaminen liiketoimintaprosessien laajentamiseksi](/dynamics365/customer-engagement/developer/write-plugin-extend-business-processes)

### <a name="see-also"></a>Katso myös

[Common Data Service for Apps Developer -palvelun yleiskatsaus](overview.md)

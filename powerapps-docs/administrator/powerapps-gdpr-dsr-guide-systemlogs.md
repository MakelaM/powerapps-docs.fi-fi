---
title: Järjestelmän luomia lokeja koskeviin rekisteröidyn henkilön pyyntöihin vastaaminen PowerApps-, Microsoft Flow- ja Common Data Service for Apps -palveluissa  | Microsoft Docs
description: Miten vastaat järjestelmän luomia lokeja koskeviin rekisteröidyn henkilön pyyntöihin PowerApps-, Microsoft Flow- ja Common Data Service for Apps -palveluissa
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms-topic: article
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/23/2018
ms.author: jamesol
ms.openlocfilehash: c3086ce05ba748b5387ec4ae5a1e794658b5677a
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-dsr-requests-for-system-generated-logs-in-powerapps-microsoft-flow-and-common-data-service-for-apps"></a>Järjestelmän luomia lokeja koskeviin rekisteröidyn henkilön pyyntöihin vastaaminen PowerApps-, Microsoft Flow- ja Common Data Service for Apps -palveluissa
Microsoft tarjoaa mahdollisuuden käyttää, viedä ja poistaa järjestelmän luomia lokeja, jotka voidaan luokitella henkilötiedoiksi Euroopan Unionin (EU) yleisen tietosuoja-asetuksen (GDPR) *henkilötietojen* laajan määritelmän mukaisesti. Esimerkkejä järjestelmän luomista lokeista, jotka voidaan luokitella henkilötiedoiksi yleisen tietosuoja-asetuksen mukaisesti:
* Tuotteen ja palvelun käyttötiedot, kuten käyttäjän toimintalokit
* Käyttäjän hakupyynnöt ja kyselytiedot
* Tuotteen ja palveluiden luomat tiedot järjestelmän toiminnallisuuden ja käyttäjien tai muiden järjestelmien vuorovaikutuksen seurauksena

Huomaathan, että järjestelmän luomien lokien tietojen rajoittamista tai korjaamista ei tueta. Järjestelmän luomien lokien tiedot ovat oikeita toimia, joita käyttäjä on tehnyt Microsoftin pilvipalveluissa, ja diagnostiikkatiedot&mdash;mukaan lukien niiden muokkaaminen&mdash;vaarantaisi toimien historiatiedot ja lisäisi petos- ja tietoturvariskejä.

## <a name="accessing-and-exporting-system-generated-logs"></a>Järjestelmän luomien lokien käyttäminen ja vienti
Järjestelmänvalvojat pääsevät käsiksi järjestelmän luomiin lokeihin, jotka sisältävät tietoja siitä, miten käyttäjä on käyttänyt PowerApps-, Microsoft Flow- ja Common Data Service (CDS) for Apps -palveluita ja -sovelluksia.

Järjestelmän luomien lokien käyttäminen ja vienti:

1. Siirry [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/) -portaaliin ja kirjaudu sisään Office 365:n yleisen järjestelmänvalvojan tunnistetiedoilla.

2. Valitse sivun yläosassa olevasta **Tietosuoja**-valikosta **Data Subject Request** (Rekisteröidyn henkilön pyyntö).

3. Valitse **Data Subject Request** (Rekisteröidyn henkilön pyyntö) -sivulla **System Generated Logs** (Järjestelmän luomat lokit) ja **Tietolokin vienti**. Tietolokin vienti näyttää luettelon tietojen vientipyynnöistä, jotka organisaatiosi on lähettänyt.

4. Jos haluat luoda uuden pyynnön käyttäjälle, valitse **Create Export Data Request** (Luo tietojen vientipyyntö).

    Kun olet luonut uuden pyynnön, se tulee näkyviin **Tietolokin vienti** -sivulle, jolla voit seurata sen tilaa. Kun pyyntö on suoritettu, voit siirtyä linkkiä napsauttamalla järjestelmän luomiin lokeihin, jotka viedään organisaatiosi Azure-tallennussijaintiin 30 päivän kuluessa pyynnön luomisesta. Tiedot tallennetaan yleisissä, koneellisesti luettavissa tiedostomuodoissa, kuten XML-, CSV- tai JSON-tiedostoina. Jos sinulla ei ole Azure-tiliä ja Azure-tallennussijaintia, sinun on luotava Azure-tili ja/tai Azure-tallennussijainti organisaatiollesi, jotta Tietolokin vienti -työkalu voi viedä järjestelmän luomat lokit. Lisätietoja on artikkelissa [Introduction to Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction) (Johdanto Azure-tallennukseen).

Seuraavassa taulukossa on yhteenveto järjestelmän luomien lokien käytöstä ja viennistä:

| Kysymys | Vastaus |
| --- | --- |
| Kuinka kauan Microsoftin Tietolokin vienti -työkalulla kestää suorittaa pyyntö? |    Tämä riippuu useista tekijöistä. Useimmissa tapauksissa pyyntö suoritetaan yhden tai kahden päivän kuluessa, mutta suorittaminen voi kestää jopa 30 päivää.
| Missä muodossa tulos on? | Tulos on jäsennettyjen, koneellisesti luettavien tiedostojen muodossa, kuten XML-, CSV- tai JSON-muodossa.
| Kenellä on oikeus käyttää Tietolokin vienti -työkalua ja lähettää järjestelmän luomien lokien käyttöoikeuspyyntöjä? | Office 365:n yleisillä järjestelmänvalvojilla on pääsy GDPR Log Manager -työkaluun.
| Mitä tietoja Tietolokin vienti -työkalu palauttaa? | Tietolokin vienti -työkalu palauttaa järjestelmän luomia lokeja, joka Microsoft tallentaa. Viedyt tiedot koskevat useita Microsoftin palveluita, mukaan lukien Office 365, Azure, Dynamics, PowerApps, Microsoft Flow ja CDS for Apps.
| Miten tiedot palautetaan käyttäjälle? |   Tiedot viedään organisaatiosi Azure-tallennussijaintiin. Organisaatiosi järjestelmänvalvojat määrittävät, miten tiedot näytetään/palautetaan käyttäjille.
| Miltä järjestelmän luomien lokien tiedot näyttävät? |  Esimerkki järjestelmän luomasta lokitietueesta JSON-muodossa: <br> [{ <br>"DateTime": "2017-04- 28T12:09:29-07:00",  <br> "AppName": "SharePoint", <br> "Action": "OpenFile", "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" <br>}]

> [!NOTE]
>  Turvallisuus- ja valvontasyistä jotkin ominaisuudet eivät salli henkilötietoja sisältävien järjestelmän luomien lokien viemistä tai poistamista, jotta kyseisten tietojen koskemattomuus säilyy.
>
>

## <a name="deleting-system-generated-logs"></a>Järjestelmän luomien lokien poistaminen
Jotta voit poistaa käyttöoikeuspyynnön kautta noudetut järjestelmän luomat lokit, sinun on poistettava käyttäjä palvelusta ja poistettava hänen Azure Active Directory -tilinsä pysyvästi. Katso ohjeet käyttäjän pysyvään poistamiseen *Azure Data Subject Request (Azuren rekisteröidyn henkilön pyyntö) -GDPR-dokumentaation* osasta **Deleting a user** (Käyttäjän poistaminen). Dokumentaatio on saatavilla [Office 365:n Service Trust Portalin](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) kautta. On tärkeää huomata, että käyttäjätilin pysyvää poistamista ei voi peruuttaa poiston aloittamisen jälkeen.

Kun käyttäjätili poistetaan pysyvästi, käyttäjän tiedot poistetaan PowerApps-, Microsoft Flow- ja CDS for Apps -palveluiden järjestelmän luomista lokeista 30 päivän kuluessa.
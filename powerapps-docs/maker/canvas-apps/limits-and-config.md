---
title: Järjestelmävaatimukset, rajoitukset ja konfigurointiarvot | Microsoft Docs
description: PowerAppsin järjestelmävaatimukset, rajoitukset ja konfigurointiarvot
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: PowerApps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/07/2018
ms.author: sharik
ms.openlocfilehash: 5bf57ec96569751b3db656abdf04cebb1e13133a
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "32329843"
---
# <a name="system-requirements-limits-and-configuration-values"></a>Järjestelmävaatimukset, rajoitukset ja konfigurointiarvot
Tämä artikkeli sisältää laiteympäristöä ja verkkoselaimia koskevat vaatimukset sekä rajoitukset ja konfigurointiarvot PowerAppsia varten.

## <a name="supported-platforms-for-running-apps-using-the-powerapps-app"></a>Tuetut ympäristöt sovellusten suorittamiseksi PowerApps-sovelluksen avulla
| **Vähimmäisvaatimus** | **Suositus** |
| --- | --- |
| iOS 9.3 tai uudempi |iOS 10 tai uudempi sekä vähintään 2 gigatavua RAM-muistia |
| Android 5 tai uudempi |Android 7 tai uudempi sekä vähintään 4 gigatavua RAM-muistia |
| Windows 8.1 tai uudempi (ainoastaan PC) |Windows 10 Fall Creators -päivitys sekä vähintään 8 gigatavua RAM-muistia|

## <a name="supported-browsers-for-running-apps"></a>Tuetut selaimet sovellusten suorittamista varten
| **Selain** | **Käyttöjärjestelmä** |
| --- | --- |
| Google Chrome (uusin versio)<br>(suositus) |Windows 7 SP1, 8.1 ja 10 <br>Android 5 tai uudempi <br>iOS 8 tai uudempi<br>macOS |
| Microsoft Edge (uusin versio)<br>(suositus) |Windows 10 |
| Microsoft Internet Explorer 11 (yhteensopivuusnäkymä pois päältä) |Windows 7 SP1, 8.1 ja 10 |
| Mozilla Firefox (uusin versio) |Windows 7 SP1, 8.1 ja 10 <br> Android 5 tai uudempi <br>iOS 8 tai uudempi <br>macOS |
| Apple Safari (uusin versio) |iOS 8 tai uudempi <br>macOS |

## <a name="supported-browsers-for-powerapps-studio"></a>PowerApps Studion tuetut selaimet
| **Selain** | **Käyttöjärjestelmä** |
| --- | --- |
| Google Chrome (uusin versio)<br>(suositus) |Windows 7 SP1, 8.1 ja 10 <br>macOS |
| Microsoft Edge (uusin versio)<br>(suositus) |Windows 10 |
| Microsoft Internet Explorer 11 (yhteensopivuusnäkymä pois päältä) |Windows 7 SP1, 8.1 ja 10 |

## <a name="request-limits"></a>Pyyntöjen rajoitukset
Näitä rajoituksia sovelletaan kuhunkin yksittäiseen lähtevään pyyntöön:

| Nimi | Rajoitus |
| --- | --- |
| Aikakatkaisu |180 sekuntia |
| Uudelleenyritysten määrä |4 |

> [!NOTE]
> Uudelleenyritysten arvo saattaa vaihdella. Tietyissä virhetilanteissa uudelleenyritys ei ole tarpeellista.

## <a name="ip-addresses"></a>IP-osoitteet
PowerAppsista tulevissa pyynnöissä käytetään IP-osoitteita, jotka riippuvat sen [ympäristön](../../administrator/environments-overview.md) alueesta, jossa sovellus sijaitsee. Emme julkaise täysin kelvollisia toimialueiden nimiä, jotka ovat saatavilla PowerApps-skenaarioita varten.

Sovelluksen kautta yhdistetystä ohjelmointirajapinnoista tehdyt kutsut (esimerkiksi SQL API tai SharePoint API) tulevat tässä artikkelissa myöhemmin määritetystä IP-osoitteesta.

Käytä näitä osoitteita esimerkiksi, jos sinun täytyy lisätä IP-osoitteita sallittujen osoitteiden luetteloon Azure SQL -tietokantaa varten.

| Alue | Lähtevä IP-osoite |
| --- | --- |
| Aasia |52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124 |
| Australia |13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35 |
| Kanada |52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56 |
| Eurooppa |52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254 |
| Intia |52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245 |
| Japani |104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229 |
| Yhdysvallat |104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| Yhdysvallat (varhainen pääsy) |52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29 |

## <a name="required-services"></a>Vaaditut palvelut
Tässä luettelossa esitellään kaikki palvelut, joiden kanssa PowerApps Studiolla on tietoliikennettä, sekä niiden käyttötarkoitukset. Verkkosi **ei** saa estää näitä palveluja.

| Toimialue(et) | Protokollat | Käyttötarkoitukset |
| --- | --- | --- |
| management.azure.com |https |RP |
| msmanaged-na.azure-apim.net |https |Yhdistimien/ohjelmointirajapintojen suorituspalvelu |
| login.microsoft.com<br>login.windows.net<br>login.microsoftonline.com<br>secure.aadcdn.microsoftonline-p.com |https |ADAL |
| graph.microsoft.com<br>graph.windows.net |https |Azure Graph – käyttäjätietojen hankkimiseen (esimerkiksi profiilikuvat) |
| gallery.azure.com |https |Esimerkki- ja mallisovellukset |
| *.azure-apim.net |https |API Hubs – eri alitoimialueet kutakin lokaalia varten |
| *.powerapps.com |https |WebAuth + portaali |
| *.azureedge.net |https |WebAuth |
| *.blob.core.windows.net |https |Blob-objektisäilö |
| vortex.data.microsoft.com |https |Telemetria |

---
title: Kangassovellusten järjestelmävaatimukset, rajoitukset ja konfigurointiarvot | Microsoft Docs
description: PowerAppsissa rakennettujen kangassovellusten järjestelmävaatimukset, rajoitukset ja konfigurointiarvot
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/07/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5ba279e361dfe450de1187cf6aca87bc026178ba
ms.sourcegitcommit: 60006ce9cb21c59e588c00f2ba5c41ffebbbba09
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/30/2018
ms.locfileid: "47456294"
---
# <a name="system-requirements-limits-and-configuration-values-for-canvas-apps"></a>Kangassovellusten järjestelmävaatimukset, rajoitukset ja konfigurointiarvot
Tämä artikkeli sisältää laiteympäristöä ja verkkoselaimia koskevat vaatimukset sekä rajoitukset ja konfigurointiarvot PowerAppsia varten.

## <a name="supported-platforms-for-running-canvas-apps-using-the-powerapps-app"></a>Tuetut ympäristöt kangassovellusten suorittamiseksi PowerApps-sovelluksen avulla

| **Vähimmäisvaatimus** | **Suositus** |
| --- | --- |
| iOS 9.3 tai uudempi |iOS 10 tai uudempi sekä vähintään 2 gigatavua RAM-muistia |
| Android 5 tai uudempi |Android 7 tai uudempi sekä vähintään 4 gigatavua RAM-muistia |
| Windows 8.1 tai uudempi (ainoastaan PC) |Windows 10 Fall Creators -päivitys sekä vähintään 8 gigatavua RAM-muistia|

## <a name="supported-browsers-for-running-canvas-apps"></a>Tuetut selaimet kangassovellusten suorittamista varten

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

> [!IMPORTANT]
>   Päivitä aiemmin määritetyt asetukset mahdollisimman pian ennen 30.9.2018 siten, että ne sisältävät ja vastaavat tämän luettelon alueiden IP-osoitteita, joissa PowerApps-sovelluksesi ovat.

| Alue | Lähtevä IP-osoite |
| --- | --- |
| Aasia | 13.75.36.64–13.75.36.79, 13.67.8.240–13.67.8.255, 52.175.23.169, 52.187.68.19, 52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 52.187.53.78, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124, 23.97.72.250  |
| Australia  | 13.70.72.192–13.70.72.207, 13.72.243.10, 13.77.50.240–13.77.50.255, 13.70.136.174, 13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.188.38, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35, 13.70.88.23 |
| Brasilia | 191.233.203.192–191.233.203.207, 104.214.19.48–104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Kanada | 13.71.170.208–13.71.170.223, 13.71.170.224–13.71.170.239, 52.237.24.126, 40.69.106.240–40.69.106.255, 52.242.35.152, 52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56, 52.229.123.161, 52.233.27.68 |
| Eurooppa | 13.69.227.208–13.69.227.223, 52.178.150.68, 13.69.64.208–13.69.64.223, 52.174.88.118, 52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 52.178.37.42, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254, 52.164.249.26, 137.117.161.181 |
| Intia  | 104.211.81.192–104.211.81.207, 52.172.211.12, 40.78.194.240–40.78.194.255, 13.71.125.22, 104.211.146.224–104.211.146.239, 104.211.189.218, 52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.49.180, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245, 52.172.153.107 |
| Japani | 13.78.108.0–13.78.108.15, 13.71.153.19, 40.74.100.224–40.74.100.239, 104.215.61.248, 104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 104.214.151.229, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229, 13.78.121.151 |
| Yhdistynyt kuningaskunta | 51.140.148.0–51.140.148.15, 51.140.80.51, 51.140.211.0–51.140.211.15, 51.141.47.105 |
| Yhdysvallat | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49, 104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| Yhdysvallat (varhainen pääsy)  | 13.71.195.32–13.71.195.47, 52.161.102.22, 13.66.140.128–13.66.140.143, 52.183.78.157, 52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 52.161.31.35, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29, 13.66.208.24 |


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

> [!NOTE]
> Jos käytät VPN:ää, se on määritettävä niin, että se ei sisällä PowerApps Mobilen tunneloinnin localhostia.

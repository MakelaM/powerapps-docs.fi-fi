---
title: Kangassovellusten järjestelmävaatimukset, rajoitukset ja konfigurointiarvot | Microsoft Docs
description: PowerAppsissa rakennettujen kangassovellusten järjestelmävaatimukset, rajoitukset ja konfigurointiarvot
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/15/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0ce5218143a8283690cdaf7c1d9be2b1da3d629e
ms.sourcegitcommit: 60a7dc7855d482b63719d121dbe5353e304d67f4
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393135"
---
# <a name="system-requirements-limits-and-configuration-values-for-canvas-apps"></a>Kangassovellusten järjestelmävaatimukset, rajoitukset ja konfigurointiarvot
Tämä artikkeli sisältää laiteympäristöä ja verkkoselaimia koskevat vaatimukset sekä rajoitukset ja konfigurointiarvot PowerAppsia varten.

## <a name="supported-platforms-for-running-canvas-apps-using-the-powerapps-app"></a>Tuetut ympäristöt kangassovellusten suorittamiseksi PowerApps-sovelluksen avulla

| **Vähimmäisvaatimus** | **Suositus** |
| --- | --- |
| iOS 9.3 tai uudempi |iOS 10 tai uudempi sekä vähintään 2 gigatavua RAM-muistia |
| Android 5 tai uudempi |Android 7 tai uudempi sekä vähintään 4 gigatavua RAM-muistia |
| Windows 8.1 tai uudempi (ainoastaan PC) |Windows 10 Fall Creators -päivitys sekä vähintään 8 gigatavua RAM-muistia|

> [!NOTE]
> Emme tällä hetkellä tue Windows-ympäristön uusia ominaisuuksia PowerApps-sovelluksessa. Ominaisuudet, kuten parannettu Common Data Service-vaihto ehto ja vieras käyttö, eivät ole käytettävissä tässä ympäristössä. Suosittelemme, että käytät Windowsin verkko soitinta, jotta voit hyödyntää kaikkia ominaisuuksia. Windows-ympäristön PowerApps-sovelluksen päivitykset julkistetaan jatkossa.

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
| Aasia | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Australia  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Brasilia | 191.233.203.192–191.233.203.207, 104.214.19.48–104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Kanada | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Eurooppa | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181|
| Intia  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Japani | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| Etelä-Amerikka | 191.233.203.192–191.233.203.207, 104.214.19.48–104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Yhdistynyt kuningaskunta | 51.140.148.0–51.140.148.15, 51.140.80.51, 51.140.211.0–51.140.211.15, 51.141.47.105 |
| Yhdysvallat | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49 |
| Yhdysvallat (varhainen pääsy)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

## <a name="required-services"></a>Vaaditut palvelut
Tässä luettelossa esitellään kaikki palvelut, joiden kanssa PowerApps Studiolla on tietoliikennettä, sekä niiden käyttötarkoitukset. Verkkosi **ei** saa estää näitä palveluja.

| Toimialue(et) | Protokollat | Käyttötarkoitukset |
| --- | --- | --- |
| management.azure.com |https |RP |
| msmanaged-na.azure-apim.net |https |Yhdistimien/ohjelmointirajapintojen suorituspalvelu |
| login.microsoft.com<br>login.windows.net<br>login.microsoftonline.com<br>secure.aadcdn.microsoftonline-p.com |https |ADAL |
| graph.microsoft.com<br>graph.windows.net |https |Azure Graph – käyttäjä tietojen hakeminen (esimerkiksi profiili kuva) |
| gallery.azure.com |https |Esimerkki- ja mallisovellukset |
| \*. azure-apim.net |https |API Hubs – eri alitoimialueet kutakin lokaalia varten |
| \*. powerapps.com |https | create.powerapps.com, make.powerapps.com, content.powerapps.com ja web.powerapps.com |
| \*. azureedge.net |https | create.powerapps.com, make.powerapps.com, content.powerapps.com ja web.powerapps.com |
| \*. blob.core.windows.net |https | Blob-objektisäilö |
| \*. flow.microsoft.com | https | create.powerapps.com, make.powerapps.com, content.powerapps.com ja web.powerapps.com |
| vortex.data.microsoft.com |https |Telemetria |
| localhost | https | PowerApps Mobile

> [!NOTE]
> Jos käytät VPN:ää, se on määritettävä niin, että se ei sisällä PowerApps Mobilen tunneloinnin localhostia.

## <a name="size-limits"></a>Koko rajoitukset

Saat lisä tietoja teksti-, hyperlinkit-, kuvat-ja tieto väline- [tieto tyyppien](functions/data-types.md#text-hyperlink-image-and-media)koko rajoituksista.

## <a name="powerapps-per-app-plan"></a>PowerApps Sovelluskohtaisen sopimuksen mukaan

Powerappsin sovellus sopimuksen mukaan yksittäiset käyttäjät voivat suorittaa kaksi sovellusta yksittäisessä portaalissa tietyssä liiketoiminta skenaariossa Powerappsin kaikkien toimintojen avulla. Tämä sopimus tarjoaa helpon tavan, jolla käyttäjät pääsevät aloittamaan käyttö ympäristön ennen laajemman asteikon käyttöönottoa.

Kun järjestelmänvalvoja on varannut Powerappsin sovellus suunnitelmaan, se määritetään käyttäjille oletusarvoisesti, kun sovellus jaetaan heidän kanssaan.

Noudata seuraavia vaiheita, jos haluat poistaa käytöstä sovelluskohtaisesti määrittämisen käyttäjien osalta, kun sovellus jaetaan heidän kanssaan:

- Valitse **sovellus**.
- Valitse **Asetukset**.
- Vaihda **Automaattinen määritys per sovellus läpäisee** -vaihto kohdan **Siirrä määritys**-kohdassa.

**Automaattinen määritys per sovellus kulkee** -vaihto painike näkyy kaikissa sovellus asetuksissa.

> [!NOTE]
> Sovelluskohtaisen sopimuksen poistaminen käytöstä on tällä hetkellä käytettävissä vain pohjaan asennettavissa sovelluksissa.  Mallipohjaiset sovellukset ja portaalit pystyvät jatkossa käyttämään tätä mahdollisuutta.

### <a name="app-settings"></a>Sovelluksen asetukset

![Kangas sovelluksen asetukset](./media/limits-and-config/app_settings.png "Kangas sovelluksen asetukset")

### <a name="pass-assignment"></a>Välitä varaus

![Pohjaan-sovelluksen asetusten läpäisy määritykset](./media/limits-and-config/app_settings_pass_assignment.png "Pohjaan-sovelluksen asetusten läpäisy määritykset")

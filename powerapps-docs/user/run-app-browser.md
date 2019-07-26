---
title: Sovelluksien suorittaminen selaimessa | Microsoft Docs
description: Tässä ohjeaiheessa opimme suorittamaan sovelluksia selaimessa
author: Mattp123
ms.service: powerapps
ms.component: pa-user
ms.topic: quickstart
ms.date: 11/16/2018
ms.author: matp
manager: kvivek
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 31bef01ef46fd0fe2ed7bae30e63d53c169812db
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/19/2019
ms.locfileid: "63321591"
---
# <a name="run-an-app-in-a-web-browser"></a>Sovelluksen suorittaminen selaimessa
Kun luot sovelluksen tai joku jakaa sovelluksen kanssasi, voit suorittaa sovelluksen Windows-, iOS- tai Android-laitteessa tai verkkoselaimessa. Tässä ohjeaiheessa opimme suorittamaan pohjaan perustuvan tai mallipohjaisen sovelluksen verkkoselaimessa [Dynamics 365 -aloitussivulta](https://home.dynamics.com).

Tarvitset tämän pikaoppaan seuraamisessa seuraavat:
- PowerApps-käyttöoikeus. Tämä on saatavissa PowerApps-palvelupaketissa, kuten [PowerApps-palvelupaketin 2 kokeiluversiossa](https://docs.microsoft.com/powerapps/maker/signup-for-powerapps) tai missä tahansa [Microsoft Office 365](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1)- tai [Dynamics 365](https://dynamics.microsoft.com/pricing/) -palvelupaketissa, joka sisältää PowerAppsin. 
- Käyttöoikeus luomaasi tai jonkun muun luomaan ja kanssasi jakamaan sovellukseen.
- Käyttöoikeus tuettuun selaimeen ja käyttöjärjestelmään.
   - Jos kyseessä on kangas sovellus, lue: [Järjestelmä vaatimukset, rajoitukset ja määritys arvot](../maker/canvas-apps/limits-and-config.md)
   - Mallipohjaisilla sovelluksilla on lisä tietoja: [Tuetut selaimet ja mobiililaitteet](https://docs.microsoft.com/dynamics365/customer-engagement/admin/supported-web-browsers-and-mobile-devices)


## <a name="sign-in-to-dynamics-365"></a>Kirjaudu Dynamics 365:een
Kirjaudu Dynamics 365:een osoitteessa [https://home.dynamics.com](https://home.dynamics.com).

## <a name="find-an-app-on-the-home-page"></a>Sovelluksen etsiminen aloitussivulta
Aloitussivulla voi olla useita yrityssovelluksia. Voit etsiä tietyn sovelluksen kirjoittamalla osan sen nimestä hakuruutuun. Voit myös suodattaa luetteloa ja näyttää vain tietyn lähteen luomat sovellukset, kuten PowerAppsin. Tee tämä napsauttamalla tai napauttamalla **Suodatin** ja valitsemalla sitten lähteen.

Jos olet asentanut sovelluksen äskettäin, se ei ehkä heti näy sovellusluettelossa. Näytä kaikki sovellukset napsauttamalla tai napauttamalla **Synkronoi**. Tämä prosessi saattaa kestää jopa minuutin.

![](./media/run-app-browser/dynamics-365-home.png)

## <a name="run-an-app-from-the-task-pane"></a>Sovelluksen suorittaminen tehtäväruudusta
Kun löydät sovelluksen, voit kiinnittää sen tehtäväruutuun, jolloin sitä on helpompi käyttää. Kiinnitä sovellus napsauttamalla tai napauttamalla sovelluksen ruudussa (...), ja napsauta tai napauta sitten **Kiinnitä sovellus**.

![](./media/run-app-browser/homepage-pin.png)

Suorita kiinnitetty sovellus tehtäväruudusta napsauttamalla tai napauttamalla vasemmassa yläkulmassa **Dynamics 365**, etsi sovellus kohdasta **Omat sovellukset** ja napsauta tai napauta sitä.

![](./media/run-app-browser/taskpane.png)

## <a name="run-an-app-from-a-url"></a>Sovelluksen suorittaminen URL-osoitteesta
Voit tallentaa sovelluksen URL-osoitteen kirjanmerkiksi selaimeen ja suorittaa sen valitsemalla kirjanmerkin tai voit lähettää URL-osoitteen linkkinä sähköpostitse. Jos joku muu loi sovelluksen ja jakoi sen sähköpostitse, voit suorittaa sovelluksen napsauttamalla tai napauttamalla sähköpostiviestissä olevaa linkkiä. Kun suoritat sovelluksen URL-osoitteen kautta, sinua saatetaan kehottaa kirjautumaan Azure Active Directory -tunnistetiedoilla.

![](./media/run-app-browser/web-login.png)

## <a name="connect-to-data"></a>Yhdistä tietoihin
Jos sovellus vaatii yhteyden tietolähteeseen tai luvan käyttää laitteen ominaisuuksia (kuten kameraa tai sijaintipalveluja), sinun on annettava suostumus, ennen kuin voit käyttää sovellusta. Tavallisesti pyyntö esitetään vain ensimmäisellä kerralla.

![Yhteys](./media/run-app-browser/app-connection.png)

## <a name="close-an-app"></a>Sovelluksen sulkeminen
Sulje sovellus kirjautumalla ulos Dynamics 365 -aloitussivulta tai avaamalla toinen sovellus.

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä ohjeaiheessa opit suorittamaan pohjaan perustuvan tai mallipohjaisen sovelluksen verkkoselaimessa. Ohjeet:
- Suorita pohjaan perustuva sovellus mobiililaitteessa, Lue artikkeli [kangas sovelluksen suorittaminen mobiililaitteessa](run-app-client.md)
- Suorita mallipohjainen sovellus mobiililaitteessa, lisä tietoja on Ohje aiheessa [mallipohjaisen sovelluksen suorittaminen mobiililaitteessa](run-app-client-model-driven.md)
- Käytä mallipohjaista sovellusta, tutustu [malliin perustuvien sovellusten käyttämiseen](use-model-driven-apps.md)


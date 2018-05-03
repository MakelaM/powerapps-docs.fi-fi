---
title: PowerAppsin integroiminen verkkosivustoihin ja muihin palveluihin | Microsoft Docs
description: Upota sovelluksia sivustoihin ja muihin palveluihin.
documentationcenter: na
author: mgblythe
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/20/2017
ms.author: mblythe
ms.openlocfilehash: 0f4ea37d93b20a768fa16d1dcdb41f921336f043
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="integrate-powerapps-into-websites-and-other-services"></a>PowerAppsin integroiminen verkkosivustoihin ja muihin palveluihin
Luomasi sovellukset ovat usein hyödyllisimpiä, kun ne ovat käytettävissä siellä, missä ihmiset työskentelevät. PowerAppsin avulla voit upottaa sovelluksia iframe-kehykseen niin, että ne voi integroida verkkosivustoihin ja muihin palveluihin, kuten Power BI:hin tai SharePointiin.

Tässä ohjeaiheessa näytämme, miten määritetään parametrit sovelluksen upottamista varten. Sen jälkeen upotamme resurssien järjestelysovelluksemme verkkosivulle.

![Upotetun sovelluksen sisältävä Power BI -koontinäyttö](./media/embed-apps-dev/embed-dashboard.png)

Ota huomioon seuraavat rajoitukset:

* Vain saman vuokraajan PowerApps-käyttäjät voivat käyttää upotettua sovellusta.
* Jos käytät PowerAppsia Internet Explorer 11 -selaimella, sinun on poistettava yhteensopivuusnäkymä käytöstä.

Voit myös integroida PowerAppsin SharePoint Onlineen (käyttämättä iframe-kehystä). Lisää tietoa on kohdassa [Sovelluksen luominen SharePointin sisältä PowerAppsilla](../canvas-apps/generate-app-from-sharepoint-list-interface.md).

## <a name="set-uri-parameters-for-your-app"></a>Sovelluksen URI-parametrien määrittäminen
Jos haluat upottaa sovelluksen, ensimmäinen vaihe on määrittää parametrit Uniform Resource Identifierille (URI) niin, että iframe-kehys tietää, mistä sovellus löytyy. URI on seuraavassa muodossa:

```
https://web.powerapps.com/webplayer/iframeapp?source=iframe
&appId=/providers/Microsoft.PowerApps/apps/[AppID]
```

> [!NOTE]
> Olemme lisänneet rivinvaihdon, jotta URI-osoite näkyy sivulla paremmin.

Sinun tarvitsee ainoastaan korvata sovelluksesi tunnus URI:ssä syötteellä [sovellustunnus] (mukaan lukien sulkeet ”[” ja ”]”). Näytämme pian, miten saat tämän arvon, mutta tässä on ensin kaikki URI:tä varten tarvittavat parametrit:

* **[appID]** – On muodossa `/providers/Microsoft.PowerApps/apps/[AppID]`. Se antaa suorittamiseen vaadittavan sovellustunnuksen.
* **screenColor** – Tarjoaa käyttäjille paremman sovelluksen lataamiskokemuksen. Tämä parametri on muotoa [RGBA (punainen arvo, vihreä arvo, sininen arvo, alfa)](../canvas-apps/functions/function-colors.md) ja se määrää näytön värin sovelluksen latautumisen aikana. Se kannattaa määrittää sovelluksesi kuvakkeen väriseksi.
* **source** – Ei vaikuta sovellukseen, mutta suosittelemme lisäämään upotuksen lähteeseen viittaavan kuvaavan nimen.
* Lopuksi voit lisätä mitä tahansa mukautettuja parametreja käyttämällä [Param()-funktiota](../canvas-apps/functions/function-param.md), ja sovellus voi käyttää näitä arvoja. Ne lisätään URI:n loppuun, kuten `[AppID]&amp;param1=value1`. Nämä parametrit luetaan vain sovelluksen käynnistämisen aikana. Jos haluat muuttaa niitä, sinun on käynnistettävä sovellus uudelleen.

### <a name="get-the-app-id"></a>Sovellustunnuksen hankkiminen
Sovellustunnus on saatavilla powerapps.com-sivustolla. Sovellukselle, jonka haluat upottaa:

1. Napsauta tai napauta [powerapps.com](https://powerapps.microsoft.com)-sivuston **Sovellukset**-välilehdessä kolmea pistettä (**...** ) ja sen jälkeen kohtaa **Tiedot**.
   
    ![Siirry sovelluksen tietoihin](./media/embed-apps-dev/details.png)
2. Kopioi **Sovellustunnus**.
   
    ![Kopioi sovellustunnus tiedoista](./media/embed-apps-dev/app-id.png)
3. Korvaa arvo `[AppID]` URI:ssä. Resurssien järjestelysovelluksemme URI näyttää tältä:
   
    ```
    https://web.powerapps.com/webplayer/iframeapp?source=iframe&appId=/providers/Microsoft.PowerApps/apps/76897698-91a8-b2de-756e-fe2774f114f2
    ```

## <a name="embed-your-app-in-a-website"></a>Sovelluksen upottaminen sivustoon
Sovelluksen upottaminen on nyt yhtä helppoa kuin iframe-kehyksen lisääminen sivustosi HTML-koodiin (tai muuhun palveluun, joka tukee iframe-kehyksiä, kuten Power BI tai SharePoint):

```
<iframe width="[W]" height="[H]" src="https://web.powerapps.com/webplayer/iframeapp?source=website&screenColor=rgba(165,34,55,1)&appId=/providers/Microsoft.PowerApps/apps/[AppID]" allow="geolocation; microphone; camera"/>
```

Määritä arvot iframe-kehyksen leveydelle ja korkeudelle ja korvaa sovelluksesi tunnus kohteella `[AppID]`.

> [!NOTE]
> Sisällytä `allow="geolocation; microphone; camera"` iframe-kehyksen HTML-koodiin, jotta sovelluksesi voi käyttää näitä ominaisuuksia Google Chromessa.

Seuraavassa kuvassa näkyy resurssien järjestelysovellus upotettuna Contoson esimerkkisivustolle.

![Upotetun sovelluksen sisältävä Contoson verkkosivusto](./media/embed-apps-dev/contoso-website.png)

Ota sovelluksen käyttäjien todentamisessa huomioon seuraavat asiat:

* Jos sivustosi käyttää Azure Active Directory (AAD) -pohjaista todennusta, muuta kirjautumista ei vaadita.
* Jos verkkosivusi käyttää mitä tahansa muuta kirjautumismenetelmää tai siinä ei käytetä tunnistautumista, käyttäjäsi näkevät kirjautumiskehotteen iframe-kehyksessä. Sisäänkirjauduttuaan he voivat käyttää sovellusta, jos sovelluksen laatija on jakanut sen heidän kanssaan.

Kuten näet, sovellusten upottaminen on yksinkertaista ja tehokasta. Upottamisen avulla voit tuoda sovelluksia juuri sinne, missä sinä ja asiakkaasi työskentelevät: Power BI -koontinäyttöihin, SharePoint-sivuille ja moniin muihin kohteisiin.


---
title: Pohjaan perustuvien sovellusten integroiminen verkkosivustoihin ja muihin palveluihin | Microsoft Docs
description: Upota pohjaan perustuvia sovelluksia sivustoihin ja muihin palveluihin.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 08/28/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ac4699818c7f5b3a136db122fad9621d865bf5f1
ms.sourcegitcommit: f296922b8039b573e5adb81423a544f70c56c1ee
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/25/2019
ms.locfileid: "71256100"
---
# <a name="integrate-canvas-apps-into-websites-and-other-services"></a>Pohjaan perustuvien sovellusten integroiminen verkkosivustoihin ja muihin palveluihin
Rakentamasi sovellukset ovat usein hyödyllisiä, kun ne ovat käytettävissä, kun käyttäjät tekevät työtään. Upottamalla pohjaan sovelluksia iframe-muodossa voit integroida kyseiset sovellukset verkko sivustoihin ja muihin palveluihin, kuten Power BI tai SharePointiin.

Tässä ohjeaiheessa näytämme, miten määritetään parametrit sovelluksen upottamista varten. Sen jälkeen upotamme verkkosivulle resurssien järjestelysovelluksemme.

![Power BI -koontinäyttö, joka sisältää upotetun sovelluksen](./media/embed-apps-dev/embed-dashboard.png)

Ota huomioon seuraavat rajoitukset:

- Vain saman vuokraajan PowerApps-käyttäjät voivat käyttää upotettua sovellusta.
- Jos käytät PowerAppsia Internet Explorer 11 -selaimella, sinun on poistettava yhteensopivuusnäkymä käytöstä.

Voit myös integroida Canvas-sovelluksia SharePoint Onlineen ilman iframe-toimintoa. Lisätietoja: [Käytä PowerApps-verkko-osaa](https://support.office.com/article/use-the-powerapps-web-part-6285f05e-e441-408a-99d7-aa688195cd1c).

## <a name="set-uri-parameters-for-your-app"></a>Sovelluksen URI-parametrien määrittäminen
Jos haluat upottaa sovelluksen, ensimmäinen vaihe on määrittää parametrit Uniform Resource Identifierille (URI) niin, että iframe-kehys tietää, mistä sovellus löytyy. URI on seuraavassa muodossa:

```
https://apps.powerapps.com/play/[AppID]?source=iframe
```

> [!IMPORTANT]
> Elokuun 2019 alkaen URI-muoto on muuttunut- https://web.powerapps.com/webplayer https://apps.powerapps.com/play kohteesta. Päivitä upotettuja iframe-muotoja käyttämään uutta URI-muotoa. Viitta ukset edelliseen muotoiluun ohjataan uuteen URI-osoitteeseen yhteensopivuuden varmistamiseksi.
>
> Edellinen muoto:
> 
> https\://Web.powerapps.com/webplayer/iframeapp? Source = iframe & AppID =/Providers/Microsoft.powerapps/apps/[AppID]

Sinun tarvitsee ainoastaan korvata sovelluksesi tunnus URI:ssä syötteellä [sovellustunnus] (mukaan lukien sulkeet ”[” ja ”]”). Näytämme pian, miten saat tämän arvon, mutta tässä on ensin kaikki URI:tä varten tarvittavat parametrit:

* **[AppID]** – se antaa suoritettavana olevan sovelluksen tunnuksen.
* **tenantid** – on valinnainen parametri, joka tukee vieraan käyttöä ja määrittää, mistä vuokraajasta sovellus avataan. 
* **screenColor** – Tarjoaa käyttäjille paremman sovelluksen lataamiskokemuksen. Tämä parametri on muotoa [RGBA (punainen arvo, vihreä arvo, sininen arvo, alfa)](../canvas-apps/functions/function-colors.md) ja se määrää näytön värin sovelluksen latautumisen aikana. Se kannattaa määrittää sovelluksesi kuvakkeen väriseksi.
* **source** – Ei vaikuta sovellukseen, mutta suosittelemme lisäämään upotuksen lähteeseen viittaavan kuvaavan nimen.
* Lopuksi voit lisätä mitä tahansa mukautettuja parametreja käyttämällä [Param()-funktiota](../canvas-apps/functions/function-param.md), ja sovellus voi käyttää näitä arvoja. Ne lisätään URI:n loppuun, kuten `[AppID]&amp;param1=value1`. Nämä parametrit luetaan vain sovelluksen käynnistämisen yhteydessä. Jos sinun on muutettava niitä, sinun on käynnistettävä sovellus uudelleen. Huomioi, että vain ensimmäisellä kohteen [AppID] jälkeen tulee olla?. sen jälkeen käytä "&" tässä kuvatulla tavalla. 

### <a name="get-the-app-id"></a>Sovellustunnuksen hankkiminen
Sovellustunnus on saatavilla powerapps.com-sivustolla. Sovellukselle, jonka haluat upottaa:

1. Napsauta tai napauta [powerapps.com](https://powerapps.microsoft.com)-sivuston **Sovellukset**-välilehdessä kolmea pistettä ( **...** ) ja sen jälkeen kohtaa **Tiedot**.
   
    ![Siirry sovelluksen tietoihin](./media/embed-apps-dev/details.png)
1. Kopioi **Sovellustunnus**.
   
    ![Kopioi sovellustunnus tiedoista](./media/embed-apps-dev/app-id.png)
1. Korvaa arvo `[AppID]` URI:ssä. Resurssien järjestelysovelluksemme URI näyttää tältä:
   
    ```
    https://apps.powerapps.com/play/76897698-91a8-b2de-756e-fe2774f114f2?source=iframe
    ```

## <a name="embed-your-app-in-a-website"></a>Sovelluksen upottaminen sivustoon
Sovelluksen upottaminen on nyt yhtä helppoa kuin iframe-kehyksen lisääminen sivustosi HTML-koodiin (tai muuhun palveluun, joka tukee iframe-kehyksiä, kuten Power BI tai SharePoint):

```html
<iframe width="[W]" height="[H]" src="https://apps.powerapps.com/play/[AppID]?source=website&screenColor=rgba(165,34,55,1)" allow="geolocation; microphone; camera"/>
```

Määritä arvot iframe-kehyksen leveydelle ja korkeudelle ja korvaa sovelluksesi tunnus kohteella `[AppID]`.

> [!NOTE]
> Sisällytä `allow="geolocation; microphone; camera"` iframe-kehyksen HTML-koodiin, jotta sovelluksesi voi käyttää näitä ominaisuuksia Google Chromessa.

Seuraavassa kuvassa näkyy resurssien järjestelysovellus upotettuna Contoson esimerkkisivustolle.

![Upotetun sovelluksen sisältävä Contoson verkkosivusto](./media/embed-apps-dev/contoso-website.png)

Ota sovelluksen käyttäjien todentamisessa huomioon seuraavat asiat:

- Jos sivustosi käyttää Azure Active Directory (AAD) -pohjaista todennusta, muuta kirjautumista ei vaadita.
- Jos verkkosivusi käyttää mitä tahansa muuta kirjautumismenetelmää tai siinä ei käytetä tunnistautumista, käyttäjäsi näkevät kirjautumiskehotteen iframe-kehyksessä. Sisäänkirjauduttuaan he voivat käyttää sovellusta, jos sovelluksen laatija on jakanut sen heidän kanssaan.

Kuten näet, sovellusten upottaminen on yksinkertaista ja tehokasta. Upottamisen avulla voit tuoda sovelluksia juuri sinne, missä sinä ja asiakkaasi työskentelevät: Power BI -koontinäyttöihin, SharePoint-sivuille ja moniin muihin kohteisiin.

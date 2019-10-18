---
title: PowerApps Component Framework-yleiskatsaus | Microsoft Docs
description: Powerappsin komponentti kehyksen avulla voit luoda koodi komponentteja, joiden avulla käyttäjät voivat tarkastella ja käsitellä tietoja lomakkeissa, näkymissä ja koonti näytöissä.
keywords: Komponentti kehys, koodi komponentit, PowerApps-ohjaus objekti
author: nkrb
manager: kvivek
ms.date: 09/05/2019
ms.service: powerapps
ms.custom:
- dyn365-a11y
- dyn365-developer
ms.topic: article
ms.assetid: 7923e36d-3640-49f7-9f2f-c97358a632db
ms.author: nabuthuk
ms.openlocfilehash: dede052df8e760748da3dae6cfab645b071b21d7
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72345792"
---
# <a name="powerapps-component-framework-overview"></a>PowerApps Component Frameworkin yleiskatsaus

PowerApps Component Frameworkin avulla voit luoda koodi komponentteja mallipohjaisia sovelluksia ja pohjaan perustuvia sovelluksia varten (kokeellinen esikatselu), jotta käyttäjät voivat tarkastella ja käsitellä lomakkeiden, näkymien ja koonti näyttöjen tietoja entistä paremmin. Esimerkki:

- Korvaa kenttä, joka näyttää numealimuotoisen teksti arvon `dial`-tai `slider`-komponentin avulla.
- Muunna lista kokonaan eri visuaaliseen kokemukseen, joka on sidottu tieto joukkoon, kuten `Calendar` tai `Map`.

> [!IMPORTANT]
> - Powerappsin komponentti kehys on kokeellinen esikatselu kangas sovelluksille ja GA malliin perustuvien sovellusten osalta. Tämä merkitsee sitä, että kaikki mallipohjaisten sovellusten tukemat ohjelmointi raja pinnat eivät ehkä vielä tue pohjaan perustuvissa sovelluksissa.
> - Oletus arvon mukaan PowerApps Component Framework on otettu käyttöön mallipohjaisia sovelluksia varten. Jos haluat ottaa tämän ominaisuuden käyttöön [kangas sovelluksille, Tutustu pohjaan](component-framework-for-canvas-apps.md).
> - [!INCLUDE[cc_preview_features_definition](../../includes/cc-preview-features-definition.md)]
> - Kangas sovellukset tukevat vain koodi komponenttien *kenttä* tyyppiä, eivät tieto *joukon* tyyppiä.


PowerApps Component Frameworkin avulla ammattimaiset kehittäjät ja sovellusten tekijät voivat luoda koodi komponentteja, joita voidaan käyttää PowerApps-toimintojen koko laajuudessaan. Toisin kuin HTML-verkko resurssit, koodi komponentit hahmonnetaan osana samaa kontekstia ja latautuvat samalla tavalla kuin muutkin komponentit. Tämä tarjoaa käyttäjille saumattoman käyttö kokemuksen. Kehittäjät voivat niputtaa kaikki HTML-, CSS-ja TypeScript-tai JavaScript-tiedostot yhdeksi ratkaisun paketti tiedostoksi. Koodi komponentteja voi käyttää uudelleen moneen kertaan eri entiteetteihin ja lomakkeisiin.

Koodi komponenteilla on pääsy monipuolisiin Framework-ohjelmointi raja pintoihin, jotka paljastavat ominaisuuksia, kuten komponenttien elin kaaren hallinta, tilannekohtaiset tiedot ja metatietojen käyttö, saumaton palvelin käyttö verkon ohjelmointi raja pinnan avulla, apuohjelman ja tietojen muotoilu menetelmät, laite ominaisuudet, kuten kamera, sijainti ja mikrofoni yhdessä helposti käynnistettävän UX-elementin, kuten dialogien, hakujen ja koko sivun hahmontamisen, kanssa.  


Kehittäjät ja sovellusten tekijät voivat käyttää nykyaikaisia verkko käytäntöjä ja hyödyntää myös ulkoisten kirjastojen tehoa ja luoda näin edistyksellistä käyttäjä viestintää. Kehys käsittelee automaattisesti komponentin elin kaaren, säilyttää sovelluksen liiketoiminta logiikan ja optimoi suoritus kyky (ei enempää asynkronisia iframe-iframeja). Osan määritys, riippuvuudet ja määritykset voidaan pakata [ratkaisuun](https://docs.microsoft.com/dynamics365/customer-engagement/customize/solutions-overview) ja siirtää eri ympäristöihin, ja ne voidaan lähettää [appsourcen](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=dynamics-365)kautta.  

## <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Mitä ovat koodi komponentit](custom-controls-overview.md)<br/>
[Kangas sovellusten saatavuus](component-framework-for-canvas-apps.md)<br/>
[Luo ja Rakenna koodi komponentti](create-custom-controls-using-pcf.md)<br/>
[PowerApps kehittäjille](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer)


---
title: 'Tekstimuotoilueditorin ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja, kuten ominaisuudet ja esimerkkejä, tekstimuotoilueditorin ohjausobjektista
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/24/2018
ms.author: fikaradz
ms.openlocfilehash: 36fa317a4611c72ab4d2f6ce09e176b14b688a55
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34585081"
---
# <a name="rich-text-editor-control-experimental-in-powerapps"></a>Tekstimuotoilueditorin ohjausobjekti (kokeellinen) PowerAppsissa
Kokeellinen ohjausobjekti, jonka avulla käyttäjät voivat muotoilla tekstiä WYSIWYG-muokkausalueen sisällä.  Tulostemuoto on HTML.

## <a name="description"></a>Kuvaus
**Tekstimuotoilueditori**-ohjausobjekti tarjoaa sovelluksen käyttäjälle WYSIWYG-muokkausalueen tekstin muotoilemista varten.  Ohjausobjektin syöte- ja tulostemuoto on HTML.

Ohjausobjektin avulla kopioitu muotoiltu teksti (eli selaimesta tai Wordista peräisin oleva) voidaan liittää ohjausobjektiin.  

Ohjausobjektin käyttötarkoitus on muotoilla tekstiä, eikä syöte-HTML:n eheyden säilymistä taata.  Editori poistaa kaikki komentosarjat, tyylit, objektit ja muut mahdollisesti vaarantavat tunnisteet.  Tämä tarkoittaa sitä, että jos muotoiltu teksti luotiin muualla kuin PowerAppsissa, se ei välttämättä näytä samalta kuin tuotteessa, jossa se luotiin.

Tällä hetkellä tuettuja ominaisuuksia ovat muun muassa seuraavat:
- Lihavointi, kursivointi, alleviivaus
- Tekstin väri, korostusväri
- Tekstin koko
- Numeroidut luettelot, luettelomerkeillä varustetut luettelot
- Hyperlinkit
- Muotoilun poistaminen

Jos haluat käyttää ohjausobjektia lomakkeen sisällä, valitse Muokkaa monirivistä tekstiä -kortti ja mukauta sitä lisäämällä RTE-ohjausobjekti.

## <a name="limitations"></a>Rajoitukset
Ohjausobjektin nykyinen versio on kokeellinen seuraavien tilapäisten rajoitusten vuoksi:
- Ohjausobjektilla on rajoitetut tekstinmuotoiluominaisuudet.  

- Ohjausobjekti on ensisijaisesti tarkoitettu käytettäväksi selaimissa suurilla näytöillä.  Ohjausobjektin käyttäminen matkapuhelimella voi olla turhauttava kokemus.

- Tunnettuja ongelmia luomisessa, kun käytetään Windows Studiota tai Edge-selainta.  Nykyinen suositus on käyttää Web Studiota Chromessa.


## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Oletus](properties-core.md)** – Editorissa näkyvän ensimmäisen tekstiarvon syöteominaisuus.

**HtmlText** – Tuloksena saatavan HTML-muodossa olevan tekstin tulosteominaisuus.



## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi. Tulee kuvata liitteiden käyttötarkoituksen.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus pois käytöstä (**Ei käytössä**).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvä vai piilotettu.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

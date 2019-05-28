---
title: And-, Or- ja Not-funktiot | Microsoft Docs
description: PowerAppsin And-, Or- ja Not-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4eb020d854549b6dc8878f07ae26390523a1bc03
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/24/2019
ms.locfileid: "66215970"
ms.PowerAppsDecimalTransform: true
---
# <a name="and-or-and-not-functions-in-powerapps"></a>PowerAppsin And-, Or- ja Not-funktiot

Totuusarvon logiikkafunktiot, joita käytetään yleensä muokkaamaan vertailujen tuloksia ja testauksia.

## <a name="description"></a>Kuvaus

**And**-funktio palauttaa arvon **tosi**, jos kaikilla sen argumenteilla on arvo **tosi**.

**Or** funktio palauttaa arvon **tosi**, jos millä tahansa sen argumentilla on arvo **tosi**.

**Not**-funktio palauttaa arvon **tosi**, jos sen argumentilla on arvo **epätosi**. Se palauttaa arvon **epätosi**, jos sen argumentilla on arvo **tosi**.

Nämä funktiot toimivat samalla tavalla kuin Excelissä. Voit myös käyttää [operaattorit](operators.md) saman näitä toimintoja, Visual Basic tai JavaScriptiä syntaksin:

| Funktio merkintätapaa | Visual Basic-operaattoria merkintätapaa | JavaScript-operaattoria merkintätapaa |
| -------------|------------|--------|
| **And( x; y )** | **x ja y** | **x & & y** |
| **Tai (x, y)** | **x- tai y** | **x &#124; &#124; y** |
| **Ei (x)** | **Ei x** | **! x** |

Nämä funktiot toimivat loogisten arvojen kanssa. Et voi välittää ne luku tai merkkijono suoraan. sen sijaan sinun on tehtävä vertailu tai testi. Esimerkiksi tämä looginen kaava **x > 1** laskee totuusarvon **true** Jos **x** on suurempi kuin **1**. Jos **x** on pienempi kuin **1**, kaavan tulos **false**.

## <a name="syntax"></a>Syntaksi

**And**( *LogicalFormula1*; *LogicalFormula2* [; *LogicalFormula3*; ... ] )<br>
**Or**( *LogicalFormula1*; *LogicalFormula2* [; *LogicalFormula3*; ... ] )<br>
**Not**( *LogicalFormula* )

- *LogicalFormula(s)* – Pakollinen.  Loogiset kaavat, jotka arvioidaan ja joille toiminto suoritetaan.

## <a name="examples"></a>Esimerkkejä

Tämän osion esimerkeissä käytetään näitä yleisiä muuttujia:

- **a** = *false*
- **b** = *true*
- **x** = 10
- **y** = 100
- **s** = ”Hei maailma”

Jos haluat luoda sovelluksen näitä yleisiä muuttujia, Lisää [ **painike** ](../controls/control-button.md) ohjausobjekti ja määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava:

```powerapps-comma
Set( a; false );; Set( b; true );; Set( x; 10 );; Set( y; 100 );; Set( s; "Hello World" )
```

Valitse painike (valitsemalla sen samalla, kun pitämällä Alt-näppäintä) ja Aseta **tekstin** ominaisuus [ **nimen** ](../controls/control-text-box.md) ominaisuudeksi seuraavan taulukon ensimmäisen sarakkeen kaava.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Ja (a, b)** | Testaa arvot **a** ja **b**.  Yksi argumentti on *false*, joten funktio palauttaa *false*. | *epätosi* |
| **Ja b** | Sama kuin edellisessä esimerkissä käyttää Visual Basic-merkintätapaa. | *epätosi* |
| **& & b** | Sama kuin edellisessä esimerkissä käyttää JavaScript-merkintätapaa. | *epätosi* |
| **Tai a, b** | Testaa arvot **a** ja **b**. Yksi argumentti on *true*, joten funktio palauttaa *true*. | *tosi* |
| **Tai b** | Sama kuin edellisessä esimerkissä käyttää Visual Basic-merkintätapaa. | *tosi* |
| **&#124; &#124; b** | Sama kuin edellisessä esimerkissä käyttää JavaScript-merkintätapaa. | *tosi* |
| **Ei (a)** | Testaa arvo **a**. Argumentti on *false*, joten funktio palauttaa vastakkaisen tuloksen. | *tosi* |
| **Ei** | Sama kuin edellisessä esimerkissä käyttää Visual Basic-merkintätapaa. | *tosi* |
| **! on** | Sama kuin edellisessä esimerkissä käyttää JavaScript-merkintätapaa. | *tosi* |
| **Len (&nbsp;s&nbsp;)&nbsp;<&nbsp;20 ja&nbsp;ei&nbsp;IsBlank (&nbsp;s&nbsp;)** | Testaa, pituus **s** on pienempi kuin 20 ja onko se ei ole **tyhjä** arvo. Pituus on pienempi kuin 20 ja arvo ei ole tyhjä. Tämän vuoksi tulos on *true*. | *tosi* |
| **Tai (&nbsp;Len (&nbsp;s&nbsp;)&nbsp;<&nbsp;10, x&nbsp;<&nbsp;100 y&nbsp;<&nbsp;100&nbsp;)** | Testaa, pituus **s** on alle 10, onko **x** on pienempi kuin 100, ja onko **y** on pienempi kuin 100. Ensimmäisen ja kolmannen argumentit ovat epätosia, mutta toinen on TOSI. Tämän vuoksi, funktio palauttaa *true*. | *tosi* |
| **Ei IsBlank (&nbsp;s&nbsp;)** | Testaa onko **s** on *tyhjä*, joka palauttaa *false*. **Ei** palauttaa tämä tulos, joka on vastakohta *true*. | *tosi* |
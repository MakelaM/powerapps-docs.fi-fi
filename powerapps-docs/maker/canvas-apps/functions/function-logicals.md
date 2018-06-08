---
title: And-, Or- ja Not-funktiot | Microsoft Docs
description: PowerAppsin And-, Or- ja Not-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: a2e62ef2aa0a52bde33ea3e40faf96889597b09b
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825897"
---
# <a name="and-or-and-not-functions-in-powerapps"></a>PowerAppsin And-, Or- ja Not-funktiot
Totuusarvon logiikkafunktiot, joita käytetään yleensä muokkaamaan vertailujen tuloksia ja testauksia.

## <a name="description"></a>Kuvaus
**And**-funktio palauttaa arvon **tosi**, jos kaikilla sen argumenteilla on arvo **tosi**.  **&&**[-operaattori](operators.md) vastaa **And**-funktiota.

**Or** funktio palauttaa arvon **tosi**, jos millä tahansa sen argumentilla on arvo **tosi**.  **||**-operaattori vastaa **Or**-funktiota.

**Not**-funktio palauttaa arvon **tosi**, jos sen argumentilla on arvo **epätosi**. Se palauttaa arvon **epätosi**, jos sen argumentilla on arvo **tosi**.  **!** -operaattori vastaa **Not**-funktiota.

Nämä funktiot toimivat loogisten arvojen kanssa. Niille ei voida suoraan välittää numeroa tai merkkijonoa. Sen sijaan täytyy suorittaa vertaus tai testaus. Esimerkiksi vertailu **x > 1** on looginen kaava, joka saa totuusarvon **tosi**, jos **x** on suurempi kuin **1**. Jos **x** on pienempi kuin **1**, kaava saa arvon **epätosi**.

## <a name="syntax"></a>Syntaksi
**And**( *LooginenKaava1*, *LooginenKaava2* [, *LooginenKaava3*, ... ] )<br>
**Or**( *LooginenKaava1*, *LooginenKaava2* [, *LooginenKaava3*, ... ] )<br>
**Not**( *LooginenKaava* )

* *LooginenKaava* – Pakollinen.  Loogiset kaavat, jotka arvioidaan ja joille toiminto suoritetaan.

## <a name="examples"></a>Esimerkkejä
### <a name="step-by-step"></a>Vaihe vaiheelta
Käytä tätä funktiota määrittämään, onko liukusäätimen arvo välin 50–100 ulkopuolella:

**Or(Slider1.Value < 50, Slider1.Value> 100)**

Jos [taulukko](../working-with-tables.md) sisältää [sarakkeet](../working-with-tables.md#columns) **Osasto** ja **Palkka**, voit käyttää tätä funktiota **Tulos**-sarakkeessa näyttämään arvon **tosi** kaikilla riveillä, joissa **Osasto**-sarakkeen arvo on **HR** tai **Palkka**-sarakkeen arvo on suurempi kuin **200 000**:

**Or(Osasto = HR, Palkka >= 200000)**

Voit vaihtoehtoisesti käyttää ||-operaattoria saman tuloksen saamiseksi kuin edelliset kaavat:

**Slider1.Value < 50 || Slider1.Value> 100**

**Osasto = "HR" || Palkka > 200000**


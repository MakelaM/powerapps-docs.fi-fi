---
title: And-, Or- ja Not-funktiot | Microsoft Docs
description: PowerAppsin And-, Or- ja Not-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: ff908d29efa02a3ebed2b2fa5517da35322518b8
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
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

Jos [taulukko](../working-with-tables.md) sisältää [sarakkeet](../working-with-tables.md#columns) **Osasto** ja **Palkka**, voit käyttää tätä funktiota **Tulos**-sarakkeessa näyttämään arvo **tosi** kaikilla riveillä, joissa **Osasto**-sarakkeen arvo on **HR** tai **Palkka**-sarakkeen arvo on suurempi kuin **200 000**:

**Or(Osasto = HR, Palkka >= 200000)**

Voit vaihtoehtoisesti käyttää ||-operaattoria saman tuloksen saamiseksi kuin edelliset kaavat:

**Slider1.Value < 50 || Slider1.Value> 100**

**Osasto = "HR" || Palkka > 200000**


---
title: HashTags-funktio | Microsoft Docs
description: PowerAppsin HashTags-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.openlocfilehash: ebeecf7ae429f9e18c1b41b7c0f0ddd7da5be07c
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31826203"
---
# <a name="hashtags-function-in-powerapps"></a>PowerAppsin HashTags-funktio
Poimii aihetunnisteet (#merkkijonot) merkkijonosta.

## <a name="description"></a>Kuvaus
**HashTags**-funktio etsii merkkijonosta aihetunnisteet. Aihetunnisteet alkavat risuaitamerkillä (#), jonka jälkeen voi olla mikä tahansa yhdistelmä:

* isoja ja pieniä kirjaimia
* numeroja
* alaviivoja
* valuuttasymboleita (kuten $)

**HashTags** palauttaa yhden sarakkeen [taulukon](../working-with-tables.md), joka sisältää merkkijonon aihetunnisteet.  Jos merkkijono ei sisällä aihetunnisteita, funktio palauttaa yhden sarakkeen [tyhjän](function-isblank-isempty.md) taulukon.

## <a name="syntax"></a>Syntaksi
**HashTags**( *Merkkijono* )

* *Merkkijono* – pakollinen.  Merkkijono, josta etsitään aihetunnisteet.

## <a name="examples"></a>Esimerkkejä
### <a name="step-by-step"></a>Vaihe vaiheelta
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti, anna sille nimeksi **Twiitti** ja kirjoita siihen tämä lause:
   
    **Tämä #sovellus on #HUIKEA ja se voi #laskea123 tai #123abc mutta ei #1-23 tai #$\*(#@")**
2. Lisää pystysuuntainen mukautettu valikoima ja aseta sen **[Items](../controls/properties-core.md)**-ominaisuudeksi tämä funktio:
   
    **HashTags(Tweet.Text)**
3. Lisää valikoiman mallipohjaan **[selite](../controls/control-text-box.md)**-ohjausobjekti.
   
    Valikoima näyttää nämä aihetunnisteet:
   
   * **\#sovellus**
   * **\#HUIKEA**
   * **\#laskea123**
   * **\#123abc**
   * **\#1**


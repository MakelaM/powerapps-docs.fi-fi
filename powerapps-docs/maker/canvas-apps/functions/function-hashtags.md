---
title: HashTags-funktio | Microsoft Docs
description: PowerAppsin HashTags-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.openlocfilehash: b2f79c55724d9dc0bc9cfaf9e2e462c646cddb85
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
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

* *Merkkijono* – Pakollinen.  Merkkijono, josta etsitään aihetunnisteet.

## <a name="examples"></a>Esimerkkejä
### <a name="step-by-step"></a>Vaihe vaiheelta
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti, anna sille nimeksi **Twiitti** ja kirjoita siihen tämä lause:
   
    **Tämä #sovellus on #HUIKEA ja se voi #laskea123 tai #123abc mutta ei #1-23 tai #$\*(#@")**
2. Lisää pystysuora mukautettu valikoima ja aseta sen **[Items](../controls/properties-core.md)**-ominaisuudeksi tämä funktio:
   
    **HashTags(Twiitti.Text)**
3. Lisää valikoiman mallipohjaan **[Otsikko](../controls/control-text-box.md)**-ohjausobjekti.
   
    Valikoima näyttää nämä aihetunnisteet:
   
   * **\#sovellus**
   * **\#HUIKEA**
   * **\#laskea123**
   * **\#123abc**
   * **\#1**


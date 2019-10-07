---
title: HashTags-funktio | Microsoft Docs
description: PowerAppsin HashTags-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d29fa336ae96a164a6f189010c66deff970ba5a7
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984911"
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

* *String* – Pakollinen.  Merkkijono, josta etsitään aihetunnisteet.

## <a name="examples"></a>Esimerkkejä
### <a name="step-by-step"></a>Vaihe vaiheelta
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)** -ohjausobjekti, anna sille nimeksi **Twiitti** ja kirjoita siihen tämä lause:
   
    **Tämä #sovellus on #HUIKEA ja se voi #laskea123 tai #123abc mutta ei #1-23 tai #$\*(#\@")**
2. Lisää pystysuuntainen mukautettu valikoima ja aseta sen **[Items](../controls/properties-core.md)** -ominaisuudeksi tämä funktio:
   
    **HashTags(Tweet.Text)**
3. Lisää valikoiman mallipohjaan **[selite](../controls/control-text-box.md)** -ohjausobjekti.
   
    Valikoima näyttää nämä aihetunnisteet:
   
   * **\#sovellus**
   * **\#HUIKEA**
   * **\#laskea123**
   * **\#123abc**
   * **\#1**


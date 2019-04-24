---
title: HashTags-funktio | Microsoft Docs
description: PowerAppsin HashTags-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 16226203262d5ecacc8fc49a88c9934dd0f673e6
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61562872"
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
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti, anna sille nimeksi **Twiitti** ja kirjoita siihen tämä lause:
   
    **Tämä #sovellus on #HUIKEA ja se voi #laskea123 tai #123abc mutta ei #1-23 tai #$\*(#\@")**
2. Lisää pystysuuntainen mukautettu valikoima ja aseta sen **[Items](../controls/properties-core.md)**-ominaisuudeksi tämä funktio:
   
    **HashTags(Tweet.Text)**
3. Lisää valikoiman mallipohjaan **[selite](../controls/control-text-box.md)**-ohjausobjekti.
   
    Valikoima näyttää nämä aihetunnisteet:
   
   * **\#sovellus**
   * **\#HUIKEA**
   * **\#laskea123**
   * **\#123abc**
   * **\#1**


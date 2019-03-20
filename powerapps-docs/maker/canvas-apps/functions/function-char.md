---
title: Char-funktio | Microsoft Docs
description: Viitetietoja Char-funktiosta PowerAppsissa, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 03/01/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b7d29d883a14e34dd89d766a6aeffb17275bde6b
ms.sourcegitcommit: 825daacc9a812637815afc1ce6fad28f0cebd479
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/04/2019
ms.locfileid: "57803454"
---
# <a name="char-function-in-powerapps"></a>Char-funktio PowerAppsissa

Muuntaa merkkikoodin merkkijonoksi.

## <a name="description"></a>Kuvaus

**Char** funktio kääntää luvun merkkijonoksi vastaava ASCII-merkin.

## <a name="syntax"></a>Syntaksi

**Char**( *CharacterCode* )

- *CharacterCode* – pakollinen. ASCII-merkkikoodi, joka muunnetaan.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Char( 65 )** |Palauttaa merkin, joka vastaa ASCII-koodia 65. |"A" |
| **Char( 105 )** |Palauttaa merkin, joka vastaa ASCII-koodia 105. |”i” |
| **Char( 35 )** |Palauttaa merkin, joka vastaa ASCII-koodia 35. |"#" |

### <a name="display-a-character-map"></a>Kartan merkki

1. Lisää tyhjä näyttö tablettisovellus, [ **valikoiman** ](../controls/control-gallery.md) ohjausobjektin **tyhjä vaakasuuntainen** asettelu, ja määritä sitten nämä ominaisuudet:

    - **Kohteet**: `[0,1,2,3,4,5,6,7]`
    - **Leveys**: 800
    - **Korkeus**: 500
    - **TemplateSize**: 100
    - **TemplatePadding**: 0

1. Kyseisen valikoiman sisällä, Lisää **valikoiman** ohjausobjektin **tyhjä pystysuuntainen** asettelu, ja määritä sitten nämä ominaisuudet:

    - **Kohteet**: `ForAll( [0,2,3,4,5,6,7,8,9,10,11,12,13,14,15], Value + ThisItem.Value * 16 )`
    - **Leveys**: 100
    - **Korkeus**: 500
    - **TemplateSize**: 30
    - **TemplatePadding**: 0

    Arvo **kohteet** ominaisuuden kertoo annettu arvo-sarake sarakenumero 16 **kohteet** ominaisuuden ensimmäinen valikoiman (0 – 7 ThisItem.Value). Kaava Lisää sitten tuloksen jokin rivinumerot toinen valikoimasta (0 – 15 tietueen vaikutusalueen, joka [ **ForAll** ](function-forall.md) funktio tarjoaa).

1. Toinen (pysty) valikoiman sisällä, Lisää **nimen** ohjausobjekti ja määritä nämä ominaisuudet:

    - **Tekstin**: `ThisItem.Value`
    - **Leveys**: 50

1. Toinen (pysty) valikoiman sisällä, Lisää toinen **nimen** ohjausobjekti ja määritä nämä ominaisuudet:

    - **Tekstin**: `Char( ThisItem.Value )`
    - **Leveys**: 50
    - **X**: 50

Olet luonut kaavion ensin 128 ASCII-merkin. Merkkejä, jotka näkyvät kuin pieni neliön ei voi tulostaa.

![Ensin 128 ASCII-merkkiä](media/function-char/chart-lower.png)

Näyttää laajennettu ASCII-merkkejä **kohteet** ominaisuus toinen tämä kaava, joka lisää 128 merkkiä jokaisen arvon:

`ForAll( [0,2,3,4,5,6,7,8,9,10,11,12,13,14,15], Value + ThisItem.Value * 16 + 128)`

![Laajennetun ASCII-merkkejä](media/function-char/chart-higher.png)

Näytä merkit fontin määrittämällä **fontin** -ominaisuuden arvoksi, kuten selitettä **tanssin komentosarjan**.

![Tanssin komentosarja](media/function-char/chart-higher-dancing-script.png)
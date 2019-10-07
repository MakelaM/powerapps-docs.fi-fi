---
title: Char-funktio | Microsoft Docs
description: Viitetietoja Char-funktiosta PowerAppsissa, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/01/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 099afb1e89d1551c6c6b969c3ae3688a3cdec777
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992963"
---
# <a name="char-function-in-powerapps"></a>Char-funktio PowerAppsissa

Muuntaa merkkikoodin merkkijonoksi.

## <a name="description"></a>Kuvaus

**Char** -funktiolla käännetään numero merkki jonoksi, jolla on vastaava ASCII-merkki.

## <a name="syntax"></a>Syntaksi

**Char**( *CharacterCode* )

- *CharacterCode* – pakollinen. ASCII-merkkikoodi, joka muunnetaan.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Char( 65 )** |Palauttaa merkin, joka vastaa ASCII-koodia 65. |ON |
| **Char( 105 )** |Palauttaa merkin, joka vastaa ASCII-koodia 105. |Olen |
| **Char( 35 )** |Palauttaa merkin, joka vastaa ASCII-koodia 35. |"#" |

### <a name="display-a-character-map"></a>Näytä merkki kartta

1. Lisää Tablet-sovelluksen tyhjässä näytössä [**valikoima**](../controls/control-gallery.md) -ohjaus objekti, jossa on **tyhjä vaakasuuntainen** ulkoasu, ja määritä sitten nämä ominaisuudet:

    - **Kohteet**: `[0,1,2,3,4,5,6,7]`
    - **Leveys**: 800
    - **Korkeus**: 500
    - **Templatesize**: 100
    - **Templatepadding**: 0

1. Lisää tämän valikoiman sisällä **valikoima** -ohjaus objekti, jossa on **tyhjä pystysuuntainen** ulkoasu, ja määritä sitten nämä ominaisuudet:

    - **Kohteet**: `ForAll( [0,2,3,4,5,6,7,8,9,10,11,12,13,14,15], Value + ThisItem.Value * 16 )`
    - **Leveys**: 100
    - **Korkeus**: 500
    - **Templatesize**: 30
    - **Templatepadding**: 0

    **Items** -ominaisuuden arvo kertoo arvon 16 ensimmäisen valikoiman (0-7 `ThisItem.Value`) **Items** -ominaisuuden arvo-sarakkeen antamalla sarake numerolla. Kaava lisää sitten tuloksen yhteen rivi numeroista toisesta valikoimasta (0-15 tietue alueessa, jonka [**forall**](function-forall.md) -toiminto antaa).

1. Lisää toisen (pystysuuntaisen) valikoiman sisällä **Selite** -ohjaus objekti ja valitse nämä ominaisuudet:

    - **Teksti**: `ThisItem.Value`
    - **Leveys**: 50

1. Lisää toisen (pystysuuntaisen) valikoiman sisällä toinen **Selite** -ohjaus objekti ja valitse nämä ominaisuudet:

    - **Teksti**: `Char( ThisItem.Value )`
    - **Leveys**: 50
    - **X**: 50

Olet luonut kaavion ensimmäisistä 128 ASCII-merkeistä. Pieniä nelikulmion näkyviä merkkejä ei voi tulostaa.

![Ensimmäiset 128 ASCII-merkkiä](media/function-char/chart-lower.png)

Jos haluat näyttää laajennetun ASCII-merkistön merkit, valitse toisen valikoiman **Items** -ominaisuudeksi Tämä kaava, joka lisää 128 kuhunkin merkki arvoon:

`ForAll( [0,2,3,4,5,6,7,8,9,10,11,12,13,14,15], Value + ThisItem.Value * 16 + 128)`

![Laajennetut ASCII-merkit](media/function-char/chart-higher.png)

Jos haluat näyttää eri fontin merkit, valitse toisen selitteen **Fontti** -ominaisuudeksi arvo, kuten **Dancing script**.

![Tanssiva komento sarja](media/function-char/chart-higher-dancing-script.png)

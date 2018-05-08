---
title: Abs-, Exp-, Ln-, Power- ja Sqrt-funktiot | Microsoft Docs
description: PowerAppsin Abs- ja Sqrt-funktioiden ja muiden funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.date: 09/13/2016
ms.author: gregli
ms.openlocfilehash: 25d9b49c7f527d7510e31dd937e1d8a580bb31cf
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="abs-exp-ln-power-and-sqrt-functions-in-powerapps"></a>PowerAppsin Abs-, Exp-, Ln-, Power- ja Sqrt-funktiot
Laskevat itseisarvot, luonnolliset logaritmit, neliöjuuret sekä *e*:n tai minkä tahansa numeron määritettyyn potenssiin korottamisen tulokset.

## <a name="description"></a>Kuvaus
**Abs**-funktio palauttaa arvon ei-negatiivisen arvon. Jos numero on negatiivinen **Abs** palauttaa positiivisen vastineen.

**Exp**-funktio palauttaa *e*:n korotettuna argumenttinsa potenssiin.  Transsendenttiluku *e* alkaa 2,7182818...

**Ln**-funktio palauttaa argumenttinsa luonnollisen logaritmin (*e*-kanta).

**Power**-funktio palauttaa luvun korotettuna haluttuun potenssiin.  [**^**-operaattori](operators.md) vastaa Power-funktiota.

**Sqrt**-funktio palauttaa numeron, joka kerrottuna itsellään on yhtä kuin sen argumentti.

Jos välität yhden numeron, paluuarvo on yksi tulos, joka perustuu kutsuttuun funktioon.  Jos välität yhden sarakkeen [taulukon](../working-with-tables.md), joka sisältää numeroita, paluuarvo on yhden sarakkeen tulostaulukko, jossa on yksi tulos jokaiselle argumentin taulukon tietueelle. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [taulukoiden käyttö](../working-with-tables.md) mukaan.  

Jos argumentti tuottaa määrittämättömän arvon, tulos on *tyhjä*.  Näin voi tapahtua esimerkiksi, jos yritetään saada negatiivisen numeron neliöjuuri tai logaritmi.

## <a name="syntax"></a>Syntaksi
**Abs**( *Numero* )<br>**Exp**( *Numero* )<br>**Ln**( *Numero* )<br>**Sqrt**( *Numero* )

* *Numero* – Pakollinen. Numero, jolle toiminto suoritetaan.

**Power**( *Kantaluku*, *Eksponentti* )

* *Kantaluku* – Pakollinen. Kantaluku, joka korotetaan potenssiin.
* *Eksponentti* – Pakollinen. Eksponentti, johon kantaluku korotetaan.

**Abs**( *YksisarakkeinenTaulukko* )<br>**Exp**( *YksisarakkeinenTaulukko* )<br>**Ln**( *YksisarakkeinenTaulukko* )<br>**Sqrt**( *YksisarakkeinenTaulukko* )

* *YksisarakkeinenTaulukko* – Pakollinen. Yhden sarakkeen numeroita sisältävä taulukko, jolle toiminto suoritetaan.

## <a name="examples"></a>Esimerkkejä
### <a name="single-number"></a>Yksittäinen luku
| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Abs( -55 )** |Palauttaa luvun ilman miinusmerkkiä. |55 |
| **Exp( 2 )** |Palauttaa luvun *e* korotettuna potenssiin 2, tai *e* \* *e*. |7,389056... |
| **Ln( 100 )** |Palauttaa luvun 100 luonnollisen logaritmin (*e*-kanta). |4,605170... |
| **Power( 5, 3 )** |Palauttaa luvun 5 korotettuna potenssiin 3, tai 5 \* 5 \* 5. |125 |
| **Sqrt( 9 )** |Palauttaa luvun, joka kerrottuna itsellään on yhtä suuri kuin 9. |3 |

### <a name="single-column-table"></a>Yksisarakkeinen taulukko
Tämän osion esimerkeissä käytetään [tietolähdettä](../working-with-data-sources.md) nimeltä **ValueTable**, joka sisältää seuraavat tiedot:

![](media/function-numericals/values.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Abs(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon numeroiden itseisarvot. |<style> img { max-width: none } </style> ![](media/function-numericals/values-abs.png) |
| **Exp(&nbsp;ValueTable&nbsp;)** |Palauttaa luvun *e* korotettuna taulukon lukujen potensseihin. |<style> img { max-width: none } </style> ![](media/function-numericals/values-exp.png) |
| **Ln(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon lukujen luonnolliset logaritmit. |<style> img { max-width: none } </style> ![](media/function-numericals/values-ln.png) |
| **Sqrt(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon lukujen neliöjuuret |![](media/function-numericals/values-sqrt.png) |

### <a name="step-by-step-example"></a>Vaiheittainen esimerkki
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti ja anna sille nimi **Source**.
2. Lisää **Selite**-ohjausobjekti ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>
   **Sqrt( Value( Source.Text ) )**
3. Kirjoita **Source**-kohtaan luku ja vahvista, että **Selite**-ohjausobjekti näyttää kirjoittamasi numeron neliöjuuren.


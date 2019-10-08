---
title: Abs-, Exp-, Ln-, Power- ja Sqrt-funktiot | Microsoft Docs
description: PowerAppsin Abs- ja Sqrt-funktioiden ja muiden funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 09/13/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6e559f482c8ad151eb04057f3178b141150acc7d
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984415"
ms.PowerAppsDecimalTransform: true
---
# <a name="abs-exp-ln-power-and-sqrt-functions-in-powerapps"></a>Abs-, Exp-, Ln-, Power- ja Sqrt-funktiot PowerAppsissa
Laskevat itseisarvot, luonnolliset logaritmit, neliöjuuret sekä *e*:n tai minkä tahansa numeron määritettyyn potenssiin korottamisen tulokset.

## <a name="description"></a>Kuvaus
**Abs**-funktio palauttaa arvon ei-negatiivisen arvon. Jos numero on negatiivinen **Abs** palauttaa positiivisen vastineen.

**Exp**-funktio palauttaa *e*:n korotettuna argumenttinsa potenssiin.  Transsendenttiluku *e* alkaa 2,7182818...

**Ln**-funktio palauttaa argumenttinsa luonnollisen logaritmin (*e*-kanta).

**Power**-funktio palauttaa luvun korotettuna haluttuun potenssiin.  Se vastaa [ **^** operaattorin](operators.md) käyttämistä.

**Sqrt**-funktio palauttaa numeron, joka kerrottuna itsellään on yhtä suuri kuin sen argumentti.

Jos välität yhden numeron, paluuarvo on yksi tulos, joka perustuu kutsuttuun funktioon.  Jos välität yhden sarakkeen [taulukon](../working-with-tables.md), joka sisältää numeroita, paluuarvo on yhden sarakkeen tulostaulukko, jossa on yksi tulos jokaiselle argumentin taulukon tietueelle. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [Taulukoiden käyttö](../working-with-tables.md) mukaisesti.  

Jos argumentti tuottaa määrittämättömän arvon, tulos on *tyhjä*.  Näin voi tapahtua esimerkiksi, jos yritetään saada negatiivisen numeron neliöjuuri tai logaritmi.

## <a name="syntax"></a>Syntaksi
**Abs**( *Number* )<br>**Exp**( *Number* )<br>**Ln**( *Number* )<br>**Sqrt**( *Number* )

* *Number* – pakollinen. Numero, jolle toiminto suoritetaan.

**Power**( *Base*; *Exponent* )

* *Base* – Pakollinen. Kantaluku, joka korotetaan potenssiin.
* *Exponent* – Pakollinen. Eksponentti, johon kantaluku korotetaan.

**Abs**( *SingleColumnTable* )<br>**Exp**( *SingleColumnTable* )<br>**Ln**( *SingleColumnTable* )<br>**Sqrt**( *SingleColumnTable* )

* *SingleColumnTable* – Pakollinen. Yhden sarakkeen numeroita sisältävä taulukko, jolle toiminto suoritetaan.

## <a name="examples"></a>Esimerkkejä
### <a name="single-number"></a>Yksittäinen luku

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Abs( -55 )** |Palauttaa luvun ilman miinusmerkkiä. |55 |
| **Exp( 2 )** |Palauttaa luvun *e* korotettuna potenssiin 2, tai *e* \* *e*. |7.389056... |
| **Ln( 100 )** |Palauttaa luvun 100 luonnollisen logaritmin (*e*-kanta). |4.605170... |
| **Power( 5; 3 )** |Palauttaa luvun 5 korotettuna potenssiin 3, tai 5 \* 5 \* 5. |125 |
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
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)** -ohjausobjekti ja anna sille nimi **Source**.
2. Lisää **Selite**-ohjausobjekti ja määritä sen **[Text](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:
   <br>
   **Sqrt( Value( Source.Text ) )**
3. Kirjoita **Source**-kohtaan luku ja vahvista, että **Selite**-ohjausobjekti näyttää kirjoittamasi numeron neliöjuuren.


---
title: And-, Or- ja Not-funktiot | Microsoft Docs
description: PowerAppsin And-, Or- ja Not-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a2b04e6a752ade561ec1b95658bcacda759b1a1c
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992568"
ms.PowerAppsDecimalTransform: true
---
# <a name="and-or-and-not-functions-in-powerapps"></a>PowerAppsin And-, Or- ja Not-funktiot

Totuusarvon logiikkafunktiot, joita käytetään yleensä muokkaamaan vertailujen tuloksia ja testauksia.

## <a name="description"></a>Kuvaus

**And**-funktio palauttaa arvon **tosi**, jos kaikilla sen argumenteilla on arvo **tosi**.

**Or** funktio palauttaa arvon **tosi**, jos millä tahansa sen argumentilla on arvo **tosi**.

**Not**-funktio palauttaa arvon **tosi**, jos sen argumentilla on arvo **epätosi**. Se palauttaa arvon **epätosi**, jos sen argumentilla on arvo **tosi**.

Nämä funktiot toimivat samalla tavalla kuin Excelissä. Voit myös käyttää [operaattoreita](operators.md) suorittamaan nämä samat toiminnot käyttämällä joko Visual Basic-tai JavaScript-syntaksia:

| Funktioiden merkintä tapa | Visual Basic operaattorin merkintä tapa | JavaScript-operaattorin merkintä tapa |
| -------------|------------|--------|
| **Ja (x, Ky)** | **x ja sy** | **x & & ty** |
| **Tai (x, Ky)** | **x tai Ky** | **x &#124; &#124; -kirjain** |
| **Ei (x)** | **Ei x** | **! x** |

Nämä funktiot toimivat loogisten arvojen kanssa. Et voi välittää heille numeroa tai merkki jonoa suoraan; sen sijaan sinun on tehtävä vertailu tai testi. Esimerkiksi tämä looginen kaava **x > 1** antaa tulokseksi totuus arvon **True** , jos **x** on suurempi kuin **1**. Jos **x** on pienempi kuin **1**, kaava antaa tulokseksi arvon **false**.

## <a name="syntax"></a>Syntaksi

**And**( *LogicalFormula1*; *LogicalFormula2* [; *LogicalFormula3*; ... ] )<br>
**Or**( *LogicalFormula1*; *LogicalFormula2* [; *LogicalFormula3*; ... ] )<br>
**Not**( *LogicalFormula* )

- *LogicalFormula(s)* – Pakollinen.  Loogiset kaavat, jotka arvioidaan ja joille toiminto suoritetaan.

## <a name="examples"></a>Esimerkkejä

Tämän osion esimerkeissä käytetään seuraavia yleisiä muuttujia:

- **@no__t-** 1*false*
- **b** = *True*
- **x** = 10
- **Ky** = 100
- **s** = "Hei maailma"

Jos haluat luoda nämä yleiset muuttujat sovelluksessa, Lisää [**painike**](../controls/control-button.md) -ohjaus objekti ja määritä sen **onselect** -ominaisuudeksi Tämä kaava:

```powerapps-comma
Set( a; false );; Set( b; true );; Set( x; 10 );; Set( y; 100 );; Set( s; "Hello World" )
```

Valitse painike (napsauttamalla sitä, kun painat Alt-näppäintä), ja määritä sitten [**Selite**](../controls/control-text-box.md) -ohjaus objektin **Text** -ominaisuudeksi kaava seuraavan taulukon ensimmäisessä sarakkeessa.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Ja (a, b)** | Testaa **a:n ja** **b:n**arvot.  Yksi argumenteista on *Epätosi*, joten funktio palauttaa arvon *false*. | *epätosi* |
| **a ja b** | Sama kuin edellisessä esimerkissä käyttäen Visual Basic merkintää. | *epätosi* |
| **& & b** | Sama kuin edellisessä esimerkissä käyttäen JavaScript-merkintää. | *epätosi* |
| **Tai (a, b)** | Testaa **a:n ja** **b:n**arvot. Yksi argumenteista on *tosi*, joten funktio palauttaa arvon *True*. | *tosi* |
| **a tai b** | Sama kuin edellisessä esimerkissä käyttäen Visual Basic merkintää. | *tosi* |
| **a &#124; &#124; b** | Sama kuin edellisessä esimerkissä käyttäen JavaScript-merkintää. | *tosi* |
| **Ei (a)** | Testaa **arvon.** Argumentti on *Epätosi*, joten funktio palauttaa vastakkaisen tuloksen. | *tosi* |
| **Ei ole** | Sama kuin edellisessä esimerkissä käyttäen Visual Basic merkintää. | *tosi* |
| **! on** | Sama kuin edellisessä esimerkissä käyttäen JavaScript-merkintää. | *tosi* |
| **Len (&nbsp;s @ no__t-2) &nbsp; @ no__t-4 @ no__t-520 ja @ no__t-6Not @ no__t-7Isteblank (&nbsp;S @ no__t-9)** | Testaa, onko **s** -pituus pienempi kuin 20 ja onko se **tyhjä** arvo. Pituus on pienempi kuin 20, eikä arvo ole tyhjä. Tulos on siis *True*. | *tosi* |
| **Tai (&nbsp;Len (&nbsp;S @ no__t-3) &nbsp; @ no__t-5 @ no__t-610, x @ no__t-7 @ no__t-8 @ no__t-9100, yn @ no__t-10 @ no__t-11 @ no__t-12100 @ no__t-13)** | Testaa, onko **s** -pituus pienempi kuin 10, onko **x** pienempi kuin 100 **ja onko** y:n arvo pienempi kuin 100. Ensimmäinen ja kolmas argumentti ovat vääriä, mutta toinen on tosi. Tämän vuoksi funktio palauttaa arvon *True*. | *tosi* |
| **Ei Onblank (&nbsp;s @ no__t-2)** | Testaa, onko s *tyhjä*, joka palauttaa arvon *false*. **Ei** Palauta tämän tuloksen vasta kohtaa, mikä on *tosi*. | *tosi* |
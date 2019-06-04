---
title: Concat- ja Concatenate-funktiot | Microsoft Docs
description: PowerAppsin Concat- ja Concatenate-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 889f612f3da208d4edfccc43a579ced07933b40d
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/24/2019
ms.locfileid: "66216094"
ms.PowerAppsDecimalTransform: true
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>Concat- ja Concatenate-funktiot PowerAppsissa

Yhdistää yksittäisiä tekstimerkkijonoja ja merkkijonoja [taulukoiksi](../working-with-tables.md).

## <a name="description"></a>Kuvaus

**Concatenate**-funktio yhdistää kokoelman yksittäisiä merkkijonoja ja yksisarakkeisen merkkijonotaulukon. Kun käytät tätä funktiota yksittäisten merkkijonojen kanssa, se vastaa **&** [operaattorin](operators.md).

**Concat**-funktio yhdistää kaikkiin taulukon [tietueisiin](../working-with-tables.md#records) käytetyn kaavan tulokset. Tuloksena on yksi merkkijono. Käytä tätä funktiota taulukon merkkijonojen laskemiseen yhteen aivan samalla tavalla kuin **[Sum](function-aggregates.md)** -funktiota luvuille.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Käytä [ **Jaa** ](function-split.md) tai [ **MatchAll** ](function-ismatch.md) funktiota merkkijonon jakamiseen osamerkkijonojen taulukoksi.

## <a name="syntax"></a>Syntaksi

**Concat**( *Table*; *Formula* )

- *Table* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
- *Formula* – Pakollinen.  Kaikkiin taulukon tietueisiin käytettävä kaava.

**Concatenate**( *String1* [; *String2*; ...] )

- *String(s)* – Pakollinen.  Yksittäisten merkkijonojen tai yksisarakkeisen taulukon merkkijonojen yhdistelmä.

## <a name="examples"></a>Esimerkkejä

Tämän osion esimerkeissä käytetään näitä yleisiä muuttujia:

- **Etunimi** = ”Jane”
- **Sukunimi** = ”Doe”
- **Tuotteiden** = ![taulukon, jossa on kaksi saraketta ja neljä riviä](media/function-concatenate/products.png)

Jos haluat luoda sovelluksen näitä yleisiä muuttujia, Lisää [ **painike** ](../controls/control-button.md) ohjausobjekti ja määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava:

```powerapps-comma
Set( FirstName; "Jane" );; Set( LastName; "Doe" );;
Set( Products;
    Table(
        { Name: "Violin"; Type: "String" };
        { Name: "Cello"; Type: "String" };
        { Name: "Trumpet"; Type: "Wind" }
    )
)
```

Valitse painike (napsauttamalla sitä pidä Alt-näppäintä).

### <a name="concatenate-function-and-the--operator"></a>Yhdistä funktio ja & operaattori

Määritä näissä esimerkeissä **tekstin** ominaisuus [ **nimen** ](../controls/control-text-box.md) seuraavan taulukon ensimmäisen sarakkeen kaavassa ohjausobjektin.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Concatenate (&nbsp;Sukunimi,&nbsp;”,&nbsp;”,&nbsp;Etunimi&nbsp;)** | Yhdistää arvo **Sukunimi**, merkkijono **””,** (pilkun ja välilyönnin), ja arvo **Etunimi**. | ”Doe&nbsp;Jane” |
| **LastName&nbsp;&&nbsp;",&nbsp;"&nbsp;&&nbsp;FirstName** | Sama kuin edellisessä esimerkissä lukuun ottamatta käyttämistä **&** operaattorin sijaan funktio. | ”Doe&nbsp;Jane” |
| **Concatenate (&nbsp;Etunimi,&nbsp;”&nbsp;”,&nbsp;Sukunimi&nbsp;)** | Yhdistää arvo **Etunimi**, merkkijono **””** (yksi välilyönti), ja arvo **Sukunimi**. | "Jane&nbsp;Doe" |
| **FirstName&nbsp;&&nbsp;"&nbsp;"&nbsp;&&nbsp;LastName** | Sama kuin edellisessä esimerkissä käyttämällä **&** operaattorin sijaan funktio. | "Jane&nbsp;Doe" |

### <a name="concatenate-with-a-single-column-table"></a>Yhdistä ja yhden sarakkeen taulukko

Tässä esimerkissä Lisää tyhjä, pysty [ **valikoiman** ](../controls/control-gallery.md) ohjausobjekti, määritä sen **kohteet** ominaisuudeksi kaava seuraavan taulukon ja lisää sitten otsikko valikoiman mallipohja.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Concatenate (”nimi:&nbsp;”,&nbsp;Products.Name ”,,&nbsp;tyyppi:&nbsp;”,&nbsp;Products.Type)** | Jokaiselle tietueelle **tuotteiden** taulukossa, yhdistää merkkijonon **”nimi”:** , merkkijono-tuotteen nimi **”, tyyppi”:** ja tuotteen tyyppi.  | ![Taulukon tuotteita](media/function-concatenate/single-column.png) |

### <a name="concat-function"></a>Concat-funktio

Määritä näissä esimerkeissä **tekstin** ominaisuuden kaavaa selitteen seuraavan taulukon ensimmäisen sarakkeen.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Concat (Products, nimi & ””,)** | Laskee lausekkeen **nimi & ””,** kullekin tietueelle **tuotteiden** ja yhdistää tulokset yhdessä yksittäiseksi merkkijonoksi.  | ”Violin,&nbsp;Cello,&nbsp;Trumpetti,&nbsp;” |
| **Concat (Filter (&nbsp;tuotteet,&nbsp;tyyppi&nbsp;=&nbsp;”String”&nbsp;), nimi & ””,)** | Laskee kaavan **nimi & ””,** kullekin tietueelle **tuotteiden** , joka täyttää suodatin **tyyppi = ”String”** , ja yhdistää tulokset yksittäiseksi merkkijonoksi.   | ”Violin,&nbsp;Cello,&nbsp;” |

### <a name="trimming-the-end"></a>Siistiminen loppuun

Viimeiset kaksi esimerkkejä ylimääräinen ””, tuloksen lopussa. Funktio lisää pilkun ja välilyönnin- **nimi** jokaisen tietueen taulukon, mukaan lukien viimeisen tietueen arvo.

Joissakin tapauksissa näiden ylimääräisiä merkkejä ei ole merkitystä. Esimerkiksi kaksinkertaista erotinta ei näy, jos voit näyttää tuloksen selitteessä. Jos haluat poistaa nämä ylimääräisiä merkkejä, käytä [ **vasemmalle** ](function-left-mid-right.md) tai [ **vastaavuus** ](function-ismatch.md) funktio.

Määritä näissä esimerkeissä **tekstin** ominaisuuden kaavaa selitteen seuraavan taulukon ensimmäisen sarakkeen.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Vasen (Concat (&nbsp;tuotteet,&nbsp;nimi&nbsp;&&nbsp;”,&nbsp;”&nbsp;), Len (&nbsp;Concat (&nbsp;tuotteet,&nbsp;nimi&nbsp; & &nbsp;”,&nbsp;”&nbsp;)&nbsp;)&nbsp;-&nbsp;2)** | Palauttaa tuloksen **Concat** mutta poistaa viimeiset kaksi merkkiä, jotka muodostavat ylimääräisten erotin. | ”Violin,&nbsp;Cello,&nbsp;Trumpetti” |
| **Vastaavuus (Concat (&nbsp;tuotteet,&nbsp;nimi&nbsp;&&nbsp;”,&nbsp;”&nbsp;) ”, ^ (?&lt; TRIM&gt;. *),&nbsp;$”) .trim** | Palauttaa merkit **Concat** alusta loppuun ($) merkkijonon (^) mutta ei sisällä ei-toivottu pilkku ja tilaa loppuun. | ”Violin,&nbsp;Cello,&nbsp;Trumpetti” |

### <a name="split-and-matchall"></a>Jaa ja MatchAll

Jos käytit **Concat** erotin, jossa voit kääntää toimintoa yhdistämällä **Jaa** ja **MatchAll** funktioita.

Näissä esimerkeissä Lisää tyhjä, pystysuuntainen valikoima, määritä sen **kohteet** ominaisuuden näyttämään kaavan, seuraavassa taulukossa ja lisää sitten otsikko valikoiman mallipohja.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Jaa (Concat (&nbsp;tuotteet,&nbsp;nimi&nbsp;&&nbsp;”,&nbsp;”&nbsp;), ””,)** | Jakaa merkkijonon erottimella **””,** . Merkkijonon lopussa pilkku ja välilyönti, joten tulos viimeistä riviä on tyhjä merkkijono.  | ![Table](media/function-concatenate/split.png) |
| **MatchAll (Concat (&nbsp;tuotteet;&nbsp;nimi&nbsp;&&nbsp;”;&nbsp;”&nbsp;) ”; [^ \s;]+”). FullMatch** | Jakaa merkkijonon merkkejä, jotka eivät ole välilyöntejä tai pilkkuja perusteella. Tämä kaava poistaa ylimääräiset pilkuin ja tilaa merkkijonon lopussa. | ![Table](media/function-concatenate/matchall.png)
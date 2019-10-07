---
title: Concat- ja Concatenate-funktiot | Microsoft Docs
description: PowerAppsin Concat- ja Concatenate-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.openlocfilehash: 0a56230539990ce51cc9270f71d8c2b7c9a1db73
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992877"
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>Concat- ja Concatenate-funktiot PowerAppsissa

Yhdistää yksittäisiä tekstimerkkijonoja ja merkkijonoja [taulukoiksi](../working-with-tables.md).

## <a name="description"></a>Kuvaus

**Concatenate**-funktio yhdistää kokoelman yksittäisiä merkkijonoja ja yksisarakkeisen merkkijonotaulukon. Kun käytät tätä funktiolla yksilöllisiä merkki jonoja, se vastaa **&-** [operaattorin](operators.md)käyttämistä.

**Concat**-funktio yhdistää kaikkiin taulukon [tietueisiin](../working-with-tables.md#records) käytetyn kaavan tulokset. Tuloksena on yksi merkkijono. Käytä tätä funktiota taulukon merkkijonojen laskemiseen yhteen aivan samalla tavalla kuin **[Sum](function-aggregates.md)** -funktiota luvuille.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Jaa merkki jono alimerkkijonojen taulukkoon [**Split**](function-split.md) -tai [**matchall**](function-ismatch.md) -funktiolla.

## <a name="syntax"></a>Syntaksi

**Concat**( *Table*, *Formula* )

- *Table* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
- *Formula* – Pakollinen.  Kaikkiin taulukon tietueisiin käytettävä kaava.

**Concatenate**( *String1* [, *String2*, ...] )

- *String(s)* – Pakollinen.  Yksittäisten merkkijonojen tai yksisarakkeisen taulukon merkkijonojen yhdistelmä.

## <a name="examples"></a>Esimerkkejä

Tämän osion esimerkeissä käytetään seuraavia yleisiä muuttujia:

- **Firstname** = "Jane"
- **Suku nimi** = "Doe"
- **Tuotteet** =  @ No__t-2table, jossa on kaksi saraketta ja neljä riviä @ no__t-3

Jos haluat luoda nämä yleiset muuttujat sovelluksessa, Lisää [**painike**](../controls/control-button.md) -ohjaus objekti ja määritä sen **onselect** -ominaisuudeksi Tämä kaava:

```powerapps-dot
Set( FirstName, "Jane" ); Set( LastName, "Doe" );
Set( Products,
    Table(
        { Name: "Violin", Type: "String" },
        { Name: "Cello", Type: "String" },
        { Name: "Trumpet", Type: "Wind" }
    )
)
```

Valitse painike (napsauttamalla sitä, kun painat Alt-näppäintä).

### <a name="concatenate-function-and-the--operator"></a>KETJUTA-funktiolla ja &-operaattorilla

Näitä esimerkkejä varten voit määrittää [**Selite**](../controls/control-text-box.md) -ohjaus objektin **Text** -ominaisuudeksi kaavan seuraavan taulukon ensimmäisestä sarakkeesta.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Concatenate (&nbsp;LastName, &nbsp; ", &nbsp;", &nbsp;FirstName @ no__t-5)** | Liittää arvon **suku nimi**, merkki jono **","** (pilkku ja väli lyönti) ja arvon **firstname**. | "Doe, &nbsp;Jane" |
| **Suku nimi @ no__t-1 @ no__t-2 @ no__t-3 ", &nbsp;" &nbsp; @ no__t-6 @ no__t-7FirstName** | Sama kuin edellisessä esimerkissä, paitsi käytettäessä **&-** operaattoria toiminnon sijaan. | "Doe, &nbsp;Jane" |
| **Concatenate (&nbsp;FirstName, &nbsp; "&nbsp;", &nbsp;LastName @ no__t-5)** | Yhdistää arvon **firstname**, merkki jonon **""** (yksittäinen väli lyönti) ja arvon **suku nimi**. | "Jane @ no__t-0Doe" |
| **Etunimi @ no__t-1 @ no__t-2 @ no__t-3 "&nbsp;" &nbsp; @ no__t-6 @ no__t-7LastName** | Sama kuin edellisessä esimerkissä käyttämällä **&-** operaattoria toiminnon sijaan. | "Jane @ no__t-0Doe" |

### <a name="concatenate-with-a-single-column-table"></a>Yhdistä yksisarakkeisella taulukolla

Lisää tässä esimerkissä tyhjä, pystysuuntainen [**valikoima**](../controls/control-gallery.md) -ohjaus objekti, määritä sen **Items** -ominaisuudeksi kaava seuraavassa taulukossa ja lisää sitten otsikko valikoima-malliin.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Concatenate ("nimi: &nbsp;", &nbsp;Products.Name, ", &nbsp;Type: &nbsp;", &nbsp;Products. Type)** | Yhdistä **tuotteet** -taulukon kunkin tietueen merkki jono **"Name:"** , tuotteen nimi, merkki jono **", tyyppi:"** ja tuotteen tyyppi.  | ![Tuote taulukko](media/function-concatenate/single-column.png) |

### <a name="concat-function"></a>Conat-Funktiot

Tässä esimerkissä asetat selitteen **teksti** -ominaisuudeksi kaavan seuraavan taulukon ensimmäisestä sarakkeesta.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Kopat (tuotteet, nimi & ",")** | Laskee kunkin **tuote** tietueen lausekkeen **nimen & ","** ja yhdistää tulokset yhteen teksti merkki jonoon.  | "Viulu, &nbsp;Cello, &nbsp;Trumpet, &nbsp;" |
| **Conat (Filter (&nbsp;Products, &nbsp;Type @ no__t-3 @ no__t-4 @ no__t-5 "String" &nbsp;), nimi & ",")** | Laskee kaavan **nimen & ","** kullekin **tuote** tietueelle, joka täyttää suodatin **tyypin = "merkki jonon"** , ja yhdistää tulokset yksittäiseksi teksti merkki jonoksi.   | "Viulu, &nbsp;Cello, &nbsp;" |

### <a name="trimming-the-end"></a>Leikkaus loppu

Viimeiset kaksi esimerkkiä sisältävät ylimääräisen "," tuloksen lopussa. -Funktiolla lisätään pilkku ja väli lyönti kunkin taulukon tietueen **nimi** arvoon, mukaan lukien viimeinen tietue.

Joissakin tapa uksissa nämä ylimääräiset merkit eivät ole tärkeitä. Esimerkiksi yksittäinen väli lyönti-erotin ei näy, jos näytät tuloksen selitteessä. Jos haluat poistaa ylimääräiset merkit, käytä [**vasenta**](function-left-mid-right.md) tai [**Match**](function-ismatch.md) -funktiolla.

Tässä esimerkissä asetat selitteen **teksti** -ominaisuudeksi kaavan seuraavan taulukon ensimmäisestä sarakkeesta.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Vasemmalla (Conat (&nbsp;Products, &nbsp;Name @ no__t-3 @ no__t-4 @ no__t-5 ", &nbsp;" &nbsp;), len (&nbsp;Concat (&nbsp;Products, 0Name @ no__t-11 @ no__t-12 @ no__t-13 ", 4" 5) 6) 7 @ no__t-18 @ no__t-192)** | Palauttaa **Conciat** -kohteen tuloksen, mutta poistaa kaksi viimeistä merkkiä, jotka muodostavat ylimääräisiä erottimia. | "Viulu, &nbsp;Cello, &nbsp;Trumpetti" |
| **Match (Conat (&nbsp;Products, &nbsp;Name @ no__t-3 @ no__t-4 @ no__t-5 ", &nbsp;" &nbsp;), "^ (? &lt;trim @ no__t-9. *), @no__t-$10"). Trim** | Palauttaa merkki jonon merkit merkki **jonon alusta (** ^) loppuun ($), mutta ei sisällä ei-toivottua pilkkua ja tilaa lopussa. | "Viulu, &nbsp;Cello, &nbsp;Trumpetti" |

### <a name="split-and-matchall"></a>Jaa ja MatchAll

Jos käytit **Conpat** -funktiota erottimen kanssa, voit kumota toiminnon yhdistämällä **Split** -ja **matchall** -funktiot.

Lisää näitä esimerkkejä varten tyhjä, pystysuuntainen valikoima, määritä sen **Items** -ominaisuudeksi kaava seuraavassa taulukossa ja lisää sitten otsikko valikoima-malliin.

| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| **Split (Conat (&nbsp;Products, &nbsp;Name @ no__t-3 @ no__t-4 @ no__t-5 ", &nbsp;" &nbsp;), ",")** | Jakaa teksti merkki jonon erottimella **","** . Merkki jono päättyy pilkuilla ja väli lyönnillä, joten tuloksen viimeinen rivi on tyhjä merkki jono.  | ![Table](media/function-concatenate/split.png) |
| **MatchAll (Conat (&nbsp;Products, &nbsp;Name @ no__t-3 @ no__t-4 @ no__t-5 ", &nbsp;" &nbsp;), "[^ \s,] +"). FullMatch** | Jakaa teksti merkki jonon niiden merkkien perusteella, jotka eivät ole väli lyöntejä tai pilkkuja. Tämä kaava poistaa ylimääräisen pilkun ja väli lyönnin merkki jonon lopusta. | ![Table](media/function-concatenate/matchall.png)
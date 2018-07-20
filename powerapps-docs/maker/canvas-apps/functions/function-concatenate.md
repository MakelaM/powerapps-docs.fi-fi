---
title: Concat- ja Concatenate-funktiot | Microsoft Docs
description: PowerAppsin Concat- ja Concatenate-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 2ead46b4b34e2013205a412eacd86197a3c3b552
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015819"
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>Concat- ja Concatenate-funktiot PowerAppsissa
Yhdistää yksittäisiä tekstimerkkijonoja ja merkkijonoja [taulukoiksi](../working-with-tables.md).

## <a name="description"></a>Kuvaus
**Concat**-funktio yhdistää kaikkiin taulukon [tietueisiin](../working-with-tables.md#records) käytetyn kaavan tulokset. Tuloksena on yksi merkkijono. Käytä tätä funktiota taulukon merkkijonojen laskemiseen yhteen aivan samalla tavalla kuin **[Summa](function-aggregates.md)**-funktiota luvuille.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Käytä **[Jaa osiin](function-split.md)** -funktiota merkkijonon jakamiseen osamerkkijonojen taulukoksi.

**Concatenate**-funktio yhdistää kokoelman yksittäisiä merkkijonoja ja yksisarakkeisen merkkijonotaulukon. Yksittäisten merkkijonojen kanssa käytettynä tämä funktio vastaa **&**[-operaattorin käyttöä](operators.md). Voit käyttää **[ShowColumns](function-table-shaping.md)**-funktion sisältävää kaavaa yksisarakkeisen taulukon luomiseen useita sarakkeita sisältävästä taulukosta.

## <a name="syntax"></a>Syntaksi
**Concat**( *Table*, *Formula* )

* *Taulukko* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
* *Kaava* – Pakollinen.  Kaikkiin taulukon tietueisiin käytettävä kaava.

**Concatenate**( *String1* [, *String2*, ...] )

* *Merkkijono(t)* – Pakollinen.  Yksittäisten merkkijonojen tai yksisarakkeisen taulukon merkkijonojen yhdistelmä.

## <a name="examples"></a>Esimerkkejä
#### <a name="concat"></a>Concat
1. Lisää **[Painike](../controls/control-button.md)**-ohjausobjekti ja määritä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   
    **Collect(Products, {String:”Violin”, Wind:”Trombone”, Percussion:”Bongos”}, {String:”Cello”, Wind:”Trumpet”, Percussion:”Tambourine”})**
2. Palaa suunnittelutyötilaan painamalla F5-näppäintä, napsauttamalla painiketta ja painamalla sitten Esc-näppäintä.
3. Lisää **[Nimi](../controls/control-text-box.md)**-ohjausobjekti ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   
    **Concat(Products, String & ” ”)**
   
    Selitteessä näkyy **Violin Cello**.

#### <a name="concatenate"></a>Concatenate
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti ja anna sille nimi **AuthorName**.
2. Lisää **[Nimi](../controls/control-text-box.md)**-ohjausobjekti ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **Concatenate(”By ”, AuthorName.Text)**
3. Kirjoita nimesi kohtaan **AuthorName**.
   
    Selitteessä näkyy **By**, jota seuraa nimesi.

Jos sinulla oli **Employees**-taulukko, joka sisälsi **FirstName**-sarakkeen ja **LastName**-sarakkeen, tämä kaava yhdistäisi näiden sarakkeiden kunkin rivin tiedot.
<br>**Concatenate(Employees.FirstName, ” ”, Employees.LastName)**


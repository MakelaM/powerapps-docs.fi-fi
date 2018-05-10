---
title: Concat- ja Concatenate-funktiot | Microsoft Docs
description: PowerAppsin Concat- ja Concatenate-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 5f69d51fc1d018a48576cade665ebd19ec1d7c82
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
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
3. Lisää **[Otsikko](../controls/control-text-box.md)**-ohjausobjekti ja määritä sen **[Teksti](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   
    **Concat(Products, String & ” ”)**
   
    Otsikossa näkyy **Viulu Sello**.

#### <a name="concatenate"></a>Concatenate
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti ja anna sille nimi **AuthorName**.
2. Lisää **[Otsikko](../controls/control-text-box.md)**-ohjausobjekti ja määritä sen **[Teksti](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **Concatenate(”By ”, AuthorName.Text)**
3. Kirjoita nimesi kohtaan **AuthorName**.
   
    Otsikossa näkyy **Tekijä**, jota seuraa nimesi.

Jos sinulla oli **Työntekijät**-taulukko, joka sisälsi **FirstName**- ja **LastName**-sarakkeen, tämä kaava yhdistäisi näiden sarakkeiden kunkin rivin tiedot.
<br>**Concatenate(Employees.FirstName, ” ”, Employees.LastName)**


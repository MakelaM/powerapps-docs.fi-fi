---
title: Date- ja Time-funktiot | Microsoft Docs
description: PowerAppsin Date- ja Time-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: bed2bc9b13b4d167d6852b7029e4e69d54d50413
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="date-and-time-functions-in-powerapps"></a>Date- ja Time-funktiot PowerAppsissa
Muuntaa päivämäärän ja kellonajan komponentit päivämäärä/aika-arvoksi.

## <a name="description"></a>Kuvaus
**Date**-funktio muuntaa yksittäiset vuosi-, kuukausi- ja päiväarvot päivämäärä/aika-arvoksi.  Aikaosa vastaa keskiyötä.

* Jos vuosi on 0–1899 (nämä arvot mukaan lukien), funktio lisää kyseisen arvon lukuun 1900 vuoden laskemista varten.  Arvosta **70** tulee **1970**.
* Jos kuukausi on pienempi kuin 1 tai suurempi kuin 12, tulosta varten vähennetään tai lisätään tämä kuukausien määrä määritetyn vuoden alkuun.
* Jos päivä on suurempi kuin määritetyn kuukauden päivien määrä, funktio lisää tämän päivien määrän kuukauden ensimmäiseen päivään ja palauttaa seuraavan kuukauden vastaavan päivämäärän.  Jos päivä on pienempi kuin 1, funktio vähentää tämän päivien määrän yhdellä lisättynä määritetyn kuukauden ensimmäisestä päivästä.

**Time**-funktio muuntaa yksittäiset tunti-, minuutti- ja sekuntiarvot päivämäärä/aika-arvoksi.  Tulokseen ei liity päivämäärää.

Katso **[DateValue](function-datevalue-timevalue.md)**-, **[TimeValue](function-datevalue-timevalue.md)**- ja **[DateTimeValue](function-datevalue-timevalue.md)**-funktioiden kohdalta tietoja siitä, miten voit muuntaa merkkijonon arvoksi.  

Lisätietoja on myös kohdassa [Päivämäärien ja kellonaikojen käsittely](../show-text-dates-times.md).

## <a name="syntax"></a>Syntaksi
**Date**( *vuosi*, *kuukausi*, *päivä* )

* *Vuosi* – pakollinen.  Lukua 1899 suuremmat luvut tulkitaan absoluuttisina (1980 tulkitaan vuotena 1980). Luvut 0–1899 tulkitaan suhteessa lukuun 1900. (Esimerkiksi 80 tulkitaan 1980.)
* *Kuukausi* – pakollinen.  Luku, joka on välillä 1–12.
* *Päivä* – pakollinen. Numero, joka on välillä 1–31.

**Time**( *tunti*, *minuutti*, *sekunti* )

* *Tunti* – pakollinen.  Luku, joka on välillä 0 (12:00 AM) – 23 (11:00 PM).
* *Minuutti* – pakollinen. Numero, joka on välillä 0–59.
* *Sekunti* – pakollinen. Numero, joka on välillä 0–59.

## <a name="examples"></a>Esimerkkejä
### <a name="date"></a>Päivämäärä
Jos käyttäjä kirjoittaa **1979** tekstisyöte-ohjausobjektiin, jonka nimi on **PalkkausVuosi**, **3** tekstisyöte-ohjausobjektiin, jonka nimi on **PalkkausKuukausi**, ja **17** tekstisyöte-ohjausobjektiin, jonka nimi on **PalkkausPäivä**, funktio palauttaa tuloksen **3/17/1979**:

**Date(Value(PalkkausVuosi.Text), Value(PalkkausKuukausi.Text), Value(PalkkausPäivä.Text))**

### <a name="time"></a>Aika
Jos käyttäjä kirjoittaa **14** tekstisyöte-ohjausobjektiin, jonka nimi on **SyntymäTunti**, **50** tekstisyöte-ohjausobjektiin, jonka nimi on **SyntymäMinuutti**, ja **24** tekstisyöte-ohjausobjektiin, jonka nimi on **SyntymäSekunti**, funktio palauttaa tuloksen **02:50:24 p**.

**Text(Time(Value(SyntymäTunti.Text), Value(SyntymäMinuutti.Text), Value(SyntymäSekunti.Text)), "hh:mm:ss a/p")**


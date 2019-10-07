---
title: Date- ja Time-funktio | Microsoft Docs
description: PowerAppsin Date- ja Time-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: efd6e2cdea45f511a545ccfe2f38309bdf622110
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985230"
---
# <a name="date-and-time-functions-in-powerapps"></a>Date- ja Time-funktio PowerAppsissa
Muuntaa päivämäärän ja kellonajan komponentit päivämäärä/aika-arvoksi.

## <a name="description"></a>Kuvaus
**Date**-funktio muuntaa yksittäiset vuosi-, kuukausi- ja päiväarvot päivämäärä/aika-arvoksi.  Aikaosa vastaa keskiyötä.

* Jos vuosi on 0–1899 (nämä arvot mukaan lukien), funktio lisää kyseisen arvon lukuun 1900 vuoden laskemista varten.  Arvosta **70** tulee **1970**.
* Jos kuukausi on pienempi kuin 1 tai suurempi kuin 12, tulosta varten vähennetään tai lisätään tämä kuukausien määrä määritetyn vuoden alkuun.
* Jos päivä on suurempi kuin määritetyn kuukauden päivien määrä, funktio lisää tämän päivien määrän kuukauden ensimmäiseen päivään ja palauttaa seuraavan kuukauden vastaavan päivämäärän.  Jos päivä on pienempi kuin 1, funktio vähentää tämän päivien määrän yhdellä lisättynä määritetyn kuukauden ensimmäisestä päivästä.

**Time**-funktio muuntaa yksittäiset tunti-, minuutti- ja sekuntiarvot päivämäärä/aika-arvoksi.  Tulokseen ei liity päivämäärää.

Katso **[DateValue](function-datevalue-timevalue.md)** -, **[TimeValue](function-datevalue-timevalue.md)** - ja **[DateTimeValue](function-datevalue-timevalue.md)** -funktioiden kohdalta tietoja siitä, miten voit muuntaa merkkijonon arvoksi.  

Lisätietoja on myös kohdassa [Päivämäärien ja kellonaikojen käsittely](../show-text-dates-times.md).

## <a name="syntax"></a>Syntaksi
**Date**( *Year*, *Month*, *Day* )

* *Year* – Pakollinen.  Lukua 1899 suuremmat luvut tulkitaan absoluuttisina (1980 tulkitaan vuotena 1980). Luvut 0–1899 tulkitaan suhteessa lukuun 1900. (Esimerkiksi 80 tulkitaan 1980.)
* *Month* – Pakollinen.  Luku, joka on välillä 1–12.
* *Day* – Pakollinen. Numero, joka on välillä 1–31.

**Time**( *Hour*, *Minute*, *Second* )

* *Hour* – Pakollinen.  Luku, joka on välillä 0 (12:00 AM) – 23 (11:00 PM).
* *Minute* – Pakollinen. Numero, joka on välillä 0–59.
* *Second* – Pakollinen. Numero, joka on välillä 0–59.

## <a name="examples"></a>Esimerkkejä
### <a name="date"></a>Date
Jos käyttäjä kirjoittaa **1979** tekstisyöte-ohjausobjektiin, jonka nimi on **HireYear**, **3** tekstisyöte-ohjausobjektiin, jonka nimi on **HireMonth**, ja **17** tekstisyöte-ohjausobjektiin, jonka nimi on **HireDate**, funktio palauttaa tuloksen **3/17/1979**:

**Date(Value(HireYear.Text), Value(HireMonth.Text), Value(HireDay.Text))**

### <a name="time"></a>Time
Jos käyttäjä kirjoittaa **14** tekstisyöte-ohjausobjektiin, jonka nimi on **BirthHour**, **50** tekstisyöte-ohjausobjektiin, jonka nimi on **BirthMinute**, ja **24** tekstisyöte-ohjausobjektiin, jonka nimi on **BirthSecond**, funktio palauttaa tuloksen **02:50:24 p**.

**Text(Time(Value(BirthHour.Text), Value(BirthMinute.Text), Value(BirthSecond.Text)), "hh:mm:ss a/p")**


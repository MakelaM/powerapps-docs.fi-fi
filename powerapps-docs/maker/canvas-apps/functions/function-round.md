---
title: Round-, RoundDown- ja RoundUp-funktiot | Microsoft Docs
description: PowerAppsin Round-, RoundDown- ja RoundUp-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 182106097fb08d6ba2a3689048e9e33c5383ff57
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39016417"
---
# <a name="round-rounddown-and-roundup-functions-in-powerapps"></a>Round-, RoundDown- ja RoundUp-funktiot PowerAppsissa
Pyöristää luvun.

## <a name="description"></a>Kuvaus
**Round**-, **RoundDown**- ja **RoundUp**-funktiot pyöristävät luvun tiettyyn desimaalien määrään:

* **Round** pyöristää luvun ylöspäin, jos seuraava numero on 5 tai sitä suurempi. Muussa tapauksessa tämä funktio pyöristää alaspäin.
* **RoundDown** pyöristää aina alaspäin edelliseen pienempään lukuun.
* **RoundUp** pyöristää aina seuraavaan suurempaan lukuun.

Jos välität yksittäisen luvun, palautusarvo on tämän luvun pyöristetty versio.  Jos välität yksisarakkeisen, lukuja sisältävän [taulukon](../working-with-tables.md), palautusarvo on yksisarakkeinen taulukko, joka sisältää pyöristettyjä lukuja. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [Taulukoiden käyttö](../working-with-tables.md) mukaisesti.

## <a name="syntax"></a>Syntaksi
**Round**( *numero*, *Desimaalipaikat* )<br>**RoundDown**( *numero*, *Desimaalipaikat* )<br>**RoundUp**( *numero*, *Desimaalipaikat* )

* *Numero* – pakollinen. Pyöristettävä luku.
* *Desimaalipaikat* – pakollinen.  Desimaalipilkun oikealla puolella olevien paikkojen määrä, joiden tarkkuudella luku pyöristetään.  Käytä arvoa 0, jos haluat pyöristää kokonaislukuun.  


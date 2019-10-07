---
title: Round-, RoundDown- ja RoundUp-funktiot | Microsoft Docs
description: PowerAppsin Round-, RoundDown- ja RoundUp-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.openlocfilehash: 8480d66949994ba59f5ab84aef7999ab36a20b51
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983972"
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

* *Number* – pakollinen. Pyöristettävä luku.
* *Desimaalipaikat* – pakollinen.  Desimaalipilkun oikealla puolella olevien paikkojen määrä, joiden tarkkuudella luku pyöristetään.  Käytä arvoa 0, jos haluat pyöristää kokonaislukuun.  


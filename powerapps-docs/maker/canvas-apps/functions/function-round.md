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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8d96b9362047113bda332ab7e7e36c8d5cea0666
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61520509"
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


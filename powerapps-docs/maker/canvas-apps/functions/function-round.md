---
title: Round-, RoundDown- ja RoundUp-funktiot | Microsoft Docs
description: PowerAppsin Round-, RoundDown- ja RoundUp-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 07771027ea728d65bfb35d79fb67bdef1ac80f1a
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "31825782"
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


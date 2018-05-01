---
title: Distinct-funktio | Microsoft Docs
description: PowerAppsin Distinct-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.openlocfilehash: 101c28f2b4ac8135a9b4def9421f886f373105bf
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="distinct-function-in-powerapps"></a>PowerAppsin Distinct-funktio
Tekee [taulukon](../working-with-tables.md#records) [tietueista](../working-with-tables.md) yhteenvedon ja poistaa kaksoiskappaleet.

## <a name="description"></a>Kuvaus
**Distinct**-funktio laskee kaavan taulukon jokaiselle tietueelle. **Distinct** palauttaa yhden sarakkeen taulukon, joka sisältää tulokset mutta ei kaksoisarvoja.  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

## <a name="syntax"></a>Syntaksi
**Distinct**( *Taulukko*, *Kaava* )

* *Taulukko* – Pakollinen.  Taulukko, jolle kaava lasketaan.
* *Kaava* – Pakollinen.  Kaava, jolla lasketaan arvot kullekin tietueelle.

## <a name="example"></a>Esimerkki
Jos sinulla on **Työntekijät**-taulukko, jossa on **Osasto**-sarake, tämä funktio luetteloi jokaisen yksilöllisen osaston nimen kyseisessä sarakkeessa riippumatta siitä, kuinka monta kertaa kukin nimi siinä esiintyy:

**Distinct(Työntekijät, Osasto)**


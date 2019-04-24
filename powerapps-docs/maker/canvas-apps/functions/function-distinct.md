---
title: Distinct-funktio | Microsoft Docs
description: PowerAppsin Distinct-funktion viitetiedot, mukaan lukien syntaksi ja esimerkkejä
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
ms.openlocfilehash: 17a2f2cfca16c5589f74ac434b36326037146b16
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551211"
---
# <a name="distinct-function-in-powerapps"></a>PowerAppsin Distinct-funktio
Tekee [taulukon](../working-with-tables.md#records) [tietueista](../working-with-tables.md) yhteenvedon ja poistaa kaksoiskappaleet.

## <a name="description"></a>Kuvaus
**Distinct**-funktio laskee kaavan taulukon jokaiselle tietueelle. **Distinct** palauttaa yksisarakkeisen taulukon, joka sisältää tulokset mutta ei arvojen kaksoiskappaleita.  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

## <a name="syntax"></a>Syntaksi
**Distinct**( *Table*, *Formula* )

* *Table* – Pakollinen.  Taulukko, jolle kaava lasketaan.
* *Formula* – Pakollinen.  Kaava, jolla lasketaan arvot kullekin tietueelle.

## <a name="example"></a>Esimerkki
Jos sinulla on **Työntekijät**-taulukko, jossa on **Osasto**-sarake, tämä funktio luetteloi jokaisen yksilöllisen osaston nimen kyseisessä sarakkeessa riippumatta siitä, kuinka monta kertaa kukin nimi siinä esiintyy:

**Distinct(Työntekijät, Osasto)**


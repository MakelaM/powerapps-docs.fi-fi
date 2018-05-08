---
title: Table-funktio | Microsoft Docs
description: PowerAppsin Table-funktion viitetiedot, mukaan lukien syntaksi ja esimerkkejä
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
ms.openlocfilehash: 2f543a75019bfe5d665aedb2e6171200e8321690
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="table-function-in-powerapps"></a>PowerAppsin Table-funktio
Luo väliaikaisen [taulukon](../working-with-tables.md).

## <a name="description"></a>Kuvaus
**Table**-funktio luo taulukon argumenttina annetun [tietueiden](../working-with-tables.md#records) luettelon pohjalta.

Taulukon [sarakkeet](../working-with-tables.md#columns) ovat yhdistelmä kaikkien argumenttitietueiden ominaisuuksista. Sarakkeeseen, jolle tietueella ei ole arvoa, lisätään *tyhjä* arvo.

PowerAppsissa taulukko on arvo, samaan tapaan kuin merkkijono tai luku. Voit määrittää taulukon funktion argumenttina ja funktio voi palauttaa tuloksena taulukon. **Table** ei luo pysyvää taulukkoa. Sen sijaan se palauttaa väliaikaisen taulukon, joka on koottu sen argumenteista.  Voit määrittää tämän väliaikaisen taulukon argumenttina toiselle funktiolle, visualisoida sen kokoelmassa tai upottaa sen toiseen taulukkoon.  Lisätietoja on kohdassa [taulukoiden käsitteleminen](../working-with-tables.md).

Voit myös luoda yhden sarakkeen taulukon syntaksilla **[ arvo1, arvo2, ... ]**.

## <a name="syntax"></a>Syntaksi
**Table**( *Tietue1* [, *Tietue2*, ... ] )

* *Tietue(et)* – Pakollinen. Taulukkoon lisättävät tietueet.

## <a name="examples"></a>Esimerkkejä
* Määritä luetteloruudun **[Items](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
  <br>**Table({Color:"red"}, {Color:"green"}, {Color:"blue"})**
  
    Luetteloruutu näyttää värit vaihtoehtoina.
* Lisää tekstivalikoima ja määritä sen **[Items](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:<br>
  **Table({Item:"Violin123", Location:"France", Owner:"Fabrikam"}, {Item:"Violin456", Location:"Chile"})**
  
    Valikoima näyttää kaksi tietuetta, jotka sisältävät kumpikin esineen nimen ja sijainnin. Vain yksi tietue sisältää omistajan nimen.


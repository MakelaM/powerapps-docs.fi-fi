---
title: Taulukkofunktio | Microsoft Docs
description: PowerAppsin Table-funktion viitetiedot, mukaan lukien syntaksi ja esimerkkejä
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
ms.openlocfilehash: 28d393d9be240b3e9ba57d108761c7a38f013b24
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31826863"
---
# <a name="table-function-in-powerapps"></a>PowerAppsin Table-funktio
Luo väliaikaisen [taulukon](../working-with-tables.md).

## <a name="description"></a>Kuvaus
**Table**-funktio luo taulukon argumenttina annetun [tietueiden](../working-with-tables.md#records) luettelon pohjalta.

Taulukon [sarakkeet](../working-with-tables.md#columns) ovat yhdistelmä kaikkien argumenttitietueiden ominaisuuksista. Sarakkeeseen, jolle tietueella ei ole arvoa, lisätään *tyhjä* arvo.

PowerAppsissa taulukko on arvo, samaan tapaan kuin merkkijono tai luku. Voit määrittää taulukon funktion argumenttina ja funktio voi palauttaa tuloksena taulukon. **Table** ei luo pysyvää taulukkoa. Sen sijaan se palauttaa väliaikaisen taulukon, joka on koottu sen argumenteista.  Voit määrittää tämän väliaikaisen taulukon argumenttina toiselle funktiolle, visualisoida sen kokoelmassa tai upottaa sen toiseen taulukkoon.  Lisätietoja on kohdassa [taulukoiden käsitteleminen](../working-with-tables.md).

Voit myös luoda yhden sarakkeen taulukon syntaksilla **[ value1, value2, ... ]**.

## <a name="syntax"></a>Syntaksi
**Table**( *Record1* [, *Record2*, ... ] )

* *Record* (yksi tai useampi) – Pakollinen. Taulukkoon lisättävät tietueet.

## <a name="examples"></a>Esimerkkejä
* Määritä luetteloruudun **[Items](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
  <br>**Table({Color:"red"}, {Color:"green"}, {Color:"blue"})**
  
    Luetteloruutu näyttää värit vaihtoehtoina.
* Lisää tekstivalikoima ja määritä sen **[Items](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:<br>
  **Table({Item:"Violin123", Location:"France", Owner:"Fabrikam"}, {Item:"Violin456", Location:"Chile"})**
  
    Valikoima näyttää kaksi tietuetta, jotka sisältävät kumpikin esineen nimen ja sijainnin. Vain yksi tietue sisältää omistajan nimen.


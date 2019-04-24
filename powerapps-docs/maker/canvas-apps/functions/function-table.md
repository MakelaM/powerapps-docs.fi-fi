---
title: Taulukkofunktio | Microsoft Docs
description: PowerAppsin Table-funktion viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ec8f14e06852bac7e09527e49bfc363723c9ea1c
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61543460"
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

* *Record(s)* – Pakollinen. Taulukkoon lisättävät tietueet.

## <a name="examples"></a>Esimerkkejä
* Määritä luetteloruudun **[Items](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
  <br>**Table({Color:"red"}, {Color:"green"}, {Color:"blue"})**
  
    Luetteloruutu näyttää värit vaihtoehtoina.
* Lisää tekstivalikoima ja määritä sen **[Items](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:<br>
  **Table({Item:"Violin123", Location:"France", Owner:"Fabrikam"}, {Item:"Violin456", Location:"Chile"})**
  
    Valikoima näyttää kaksi tietuetta, jotka sisältävät kumpikin esineen nimen ja sijainnin. Vain yksi tietue sisältää omistajan nimen.


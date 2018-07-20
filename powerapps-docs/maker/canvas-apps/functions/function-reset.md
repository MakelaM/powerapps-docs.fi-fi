---
title: Reset-funktio | Microsoft Docs
description: PowerAppsin Reset-funktion viitetiedot, mukaan lukien syntaksi ja esimerkki
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/06/2017
ms.author: gregli
ms.openlocfilehash: d9d83ab85ada125ff681040b4badbb8abfaafac0
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39020350"
---
# <a name="reset-function-in-powerapps"></a>PowerAppsin Reset-funktio
Reset nollaa ohjausobjektin oletusarvoonsa hyläten kaikki käyttäjän tekemät muutokset.  

## <a name="description"></a>Kuvaus
**Reset**-funktio nollaa ohjausobjektin **Default**-ominaisuuden arvoon.  Kaikki käyttäjän muutokset hylätään.

Et voi nollata [**Valikoima**](../controls/control-gallery.md)- tai [**Muokkaa lomaketta**](../controls/control-form-detail.md) -ohjausobjektissa olevia ohjausobjekteja näiden ohjausobjektien ulkopuolelta.  Voit nollata ohjausobjekteja kaavoista ohjausobjekteilla, jotka ovat samassa valikoimassa tai lomakkeessa.  Voit myös nollata kaikki lomakkeen ohjausobjektit [**ResetForm**](function-form.md)-funktiolla. 

**Reset**-funktion käyttäminen on vaihtoehto syöttöohjausobjektien **Reset**-ominaisuuden kytkemiselle, ja funktion käyttö on yleensä suositeltavaa.  **Reset**-ominaisuus voi olla parempi vaihtoehto, jos useita ohjausobjekteja täytyy nollata yhdessä useiden kaavojen kautta.  **Reset**-ominaisuuden kytkeminen voidaan suorittaa [**Painike**](../controls/control-button.md)-ohjausobjektin kautta kaavalla **Reset = Button.Pressed** tai muuttujan kautta kaavalla **Reset = MyVar** ja kytkemällä **MyVar** kaavalla **Button.OnSelect = Set( MyVar, true ); Set( MyVar, false )**.    

Syöttöohjausobjektit nollataan myös, kun niiden **Default**-ominaisuutta muutetaan.

**Reset**-funktiolla ei ole palautusarvoa, ja voit käyttää sitä vain [toimintakaavojen](../working-with-formulas-in-depth.md) sisällä.

## <a name="syntax"></a>Syntaksi
**Reset**( *Control* )

* *Control* – Pakollinen. Nollattava ohjausobjekti.

## <a name="example"></a>Esimerkki
1. Lisää näytölle **Tekstisyöttö**-ohjausobjekti.  Sen nimi on oletuksena **TextInput1**, ja sen **Default**-ominaisuudeksi asetetaan **"Text input"**.
2. Kirjoita tekstikenttään uusi arvo.  
3. Lisää näytölle **Painike**-ohjausobjekti.
4. Määritä painikkeen **OnSelect**-ominaisuudeksi **Reset( TextInput1 )**.
5. Valitse painike.  Tämä voidaan suorittaa myös laatimisen aikana valitsemalla kohta läheltä ohjausobjektin päätyjä.
6. Tekstikentän sisältö palautuu **Default**-ominaisuuden arvoksi.


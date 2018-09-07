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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9c032c237018fbd564dd1143f20951dfb42d9795
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42832875"
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


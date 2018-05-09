---
title: Revert-funktio | Microsoft Docs
description: PowerAppsin Revert-funktion viitetiedot, mukaan lukien syntaksi ja esimerkki
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: 08cb0690904a4b63645828678232769b66a439a1
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="revert-function-in-powerapps"></a>PowerAppsin Revert-funktio
Lataa uudelleen ja poistaa virheet [tietolähteen](../working-with-data-sources.md) [tietueista](../working-with-tables.md#records).

## <a name="description"></a>Kuvaus
**Revert**-funktio lataa uudelleen koko tietolähteen tai yhden kyseisen tietolähteen tietueen. Näet muiden käyttäjien tekemät muutokset.

**Revert** poistaa myös palautettujen tietueiden virheet [taulukosta](../working-with-tables.md), jonka **[Errors](function-errors.md)**-funktio palautti.

Jos **[Errors](function-errors.md)**-funktio ilmoittaa ristiriidasta **[Patch](function-patch.md)**-funktion tai muun tietotoiminnon jälkeen, palauta kyseinen tietue **Revert**-funktiolla aloittamiseksi ristiriitaisella versiolla ja muutoksen uudelleensuorittamiseksi.

**Revert**-funktiolla ei ole paluuarvoa. Sitä voidaan käyttää vain [toimintakaavassa](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaksi
**Revert**( *Tietolähde* [, *Tietue* ] )

* *Tietolähde* – Pakollinen. Tietolähde, jonka haluat palauttaa.
* *Tietue* – Valinnainen.  Tietue, jonka haluat palauttaa.  Jos et määritä tietuetta, koko tietolähde palautetaan.

## <a name="example"></a>Esimerkki
Tässä esimerkissä palautetaan tietolähde nimeltä **IceCream**, jolla on aluksi tämän taulukon tiedot:

![](media/function-revert/icecream.png)

Käyttäjä muuttaa eri laitteella **Strawberry**-tietueen **Quantity**-ominaisuudeksi **400**.  Noin samaan aikaan sinä muutat saman tietueen samaksi ominaisuudeksi **500** tietämättä toisen käyttäjän muutoksesta.

Käytät **[Patch](function-patch.md)**-funktiota tietueen päivittämiseen:<br>
**Patch( IceCream, First( Filter( IceCream, Flavor = "Strawberry" ) ), { Quantity: 500 } )**

Tarkistat **[Errors](function-errors.md)**-taulukon ja näet virheen:

| Tietue | [Sarake](../working-with-tables.md#columns) | Viesti | Virhe |
| --- | --- | --- | --- |
| **{ ID: 1, Flavor: "Strawberry", Quantity: 300 }** |*tyhjä* |**"Tietuetta, jota yrität muokata, on muokannut toinen käyttäjä.  Palauta tietue ja yritä uudelleen."** |**ErrorKind.Conflict** |

**Error**-sarakkeen perusteella sinulla on **Lataa uudelleen** -painike, jonka **[OnSelect](../controls/properties-core.md)**-ominaisuus on tämä kaava:<br>
**Revert( IceCream, First( Filter( IceCream, Flavor = "Strawberry" ) ) )**

Kun olet valinnut **Lataa uudelleen** -painikkeen, **[Errors](function-errors.md)**-taulukko on [tyhjä](function-isblank-isempty.md) ja **Strawberry**-tietueen uusi arvo on ladattu:

![](media/function-revert/icecream-after.png)

Muutoksesi tehdään edellisen muutoksen päälle ja muutoksesi onnistuu, koska ristiriita on ratkaistu.

![](media/function-revert/icecream-success.png)


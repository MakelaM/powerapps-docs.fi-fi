---
title: Revert-funktio | Microsoft Docs
description: PowerAppsin Revert-funktion viitetiedot, mukaan lukien syntaksi ja esimerkki
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: c02bc4321498d28cbc664f144f1dc396e4052cbd
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39019706"
---
# <a name="revert-function-in-powerapps"></a>PowerAppsin Revert-funktio
Lataa uudelleen ja poistaa virheet [tietolähteen](../working-with-data-sources.md) [tietueista](../working-with-tables.md#records).

## <a name="description"></a>Kuvaus
**Revert**-funktio lataa uudelleen koko tietolähteen tai kyseisen tietolähteen yhden tietueen. Näet muiden käyttäjien tekemät muutokset.

**Revert** poistaa myös palautettujen tietueiden virheet [taulukosta](../working-with-tables.md), jonka **[Errors](function-errors.md)**-funktio palautti.

Jos **[Errors](function-errors.md)**-funktio ilmoittaa ristiriidasta **[Patch](function-patch.md)**-funktion tai muun tietotoiminnon jälkeen, palauta kyseinen tietue **Revert**-funktiolla aloittaaksesi ristiriitaisella versiolla ja muutoksen suorittamiseksi uudelleen.

**Revert**-funktiolla ei ole paluuarvoa. Sitä voidaan käyttää vain [toimintakaavassa](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaksi
**Revert**( *Tietolähde* [, *Tietue* ] )

* *Tietolähde* – pakollinen. Tietolähde, jonka haluat palauttaa.
* *Tietue* – Valinnainen.  Tietue, jonka haluat palauttaa.  Jos et määritä tietuetta, koko tietolähde palautetaan.

## <a name="example"></a>Esimerkki
Tässä esimerkissä palautetaan tietolähde nimeltä **IceCream**, jolla on aluksi tämän taulukon tiedot:

![](media/function-revert/icecream.png)

Käyttäjä muuttaa eri laitteella **Strawberry**-tietueen **Quantity**-ominaisuudeksi **400**.  Samaan aikaan sinä muutat saman tietueen samaksi ominaisuudeksi **500** tietämättä toisen käyttäjän muutoksesta.

Käytät **[Patch](function-patch.md)**-funktiota tietueen päivittämiseen:<br>
**Patch( IceCream, First( Filter( IceCream, Flavor = "Strawberry" ) ), { Quantity: 500 } )**

Tarkistat **[Errors](function-errors.md)**-taulukon ja näet virheen:

| Tietue | [Sarake](../working-with-tables.md#columns) | Viesti | Virhe |
| --- | --- | --- | --- |
| **{ ID: 1, Flavor: "Strawberry", Quantity: 300 }** |*tyhjä* |**"Toinen käyttäjä on muokannut tietuetta, jota yrität muokata.  Palauta tietue ja yritä uudelleen."** |**ErrorKind.Conflict** |

**Error**-sarakkeen perusteella sinulla on **Lataa uudelleen** -painike, jonka **[OnSelect](../controls/properties-core.md)**-ominaisuus on tämä kaava:<br>
**Revert( IceCream, First( Filter( IceCream, Flavor = "Strawberry" ) ) )**

Kun olet valinnut **Lataa uudelleen** -painikkeen, **[Errors](function-errors.md)**-taulukko on [tyhjä](function-isblank-isempty.md) ja **Strawberry**-tietueen uusi arvo on ladattu:

![](media/function-revert/icecream-after.png)

Muutoksesi tehdään edellisen muutoksen päälle ja muutoksesi onnistuu, koska ristiriita on ratkaistu.

![](media/function-revert/icecream-success.png)


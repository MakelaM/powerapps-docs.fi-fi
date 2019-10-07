---
title: Refresh-funktio | Microsoft Docs
description: Tietoa PowerAppsin Refresh-funktiosta, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/21/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 72fafd2b55237dc4804c50c26530fddb763d9623
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984289"
---
# <a name="refresh-function-in-powerapps"></a>PowerAppsin Refresh-funktio
Päivittää [tietolähteen](../working-with-data-sources.md) [tietueita](../working-with-tables.md#records).

## <a name="description"></a>Kuvaus
**Refresh**-funktio noutaa tietolähteestä tuoreen kopion.  Näet muiden käyttäjien tekemät muutokset.

**Refresh**-funktiolla ei ole palautusarvoa, ja voit käyttää sitä vain [toimintakaavojen](../working-with-formulas-in-depth.md) sisällä.

## <a name="syntax"></a>Syntaksi
**Refresh**( *DataSource* )

* *DataSource* – Pakollinen. Tietolähde, jonka haluat päivittää.

## <a name="example"></a>Esimerkki
Tässä esimerkissä päivitetään tietolähde nimeltä **IceCream**, jolla on aluksi nämä tiedot:

![](media/function-refresh/icecream.png)

Käyttäjä muuttaa eri laitteella **Strawberry**-tietueen **Quantity**-ominaisuudeksi **400**.  Et näe tätä muutosta ennen kuin tämä kaava toteutetaan:

**Refresh( IceCream )**

Kun tämä kaava on toteutettu, **IceCream**-tietolähteeseen liitetyt valikoimat näyttävät **Strawberry**-tietueen päivitetyn arvon:

![](media/function-refresh/icecream-after.png)


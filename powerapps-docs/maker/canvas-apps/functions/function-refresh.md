---
title: Refresh-funktio | Microsoft Docs
description: Tietoa PowerAppsin Refresh-funktiosta, mukaan lukien syntaksi ja esimerkkejä
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
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: 631b0c8fbfc98d73cf1d944c2a0f3933f8f10c11
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
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


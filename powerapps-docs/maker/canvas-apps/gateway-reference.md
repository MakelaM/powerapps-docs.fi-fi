---
title: Paikallinen tietoyhdyskäytävä | Microsoft Docs
description: Tämä artikkeli on yleiskatsaus Powerappsin paikalliseen tietoyhdyskäytävään.
author: arthiriyer
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/16/2019
ms.author: arthii
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1a5e27b59f1b19460933b61bb92b312a4b12b6f5
ms.sourcegitcommit: 6984ce43cc5653ccb957219d2a687907ebb5520c
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/18/2019
ms.locfileid: "72561009"
---
# <a name="what-is-an-on-premises-data-gateway"></a>Mikä on paikallinen tietoyhdyskäytävä?

Paikallinen tietoyhdyskäytävä toimii siltana, joka tarjoaa nopean ja turvallisen tiedon siirron paikallisten tietojen (tiedot, jotka eivät ole pilvi palvelussa) ja useiden Microsoftin pilvi palveluiden välillä. Näitä pilvi palveluita ovat Power BI, PowerApps, Microsoft Flow, Azure Analysis Services ja Azure Logic Apps. Yhdyskäytävän avulla organisaatiot voivat pitää tieto kannat ja muut tieto lähteet omissa paikallisissa verkossaan, mutta käyttävät näitä paikallisia tietoja turvallisesti pilvi palveluissa.

## <a name="how-the-gateway-works"></a>Yhdyskäytävän toiminta

![Yhdyskäytävän yleiskatsaus](media/gateway-reference/on-premises-data-gateway.png)

Lisä tietoja yhdyskäytävän toiminnasta [on kohdassa Paikallinen tietoyhdyskäytävän arkkitehtuuri](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Yhdyskäytävien tyypit

Yhdyskäytäviä on kaksi eri tyyppiä, joista kukin on eri skenaariossa:

- **Paikallisen tietoyhdyskäytävän** avulla useat käyttäjät voivat muodostaa yhteyden useisiin paikallisiin tieto lähteisiin. Voit käyttää paikallista tietoyhdyskäytävää kaikilla tuetuilla palveluilla yhdellä yhdyskäytävän asennuksella. Tämä yhdyskäytävä sopii hyvin monimutkaisiin tilanteisiin, joissa useat käyttäjät ovat käyttänyt useita tieto lähteitä.

- **Paikallisen tietoyhdyskäytävän (henkilökohtainen tila)** avulla yksi käyttäjä voi muodostaa yhteyden lähteisiin, eikä sitä voi jakaa muiden kanssa. Paikallista tietoyhdyskäytävää (henkilökohtainen tila) voi käyttää vain Power BI kanssa. Tämä yhdyskäytävä sopii hyvin tilanteisiin, joissa olet ainoa raporttien luova henkilö, eikä sinun tarvitse kertoa mitään tieto lähteitä muiden kanssa.

## <a name="use-a-gateway"></a>Käytä yhdyskäytävää

Yhdyskäytävän käyttämiseen on neljä päävaihetta.

1. [Lataa ja asenna yhdyskäytävä](/data-integration/gateway/service-gateway-install) paikalliseen tieto koneeseen.
2. [Määritä](/data-integration/gateway/service-gateway-app) yhdyskäytävä palo muurin ja muiden verkko tarpeiden mukaan.
3. [Lisää yhdyskäytävän järjestelmänvalvojia](/data-integration/gateway/service-gateway-manage) , jotka voivat myös hallita ja hallita muita verkko vaatimuksia.
4. [Suorita yhdyskäytävän vian määritys](/data-integration/gateway/service-gateway-tshoot) virheiden varalta.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Asenna paikallinen tietoyhdyskäytävä](/data-integration/gateway/service-gateway-install)
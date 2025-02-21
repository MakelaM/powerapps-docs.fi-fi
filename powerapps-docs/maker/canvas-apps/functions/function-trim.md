---
title: Trim- ja TrimEnds-funktiot | Microsoft Docs
description: PowerAppsin Trim- ja TrimEnds-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkki
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 09/09/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 79f035271b2a98faf6ddb7bba716c7107e311183
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71991929"
ms.PowerAppsDecimalTransform: true
---
# <a name="trim-and-trimends-functions-in-powerapps"></a>Trim- ja TrimEnds-funktiot PowerAppsissa
Poistavat ylimääräiset välilyönnit tekstimerkkijonosta.

## <a name="description"></a>Kuvaus
**Trim**-funktio poistaa tekstimerkkijonosta kaikki välilyönnit lukuun ottamatta yksittäisiä välejä sanojen välillä.  

**TrimEnds**-funktio poistaa kaikki välilyönnit tekstimerkkijonon alusta ja lopusta, mutta jättää sanojen väliset välilyönnit ennalleen.

Jos määrität yksittäisen tekstimerkkijonon, molempien funktioiden palautusarvo on merkkijono, josta on poistettu kaikki ylimääräiset välilyönnit. Jos määrität yksisarakkeisen, merkkijonoja sisältävän [taulukon](../working-with-tables.md), palautusarvo on yksisarakkeinen taulukko, joka sisältää merkkijonoja, joista on poistettu välilyönnit. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [taulukoiden käyttö](../working-with-tables.md) mukaan.

Sanojen välisiä välilyöntejä poistava **Trim**-funktio on yhdenmukainen samannimisen Microsoft Excelin funktion kanssa. **TrimEnds**-funktio on kuitenkin yhdenmukainen sellaisten ohjelmointityökalujen kanssa, jotka poistavat välilyöntejä vain kunkin merkkijonon alusta ja lopusta.

## <a name="syntax"></a>Syntaksi
**Trim**( *String* )<br>**TrimEnds**( *String* )

* *String* – Pakollinen. Tekstimerkkijono, josta välilyönnit poistetaan.

**Trim**( *SingleColumnTable* )<br>**TrimEnds**( *SingleColumnTable* )

* *SingleColumnTable* – Pakollinen. Yksisarakkeinen taulukko merkkijonoista, joista poistetaan välilyöntejä.

## <a name="example"></a>Esimerkki

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Trim(&nbsp;"&nbsp;&nbsp;&nbsp;Hei&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maailma&nbsp;&nbsp;&nbsp;"&nbsp;)** |Poistaa kaikki välilyönnit merkkijonon alusta ja lopusta sekä ylimääräiset välilyönnit merkkijonon sisältä. |”Hei maailma” |
| **TrimEnds(&nbsp;"&nbsp;&nbsp;&nbsp;Hei&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maailma&nbsp;&nbsp;&nbsp;"&nbsp;)** |Poistaa kaikki välilyönnit merkkijonon alusta ja lopusta. |"Hei&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maailma" |

Seuraavissa esimerkeissä käytetään yksisarakkeista kokoelmaa, jonka nimi on **Spaces** ja joka sisältää nämä merkkijonot:

![](media/function-trim/input-strings.png)

Luo tämä kokoelma määrittämällä **[Painike](../controls/control-button.md)** -ohjausobjektin **OnSelect**-ominaisuudeksi tämä kaava avaamalla esikatselutila ja napsauttamalla tai napauttamalla painiketta:
<br>**ClearCollect( Spaces; [ "&nbsp;&nbsp;&nbsp;Jane&nbsp;&nbsp;&nbsp;Doe&nbsp;&nbsp;&nbsp;"; "&nbsp;&nbsp;&nbsp;&nbsp;Jack&nbsp;&nbsp;&nbsp;and&nbsp;&nbsp;&nbsp;Jill"; "Already&nbsp;trimmed"; "&nbsp;&nbsp;&nbsp;Venus,&nbsp;&nbsp;&nbsp;Earth,&nbsp;&nbsp;&nbsp;Mars&nbsp;&nbsp;"; "Oil&nbsp;and&nbsp;Water&nbsp;&nbsp;&nbsp;" ] )**

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Trim(&nbsp;Spaces&nbsp;)** |Poistaa kaikki välilyönnit jokaisen merkkijonon alusta ja lopusta sekä ylimääräiset välilyönnit merkkijonon sisältä **Spaces**-kokoelmassa. |<style> img { max-width: none } </style> ![](media/function-trim/output-trim.png) |
| **TrimEnds(&nbsp;Spaces&nbsp;)** |Poistaa kaikki välilyönnit jokaisen merkkijonon alusta ja lopusta **Spaces**-kokoelmassa. |<style> img { max-width: none } </style> ![](media/function-trim/output-trimends.png) |

> [!NOTE]
> Ylimääräiset välilyönnit eivät näy, jos näytät kokoelman napsauttamalla tai napauttamalla kohtaa **Kokoelmat** **Tiedosto**-valikossa. Voit tarkistaa merkkijonon pituuden käyttämällä **[Len](function-len.md)** -funktiota.


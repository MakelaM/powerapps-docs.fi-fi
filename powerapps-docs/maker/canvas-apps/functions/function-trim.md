---
title: Trim- ja TrimEnds-funktiot | Microsoft Docs
description: PowerAppsin Trim- ja TrimEnds-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkki
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
ms.date: 09/09/2016
ms.author: gregli
ms.openlocfilehash: 7dc9372071b905cf2b95f7355864276d8f344d9c
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="trim-and-trimends-functions-in-powerapps"></a>Trim- ja TrimEnds-funktiot PowerAppsissa
Poistaa ylimääräiset välilyönnit tekstimerkkijonosta.

## <a name="description"></a>Kuvaus
**Trim**-funktio poistaa tekstimerkkijonosta kaikki välilyönnit lukuun ottamatta yksittäisiä välejä sanojen välillä.  

**TrimEnds**-funktio poistaa kaikki välilyönnit tekstimerkkijonon alusta ja lopusta, mutta jättää sanojen väliset välilyönnit ennalleen.

Jos määrität yksittäisen tekstimerkkijonon, molempien funktioiden palautusarvo on merkkijono, josta on poistettu kaikki ylimääräiset välilyönnit. Jos määrität yksisarakkeisen, merkkijonoja sisältävän [taulukon](../working-with-tables.md), palautusarvo on yksisarakkeinen taulukko, joka sisältää merkkijonoja, joista on poistettu välilyönnit. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [taulukoiden käyttö](../working-with-tables.md) mukaan.

Sanojen välisiä välilyöntejä poistava **Trim**-funktio on yhdenmukainen on samannimisen Microsoft Excelin funktion kanssa. **TrimEnds**-funktio on kuitenkin yhdenmukainen sellaisten ohjelmointityökalujen kanssa, jotka poistavat välilyöntejä vain kunkin merkkijonon alusta ja lopusta.

## <a name="syntax"></a>Syntaksi
**Trim**( *Merkkijono* )<br>**TrimEnds**( *Merkkijono* )

* *String* – Pakollinen. Tekstimerkkijono, josta välilyönnit poistetaan.

**Trim**( *YksiSarakkeinenTaulukko* )<br>**TrimEnds**( *YksiSarakkeinenTaulukko* )

* *YksiSarakkeinenTaulukko* – pakollinen. Yksisarakkeinen taulukko merkkijonoista, joista poistetaan välilyöntejä.

## <a name="example"></a>Esimerkki
| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Trim(&nbsp;"&nbsp;&nbsp;&nbsp;Hei&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maailma&nbsp;&nbsp;&nbsp;"&nbsp;)** |Poistaa kaikki välilyönnit merkkijonon alusta ja lopusta sekä ylimääräiset välilyönnit merkkijonon sisältä. |”Hei maailma” |
| **TrimEnds(&nbsp;"&nbsp;&nbsp;&nbsp;Hei&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maailma&nbsp;&nbsp;&nbsp;"&nbsp;)** |Poistaa kaikki välilyönnit merkkijonon alusta ja lopusta. |”Hei&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maailma” |

Seuraavissa esimerkeissä käytetään yksisarakkeista kokoelmaa, jonka nimi on **Spaces** ja joka sisältää nämä merkkijonot:

![](media/function-trim/input-strings.png)

Luo tämä kokoelma määrittämällä **[painike](../controls/control-button.md)**-ohjausobjektin **OnSelect**-ominaisuudeksi tämä kaava avaamalla esikatselutila ja napsauttamalla tai napauttamalla painiketta:
<br>**ClearCollect( Spaces, [ "&nbsp;&nbsp;&nbsp;Jane&nbsp;&nbsp;&nbsp;Doe&nbsp;&nbsp;&nbsp;", "&nbsp;&nbsp;&nbsp;&nbsp;Jack&nbsp;&nbsp;&nbsp;and&nbsp;&nbsp;&nbsp;Jill", "Already&nbsp;trimmed", "&nbsp;&nbsp;&nbsp;Venus,&nbsp;&nbsp;&nbsp;Earth,&nbsp;&nbsp;&nbsp;Mars&nbsp;&nbsp;", "Oil&nbsp;and&nbsp;Water&nbsp;&nbsp;&nbsp;" ] )**

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Trim(&nbsp;Spaces&nbsp;)** |Poistaa kaikki välilyönnit jokaisen merkkijonon alusta ja lopusta sekä ylimääräiset välilyönnit merkkijonon sisältä **Spaces**-kokoelmassa. |<style> img { max-width: none } </style> ![](media/function-trim/output-trim.png) |
| **TrimEnds(&nbsp;Spaces&nbsp;)** |Poistaa kaikki välilyönnit jokaisen merkkijonon alusta ja lopusta **Spaces**-kokoelmassa. |<style> img { max-width: none } </style> ![](media/function-trim/output-trimends.png) |

> [!NOTE]
> Ylimääräiset välilyönnit eivät näy, jos näytät kokoelman napsauttamalla tai napauttamalla kohtaa **Kokoelmat** **Tiedosto**-valikossa. Voit tarkistaa merkkijonon pituuden käyttämällä **[Len](function-len.md)** funktiota.


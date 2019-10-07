---
title: Split-funktio | Microsoft Docs
description: Tietoa PowerAppsin Split-funktion ominaisuuksista, kuten syntaksista, sekä joitakin esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm tapanm
ms.date: 09/14/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 72f92477cc8c942ee0274267c5bcb13094681873
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984136"
---
# <a name="split-function-in-powerapps"></a>PowerAppsin Split-funktio
Jakaa merkkijonon osamerkkijonojen taulukoksi.

## <a name="description"></a>Kuvaus
**Split**-funktio jakaa merkkijonon osamerkkijonojen taulukoksi.  **Split**-funktiota käytetään pilkulla eroteltaviin luetteloihin, vinoviivalla jaettuihin päivämääriin tai erottamaan merkkijonot jollain muulla määritetyllä erottimella.  

Merkkijono jaetaan osiin käyttämällä erotinta.  Erotin voi muodostua nollasta merkistä, yhdestä merkistä tai useammasta merkistä, jotka yhdistetään kokonaisuutena merkkijonoon.  Jos käytetään nollapituutta eli *tyhjää* merkkijonoa, kaikki merkit erotetaan toisistaan.  Yhdistettyjä erotinmerkkejä ei palauteta tuloksen mukana.  Jos erottimelle ei löydy vastinetta, koko merkkijono palautetaan yhtenä tuloksena.

Käytä **[Conpat](function-concatenate.md)** -funktiolla merkki jonon yhdistämistä uudelleen ilman erottimia. 
 
Jaa merkki jono käyttämällä **[Matchall](function-ismatch.md)** -funktiolla säännönmukaista lauseketta.

Esimerkeissä näytetään, miten **jakoa** voidaan käyttää **[ensimmäisten](function-first-last.md)** ja **[viimeisten](function-first-last.md)** funktioiden kanssa yksittäisen erotellun alimerkkijonon poimiminen.  **[Match](function-ismatch.md)** -funktiolla on usein suppeampi ja tehokkaampi vaihto ehto säännöllisillä lausekkeilla tutuille.

## <a name="syntax"></a>Syntaksi
**Split**( *Text*, *Separator* )

* *Text* – Pakollinen.  Jaettava teksti.
* *Separator* – Pakollinen.  Merkkijonon jakamiseen käytettävä erotin.  Voi olla nolla, yksi tai useampia merkkejä.

## <a name="examples"></a>Esimerkkejä

### <a name="basic-usage"></a>Peruskäyttö

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| `Split( "Apples, Oranges, Bananas", "," )` |Jakaa hedelmät erilleen pilkkuerottimen perusteella.  Jako perustuu vain pilkkuun, ei sitä seuraavaan välilyöntiin, joten tuloksena on välilyönti "&nbsp;Appelsiinit"- ja "&nbsp;Banaanit” -merkkijonojen välillä. |<style> img { max-width: none; } </style> ![](media/function-split/fruit1.png) |
| `TrimEnds( Split( "Apples, Oranges, Bananas", "," ) )` |Sama kuin edellisessä esimerkissä, mutta tässä tapauksessa **Split**-funktiolla aikaan saadussa yhden sarakkeen taulukossa on käytetty [**TrimEnds**-funktiota](function-trim.md), joka poisti välilyönnin. Olisimme voineet käyttää myös erotinta **",&nbsp;"** , johon sisältyy myös pilkun perässä oleva välilyönti, mutta se ei toimi kunnolla, jos välilyöntiä ei ole tai niitä on kaksi. |<style> img { max-width: none; } </style> ![](media/function-split/fruit2.png) |
| `Split( "08/28/17", "/" )` |Jakaa päivämäärän osat käyttämällä erottimena vinoviivaa. |<style> img { max-width: none; } </style> ![](media/function-split/date.png) |

### <a name="different-delimiters"></a>Eri erottimet

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| `Split( "Hello, World", "," )` |Jakaa sanat toisistaan käyttämällä erottimena pilkkua.  Toisen tuloksen alussa on välilyönti, koska pilkun perässä oli välilyönti. |<style> img { max-width: none; } </style> ![](media/function-split/comma.png) |
| `Split( "Hello, World", "o" )` |Jakaa merkkijonon käyttämällä erottimena kirjainta ”o”. |<style> img { max-width: none; } </style> ![](media/function-split/o.png) |
| `Split( "Hello, World", "l" )` |Jakaa merkkijonon käyttämällä erottimena yksittäistä merkkiä ”l”. Koska kahden **l**-kirjaimen välissä ei ollut merkkejä **Hello**-sanassa, ohjelma palautti *tyhjän* arvon. |<style> img { max-width: none; } </style> ![](media/function-split/l.png) |
| `Split( "Hello, World", "ll" )` |Jakaa merkkijonon käyttämällä erottimena kaksoismerkkiä ”lI”. |<style> img { max-width: none; } </style> ![](media/function-split/ll.png) |
| `Split( "Hello, World", "%" )` |Jakaa merkkijonon käyttämällä erottimena prosenttimerkkiä. Koska tätä erotinta ei näy merkkijonossa, koko merkkijono palautetaan yhtenä tuloksena. |<style> img { max-width: none; } </style> ![](media/function-split/percent.png) |
| `Split( "Hello, World", "" )` |Jakaa merkkijonon käyttämällä erottimena tyhjää merkkijonoa (nolla merkkiä). Tämä erottaa merkkijonon jokaisen merkin toisistaan. |<style> img { max-width: none; } </style> ![](media/function-split/none.png) |

### <a name="substring-extraction"></a>Alimerkkijonon poiminta

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| `First( Split( Last( Split( "Bob Jones <bob.jones@contoso.com>", "<" ) ).Result, ">" ) ).Result` | Jakaa merkki jonon toisistaan avaamisen erottimen (<) perusteella ja poimii erottimen oikealla puolella olevan merkki jonon **viimeiseen**.  Kaava jakaa tämän tuloksen loppu erottimen (>) perusteella ja poimii erottimen vasemmalla puolella olevan merkki jonon **oikealla**. | "bob.jones@contoso.com" |
| `Match( "Bob Jones <bob.jones@contoso.com>", "<(?<email>.+)>" ).email` | Suorittaa saman erottimen perustuvan poiminnan viimeisenä esimerkkinä, mutta käyttää sen sijaan **Match** -funktiota ja säännönmukaista lauseketta. | "bob.jones@contoso.com" |


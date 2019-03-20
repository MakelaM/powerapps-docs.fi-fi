---
title: Split-funktio | Microsoft Docs
description: Tietoa PowerAppsin Split-funktion ominaisuuksista, kuten syntaksista, sekä joitakin esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta anneta
ms.date: 08/28/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b8f8dc0d354dd17fedd16524fed0f358b70839d4
ms.sourcegitcommit: f5013108140276b3d66a9dce13a061df89609d26
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/24/2019
ms.locfileid: "57798394"
---
# <a name="split-function-in-powerapps"></a>PowerAppsin Split-funktio
Jakaa merkkijonon osamerkkijonojen taulukoksi.

## <a name="description"></a>Kuvaus
**Split**-funktio jakaa merkkijonon osamerkkijonojen taulukoksi.  **Split**-funktiota käytetään pilkulla eroteltaviin luetteloihin, vinoviivalla jaettuihin päivämääriin tai erottamaan merkkijonot jollain muulla määritetyllä erottimella.  

Merkkijono jaetaan osiin käyttämällä erotinta.  Erotin voi muodostua nollasta merkistä, yhdestä merkistä tai useammasta merkistä, jotka yhdistetään kokonaisuutena merkkijonoon.  Jos käytetään nollapituutta eli *tyhjää* merkkijonoa, kaikki merkit erotetaan toisistaan.  Yhdistettyjä erotinmerkkejä ei palauteta tuloksen mukana.  Jos erottimelle ei löydy vastinetta, koko merkkijono palautetaan yhtenä tuloksena.

Voit koota merkkijonon uudelleen käyttämällä **[Concat](function-concatenate.md)**-funktiota (ilman erottimia). Käytä **[MatchAll](function-ismatch.md)** funktiolla merkkijonon osan säännönmukainen lauseke, jonka (joissakin tapauksissa) avulla voit jakaa merkkijonon käyttämällä. 

## <a name="syntax"></a>Syntaksi
**Split**( *Text*, *Separator* )

* *Text* – Pakollinen.  Jaettava teksti.
* *Separator* – Pakollinen.  Merkkijonon jakamiseen käytettävä erotin.  Voi olla nolla, yksi tai useampia merkkejä.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Split( "Omenat,&nbsp;Appelsiinit,&nbsp;Banaanit", "," )** |Jakaa hedelmät erilleen pilkkuerottimen perusteella.  Jako perustuu vain pilkkuun, ei sitä seuraavaan välilyöntiin, joten tuloksena on välilyönti "&nbsp;Appelsiinit"- ja "&nbsp;Banaanit” -merkkijonojen välillä. |<style> img { max-width: none; } </style> ![](media/function-split/fruit1.png) |
| **TrimEnds( Split( "Omenat,&nbsp;Appelsiinit,&nbsp;Banaanit, "," ) )** |Sama kuin edellisessä esimerkissä, mutta tässä tapauksessa **Split**-funktiolla aikaan saadussa yhden sarakkeen taulukossa on käytetty [**TrimEnds**-funktiota](function-trim.md), joka poisti välilyönnin. Olisimme voineet käyttää myös erotinta **",&nbsp;"**, johon sisältyy myös pilkun perässä oleva välilyönti, mutta se ei toimi kunnolla, jos välilyöntiä ei ole tai niitä on kaksi. |<style> img { max-width: none; } </style> ![](media/function-split/fruit2.png) |
| **Split( "08/28/17", "/" )** |Jakaa päivämäärän osat käyttämällä erottimena vinoviivaa. |<style> img { max-width: none } </style> ![](media/function-split/date.png) |
| **Split( "Hello,&nbsp;World", "," )** |Jakaa sanat toisistaan käyttämällä erottimena pilkkua.  Toisen tuloksen alussa on välilyönti, koska pilkun perässä oli välilyönti. |<style> img { max-width: none; } </style> ![](media/function-split/comma.png) |
| **Split( "Hello,&nbsp;World", "o" )** |Jakaa merkkijonon käyttämällä erottimena kirjainta ”o”. |<style> img { max-width: none; } </style> ![](media/function-split/o.png) |
| **Split( "Hello,&nbsp;World", "l" )** |Jakaa merkkijonon käyttämällä erottimena yksittäistä merkkiä ”l”. Koska kahden **l**-kirjaimen välissä ei ollut merkkejä **Hello**-sanassa, ohjelma palautti *tyhjän* arvon. |<style> img { max-width: none; } </style> ![](media/function-split/l.png) |
| **Split( "Hello,&nbsp;World", "ll" )** |Jakaa merkkijonon käyttämällä erottimena kaksoismerkkiä ”lI”. |<style> img { max-width: none; } </style> ![](media/function-split/ll.png) |
| **Split( "Hello,&nbsp;World", "%" )** |Jakaa merkkijonon käyttämällä erottimena prosenttimerkkiä. Koska tätä erotinta ei näy merkkijonossa, koko merkkijono palautetaan yhtenä tuloksena. |<style> img { max-width: none; } </style> ![](media/function-split/percent.png) |
| **Split( "Hello,&nbsp;World", "" )** |Jakaa merkkijonon käyttämällä erottimena tyhjää merkkijonoa (nolla merkkiä). Tämä erottaa merkkijonon jokaisen merkin toisistaan. |<style> img { max-width: none; } </style> ![](media/function-split/none.png) |


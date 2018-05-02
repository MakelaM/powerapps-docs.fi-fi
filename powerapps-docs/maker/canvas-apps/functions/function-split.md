---
title: Split-funktio | Microsoft Docs
description: '*Tietoa PowerAppsin Split-funktion ominaisuuksista, kuten syntaksista, sekä joitakin esimerkkejä'
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
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: e1953767c40edbe27a232678bdeaab8cebfdea17
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/12/2018
---
# <a name="split-function-in-powerapps"></a>PowerAppsin Split-funktio
Jakaa merkkijonon osamerkkijonojen taulukoksi.

## <a name="description"></a>Kuvaus
**Split**-funktio jakaa merkkijonon osamerkkijonojen taulukoksi.  **Split**-funktiota käytetään pilkulla eroteltaviin luetteloihin, vinoviivalla jaettuihin päivämääriin tai erottamaan merkkijonot jollain muulla määritetyllä erottimella.  

Merkkijono jaetaan osiin käyttämällä erotinta.  Erotin voi muodostua nollasta merkistä, yhdestä merkistä tai useammasta merkistä, jotka yhdistetään kokonaisuutena merkkijonoon.  Jos käytetään nollapituutta eli *tyhjää* merkkijonoa, kaikki merkit erotetaan toisistaan.  Yhdistettyjä erotinmerkkejä ei palauteta tuloksen mukana.  Jos erottimelle ei löydy vastinetta, koko merkkijono palautetaan yhtenä tuloksena.

Voit koota merkkijonon uudelleen käyttämällä **[Concat](function-concatenate.md)**-funktiota (ilman erottimia).  

## <a name="syntax"></a>Syntaksi
**Split**( *teksti*, *erotin* )

* *Teksti* – Pakollinen.  Jaettava teksti.
* *Erotin* – Pakollinen.  Merkkijonon jakamiseen käytettävä erotin.  Voi olla nolla, yksi tai useampia merkkejä.

## <a name="examples"></a>Esimerkkejä
| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Split( "Omenat,&nbsp;Appelsiinit,&nbsp;Banaanit", "," )** |Jakaa hedelmät erilleen pilkkuerottimen perusteella.  Jako perustuu vain pilkkuun, ei sitä seuraavaan välilyöntiin, joten tuloksena on välilyönti ”&nbsp;Appelsiinit"- ja "&nbsp;Banaanit” -merkkijonojen välillä. |<style> img { max-width: none; } </style> ![](media/function-split/fruit1.png) |
| **TrimEnds( Split( "Omenat,&nbsp;Appelsiinit,&nbsp;Banaanit, "," ) )** |Sama kuin edellisessä esimerkissä, mutta tässä tapauksessa **Split**-funktiolla aikaan saadussa yhden sarakkeen taulukossa on käytetty [**TrimEnds**-funktiota](function-trim.md), joka poisti välilyönnin. Olisimme voineet käyttää myös erotinta **",&nbsp;"**, johon sisältyy myös pilkun perässä oleva välilyönti, mutta se ei toimi kunnolla, jos välilyöntiä ei ole tai niitä on kaksi. |<style> img { max-width: none; } </style> ![](media/function-split/fruit2.png) |
| **Split( "08/28/17", "/" )** |Jakaa päivämäärän osat käyttämällä erottimena vinoviivaa. |<style> img { max-width: none } </style> ![](media/function-split/date.png) |
| **Split( "Hei,&nbsp;maailma", "," )** |Jakaa sanat toisistaan käyttämällä erottimena pilkkua.  Toisen tuloksen alussa on välilyönti, koska pilkun perässä oli välilyönti. |<style> img { max-width: none; } </style> ![](media/function-split/comma.png) |
| **Split( "Hello,&nbsp;World", "o" )** |Jakaa merkkijonon käyttämällä erottimena kirjainta ”o”. |<style> img { max-width: none; } </style> ![](media/function-split/o.png) |
| **Split( "Hei,&nbsp;maailma", "l" )** |Jakaa merkkijonon käyttämällä erottimena yksittäistä merkkiä ”l”. Koska kahden **l**-kirjaimen välissä ei ollut merkkejä **Hello**-sanassa, ohjelma palautti *tyhjän* arvon. |<style> img { max-width: none; } </style> ![](media/function-split/l.png) |
| **Split( "Hello,&nbsp;World", "ll" )** |Jakaa merkkijonon käyttämällä erottimena kaksoismerkkiä ”lI”. |<style> img { max-width: none; } </style> ![](media/function-split/ll.png) |
| **Split( "Hello,&nbsp;World", "%" )** |Jakaa merkkijonon käyttämällä erottimena prosenttimerkkiä. Koska tätä erotinta ei näy merkkijonossa, koko merkkijono palautetaan yhtenä tuloksena. |<style> img { max-width: none; } </style> ![](media/function-split/percent.png) |
| **Split( "Hello,&nbsp;World", "" )** |Jakaa merkkijonon käyttämällä erottimena tyhjää merkkijonoa (nolla merkkiä). Tämä erottaa merkkijonon jokaisen merkin toisistaan. |<style> img { max-width: none; } </style> ![](media/function-split/none.png) |


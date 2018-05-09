---
title: Average-, Max-, Min-, StdevP-, Sum- ja VarP-funktiot | Microsoft Docs
description: PowerAppsin Average-, Max-, Min-, StdevP-, Sum- ja VarP-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 08/15/2017
ms.author: gregli
ms.openlocfilehash: e488383acbd163383079b5078e464cab89e677ad
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="average-max-min-stdevp-sum-and-varp-functions-in-powerapps"></a>PowerAppsin Average-, Max-, Min-, StdevP-, Sum- ja VarP-funktiot
Koostefunktiot, jotka koostavat numerojoukon.

## <a name="description"></a>Kuvaus
**Average**-funktio laskee argumenttiensa keskiarvon.

**Max**-funktion etsii enimmäisarvon.

**Min**-funktion etsii vähimmäisarvon.

**Sum**-funktio laskee argumenttiensa summan.

**StdevP**-funktio laskee argumenttiensa keskihajonnan.

**VarP**-funktio laskee argumenttiensa varianssin.

Voit antaa arvot funktioille:

* Erillisinä argumentteina. Esimerkiksi **Sum( 1, 2, 3 )** palauttaa arvon 6.
* [Taulukkona](../working-with-tables.md) ja kaavana, joka suoritetaan taulukolle.  Kooste lasketaan kaavan arvoille joka [tietueelle](../working-with-tables.md#records).  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Nämä funktiot toimivat vain numeroarvojen kanssa. Muut arvotyypit, kuten merkkijonot ja tietueet, jätetään huomiotta. Käytä **[Value](function-value.md)**-funktiota muuntamaan merkkijono luvuksi.

**Average**-, **Max**-, **Min**- ja **Sum**-funktiot voidaan delegoida, kun niitä käytetään [tietolähteen kanssa, joka tukee näiden funktioiden delegointia](../delegation-list.md).  **StdevP**- ja **VarP**-funktioita ei kuitenkaan voi delegoida millään tietolähteellä.  Jos delegointia ei tueta, vain tietojen ensimmäinen osa noudetaan ja sen jälkeen funktio otetaan käyttöön paikallisesti.  Tulos ei ehkä vastaa koko tarinaa.  Muokkaamisen aikana näyttöön ilmestyy sininen piste, joka muistuttaa tästä rajoituksesta ja ehdottaa mahdollisia vaihtoehtoja, joita voi delegoida. Lisätietoja on artikkelissa [delegoinnin yleiskatsaus](../delegation-overview.md).

## <a name="syntax"></a>Syntaksi
**Average**( *NumeroKaava1*, [ *NumeroKaava2*, ... ] )<br>**Max**( *NumeroKaava1*, [ *NumeroKaava2*, ... ] )<br>**Min**( *NumeroKaava1*, [ *NumeroKaava2*, ... ] )<br>**Sum**( *NumeroKaava1*, [ *NumeroKaava2*, ... ] )<br>**StdevP**( *NumeroKaava1*, [ *NumeroKaava2*, ... ] )<br>**VarP**( *NumeroKaava1*, [ *NumeroKaava2*, ... ] )

* *NumeroKaava(t)* – Pakollinen.  Lukuarvot, joille toiminto suoritetaan.

**Average**( *Taulukko*, *NumeroKaava* )<br>**Max**( *Taulukko*, *NumeroKaava* )<br>**Min**( *Taulukko*, *NumeroKaava* )<br>**Sum**( *Taulukko*, *NumeroKaava* )<br>**StdevP**( *Taulukko*, *NumeroKaava* )<br>**VarP**( *Taulukko*, *NumeroKaava* )

* *Taulukko* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
* *NumeroKaava* – Pakollinen. Kaava, jolla lasketaan arvot kullekin tietueelle. Tämän kaavan tulosta käytetään koostamiseen. Voit käyttää taulukon sarakkeita kaavassa.

## <a name="examples"></a>Esimerkkejä
### <a name="step-by-step"></a>Vaihe vaiheelta
Oletetaan, että käytössä on [tietolähde](../working-with-data-sources.md) nimeltä **Sales**, joka sisältää sarakkeen **CostPerUnit** ja sarakkeen **UnitsSold**, ja asetat selitteen **[Text](../controls/properties-core.md)**-ominaisuudeksi tämän kaavan:<br>
**Sum(Sales, CostPerUnit * UnitsSold)**

Selite näyttää kokonaismyynnit kertomalla tietueiden sarakkeiden arvot ja lisäämällä kaikkien tietueiden tulokset yhteen:<br>![Kokonaismyynnin laskenta myydyistä yksiköistä ja yksikköhinnasta](./media/function-aggregates/total-sales.png)

Katsotaan eri esimerkkiä, jossa käytössä on liukusäätimet nimeltä **Slider1**, **Slider2** ja **Slider3** ja selite, jonka **[Text](../controls/properties-core.md)**-ominaisuus on tämä kaava:<br>
**Sum(Slider1.Value, Slider2.Value, Slider3.Value)**

Selite näyttää kaikkien näiden liukusäädinten asetusten summan.


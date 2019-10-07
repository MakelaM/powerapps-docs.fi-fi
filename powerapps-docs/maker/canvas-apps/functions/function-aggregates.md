---
title: Average-, Max-, Min-, StdevP-, Sum- ja VarP-funktiot | Microsoft Docs
description: PowerAppsin Average-, Max-, Min-, StdevP-, Sum- ja VarP-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 08/15/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9c11c8e689254de1551bd35661d2768407cf4d6f
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985537"
---
# <a name="average-max-min-stdevp-sum-and-varp-functions-in-powerapps"></a>PowerAppsin Average-, Max-, Min-, StdevP-, Sum- ja VarP-funktiot
Koostefunktiot, jotka koostavat numerojoukon.

## <a name="description"></a>Kuvaus
**Average**-funktio laskee argumenttiensa keskiarvon.

**Max**-funktio etsii enimmäisarvon.

**Min**-funktio etsii vähimmäisarvon.

**Sum**-funktio laskee argumenttiensa summan.

**StdevP**-funktio laskee argumenttiensa keskihajonnan.

**VarP**-funktio laskee argumenttiensa varianssin.

Voit antaa funktioille arvot seuraavin tavoin:

* Erillisinä argumentteina. Esimerkiksi **Sum( 1, 2, 3 )** palauttaa arvon 6.
* [Taulukkona](../working-with-tables.md) ja kaavana, joka suoritetaan taulukolle.  Kooste lasketaan kaavan arvoille joka [tietueelle](../working-with-tables.md#records).  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Nämä funktiot toimivat vain numeroarvojen kanssa. Muut arvotyypit, kuten merkkijonot ja tietueet, jätetään huomiotta. Käytä **[Value](function-value.md)** -funktiota muuntamaan merkkijono luvuksi.

**Average**-, **Max**-, **Min**- ja **Sum**-funktiot voidaan delegoida, kun niitä käytetään [näiden funktioiden delegointia tukevan tietolähteen kanssa](../delegation-list.md).  **StdevP**- ja **VarP**-funktioita ei kuitenkaan voi delegoida minkään tietolähteen osalta.  Jos delegointia ei tueta, vain tietojen ensimmäinen osa noudetaan ja sen jälkeen funktio otetaan käyttöön paikallisesti.  Tulos ei ehkä vastaa koko tarinaa.  Muokkaamisen aikana näyttöön tulee delegointivaroitus, joka muistuttaa tästä rajoituksesta ja ehdottaa mahdollisia delegoitavia vaihtoehtoja. Lisätietoja on kohdassa [Delegoinnin yleiskatsaus](../delegation-overview.md).

## <a name="syntax"></a>Syntaksi
**Average**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Max**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Min**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Sum**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**StdevP**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**VarP**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )

* *NumericalFormula(s)* – Pakollinen.  Käsiteltävät numeeriset arvot.

**Average**( *Table*, *NumericalFormula* )<br>**Max**( *Table*, *NumericalFormula* )<br>**Min**( *Table*, *NumericalFormula* )<br>**Sum**( *Table*, *NumericalFormula* )<br>**StdevP**( *Table*, *NumericalFormula* )<br>**VarP**( *Table*, *NumericalFormula* )

* *Table* – Pakollinen.  Käsiteltävä taulukko.
* *NumericalFormula* – Pakollinen. Kullekin tietueelle laskettava kaava. Tämän kaavan tulosta käytetään koostamiseen. Voit käyttää taulukon sarakkeita kaavassa.

## <a name="examples"></a>Esimerkkejä
### <a name="step-by-step"></a>Vaihe vaiheelta
Oletetaan, että käytössä on [tietolähde](../working-with-data-sources.md) nimeltä **Sales**, joka sisältää sarakkeen **CostPerUnit** ja sarakkeen **UnitsSold**, ja asetat selitteen **[Text](../controls/properties-core.md)** -ominaisuudeksi tämän kaavan:<br>
**Sum(Sales, CostPerUnit * UnitsSold)**

Selite näyttää kokonaismyynnit kertomalla tietueiden sarakkeiden arvot ja lisäämällä kaikkien tietueiden tulokset yhteen:<br>![Kokonaismyynnin laskenta myydyistä yksiköistä ja yksikköhinnasta](./media/function-aggregates/total-sales.png)

Toisessa erilaisessa esimerkissä käytössä on liukusäätimet nimeltä **Slider1**, **Slider2** ja **Slider3** ja selite, jonka **[Text](../controls/properties-core.md)** -ominaisuudeksi on määritetty seuraava kaava:<br>
**Sum(Slider1.Value, Slider2.Value, Slider3.Value)**

Selite näyttää kaikkien näiden liukusäädinten asetusten summan.


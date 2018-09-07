---
title: Remove- ja RemoveIf-funktio | Microsoft Docs
description: Tietoja PowerAppsin Remove- ja RemoveIf-funktiosta, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/21/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a6887694f2cc64cd44dcdc74e7769ce874872f70
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863274"
---
# <a name="remove-and-removeif-functions-in-powerapps"></a>PowerAppsin Remove- ja RemoveIf-funktio
Poistaa [tietueita](../working-with-tables.md#records) [tietolähteestä](../working-with-data-sources.md).

## <a name="description"></a>Kuvaus
### <a name="remove-function"></a>Remove-funktio
**Remove**-funktiolla voit poistaa tietolähteestä yhden tai useamman tietueen.  

Jos kyseessä on [kokoelma](../working-with-data-sources.md#collections), koko tietueen on oltava funktion mukainen. Jos haluat poistaa kaikki tietueen kopiot, käytä **All**-argumenttia; muussa tapauksessa vain yksi tietueen kopio poistetaan.

### <a name="removeif-function"></a>RemoveIf-funktio
Käytä **RemoveIf**-funktiota, jos haluat soveltaa tietueen/tietueiden poistamiseen yhtä tai useampaa ehtoa. Kukin ehto voi olla mikä tahansa kaava, jonka tulos on **true** tai **false**, ja se voi viitata tietolähteen [sarakkeisiin](../working-with-tables.md#columns) nimen mukaan. Kukin ehto arvioidaan erikseen kunkin tietueen osalta, ja tietue poistetaan, jos kaikkien ehtojen arvoksi tulee **true**.

Sekä **Remove** että **RemoveIf** palauttavat muokatun tietolähteen [taulukon muodossa](../working-with-tables.md). Näitä funktioita voidaan käyttää vain [toimintakaavoissa](../working-with-formulas-in-depth.md).

Jos haluat poistaa kaikki tietolähteen tietueet, voit käyttää myös **[Clear](function-clear-collect-clearcollect.md)**-funktiota.

### <a name="delegation"></a>Delegointi
[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaksi
**Remove**( *DataSource*, *Record1* [, *Record2*, ... ] [, **All** ] )

* *DataSource* – Pakollinen. Tietolähde, joka sisältää tietueen tai tietueet, jotka haluat poistaa.
* *Record(s)* – Pakollinen. Tietue tai tietueet, jotka haluat poistaa.
* **All** – Valinnainen. Sama tietue voi näkyä kokoelmassa useamman kerran.  Voit lisätä **All**-argumentin, jos haluat poistaa kaikki tietueen kopiot.

**Remove**( *DataSource*, *Table* [, **All** ] )

* *DataSource* – Pakollinen. Tietolähde, joka sisältää tietueen tai tietueet, jotka haluat poistaa.
* *Taulukko* – Pakollinen. Taulukko, joka sisältää poistettavat tietueet.
* **All** – Valinnainen. Sama tietue voi näkyä kokoelmassa useamman kerran.  Voit lisätä **All**-argumentin, jos haluat poistaa kaikki tietueen kopiot.

**RemoveIf**( *DataSource*, *Condition* [, ... ] )

* *DataSource* – Pakollinen. Tietolähde, joka sisältää tietueen tai tietueet, jotka haluat poistaa.
* *Condition(s)* – Pakollinen. Kaava, joka määrittää poistettavan tietueen tai poistettavien tietueiden arvoksi **true**.  Voit käyttää kaavassa *DataSource*-tietolähteessä olevia sarakenimiä.  Jos määrität useita ehtoja (*Conditions*), niiden kaikkien arvoksi on tultava **true**, ennen kuin tietue tai tietueet poistetaan.

## <a name="examples"></a>Esimerkkejä
Näissä esimerkeissä poistat tietueita tietolähteestä, jonka nimi on **IceCream** ja joka alkaa seuraavan taulukon tiedoilla:

![](media/function-remove-removeif/icecream.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Remove(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Chocolate"&nbsp;)&nbsp;) )** |Poistaa tietolähteestä **Chocolate**-tietueen. |<style> img { max-width: none } </style> ![](media/function-remove-removeif/icecream-no-chocolate.png)<br><br>**IceCream**-tietolähdettä on muokattu. |
| **Remove(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Chocolate"&nbsp;)&nbsp;) First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Strawberry"&nbsp;)&nbsp;) )** |Poistaa tietolähteestä kaksi tietuetta. |![](media/function-remove-removeif/icecream-only-vanilla.png)<br><br>**IceCream**-tietolähdettä on muokattu. |
| **RemoveIf(&nbsp;IceCream, Quantity&nbsp;>&nbsp;150 )** |Muokkaa tietueita, joiden määrä (**Quantity**) on suurempi kuin **150**. |![](media/function-remove-removeif/icecream-only-chocolate.png)<br><br>**IceCream**-tietolähdettä on muokattu. |
| **RemoveIf(&nbsp;IceCream, Quantity&nbsp;>&nbsp;150, Left(&nbsp;Flavor,&nbsp;1&nbsp;) = "S" )** |Poistaa tietueita, joiden määrä (**Quantity**) on suurempi kuin 150 ja maku **(Flavor)** alkaa **S**-kirjaimella. |![](media/function-remove-removeif/icecream-no-strawberry.png)<br><br><br>**IceCream**-tietolähdettä on muokattu. |
| **RemoveIf(&nbsp;IceCream, true )** |Poistaa tietolähteestä kaikki tietueet. |![](media/function-remove-removeif/icecream-empty.png)<br><br>**IceCream**-tietolähdettä on muokattu. |

### <a name="step-by-step"></a>Ohjeet vaihe vaiheelta
1. Tuo tai luo kokoelma, jonka nimi on **Luettelo**, ja näytä se valikoimassa artikkelin [Tietojen näyttäminen valikoimassa](../show-images-text-gallery-sort-filter.md) mukaan.
2. Aseta **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava lauseke:<br>**Remove(Inventory, ThisItem)**
3. Paina F5-näppäintä ja valitse valikoimasta kuva.<br>Kohde poistetaan valikoimasta ja kokoelmasta.


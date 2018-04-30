---
title: Operaattorit | Microsoft Docs
description: Viittaustietoja operaattoreista PowerAppsissa, muun muassa syntaksi ja esimerkkejä
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
ms.date: 07/24/2017
ms.author: gregli
ms.openlocfilehash: 3250251e02170d2dd7bab441bc3c94705216ec00
ms.sourcegitcommit: 397a968f57ce5aaaf2b86e804dfedda8cf34f307
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/19/2018
---
# <a name="operators-and-data-types-in-powerapps"></a>Operaattorit ja tietotyypit PowerAppsissa
Jotkin näistä operaattoreista ovat riippuvaisia tekijän kielestä.  Jos haluat lisätietoja, katso [Yleiset sovellukset](../global-apps.md).

| Symboli | Tyyppi | Syntaksi | Kuvaus |
| --- | --- | --- | --- |
| **.** |Ominaisuuden valitsin |**Slider1.Value<br>Color.Red<br>Acceleration.X** |Poimii ominaisuuden [taulukosta](../working-with-tables.md), ohjausobjektista, [signaalista](signals.md) tai luetteloinnista.  Yhteensopivuus aikaisempien versioiden kanssa, **!** on myös käytettävissä. |
| **.**<br>[tai **,** [riippuen kielestä](../global-apps.md)] |Desimaalierotin |**1.23**<br>[tai **1,23** riippuen kielestä] |Erotin numeron kokonaisosien ja murto-osien välissä.  Merkki on riippuvainen kielestä. |
| **( )** |Sulkeet |**Filter(T, A &lt; 10)**<br><br>**(1 + 2) * 3** |Pakottaa käsittelyjärjestyksen ja ryhmittää suuremman lausekkeen alilausekkeet |
| **+** |Aritmeettiset operaattorit |**1 + 2** |Yhteenlasku |
| **-** |&nbsp; |**2 - 1** |Vähennyslasku ja merkki |
| **\*** |&nbsp; |**2 * 3** |Kertolasku |
| **/** |&nbsp; |**2 / 3** |Jakolasku (katso myös **[Mod](function-mod.md)**-funktio) |
| **^** |&nbsp; |**2 ^ 3** |Potenssiin korotus, vastaa **[Power](function-numericals.md)**-funktiota |
| **%** |&nbsp; |**20%** |Prosenttiosuus (vastaa: &quot;* 1/100&quot;) |
| **=** |Vertailuoperaattorit |**Price = 100** |Yhtä suuri kuin |
| **&gt;** |&nbsp; |**Price &gt; 100** |Suurempi kuin |
| **&gt;=** |&nbsp; |**Price &gt; 100** |Suurempi tai yhtä suuri kuin |
| **&lt;** |&nbsp; |**Price &lt; 100** |Pienempi kuin |
| **&lt;=** |&nbsp; |**Price &lt;= 100** |Pienempi tai yhtä suuri kuin |
| **&lt;&gt;** |&nbsp; |**Price &lt;&gt; 100** |Eri suuri kuin |
| **&amp;** |Merkkijonon yhdistämisoperaattori |**&quot;hello&quot; &amp; &quot; &quot; &amp; &quot;world&quot;** |Muodostaa useista merkkijonoista yhtenäisen näkymän |
| **&amp;&amp;** tai **And** |Loogiset operaattorit |**Price &lt; 100 &amp;&amp; Slider1.Value = 20**<br>tai **Price &lt; 100 And Slider1.Value = 20** |Looginen yhdistäminen, vastaa **[And](function-logicals.md)**-funktiota |
| **&#124;&#124;** tai **Or** |&nbsp; |**Price &lt; 100 &#124;&#124; Slider1.Value = 20** tai **Price &lt; 100 Or Slider1.Value = 20** |Looginen erottaminen, vastaa **[Or](function-logicals.md)**-funktiota |
| **!** tai **Not** |&nbsp; |**!(Price &lt; 100)** tai **Not (Price &lt; 100)** |Looginen negaatio, vastaa **[Not](function-logicals.md)**-funktiota |
| **exactin** |[Jäsenyysoperaattorit](#in-and-exactin-operators) |**Gallery1.Selected exactin SavedItems** |[Kokoelmaan](../working-with-data-sources.md#collections) tai taulukkoon kuuluva |
| **exactin** |&nbsp; |**&quot;Windows&quot; exactin ”To display windows in the Windows operating system...”** |Alimerkkijonotesti (kirjainkoko on merkitsevä) |
| **in** |&nbsp; |**Gallery1.Selected in SavedItems** |Kokoelmaan tai taulukkoon kuuluva |
| **in** |&nbsp; |**&quot;The&quot; in &quot;The keyboard and the monitor...&quot;** |Alimerkkijonotesti (kirjainkoko ei ole merkitsevä) |
| **@** |[Selvitysoperaattori](#disambiguation-operator) |**MyTable[@fieldname]** |Kentän selvitys |
| **@** |&nbsp; |**[@MyVariable]** |Yleinen selvitys |
| **,**<br>[tai **;** [riippuen kielestä](../global-apps.md)] |Luetteloerotin |**If( X < 10, "Low", "Good" )**<br>**{ X: 12, Y: 32 }**<br>**[ 1, 2, 3 ]**<br>[tai **If( X < 10; "Low"; "Good" )<br>{ FirstName: "Jane"; LastName: "Doe" }<br>[ 1; 2; 3 ]** ] |Erottaa: <ul><li>argumentit funktiokutsuissa</li><li>kentät [tietueessa](../working-with-tables.md#elements-of-a-table)</li><li>tietueet [arvotaulukossa](../working-with-tables.md#inline-syntax)</li></ul>.  Tämä merkki on riippuvainen kielestä. |
| **;**<br>[tai **;;** [riippuen kielestä](../global-apps.md)] |Kaavan ketjutus |**Collect(T, A); Navigate(S1, &quot;&quot;)**<br>[tai **Collect(T; A);; Navigate(S1; &quot;&quot;)**] |Erilliset funktioiden kutsut toimintaominaisuuksissa.  Ketjutusoperaattori on riippuvainen kielestä. |
| **Parent** |[Parent-operaattori](#parent-operator) |**Parent.Fill** |Ohjausobjektin säilön ominaisuuksien käyttö |
| **ThisItem** |[ThisItem-operaattori](#thisitem-operator) |**ThisItem.FirstName** |Pääsy valikoiman tai lomakkeen ohjausobjektin kenttiin |

## <a name="in-and-exactin-operators"></a>in- ja exactin-operaattorit
Voit käyttää **[in](operators.md#in-and-exactin-operators)**- ja **[exactin](operators.md#in-and-exactin-operators)**-operaattoreita löytääksesi merkkijonon [tietolähteestä](../working-with-data-sources.md), kuten kokoelmasta tai tuodusta taulukosta. **[in](operators.md#in-and-exactin-operators)**-operaattori tunnistaa osumat riippumatta tilanteesta. **[exactin](operators.md#in-and-exactin-operators)**-operaattori tunnistaa osumat vain, jos niiden ensimmäisen kirjaimen kirjainkoko on sama. Tässä on esimerkki:

1. Luo tai tuo kokoelma, jonka nimi on **Inventory**, ja näytä se valikoimassa, kuten kohdan [Kuvien ja tekstin näyttäminen valikoimassa](../show-images-text-gallery-sort-filter.md) ensimmäisessä toimintosarjassa on kuvattu.
2. Aseta valikoiman **[Items](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**Filter(Inventory, "E" in ProductName)**
   
    Valikoima näyttää kaikki muut tuotteet paitsi Calliston, koska tämän tuotteen nimi on ainoa, joka ei sisällä määrittämääsi kirjainta.
3. Muuta valikoiman **[Items](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**Filter(Inventory, "E" exactin ProductName)**
   
    Valikoima näyttää vain Europan, koska se on ainoa nimi, joka sisältää määrittämäsi kirjaimen.

## <a name="thisitem-operator"></a>ThisItem-operaattori
Voit näyttää tietoa **[Gallery](../controls/control-gallery.md)**-, **[Edit form](../controls/control-form-detail.md)**- tai **[Display form](../controls/control-form-detail.md)** -ohjausobjekteissa sitomalla sen taulukkoon tai kokoelmaan.  Nämä ohjausobjektit ovat säilöjä muille korteille ja ohjausobjekteille.  Jokainen säilössä oleva kortti tai ohjausobjekti voi käyttää sidottua tietoa **[ThisItem](operators.md#thisitem-operator)**-operaattorin avulla.   

Voit käyttää **[ThisItem](operators.md#thisitem-operator)**-operaattoria määrittääksesi tiedon [sarakkeen](../working-with-tables.md#columns) jokaiselle kortille tai ohjausobjektille ulommassa ohjausobjektissa. Esimerkiksi operaattori kohdan [Näytä valikoiman kuvat ja teksti](../show-images-text-gallery-sort-filter.md) tuotevalikoimassa määritti, että kuvan ohjausobjekti näytti tuotemuotoilun, ylempi otsikko näytti tuotteen nimen ja alempi otsikko näytti varastossa olevien yksikköjen määrän.

Sisäkkäisissä valikoimissa **[ThisItem](operators.md#thisitem-operator)** viittaa sisimmän valikoiman kohteisiin. Olettaen, että sisemmän ja ulomman valikoiman rivikentät eivät olleet ristiriidassa, voit käyttää myös tarkentamattomia kentän (sarakkeen) nimiä suoraan. Tämän lähestymistavan avulla sisemmän valikoiman säännöt voivat viitata ulomman valikoiman kohteisiin.

## <a name="parent-operator"></a>Parent-operaattori
Jotkin ohjausobjektit isännöivät muita ohjausobjekteja. Esimerkiksi **[Screen](../controls/control-screen.md)**-, **[Gallery](../controls/control-gallery.md)**-, **[Card](../controls/control-card.md)**-, **[Edit form](../controls/control-form-detail.md)**- ja **[Display form](../controls/control-form-detail.md)** -ohjausobjektit ovat kaikki ohjausobjektien säilöjä. Kutsumme isännöivää ohjausobjektia sisällä olevien ohjausobjektien ”ylätasoksi”.

Kaikkiin ohjausobjekteihin PowerAppsissa voidaan viitata nimellä mistä tahansa sovelluksessa. **Screen1** voi olla näytön nimi sovelluksessa. Voit hakea tämän näytön taustavärin käyttämällä funktiota **Screen1.Fill**.

Tämän näytön ohjausobjekteilla on toinen vaihtoehto. Ne voivat käyttää suhteellista viittausta: **Parent.Fill**. **[Parent](operators.md#parent-operator)**-operaattorilla viitataan ohjausobjektiin, joka isännöi tätä ohjausobjektia, jolloin sen kaikki ominaisuudet ovat käytettävissä. **[Parent](operators.md#parent-operator)**-operaattorin käyttäminen on hyödyllistä, koska se ei ole riippuvainen ohjausobjektin nimestä. Voit kopioida ja liittää säilön ohjausobjektin säätämättä viittauksia säilössä. Tämä operaattori tekee myös aliohjausobjektien ja ylemmän tason ohjausobjektien suhteista selkeämpiä kaavoja luettaessa.

## <a name="disambiguation-operator"></a>Selvitysoperaattori
Jotkin funktiot luovat [tietuealueita](../working-with-tables.md#record-scope) taulukon kenttien käyttämiseksi tietueita käsiteltäessä, kuten **Filter**, **AddColumns** ja **Sum**.  Tietuealueen kanssa lisätyt kentän nimet ohittavat samat nimet muualta sovelluksesta.  Kun näin tapahtuu, voit edelleen käyttää arvoja tietuealueen ulkopuolelta käyttämällä **@** selvitysoperaattoria:

* Voit käyttää sisäkkäisten tietuealueiden arvoja käyttämällä **@** -operaattoria ja käytettävän taulukon nimeä käyttämällä mallia ***Table *[@* FieldName*]**.  
* Voit käyttää yleisiä arvoja, kuten tietolähteitä, kokoelmia ja kontekstimuuttujia, käyttämällä mallia **[@*ObjectName*]** (ilman taulukon nimeä).

Saat lisätietoja ja esimerkkejä katsomalla keskustelun kohdassa [tietuealueet](../working-with-tables.md#record-scope).


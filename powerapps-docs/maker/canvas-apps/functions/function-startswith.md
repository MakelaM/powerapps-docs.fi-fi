---
title: EndsWith- ja StartsWith-funktiot | Microsoft Docs
description: PowerAppsin EndsWith- ja StartsWith-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 07/24/2017
ms.author: gregli
ms.openlocfilehash: c01a69f311378e8e818036c866b96a78f223baf9
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="endswith-and-startswith-functions-in-powerapps"></a>EndsWith- ja StartsWith-funktiot PowerAppsissa
Testaa, alkaako tekstimerkkijono toisella merkkijonolla tai päättyykö se toiseen tekstimerkkijonoon.

## <a name="description"></a>Kuvaus
**EndsWith**-funktio testaa, päättyykö tekstimerkkijono toiseen tekstimerkkijonoon.

**StartsWith**-funktio testaa, alkaako tekstimerkkijono toisella tekstimerkkijonolla.    

Funktioiden testien kirjainkoko ei ole merkitsevä.  Palautusarvo on totuusarvo **true** tai **false**.  

Hae tietoa sovelluksestasi yhdistämällä **EndsWith** ja **StartsWith** **[Suodatin](function-filter-lookup.md)**-funktioon. Voit etsiä mistä tahansa tekstijonojen sisältä, ei pelkästään alusta tai lopusta, käyttämällä **[in](operators.md#in-and-exactin-operators)**-operaattoria tai **[Search](function-filter-lookup.md)**-funktiota.  Funktioiden valinta riippuu sovelluksesi tarpeista ja siitä, mikä funktio tietolähteellesi voidaan [delegoida](../delegation-overview.md).  Jos jotakin näistä funktioista ei voi delegoida, näyttöön ilmestyy muokkaamisen aikana sininen piste, joka varoittaa tästä rajoituksesta.

## <a name="syntax"></a>Syntaksi
**EndsWith**( *Text*, *EndText* )

* *Teksti* – Pakollinen.  Testattava teksti.
* *EndText* – Pakollinen.  Teksti, jota haetaan *Tekstin* lopusta.  Jos *EndText* on tyhjä merkkijono, **EndsWith** palauttaa arvon *true*.

**StartsWith**( *Text*, *StartText* )

* *Teksti* – Pakollinen.  Testattava teksti.
* *StartText* – Pakollinen.  Teksti, jota haetaan *Tekstin* alusta.  Jos *StartText* on tyhjä merkkijono, **StartsWith** palauttaa arvon *true*.

## <a name="examples"></a>Esimerkkejä
| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **EndsWith( "Hei, Maailma", "maailma" )** |Testaa, päättyykö **”Hei, Maailma”** tekstiin **”maailma”**.  Testin kirjainkoolla ei ole merkitystä. |**true** |
| **EndsWith( "Näkemiin", "näke" )** |Testaa, päättyykö **”Näkemiin”** tekstiin **”näke”**.  *EndText*-argumentti (**”näke”**) esiintyy tekstissä, mutta ei sen lopussa. |**false** |
| **EndsWith( "Sano aina hei", "hei" )** |Testaa, päättyykö **”Sano aina hei”** tekstiin **”hei”**. |**true** |
| **Endswith( "Hei hei", "" )** |Testaa, päättyykö **”Hei hei”** tyhjään tekstimerkkijonoon (**Len** palauttaa arvon 0).  Jotta **EndsWith**-funktiota olisi helpompi käyttää **Suodatin**-lausekkeissa, se on määritetty palauttamaan tässä tapauksessa arvo **true**. |**true** |

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **StartsWith( "Hei, Maailma", "hei" )** |Testaa, alkaako **”Hei, Maailma”** tekstillä **”hei”**.  Testin kirjainkoolla ei ole merkitystä. |**true** |
| **StartsWith( "Näkemiin", "hei" )** |Testaa, alkaako **”Näkemiin”** tekstillä **”hei”**. |**false** |
| **StartsWith( "Sano aina hei", "hei" )** |Testaa, alkaako **”Sano aina hei”** tekstillä **”hei”**.  **”Hei”** esiintyy tekstissä, mutta ei sen alussa. |**false** |
| **StartsWith( "Hei hei", "" )** |Testaa, alkaako **”Hei hei”** tyhjällä merkkijonolla (**Len** palauttaa arvon 0).  Jotta **StartsWith**-funktiota olisi helpompi käyttää **Suodatin**-lausekkeissa, se on määritetty palauttamaan tässä tapauksessa arvo **true**. |**true** |

### <a name="search-user-experience"></a>Haun käyttökokemus
Monissa sovelluksissa hakukenttään voi kirjoittaa yhden tai useamman merkin. Tällä tavalla voit suodattaa tietueluetteloita suurissa tietojoukoissa. Luettelossa näytetään vain ne tietueet, jotka vastaavat kirjoittamiasi hakuehtoja.

Loput tämän ohjeaiheen esimerkeistä näyttävät hakutuloksia luettelosta, jonka nimi on **Asiakkaat**, joka sisältää nämä tiedot:

![](media/function-startswith/customers.png)

Luo tämä tietolähde kokoelmana luomalla **[Painike](../controls/control-button.md)**-ohjausobjekti ja määrittämällä sen **OnSelect**-ominaisuuden arvoksi tämä kaava:

**ClearCollect( Asiakkaat, Table( { Nimi: "Fred Garcia", Yritys: "Northwind Traders" }, { Nimi: "Cole Miller", Yritys: "Contoso" }, { Nimi: "Glenda Johnson", Yritys: "Contoso" }, { Nimi: "Mike Collins", Yritys: "Adventure Works" }, { Nimi: "Colleen Jones", Yritys: "Adventure Works" } ) )**

Kuten tässä esimerkissä, voit näyttää luettelon [**Valikoima-ohjausobjektin**](../controls/control-gallery.md) tietueista näytön alareunassa. Näytön yläosassa voit lisätä [**Tekstisyöte**](../controls/control-text-input.md)-ohjausobjektin nimeltä **hakusyöte**, jotta käyttäjät voivat määrittää, mitkä tietueet kiinnostavat heitä.

![](media/function-startswith/customers-ux-unfiltered.png)

Kun käyttäjä kirjoittaa merkkejä **hakusyötteeseen**, valikoiman tuloksia suodatetaan automaattisesti. Tässä tapauksessa valikoima on määritetty näyttämään tietueet, joiden asiakkaan nimi (ei yrityksen nimi) alkaa merkeillä, jotka on syötetty **hakusyötteeseen**. Jos käyttäjä kirjoittaa hakuruutuun **co**, valikoima näyttää seuraavat tulokset:

![](media/function-startswith/customers-ux-startswith-co.png)

Voit suodattaa **Nimi**-sarakkeen perusteella määrittämällä valikoiman **Kohteet**-ominaisuudeksi jonkin seuraavista kaavoista:

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Filter( Asiakkaat, StartsWith( Nimi, hakusyöte.Text ) )** |Suodattaa **Asiakkaat**-tietolähteestä tietueet, joiden **Nimi**-sarakkeen alussa esiintyy hakumerkkijono. Testin kirjainkoolla ei ole merkitystä. Jos käyttäjä kirjoittaa hakuruutuun **co**, valikoima näyttää tulokset **Colleen Jones** ja **Cole Miller**. Valikoima ei näytä tietuetta **Mike Collins**, koska sen **Nimi**-sarake ei ala hakumerkkijonolla. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-name-co-startswith.png) |
| **Filter( Asiakkaat, hakusyöte.Text in Nimi)** |Suodattaa **Asiakkaat**-tietolähteestä tietueet, joiden **Nimi**-sarakkeen jossain kohdassa esiintyy hakumerkkijono. Testin kirjainkoolla ei ole merkitystä. Jos käyttäjä kirjoittaa hakukenttään **co**, valikoima näyttää tulokset **Colleen Jones,** **Cole Miller** ja **Mike Collins**, koska hakumerkkijono esiintyy jossain kohdassa tietueen **Nimi**-saraketta. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-name-co-contains.png) |
| **Search( Asiakkaat, hakusyöte.Text, "Nimi" )** |**Search**-funktio etsii vastaavuutta missä tahansa kunkin tietueen **Nimi**-sarakkeen osassa, samaan tapaan kuin **in**-operaattori. Huomaa, että sarakkeen nimi on kirjoitettava lainausmerkkeihin. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-name-co-contains.png) |

Voit laajentaa haun sisältämään sekä **Yritys**-sarakkeen että **Nimi**-sarakkeen:

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Filter( Asiakkaat, StartsWith( Nimi, hakusyöte.Text ) &#124;&#124; StartsWith( Yritys, hakusyöte.Text ) )** |Suodattaa **Asiakkaat**-tietolähteestä tietueet, joiden **Nimi**-sarake tai **Yritys**-sarake alkaa hakumerkkijonolla (esimerkiksi **co**).  [**&#124;&#124;**-operaattori ](operators.md) on *true*, jos jompikumpi **StartsWith**-funktio on *true*. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-all-co-startswith.png) |
| **Filter( Asiakkaat, hakusyöte.Text in Nimi &#124;&#124; hakusyöte.Text in Yritys)** |Suodattaa **Asiakkaat**-tietolähteestä tietueet, joiden **Nimi**-sarakkeen tai **Yritys**-sarakkeen jossain kohdassa esiintyy hakumerkkijono (esimerkiksi **co**). |<style> img { max-width: none } </style> ![](media/function-startswith/customers-all-co-contains.png) |
| **Search( Asiakkaat, hakusyöte.Text, "Nimi", "Yritys" )** |Samoin kuin **in**-operaattori, **Search**-funktio hakee **Asiakkaat**-tietolähteestä tietueet, joiden **Nimi**-sarakkeen tai **Yritys**-sarakkeen jossain kohdassa esiintyy hakumerkkijono (esimerkiksi **co**). **Search**-funktio on helpompi lukea ja kirjoittaa kuin **Suodatin**-funktio, jos haluat määrittää useita sarakkeita ja useita **in**-operaattoreita. Huomaa, että sarakkeiden nimet on kirjoitettava lainausmerkkeihin. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-all-co-contains.png) |


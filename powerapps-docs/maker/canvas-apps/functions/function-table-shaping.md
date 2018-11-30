---
title: AddColumns-, DropColumns-, RenameColumns- ja ShowColumns-funktiot | Microsoft Docs
description: PowerAppsin AddColumns-, DropColumns-, RenameColumns- ja ShowColumns-funktioiden viitetietoja, kuten syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/24/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 056c5e1142b3a34776e72f788f5b2cef9e3b2a27
ms.sourcegitcommit: 3dc330d635aaf5bc689efa6bd39826d6e396c832
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/09/2018
ms.locfileid: "48875895"
---
# <a name="addcolumns-dropcolumns-renamecolumns-and-showcolumns-functions-in-powerapps"></a>AddColumns-, DropColumns-, RenameColumns- ja ShowColumns-funktiot PowerAppsissa
Muokkaa [taulukkoa](../working-with-tables.md) lisäämällä, poistamalla, nimeämällä uudelleen ja valitsemalla sen [sarakkeita](../working-with-tables.md#columns).

## <a name="overview"></a>Yleiskatsaus
Nämä funktiot muokkaavat taulukkoa säätämällä sen sarakkeita:

* Pienennä useita sarakkeita sisältävä taulukko yhteen sarakkeeseen käytettäväksi yksisarakkeisten funktioiden kanssa, kuten **[Lower](function-lower-upper-proper.md)** ja **[Abs](function-numericals.md)**.  
* Lisää taulukkoon laskettu sarake (esimerkiksi **Kokonaishinta**-sarake, joka näyttää tulokset kertomalla **määrän** **yksikköhinnalla**).
* Nimeä sarake uudelleen, jotta sen nimi sopii paremmin näytettäväksi käyttäjille ja käytettäväksi kaavoissa.

PowerAppsissa taulukko on arvo, samaan tapaan kuin merkkijono tai luku.  Voit määrittää taulukon kaavan argumenttina, ja funktio voi palauttaa tuloksena taulukon. Tässä aiheessa kuvatut funktiot eivät muokkaa taulukkoa. Sen sijaan ne ottavat taulukon argumenttina ja palauttavat uuden taulukon, jota on muunnettu.  Lisätietoja on kohdassa [taulukoiden käsitteleminen](../working-with-tables.md).  

Et voi muokata [tietolähteen](../working-with-data-sources.md) sarakkeita käyttämällä näitä funktioita. Sinun on muokattava tietoa sen lähteessä. Voit lisätä sarakkeita [kokoelmaan](../working-with-data-sources.md#collections) käyttämällä **[Collect](function-clear-collect-clearcollect.md)**-funktiota.  Lisätietoja on kohdassa [tietolähteiden käsitteleminen](../working-with-data-sources.md).  

## <a name="description"></a>Kuvaus
**AddColumns**-funktio lisää sarakkeen taulukkoon. Kaava määrittää kyseisen sarakkeen arvot. Olemassa olevia sarakkeita ei muokata.

Kaava lasketaan taulukon jokaiselle tietueelle.
[!INCLUDE [record-scope](../../../includes/record-scope.md)]

**DropColumns**-funktio jättää sarakkeita pois taulukosta.  Mitään muita sarakkeita ei muokata. **DropColumns** jättää pois sarakkeet, **ShowColumns** sisällyttää sarakkeet.

**RenameColumns**-funktiolla voit nimetä vähintään yhden taulukon sarakkeet uudelleen antamalla vähintään yhden argumenttiparin, joka määrittää sarakkeen nimen, jonka taulukko sisältää (vanha nimi, jonka haluat korvata), sekä sarakkeen nimen, jota taulukko ei sisällä (uusi nimi, jota haluat käyttää). Vanhan nimen on jo oltava olemassa taulukossa ja uutta nimeä ei saa olla olemassa. Jokainen sarakkeen nimi voi olla vain kerran argumenttiluettelossa joko vanhana sarakkeen nimenä tai uutena sarakkeen nimenä. Jos haluat antaa sarakkeelle jo olemassa olevan nimen, jätä ensin olemassa oleva sarake pois **DropColumns**-funktiolla tai nimeä se uudelleen laittamalla yksi **RenameColumns**-funktio sisäkkäin toisen kanssa.

**ShowColumns**-funktio sisällyttää taulukon sarakkeet ja jättää pois kaikki muut sarakkeet. Voit käyttää **ShowColumns**-funktiota yksisarakkeisen taulukon luomiseen usean sarakkeen taulukosta.  **ShowColumns** sisällyttää sarakkeet, **DropColumns** jättää pois sarakkeet.  

Kaikkien näiden funktioiden tuloksena on uusi taulukko, johon on tehty muunnos.  Alkuperäistä taulukkoa ei muokata.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaksi
**AddColumns**( *Table*, *ColumnName1*, *Formula1* [, *ColumnName2*, *Formula2*, ... ] )

* *Table* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
* *ColumnName(s)* – Pakollinen. Lisättävien sarakkeiden nimet.  Sinun on määritettävä merkkijono (esimerkiksi **"Nimi"** lainausmerkeissä) tähän argumenttiin.
* *Formula(s)* – Pakollinen.  Kullekin tietueelle laskettavat kaavat. Tulos lisätään vastaavan uuden sarakkeen arvona. Voit viitata taulukon muihin sarakkeisiin tässä kaavassa.

**DropColumns**( *Table*, *ColumnName1* [, *ColumnName2*, ... ] )

* *Table* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
* *ColumnName(s)* – Pakollinen. Pois jätettävien sarakkeiden nimet. Sinun on määritettävä merkkijono (esimerkiksi **"Nimi"** lainausmerkeissä) tähän argumenttiin.

**RenameColumns**( *Table*, *OldColumneName1*, *NewColumnName1* [, *OldColumnName2*, *NewColumnName2*, ... ] )

* *Table* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
* *OldColumnName* – Pakollinen. Alkuperäisen taulukon uudelleennimettävän sarakkeen nimi. Tämä elementti näkyy ensimmäisenä argumenttiparissa (tai ensimmäisenä kussakin argumenttiparissa, jos kaava sisältää useamman kuin yhden parin). Tämän nimen on oltava merkkijono (esimerkiksi **"Nimi"** lainausmerkeissä).
* *NewColumnName* – Pakollinen. Korvaava nimi. Tämä elementti näkyy viimeisenä argumenttiparissa (tai viimeisenä kussakin argumenttiparissa, jos kaava sisältää useamman kuin yhden parin). Sinun on määritettävä merkkijono (esimerkiksi **"Asiakkaan nimi"** lainausmerkeissä) tähän argumenttiin.

**ShowColumns**( *Table*, *ColumnName1* [, *ColumnName2*, ... ] )

* *Table* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
* *ColumnName(s)* – Pakollinen. Sisällytettävien sarakkeiden nimet. Sinun on määritettävä merkkijono (esimerkiksi **"Nimi"** lainausmerkeissä) tähän argumenttiin.

## <a name="examples"></a>Esimerkkejä
Tämän osion esimerkeissä käytämme **IceCreamSales**-tietolähdettä, joka sisältää tämän taulukon tiedot:

![](media/function-table-shaping/icecream.png)

Mikään näistä esimerkeistä ei muokkaa **IceCreamSales**-tietolähdettä. Jokainen funktio muuntaa tietolähteen arvon taulukkomuodossa ja palauttaa tuloksena tämän arvon.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **AddColumns( IceCreamSales, "Revenue", UnitPrice * QuantitySold )** |Lisää **Revenue**-sarakkeen tulokseen.  **UnitPrice * QuantitySold** arvioidaan jokaiselle tietueelle, ja tulos sijoitetaan uuteen sarakkeeseen. |<style> img { max-width: none; } </style> ![](media/function-table-shaping/icecream-add-revenue.png) |
| **DropColumns( IceCreamSales, "UnitPrice" )** |Sulkee pois **UnitPrice**-sarakkeen tuloksesta. Tällä funktiolla voit sulkea pois sarakkeita, ja **ShowColumns**-funktiolla voit sisällyttää niitä. |![](media/function-table-shaping/icecream-drop-price.png) |
| **ShowColumns( IceCreamSales, "Flavor" )** |Sisältää vain tuloksen **Flavor**-sarakkeen. Tällä funktiolla voit sisällyttää sarakkeita, ja **DropColumns**-funktiolla voit sulkea niitä pois. |![](media/function-table-shaping/icecream-select-flavor.png) |
| **RenameColumns( IceCreamSales, "UnitPrice", "Price")** |Nimeää uudelleen **UnitPrice**-sarakkeen tuloksessa. |![](media/function-table-shaping/icecream-rename-price.png) |
| **RenameColumns( IceCreamSales, "UnitPrice", "Price", "QuantitySold", "Number")** |Nimeää uudelleen **UnitPrice**- ja **QuantitySold**-sarakkeet tuloksessa. |![](media/function-table-shaping/icecream-rename-price-quant.png) |
| **DropColumns(<br>RenameColumns(<br>AddColumns( IceCreamSales, "Revenue",<br>UnitPrice * QuantitySold ),<br>"UnitPrice", "Price" ),<br>"Quantity" )** |Suorittaa seuraavan taulukkomuunnoksen järjestyksessä alkaen kaavan sisältä: <ol><li>Lisää **Revenue**-sarakkeen tietuekohtaisen **UnitPrice * Quantity** -laskutoimituksen perusteella.<li>Muuttaa **UnitPrice**-sarakkeen nimeksi **Price**.<li>Jättää pois **Quantity**-sarakkeen.</ol>  Huomaa, että järjestys on tärkeä. Emme voi esimerkiksi laskea sarakkeella **UnitPrice**, kun sen nimi on muutettu. |![](media/function-table-shaping/icecream-all-transforms.png) |

### <a name="step-by-step"></a>Vaihe vaiheelta
1. Tuo tai luo kokoelma, jonka nimi on **Inventory**, kuten kohdan [Kuvien ja tekstin näyttäminen valikoimassa](../show-images-text-gallery-sort-filter.md) ensimmäisessä alitoimintosarjassa on kuvattu.
2. Lisää painike ja määritä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   
    **ClearCollect(Inventory2, RenameColumns(Inventory, "ProductName", "JacketID"))**
3. Palaa suunnittelutyötilaan painamalla F5-näppäintä, valitsemalla juuri luomasi painike ja painamalla Esc-näppäintä.
4. Valitse **Tiedosto**-valikosta **Kokoelmat**.
5. Vahvista, että olet luonut kokoelman, jonka nimi on **Inventory2**. Uusi kokoelma sisältää samat tiedot kuin **Inventory**, paitsi että sarake **ProductName** kohteessa **Inventory** on nimeltään **JacketID** kohteessa **Inventory2**.


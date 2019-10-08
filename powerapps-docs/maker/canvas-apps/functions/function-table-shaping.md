---
title: AddColumns-, DropColumns-, RenameColumns- ja ShowColumns-funktiot | Microsoft Docs
description: PowerAppsin AddColumns-, DropColumns-, RenameColumns- ja ShowColumns-funktioiden viitetietoja, kuten syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/04/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6f2dfae897a19c66e493cbdecd897df87b8194c2
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992226"
ms.PowerAppsDecimalTransform: true
---
# <a name="addcolumns-dropcolumns-renamecolumns-and-showcolumns-functions-in-powerapps"></a>AddColumns-, DropColumns-, RenameColumns- ja ShowColumns-funktiot PowerAppsissa
Muokkaa [taulukkoa](../working-with-tables.md) lisäämällä, poistamalla, nimeämällä uudelleen ja valitsemalla sen [sarakkeita](../working-with-tables.md#columns).

## <a name="overview"></a>Yleiskatsaus
Nämä funktiot muokkaavat taulukkoa säätämällä sen sarakkeita:

* Pienennä useita sarakkeita sisältävä taulukko yhteen sarakkeeseen käytettäväksi yksisarakkeisten funktioiden kanssa, kuten **[Lower](function-lower-upper-proper.md)** ja **[Abs](function-numericals.md)** .  
* Lisää taulukkoon laskettu sarake (esimerkiksi **Kokonaishinta**-sarake, joka näyttää tulokset kertomalla **määrän** **yksikköhinnalla**).
* Nimeä sarake uudelleen, jotta sen nimi sopii paremmin näytettäväksi käyttäjille ja käytettäväksi kaavoissa.

PowerAppsissa taulukko on arvo, samaan tapaan kuin merkkijono tai luku.  Voit määrittää taulukon kaavan argumenttina, ja funktio voi palauttaa tuloksena taulukon.

> [!NOTE]
> Tässä aiheessa kuvatut funktiot eivät Muokkaa alkuperäistä taulukkoa. Sen sijaan ne ottavat kyseisen taulukon argumenttina ja palauttavat uuden taulukon, jossa on käytetty muunnosta. Lisätietoja on kohdassa [taulukoiden käsitteleminen](../working-with-tables.md).  

Et voi muokata [tietolähteen](../working-with-data-sources.md) sarakkeita käyttämällä näitä funktioita. Sinun on muokattava tietoa sen lähteessä. Voit lisätä sarakkeita [kokoelmaan](../working-with-data-sources.md#collections) käyttämällä **[Collect](function-clear-collect-clearcollect.md)** -funktiota. Lisätietoja on kohdassa [tietolähteiden käsitteleminen](../working-with-data-sources.md).  

## <a name="description"></a>Kuvaus
**AddColumns**-funktio lisää sarakkeen taulukkoon. Kaava määrittää kyseisen sarakkeen arvot. Olemassa olevia sarakkeita ei muokata.

Kaava lasketaan taulukon jokaiselle tietueelle.
[!INCLUDE [record-scope](../../../includes/record-scope.md)]

**DropColumns**-funktio jättää sarakkeita pois taulukosta.  Mitään muita sarakkeita ei muokata. **DropColumns** jättää pois sarakkeet, **ShowColumns** sisällyttää sarakkeet.

**RenameColumns**-funktiolla voit nimetä vähintään yhden taulukon sarakkeet uudelleen antamalla vähintään yhden argumenttiparin, joka määrittää sarakkeen nimen, jonka taulukko sisältää (vanha nimi, jonka haluat korvata), sekä sarakkeen nimen, jota taulukko ei sisällä (uusi nimi, jota haluat käyttää). Vanhan nimen on jo oltava olemassa taulukossa ja uutta nimeä ei saa olla olemassa. Jokainen sarakkeen nimi voi olla vain kerran argumenttiluettelossa joko vanhana sarakkeen nimenä tai uutena sarakkeen nimenä. Jos haluat antaa sarakkeelle jo olemassa olevan nimen, jätä ensin olemassa oleva sarake pois **DropColumns**-funktiolla tai nimeä se uudelleen laittamalla yksi **RenameColumns**-funktio sisäkkäin toisen kanssa.

**ShowColumns**-funktio sisällyttää taulukon sarakkeet ja jättää pois kaikki muut sarakkeet. Voit käyttää **ShowColumns**-funktiota yksisarakkeisen taulukon luomiseen usean sarakkeen taulukosta.  **ShowColumns** sisällyttää sarakkeet, **DropColumns** jättää pois sarakkeet.  

Kaikkien näiden funktioiden tuloksena on uusi taulukko, johon on tehty muunnos. Alkuperäistä taulukkoa ei muokata. Et voi muokata aiemmin luotua taulukkoa kaavalla. SharePoint, Common Data Service, SQL Server ja muut tieto lähteet tarjoavat työkaluja luetteloiden, entiteettien ja taulu koiden sarakkeiden muokkaamiseen, joita kutsutaan usein rakenteeksi. Tämän ohje aiheen Funktiot muuntavat syöte taulukon ilman alkuperäisen muokkaamista tulostus taulukkoon myöhempää käyttöä varten.

Näiden funktioiden argumentit tukevat delegointia. Esimerkiksi **Filter** -funktiolla, jota käytettiin argumenttina liittyvissä tietueissa, etsitään kaikista luetteloista, vaikka **[DBO]. [ AllListings]-** tieto lähde sisältää miljoona riviä:

```powerapps-comma
AddColumns( RealEstateAgents; 
    "Listings";  
    Filter(  '[dbo].[AllListings]'; ListingAgentName = AgentName ) 
)
```

Näiden funktioiden tuotosta koskee kuitenkin [muun kuin delegointi tietueen enimmäismäärä](../delegation-overview.md#non-delegable-limits).  Tässä esimerkissä palautetaan vain 500 tietuetta, vaikka **Realestateagents** -tieto lähteellä on 501 tai enemmän tietueita.

Jos käytät **Addcolumns** -kenttää tällä tavalla, **suodattimen** on tehtävä erilliset kutsut tieto lähteeseen kutakin **realestateagents**-kohteen ensimmäistä tietuetta kohden, mikä aiheuttaa paljon verkon räpäystä. IF **[DBO]. [ AllListings]** on tarpeeksi pieni eikä muutu usein, voit kutsua **Collect** -funktiota [**ONSTART**](signals.md#app) -toiminnossa, jos haluat tallentaa tieto lähteen väli muistiin sovelluksessa, kun se käynnistyy. Vaihtoehtoisesti voit järjestellä sovelluksesi uudelleen niin, että siihen liittyvät tietueet vedetään vain silloin, kun käyttäjä pyytää niitä.  

## <a name="syntax"></a>Syntaksi
**AddColumns**( *Table*; *ColumnName1*; *Formula1* [; *ColumnName2*; *Formula2*; ... ] )

* *Table* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
* *ColumnName(s)* – Pakollinen. Lisättävien sarakkeiden nimet.  Sinun on määritettävä merkkijono (esimerkiksi **"Nimi"** lainausmerkeissä) tähän argumenttiin.
* *Formula(s)* – Pakollinen.  Kullekin tietueelle laskettavat kaavat. Tulos lisätään vastaavan uuden sarakkeen arvona. Voit viitata taulukon muihin sarakkeisiin tässä kaavassa.

**DropColumns**( *Table*; *ColumnName1* [; *ColumnName2*; ... ] )

* *Table* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
* *ColumnName(s)* – Pakollinen. Pois jätettävien sarakkeiden nimet. Sinun on määritettävä merkkijono (esimerkiksi **"Nimi"** lainausmerkeissä) tähän argumenttiin.

**Renamecolumns**( *taulukko*; *OldColumnName1*; *NewColumnName1* [; *OldColumnName2*; *NewColumnName2*;...])

* *Table* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
* *OldColumnName* – Pakollinen. Alkuperäisen taulukon uudelleennimettävän sarakkeen nimi. Tämä elementti näkyy ensimmäisenä argumenttiparissa (tai ensimmäisenä kussakin argumenttiparissa, jos kaava sisältää useamman kuin yhden parin). Tämän nimen on oltava merkkijono (esimerkiksi **"Nimi"** lainausmerkeissä).
* *NewColumnName* – Pakollinen. Korvaava nimi. Tämä elementti näkyy viimeisenä argumenttiparissa (tai viimeisenä kussakin argumenttiparissa, jos kaava sisältää useamman kuin yhden parin). Sinun on määritettävä merkkijono (esimerkiksi **"Asiakkaan nimi"** lainausmerkeissä) tähän argumenttiin.

**ShowColumns**( *Table*; *ColumnName1* [; *ColumnName2*; ... ] )

* *Table* – Pakollinen.  Taulukko, jolle toiminto suoritetaan.
* *ColumnName(s)* – Pakollinen. Sisällytettävien sarakkeiden nimet. Sinun on määritettävä merkkijono (esimerkiksi **"Nimi"** lainausmerkeissä) tähän argumenttiin.

## <a name="examples"></a>Esimerkkejä
Tämän osion esimerkeissä käytämme **IceCreamSales**-tietolähdettä, joka sisältää tämän taulukon tiedot:

![](media/function-table-shaping/icecream.png)

Mikään näistä esimerkeistä ei muokkaa **IceCreamSales**-tietolähdettä. Jokainen funktio muuntaa tietolähteen arvon taulukkomuodossa ja palauttaa tuloksena tämän arvon.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **AddColumns( IceCreamSales; "Revenue"; UnitPrice * QuantitySold )** |Lisää **Revenue**-sarakkeen tulokseen.  **UnitPrice * QuantitySold** arvioidaan jokaiselle tietueelle, ja tulos sijoitetaan uuteen sarakkeeseen. |<style> img { max-width: none; } </style> ![](media/function-table-shaping/icecream-add-revenue.png) |
| **DropColumns( IceCreamSales; "UnitPrice" )** |Sulkee pois **UnitPrice**-sarakkeen tuloksesta. Tällä funktiolla voit sulkea pois sarakkeita, ja **ShowColumns**-funktiolla voit sisällyttää niitä. |![](media/function-table-shaping/icecream-drop-price.png) |
| **ShowColumns( IceCreamSales; "Flavor" )** |Sisältää vain tuloksen **Flavor**-sarakkeen. Tällä funktiolla voit sisällyttää sarakkeita, ja **DropColumns**-funktiolla voit sulkea niitä pois. |![](media/function-table-shaping/icecream-select-flavor.png) |
| **RenameColumns( IceCreamSales; "UnitPrice"; "Price")** |Nimeää **UnitPrice** -sarakkeen uudelleen tuloksessa. |![](media/function-table-shaping/icecream-rename-price.png) |
| **RenameColumns( IceCreamSales; "UnitPrice"; "Price"; "QuantitySold"; "Number")** |Nimeää uudelleen **UnitPrice**- ja **QuantitySold**-sarakkeet tuloksessa. |![](media/function-table-shaping/icecream-rename-price-quant.png) |
| **DropColumns(<br>RenameColumns(<br>AddColumns( IceCreamSales; "Revenue";<br>UnitPrice * QuantitySold );<br>"UnitPrice"; "Price" );<br>"Quantity" )** |Suorittaa seuraavan taulukkomuunnoksen järjestyksessä alkaen kaavan sisältä: <ol><li>Lisää **Revenue**-sarakkeen tietuekohtaisen **UnitPrice * Quantity** -laskutoimituksen perusteella.<li>Muuttaa **UnitPrice**-sarakkeen nimeksi **Price**.<li>Jättää pois **Quantity**-sarakkeen.</ol>  Huomaa, että järjestys on tärkeä. Emme voi esimerkiksi laskea sarakkeella **UnitPrice**, kun sen nimi on muutettu. |![](media/function-table-shaping/icecream-all-transforms.png) |

### <a name="step-by-step"></a>Vaihe vaiheelta

Kokeilkaamme joitakin esimerkkejä aiemmin tässä aiheessa.  

1. Luo kokoelma lisäämällä **[painike](../controls/control-button.md)** -ohjaus objekti ja määrittämällä sen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    ClearCollect( IceCreamSales; 
        Table(
            { Flavor: "Strawberry"; UnitPrice: 1,99; QuantitySold: 20 }; 
            { Flavor: "Chocolate"; UnitPrice: 2,99; QuantitySold: 45 };
            { Flavor: "Vanilla"; UnitPrice: 1,50; QuantitySold: 35 }
        )
    )
    ```

1. Suorita kaava valitsemalla painike pitäen Alt-näppäintä painettuna.

1. Lisää toinen **painike** -ohjaus objekti, määritä sen **onselect** -ominaisuudeksi Tämä kaava ja suorita se sitten:

    ```powerapps-comma
    ClearCollect( FirstExample; 
        AddColumns( IceCreamSales; "Revenue"; UnitPrice * QuantitySold )
    ) 
    ```
1. Valitse **tiedosto-** valikosta **kokoelmat**ja valitse sitten **icereamamsales** näyttääksesi kyseisen kokoelman.
 
    Kuten tässä kuvassa näytetään, toinen kaava ei muokannut tätä kokoelmaa. **Addcolumns** -funktiolla käytettiin **Icereamsales** -arvoa vain luku-argumenttina. funktiolla ei muuteta taulukkoa, johon kyseinen argumentti viittaa.
    
    ![Kokoelma katselu ohjelma, joka näyttää kolme kirjaa Ice Cream Sales-kokoelmasta, joka ei sisällä tuotto saraketta](media/function-table-shaping/ice-cream-sales-collection.png)

1. Valitse **FirstExample**.

    Kuten tässä kuvassa näytetään, toinen kaava palautti uuden taulukon, jossa on lisätty-sarake. **Clearcollect** -funktiolla siepattiin uusi taulukko **FirstExample** -kokoelmassa, mikä lisää alkuperäisen taulukon tietoja, kun se virtasi funktiolla muokkaamatta lähdettä:

    ![Kokoelma katselu ohjelma, joka näyttää kolme tietuetta ensimmäisestä esimerkki kokoelmasta, joka sisältää uuden tuotto sarakkeen](media/function-table-shaping/first-example-collection.png)

---
title: Filter-, Search- ja LookUp-funktiot| Microsoft Docs
description: PowerAppsin Filter- ja LookUp-funktioiden viitetiedot, kuten syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 02/05/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1412cdd79531f70a1c029d7657940200823e5ba0
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992851"
---
# <a name="filter-search-and-lookup-functions-in-powerapps"></a>Filter-, Search- ja LookUp-funktiot PowerAppsissa
Etsii vähintään yhden [tietueen](../working-with-tables.md#records) [taulukosta](../working-with-tables.md).

## <a name="description"></a>Kuvaus
**Filter**-funktio löytää taulukosta tietueet, jotka vastaavat kaavaa.  Käytä **Filter**-funktiota etsimään tietuejoukko, joka vastaa yhtä tai useampaa ehtoa, ja poistamaan ei-vastaavat tietueet.

**LookUp**-funktio etsii taulukosta ensimmäisen tietueen, joka täyttää kaavan.  Käytä **LookUp**-funktiota etsimään yksittäinen tietue, joka vastaa yhtä tai useampaa ehtoa.

Kumpikin kaava lasketaan taulukon jokaiselle tietueelle.  Tulokseen sisällytetään tietueet, joiden tulos on *true*.  Normaalien kaavan [operaattoreiden](operators.md) lisäksi voit käyttää **[in](operators.md#in-and-exactin-operators)** - ja **[exactin](operators.md#in-and-exactin-operators)** -operaattoreita alimerkkijonojen vastaavuuksille.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

**Search**-funktio etsii taulukosta tietueet, jotka sisältävät merkkijonon yhdessä niiden sarakkeista. Merkkijono saattaa sijaita missä tahansa sarakkeen kohdassa. Esimerkiksi hakusanat ”rob” ja ”bert” löytävät molemmat sarakkeen, jossa lukee ”Robert”. Haun kirjainkoolla ei ole merkitystä. Toisin kuin **Filter** ja **LookUp**, **Search**-funktio käyttää vastaavuuden etsimiseen yksittäistä merkkijonoa, ei kaavaa.

**Filter** ja **Search** palauttavat taulukon, joka sisältää samat sarakkeet kuin alkuperäinen taulukko sekä tietueet, jotka vastaavat ehtoja. **LookUp** palauttaa vain ensimmäisen löydetyn tietueen, jonka se on supistanut yhdeksi arvoksi kaavan avulla. Jos tietueita ei löydy, **Filter** ja **Search** palauttavat [tyhjän](function-isblank-isempty.md) taulukon, ja **LookUp** palauttaa arvon *tyhjä*.  

[Tables](../working-with-tables.md) on arvo PowerAppsissa, samaan tapaan kuin merkkijono tai numero. Ne voidaan välittää funktioihin ja palauttaa niistä.  **Filter**, **Search** ja **LookUp** eivät muokkaa taulukkoa. Sen sijaan ne kohtelevat taulukkoa argumenttina, josta ne palauttavat taulukon, tietueen tai yksittäisen arvon. Lisätietoja on kohdassa [taulukoiden käsitteleminen](../working-with-tables.md).

[!INCLUDE [delegation](../../../includes/delegation.md)]

## <a name="syntax"></a>Syntaksi
**Filter**( *Table*, *Formula1* [, *Formula2*, ... ] )

* *Table* – Pakollinen. Taulukko, josta haetaan.
* *Formula(s)* – Pakollinen. Kaava, jonka mukaan jokaista taulukon tietuetta arvioidaan. Funktio palauttaa kaikki tietueet, jotka palauttavat arvon **true**. Voit viitata sarakkeisiin taulukon sisällä. Jos annat useamman kuin yhden kaavan, kaikkien kaavojen tulokset yhdistetään **[And](function-logicals.md)** -funktiolla.

**Search**( *Table*, *SearchString*, *Column1* [, *Column2*, ... ] )

* *Table* – Pakollinen. Taulukko, josta haetaan.
* *SearchString* – Pakollinen. Haettava merkkijono. Jos arvo on *tyhjä* tai tyhjä merkkijono, kaikki tietueet palautetaan.
* *Column(s)* – Pakollinen. *Taulukon* sarakkeiden nimet, joista haetaan. Sarakkeiden, joista haetaan, on sisällettävä tekstiä. Sarakkeiden nimien on oltava merkkijonoja, jotka ovat lainausmerkeissä. Sarakkeiden nimien on kuitenkin oltava staattisia, eikä niitä voi laskea kaavalla. Jos jonkin haettavan sarakkeen tiedoista löytyy *SearchString*in osittainen vastaavuus, koko tietue palautetaan.

> [!NOTE]
> Jos SharePoint- ja Excel-tietolähteiden sarakenimissä käytetään välilyöntejä, merkitse jokaisen välilyönnin tilalle **\_x0020\_** . Voit esimerkiksi määrittää **Column Name** -arvoksi **"Sarakkeen_x0020_Nimi"** .

**LookUp**( *Table*, *Formula* [, *ReductionFormula* ] )

* *Table* – Pakollinen. Taulukko, josta haetaan. Syntaksi näytetään käyttöliittymässä *lähteenä* funktioruudun yläpuolella.
* *Formula* – Pakollinen.
  Kaava, jonka mukaan jokaista taulukon tietuetta arvioidaan. Funktio palauttaa ensimmäisen tietueen, jonka tulos on **true**. Voit viitata sarakkeisiin taulukon sisällä. Syntaksi näytetään käyttöliittymässä *ehtona* funktioruudun yläpuolella.
* *ReductionFormula* – Valinnainen. Tämä kaava lasketaan löydetylle tietueelle, ja se supistaa tietueen yksittäiseksi arvoksi. Voit viitata sarakkeisiin taulukon sisällä. Jos et käytä tätä parametria, funktio palauttaa koko tietueen taulukosta. Syntaksi näytetään käyttöliittymässä *tuloksena* funktioruudun yläpuolella.

## <a name="examples"></a>Esimerkkejä
Seuraavissa esimerkeissä käytetään **IceCream**-[tietolähdettä](../working-with-data-sources.md):

![](media/function-filter-lookup/icecream.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Filter( IceCream, OnOrder > 0 )** |Palauttaa tietueet, joissa **OnOrder** on suurempi kuin nolla. |<style> img { max-width: none; } </style> ![](media/function-filter-lookup/icecream-onorder.png) |
| **Filter( IceCream, Quantity + OnOrder > 225 )** |Palauttaa tietueet, joissa **Quantity**- ja **OnOrder**-sarakkeiden summa on suurempi kuin 225. |![](media/function-filter-lookup/icecream-overstock.png) |
| **Filter( IceCream, "chocolate" in Lower( Flavor ) )** |Palauttaa tietueet, joiden sarakkeessa **Flavor** esiintyy sana chocolate, kirjainkoosta riippumatta. |![](media/function-filter-lookup/icecream-chocolate.png) |
| **Filter( IceCream, Quantity < 10  && OnOrder < 20 )** |Palauttaa tietueet, joissa **Quantity** on alle 10 ja **OnOrder** on pienempi kuin 20.  Koska yksikään tietue ei vastaa näitä ehtoja, palautetaan tyhjä taulukko. |![](media/function-filter-lookup/icecream-empty.png) |
| **Search( IceCream, "choc", "Flavor" )** |Palauttaa tietueet, joiden sarakkeessa **Flavor** esiintyy merkkijono choc, kirjainkoosta riippumatta. |![](media/function-filter-lookup/icecream-chocolate.png) |
| **Search( IceCream, "", "Flavor" )** |Koska hakuehto on tyhjä, kaikki tietueet palautetaan. |![](media/function-filter-lookup/icecream.png) |
| **LookUp( IceCream, Flavor = "Chocolate", Quantity )** |Etsii tietuetta, jonka **Flavor** on Chocolate. Sellaisia on yksi.  Palauttaa ensimmäisen löydetyn tietueen **Quantity**-arvon. |100 |
| **LookUp( IceCream, Quantity > 150, Quantity + OnOrder )** |Etsii tietuetta, jonka **Quantity** on suurempi kuin 100. Sellaisia on useita.  Ensimmäisen löydetyn tietueen **Flavor** on Vanilja. Palauttaa kyseisen tietueen **Quantity**- ja **OnOrder**-sarakkeiden summan. |250 |
| **LookUp( IceCream, Flavor = "Pistachio", OnOrder )** |Etsii tietuetta, jonka **Flavor** on Pistachio. Sellaisia ei ole.  Koska yhtään tietuetta ei löytynyt, **Lookup** palauttaa arvon *tyhjä*. |*tyhjä* |
| **LookUp( IceCream, Flavor = "Vanilla" )** |Etsii tietuetta, jonka **Flavor** on Vanilla. Sellaisia on yksi.  Koska vähennyskaavaa ei annettu, koko tietue palautetaan. |Maku "Vanilja", määrä: 200, OnOrder: 75} |

### <a name="search-user-experience"></a>Käyttökokemuksen etsiminen
Monissa sovelluksissa hakukenttään voi kirjoittaa yhden tai useamman merkin. Tällä tavalla voit suodattaa tietueluetteloita suurissa tietojoukoissa. Luettelossa näytetään vain ne tietueet, jotka vastaavat kirjoittamiasi hakuehtoja.

Loput tämän ohjeaiheen esimerkeistä näyttävät hakutuloksia luettelosta, jonka nimi on **Customers**, joka sisältää nämä tiedot:

![](media/function-filter-lookup/customers.png)

Luo tämä tietolähde kokoelmana luomalla **[Painike](../controls/control-button.md)** -ohjausobjekti ja määrittämällä sen **OnSelect**-ominaisuuden arvoksi tämä kaava:

**ClearCollect (Customers, Table ({Name: "Fred Garcia", yritys: "Northwind Traders"}, {Name: "Cole Miller", yritys: "Contoso"}, {nimi: "Glenda Johnson", yritys: "Contoso"}, {nimi: "Mike Collins", yritys: "Adventure Works"}, {nimi: "Colleen Jones", yritys: "Adventure Works"}))**

Kuten tässä esimerkissä, voit näyttää luettelon [**Valikoima-ohjausobjektin**](../controls/control-gallery.md) tietueista näytön alareunassa. Näytön yläosassa voit lisätä [**Tekstisyöte**](../controls/control-text-input.md)-ohjausobjektin nimeltä **SearchInput**, jotta käyttäjät voivat määrittää, mitkä tietueet kiinnostavat heitä.

![](media/function-filter-lookup/customers-ux-unfiltered.png)

Kun käyttäjä kirjoittaa merkkejä **SearchInput**-ohjausobjektiin, valikoiman tulokset suodatetaan automaattisesti. Tässä tapauksessa valikoima on määritetty näyttämään tietueet, joiden asiakkaan nimi (ei yrityksen nimi) alkaa merkeillä, jotka on syötetty **SearchInput**-ohjausobjektiin. Jos käyttäjä kirjoittaa hakuruutuun **co**, valikoima näyttää nämä tulokset:

![](media/function-filter-lookup/customers-ux-startswith-co.png)

Voit suodattaa **Name**-sarakkeen perusteella määrittämällä valikoiman **Kohteet**-ominaisuudeksi jonkin seuraavista kaavoista:

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Filter( Customers, StartsWith( Name, SearchInput.Text ) )** |Suodattaa **Customers**-tietolähteestä tietueet, joiden **Name**-sarakkeen alussa esiintyy hakumerkkijono. Testin kirjainkoolla ei ole merkitystä. Jos käyttäjä kirjoittaa hakuruutuun **co**, valikoima näyttää tulokset **Colleen Jones** ja **Cole Miller**. Valikoima ei näytä tietuetta **Mike Collins**, koska sen **Name**-sarake ei ala hakumerkkijonolla. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-name-co-startswith.png) |
| **Filter( Customers, SearchInput.Text in Name )** |Suodattaa **Customers**-tietolähteestä tietueet, joiden **Name**-sarakkeen jossain kohdassa esiintyy hakumerkkijono. Testin kirjainkoolla ei ole merkitystä. Jos käyttäjä kirjoittaa hakukenttään **co**, valikoima näyttää tulokset **Colleen Jones,** **Cole Miller** ja **Mike Collins**, koska hakumerkkijono esiintyy jossain kohdassa tietueen **Name**-saraketta. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-name-co-contains.png) |
| **Search( Customers, SearchInput.Text, "Name" )** |**Search**-funktio etsii vastaavuutta missä tahansa kunkin tietueen **Name**-sarakkeen osassa, samaan tapaan kuin **in**-operaattori. Huomaa, että sarakkeen nimi on kirjoitettava lainausmerkkeihin. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-name-co-contains.png) |

Voit laajentaa haun sisältämään sekä **Company**-sarakkeen että **Name**-sarakkeen:

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Filter( Customers, StartsWith( Name, SearchInput.Text ) &#124;&#124; StartsWith( Company, SearchInput.Text ) )** |Suodattaa **Customers**-tietolähteestä tietueet, joiden **Name**-sarake tai **Company**-sarake alkaa hakumerkkijonolla (esimerkiksi **co**).  [ **&#124;&#124;** -operaattori ](operators.md) on *true*, jos jompikumpi **StartsWith**-funktio on *true*. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-all-co-startswith.png) |
| **Filter( Customers, hakusyöte.Text in Nimi &#124;&#124; hakusyöte.Text in Yritys)** |Suodattaa **Customers**-tietolähteestä tietueet, joiden **Name**-sarakkeen tai **Company**-sarakkeen jossain kohdassa esiintyy hakumerkkijono (esimerkiksi **co**). |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-all-co-contains.png) |
| **Search( Customers, SearchInput.Text, "Name", "Company" )** |Samoin kuin **in**-operaattori, **Search**-funktio hakee **Customers**-tietolähteestä tietueet, joiden **Name**-sarakkeen tai **Company**-sarakkeen jossain kohdassa esiintyy hakumerkkijono (esimerkiksi **co**). **Search**-funktio on helpompi lukea ja kirjoittaa kuin **Filter**-funktio, jos haluat määrittää useita sarakkeita ja useita **in**-operaattoreita. Huomaa, että sarakkeiden nimet on kirjoitettava lainausmerkkeihin. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-all-co-contains.png) |


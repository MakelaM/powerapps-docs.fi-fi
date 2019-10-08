---
title: Sort- ja SortByColumns-funktiot | Microsoft Docs
description: PowerAppsin Sort- ja SortByColumns-funktioiden viitetietoja, kuten syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/26/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: aa51c97eff57b9659e5fd246af8016898eeeb9df
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992229"
ms.PowerAppsDecimalTransform: true
---
# <a name="sort-and-sortbycolumns-functions-in-powerapps"></a>Sort- ja SortByColumns-funktiot PowerAppsissa
Lajittelee [taulukon](../working-with-tables.md).

## <a name="description"></a>Kuvaus
**Sort**-funktio lajittelee taulukon kaavan perusteella.  

Kaava lasketaan taulukon jokaisen [tietueen](../working-with-tables.md#records) kohdalla, ja tuloksia käytetään taulukon lajittelemiseen.  Kaavan tuloksen on oltava numero, merkkijono tai totuusarvo. Se ei voi olla taulukko tai tietue.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Jos haluat lajitella ensin yhden sarakkeen mukaan ja sitten toisen mukaan, upota **Sort**-kaava toisen kaavan sisään. Tämän kaavan avulla voit esimerkiksi lajitella **yhteys tieto** taulukon ensin **suku nimi** -sarakkeen mukaan ja sitten **Etunimi** -sarakkeen mukaan:  **Lajittele (lajittelu (yhteys tiedot, suku nimi), etunimi)**

**SortByColumns**-funktiolla voidaan myös lajitella taulukko yhden tai useamman sarakkeen mukaan.

**SortByColumns**-funktion parametriluettelosta saadaan sarakkeiden nimet, joiden perusteella lajitellaan, sekä sarakekohtainen lajittelusuunta.  Lajittelu suoritetaan parametrien määräämässä järjestyksessä (lajitellaan ensin ensimmäisen sarakkeen mukaan, sitten toisen ja niin edelleen).  Sarakenimet määritetään merkkijonoiksi, ja ne täytyy merkitä lainausmerkkeihin, jos ne lisätään suoraan parametrilistaan.  Esimerkiksi **SortByColumns( Asiakastaulukko; "Sukunimi" )** .

Voit yhdistää **SortByColumns**-funktion **[avattava luettelo](../controls/control-drop-down.md)** - tai **[luetteloruutu](../controls/control-list-box.md)** -ohjausobjektiin, jos haluat että käyttäjät voivat valita, minkä sarakkeen perusteella lajittelu suoritetaan.

Nousevan ja laskevan lajittelun lisäksi **SortByColumns** voi lajitella arvoja yksittäisen saraketaulukon mukaan.  Voit esimerkiksi lajitella tietueen viikonpäivän nimen mukaan lisäämällä lajittelujärjestykseksi **[ "Maanantai"; "Tiistai"; "Keskiviikko"; "Torstai"; "Perjantai"; "Lauantai"; "Sunnuntai" ]** .  Kaikki tietueet, joissa on **Maanantai**, tulevat ensin, tämän jälkeen **Tiistai** ja niin edelleen.  Löydetyt tietueet, jotka eivät näy lajittelutaulukossa, sijoitetaan luettelon loppuun.

[Tables](../working-with-tables.md) on arvo PowerAppsissa, samaan tapaan kuin merkkijono tai numero.  Ne voidaan välittää funktioihin ja niitä voidaan palauttaa funktioista.  **Sort** ja **SortByColumn** eivät muokkaa taulukkoa. Ne käsittelevät sen sijaan taulukkoa argumenttina ja palauttavat uuden, lajitellun taulukon.  Lisätietoja on kohdassa [taulukoiden käsitteleminen](../working-with-tables.md).

[!INCLUDE [delegation](../../../includes/delegation.md)]

## <a name="syntax"></a>Syntaksi
**Sort**( *Table*; *Formula* [; *SortOrder* ] )

* *Table* – Pakollinen. Lajiteltava taulukko.
* *Formula* – Pakollinen. Kaava lasketaan taulukon jokaisen tietueen kohdalla, ja tuloksia käytetään taulukon lajittelemiseen.  Voit viitata sarakkeisiin taulukon sisällä.
* *SortOrder* – Valinnainen. Määritä **SortOrder.Descending** lajitellaksesi taulukon laskevassa järjestyksessä. **SortOrder.Ascending** on oletusarvo.

**SortByColumns**( *Table*; *ColumnName1* [; *SortOrder1*; *ColumnName2*; *SortOrder2*; ... ] )

* *Table* – Pakollinen. Lajiteltava taulukko.
* *ColumnName(s)* – Pakollinen. Lajiteltavien sarakkeiden nimet merkkijonoina.
* *SortOrder(s)* – Valinnainen.  **SortOrder.Ascending** tai **SortOrder.Descending**.  **SortOrder.Ascending** on oletusarvo.  Jos useita *ColumnName(s)* -arvoja annetaan, kaikkien paitsi viimeisen sarakkeen tulee sisältää *SortOrder*.
  
    > [!NOTE]
  > Jos SharePoint- ja Excel-tietolähteiden sarakenimissä käytetään välilyöntejä, merkitse jokaisen välilyönnin tilalle **\_x0020\_** . Voit esimerkiksi määrittää **Column Name** -arvoksi **"Sarakkeen_x0020_Nimi"** .

**SortByColumns**( *Table*; *ColumnName*; *SortOrderTable* )

* *Table* – Pakollinen. Lajiteltava taulukko.
* *ColumnName* – Pakollinen. Lajiteltavan sarakkeen nimi merkkijonoina.
* *SortOrderTable* – Pakollinen.  Yksisarakkeinen arvotaulukko, jonka mukaan lajitellaan.
  
    > [!NOTE]
  > Jos SharePoint- ja Excel-tietolähteiden sarakenimissä käytetään välilyöntejä, merkitse jokaisen välilyönnin tilalle **\_x0020\_** . Voit esimerkiksi määrittää **Column Name** -arvoksi **"Sarakkeen_x0020_Nimi"** .

## <a name="examples"></a>Esimerkkejä
Seuraavissa esimerkeissä käytämme **IceCream**-[tietolähdettä](../working-with-data-sources.md), joka sisältää tämän taulukon tiedot:

![](media/function-sort/icecream.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Sort( IceCream; Flavor )**<br><br>**SortByColumns( IceCream; "Flavor" )** |Lajittelee **IceCream**-tietolähteen sen **Flavor**-sarakkeen mukaan. **Flavor**-sarake sisältää merkkijonoja, joten taulukko lajitellaan aakkosjärjestyksessä. Lajittelujärjestys on oletusarvoisesti nouseva. |<style> img { max-width: none; } </style> ![](media/function-sort/icecream-flavor.png) |
| **Sort( IceCream; Quantity )**<br><br>**SortByColumns( IceCream; "Quantity" )** |Lajittelee **IceCream**-tietolähteen sen **Quantity**-sarakkeen mukaan.  **Quantity**-sarake sisältää numeroita, joten taulukko lajitellaan numeerisesti.  Lajittelujärjestys on oletusarvoisesti nouseva. |![](media/function-sort/icecream-quantity-asc.png) |
| **Sort( IceCream; Quantity; SortOrder.Descending )**<br><br>**SortByColumns( IceCream; "Quantity"; SortOrder.Descending )** |Lajittelee **IceCream**-tietolähteen sen **Quantity**-sarakkeen mukaan.  **Quantity**-sarake sisältää numeroita, joten lajittelu tehdään numeerisesti.  Lajittelujärjestys on määritetty laskevaksi. |![](media/function-sort/icecream-quantity-desc.png) |
| **Sort( IceCream; Quantity + OnOrder )** |Lajittelee **IceCream**-tietolähteen sen **Quantity**- ja **OnOrder**-sarakkeiden summan mukaan, kunkin tietueen erikseen. Summa on luku, joten taulukko lajitellaan numeerisesti.  Lajittelujärjestys on oletusarvoisesti nouseva.  Koska lajittelemme kaavan mukaan emmekä sarakkeen raaka-arvojen mukaan, **SortByColumns**-funktion käyttämiselle ei ole vastinetta. |![](media/function-sort/icecream-total.png) |
| **Sort( Sort( IceCream; OnOrder ); Quantity )**<br><br>**SortByColumns( IceCream; "OnOrder"; Ascending; "Quantity"; Ascending )** |Lajittelee **IceCream**-tietolähteen ensin sen **OnOrder**-sarakkeen mukaan ja sitten sen **Quantity**-sarakkeen mukaan.  Huomaa, että "Pistachio" nousi kohteen "Vanilla" yläpuolelle ensimmäisessä lajittelussa **OnOrder**-sarakkeen mukaan, ja yhdessä ne siirtyivät oikeaan paikkaan **Quantity**-sarakkeessa. |![](media/function-sort/icecream-onorder-quantity.png) |
| **SortByColumns( IceCream; "Flavor"; [&nbsp;"Pistachio";&nbsp;"Strawberry"&nbsp;] )** |Lajittelee **IceCream**-tietolähteen sen **Flavor**-sarakkeen mukaan yksisarakkeisen taulukon pohjalta, joka sisältää kohteet "Pistachio" ja "Strawberry".  Tietueet, joiden **Flavor** on "Pistachio", näkyvät ensimmäisenä tuloksessa. Sen jälkeen näytetään tietueet, jotka sisältävät maun "Strawberry".  **Flavor**-sarakkeen arvot, joille ei löytynyt vastaavuutta, kuten "Vanilla", näkyvät vastanneiden kohteiden jälkeen. |![](media/function-sort/icecream-onflavor-sorttable.png) |

### <a name="step-by-step"></a>Vaihe vaiheelta
Voit suorittaa näitä esimerkkejä itse luomalla **IceCream**-tietolähteen [kokoelmana](../working-with-data-sources.md#collections):

1. Lisää painike ja määritä sen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:<br>**ClearCollect (IceCream; {Flavor: "Suklaa"; määrä: 100; OnOrder: 150}; {Flavor:  "Vanilja"; määrä: 200; OnOrder: 20}; {Flavor: "Mansikka"; määrä: 300; OnOrder: 0}; {Flavor: "Minttu suklaa"; määrä: 60; OnOrder: 100}; {Flavor: "Pistao"; määrä: 200; OnOrder: 10})**
2. Esikatsele sovellusta, valitse painike ja palaa oletustyötilaan painamalla ESC-näppäintä.
3. Valitse **Kokoelmat** **Tiedosto**-valikossa näyttääksesi juuri luomasi kokoelman. Palaa oletustyötilaan painamalla Esc-näppäintä.

#### <a name="sort"></a>Lajittelu
1. Lisää toinen painike ja aseta sen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>
   **ClearCollect( SortByFlavor; Sort( IceCream; Flavor ) )**
   
     Edellinen kaava luo toisen kokoelman, jonka nimi on **SortByFlavor**, ja se sisältää samat tiedot kuin **IceCream**. Uusi kokoelma sisältää **Flavor**-sarakkeen aakkosjärjestyksessä lajitellut tiedot nousevasti.
2. Paina F5-näppäintä, valitse uusi painike ja paina sitten ESC-näppäintä.
3. Valitse **Kokoelmat** **Tiedosto**-valikossa näyttääksesi molemmat kokoelmat. Palaa sitten oletustyötilaan painamalla ESC-näppäintä.
4. Toista kolme edellistä vaihetta, mutta muuta luotavan kokoelman nimeä ja korvaa **Sort**-kaava eri kaavalla sellaisessa aiemmissa esimerkeissä käytetyssä taulukossa, jossa käytettiin **Sort**-kaavaa.

#### <a name="sortbycolumns"></a>SortByColumns
1. Lisää toinen painike ja aseta sen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>
   **ClearCollect( SortByQuantity; SortByColumns( IceCream; "Quantity"; Ascending; "Flavor"; Descending ) )**
   
     Edellinen kaava luo kolmannen kokoelman, jonka nimi on **SortByQuantity**. Se sisältää samat tiedot kuin **IceCream**. Uusi kokoelma sisältää kuitenkin tiedot, jotka lajitellaan numeerisesti **määrä** -sarakkeen mukaan nousevassa järjestyksessä ja sitten **Flavor** -sarakkeen mukaan laskevassa järjestyksessä.
2. Paina F5-näppäintä, valitse uusi painike ja paina sitten ESC-näppäintä.
3. Valitse **Kokoelmat** **Tiedosto**-valikossa näyttääksesi kaikki kolme kokoelmaa. Palaa oletustyötilaan painamalla ESC-näppäintä.
4. Toista kolme edellistä vaihetta, mutta muuta luotavan kokoelman nimeä ja korvaa **SortByColumns**-kaava **SortByColumns**-funktiota käyttävällä eri kaavalla, joka on esitetty aiemmin tämän osion esimerkkitaulukossa.


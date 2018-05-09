---
title: Blank-, Coalesce-, IsBlank- ja IsEmpty-funktiot | Microsoft Docs
description: PowerAppsin Blank-, Coalesce-, IsBlank- IsEmpty-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.openlocfilehash: 80d06a30dbe334f7fa9691d2a56805d53876693c
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="blank-coalesce-isblank-and-isempty-functions-in-powerapps"></a>PowerAppsin Blank-, Coalesce-, IsBlank- ja IsEmpty-funktiot
Testaa, onko arvo tyhjä tai että sisältääkö [taulukko](../working-with-tables.md) nolla [tietuetta](../working-with-tables.md#records) ja mahdollistaa *tyhjien* arvojen luomisen.

## <a name="overview"></a>Yleiskatsaus
*Tyhjä* merkitsee "eri arvoa" tai "tuntematon arvo." **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti on *tyhjä*, jos käyttäjä ei ole syöttänyt siihen yhtään merkkiä. Tämä ohjausobjekti ei ole enää *tyhjä*, kun käyttäjä on kirjoittanut siihen merkkejä.  Jotkin tietolähteet voivat varastoida ja palauttaa NULL-arvoja, jotka esitetään PowerAppsissa *tyhjinä*.

> [!NOTE]
> Tällä hetkellä *tyhjän* arvon varastointia tuetaan vain paikallisille kokoelmille. Tiedämme, että monet tietolähteet tukevat *tyhjiä* arvoja (NULL), ja pyrimme poistamaan tämän rajoituksen.

Mikä tahansa ominaisuus tai laskettu arvo voi olla *tyhjä*.  Esimerkiksi totuusarvolla on yleensä kaksi arvoa: **tosi** tai **epätosi**.  Mutta näiden kahden lisäksi se voi olla myös *tyhjä*.  Tämä muistuttaa Microsoft Exceliä, missä laskentataulukon solu on ensin tyhjä, mutta voi muun muassa sisältää arvot **TOSI** tai **EPÄTOSI**. Solun sisältö voidaan milloin tahansa poistaa, jolloin se palautuu *tyhjä*-tilaan.

*Tyhjä* (Empty) viittaa erityisesti taulukoihin, jotka eivät sisällä tietueita. Taulukon rakenne voi olla kokonainen ja sisältää [sarakkeiden](../working-with-tables.md#columns) nimet, mutta taulukossa ei ole tietoja. Taulukko voi olla aluksi tyhjä ja se voi ottaa vastaan tietueita, jolloin se ei ole enää tyhjä ja siitä voidaan poistaa tietueet, jolloin se on jälleen tyhjä.

## <a name="description"></a>Kuvaus
**Blank**-funktio palauttaa *tyhjän* arvon. Käytä tätä tallentamaan näitä arvoja tukevan tietolähteen NULL-arvon tallentamiseen, jolloin käytännössä poistetaan kentän arvo.

**IsBlank**-funktio testaa, onko arvo *tyhjä*. *Tyhjiä* arvoja esiintyy esimerkiksi seuraavissa tilanteissa:

* **Blank**-funktion paluuarvo.
* Ohjausobjektin ominaisuudelle ei ole asetettu kaavaa.
* Tekstisyötekenttään ei ole syötetty arvoa tai luetteloruudussa ei ole tehty valintaa. Voit käyttää **IsBlank**-funktiota määrittämään pakollisen kentän.
* Merkkijonon, joka ei sisällä merkkejä, **[Len](function-len.md)**-arvo on 0.
* Funktiossa tapahtui virhe. Usein funktion yksi tai useampi argumentti ei ole kelvollinen. Monet funktiot palauttavat *tyhjän* arvon, jos argumentin arvo on *tyhjä*.
* Yhdistetyt [tietolähteet](../working-with-data-sources.md), kuten SQL Server, voivat käyttää "null"-arvoja. Nämä arvot näytetään *tyhjinä* PowerAppsissa.
* **[If](function-if.md)**-funktion *else*-osaa ei määritetty ja kaikkien ehtojen arvot olivat **epätosi**.
* Käytit **[Update](function-update-updateif.md)**-funktiota, mutta et määrittänyt arvoa kaikille sarakkeille. Näin ollen sarakkeille, joita et määrittänyt, ei asetettu arvoja.

**Coalesce**-funktio arvioi argumentin järjestyksessä ja palauttaa ensimmäisen arvon, joka ei ole *tyhjä*.  Käytä funktiota korvaamaan *tyhjä* arvo toisella arvolla niin, että ei-*tyhjiä* arvoja ei muuteta.  Jos kaikki argumentit ovat *tyhjiä*, funktio palauttaa *tyhjän* arvon.  Kaikkien **Coalesce**-funktion argumenttien täytyy olla samaa tyyppiä. Et voi esimerkiksi sekoittaa numeroita ja merkkijonoja.  **Coalesce( arvo1, arvo2 )** on tiiviimpi versio kaavasta **If( IsBlank( arvo1 ) arvo1, arvo2 )** eikä se vaadi **arvo1**:n arvioimista kahdesti.  

**IsEmpty**-funktio testaa, sisältääkö taulukko yhtään tietuetta. Se vastaa **[CountRows](function-table-counts.md)**-funktion käyttämistä, kun haetaan nollaa. Voit tarkistaa, onko tietolähteessä virheitä, yhdistämällä **IsEmpty**-funktion **[Errors](function-errors.md)**-funktioon.

Sekä **IsBlank**- että **IsEmpty**-funktion paluuarvo on totuusarvo, joka on joko **tosi** tai **epätosi**.

## <a name="syntax"></a>Syntaksi
**Blank**()

**Coalesce**( *Arvo1* [, *Arvo2*, ... ] )

* *Arvo(t)* – Pakollinen. Testattavat arvot.  Jokainen arvo arvioidaan, kunnes löydetään ei-*tyhjä* arvo.  Ensimmäisen ei-*tyhjän* arvon jälkeisiä arvoja ei arvioida.  

**IsBlank**( *Arvo* )

* *Arvo* – Pakollinen. Testattava arvo.

**IsEmpty**( *Taulukko* )

* *Taulukko* – Pakollinen. Taulukko, josta haetaan tietueita.

## <a name="examples"></a>Esimerkkejä
### <a name="blank"></a>Blank
> [!NOTE]
> Tällä hetkellä seuraava esimerkki toimii vain paikallisten kokoelmien kanssa.  Tiedämme, että monet tietolähteet tukevat *tyhjiä* arvoja (NULL), ja pyrimme poistamaan tämän rajoituksen.

1. Luo sovellus alusta alkaen ja lisää **Painike**-ohjausobjekti.
2. Määritä painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   
    **ClearCollect( Cities, { Name: "Seattle", Weather: "Rainy" } )**
3. Esikatsele sovellustasi, napsauta tai napauta luomaasi painiketta ja sulje esikatselu.  
4. Napsauta tai napauta **Tiedosto**-valikosta **Kokoelmat**.
   
     **Cities**-kokoelma avautuu ja siinä näytetään yksi tietue, jossa on "Seattle" ja "Rainy":
   
    ![Kokoelma, jossa näytetään Seattle ja sateinen sää](./media/function-isblank-isempty/seattle-rainy.png)
5. Palaa oletustyötilaan napsauttamalla tai napauttamalla takaisin-nuolta.
6. Lisää **Otsikko**-ohjausobjekti ja määritä sen **Text**-ominaisuudeksi seuraava kaava:
   
    **IsBlank( First( Cities ).Weather )**
   
    Otsikko näyttää arvon **epätosi**, koska **Weather** sisältää arvon ("Rainy").
7. Lisää toinen painike ja aseta sen **OnSelect**-ominaisuudeksi seuraava kaava:
   
    **Patch( Cities, First( Cities ), { Weather: Blank() } )**
8. Esikatsele sovellustasi, napsauta tai napauta luomaasi painiketta ja sulje esikatselu.  
   
    **Cities**-kohdan ensimmäisen tietueen **Weather**-kenttä korvataan *tyhjällä* arvolla. Siitä poistetaan siinä aiemmin ollut "Rainy".
   
    ![Kokoelma, jossa näytetään Seattle ja tyhjä sääkenttä](./media/function-isblank-isempty/seattle-blank.png)
   
    Otsikko näyttää arvon **tosi**, koska **Weather**-kenttä sisältää arvon.

### <a name="coalesce"></a>Coalesce
| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Coalesce( Blank(), 1 )** |Testaa **Blank**-funktion paluuarvon. Blank palauttaa aina *tyhjän* arvon. Koska ensimmäinen argumentti on *tyhjä*, arviointi jatkuu seuraavalla arvolla, kunnes löydetään ei-*tyhjä* arvo. |**1** |
| **Coalesce( Blank(), Blank(), Blank(), Blank(), 2, 3 )** |**Coalesce** aloittaa argumenttiluettelon alusta ja arvioi argumentteja, kunnes löydetään ei-*tyhjä* arvo.  Tässä tapauksessa ensimmäiset neljä argumenttia palauttavat kaikki *tyhjän* arvon, joten arviointi jatkuu viidenteen argumenttiin. Viidennen argumentin arvo on ei-*tyhjä*, joten arviointi päättyy tähän. Viidennen argumentin arvo palautetaan ja kuudetta argumenttia ei arvioida. |**2** |

### <a name="isblank"></a>IsBlank
1. Luo sovellus alusta alkaen, lisää Tekstisyöte-ohjausobjekti ja anna sille nimeksi **FirstName**.
2. Lisää otsikko ja aseta sen **[Text](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **If( IsBlank( FirstName.Text ), "Etunimi on pakollinen kenttä." )**
   
    Oletuksena Tekstisyöte-ohjausobjektin **[Text](../controls/properties-core.md)**-ominaisuudeksi asetetaan **"Text input"**. Koska ominaisuus sisältää arvon, se ei ole tyhjä, ja otsikko ei näytä mitään viestiä.
3. Poista kaikki merkit Tekstisyöttö-ohjausobjektista, mukaan lukien välilyönnit.
   
    Koska **[Text](../controls/properties-core.md)**-ominaisuus ei sisällä enää merkkejä, se on *tyhjä* ja **IsBlank( FirstName.Text )** palauttaa arvon **tosi**. Pakollisesta kentästä ilmoittava viesti näytetään.

Katso tietoa vahvistuksen suorittamisesta muilla työkaluilla **[Validate](function-validate.md)**-funktion aiheesta ja [tietolähteiden kanssa työskentelyn](../working-with-data-sources.md) aiheesta.  

Muita esimerkkejä:

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **IsBlank( Blank() )** |Testaa **Blank**-funktion paluuarvon. Blank palauttaa aina *tyhjän* arvon. |**tosi** |
| **IsBlank( "" )** |Merkkijono, joka ei sisällä merkkejä. |**tosi** |
| **IsBlank( "Hei" )** |Merkkijono, joka sisältää yhden tai useamman merkin. |**epätosi** |
| **IsBlank( *AnyCollection* )** |Koska [kokoelma](../working-with-data-sources.md#collections) on olemassa, se ei ole tyhjä, vaikka se ei sisältäisi tietueita. Jos haluat tarkistaa, onko kokoelma tyhjä, käytä **IsEmpty**-funktiota. |**epätosi** |
| **IsBlank( Mid( "Hei", 17, 2 ) )** |**[Mid](function-left-mid-right.md)**-aloitusmerkki on merkkijonon jälkeen.  Tuloksena on tyhjä merkkijono. |**tosi** |
| **IsBlank( If( false, false ) )** |**[If](function-if.md)**-funktio ilman *ElseResult*:ia.  Koska ehto on aina **epätosi**, tämä **[If](function-if.md)** palauttaa aina *tyhjän* arvon. |**tosi** |

### <a name="isempty"></a>IsEmpty
1. Luo sovellus alusta alkaen ja lisää **Painike**-ohjausobjekti.
2. Määritä painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   
    **Collect( IceCream, { Flavor: "Strawberry", Quantity: 300 }, { Flavor: "Chocolate", Quantity: 100 } )**
3. Esikatsele sovellustasi, napsauta tai napauta luomaasi painiketta ja sulje esikatselu.  
   
    Kokoelma nimeltä **IceCream** luodaan ja se sisältää nämä tiedot:
   
    ![](media/function-isblank-isempty/icecream-strawberry-chocolate.png)
   
    Tässä kokoelmassa on kaksi tietuetta ja se ei ole tyhjä. **IsEmpty( IceCream )** palauttaa arvon **epätosi** ja **CountRows( IceCream )** palauttaa arvon **2**.
4. Lisää toinen painike ja aseta sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   
    **Clear( IceCream )**
5. Esikatsele sovellustasi, napsauta tai napauta toista painiketta ja sulje esikatselu.  
   
    Kokoelma on nyt tyhjä:
   
    ![](media/function-isblank-isempty/icecream-clear.png)
   
    **[Clear](function-clear-collect-clearcollect.md)**-funktio poistaa kaikki tietueet kokoelmasta, jolloin tuloksena on tyhjä kokoelma. **IsEmpty( IceCream )** palauttaa arvon **tosi** ja **CountRows( IceCream )** palauttaa arvon **0**.

Voit testata **IsEmpty**-funktiolla, onko laskettu taulukko tyhjä, kuten seuraavissa esimerkeissä:

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **IsEmpty( [&nbsp;1,&nbsp;2,&nbsp;3 ] )** |Yhden sarakkeen taulukko sisältää kolme tietuetta, eikä se siis ole tyhjä. |**epätosi** |
| **IsEmpty( [&nbsp;] )** |Yhden sarakkeen taulukko ei sisällä tietueita, joten se on tyhjä. |**tosi** |
| **IsEmpty( Filter( [&nbsp;1,&nbsp;2,&nbsp;3&nbsp;], Value > 5 ) )** |Yhden sarakkeen taulukko ei sisällä tietueita, joiden arvo on suurempi kuin 5.  Suodattimen tulos ei sisällä tietueita, joten se on tyhjä. |**tosi** |


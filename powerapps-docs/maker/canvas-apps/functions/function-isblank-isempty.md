---
title: Blank-, Coalesce-, IsBlank- ja IsEmpty-funktiot | Microsoft Docs
description: PowerAppsin Blank-, Coalesce-, IsBlank- IsEmpty-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.component: canvas
ms.date: 08/27/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d932d43bd9474f3cd7ca63ef0ef0a51a9e74ca91
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984753"
ms.PowerAppsDecimalTransform: true
---
# <a name="blank-coalesce-isblank-and-isempty-functions-in-powerapps"></a>PowerAppsin Blank-, Coalesce-, IsBlank- ja IsEmpty-funktiot
Testaa, onko arvo tyhjä tai sisältääkö [taulukko](../working-with-tables.md) nolla [tietuetta](../working-with-tables.md#records), ja mahdollistaa *tyhjien* arvojen luomisen.

## <a name="overview"></a>Yleiskatsaus
*Blank* merkitsee ”ei arvoa” tai ”tuntematon arvo”.  Esimerkiksi **[yhdistelmä ruutu](../controls/control-combo-box.md)** -ohjaus objektin **valittu** ominaisuus on *tyhjä* , jos käyttäjä ei ole tehnyt valintaa. Monet tieto lähteet voivat tallentaa ja palauttaa TYHJÄARVOJA, jotka esitetään Powerappsissa *tyhjinä*.

Powerappsin mikä tahansa ominaisuus tai laskettu arvo voi olla *tyhjä*.  Esimerkiksi totuusarvolla on yleensä kaksi arvoa: **tosi** tai **epätosi**.  Näiden kahden lisäksi se voi myös olla *tyhjä* , joka ilmaisee, että tilaa ei tiedetä.  Tämä on samanlainen kuin Microsoft Excel, jossa laskenta taulukon solu alkaa tyhjästä ilman sisältöä, mutta se voi sisältää arvot **True** tai **false** (muun muassa). Solun sisältö voidaan milloin tahansa tyhjentää uudelleen, jolloin se palautetaan *tyhjään* tilaan.

*Tyhjä merkki jono* viittaa merkki jonoon, joka ei sisällä merkkejä.  [ **Len** -funktio](function-len.md) palauttaa nollan tälle merkki jonolle, ja se voidaan kirjoittaa kaavoihin kahdessa lainaus merkeissä, joissa ei ole mitään välillä `""`.  Jotkin ohjaus objekteista ja tieto lähteistä käyttävät tyhjää merkki jonoa, joka ilmaisee No Value-ehdon.  Sovellusten luonnin yksinkertaistamiseksi **isblank** -ja **conalesce** -Funktiot testaavat sekä *tyhjiä* arvoja että tyhjiä merkki jonoja.    

*Tyhjä* **-funktiolla** tyhjä on määritetty taulu koille, jotka eivät sisällä tietueita. Taulukon rakenne voi olla kokonainen ja sisältää [sarakkeiden](../working-with-tables.md#columns) nimet, mutta taulukossa ei ole tietoja. Taulukko voi olla aluksi tyhjä, se voi ottaa vastaan tietueita, jolloin se ei ole enää tyhjä, ja siitä voidaan poistaa tietueet, jolloin se on jälleen tyhjä.

> [!NOTE]
> Olemme siirtymävaiheessa.  Tähän asti *tyhjiä* on käytetty myös virheiden raportelemiseen, jolloin ei ole mahdollista erotella kelvollista "No Value"-arvoa virheestä.  Tästä syystä *tyhjien* arvojen tallentamista tuetaan tällä hetkellä vain paikallisille kokoelmille.  Voit tallentaa *tyhjiä* arvoja muihin tieto lähteisiin, jos otat käyttöön kaava tason virheiden hallinnan kokeellisen ominaisuuden tiedosto-valikosta, sovellus asetukset, lisä asetukset ja kokeelliset ominaisuudet.  Pyrimme aktiivisesti viimeistelemään tämän ominaisuuden ja suorittamaan *tyhjien* arvojen asianmukaisen erottelun virheistä.

## <a name="description"></a>Kuvaus
**Blank**-funktio palauttaa *tyhjän* arvon. Käytä tätä näitä arvoja tukevan tietolähteen NULL-arvon tallentamiseen, jolloin käytännössä poistetaan kentän arvo.

*Tyhjän* arvon tai tyhjän merkki jonon **onblank** -funktioiden testit.  Testi sisältää tyhjiä merkki jonoja, jotka helpottavat sovelluksen luontia, koska jotkin tieto lähteet ja ohjaus toiminnot käyttävät tyhjää merkki jonoa, kun arvoa ei ole.  Jos haluat testata erityisesti *tyhjää* arvoa, käytä `if( Value = Blank(); ...` **isblank**-kohteen asemesta.

**Conalesce** -funktio arvioi sen argumentit järjestyksessä ja palauttaa ensimmäisen arvon, joka ei ole *tyhjä* tai tyhjä merkki jono.  Tämän funktiolla korvataan *tyhjä* arvo tai tyhjä merkki jono, jolla on eri arvo, mutta jätetään muut kuin*Tyhjät* merkki jono arvot ennalleen.  Jos kaikki argumentit ovat *tyhjiä* tai tyhjiä merkki jonoja, funktio palauttaa *tyhjän*, jolloin **sulautuvat** oikein, jotta tyhjät merkki jonot voidaan *muuntaa tyhjiksi arvoiksi.*  Kaikkien **Coalesce**-funktion argumenttien täytyy olla samaa tyyppiä. Et voi esimerkiksi sekoittaa numeroita ja merkkijonoja.  

`Coalesce( value1; value2 )` on suppeampi `If( Not IsBlank( value1 ); value1; Not IsBlank( value2 ); value2 )`-arvo, eikä se edellytä **arvo1** -ja **arvo2** -laskentaa kahdesti.  [ **IF** -funktio](function-if.md) palauttaa *tyhjän* , jos ei ole muuta-kaavaa, kuten tässä tapa uksessa.

**IsEmpty**-funktio testaa, sisältääkö taulukko yhtään tietuetta. Se vastaa **[CountRows](function-table-counts.md)** -funktion käyttämistä, kun haetaan nollaa. Voit tarkistaa, onko tietolähteessä virheitä, yhdistämällä **IsEmpty**-funktion **[Errors](function-errors.md)** -funktioon.

Sekä **IsBlank**- että **IsEmpty**-funktion paluuarvo on totuusarvo, joka on joko **tosi** tai **epätosi**.

## <a name="syntax"></a>Syntaksi
**Blank**()

**Coalesce**( *Arvo1* [; *Arvo2*; ... ] )

* *Arvo(t)* – Pakollinen. Testattavat arvot.  Jokainen arvo arvioidaan järjestyksessä, kunnes arvo ei ole *tyhjä* eikä tyhjää merkki jonoa löytynyt.  Tämän pisteen jälkeisiä arvoja ei lasketa.  

**IsBlank**( *Arvo* )

* *Value* – pakollinen. Arvo, jonka avulla testataan *tyhjä* arvo tai tyhjä merkki jono.

**IsEmpty**( *Taulukko* )

* *Taulukko* – Pakollinen. Taulukko, josta haetaan tietueita.

## <a name="examples"></a>Esimerkkejä
### <a name="blank"></a>Blank
> [!NOTE]
> Tällä hetkellä seuraava esimerkki toimii vain paikallisten kokoelmien kanssa.  Voit tallentaa *tyhjiä* arvoja muihin tieto lähteisiin, jos otat käyttöön kaava tason virheiden hallinnan kokeellisen ominaisuuden tiedosto-valikosta, sovellus asetukset, lisä asetukset ja kokeelliset ominaisuudet.  Pyrimme aktiivisesti viimeistelemään tämän ominaisuuden ja suorittamaan *tyhjien* arvojen erottamisen virheistä.

1. Luo sovellus alusta alkaen ja lisää **Painike**-ohjausobjekti.
2. Määritä painikkeen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    ClearCollect( Cities; { Name: "Seattle"; Weather: "Rainy" } )
    ```
3. Esikatsele sovellustasi, napsauta tai napauta luomaasi painiketta ja sulje esikatselu.  
4. Napsauta tai napauta **Tiedosto**-valikosta **Kokoelmat**.

     **Cities**-kokoelma avautuu, ja siinä näytetään yksi tietue, jossa on "Seattle" ja "Rainy":

    ![Kokoelma, jossa näytetään Seattle ja sateinen sää](./media/function-isblank-isempty/seattle-rainy.png)
5. Palaa oletustyötilaan napsauttamalla tai napauttamalla takaisin-nuolta.
6. Lisää **Otsikko**-ohjausobjekti ja määritä sen **Text**-ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    IsBlank( First( Cities ).Weather )
    ```

    Otsikko näyttää arvon **epätosi**, koska **Weather** sisältää arvon ("Rainy").
7. Lisää toinen painike ja aseta sen **OnSelect**-ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    Patch( Cities; First( Cities ); { Weather: Blank() } )
    ```
8. Esikatsele sovellustasi, napsauta tai napauta luomaasi painiketta ja sulje esikatselu.  

    **Cities**-kohdan ensimmäisen tietueen **Weather**-kenttä korvataan *tyhjällä* arvolla. Siitä poistetaan siinä aiemmin ollut "Rainy".

    ![Kokoelma, jossa näytetään Seattle ja tyhjä sääkenttä](./media/function-isblank-isempty/seattle-blank.png)

    Otsikko näyttää arvon **tosi**, koska **Weather**-kenttä sisältää arvon.

### <a name="coalesce"></a>Coalesce

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Conalesce (&nbsp;Blank (), &nbsp;1 @ no__t-3)** |Testaa **Blank**-funktion paluuarvon. Blank palauttaa aina *tyhjän* arvon. Koska ensimmäinen argumentti on *tyhjä*, arviointi jatkuu seuraavan argumentin kohdalle, kunnes löydettiin muu kuin*tyhjä* arvo ja muu kuin tyhjä merkki jono. |**1** |
| **Sulautuvat ("", 2)** |Testaa ensimmäistä argumenttia, joka on tyhjä merkki jono. Koska ensimmäinen argumentti on tyhjä merkki jono, arviointi jatkuu seuraavan argumentin kanssa, kunnes löydettiin muu kuin*tyhjä* arvo ja muu kuin tyhjä merkki jono. |**2** |
| **Colalesce (tyhjä (), ", tyhjä ()," ", 3, 4)** |**Conalesce** alkaa argumentti luettelon alusta ja arvioi kutakin argumenttia vuorotellen, kunnes löydettiin muu kuin*tyhjä* arvo ja muu kuin tyhjä merkki jono.  Tässä tapa uksessa neljä ensimmäistä argumenttia palauttavat *tyhjän* merkki jonon tai tyhjän merkki jonon, joten arviointi jatkuu viidenteen argumenttiin. Viides argumentti ei ole*tyhjä* merkki jono, joka ei ole tyhjä, joten arviointi päättyy tähän. Viidennen argumentin arvo palautetaan, ja kuudetta argumenttia ei arvioida. |**3** |
| **Sulautuvat ("")** | Testaa ensimmäistä argumenttia, joka on tyhjä merkki jono. Koska ensimmäinen argumentti on tyhjä merkki jono eikä enempää argumentteja, funktio palauttaa *tyhjän*.   |*tyhjä* |

### <a name="isblank"></a>IsBlank
1. Luo sovellus alusta alkaen, lisää Tekstisyöte-ohjausobjekti ja anna sille nimeksi **FirstName**.
2. Lisää otsikko ja aseta sen **[Text](../controls/properties-core.md)** -ominaisuudeksi tämä kaava:

    ```powerapps-comma
    If( IsBlank( FirstName.Text ); "First Name is a required field." )
    ```

    Oletuksena Tekstisyöte-ohjausobjektin **[Text](../controls/properties-core.md)** -ominaisuudeksi asetetaan **"Text input"** . Koska ominaisuus sisältää arvon, se ei ole tyhjä, eikä otsikko näytä mitään viestiä.
3. Poista kaikki merkit Tekstisyöttö-ohjausobjektista, mukaan lukien välilyönnit.

    Koska **[Text](../controls/properties-core.md)** -ominaisuus ei enää sisällä merkkejä, se on tyhjä merkki jono, ja **isblank (firstname. text)** on **True**. Pakollisesta kentästä ilmoittava viesti näytetään.

Katso tietoa vahvistuksen suorittamisesta muilla työkaluilla **[Validate](function-validate.md)** -funktion aiheesta ja [tietolähteiden kanssa työskentelyn](../working-with-data-sources.md) aiheesta.  

Muita esimerkkejä:

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Isiblank (&nbsp;Blank () &nbsp;)** |Testaa **Blank**-funktion paluuarvon. Blank palauttaa aina *tyhjän* arvon. |**tosi** |
| **IsBlank( "" )** |Merkkijono, joka ei sisällä merkkejä. |**tosi** |
| **IsBlank( "Hei" )** |Merkkijono, joka sisältää yhden tai useamman merkin. |**epätosi** |
| **IsBlank( *AnyCollection* )** |Koska [kokoelma](../working-with-data-sources.md#collections) on olemassa, se ei ole tyhjä, vaikka se ei sisältäisi tietueita. Jos haluat tarkistaa, onko kokoelma tyhjä, käytä **IsEmpty**-funktiota. |**epätosi** |
| **IsBlank( Mid( "Hei"; 17; 2 ) )** |**[Mid](function-left-mid-right.md)** -aloitusmerkki on merkkijonon jälkeen.  Tuloksena on tyhjä merkkijono. |**tosi** |
| **IsBlank( If( false; false ) )** |**[If](function-if.md)** -funktio ilman *ElseResult*:ia.  Koska ehto on aina **epätosi**, tämä **[If](function-if.md)** palauttaa aina *tyhjän* arvon. |**tosi** |

### <a name="isempty"></a>IsEmpty
1. Luo sovellus alusta alkaen ja lisää **Painike**-ohjausobjekti.
2. Määritä painikkeen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:

    **Collect (IceCream; {Flavor: "Mansikka"; määrä: 300}; {Flavor: "Suklaa"; määrä: 100})**
3. Esikatsele sovellustasi, napsauta tai napauta luomaasi painiketta ja sulje esikatselu.  

    Kokoelma nimeltä **IceCream** luodaan ja se sisältää nämä tiedot:

    ![](media/function-isblank-isempty/icecream-strawberry-chocolate.png)

    Tässä kokoelmassa on kaksi tietuetta, eikä se ole tyhjä. **IsEmpty( IceCream )** palauttaa arvon **epätosi** ja **CountRows( IceCream )** palauttaa arvon **2**.
4. Lisää toinen painike ja aseta sen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:

    **Clear( IceCream )**
5. Esikatsele sovellustasi, napsauta tai napauta toista painiketta ja sulje esikatselu.  

    Kokoelma on nyt tyhjä:

    ![](media/function-isblank-isempty/icecream-clear.png)

    **[Clear](function-clear-collect-clearcollect.md)** -funktio poistaa kaikki tietueet kokoelmasta, jolloin tuloksena on tyhjä kokoelma. **IsEmpty( IceCream )** palauttaa arvon **tosi** ja **CountRows( IceCream )** palauttaa arvon **0**.

Voit testata **IsEmpty**-funktiolla, onko laskettu taulukko tyhjä, kuten seuraavissa esimerkeissä:

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **IsEmpty( [&nbsp;1;&nbsp;2;&nbsp;3 ] )** |Yhden sarakkeen taulukko sisältää kolme tietuetta, eikä se siis ole tyhjä. |**epätosi** |
| **IsEmpty( [&nbsp;] )** |Yhden sarakkeen taulukko ei sisällä tietueita, joten se on tyhjä. |**tosi** |
| **IsEmpty( Filter( [&nbsp;1;&nbsp;2;&nbsp;3&nbsp;]; Value > 5 ) )** |Yhden sarakkeen taulukko ei sisällä tietueita, joiden arvo on suurempi kuin 5.  Suodattimen tulos ei sisällä tietueita, joten se on tyhjä. |**tosi** |


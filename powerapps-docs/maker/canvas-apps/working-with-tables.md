---
title: Tutustu taulukkoihin | Microsoft Docs
description: Taulukoiden, sarakkeiden ja tietueiden käsittelemisen viitetiedot
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: 42a7c0db6aaf46d8cdbd112cf72c6f95f58dc9ec
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="understand-tables-and-records-in-powerapps"></a>Tutustu taulukkoihin ja tietueisiin PowerAppsissa
Voit luoda sovelluksen, joka käyttää tietoja Microsoft Excelistä, SharePointista, SQL Serveristä ja useista muista lähteistä, jotka tallentavat tietoja tietueisiin ja taulukkoihin. Jos haluat käsitellä tällaisia tietoja tehokkaasti, tutustu näiden rakenteiden taustalla oleviin käsitteisiin.

* Tietue sisältää yhden tai useamman henkilön, sijainnin tai asian tietoluokan. Tietue voi esimerkiksi sisältää yksittäisen asiakkaan nimen, sähköpostiosoitteen ja puhelinnumeron. Muut työkalut viittaavat tietueeseen termillä ”rivi” tai ”kohde”.
* Taulukko sisältää yhden tai useampia tietueita, jotka sisältävät samat tietoluokat. Taulukko saattaa esimerkiksi sisältää 50 asiakkaan nimet, sähköpostiosoitteet ja puhelinnumerot.

Sovelluksessa käytetään [kaavoja](working-with-formulas.md), joilla luodaan, päivitetään ja käsitellään tietueita ja taulukkoja. Todennäköisesti luet ja kirjoitat tietoja ulkoiseen [tietolähteen](working-with-data-sources.md), joka on laajennettu taulukko. Lisäksi luot ehkä yhden tai useita sisäisiä taulukoita, joita kutsutaan [kokoelmiksi](working-with-data-sources.md#collections).

Voit luoda erilaisia kaavoja, jotka ottavat taulukon nimen argumenttina samalla tavalla kuin kaavat Excelissä ottavat yhden tai useampia soluviittauksia argumentteina. Jotkin powerAppsin kaavat palauttavat taulukon, joka kuvastaa määrittämiäsi argumentteja. Voit esimerkiksi luoda seuraavan kaavan:

* päivittämään tietueen taulukossa määrittämällä kyseisen taulukon yhtenä useista argumenteista **[Ohjelmakorjaus](functions/function-patch.md)**-funktiolle
* lisäämään, poistamaan ja nimeämään uudelleen taulukon sarakkeet määrittämällä kyseisen taulukon argumenttina **[AddColumns](functions/function-table-shaping.md)**-, **[DropColumns](functions/function-table-shaping.md)**- tai **[RenameColumns](functions/function-table-shaping.md)**-funktiolle. Mikään näistä funktioista ei muokkaa alkuperäistä taulukkoa. Sen sijaan funktio palauttaa toisen taulukon määrittämiesi argumenttien perusteella.

## <a name="elements-of-a-table"></a>Taulukon osat
![](media/working-with-tables/elements-of-a-table.png)

### <a name="records"></a>Tietueet
Kukin tietue sisältää vähintään yhden henkilön, sijainnin tai asian tietoluokan. Edellä olevassa esimerkissä näkyy tietue kullekin tuotteelle (**Chocolate**, **Bread** ja **Water**) ja sarakkeen kullekin tietoluokalle (**Price**, **Quantity on Hand** ja **Quantity on Order**).

Kaavassa voit viitata tietueeseen yksinään, taulukon kontekstin ulkopuolella, käyttämällä aaltosulkeita. Tätä tietuetta **{ Name: "Strawberries", Price: 7.99 }** ei esimerkiksi ole liitetty taulukkoon.

### <a name="fields"></a>Kentät
Kenttä on yksittäinen tieto tietueessa. Voit visualisoida tämän tyyppisen kentän arvona tietylle tietueelle.

Samoin kuin ohjausobjektilla, kenttään viitataan tietueeseen käyttämällä **.** [-operaattoria](functions/operators.md) tietueessa.  Esimerkiksi **First(Products).Name** palauttaa **Name**-kentän **Products**-taulukon ensimmäiselle tietueelle.

Kenttä voi sisältää toiseen tietueen tai taulukon, kuten esimerkki **[GroupBy](functions/function-groupby.md)**-funktiosta esittää. Voit asettaa sisäkkäin niin monta tieto- ja taulukkotasoa kuin haluat.

### <a name="columns"></a>Sarakkeet
Sarake viittaa taulukon yhden tai useamman tietueen samaan kenttään. Yllä olevassa esimerkissä kullakin tuotteella on hinta-kenttä, ja kyseinen hinta on samassa sarakkeessa kaikille tuotteille.  Yllä olevassa taulukossa on neljä saraketta, jotka näkyvät yläreunassa vaakasuunnassa:

* **Name**
* **Price**
* **Quantity on Hand**
* **Quantity on Order**

Sarakkeen nimi kuvastaa kyseisen sarakkeen kenttiä.

Kaikki sarakkeen arvot ovat samaa tietotyyppiä. Yllä olevassa esimerkissä ”Quantity on Hand” -sarake sisältää aina luvun eikä voi sisältää merkkijonoa, kuten ”12 units”, yhdelle tietueelle.  Minkä tahansa kentän arvo voi myös olla *tyhjä*.  

Olet ehkä on kutsunut sarakkeita ”kentiksi” muissa työkaluissa.

> [!NOTE]
> SharePoint- ja Excel-tietolähteissä, joissa on välilyönnin sisältäviä sarakenimiä, PowerApps korvaa välilyönnit merkkijonolla **\_x0020\_**. Esimerkiksi **"Sarakkeen Nimi"** SharePointissa tai Excelissä näkyy muodossa **"Sarakkeen_x0020_Nimi"** PowerAppsissa, kun se näytetään tietoasettelussa tai sitä käytetään kaavassa.

### <a name="table"></a>Taulukko
Taulukko koostuu yhdestä tai useammasta tietueesta, joista kullakin on useita kenttiä, joilla on yhtenäiset nimet kaikissa tietueet.

Kaikilla taulukoilla, joka on tallennettu tietolähteeseen tai kokoelmaan, on nimi, jolla viitataan taulukkoon, ja se välitetään funktioille, jotka ottavat taulukot argumentteina.  Taulukot voivat olla myös funktion tai kaavan tulos.

Seuraavan esimerkin mukaisesti voit ilmaista taulukon kaavan **[Table](functions/function-table.md)**-funktiolla, jossa on tietuejoukko, jotka ilmaistaan aaltosulkeilla:

**Table( { Value: "Strawberry" }, { Value: "Vanilla" } )**

Voit myös määrittää yksisarakkeisen taulukon hakasulkeilla.  Edellinen kaava voidaan kirjoittaa myös näin:

**[ "Strawberry", "Vanilla" ]**

## <a name="table-formulas"></a>Taulukkokaavat
Excelissä ja PowerAppsissa käytetään kaavoja, joilla käsitellään numeroita ja tekstimerkkijonoja samankaltaisilla tavoilla:

* Kirjoita Excelissä arvo, kuten **42** soluun **A1**, ja kirjoita sitten kaava, kuten **A1 + 2**, toiseen soluun näyttääksesi arvon **44**.
* Määritä PowerAppsissa **Slider1**:n **[Default](controls/properties-core.md)**-ominaisuudeksi **42**, ja määritä selitteen **[Text](controls/properties-core.md)**-ominaisuudeksi **Slider1.Value + 2** näyttääksesi arvon **44**.

Molemmissa tapauksissa laskettu arvo muuttuu automaattisesti, jos muutat argumenttien arvoja (esimerkiksi numeroa solussa **A1** tai **Slider1**:n arvoa).

Kaavojen avulla voit vastaavasti käsitellä tietoja taulukoissa ja tietueissa. Voit käyttää taulukoiden nimiä argumentteina joissakin kaavoissa, kuten **Min(Catalog, Price)**, jotta voit näyttää **Catalog**-taulukon alimman arvon **Price**-sarakkeessa. Muut kaavat tarjoavat kokonaisia taulukkoja palautusarvoina, kuten **RenameColumns(Catalog, "Price", "Cost")**, joka palauttaa kaikki tietueet **Catalog**-taulukosta, mutta muuttaa**Price**-sarakkeen nimeksi **Cost**.

Samoin kuin numerot, kaavat, jotka liittyvät taulukkoihin ja tietueisiin, lasketaan automaattisesti uudelleen, kun niiden pohjana oleva taulukko tai tietue muuttuu. Jos **Catalog**-taulukon tuotteen hinta laskee edellistä vähimmäishintaa alhaisemmaksi, **[Min](functions/function-aggregates.md)**-kaavan palautusarvo muuttuu automaattisesti tätä vastaavaksi.

Katsotaan joitakin yksinkertaisia esimerkkejä.

1. Lisää **Text gallery** -ohjausobjekti ja määritä sen **[Items](controls/properties-core.md)**-ominaisuudeksi taulukon nimi.
   
    Valikoima näyttää oletusarvoisesti paikkamerkkitekstin taulukosta nimeltä **TextualGallerySample**. Valikoiman **[Items](controls/properties-core.md)**-ominaisuudeksi asetetaan automaattisesti tämä taulukko.
   
    > [!NOTE]
> Jotkin ohjausobjektit on järjestetty uudelleen ja suurennettu esimerkkitarkoituksessa.
   
    ![](media/working-with-tables/gallery-items.png)
2. Sen sijaan, että asetat **[Items](controls/properties-core.md)**-ominaisuudeksi taulukon nimen, aseta se kaavaksi, joka sisältää taulukon nimen argumenttina, kuten tässä esimerkissä:<br>
   **Sort(TextualGallerySample, Heading, Descending)**
   
    Tämä kaava sisältää **[Sort](functions/function-sort.md)**-funktion, joka ottaa taulukon nimen ensimmäisenä argumenttinaan ja sarakkeen nimen kyseisessä taulukossa toisena argumenttinaan. Funktio tukee myös valinnaista kolmatta argumenttia, joka määrää, että tietojen lajittelu tehdään laskevassa järjestyksessä.
   
    ![](media/working-with-tables/gallery-items-sort.png)
3. Aseta **[Items](controls/properties-core.md)**-ominaisuudeksi kaava, joka ottaa kaavan edellisestä vaiheesta argumenttina ja palauttaa taulukon, kuten tässä esimerkissä:<br>
   **FirstN(Sort(TextualGallerySample, Heading, Descending), 2)**
   
    Tässä kaavassa käytetään **[FirstN](functions/function-first-last.md)**-funktiota näyttämään tietty tietueiden määrä taulukossa. Voit käyttää **[Sort](functions/function-sort.md)**-funktiota ensimmäisenä **[FirstN](functions/function-first-last.md)**-argumenttina ja numeroa (tässä tapauksessa **2**) toisena argumenttina, joka määrittää, kuinka monta tietuetta näytetään.
   
    Koko kaava palauttaa taulukon, joka sisältää **TextualGallerySample**-taulukon kaksi ensimmäistä tietuetta lajiteltuna **Heading**-sarakkeen mukaan laskevassa järjestyksessä.
   
    ![](media/working-with-tables/gallery-items-sort-firstn.png)

### <a name="table-functions-and-control-properties"></a>Taulukkofunktiot ja ohjausobjektien ominaisuudet
Monet PowerAppsin funktiot ottavat taulukon nimen argumenttina, luovat toisen taulukon, joka sisältää samat tiedot, käsittelevät uuden taulukon muiden argumenttien perusteella ja palauttavat sitten tuloksen. Nämä funktiot eivät muokkaa alkuperäistä taulukkoa, vaikka se olisi tietolähde.

* **[Sort](functions/function-sort.md)**, **[Filter](functions/function-filter-lookup.md)** – Lajittelee ja suodattaa tietueita.
* **[FirstN](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)** – Palauttaa taulukon ensimmäiset tai viimeiset N-tietueet.
* **[Abs](functions/function-numericals.md)**, **[Sqrt](functions/function-numericals.md)**, **[Round](functions/function-round.md)**, **[RoundUp](functions/function-round.md)**, **[RoundDown](functions/function-round.md)** – aritmeettiset toiminnot kullekin yksisarakkeisen taulukon tietueelle, mistä tuloksena saadaan tulosten yksisarakkeinen taulukko.
* **[Left](functions/function-left-mid-right.md)**, **[Mid](functions/function-left-mid-right.md)**, **[Right](functions/function-left-mid-right.md)**, **[Replace](functions/function-replace-substitute.md)**, **[Substitute](functions/function-replace-substitute.md)**, **[Trim](functions/function-trim.md)**, **[Lower](functions/function-lower-upper-proper.md)**, **[Upper](functions/function-lower-upper-proper.md)**, **[Proper](functions/function-lower-upper-proper.md)** – merkkijonon käsittelytoimintoja yksisarakkeisen taulukon kullekin tietueelle, mistä tuloksena saadaan merkkijonojen yksisarakkeinen taulukko.
* **[Len](functions/function-len.md)** – Palauttaa merkkijonosarakkeessa yksisarakkeisen taulukon, joka sisältää jokaisen merkkijonon pituuden.
* **[Concatenate](functions/function-concatenate.md)** – yhdistää useita merkkijonojen sarakkeita, mistä tuloksena saadaan merkkijonojen yksisarakkeinen taulukko.
* **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)**, **[RenameColumns](functions/function-table-shaping.md)**, **[ShowColumns](functions/function-table-shaping.md)** – Sarakkeen käsittelyä taulukossa, mistä saadaan tuloksena uusi taulukko, jossa on erilaisia sarakkeita.
* **[Distinct](functions/function-distinct.md)** – Poistaa tietueiden kaksoiskappaleet.
* **[Shuffle](functions/function-shuffle.md)** – Sekoittaa tietueita satunnaisessa järjestyksessä.
* **[HashTags](functions/function-hashtags.md)** – Etsii aihetunnisteita merkkijonosta.
* **[Errors](functions/function-errors.md)** – Antaa virhetietoja työskenneltäessä tietolähteen parissa.

Voit suorittaa funktion taulukossa, joka sisältää useita sarakkeita, vaikka funktio vaatisi yksittäisen sarakkeen argumenttina. Voit purkaa yksittäisen sarakkeen usean sarakkeen taulukosta **[ShowColumns](functions/function-table-shaping.md)**-funktiolla argumenttina funktiolle, jota haluat käyttää, kuten tässä esimerkissä:<br>**Lower( ShowColumns( Products, "Name" ) )**

Tämä kaava luo yksisarakkeisen taulukon, joka sisältää **Products**-taulukon **Name**-sarakkeiden kaikki tiedot, mutta muuntaa kaikki isot kirjaimet pieniksi kirjaimiksi. Jos määrität taulukon argumenttina funktiolle **[AddColumns](functions/function-table-shaping.md)**, **[RenameColumns](functions/function-table-shaping.md)** tai **[ DropColumns](functions/function-table-shaping.md)**, voit muotoilla kyseisen taulukon täysin haluamallasi tavalla.

Jos määrität tietolähteen argumenttina jollekin näistä funktioista, kyseisen tietolähteen tietueita muokataan, ja tietolähteen uusi arvo taulukkona palautetaan yleensä.

* **[Collect](functions/function-clear-collect-clearcollect.md)**, **[Clear](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)** – Luo tai tyhjentää kokoelman tai lisää siihen.
* **[Update](functions/function-update-updateif.md)**, **[UpdateIf](functions/function-update-updateif.md)** – Päivittää tietueet vastaamaan yhtä tai useampia määrittämiäsi ehtoja.
* **[Remove](functions/function-remove-removeif.md)**, **[RemoveIf](functions/function-remove-removeif.md)** – Poistaa tietueet, jotka vastaavat yhtä tai useampaa määrittämääsi ehtoa.

Seuraavilla ohjausobjekteilla on ominaisuuksia, jotka ovat taulukoita:

* **Items** – Koskee valikoimia ja luetteloruutuja. Taulukko näytetään valikoimassa.
* **SelectedItems** – Koskee luetteloruutuja. Käyttäjän valitsemien kohteiden taulukko.

## <a name="record-formulas"></a>Tietueen kaavat
Voit myös luoda kaavan, joka laskee yksittäisen tietueen tiedot, ottaa argumentiksi yksittäisen tietueen ja tarjoaa yksittäisen tietueen palautusarvona. Katsotaan uudestaan edellistä valikoimaesimerkkiä. Käytetään **Gallery1.Selected**-ominaisuutta näyttämään tiedot mistä tahansa tietueesta, jonka käyttäjä valitsee kyseisestä valikoimasta.

1. Lisää painike ja määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
    **Collect( SelectedRecord, Gallery1.Selected )**

2. Jos painike ei ole valittuna, valitse se napsauttamalla sitä ja suorita kaava napsauttamalla sitä uudelleen.

3. Valitse **Tiedosto**-valikosta **Kokoelmat**.

![](media/working-with-tables/selected-collection.png)

Tämä kaava palauttaa tietueen, joka sisältää valikoiman sillä hetkellä valitun tietueen tietojen lisäksi myös valikoiman jokaisen ohjausobjektin. Tietue sisältää esimerkiksi sekä **Body**-sarakkeen, joka vastaa alkuperäisen taulukon **Body**-saraketta, että **Body1** sarakkeen, joka edustaa otsikkoa, joka näyttää kyseisen sarakkeen tiedot. Valitse **Body1**-sarakkeen taulukko-kuvake, niin voit porautua näihin tietoihin.

Nyt kun sinulla on valittuna tietue, voit poistaa siitä yksittäisiä kenttiä **.** -operaattorilla.

1. Painamalla Esc-näppäintä voit palata oletusarvoiseen työtilaan ja lisätä sitten otsikon valikoiman alle.

2. Määritä selitteen **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
    **Gallery.Selected.Heading**
   
    ![](media/working-with-tables/gallery-selected.png)

Olet ottanut **Selected**-ominaisuuden, joka on tietue, ja poiminut siitä **Heading**-ominaisuuden.  

Voit myös käyttää tietuetta yleiskäyttöisenä säilönä liittyville nimetyille arvoille.

* Jos luot kaavan funktioiden **[UpdateContext](functions/function-updatecontext.md)** ja **[Navigate](functions/function-navigate.md)** ympärille, kerää päivitettävät [kontekstimuuttujat](working-with-variables.md#create-a-context-variable) tietueen avulla.
* Käytä **[Edit form](controls/control-form-detail.md)** -ohjausobjektin **[Updates](controls/control-form-detail.md)**-ominaisuutta keräämään muutokset, jotka käyttäjä on tehnyt lomakkeeseen.
* Käytä **[Patch](functions/function-patch.md)**-funktiota päivittämään tietolähde mutta myös yhdistämään tietueita.

Näissä tapauksissa tietue ei koskaan ollut taulukon osa.

### <a name="record-functions-and-control-properties"></a>Tietuefunktiot ja ohjausobjektien ominaisuudet
Funktiot, jotka palauttavat tietueita:

* **[FirstN](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)** – Palauttaa taulukon ensimmäisen tai viimeisen N-tietueen.
* **[Lookup](functions/function-filter-lookup.md)** – Palauttaa ensimmäisen tietueen taulukosta, joka vastaa yhtä tai useampia ehtoja.
* **[Patch](functions/function-patch.md)** – Päivittää tietolähteen tai yhdistää tietueita.
* **[Defaults](functions/function-defaults.md)** – Palauttaa tietolähteelle oletusarvot.

Ominaisuudet, jotka palauttavat tietueita:

* **Selected** – Koskee valikoimia ja luetteloruutuja. Palauttaa valittuna olevan tietueen.
* **Updates** – Koskee valikoimia.  Tuo yhteen kaikki muutokset, jotka käyttäjä tekee tietolomakkeeseen.
* **[Update](functions/function-update-updateif.md)** – Koskee syöteohjausobjekteja, kuten tekstisyötteen ohjausobjekteja ja liukusäätimiä. Määrittää yksittäiset ominaisuudet valikoimalle tietojen kokoamiseksi.

## <a name="record-scope"></a>Tietueen laajuus
Jotkin toiminnot toimivat arvioimalla kaavan kaikissa taulukon tietueissa erikseen.  Kaavan tulosta käytetään eri tavoin:  

* **Filter**, **Lookup** – Kaava määrittää, sisällytetäänkö tietue tulokseen.
* **Sort** – Kaava antaa arvon, jonka mukaan tietueita lajitellaan.
* **Concat** – Kaava määrittää merkkijonot, jotka yhdistetään.
* **ForAll** – Kaava voi palauttaa minkä tahansa arvon mahdollisen sivuvaikutuksen kanssa.
* **Distinct** – Kaava palauttaa arvon, jolla tunnistetaan tietueiden kaksoiskappaleet.  
* **AddColumns** – Kaava antaa lisätyn kentän arvon.
* **Average**, **Max**, **Min**, **Sum**, **StdevP**, **VarP** – Kaava antaa koostearvon.

Näissä kaavoissa voidaan viitata käsiteltäviin tietueen kenttiin.  Kaikki nämä funktiot luovat ”tietueen vaikutusalueen”, jossa kaava lasketaan, tietueen kenttien ollessa käytettävissä ylimmän tason tunnisteina.  Voit myös viitata ohjausobjektin ominaisuuksiin ja muihin arvoihin sovelluksesi eri osista.

Katsotaan esimerkiksi **Products**-taulukkoa:

![](media/working-with-tables/requested.png)

Määritä, pyydettiinkö mitään näitä tuotteita enemmän kuin niitä oli saatavana:

**Filter( Products, 'Quantity Requested' > 'Quantity Available' )**

Ensimmäinen suodatuksen **Filter**-argumentti on käsiteltävä tietueiden taulukko, ja toinen argumentti on kaava.  **Filter** luo tietueen laajuuden kaavan arvioimista varten, missä käytettävissä ovat jokaisen tietueen kentät, tässä tapauksessa **Product**, **Quantity Requested** ja **Quantity Available**.  Vertailun tulos määrittää, sisällytetäänkö jokainen tietue funktion tulokseen:

![](media/working-with-tables/needed.png)

Laajennetaan esimerkkiä laskemalla, paljonko kutakin tuotetta tilataan:

**AddColumns( Filter( Products, 'Quantity Requested' > 'Quantity Available' ), "Quantity To Order", 'Quantity Requested' - 'Quantity Available' )**

Tässä lisäämme lasketun sarakkeen tulokseen.  **AddColumns**illa on oma tietuealueensa, jolla se laskee pyydettyjen ja saatavana olevien tuotteiden välisen eron.

![](media/working-with-tables/toorder.png)

Lopuksi voimme pienentää tulostaulukkoa niin, että se sisältää vain haluamamme sarakkeet:

**ShowColumns( AddColumns( Filter( Products, 'Quantity Requested' > 'Quantity Available' ), "Quantity To Order", 'Quantity Requested' - 'Quantity Available' ), "Product", "Quantity To Order" )**

![](media/working-with-tables/toorderonly.png)

Huomaa, että käytämme edellä toisinaan lainausmerkkejä (”) ja toisinaan heittomerkkejä (').  Heittomerkkejä on käytettävä, kun viitataan objektin arvoon, kuten kenttään tai taulukkoon, kun objektin nimessä on välilyönti.  Lainausmerkkejä käytetään, kun emme viittaa objektin arvoon, vaan sen sijaan keskustelemme siitä. Tämä koskee erityisesti tilanteita, joissa objektia ei vielä ole, kuten **AddColumns**in yhteydessä.  

### <a name="disambiguation"></a>Selvitys
Tietuealueen kanssa lisätyt kentän nimet ohittavat samat nimet muualta sovelluksesta.  Kun näin tapahtuu, voit edelleen käyttää arvoja tietuealueen ulkopuolelta käyttämällä [**@** selvitysoperaattoria](functions/operators.md):

* Voit käyttää sisäkkäisten tietuealueiden arvoja **@** -operaattorin avulla ja käytettävän taulukon nimeä mallin ***Table *[@* FieldName*]** avulla.  
* Voit käyttää yleisiä arvoja, kuten tietolähteitä, kokoelmia ja kontekstimuuttujia, mallin **[@*ObjectName*]** avulla (ilman taulukon nimeä).

Jos käsiteltävä taulukko on lauseke, kuten **Filter( *table*, ... )**, selvitysoperaattoria ei voi käyttää.  Vain sisin tietuealue voi käyttää kenttiä tästä taulukkolausekkeesta ilman selvitysoperaattoria.

Kuvitellaan esimerkiksi kokoelma **X**:

![](media/working-with-tables/X.png)

Voit luoda tämän kokoelman käyttämällä **ClearCollect( X, \[1, 2\] )**.

Ja toisen kokoelman **Y**:

![](media/working-with-tables/Y.png)

Voit luoda tämän kokoelman käyttämällä **ClearCollect( Y, ["A", "B"] )**.

Määritä lisäksi kontekstimuuttuja nimeltä **Value** tällä kaavalla: **UpdateContext( {Value: "!"} )**

Kootaan sitten kaikki tiedot yhteen.  Tässä kontekstissa seuraava kaava:

* **Ungroup( ForAll( X, ForAll( Y, Y[@Value] & Text( X[@Value] ) & [@Value] ) ), "Value" )**

tuottaa tämän taulukon:

![](media/working-with-tables/XY.png)

Mitä tapahtui?  Uloin **ForAll**-funktio määrittää tietuealueen **X**:lle myöntäen käyttöoikeuden kunkin tietueen **Value**-kenttään, kun niitä käsitellään.  Sitä voidaan käyttää yksinkertaisesti sanalla **Value** tai tekstillä **X[@Value]**.

Sisin **ForAll**-funktio määrittää toisen tietuealueen **Y**:lle.  Koska tässä taulukossa on myös määritetty **Value**-kenttä, **Value**-kentän käyttäminen tässä viittaa kenttään **Y**:n tietueessa eikä enää **X**:n tietueessa.  Jotta **X**:n **Value**-kenttää voidaan käyttää, joudumme käyttämään pidempää versiota ja selvitysoperaattoria.

Koska **Y** on alueen sisin tietue, tämän taulukon tietuiden käyttämiseen ei tarvita selvitystä. Näin ollen voimme käyttää tätä kaavaa ja samaa tulosta:

* **Ungroup( ForAll( X, ForAll( Y, Value & Text( X[@Value] ) & [@Value] ) ), "Value" )**

Kaikki **ForAll**-tietuealueet ohittavat yleisen vaikutusalueen.  Määrittämämme **Value**-kontekstimuuttuja ei ole käytettävissä nimen mukaan ilman selvennysoperaattoria.   Jotta voimme käyttää tätä arvoa, joudumme käyttämään tekstiä **[@Value]**.

**Ungroup** tasoittaa tuloksen, koska sisäkkäiset **ForAll**-funktiot tuottavat sisäkkäisen tulostaulukon.

## <a name="inline-syntax"></a>Sisäinen syntaksi
### <a name="records"></a>Tietueet
Tietueita voidaan ilmaista aaltosulkeilla, jotka sisältävät nimetyt kenttäarvot.  Voit esimerkiksi ilmaista ohjeaiheen alussa taulukon ensimmäisen tietueen käyttämällä seuraavaa kaavaa:

**{ Name: "Chocolate", Price: 3.95, 'Quantity on Hand': 12, 'Quantity on Order': 10 }**

Voit myös upottaa kaavoja muihin kaavoihin, kuten tässä esimerkissä näytetään:

**{ Name: First(Products).Name, Price: First(Products).Price * 1.095 }**

Voit sijoittaa tietueita sisäkkäin käyttämällä aaltosulkeita sisäkkäin, kuten tässä esimerkissä näytetään:

**{ 'Quantity': { 'OnHand': ThisItem.QuantOnHand, 'OnOrder': ThisItem.QuantOnOrder } }**

Lisää jokaisen sarakkeen nimi, joka sisältää erikoismerkin, kuten välilyönnin tai kaksoispisteen, heittomerkkien sisään.  Kun haluat käyttää heittomerkkiä sarakkeen nimen sisällä, tuplaa se.

Huomaa, että arvo **Price**-sarakkeessa ei sisällä valuuttasymbolia, kuten dollarimerkkiä. Kyseinen muotoilu otetaan käyttöön, kun arvo näytetään.  

### <a name="tables"></a>Taulukot
Voit luoda taulukon **[Table](functions/function-table.md)**-funktiolla ja tietuejoukolla. Voit ilmaista taulukon ohjeaiheen alussa käyttämällä seuraavaa kaavaa:

**Table( { Name: "Chocolate", Price: 3.95, 'Quantity on Hand': 12, 'Quantity on Order': 10 },<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ Name: "Bread", Price: 4.95, 'Quantity on Hand': 34, 'Quantity on Order': 0 },<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ Name: "Water", Price: 4.95, 'Quantity on Hand': 10, 'Quantity on Order': 0 } )**

Voit myös asettaa taulukoita sisäkkäin:

**Table( { Name: "Chocolate",<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'Quantity History': Table( { Quarter: "Q1", OnHand: 10, OnOrder: 10 },<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ Quarter: "Q2", OnHand: 18, OnOrder: 0 } ) } )**

### <a name="value-tables"></a>Arvotaulukot
Voit luoda yhden sarakkeen taulukoita määrittämällä arvot hakasulkeisissa. Tuloksena saatavassa taulukossa on yksittäinen sarake nimeltä **Value**.

Esimerkiksi **[ 1, 2, 3, 4 ]** vastaa kaavaa **Table( { Value: 1 }, { Value: 2 }, { Value: 3 }, { Value: 4 } )** ja palauttaa tämän taulukon:

![](media/working-with-tables/inline-table.png)


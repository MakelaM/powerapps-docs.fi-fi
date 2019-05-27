---
title: Taulukoiden ymmärtäminen pohjaan perustuvissa sovelluksissa | Microsoft Docs
description: Viitetietoja pohjaan perustuvan sovelluksen taulukoiden, sarakkeiden ja tietueiden käyttämisestä PowerAppsissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 264bce9c986544f8294d4a0346be2e7694d606d8
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/24/2019
ms.locfileid: "66216209"
---
# <a name="understand-canvas-app-tables-and-records-in-powerapps"></a>Pohjaan perustuvan sovelluksen taulukoiden ja tietueiden ymmärtäminen PowerAppsissa

Voit luoda PowerAppsissa pohjaan perustuvan sovelluksen, joka käyttää tietoja Microsoft Excelistä, SharePointista, SQL Serveristä ja useista muista lähteistä, jotka tallentavat tietoja tietueisiin ja taulukkoihin. Jos haluat käsitellä tällaisia tietoja mahdollisimman tehokkaasti, tutustu näiden rakenteiden taustalla oleviin käsitteisiin.

* Tietue sisältää yhden tai useamman tietoluokan, joka koskee henkilöä, paikkaa tai asiaa. Tietue voi esimerkiksi sisältää yksittäisen asiakkaan nimen, sähköpostiosoitteen ja puhelinnumeron. Muut työkalut viittaavat tietueeseen termillä ”rivi” tai ”kohde”.
* Taulukko sisältää yhden tai useampia tietueita, jotka sisältävät samat tietoluokat. Taulukko saattaa esimerkiksi sisältää 50 asiakkaan nimet, sähköpostiosoitteet ja puhelinnumerot.

Kun luot, päivität ja käsittelet sovelluksessasi tietueita ja taulukkoja, tarvitset [kaavoja](working-with-formulas.md). Todennäköisesti luet ja kirjoitat tietoja ulkoiseen [tietolähteeseen](working-with-data-sources.md), joka on laajennettu taulukko. Lisäksi luot ehkä yhden tai useita sisäisiä taulukoita, joita kutsutaan [kokoelmiksi](working-with-data-sources.md#collections).

Voit luoda erilaisia kaavoja, joille taulukon nimi annetaan argumenttina samalla tavoin kuin Excelissä olevalle kaavalle annetaan yksi tai useampi soluviittaus argumentteina. Jotkin PowerAppsin kaavat palauttavat taulukon, joka kuvastaa muita argumentteja, joita sinä määrität. Voit luoda kaavan esimerkiksi:

* päivittämään taulukossa olevan tietueen siten, että kyseinen taulukko määritetään yhdeksi **[Patch](functions/function-patch.md)**-funktion useista argumenteista
* lisäämään, poistamaan ja nimeämään uudelleen taulukon sarakkeita siten, että kyseinen taulukko määritetään argumentiksi **[AddColumns](functions/function-table-shaping.md)**-, **[DropColumns](functions/function-table-shaping.md)**- tai **[RenameColumns](functions/function-table-shaping.md)**-funktiolle. Mikään näistä funktioista ei muokkaa alkuperäistä taulukkoa. Sen sijaan funktio palauttaa toisen taulukon määrittämiesi argumenttien perusteella.

## <a name="elements-of-a-table"></a>Taulukon osat
![](media/working-with-tables/elements-of-a-table.png)

### <a name="records"></a>Tietueet
Kukin tietue sisältää vähintään yhden henkilön, sijainnin tai asian tietoluokan. Edellä olevassa esimerkissä näkyy tietue kullekin tuotteelle (**Suklaa**, **Leipä** ja **Vesi**) ja sarakkeet kullekin tietoluokalle (**Hinta**, **Saatavilla oleva määrä** ja **Tilattu määrä**).

Jos haluat viitata kaavassa johonkin tietueeseen yksinään taulukon kontekstin ulkopuolella, voit käyttää aaltosulkeita. Esimerkiksi tämä tietue **{nimi: ”Mansikat”, hinta: 7.99}** ei ole liitetty taulukkoon. Huomaa, että kyseisessä esimerkissä olevat kenttien nimet, kuten **Nimi** ja **Hinta**, eivät ole lainausmerkeissä.

### <a name="fields"></a>Kentät
Kenttä on yksittäinen tieto-osio tietueessa. Voit määrittää tämän tyyppisen kentän näkymään arvona tietyssä tietueessa olevassa sarakkeessa.

Samoin kuin ohjausobjektilla, tietueen kenttää viitataan käyttämällä tietueessa **.** [-operaattoria](functions/operators.md).  Esimerkiksi **First(Tuotteet).Nimi** hakee **Nimi**-kentän sisällön **Tuotteet**-taulukon ensimmäiseen tietueeseen.

Kenttä voi sisältää toisen tietueen tai taulukon, kuten esimerkki **[GroupBy](functions/function-groupby.md)**-funktiosta esittää. Voit asettaa sisäkkäin niin monta tieto- ja taulukkotasoa kuin haluat.

### <a name="columns"></a>Sarakkeet
Sarake viittaa kenttään, joka on yhteinen taulukon tietueessa oleville tietueille. Edellä kuvatussa esimerkissä kullakin tuotteella on Hinta-kenttä, ja kaikkien tuotteiden Hinta-kenttä näkyy samassa sarakkeessa.  Edellä olevan taulukon yläreunassa on neljä saraketta:

* **Nimi**
* **Hinta**
* **Käytettävissä oleva määrä**
* **Tilauksen määrä**

Sarakkeen nimi kuvastaa kyseisen sarakkeen kenttiä.

Kaikki sarakkeen arvot ovat samaa tietotyyppiä. Edellä kuvatussa esimerkissä ”Käytettävissä oleva määrä” -sarake sisältää kutakin tietuetta kohden yhden numeron, eikä se voi sisältää merkkijonoa, kuten ”12 yksikköä”.  Minkä tahansa kentän arvo voi olla myös *tyhjä*.  

Olet ehkä on kutsunut sarakkeita ”kentiksi” muissa työkaluissa.

> [!NOTE]
> SharePoint- ja Excel -tietolähteissä, joissa on välilyönnin sisältäviä sarakenimiä, PowerApps korvaa välilyönnit merkkijonolla **\_x0020\_** . Esimerkiksi SharePointissa tai Excelissä näkyvä **"Sarakkeen Nimi"** näkyy PowerAppsissa muodossa **"Sarakkeen_x0020_Nimi"** , kun se näytetään tietoasettelussa tai sitä käytetään kaavassa.

### <a name="table"></a>Taulukko
Taulukko koostuu yhdestä tai useammasta tietueesta, ja jokaisessa tietueessa on useita kenttiä. Kenttien nimet ovat yhdenmukaisia kaikissa tietueissa.

Kaikilla tietolähteeseen tai kokoelmaan tallennetuilla taulukoilla on nimi, jolla käyttäjä viittaa taulukkoon. Tämä nimi annetaan funktioon argumenttina.  Taulukkoja voidaan saada myös funktion tai kaavan tuloksena.

Seuraavassa esimerkissä taulukko ilmaistaan kaavassa käyttämällä **[Table](functions/function-table.md)**-funktiota, ja funktion tietojoukko ilmaistaan aaltosulkeilla:

`Table( { Value: "Strawberry" }, { Value: "Vanilla" } )`

Voit myös määrittää yksisarakkeisen taulukon käyttämällä hakasulkeita.  Edellisen kaavan voi kirjoittaa myös näin:

`[ "Strawberry", "Vanilla" ]`

## <a name="table-formulas"></a>Taulukkokaavat
Excelissä ja PowerAppsissa käytetään kaavoja, joilla käsitellään numeroita ja tekstimerkkijonoja samalla tavoin:

* Kirjoita Excelissä soluun **A1** arvo **42**, ja kirjoita sitten toiseen soluun kaava **A1 + 2**. Näkyviin tulee arvo **44**.
* Määritä PowerAppsissa **Slider1**:n **[Oletus](controls/properties-core.md)**-ominaisuudeksi **42**, ja määritä selitteen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **Slider1.Arvo + 2**, jolloin näkyviin tulee arvo **44**.

Kummassakin tapauksessa laskettu arvo muuttuu automaattisesti, jos muutat argumenttien arvoja (esimerkiksi numeroa solussa **A1** tai **Slider1**:n arvoa).

Samalla tavoin voit käyttää kaavoja taulukoissa ja tietueissa olevien tietojen käyttöönottoon ja käsittelyyn. Voit käyttää taulukoiden nimiä argumentteina joissakin kaavoissa. Esimerkiksi käyttämällä kaavaa **Min(Tuoteluettelo, Hinta)** voit näyttää **Tuoteluettelo**-taulukon pienimmän arvon **Hinta**-sarakkeessa. Lisäksi on kaavoja, jotka tarjoavat palautusarvoina kokonaisia taulukkoja. Esimerkiksi **RenameColumns(Tuoteluettelo, "Hinta", "Kustannus")** -kaava palauttaa kaikki tietueet **Tuoteluettelo**-taulukosta, mutta muuttaa**Hinta**-sarakkeen nimeksi **Kustannus**.

Numeroiden tavoin myös taulukkoihin ja tietueisiin liittyvät kaavat lasketaan automaattisesti uudelleen, jos niiden pohjana oleva taulukko tai tietue muuttuu. Jos **Tuoteluettelo**-taulukossa olevan tuotteen aiheuttama kustannus laskee edellistä vähimmäisarvoa pienemmäksi, **[Min](functions/function-aggregates.md)**-kaavan palautusarvo muuttuu automaattisesti tätä vastaavaksi.

Katsotaan joitakin yksinkertaisia esimerkkejä.

1. Luo tyhjä sovellus puhelinta varten ja lisää pystysuora **[Valikoima](controls/control-gallery.md)** -ohjausobjekti, joka sisältää muita ohjausobjekteja.

    Näytössä näkyy oletusarvoisesti paikkamerkkiteksti taulukosta, jonka nimi on **CustomGallerySample**. **[Items](controls/properties-core.md)**-ominaisuus näytön **[Valikoima](controls/control-gallery.md)**-ohjausobjektissa määritetään automaattisesti kyseiseen taulukkoon.

    ![](media/working-with-tables/gallery-items.png)

    > [!NOTE]
    > Jotkin ohjausobjektit on järjestetty uudelleen ja suurennettu esimerkkitarkoituksessa.

2. Sen sijaan, että määrittäisit **[Kohteet](controls/properties-core.md)**-ominaisuuden taulukon nimelle, määritä se kaavalle, jossa taulukon nimi annetaan argumenttina tämän esimerkin mukaisesti:

    `Sort(CustomGallerySample, SampleHeading, Descending)`

    Tämä kaava sisältää **[Sort](functions/function-sort.md)**-funktion, jossa taulukon nimi (TextualGallerySample) on ensimmäinen argumentti ja taulukossa olevan sarakkeen nimi (Heading) toinen argumentti. Funktio tukee myös valinnaista kolmatta argumenttia, joka määrää, että tietojen lajittelu tehdään laskevassa järjestyksessä (Descending).

    ![](media/working-with-tables/gallery-items-sort.png)

3. Aseta **[Kohteet](controls/properties-core.md)**-ominaisuudeksi kaava, jolle edellisen vaiheen kaava annetaan argumenttina. Kaava palauttaa taulukon tämän esimerkin mukaisesti:

    `FirstN(Sort(CustomGallerySample, SampleHeading, Descending), 2)`

    Tässä kaavassa käytetään **[FirstN](functions/function-first-last.md)**-funktiota näyttämään taulukossa tietty määrä tietueita. **[Sort](functions/function-sort.md)**-funktio on **[FirstN](functions/function-first-last.md)**-funktion ensimmäinen argumentti, ja numero (tässä tapauksessa **2**) on toinen argumentti, joka määrittää, kuinka monta tietuetta näytetään.

    Koko kaava palauttaa taulukon, jossa **CustomGallerySample**-taulukon kaksi ensimmäistä tietuetta näkyvät laskevassa järjestyksessä **SampleHeading**-sarakkeessa.

    ![](media/working-with-tables/gallery-items-sort-firstn.png)

## <a name="table-functions-and-control-properties"></a>Taulukkofunktiot ja ohjausobjektien ominaisuudet

Harkitse **pienempi** funktio. Jos muuttujan **Tervetuloa** sisältää tekstimerkkijonon **”Hello, World”** , kaava **Lower (Tervetuloa)** palauttaa **”hello, world”** .  Tämä funktio ei, muuta kyseisen muuttujan arvo millään tavalla. **LOWER** on puhdas funktio siten, että se käsittelee vain syöte- ja tuottaa tulosteen. Siinä kaikki; sillä ei ole sivuvaikutuksia. Kaikki funktiot Excelissä ja Useimmat-funktiot powerappsissa ovat täysin Funktiot, jotka mahdollistavat työkirjaan tai sovelluksen lasketaan automaattisesti uudelleen.

PowerApps tarjoaa joukon funktioita, jotka toimivat samalla tavalla taulukoille. Nämä funktiot kestää taulukoita, koska syöte ja Suodata, Lajittele, muuntaa, pienennä ja yhteenvedon koko taulukoiden tiedot. Itse asiassa **pienempi** ja monia muita funktioita, jotka kestää yleensä yhden arvon voit myös ottaa yhden sarakkeen taulukkoa syötteeksi.

* **[Sort](functions/function-sort.md)**, **[Filter](functions/function-filter-lookup.md)** – nämä lajittelevat ja suodattavat tietueita.
* **[FirstN](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)** – nämä palauttavat N-määrän taulukon ensimmäisiä tai viimeisiä tietueita.
* **[Abs](functions/function-numericals.md)**, **[Sqrt](functions/function-numericals.md)**, **[Round](functions/function-round.md)**, **[RoundUp](functions/function-round.md)**, **[RoundDown](functions/function-round.md)** – nämä ovat aritmeettisia toimintoja, joita käytetään kussakin yksisarakkeisen taulukon tietueessa. Tuloksena saadaan yksisarakkeinen tulostaulukko.
* **[Left](functions/function-left-mid-right.md)**, **[Mid](functions/function-left-mid-right.md)**, **[Right](functions/function-left-mid-right.md)**, **[Replace](functions/function-replace-substitute.md)**, **[Substitute](functions/function-replace-substitute.md)**, **[Trim](functions/function-trim.md)**, **[Lower](functions/function-lower-upper-proper.md)**, **[Upper](functions/function-lower-upper-proper.md)**, **[Proper](functions/function-lower-upper-proper.md)** – nämä ovat merkkijonon käsittelytoimintoja, joita käytetään kussakin yksisarakkeisen taulukon tietueessa. Tuloksena saadaan yksisarakkeinen merkkijonotaulukko.
* **[Len](functions/function-len.md)** – tämä palauttaa merkkijonosarakkeeseen yksisarakkeisen taulukon, joka sisältää kunkin merkkijonon pituuden.
* **[Concatenate](functions/function-concatenate.md)** – tätä käytetään merkkijonosarakkeiden yhdistämiseen. Tuloksena saadaan yksisarakkeinen merkkijonotaulukko.
* **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)**, **[RenameColumns](functions/function-table-shaping.md)**, **[ShowColumns](functions/function-table-shaping.md)** – näitä käytetään taulukon sarakkeiden käsittelyyn. Tuloksena saadaan uusi taulukko, jossa on erilaisia sarakkeita.
* **[Distinct](functions/function-distinct.md)** – poistaa tietueiden kaksoiskappaleet.
* **[Shuffle](functions/function-shuffle.md)** – sekoittaa tietueet satunnaiseen järjestykseen.
* **[HashTags](functions/function-hashtags.md)** – tällä etsitään merkkijonoja aihetunnisteen perusteella.
* **[Errors](functions/function-errors.md)** – antaa virhetietoja työskenneltäessä tietolähteen parissa.

Monet näistä funktioista kestää yksisarakkeisen taulukon niiden syötteenä. Jos koko taulukossa on vain yksi sarake, voit määrittää nimen mukaan. Jos taulukossa on useita sarakkeita, voit määrittää yhden nämä sarakkeet käyttämällä *Table.Column* syntaksi. Esimerkiksi **Products.Name** palauttaa vain yhden sarakkeen taulukon **nimi** arvot **tuotteiden** taulukon.

Voit uudelleenmuotoilla taulukon täysin haluamallasi käyttämällä  **[AddColumns](functions/function-table-shaping.md)**,  **[RenameColumns](functions/function-table-shaping.md)**,  **[ ShowColumns](functions/function-table-shaping.md)**, tai **[DropColumns](functions/function-table-shaping.md)** funktio. Nämä funktiot muuttavat uudelleen vain niiden output-, ei lähteen.

Olevien ohjausobjektien ominaisuuksiin voi olla myös taulukot:

* **Kohteet** – koskee valikoimia ja luetteloruutuja yhdistelmäruutu. Tämä ominaisuus määrittää taulukkoa, joka näyttää valikoiman tai luettelo.
* **SelectedItems** -luettelo ja yhdistelmäruutu koskee. Tämä ominaisuus määrittää kohteita, jotka käyttäjä on valinnut, jos taulukko **SelectMultiple** on käytössä.

## <a name="behavioral-formulas"></a>Pohjautuvaa kaavat

Muista funktioista on suunniteltu erityisesti on sivuvaikutuksia ja muokata tietoja. Koska nämä funktiot eivät ole oikeanlainen, sinun täytyy muodostaa niitä huolellisesti ja ne ei voi osallistua lasketaan automaattisesti uudelleen sovelluksessa arvot. Voit käyttää näitä funktioita vain [pohjautuvaa kaavat](working-with-formulas-in-depth.md).

* **[Kerää](functions/function-clear-collect-clearcollect.md)**,  **[Tyhjennä](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)** – Luo kokoelmia, poistaa niitä ja lisää tietoja ne.
* **[Patch](functions/function-patch.md)**  -Muokkaa yhden tai useamman tietueen kenttää.
* **[Update](functions/function-update-updateif.md)**, **[UpdateIf](functions/function-update-updateif.md)** – näillä päivitetään tietueet, jotka vastaavat yhtä tai useampaa määrittämääsi kriteeriä.
* **[Remove](functions/function-remove-removeif.md)**, **[RemoveIf](functions/function-remove-removeif.md)** – näillä poistetaan tietueet, jotka vastaavat yhtä tai useampaa määrittämääsi kriteeriä.

## <a name="record-formulas"></a>Tietueen kaavat

Voit myös luoda kaavan, joka laskee yksittäisen tietueen tiedot, määrittää argumentiksi yksittäisen tietueen ja tarjoaa yksittäisen tietueen palautusarvona. Katsotaan uudestaan edellistä valikoimaesimerkkiä. Käytetään **Gallery1.Selected**-ominaisuutta näyttämään tiedot mistä tahansa tietueesta, jonka käyttäjä valitsee kyseisestä valikoimasta.

1. Lisää [ **painike**](controls/control-button.md), ja määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuuden arvoksi tämä kaava:<br>
    **Collect( SelectedRecord, Gallery1.Selected )**

2. Pidä Alt-näppäintä painettuna ja valitse painike.

3. Valitse **Tiedosto**-valikosta **Kokoelmat.**

    ![](media/working-with-tables/selected-collection.png)

Tämän kaavan palauttama tietue sisältää paitsi valikoimassa valittuna olevan tietueen tiedot, myös valikoiman jokaisen ohjausobjektin. Tietue sisältää esimerkiksi sekä **SampleText**-sarakkeen, joka vastaa alkuperäisen taulukon **SampleText**-saraketta, että **Subtitle1** sarakkeen, joka edustaa selitettä ja näyttää kyseisen sarakkeen tiedot. Valitse taulukkokuvake **Subtitle1**-sarakkeessa, niin voit porautua kyseisiin tietoihin.

> [!NOTE]
> **Subtitle1**-sarakkeen nimi voi olla **Subtitle2** tai vastaava, jos olet lisännyt elementtejä, joita ei ole määritetty tässä ohjeaiheessa.

Nyt kun sinulla on tietue valittuna, voit poistaa siitä yksittäisiä kenttiä käyttämällä **.** -operaattoria.

1. Lisää **[Selite](controls/control-text-box.md)**-ohjausobjekti ja siirrä se sitten valikoiman ja painikkeen alapuolelle.

1. Määritä selitteen **[Teksti](controls/properties-core.md)**-ominaisuuteen tämä lauseke:<br>
    **"Selected: " & Gallery1.Selected.SampleHeading**

    ![](media/working-with-tables/gallery-selected.png)

Olet määrittänyt **Selected**-ominaisuuden, joka on tietue, ja poiminut siitä **SampleHeading**-ominaisuuden.

Voit myös käyttää tietueita yleiskäyttöisenä säilönä valikoimaan liittyville nimetyille arvoille.

* Jos luot kaavan funktioiden **[UpdateContext](functions/function-updatecontext.md)** ja **[Navigate](functions/function-navigate.md)** ympärille, voit käyttää tietuetta keräämään [kontekstimuuttujat](working-with-variables.md#use-a-context-variable), jotka haluat päivittää.
* Käytä **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjektin **[Päivitykset](controls/control-form-detail.md)**-ominaisuutta keräämään muutokset, jotka käyttäjä on tehnyt lomakkeeseen.
* Voit käyttää **[Patch](functions/function-patch.md)**-funktiota tietolähteen päivittämiseen, mutta myös tietueiden yhdistämiseen.

Näissä tapauksissa tietue ei koskaan ollut taulukon osa.

## <a name="record-functions-and-control-properties"></a>Tietuefunktiot ja ohjausobjektien ominaisuudet
Funktiot, jotka palauttavat tietueita:

* **[FirstN](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)** – Palauttaa taulukon ensimmäisen tai viimeisen tietueen/tietueet.
* **[Lookup](functions/function-filter-lookup.md)** – Palauttaa ensimmäisen tietueen taulukosta, joka vastaa yhtä tai useampaa kriteeriä.
* **[Patch](functions/function-patch.md)** – Päivittää tietolähteen tai yhdistää tietueita.
* **[Defaults](functions/function-defaults.md)** – Palauttaa tietolähteelle oletusarvot.

Ominaisuudet, jotka palauttavat tietueita:

* **Valittuna** – Koskee valikoimia ja luetteloruutuja. Palauttaa valittuna olevan tietueen.
* **Päivitykset** – Koskee valikoimia.  Tuo yhteen kaikki muutokset, jotka käyttäjä tekee tietolomakkeeseen.
* **[Päivitä](functions/function-update-updateif.md)** – Koskee syöteohjausobjekteja, kuten tekstisyötteen ohjausobjekteja ja liukusäätimiä. Määrittää valikoimalle yksittäiset ominaisuudet, joiden mukaan tiedot kootaan yhteen.

## <a name="record-scope"></a>Tietueen vaikutusalue

Jotkin toiminnot toimivat arvioimalla kaavan kaikissa taulukon tietueissa erikseen. Kaavan tulosta käytetään eri tavoin:

* **Filter**, **Lookup** – määrittää, sisällytetäänkö tietue tulokseen.
* **Sort** – antaa arvon, jonka mukaan tietueita lajitellaan.
* **Concat** – määrittää merkkijonot, jotka yhdistetään.
* **ForAll** – voi palauttaa minkä tahansa arvon, ja sillä voi olla jokin sivuvaikutus.
* **Distinct** – palauttaa arvon, jolla tunnistetaan tietueiden kaksoiskappaleet.
* **AddColumns** – antaa lisätyn kentän arvon.
* **Average**, **Max**, **Min**, **Sum**, **StdevP**, **VarP** – nämä määritteet antavat koostearvon.

Näiden kaavojen sisällä voit viitata käsiteltävänä olevan tietueen kenttiin. Kaikki nämä funktiot luovat ”tietueen vaikutusalueen”, jossa kaava lasketaan ja tietueen kentät ovat käytettävissä ylimmän tason tunnisteina. Voit myös viitata ohjausobjektin ominaisuuksiin ja muihin arvoihin, jotka sijaitsevat sovelluksesi eri osissa.

Katsotaan esimerkiksi **Tuotteet**-taulukkoa:

![](media/working-with-tables/requested.png)

Sovelluksesi tässä esimerkissä taulukon luomiseen Lisää painike, määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava ja valitse sitten painike (napsauttamalla sen samalla, kun pitämällä Alt-näppäintä PowerApps Studio):

```powerapps-dot
Set( Products,
    Table(
        { Product: "Widget",    'Quantity Requested': 6,  'Quantity Available': 3 },
        { Product: "Gadget",    'Quantity Requested': 10, 'Quantity Available': 20 },
        { Product: "Gizmo",     'Quantity Requested': 4,  'Quantity Available': 11 },
        { Product: "Apparatus", 'Quantity Requested': 7,  'Quantity Available': 6 }
    )
)
```

Selvitä, onko mitään näitä tuotteita oli pyydetty enemmän kuin on saatavilla:

`Filter( Products, 'Quantity Requested' > 'Quantity Available' )`

**Filter**-kaavan ensimmäinen argumentti on käsiteltävänä oleva tietuetaulukko, ja toinen argumentti on kaava.  **Filter**-kaava luo tietueen vaikutusalueen, jonka perusteella määritetään tämä kaava, jossa kunkin tietueen kentät ovat käytettävissä. Tässä tapauksessa näitä kenttiä ovat **Tuote**, **Pyydetty määrä** ja **Käytettävissä oleva määrä**.  Vertailun tulos määrittää, sisällytetäänkö kukin tietue funktion tulokseen:

![](media/working-with-tables/needed.png)

Laajennetaan esimerkkiä laskemalla, kuinka paljon kutakin tuotetta on tilattava:

```powerapps-dot
AddColumns( 
    Filter( Products, 'Quantity Requested' > 'Quantity Available' ), 
    "Quantity To Order", 'Quantity Requested' - 'Quantity Available'
)
```

Tässä lisäämme lasketun sarakkeen tulokseen. **AddColumns**-ominaisuudella on oma tietuealueensa, jonka mukaan se laskee pyydettyjen ja saatavana olevien tuotteiden välisen eron.

![](media/working-with-tables/toorder.png)

Lopuksi voimme pienentää Tulostaulukkoa vain sarakkeita, jotka haluamme:

```powerapps-dot
ShowColumns(
    AddColumns(
        Filter( Products, 'Quantity Requested' > 'Quantity Available' ),
        "Quantity To Order", 'Quantity Requested' - 'Quantity Available'
    ),
    "Product",
    "Quantity To Order"
)
```

![](media/working-with-tables/toorderonly.png)

Huomaa, että käytämme edellä toisinaan lainausmerkkejä (") ja toisinaan heittomerkkejä (').  Heittomerkkejä on käytettävä, kun viitataan objektin arvoon, kuten kenttään tai taulukkoon, jossa objektin nimessä on välilyönti.  Lainausmerkkejä käytetään, kun emme viittaa objektin arvoon, vaan sen sijaan keskustelemme siitä. Tämä koskee erityisesti tilanteita, joissa objektia ei vielä ole, kuten **AddColumns**-määritteen yhteydessä.

## <a name="disambiguation"></a>Selvitys

Tietuealueen kanssa lisättyjen kenttien nimet ohittavat samat nimet, jotka ovat peräisin muualta sovelluksesta.  Kun näin tapahtuu, voit edelleen käyttää arvoja tietuealueen ulkopuolelta käyttämällä [ **@** selvitysoperaattoria](functions/operators.md):

* Voit käyttää sisäkkäisten tietuealueiden arvoja käyttämällä operaattoria **@** siten, että käsiteltävänä olevan taulukon nimi esitetään tämän mallin mukaisesti:<br>_Table_ **[@** _FieldName_ **]**
* Voit käyttää yleisiä arvoja, kuten tietolähteitä, kokoelmia ja kontekstimuuttujia, esittämällä ne mallin **[@** _ObjectName_ **]** mukaisesti (ilman taulukon määritystä).

Jos käsiteltävä taulukko on lauseke, kuten **Filter(** _Table_ **,** ... **)** , selvitysoperaattoria ei voi käyttää.  Vain sisin tietuealue voi käyttää kenttiä tästä taulukkolausekkeesta ilman selvitysoperaattoria.

Kuvitellaan esimerkiksi kokoelma **X**:

![](media/working-with-tables/X.png)

Voit luoda tämän kokoelman käyttämällä kaavaa **ClearCollect( X, \[1, 2\] )** .

Ja toinen kokoelma **Y**:

![](media/working-with-tables/Y.png)

Voit luoda tämän kokoelman käyttämällä kaavaa **ClearCollect( Y, ["A", "B"] )** .

Määritä lisäksi kontekstimuuttuja, jonka nimi **arvo** käyttämällä tätä kaavaa: **UpdateContext( {Value: "!"} )**

Kootaan nyt kaikki tiedot yhteen. Tässä kontekstissa seuraava kaava:

```powerapps-dot
Ungroup(
    ForAll( X,
        ForAll( Y,
            Y[@Value] & Text( X[@Value] ) & [@Value]
        )
    ),
    "Value"
)
```

tuottaa tämän taulukon:

![](media/working-with-tables/XY.png)

Mitä tapahtui?  Uloin **ForAll**-funktio määrittää tietuealueen **X**:lle ja antaa käyttöoikeuden kunkin tietueen **Arvo**-kenttään, kun niitä käsitellään.  Se voidaan ottaa käyttöön sanalla **Arvo** tai tekstillä **X[@Value]** .

Sisin **ForAll**-funktio määrittää toisen tietuealueen **Y**:lle.  Koska myös tässä taulukossa on määritettynä **Arvo**-kenttä, **Arvo**-kentän käyttäminen tässä viittaa **Y**:n tietueessa olevaan kenttään eikä enää **X**:n tietueessa olevaan kenttään.  Voidaksemme käyttää **X**:n **Arvo**-kenttää meidän on käytettävä pidempää versiota ja selvitysoperaattoria.

Koska **Y** on alueen sisin tietuealue, tämän taulukon tietueiden käyttämiseen ei tarvita selvitystä. Näin ollen voimme käyttää tätä kaavaa ja samaa tulosta:

```powerapps-dot
Ungroup(
    ForAll( X,
        ForAll( Y,
            Value & Text( X[@Value] ) & [@Value]
        )
    ),
    "Value"
)
```

Kaikki **ForAll**-tietuealueet ohittavat yleisen vaikutusalueen. **Arvo** määritettiin kontekstimuuttuja ei ole käytettävissä nimen perusteella ilman selvitysoperaattoria. Voit käyttää tätä arvoa **[@Value]** .

**Ungroup** tasoittaa tuloksen, koska sisäkkäin **ForAll** Funktiot johtaa sisäkkäisen tulostaulukon.

## <a name="single-column-tables"></a>Yhden sarakkeen taulukoita

Käsiteltävä yksisarakkeinen taulukosta, käytä **ShowColumns** toimi tämän esimerkin mukaisesti:

```powerapps-dot
ShowColumns( Products, "Product" )
```

Tämä kaava tuottaa yhden sarakkeen tämän taulukon:

![](media/working-with-tables/single-column.png)

Määritä lyhyempi vaihtoehtoinen *Table.Column*, joka poimii vain yhden sarakkeen taulukko *sarakkeen* - *taulukon*. Esimerkiksi Tämä kaava tuottaa täsmälleen saman tuloksen kuin käyttämällä **ShowColumns**.

```powerapps-dot
Products.Product
```

## <a name="inline-records"></a>Sisäinen tietueet

Tietueita ilmaistaan aaltosulkeilla, jotka sisältävät nimetyt kenttäarvot.  Voit esimerkiksi ilmaista tämän ohjeaiheen alussa olevan taulukon ensimmäisen tietueen käyttämällä seuraavaa kaavaa:

`{ Name: "Chocolate", Price: 3.95, 'Quantity on Hand': 12, 'Quantity on Order': 10 }`

Voit myös upottaa kaavoja muihin kaavoihin tämän esimerkin mukaan:

`{ Name: First(Products).Name, Price: First(Products).Price * 1.095 }`

Voit sijoittaa tietueita sisäkkäin käyttämällä aaltosulkeita sisäkkäin tämän esimerkin mukaisesti:

`{ 'Quantity': { 'OnHand': ThisItem.QuantOnHand, 'OnOrder': ThisItem.QuantOnOrder } }`

Lisää heittomerkkien sisään jokainen sarakkeen nimi, joka sisältää erikoismerkin, kuten välilyönnin tai kaksoispisteen.  Kun haluat käyttää heittomerkkiä sarakkeen nimen sisällä, tuplaa se.

Huomaa, että **Hinta**-sarakkeessa oleva arvo ei sisällä valuuttasymbolia, kuten dollarimerkkiä. Kyseinen muotoilu otetaan käyttöön, kun arvo näytetään.  

## <a name="inline-tables"></a>Inline-taulukot
Voit luoda taulukon käyttämällä **[Table](functions/function-table.md)**-funktiota ja tietuejoukkoa. Voit ilmaista tämän ohjeaiheen alussa olevan taulukon käyttämällä seuraavaa kaavaa:

```powerapps-dot
Table( 
    { Name: "Chocolate", Price: 3.95, 'Quantity on Hand': 12, 'Quantity on Order': 10 },
    { Name: "Bread", Price: 4.95, 'Quantity on Hand': 34, 'Quantity on Order': 0 },
    { Name: "Water", Price: 4.95, 'Quantity on Hand': 10, 'Quantity on Order': 0 } 
)
```

Voit myös asettaa taulukkoja sisäkkäin:

```powerapps-dot
Table( 
    { Name: "Chocolate", 
      'Quantity History': Table( { Quarter: "Q1", OnHand: 10, OnOrder: 10 },
                                 { Quarter: "Q2", OnHand: 18, OnOrder: 0 } ) 
    }
)
```

## <a name="inline-value-tables"></a>Sisäinen arvotaulukot
Voit luoda yksisarakkeisia taulukkoja määrittämällä arvot hakasulkeisissa. Tuloksena saatavassa taulukossa on yksittäinen sarake, jonka nimi on **Arvo**.

Esimerkiksi `[ 1, 2, 3, 4 ]` vastaa `Table( { Value: 1 }, { Value: 2 }, { Value: 3 }, { Value: 4 } )` ja palauttaa tämän taulukon:

![](media/working-with-tables/inline-table.png)


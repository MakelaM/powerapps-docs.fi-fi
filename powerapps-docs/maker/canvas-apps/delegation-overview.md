---
title: Tutustu delegointiin | Microsoft Docs
description: Delegoinnin avulla voidaan käsitellä suuria tietomääriä tehokkaasti.
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
ms.date: 03/27/2018
ms.author: gregli
ms.openlocfilehash: 98cf32e1b379812e1d3175e6403b7c6fd7fb794b
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/28/2018
---
# <a name="understand-delegation"></a>Tutustu delegointiin
PowerApps sisältää tehokkaita funktioita taulukkojen tietojen suodattamiseen, lajittelemiseen ja muotoilemiseen. Joitakin näitä funktioita ovat **[Suodatin](functions/function-filter-lookup.md)**, **[Lajittele](functions/function-sort.md)** ja **[AddColumns](functions/function-table-shaping.md)**.  Näillä funktioilla voit antaa käyttäjille keskitetyn käyttöoikeuden heidän tarvitsemiinsa tietoihin.  Tietokannat tunteville käyttäjille näiden funktioiden käyttäminen vastaa tietokantakyselyn kirjoittamista.  

Keskeistä tehokkaiden sovellusten kehittämisessä on sen tietomäärän pienentäminen, jota joudutaan siirtämään laitteeseesi.  Ehkä vain muutama kourallinen tietueita miljoonien joukosta tarvitaan, tai yksittäinen koostearvo voi edustaa tuhansia tietueita.  Tai ehkä vain ensimmäinen tietuejoukko voidaan hakea ja muut tuoda, kun käyttäjä ilmoittaa tarvitsevansa lisää.  Keskittyneisyys voi huomattavasti pienentää sovelluksen tarvitsemaa käsittelytehoa, muistia ja verkon kaistanleveyttä. Tästä on tuloksena nopeammat reaktioajat käyttäjillesi jopa matkapuhelinverkon kautta liitetyissä puhelimissa.  

*Delegoinnissa* yhdistyvät PowerApps-kaavojen ilmaisukyky ja tarve rajoittaa verkon kautta siirrettäviä tietoja.  Lyhyesti sanottuna se tarkoittaa sitä, että PowerApps delegoi tietojen käsittelyn tietolähteeseen sen sijaan, että tiedot siirretään sovellukseen käsiteltäväksi paikallisesti.  

Tässä asia monimutkaistuu, ja juuri tästä syystä tämä artikkeli on olemassa, sillä kaikkea, mitä voidaan ilmaista PowerApps-kaavassa, ei voida delegoida jokaiseen tietolähteeseen.  PowerApps-kieli imitoi Excelin kaavakieltä, johon sisältyy täydellinen ja välitön käyttöoikeus muistissa olevaan täydelliseen työkirjaan monine erilaisine numeron- ja tekstinkäsittelyfunktioineen.  Näin ollen PowerApps-kieli on monin verroin monipuolisempi kuin mitä useimmat tietolähteet voivat tukea, ja siihen kuuluvat tehokkaat tietokantamoduulit, kuten SQL Server.

**Suurien tietomäärien käyttäminen edellyttää delegoitavien tietolähteiden ja kaavojen käyttöä.**  Se on ainoa tapa, jolla sovellus voidaan pitää hyvin toiminnassa ja varmistaa, että käyttäjät voivat käyttää kaikkia tarvitsemansa tietoja. Ota huomioon [sinisellä pisteellä merkityt ehdotukset](delegation-overview.md#blue-dot-suggestions), jotka ilmoittavat paikat, joissa delegointia ei voi tehdä.  Jos käsittelet pieniä tietojoukkoja (alle 500 tietuetta), voit käyttää mitä tahansa tietolähdettä ja kaavaa, sillä käsittely voidaan tehdä paikallisesti, jos kaavaa ei voi delegoida. 

## <a name="delegable-data-sources"></a>Delegoitavat tietolähteet
Katso [delegointiluettelosta](delegation-list.md) täydellistä luetteloa tietolähteistä, jotka tukevat delegointia ja sen laajuutta.

Lisäämme jatkuvasti delegointitukea olemassa oleviin tietolähteisiin ja lisäämme tietolähteitä.

Tuodut Excel-työkirjat (lisää staattista tietoa sovellukseen -tietolähteellä), kokoelmat ja taulukot, jotka on tallennettu kontekstimuuttujiin, eivät edellytä delegointia. Kaikki nämä tiedot ovat jo muistissa ja koko PowerApps-kieltä voidaan soveltaa.

## <a name="delegable-functions"></a>Delegoitavat funktiot
Seuraava vaihe on vain delegoitavien kaavojen käyttäminen. Tässä ovat kaavan osat, jotka voidaan delegoida.  Jokainen tietolähde on kuitenkin erilainen, eivätkä ne kaikki tue kaikkia näitä elementtejä. Tarkista sinisellä pisteellä merkityt ehdotukset kaavassasi.

Nämä luettelot muuttuvat ajan myötä. Pyrimme tukemaan delegoinnilla useampia funktioita ja operaattoreita.

### <a name="filter-functions"></a>Suodatustoiminnot
**[Filter](functions/function-filter-lookup.md)**, **[Search](functions/function-filter-lookup.md)** ja **[LookUp](functions/function-filter-lookup.md)** voidaan delegoida.  

**Filter**- ja **LookUp**-funktioissa voidaan käyttää seuraavia termejä valitsemaan tarvittavia tietueita taulukon sarakkeilla:

* **[And](functions/function-logicals.md)** (mukaan lukien **[&&](functions/operators.md)**), **[Or](functions/function-logicals.md)** (mukaan lukien **[||](functions/operators.md)**), **[Not](functions/function-logicals.md)** (mukaan lukien **[!](functions/operators.md)**)
* **[In](functions/operators.md)**
* **[=](functions/operators.md)**, **[<>](functions/operators.md)**, **[>=](functions/operators.md)**, **[<=](functions/operators.md)**, **[>](functions/operators.md)**, **[<](functions/operators.md)**
* **[+](functions/operators.md)**, **[-](functions/operators.md)**
* **[TrimEnds](functions/function-trim.md)**
* **[IsBlank](functions/function-isblank-isempty.md)**
* **[StartsWith](functions/function-startswith.md)**
* Vakioarvot, jotka ovat samat kaikissa tietueissa, kuten ohjausobjektien ominaisuudet ja [yleiset ja kontekstimuuttujat](working-with-variables.md).

Kaavan osia, jotka antavat tulokseksi vakioarvon kaikille tietueille, voidaan myös käyttää.  Esimerkiksi **Left( Language(), 2 )** ei ole riippuvainen tietueen mistään sarakkeista ja näin ollen palauttaa saman arvon kaikille tietueille.  Käytännössä se on vakio.  Kontekstimuuttujien, kokoelmien ja signaalien käyttö ei ehkä ole vakiomallista, mikä estää **Filter**- ja **LookUp**-funktioiden delegoimisen.  

Joitakin huomionarvoisia kohteita puuttuu yllä olevasta luettelosta:

* **[If](functions/function-if.md)**
* **[*](functions/operators.md)**, **[/](functions/operators.md)**, **[Mod](functions/function-mod.md)**
* **[Concatenate](functions/function-concatenate.md)** (mukaan lukien **[&](functions/operators.md)**)
* **[ExactIn](functions/operators.md)**
* Merkkijonon käsittelyfunktiot: **[Lower](functions/function-lower-upper-proper.md)**, **[Upper](functions/function-lower-upper-proper.md)**, **[Left](functions/function-left-mid-right.md)**, **[Mid](functions/function-left-mid-right.md)**, **[Len](functions/function-left-mid-right.md)**, ...
* Signaalit: **[Location](functions/signals.md)**, **[Acceleration](functions/signals.md)**, **[Compass](functions/signals.md)**, ...
* Vaihtuvat: **[Now](functions/function-now-today-istoday.md)**, **[Today](functions/function-now-today-istoday.md)**, **[Rand](functions/function-rand.md)**, ...
* [Kokoelmat](working-with-variables.md)

### <a name="sorting-functions"></a>Funktioiden lajittelu
**[Sort](functions/function-sort.md)** ja **[SortByColumns](functions/function-sort.md)** voidaan delegoida.  

**Sort**-funktiossa kaava voi olla vain yhden sarakkeen nimi eikä voi sisältää muita operaattoreita tai funktioita.

### <a name="aggregate-functions"></a>Koostefunktiot
**[Sum](functions/function-aggregates.md)**, **[Average](functions/function-aggregates.md)**, **[Min](functions/function-aggregates.md)** ja **[Max](functions/function-aggregates.md)** voidaan delegoida.  Vain rajoitettu tietolähteiden määrä tukee tätä delegointia tällä hetkellä. Katso lisätietoja [delegointiluettelosta](delegation-list.md).

Laskentafunktioita, kuten **[CountRows](functions/function-table-counts.md)**, **[CountA](functions/function-table-counts.md)** and **[Count](functions/function-table-counts.md)**, ei voi delegoida.

Muita koostefunktioita, kuten **[StdevP](functions/function-aggregates.md)** ja **[VarP](functions/function-aggregates.md)**, ei voi delegoida.

## <a name="non-delegable-functions"></a>Funktiot, joita ei voi delegoida
Kaikki muut toiminnot eivät tue delegointia, mukaan lukien nämä huomionarvoiset funktiot:

* Taulukon muovaaminen: **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)**, **[ShowColumns](functions/function-table-shaping.md)**, ...
* **[First](functions/function-first-last.md)**, **[FirstN](functions/function-first-last.md)**, **[Last](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)**
* **[Concat](functions/function-concatenate.md)**
* **[Collect](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)**
* **[CountIf](functions/function-table-counts.md)**, **[RemoveIf](functions/function-remove-removeif.md)**, **[UpdateIf](functions/function-update-updateif.md)**
* **[GroupBy](functions/function-groupby.md)**, **[Ungroup](functions/function-groupby.md)**

Yleinen malli on **AddColumns**- ja **LookUp**-funktioiden käyttäminen tietojen yhdistämiseen yhdestä taulukosta toiseen. Tätä kutsutaan yleisesti tietokantojen yhdistämiseksi.  Esimerkki:

**AddColumns( Products, "Supplier Name", LookUp( Suppliers, Suppliers.ID = Product.SupplierID ).Name )**

Vaikka **Products** ja **Suppliers** ovat ehkä delegoitavia tietolähteitä ja **LookUp** on delegoitava funktio, **AddColumns**-funktio ei ole delegoitava.  Koko kaavan tulos rajoittuu **Products**-tietolähteen ensimmäiseen osaan.  

Koska **LookUp** ja sen tietolähde ovat delegoitavia, **Suppliers**-vastaavuus on löydettävissä mistä tahansa tietolähteessä, vaikka se olisi suuri.  Mahdollinen huono puoli on se, että **LookUp** lähettää erilliset kutsut tietolähteeseen kunkin **Products**-tietolähteen ensimmäisille tietueille, mikä aiheuttaa paljon liikennettä verkossa.  Jos **Suppliers** on tarpeeksi pieni eikä muutu usein, voit lisätä tietolähteen välimuistiin sovelluksessa **Collect**-kutsulla, kun sovellus käynnistyy (käyttämällä [**OnVisible**](controls/control-screen.md)-ominaisuutta aloitusnäytössä) ja tehdä sille **LookUp**-haun sen sijaan.  

## <a name="non-delegable-limits"></a>Rajoitukset, joita ei voi delegoida
Kaavat, jotka ei voi delegoida, käsitellään paikallisesti.  Tämä sallii PowerApps-kaavakielen käytön koko laajuudessaan.  Tällä on kuitenkin hintansa: kaikki tiedot on ensin tuotava laitteeseen, mikä saattaa merkitä suurten tietomäärin noutamista verkosta.  Tähän voi kulua aikaa, mikä antaa sovelluksesta hitaan tai jumittuneen vaikutelman.

Voit välttää tämän, sillä PowerApps rajoittaa paikallisesti käsiteltävien tietojen määrää ja sallii oletusarvoisesti vain 500 tietuetta.  Valitsimme tämän luvun, jotta sinulla olisi yhä täydet käyttöoikeudet pieniin tietojoukkoihin, ja voit tarkentaa suurien tietojoukkojen käyttöä näkemällä osittaiset tulokset.

Tätä ominaisuutta on luonnollisesti käytettävä varoen, sillä se saattaa hämmentää käyttäjiä.  Ajatellaan esimerkiksi **Filter**-funktiota, jolla on valintakaava, jota ei voi delegoida, yli miljoonan tietueen tietolähteessä.  Koska suodatus tehdään paikallisesti, vain ensimmäiset 500 tietuetta miljoonasta tarkistetaan.  Jos haluttu tietue on tietue 501 tai 500 001, **Filter** ei huomioi tai palauta sitä.

Tämä voi aiheuttaa sekaannusta myös koostefunktioiden yhteydessä.  Käytetään **Average**-funktiota saman miljoonan tietueen tietolähteen sarakkeessa.  Koska **Average** ei vielä ole delegoitavissa, vain ensimmäisten 500 tietueen keskiarvo lasketaan.  Tässä on oltava tarkkana, ettei sovelluksen käyttäjä vahingossa tulkitse osittaista vastausta täydelliseksi vastaukseksi.

## <a name="changing-the-limit"></a>Rajan muuttaminen

500 on tietueiden oletusarvoinen lukumäärä.  Tätä lukua voidaan muuttaa siirtymällä Tiedosto-välilehteen, valitsemalla vasemmanpuoleisesta siirtymisruudusta Sovelluksen asetukset ja katsomalla kohtaa Kokeelliset ominaisuudet.  Täällä on Tietojen rivirajoitus kyselyille, joita ei voi delegoida -asetus, jota voi muuttaa arvosta 1 arvoon 2000.  Tämä asetus vaikuttaa koko sovellukseen.

Joissakin tapauksissa tiedät, että 2000 (tai 1000 tai 1500) on riittävä tilanteen tarpeisiin.  Voit varoen suurentaa tämän asetuksen vastaamaan tilannettasi.  Ota huomioon, että kun suurennat tätä lukua, sovelluksesi suorituskyky voi heikentyä erityisesti leveissä taulukoissa, joissa on paljon sarakkeita.  Paras tapa on silti delegoida aina, kun mahdollista.

Jotta sovellus voi skaalautua suuriin tietomääriin, pienennä tämä asetus arvoon 1.  Kaikki, mitä ei voi delegoida, palauttaa nyt vain yhden tietueen, joka on helppo tunnistaa sovellusta testattaessa.  Tämä voi auttaa estämään yllätyksiä yritettäessä ottaa soveltuvuusselvityssovellusta käyttöön.

## <a name="blue-dot-suggestions"></a>Sinisellä pisteellä merkityt ehdotukset
Muokkausominaisuus tarjoaa sinisillä pisteillä merkityillä ehdotuksilla helpon tavan tietää, mitä delegoidaan ja mitä ei, kun kaavassa on jotakin, mitä ei voi delegoida.

Siniset pisteet näytetään vain kaavoissa, jotka toimivat delegoitavissa tietolähteissä.  Jos et näe sinistä pistettä ja uskot, että kaavaa ei ole delegoitu oikein, vertaa tietolähdetyyppiä edellä olevaan <a href="#delegable-data-sources">delegoitavien tietolähteiden</a> luetteloon.

## <a name="examples"></a>Esimerkkejä
Tässä esimerkissä käytämme SQL Server -taulukkoa, joka sisältää tuotteita, tässä tapauksessa hedelmien nimiä **[dbo].[Products]**.  Uudessa näytössä PowerApps voi luoda kolmen näytön perussovelluksen yhdistettynä tähän tietolähteeseen:

![Kolmen näytön sovellus](./media/delegation-overview/products-afd.png)

Huomaa kaava valikoiman **Kohteet**-ominaisuudelle.  Se käyttää **SortByColumns**- ja **Search**-funktioita, jotka molemmat voidaan delegoida.

Kirjoitetaan **”Apple”** haun tekstisyötteen ohjausobjektiin.  Jos olet tarkkaavainen, näet liikkuvia pisteitä näytön yläosassa hetken ajan, kun uuden haun uutta tietoa käsitellään.  Liikkuvat pisteet ilmaisevat kommunikoinnin SQL Serverin kanssa:

![Haun tekstisyötteen ohjausobjekti](./media/delegation-overview/products-apple.png)

Koska tämä on kaikki delegoitavissa, vaikka **[dbo].[Products]**-taulukko sisältäisi miljoonia tietueita, löydämme ne kaikki käymällä sivuja läpi valikoimassa käyttäjän selatessa tuloksia.

Huomioi, että näemme osuman sekä termille ”Apple” että termille ”Pineapple”.  **Search**-funktio löytää hakutermin tekstisarakkeen mistä tahansa kohdasta.  Jos kuitenkin haluamme löytää esimerkiksi hakutermin vain hedelmän nimen alussa,  voimme käyttää toista delegoitavaa funktiota **Filter** ja monimutkaisempaa hakutermiä (yksinkertaisuuden vuoksi poistamme **SortByColumns**-kutsun):

![Remove SortByColumns -kutsu](./media/delegation-overview/products-apple-bluedot.png)

Tämä näyttää toimivan: vain **”Apples”** näkyy nyt oikein ja **”Pineapple”** ei.  Valikoiman vieressä näkyy kuitenkin sininen piste, ja osa kaavasta on alleviivattu sinisellä aaltoviivalla.  Sininen piste näkyy jopa näytön pikkukuvassa.  Jos pidämme kohdistinta valikoiman vieressä olevan sinisen pisteen päällä, seuraava teksti tulee näkyviin:

![Kohdistin sinisen pisteen päällä](./media/delegation-overview/products-apple-bluepopup.png)

Vaikka käytämme delegoitavaa **Filter**-funktiota SQL Serverin kanssa, joka on delegoitava tietolähde, funktiossa **Filter** käyttämämme kaava ei ole delegoitava.  Funktioita **Mid** ja **Len** ei voi delegoida mihinkään tietolähteeseen.

Mutta se toimi, eikö toiminutkin?  Tavallaan.  Tästä syystä näemme sinisen pisteen keltaisen vaarakuvakkeen ja punaisen aaltoviivavirheen sijasta.  Jos **[dbo].[Products]**-taulukko sisältää alle 500 tietuetta, sitten tämä toimi täydellisesti.   Kaikki tietueet tuotiin laitteeseen ja funktiota **Filter** sovellettiin paikallisesti.  

Jos sen sijaan tämä taulukko sisältää enemmän kuin 500 tietuetta, vain ne hedelmät *taulukon ensimmäisten 500 tietueen joukossa*, jotka alkavat sanalla **”Apple”**, näytetään valikoimassa.  Jos **”Apple, Fuji”** näkyy nimessä tietueessa 501 tai 500 001, sitä ei löydetä.

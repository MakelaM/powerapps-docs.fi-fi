---
title: Tutustu delegointiin pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Delegoinnin avulla voidaan käsitellä suuria tietojoukkoja tehokkaasti pohjaan perustuvassa sovelluksessa.
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/05/2018
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 61a7e67b7914e5f844397389833f830244d5af28
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "63318119"
ms.PowerAppsDecimalTransform: true
---
# <a name="understand-delegation-in-a-canvas-app"></a>Tutustu delegointiin pohjaan perustuvassa sovelluksessa
PowerApps sisältää tehokkaita toimintoja, joilla suodatusta, lajittelemiseen ja muotoilemiseen taulukoiden pohjaan perustuvan sovelluksen tiedot: **[Suodattimen](functions/function-filter-lookup.md)**,  **[Lajittele](functions/function-sort.md)**, ja **[AddColumns](functions/function-table-shaping.md)** joitakin funktioita. Näillä funktioilla voit antaa käyttäjille keskitetyn käyttöoikeuden heidän tarvitsemiinsa tietoihin. Tietokannat tunteville käyttäjille näiden funktioiden käyttäminen vastaa tietokantakyselyn kirjoittamista.

Keskeistä tehokkaiden sovellusten kehittämisessä on sen tietomäärän pienentäminen, joka on siirrettävä laitteeseesi. Ehkä tarvitset vain muutaman kourallisen tietueita miljoonien joukosta, ja yksittäinen koostearvo voi edustaa tuhansia tietueita. Tai ehkä vain ensimmäinen tietuejoukko voidaan hakea ja muut tuoda, kun käyttäjä ilmoittaa tarvitsevansa lisää. Keskittyneisyys voi pienentää huomattavasti sovelluksen tarvitsemaa käsittelytehoa, muistia ja verkon kaistanleveyttä. Tämän ansiosta käyttäjiesi kokemat vasteajat lyhenevät jopa matkapuhelinverkon kautta yhdistetyissä puhelimissa. 

*Delegoinnissa* yhdistyvät PowerApps-kaavojen ilmaisukyky ja tarve rajoittaa verkon kautta siirrettäviä tietoja. Lyhyesti sanottuna PowerApps delegoi tietojen käsittelyn tietolähteeseen sen sijaan, että tiedot siirrettäisiin sovellukseen käsiteltäväksi paikallisesti.

Tässä asia monimutkaistuu, ja juuri tästä syystä tämä artikkeli on olemassa: kaikkea, mitä voidaan ilmaista PowerApps-kaavassa, ei voida delegoida jokaiseen tietolähteeseen. PowerApps-kieli imitoi Excelin kaavakieltä, johon sisältyy täydellinen ja välitön käyttöoikeus muistissa olevaan täydelliseen työkirjaan monine erilaisine numeron- ja tekstinkäsittelyfunktioineen. Näin ollen PowerApps-kieli on monin verroin monipuolisempi kuin mitä useimmat tietolähteet voivat tukea, ja siihen kuuluvat tehokkaat tietokantamoduulit, kuten SQL Server.

**Suurien tietomäärien käyttäminen edellyttää delegoitavien tietolähteiden ja kaavojen käyttöä.** Se on ainoa tapa, jolla sovellus voidaan pitää hyvin toiminnassa ja varmistaa, että käyttäjät voivat käyttää kaikkia tarvitsemiaan tietoja. Kiinnitä huomiota delegointivaroituksiin. Ne ilmaisevat paikat, joissa delegointi ei ole mahdollista. Jos käsittelet pieniä tietojoukkoja (alle 500 tietuetta), voit käyttää mitä tahansa tietolähdettä ja kaavaa, sillä sovellus voi käsitellä tietoja paikallisesti, jos kaavaa ei voi delegoida. 

> [!NOTE]
> Delegointivaroituksia kutsuttiin PowerAppsissa aiemmin sinisellä pisteellä merkityiksi ehdotuksiksi, mutta delegointiehdotukset on sittemmin luokiteltu uudelleen varoituksiksi. Jos tietolähteessä on yli 500 tietuetta eikä funktiota voida delegoida, PowerApps ei ehkä voi noutaa kaikkia tietoja ja sovelluksesi tulokset voivat olla vääriä. Delegointivaroitukset helpottavat sovelluksesi hallintaa niin, että sen tulokset ovat oikeat.

## <a name="delegable-data-sources"></a>Delegoitavat tietolähteet
Delegointia tuetaan tiettyjen vain Taulukkomuotoisissa tietolähteissä. Jos tietolähde tukee delegointia, sen [connector ohjeet](https://docs.microsoft.com/connectors/) kuvataan tukevat. Taulukkomuotoiset tietolähteet ovat Suosituimmat, ja ne delegointia:

- [Common Data Service](https://docs.microsoft.com/connectors/commondataservice/) 
- [SharePoint](https://docs.microsoft.com/connectors/sharepointonline/) 
- [SQL Server](https://docs.microsoft.com/connectors/sql/) 

Tuotu Excel-työkirjojen (käyttämällä **Lisää staattisia tietoja sovellukseesi** tietolähde), kokoelmat ja taulukot, jotka on tallennettu kontekstimuuttujiin, eivät edellytä delegointia. Kaikki nämä tiedot ovat jo muistissa, ja koko PowerApps-kieltä voidaan soveltaa.

## <a name="delegable-functions"></a>Delegoitavat funktiot
Seuraava vaihe on vain delegoitavien kaavojen käyttäminen. Tässä ovat kaavan osat, jotka voidaan delegoida. Jokainen tietolähde on kuitenkin erilainen, eivätkä ne kaikki tue kaikkia näitä elementtejä. Tarkista delegointivaroitukset kaavassasi.

Nämä luettelot muuttuvat ajan myötä. Pyrimme tukemaan delegoinnilla useampia funktioita ja operaattoreita.

### <a name="filter-functions"></a>Suodatustoiminnot
**[Filter](functions/function-filter-lookup.md)**, **[Search](functions/function-filter-lookup.md)** ja **[LookUp](functions/function-filter-lookup.md)** voidaan delegoida.  

**Filter**- ja **LookUp**-funktioissa voidaan käyttää näitä termejä tarvittavien tietueiden valitsemiseen taulukon sarakkeista:

* **[And](functions/function-logicals.md)** (mukaan lukien **[&&](functions/operators.md)**), **[Or](functions/function-logicals.md)** (mukaan lukien **[||](functions/operators.md)**), **[Not](functions/function-logicals.md)** (mukaan lukien **[!](functions/operators.md)**)
* **[In](functions/operators.md)**
* **[=](functions/operators.md)**, **[<>](functions/operators.md)**, **[>=](functions/operators.md)**, **[<=](functions/operators.md)**, **[>](functions/operators.md)**, **[<](functions/operators.md)**
* **[+](functions/operators.md)**, **[-](functions/operators.md)**
* **[TrimEnds](functions/function-trim.md)**
* **[IsBlank](functions/function-isblank-isempty.md)**
* **[StartsWith](functions/function-startswith.md)**,  **[EndsWith](functions/function-startswith.md)**
* Vakioarvot, jotka ovat samat kaikissa tietueissa, kuten ohjausobjektien ominaisuudet ja [yleiset ja kontekstimuuttujat](working-with-variables.md).

Voit käyttää myös kaavan osia, jotka antavat tulokseksi vakioarvon kaikille tietueille. Esimerkiksi **Left (Language(); 2)**, **päivämäärä (2019, 3, 31)**, ja **Today()** ei ole riippuvainen tietueen mistään sarakkeista ja siksi palautetaan saman arvon kaikille tietueille. Nämä arvot voidaan lähettää tietolähteeseen vakiona, ja se ei estä delegointia. 

Edellinen luettelo ei sisällä näitä huomattavia kohteita:

* **[If](functions/function-if.md)**
* **[*](functions/operators.md)**, **[/](functions/operators.md)**, **[Mod](functions/function-mod.md)**
* **[Concatenate](functions/function-concatenate.md)** (mukaan lukien **[&](functions/operators.md)**)
* **[ExactIn](functions/operators.md)**
* Merkkijonon käsittelyfunktiot: **[LOWER](functions/function-lower-upper-proper.md)**,  **[Upper](functions/function-lower-upper-proper.md)**,  **[vasemmalle](functions/function-left-mid-right.md)**, **[Mid](functions/function-left-mid-right.md)**,  **[Len](functions/function-left-mid-right.md)**,...
* Signaalit: **[Sijainnin](functions/signals.md)**,  **[Acceleration](functions/signals.md)**,  **[kompassi](functions/signals.md)**,...
* Vaihtuvat: **[RAND](functions/function-rand.md)**,...
* [Kokoelmat](working-with-variables.md)

### <a name="sorting-functions"></a>Funktioiden lajittelu
**[Sort](functions/function-sort.md)** ja **[SortByColumns](functions/function-sort.md)** voidaan delegoida.

**Sort**-funktiossa kaava voi olla vain yhden sarakkeen nimi eikä voi sisältää muita operaattoreita tai funktioita.

### <a name="aggregate-functions"></a>Koostefunktiot
**[Sum](functions/function-aggregates.md)**, **[Average](functions/function-aggregates.md)**, **[Min](functions/function-aggregates.md)** ja **[Max](functions/function-aggregates.md)** voidaan delegoida. Vain rajoitettu tietolähteiden määrä tukee tätä delegointia tällä hetkellä. Katso lisätietoja [delegointiluettelosta](delegation-list.md).

Laskentafunktioita, kuten **[CountRows](functions/function-table-counts.md)**, **[CountA](functions/function-table-counts.md)** ja **[Count](functions/function-table-counts.md)**, ei voi delegoida.

Muita koostefunktioita, kuten **[StdevP](functions/function-aggregates.md)** ja **[VarP](functions/function-aggregates.md)**, ei voi delegoida.

### <a name="table-shaping-functions"></a>Taulukon muovaaminen Funktiot

**[AddColumns](functions/function-table-shaping.md)**,  **[DropColumns](functions/function-table-shaping.md)**,  **[RenameColumns](functions/function-table-shaping.md)**, ja **[ShowColumns](functions/function-table-shaping.md)** osittain delegointia.  Niiden argumentit kaavat voidaan delegoida.  Nämä funktiot tulos koskevat kuitenkin delegointia tietueen rajan.

Kuten tässä esimerkissä käyttäjät voivat käyttää usein **AddColumns** ja **LookUp** yhdistämiseen yhdestä taulukosta toiseen, kutsutaan yleisesti tietokantojen yhdistämiseksi liitoksen:

```powerapps-comma
AddColumns( Products; 
    "Supplier Name"; 
    LookUp( Suppliers; Suppliers.ID = Product.SupplierID ).Name 
)
```

Vaikka **tuotteiden** ja **toimittajat** ehkä delegoitavia tietolähteitä ja **LookUp** on delegoitava funktio, tuloksesta **AddColumns**funktio ei ole delegoitava. Koko kaavan tulos rajoittuu ensimmäinen osa **tuotteiden** tietolähteeseen. Koska **LookUp**-funktio ja sen tietolähde ovat delegoitavia, **Suppliers**-vastaavuus on löydettävissä mistä tahansa tietolähteessä, vaikka se olisi suuri. 

Jos käytät **AddColumns** tällä tavalla **LookUp** täytyy tehdä erilliset kutsut tietolähteeseen kunkin ensimmäisille tietueille **tuotteiden**, joka aiheuttaa paljon verkon chatter. Jos **toimittajat** on tarpeeksi pieni eikä muutu usein, voi olla vaikkapa **kerätä** funktiota [ **OnStart** ](functions/signals.md) välimuistiin tiedot lähde sovelluksesi yhteydessä. Sovelluksesi vaihtoehtoisesti voitu uudelleen niin, että voit saada näkyviin liittyvät tietueet vain, kun käyttäjä pyytää niitä.  
 
## <a name="non-delegable-functions"></a>Funktiot, joita ei voi delegoida
Kaikki muut toiminnot eivät tue delegointia, mukaan lukien nämä tärkeät funktiot:

* **[First](functions/function-first-last.md)**, **[FirstN](functions/function-first-last.md)**, **[Last](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)**
* **[Choices](functions/function-choices.md)**
* **[Concat](functions/function-concatenate.md)**
* **[Collect](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)**
* **[CountIf](functions/function-table-counts.md)**, **[RemoveIf](functions/function-remove-removeif.md)**, **[UpdateIf](functions/function-update-updateif.md)**
* **[GroupBy](functions/function-groupby.md)**, **[Ungroup](functions/function-groupby.md)**

## <a name="non-delegable-limits"></a>Rajoitukset, joita ei voi delegoida
Kaavat, joita ei voi delegoida, käsitellään paikallisesti. Tämä sallii PowerApps-kaavakielen käytön koko laajuudessaan. Tällä on kuitenkin hintansa: kaikki tiedot on ensin tuotava laitteeseen, mikä saattaa merkitä suurten tietomäärin noutamista verkosta. Tähän voi kulua aikaa, mikä antaa sovelluksesta hitaan tai kaatuneen vaikutelman.

Voit välttää tämän, PowerApps rajoittaa paikallisesti tietojen määrään: oletusarvoisesti vain 500 tietuetta.  Valitsimme tämän luvun, jotta sinulla olisi yhä täydet käyttöoikeudet pieniin tietojoukkoihin ja voisit tarkentaa suurien tietojoukkojen käyttöä näkemällä osittaiset tulokset.

Tätä ominaisuutta on luonnollisesti käytettävä varoen, sillä se saattaa hämmentää käyttäjiä. Ajatellaan esimerkiksi **Filter**-funktiota, jossa on delegointikelvoton valintakaava, yli miljoona tietuetta sisältävässä tietolähteessä. Koska suodatus tehdään paikallisesti, vain 500 ensimmäistä tietuetta luetaan. Jos haluttu tietue on tietue 501 tai 500 001, **Filter** ei ota sitä huomioon eikä palauta sitä.

Koostefunktiot voivat myös aiheuttaa sekaannusta. Laske keskiarvo **Average**-funktiolla samasta miljoonan tietueen tietolähteen sarakkeesta. **Average** ei vielä ole delegoitavissa, joten vain ensimmäisten 500 tietueen keskiarvo lasketaan. Jos et ole huolellinen, sovelluksen käyttäjä voi vahingossa tulkita osittaisen vastauksen täydelliseksi vastaukseksi.

## <a name="changing-the-limit"></a>Rajan muuttaminen
500 on oletusarvoinen tietueiden määrä, mutta voit muuttaa tätä arvoa koko sovellusta varten:

1. Valitse **Tiedosto**-välilehdessä **Sovellusasetukset**.
2. Vaihda **Kokeiluominaisuudet**-kohdassa **Tietojen rivirajoitus kyselyille, joita ei voi delegoida** -asetuksen arvon 1 tilalle arvo 2000.

Joissakin tapauksissa tiedät, että 2000 (tai 1000 tai 1500) on riittävä tilanteen tarpeisiin. Voit varoen suurentaa tämän asetuksen vastaamaan tilannettasi. Kun suurennat tätä arvoa, sovelluksesi suorituskyky voi heikentyä erityisesti leveissä taulukoissa, joissa on paljon sarakkeita. Silti on parasta delegoida mahdollisimman paljon.

Jotta sovellus voi skaalautua suuriin tietomääriin, pienennä tämä asetus arvoon 1. Kaikki, mitä ei voi delegoida, palauttaa yhden tietueen, joka on helppo tunnistaa sovellusta testattaessa. Tämä voi auttaa estämään yllätyksiä yritettäessä ottaa soveltuvuusselvityssovellusta käyttöön.

## <a name="delegation-warnings"></a>Delegointivaroitukset
PowerApps antaa varoituksen (keltaisen kolmion), kun luot kaavan, joka sisältää jotakin delegointikelvotonta. Tämä helpottaa sen tietämistä, mitä delegoidaan ja mitä ei.

Delegointivaroitukset näytetään vain kaavoissa, jotka toimivat delegoitavissa tietolähteissä. Jos varoitusta ei tule näkyviin ja uskot, että kaavaa ei delegoida oikein, vertaa tietolähdetyyppiä edellä tässä ohjeaiheessa olevaan [delegoitavien tietolähteiden](delegation-overview.md#delegable-data-sources) luetteloon.

## <a name="examples"></a>Esimerkkejä
Tässä esimerkissä luodaan automaattisesti kolmen näytön sovellus käyttämällä pohjana SQL Server -taulukkoa nimeltä **[dbo].[Fruit]**. Lisätietoja siitä, miten voit luoda sovelluksen, voit käyttää samankaltaisia periaatteet [aiheessa tietoja Common Data Service-](data-platform-create-app.md) SQL Server.

![Kolmen näytön sovellus](./media/delegation-overview/products-afd.png)

Valikoiman **Items**-ominaisuuteen on määritetty kaava, joka sisältää **SortByColumns**- ja **Search**-funktiot. Ne molemmat voi delegoida.

Kirjoita hakuruutuun **”Apple”**.

Näytön yläreunaan tulee hetkeksi pisteitä, kun sovellus viestii SQL Serverin kanssa hakupyynnön käsittelyä varten. Kaikki hakuehtojen mukaiset tietueet tulevat näkyviin, vaikka tietolähde sisältäisi miljoonia tietueita.

![Haun tekstisyötteen ohjausobjekti](./media/delegation-overview/products-apple.png)

Hakutulokset sisältävät sanat **”Apples”**, **”Crab apples”** ja **”Pineapple”**, koska **Search**-funktio hakee kaikkialta tekstisarakkeesta. Jos halusit löytää vain ne tietueet, jotka sisältävät hakusanan hedelmän nimen alussa, voit käyttää monimutkaisempaa hakusanaa toisessa delegoitavassa funktiossa, eli **Filter**-funktiossa. (Yksinkertaisuuden vuoksi poista **SortByColumns**-kutsu.)

![Poistetaan SortByColumns-kutsu](./media/delegation-overview/products-apple-delegationwarning.png)

Uudet tulokset sisältävät sanan **”Apples”**, mutta eivät sanoja **”Crab apples”** ja **”Pineapple”**.  Valikoiman vieressä (ja näytön pikkukuvassa, jos vasemmassa siirtymispalkissa näkyy kuitenkin pikkukuvia) ja kaavan osan alapuolella näkyy sininen aaltoviiva. Nämä elementit ilmaisevat varoitusta. Jos pidät osoitinta valikoiman vieressä olevan keltaisen kolmion kohdalla, tämä sanoma tulee näyttöön:

![Osoittimen pitäminen delegointivaroituksen kohdalla](./media/delegation-overview/products-apple-yellowwarning.png)

SQL Server on delegoitava tietolähde, ja **Filter** on delegoitava funktio. Funktioita **Mid** ja **Len** ei kuitenkaan voida delegoida mihinkään tietolähteeseen.

Mutta se toimi, eikö toiminutkin? Tavallaan. Siksi kyseessä on varoitus, eikä punainen aaltoviiva.

- Jos taulukossa on alle 500 tietuetta, kaava on toiminut täydellisesti. Kaikki tietueet tuotiin laitteeseen ja funktiota **Filter** sovellettiin paikallisesti.
- Jos taulukossa on yli 500 tietuetta, kaava ei palauta tietuetta 501 eikä sitä seuraavia, vaikka ehdot täyttyisivät.

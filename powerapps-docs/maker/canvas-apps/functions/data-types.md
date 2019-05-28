---
title: Tietotyypit | Microsoft Docs
description: Tietotyypit pohjaan perustuvat sovellukset
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/19/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f9acc04a9159349075647ca4e318f15939a230f7
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/24/2019
ms.locfileid: "66216641"
ms.PowerAppsDecimalTransform: true
---
# <a name="data-types-in-canvas-apps"></a>Tietotyypit pohjaan perustuvat sovellukset

Kuten laskentataulukon solujen tiedot työnkulkuja pieni, erilliset arvot sovelluksen kautta hyvin. Esimerkiksi tiedot **Syntymäpäivä** kenttä ja **Anniversary** kentän sekä työnkulun kautta nimellä **päivämäärä** arvo, joka sisältää vuoden, kuukauden ja päivän. Sovelluksen tietää, miten nämä arvot Muotoile, rajoite siihen, mikä on asianmukainen kullekin ja jakaa arvot tietokannan kanssa. Syntymäpäivät eroavat vuosipäivistä henkilöille, mutta järjestelmä käsittelee niitä täsmälleen samalla tavalla. Tässä tapauksessa **päivämäärä** on esimerkki siitä [tietotyyppi](https://en.wikipedia.org/wiki/Data_type).

Tämä artikkeli sisältää tiedot tietotyypit, jotka pohjaan sovellusten tuki. Kun sovellus muodostaa yhteyden ulkoiseen tietolähteeseen, lähteen kullekin tietotyypille on yhdistetty pohjaan perustuvat sovellukset tietotyyppi.

| Tietotyyppi | Kuvaus | Esimerkkejä |
|-----------|-------------|---------|
| **Boolean** | A *true* tai *false* arvo.  Voi käyttää suoraan **Jos**, **suodatin** ja muita funktioita ilman vertailu.  | *tosi* |
| **Hyperlinkki** | Merkkijono, joka sisältää hyperlinkki. | **"http://powerapps.microsoft.com"** |
| **Valuutta** | Valuutta-arvon, joka on tallennettu kaksoistarkkuuksinen liukuluku. Valuutta-arvot ovat samat kuin lukuarvot Valuuttamuotoilu asetuksilla.  | **123**<br>**4.56** |
| **Kuva** | A [Universal Resource Identifier (URI)](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier) tekstimerkkijonon kuvan .jpeg, .png, .svg, .gif ja muut common WWW-kuva muotoilee. | **MyImage** lisätä app-resursseina<br>**"https://northwindtraders.com/logo.jpg"**<br>**”appres://blobmanager/7b12ffa2...”** |
| **Väri** | Värimäärityksen, mukaan lukien alfa-kanavaa. | **Color.Red**<br>**ColorValue (”#102030”)**<br>**RGBA (255, 128, 0, 0,5)** |
| **Päivämäärä** | Ilman aikaa, sovelluksen käyttäjän aikavyöhykkeen päivämäärä. | **Päivämäärä (2019, 5, 16)** |
| **DateTime** | Sovelluksen käyttäjän aikavyöhykkeen ajan, päivämäärän. | **DateTimeValue (”16 toukokuun 2019:23 09 KLO”)** |
| **GUID** | A [GUID-tunnus](https://en.wikipedia.org/wiki/Universally_unique_identifier). | **GUID()**<br>**GUID-tunnus (”123e4567-e89b-12d3-a456-426655440000”)** |
| **Media** | Video- tai tallennus URI tekstimerkkijono. | **MyVideo** lisätä app-resursseina<br>**"https://northwindtraders.com/intro.mp4"**<br>**”appres://blobmanager/3ba411c...”** |
| **Numero** | Liukuluku. | **123**<br>**-4.567**<br>**8.903e121** |
| **Asetusjoukko** | Valinta joukon vaihtoehtojen luku tukena. Tämän tietotyypin yhdistää lokalisoitavan tekstiotsikko numeerinen arvo. Otsikko näkyy sovelluksen ja numeerinen arvo tallennetaan ja käyttää vertailujen. | **ThisItem.OrderStatus** |
| **Tietue** | Tietueen tietojen arvoista. Tämä peräkkäisillä tietotyyppi on muiden tietotyyppien on lueteltu tässä ohjeaiheessa esiintymiä. Lisätietoja: [Taulukoiden](../working-with-tables.md). | **{Yrityksen: "Northwind Traders";<br>Staff: 35 <br>NonProfit: false}** |
| **Tietueen viittaus** | Viittaus tietueen entiteetissä. Viittaukset käytetään usein polymorfinen hakuja. Lisätietoja: [Viittaukset käsitteleminen](../working-with-references.md).| **First(accounts). Omistaja** |
| **Taulukko** | Tietueiden taulukko.  Kaikki tietueet on oltava samat nimet kenttien käyttäen samaa tietotyyppejä ja puuttuu kentät käsitellään *tyhjä*. Tämä peräkkäisillä tietotyyppi on muiden tietotyyppien on lueteltu tässä ohjeaiheessa esiintymiä. Lisätietoja: [Taulukoiden](../working-with-tables.md). | **TABLE ({FirstName: "Sidney";<br>LastName: ”Higa”}; <br>{FirstName: "Nancy";<br>LastName: ”Andersonin”})**
| **Teksti** | Unicode-merkkijono. | **"Hello, World"** |
| **Time** | Ilman päivämäärää, sovelluksen käyttäjän aikavyöhykkeen ajan. | **Aika (11, 23, 45)** |
| **Kaksi vaihtoehtoa** | Valinta kaksi vaihtoehtoa, totuusarvo tukena joukosta. Tämän tietotyypin yhdistää lokalisoitavan tekstiotsikko totuusarvo. Otsikko näkyy sovelluksen ja looginen arvo tallennetaan ja käyttää vertailujen. | **ThisItem.Taxable** |

Monet näistä tietotyypit ovat samankaltaisia ja on sama pohjana esityksen, kuten **hyperlinkki** kentän käsitellään erillisinä **tekstin**.  Lisää tietotyyppejä antaa paremman oletusarvon käyttökokemukset lomakkeet ja muita ohjausobjekteja.

## <a name="blank"></a>Blank

Kaikki tietotyypit voi olla arvoa *tyhjä* (toisin sanoen ei arvoa). Termillä ”null” käytetään usein tietokantoihin tämä konsepti.  

Käytä **tyhjä** funktio **määrittää** tai **Patch** -funktio määrittää muuttuja tai -kentän *tyhjä*. Esimerkiksi **Set (x; kohteen Blank())** poistaa mikä tahansa arvo yleisen muuttujan **x**.  

Testaa *tyhjä* arvon käyttämällä [ **IsBlank** ](function-isblank-isempty.md) funktio. Korvaa mahdollista *tyhjä* arvot, joilla on muita kuin*tyhjä* arvoja käyttämällä [ **Coalesce** ](function-isblank-isempty.md) funktio.

Koska kaikki tietotyypit tue *tyhjä*, **totuusarvo** ja **kaksi vaihtoehtoa** ole tehokkaasti kolme mahdolliset arvot.

## <a name="text-hyperlink-image-and-media"></a>Teksti, hyperlinkin, kuvan ja Media

Nämä tietotyypit neljä perustuvat [Unicode](https://en.wikipedia.org/wiki/Unicode) merkkijono.

### <a name="image-and-media-resources"></a>Kuva ja Media-resurssit

Kautta **tiedoston** -valikosta voit lisätä kuvan, videon ja äänen tiedostoja app-resursseina. Tuotu tiedosto nimen tulee resurssinimi sovelluksessa. Tässä kuvassa logon, jonka nimi on Northwind Traders **nwindlogo**, on lisätty sovellukseen:

![](media/data-types/nwind-resource.png)

Jos haluat käyttää tätä resurssia sovelluksessa, määritä sen **kuvan** ominaisuus [ **kuvan** ](../controls/control-image.md) ohjausobjektin:

![](media/data-types/nwind-image.png)

### <a name="uris-for-images-and-other-media"></a>URI-kuvia ja muuta mediasisältöä

Voit pureudut syvemmälle kyseisen viimeisen esimerkin asettamalla **tekstin** ominaisuus [ **nimen** ](../controls/control-text-box.md) ohjausobjektin **nwindlogo**. Selite näyttää merkkijonon:

![](media/data-types/nwind-text.png)

Pohjaan perustuvat sovellukset kunkin kuvan tai viitata muihin mediatiedosto on pilvipalvelu tai URI-merkkijonon lisännyt app-resursseina.

Esimerkiksi **kuvan** kuvan ohjausobjektin ominaisuus hyväksyy sovelluksen resurssien paitsi myös linkkejä kuviin verkossa, kuten ”https://northwindtraders.com/logo.jpg”. Ominaisuus hyväksyy myös inline-kuvia, jotka käyttävät [tietojen URI-rakennetta](https://en.wikipedia.org/wiki/Data_URI_scheme), kuten tässä esimerkissä:

```powerapps-comma
"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAFAQMAAACtnVQoAAAABlBMVEUAAAB0J3UMNU6VAAAAAXRSTlMAQObYZgAAABRJREFUCNdjUGJgCGVg6GgAkkA2AA8/AffqCEBsAAAAAElFTkSuQmCC"
```

Että URI-osoite näkyy kaksi purppura ruudut skaalataan ylös-versio:

![](media/data-types/double-diamonds.png)

Voit näyttää uusimmat kuva, joka siepataan [ **kameran** ](../controls/control-camera.md) ohjausobjektissa, jos määrität **kuvan** ominaisuuden kuva-ohjausobjektin **valokuva** kamera-ohjausobjektin ominaisuus. Sovellus sisältää kuvan muistissa, ja **valokuva** kamera-ohjausobjektin ominaisuus palauttaa URI-viittaus kuva. Esimerkiksi voi kestää kuvan ja kameran **valokuva** ominaisuus voi palauttaa **”appres://blobmanager/7b12ffa2ea4547e5b3812cb1c7b0a2a0/1”** .

Voit viitata kuvan tai toiseen tietokantaan tallennetun mediatiedosto URI avulla. Näin sovelluksen ei noutaa todellisten tietojen kunnes se itse asiassa tarvitaan. Esimerkiksi liitteen Common Data Service-entiteetissä saattaa palauttaa **”appres://datasources/Contacts/table/...”** Kameran esimerkissä voit näyttää tämän kuvan asettamalla **kuvan** kuvan ohjausobjektin avulla viitettä, joka hakee binaaritiedot-ominaisuuden.

Kun tallennat media-tietotyyppi, kuten kuvan tietokanta, sovellus lähettää todellisen kuvan tai mediatietoja, ei URI-viittaus.

### <a name="size-limits"></a>Kokorajoitukset

Merkkijonoja ja URI nämä tietotyypit on pituudeltaan esiasetus rajaa.

Binaaritiedot, jotka nämä tietotyypit viittaavat myös ei esiasetus rajaa koon. Esimerkiksi kamera-ohjausobjekti, joka viittaa nyt kautta siepattu kuvan **”appres: / /...”** voidaan suuri ja suuren tarkkuuden, kuten laitteen kameran voit muster. Tarkkuus, kehyksen määrä ja muita mediatiedostoja määritteet eivät ole rajoittaa tietotyyppi, mutta tiettyjen ohjausobjektien pelaamista ja tilastotietojen media voi olla omia rajoituksia.

Tietojen kaikenkokoisille koskevat kuitenkin sovelluksen käytettävissä oleva määrä. Selaimista pöytätietokone yleensä tue yli 100 megatavua. Käytettävissä olevan muistin määrän laitteessa, kuten puhelimessa saattaa kuitenkin olla paljon pienempi yleensä alueella 30 – 70 megatavua. Voit selvittää, onko sovelluksesi suoritetaan näiden rajojen, Testaa yleisiä skenaarioita, johon se tulee suorittaa kaikki laitteet.

Paras käytäntö säilyttävät tietoja muistissa vain niin kauan kuin on tarpeen. Lataa kuvat tietokannan heti, kun voit; Lataa kuvat, vain, kun sovelluksen käyttäjä pyytää niitä.

## <a name="number-and-currency"></a>Luku- ja

**Luku** ja **valuutan** tietotyyppejä käyttöä [754 Kahdeksantavuisen kaksoistarkkuuksisen kaksoistarkkuuksinen standard](https://en.wikipedia.org/wiki/IEEE_754). Tämä standardi sisältää erittäin numeroalueen, jossa toimimaan –1.79769 x 10<sup>308</sup> 1.79769 x 10<sup>308</sup>. Pienimmän arvon, joka voidaan esittää on 5 x 10<sup>–324</sup>.

Pohjaan perustuvia sovelluksia voi tarkalleen edustaa kokonaislukuja (tai kokonaislukuja) välillä –9,007,199,254,740,991 (– (2<sup>53</sup> – 1)) ja 9,007,199,254,740,991 (2<sup>53</sup> – 1), mukaan lukien. Tällä alueella on suurempi kuin 32-bittinen (tai 4-tavuinen) kokonaisluku tietotyypit, jotka yleisesti käytettävä. Kuitenkin pohjaan perustuvia sovelluksia ei voi edustaa 64-bittinen (tai 8 tavun) kokonaislukutietotyypeistä. Haluat ehkä Tallenna luku tekstikenttään tai avulla lasketun sarakkeen kopio määrä tekstikenttään, niin, että se on yhdistetty **tekstin** tietotyyppi kangas-sovellus. Tällä tavalla voit pidä, näyttää ja anna nämä arvot sekä vertailu niitä, jotta voit määrittää, onko ne ovat yhtä suuret; kuitenkin numeeristen laskutoimituksia ei voi suorittaa niitä tämän lomakkeen.

Kaksoistarkkuuksinen aritmeettisen on arvioitu, joten se joskus antaa odottamattomia tuloksia dokumentoitu esimerkkejä kanssa. Luonnollisesti kaavan **55 / 100 * 100** palautettavien tarkalleen 55 ja **(55 / 100 * 100) – 55** palautettavien tarkalleen nolla. Kuitenkin jälkimmäisessä kaava palauttaa 7.1054 x 10<sup>–15</sup>, joka on erittäin pieni, mutta ei nolla. Pieni ero ei tavallisesti aiheuttaa ongelmia ja sovelluksen pyöristää sen pois kun tulos näytetään. Pieniä eroja voi kuitenkin yhdistelmä myöhemmät laskutoimituksissa ja antaa väärän vastaukselle näkyvät.

Tietokannan järjestelmien tallentaa valuuttoja usein ja suorittavat laskutoimituksia käyttämällä desimaali matematiikka, joka tarjoaa pienempää aluetta, mutta tarkkuuden tarkemmin. Oletusarvon mukaan pohjaan sovelluksia kartan valuuttoja uloskirjautuminen kaksoistarkkuuksinen arvoille. Tämän vuoksi tulos eri laskutoimituksia, jotka tehdään alkuperäisen decimal-tietotyyppiä. Jos tämän tyyppisen tilitiimin aiheuttaa ongelmia, haluat ehkä näitä arvoja kuin **tekstin**, aivan kuten saattaa suuri kokonaislukuja, jotka on kuvattu aiemmin tässä osiossa kanssa.

## <a name="date-time-and-datetime"></a>Päivämäärä, aika ja päivämäärä ja aika

### <a name="time-zones"></a>Aikavyöhykkeet

Päivämäärän/kellonajan arvot nousua luokkaa:

- **Käyttäjän paikallinen**: Nämä arvot tallennetaan [UTC-AIKAAN (Coordinated Universal Time)](https://en.wikipedia.org/wiki/Coordinated_Universal_Time), mutta sovelluksen käyttäjän aikavyöhykkeen vaikuttaa siihen, miten sovellus näyttää nämä arvot ja miten sovelluksen käyttäjä määrittää ne. Esimerkiksi sama hetkellä näkyy eri tavalla Kanadassa käyttäjälle kuin Japanissa käyttäjälle.
- **Aikavyöhykkeestä riippumaton**: Sovellus näyttää nämä arvot samalla tavalla kuin ja sovelluksen käyttäjälle määrittää samalla tavalla aikavyöhyke riippumatta. Sama hetkellä näkyy käyttäjälle Kanadassa samalla tavalla kuin Japanissa käyttäjälle. Tekijöihin, joka ei pitäisi sovelluksiaan suoritettavaksi eri aikavyöhykkeiden Käytä näitä arvoja, koska ne ovat yksinkertaisempi yleinen.

Tässä taulukossa on joitakin esimerkkejä:

| Päivämäärä-ja aika-tyyppi | Arvo, joka on tallennettu tietokantaan | Näytetään ja annettu 7 tuntia länteen UTC | Näytetään ja annettu neljän tunnin linjan UTC |
|--------------------------|------------------------------|------------------------------|
| **Käyttäjän paikallinen** | Sunnuntai,&nbsp;saattaa&nbsp;19&nbsp;2019: lle<br>4.00 | Lauantai,&nbsp;saattaa&nbsp;18&nbsp;2019: lle<br>9:00 PM | Sunnuntai,&nbsp;saattaa&nbsp;19&nbsp;2019: lle<br>8.00 |
| **Aikavyöhykkeestä riippumaton** | Sunnuntai,&nbsp;saattaa&nbsp;19&nbsp;2019: lle<br>4.00 | Sunnuntai,&nbsp;saattaa&nbsp;19&nbsp;2019: lle<br>4.00 | Sunnuntai,&nbsp;saattaa&nbsp;19&nbsp;2019: lle<br>4.00 | 

- **Käyttäjän paikallisen** ja-aikoja, pohjaan perustuvat sovellukset käyttää selaimessa tai laitteessa aikavyöhyke, mutta mallipohjaisten sovellusten käyttää käyttäjän asetusta tässä Common Data Service. Nämä asetukset yleensä samat, mutta tulokset vaihtelevat, jos nämä asetukset ovat erilaiset.

### <a name="numeric-equivalents"></a>Numeerinen vastaavia kohteita

Pohjaan perustuvat sovellukset pitämällä ja laskea kaikki päivämäärä-ja aika arvoja, onko **käyttäjän paikallisen** tai **aikavyöhykkeestä riippumaton** UTC-muodossa. Sovelluksen kääntää perusteella sovelluksen käyttäjän aikavyöhykkeen, kun ne näytetään ja kun sovelluksen käyttäjä määrittää niiden arvot.

Kun pohjaan perustuva sovellus lukee **aikavyöhykkeestä riippumaton** arvo tietolähteen tai kirjoittaa arvo tietolähteeseen, sovellus säätää automaattisesti korvaamaan sovelluksen käyttäjän aikavyöhykkeen arvon. Sovelluksen käsittelee arvo UTC-arvolle, kaikki muiden päivämäärä ja aika-arvojen sovelluksen kanssa. Tämä korvaaminen alkuperäisen vuoksi **aikavyöhykkeestä riippumaton** arvo tulee näkyviin, kun sovellus säätää sovelluksen käyttäjän aikavyöhykkeen UTC-arvo.

Näin voit tutkia tarkemmin käyttämällä [ **arvo** ](function-value.md) funktio käyttää pohjana olevan numeroarvon päivämäärä ja aika-arvoa. Tämä funktio palauttaa päivämäärä/aika-arvoa millisekunteina jälkeen 1. tammikuuta 1970 00:00:00.000 UTC.

Koska kaikki päivämäärä-ja aika-arvot säilytetään UTC-kaavan **arvo (päivämäärä (1970, 1, 1))** ei palauta nolla useimmat osia maailman, koska **päivämäärä** UTC-funktio palauttaa päivämäärä. Esimerkiksi kaavan, palautetaan 28,800,000 aikavyöhyke, jolla on siirtymä UTC kahdeksan tunnin mukaan. Määrä kuvastaa millisekunteina kahdeksan tunnin aikana.

Palaa yllä esimerkkiä:

| Päivämäärä-ja aika-tyyppi | Arvo, joka on tallennettu tietokantaan | Näytetään ja annettu 7 tuntia länteen UTC | **Arvo** funktio palauttaa |
|--------------------------|------------------------------|------------------------------|
| **Käyttäjän paikallinen** | Sunnuntai,&nbsp;saattaa&nbsp;19&nbsp;2019: lle<br>4.00 | Lauantai,&nbsp;saattaa&nbsp;18&nbsp;2019: lle<br>9:00 PM | 1,558,238,400,000<br> (Sunnuntai,&nbsp;saattaa&nbsp;19&nbsp;2019: lle<br>4:00 AM UTC) |
| **Aikavyöhykkeestä riippumaton** | Sunnuntai,&nbsp;saattaa&nbsp;19&nbsp;2019: lle<br>4.00 | Sunnuntai,&nbsp;saattaa&nbsp;19&nbsp;2019: lle<br>4.00 |1,558,263,600,000<br> (Sunnuntai,&nbsp;saattaa&nbsp;19&nbsp;2019: lle<br>11:00 AM UTC) |

### <a name="converting-unix-times"></a>Muuntaminen Unix kertaa

UNIX kertaa ilmaise 1. tammikuuta 1970 sekuntia määrää 00:00:00 UTC. Koska pohjaan perustuvat sovellukset käyttävät millisekuntia sekunnin sijaan, voit muuntaa kertomalla tai jakamalla 1 000 kahden välillä.

On esimerkiksi Unix-aika on 9. syyskuuta 2001 01:46:40 UTC kuin 1 000 000 000. Voit osoittaa, että päivämäärä-ja aika-arvoa pohjaan perustuvan sovelluksen, kerro numero 1 000 muuntaminen milliseconds ja käyttää sitä [ **tekstin** ](function-text.md) funktio. Kaava **teksti (1000000000 * 1 000, DateTimeFormat.UTC)** palauttaa merkkijonon **2001 – 09-09T01:46:40.000Z**.

Kuitenkin, että-funktio palauttaa **lauantai, syyskuun 8-2001 18:46:40** Jos käytät **DateTimeFormat.LongDateTime24** aikavyöhyke, jolla on siirtymä-7 tuntia (7 tuntia länteen UTC) UTC-muodossa. Tämä tulos näyttää **DateTime** arvon perusteella oikein paikallisen aikavyöhykkeen.

Jaa muuntamaan Unix-aika-tulos **arvo** 1 000 mukaan:
<br>**RoundDown (arvo (UnixTime) / 1 000, 0)**

Jos tarvitset Unix-aika **päivämäärä** arvo muita laskutoimituksia tai näyttää powerappsissa, käyttää tätä kaavaa:
<br>**DateAdd (päivämäärä (1970,1,1) UnixTime, sekuntia)**

### <a name="sql-server"></a>SQL Server

SQL Server on [ **Datetime**, **Datetime2**, ja muut päivämäärä/kellonaika-tietotyypit](https://docs.microsoft.com/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql?view=sql-server-2017) , älä sisällytä aikavyöhykkeen siirtymä ja millä aikavyöhykkeellä ei määritä ne sisältyvät. Pohjaan perustuvat sovellukset oletetaan, että nämä arvot tallennetaan UTC- ja käsitellä niitä **käyttäjän paikallisen**. Jos arvot on tarkoitus aikavyöhykkeen riippumaton, korjaa UTC-käännösten käyttämällä [ **TimeZoneOffset** ](function-dateadd-datediff.md#converting-to-utc) funktio.

Pohjaan perustuvat sovellukset käyttää sisältyvät aikavyöhykkeen tiedot **Datetimeoffset** kentät muunnettaessa arvo sovelluksen sisäinen UTC-esityksen. Sovellusten käyttää aikavyöhyke (aikavyöhyke nollasiirtymää) UTC aina kun tietoja kirjoittaa.

Kaaviosovellusten lukeminen ja kirjoittaminen arvojen [ **aika** ](https://docs.microsoft.com/en-us/sql/t-sql/data-types/time-transact-sql) tyyppi on SQL Server merkkijonoja [kesto ISO 8601-muodossa](https://en.wikipedia.org/wiki/ISO_8601#Durations). On esimerkiksi jäsentää merkkijonon muodossa ja käyttää [ **aika** ](function-date-time.md) funktiota muuntamaan merkkijono **”PT2H1M39S”** - **aika** arvo:

```powerapps-comma
First(
    ForAll(
        MatchAll( "PT2H1M39S"; "PT(?:(?<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" );
        Time( Value( hours ); Value( minutes ); Value( seconds ) )
    )
).Value
```

### <a name="mixing-date-and-time-information"></a>Kohdistinasetusten päivämäärä-ja aika

**Päivämäärä**, **aika**, ja **DateTime** on eri nimet, mutta ne kaikki sisältää samat tiedot päivämäärät ja kellonajat. 

A **päivämäärä** arvo voivat sisältää tiedot, joka on yleensä keskiyöhön. A **aika** arvo voi suorittaa päivämäärätiedot, joka on yleensä 1. tammikuuta 1970. Common Data Service-tallentaa myös ajan tiedot **vain päivämäärä** kentässä on kuitenkin vain päivämäärätiedot oletusarvon mukaan. Vastaavasti pohjaan perustuvat sovellukset joskus erottaa näitä tietotyyppejä määrittää oletusarvon muodot ja ohjausobjekteja.

Lisäämällä ja vähentämällä päivämäärä ja aika-arvoja suoraan ei suositella, koska aikavyöhyke- ja muut muunnosten saattaa aiheuttaa sekavalta tulokset. Käyttämällä **arvo** päivämäärä ja aika-arvoista muuntaminen milliseconds ensin ja otettava huomioon sovelluksen käyttäjän aikavyöhykkeen, tai käytä [ **DateAdd** ](function-dateadd-datediff.md) ja [ **DateDiff** ](function-dateadd-datediff.md) funktioita lisätä tai vähentää siitä jokin näistä arvoista.

## <a name="option-sets-and-two-options"></a>Asetusjoukkoja ja kaksi vaihtoehtoa

Asetusjoukkoja ja kaksi asetusta tietotyyppien on vähintään kaksi vaihtoehtoa, sovellus-käyttäjä voi valita. Esimerkiksi **tilauksen tila** asetusjoukko saattaa tarjota vaihtoehtoja **uusi**, **Shipped**, **laskutettu**, ja **suljettu** . Kaksi asetusta tietotyyppi on vain kaksi vaihtoehtoa.

Molemmat nämä tietotyypit Näytä niiden nimet-merkkijono kontekstissa. Esimerkiksi nimen ohjausobjekti näyttää yhden tilauksen tilan vaihtoehdot Jos ohjausobjektin **tekstin** asetuksena on kaava, joka viittaa kyseisen asetusjoukkoa. Asetuksen nimet saattaa lokalisoitu käyttäjillä eri sijainteihin.

Kun sovellus käyttäjä valitsee vaihtoehdon ja tallentaa muutokset, sovellus lähettää tietokantaan, joka tallentaa tiedot, joka on riippumaton kielen esityksen tietoja. Asetusjoukon vaihtoehtoa lähetettyjen ja tallennettu lukuna ja kaksi asetusta tietotyyppi vaihtoehtoa lähetettyjen ja tallennettu totuusarvo.

Otsikot ovat vain näyttötarkoituksia varten. Suora vertailuja nimien ei voi suorittaa, koska ne ovat tietyn kielelle. Sen sijaan kullekin asetusjoukon on luettelointi, joka toimii taustalla oleva numero tai totuusarvo. Ei voi käyttää esimerkiksi Tämä kaava:

`If( ThisItem.OrderStatus = "Active"; ...`

Mutta voit käyttää tätä kaavaa:

`If( ThisItem.OrderStatus = OrderStatus.Active; ...`

-Yleisiä asetusjoukkoja (entiteeteille jakaa), asetusjoukko luetteloinnin nimi vastaa yleinen asetusjoukko nimi. Paikallisia asetusjoukkoja (joka on rajoitettu entiteetti),-nimi saattaa sisältää entiteetin nimi. Näin vältetään ristiriidassa, jos useita entiteettejä on asetusjoukkoja, joilla on sama nimi. Esimerkiksi **tilit** entiteetillä voi olla **OrderStatus** asetusjoukon ja sen nimi voi olla **OrderStatus (tiliä)** . Kyseistä nimeä sisältää yhden tai useamman välilyöntejä ja sulkeet, joten ympäröi se heittomerkit Jos viitata kaavassa.

Kaksi asetusta arvot voivat lisäksi myös toimivat totuusarvoja. Esimerkiksi nimeltä kaksi asetusta arvo **TaxStatus** voi olla nimien **verollisen** ja **verottoman**, jotka vastaavat *true* ja *false* vastaavasti. Mallitiedoilla, voit käyttää tätä kaavaa:

`If( ThisItem.Taxable = TaxStatus.Taxable; ...`

Voit käyttää myös vastaava kaava:

`If( ThisItem.Taxable; ...`
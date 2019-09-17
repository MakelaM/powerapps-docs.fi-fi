---
title: Tieto tyypit | Microsoft Docs
description: Tieto tyypit kangas sovelluksissa
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
ms.openlocfilehash: 10c5ff9eaa709ab950fa3c3f0efce4f859a71dbc
ms.sourcegitcommit: 5899d37e38ed7111d5a9d9f3561449782702a5e9
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/17/2019
ms.locfileid: "71038001"
ms.PowerAppsDecimalTransform: true
---
# <a name="data-types-in-canvas-apps"></a>Tieto tyypit kangas sovelluksissa

Tieto kulkee sovelluksen kautta pienissä, erillisissä arvoissa, kuten laskenta taulukon soluissa. Esimerkiksi **syntymä** päivä-kentän ja **vuosi** päivä-kentän tiedot kulkevat sekä **päivämäärä** arvona, joka sisältää vuoden, kuukauden ja päivän. Sovellus osaa muotoilla näitä arvoja, rajoittaa syötteen kullekin sopivaan kohtaan ja kertoa arvot tieto kannan kanssa. Syntymä päivät eroavat eri merkki päivistä ihmisiin, mutta järjestelmä käsittelee ne täsmälleen samalla tavalla. Tässä tapa uksessa **päivä määrä** on esimerkki [tieto tyypistä](https://en.wikipedia.org/wiki/Data_type).

Tässä artikkelissa on tietoja kangas sovellusten tukemista tieto tyypeistä. Kun sovellus muodostaa yhteyden ulkoiseen tieto lähteeseen, jokainen kyseisen lähteen tieto tyyppi on yhdistetty kangas sovellusten tieto tyyppiin.

| Tietotyyppi | Kuvaus | Esimerkkejä |
|-----------|-------------|---------|
| **Totuus arvo** | Arvo on *tosi* tai *Epätosi* .  Voidaan käyttää suoraan **IF**-, **Filter** -ja Other-funktioissa ilman vertailua.  | *tosi* |
| **Väri** | Väri määritys, mukaan lukien alfa kanava. | **Color.Red**<br>**ColorValue ("#102030")**<br>**RGBA (255, 128, 0, 0,5)** |
| **Valuutta** | Valuutan arvo, joka on tallennettu liuku luku numeroon. Valuutta-arvot ovat samat kuin luku arvot, joissa on valuutta muotoilu asetukset.  | **123**<br>**4,56** |
| **Päivä määrä** | Päivä määrä ilman aikaa sovelluksen käyttäjän aika vyöhykkeellä. | **Päivä määrä (2019, 5, 16)** |
| **DateTime** | Päivä määrä, joka on aika, sovelluksen käyttäjän aika vyöhykkeellä. | **Datetime Value ("16. toukokuuta 2019 1:23:09 PM")** |
| **GUID** | [Globally Unique-tunnus](https://en.wikipedia.org/wiki/Universally_unique_identifier). | **GUID ()**<br>**GUID ("123e4567-e89b-12d3-A456-426655440000")** |
| **HYPERLINK** | Teksti merkki jono, joka sisältää hyperlinkin. | **"http://powerapps.microsoft.com"** |
| **Kuva** | [URI (Universal Resource Identifier)](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier) -teksti merkki jono kuvaan kohteessa. JPEG,. png,. SVG,. gif tai muu yleinen www-kuva muoto. | **Myimage** lisättiin sovellus resurssina<br>**"https://northwindtraders.com/logo.jpg"**<br>**"appres://blobmanager/7b12ffa2..."** |
| **Media** | URI-teksti merkki jono video-tai ääni tallenteeseen. | **MyVideo** lisättiin sovellus resurssina<br>**"https://northwindtraders.com/intro.mp4"**<br>**"appres://blobmanager/3ba411c..."** |
| **Numero** | Liuku luku numero. | **123**<br>**-4,567**<br>**8.903e121** |
| **Asetus asetus** | Valinta vaihtoehto joukosta, jota tukee luku. Tämä tieto tyyppi yhdistää lokalisoitavan teksti nimen, jolla on luku arvo. Nimi näkyy sovelluksessa, ja numero-arvo tallennetaan ja sitä käytetään vertailuissa. | **ThisItem. OrderStatus** |
| **Tietue** | Tieto arvojen tietue. Tämä yhdistelmä tieto tyyppi sisältää esiintymiä muista tieto tyypeistä, jotka on lueteltu tässä ohje aiheessa. Lisätietoja: [Taulu koiden käsitteleminen](../working-with-tables.md). | **Yritys "Northwind Traders";<br>henkilöstö: 35; <br>kaupallinen: False}** |
| **Tietue viittaus** | Viittaus entiteetin tietueeseen. Tällaisia viitta uksia käytetään usein polymorfisten hakujen yhteydessä. Lisätietoja: [Käsitellään viitta uksia](../working-with-references.md).| **First (accounts). Omistaja** |
| **Taulukon** | Tietue taulukko.  Kaikilla tietueilla on oltava samat nimet kentissä, joilla on samat tieto tyypit, ja pois jätetyt kentät käsitellään *tyhjinä*. Tämä yhdistelmä tieto tyyppi sisältää esiintymiä muista tieto tyypeistä, jotka on lueteltu tässä ohje aiheessa. Lisätietoja: [Taulu koiden käsitteleminen](../working-with-tables.md). | **Taulukko ({FirstName: "Sidney";<br>suku nimi: "Higa"}; <br>{firstname: "Nancy";<br>suku nimi: "Anderson"})**
| **Teksti** | Unicode-teksti merkki jono. | **"Hei maailma"** |
| **Aika** | Aika ilman päivä määrää sovelluksen käyttäjän aika vyöhykkeellä. | **Aika (11, 23, 45)** |
| **Kaksi vaihto ehtoa** | Vaihto ehto kahdesta vaihto ehdosta, joiden tukena on totuus arvo. Tämä tieto tyyppi yhdistää lokalisoitavan teksti nimen, jolla on totuus arvo. Nimi näkyy sovelluksessa, ja totuus arvo tallennetaan ja sitä käytetään vertailuissa. | **ThisItem. verotettava** |

Monet näistä tieto tyypeistä ovat samankaltaisia ja niiden pohjana on sama esitys tapa, kuten **hyperlinkkikenttä** , jota käsitellään **tekstinä**.  Lisä tieto tyypit tarjoavat parempia oletus kokemuksia lomakkeissa ja muissa ohjaus objekteissa.

## <a name="blank"></a>Blank

Kaikkien tieto tyyppien arvo voi olla *tyhjä* (toisin sanoen ei arvoa). Käsitettä "Null" käytetään usein tieto kannoissa tätä käsitettä varten.  

Voit määrittää muuttujan tai kentän *tyhjäksi*käyttämällä **tyhjä** -funktiolla **joukko** -tai **patch** -funktiolla. Esimerkiksi **asetus (x, Blank ())** poistaa minkä tahansa arvon yleisestä muuttujasta **x**.  

Testaa *tyhjää* arvoa käyttämällä [**isblank**](function-isblank-isempty.md) -funktiolla. Korvaa mahdolliset *Tyhjät* arvot muilla kuin*tyhmillä* arvoilla käyttämällä [**conalesce**](function-isblank-isempty.md) -funktiolla.

Koska kaikki tieto tyypit tukevat *tyhjää*, **Boolean** -ja **Two-asetus** tieto tyypeillä on todellisuudessa kolme mahdollista arvoa.

## <a name="text-hyperlink-image-and-media"></a>Teksti, hyperlinkki, kuva ja tieto väline

Kaikki neljä tieto tyyppiä perustuvat [Unicode](https://en.wikipedia.org/wiki/Unicode) -teksti merkki jonoon.

### <a name="image-and-media-resources"></a>Kuva-ja Multimediaresurssit

**Tiedosto** -valikon avulla voit lisätä kuva-, video-ja ääni tiedostoja sovellus resursseina. Tuodun tiedoston nimestä tulee sovelluksen resurssin nimi. Tässä kuvassa Northwind Traders-logo, jonka nimi on **nwindlogo**, on lisätty sovellukseen:

![](media/data-types/nwind-resource.png)

Jos haluat käyttää tätä resurssia sovelluksessa, määritä se [**kuva**](../controls/control-image.md) -ohjaus objektin **Image** -ominaisuudessa:

![](media/data-types/nwind-image.png)

### <a name="uris-for-images-and-other-media"></a>Kuvien ja muiden tieto väline-URI-osoitteita

Voit kaivaa hieman syvemmälle tähän viimeiseen esimerkkiin asettamalla [**Label**](../controls/control-text-box.md) -ohjaus objektin **Text** -ominaisuudeksi **nwindlogo**. Selitteessä näytetään teksti merkki jono:

![](media/data-types/nwind-text.png)

Pohjaan liittyvät sovellukset viittaavat kuhunkin kuvaan tai muuhun multimediatiedostoon, olipa se pilvi palvelussa tai lisättynä sovellus resurssina URI-teksti merkki jonon avulla.

Esimerkiksi kuva-ohjaus objektin **Image** -ominaisuus hyväksyy sovellus resurssien lisäksi myös linkit verkossa oleviin kuviin, kuten "https://northwindtraders.com/logo.jpg". Ominaisuus hyväksyy myös sisäiset kuvat, jotka käyttävät [tietojen URI-rakennetta](https://en.wikipedia.org/wiki/Data_URI_scheme), kuten tässä esimerkissä:

```powerapps-comma
"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAFAQMAAACtnVQoAAAABlBMVEUAAAB0J3UMNU6VAAAAAXRSTlMAQObYZgAAABRJREFUCNdjUGJgCGVg6GgAkkA2AA8/AffqCEBsAAAAAElFTkSuQmCC"
```

URI näyttää kahden purppuran timantin skaalatun version:

![](media/data-types/double-diamonds.png)

Voit näyttää [**kamera**](../controls/control-camera.md) -ohjaus objektissa siepatun uusimman kuvan, jos asetat kuva-ohjaus objektin **kuva** -ominaisuudeksi kamera-ohjaus objektin **valo kuva** -ominaisuudeksi. Sovellus pitää kuvan muistissa, ja kamera-ohjaus objektin **valo kuva** -ominaisuus palauttaa kuvaan URI-viitta uksen. Voit esimerkiksi ottaa kuvan, ja kameran **valokuva** ominaisuus saattaa palauttaa kohteen **"appres://blobmanager/7b12ffa2ea4547e5b3812cb1c7b0a2a0/1"** .

URI-tunnuksessa viitataan kuvaan tai toiseen tieto kantaan tallennettuun tieto väline tiedostoon. Näin sovellus ei nouda todellisia tietoja, ennen kuin se on todella tarpeellinen. Esimerkiksi Common Data Service-entiteetin liite voi palauttaa kohteen **"appres://DataSources/Contacts/Table/..."** Kuten kamera esimerkissä, voit näyttää tämän kuvan asettamalla kuva-ohjaus objektin **Image** -ominaisuudeksi tämän viitta uksen, joka noutaa binaaritiedot.

Kun tallennat tieto kantaan tieto tyypin, kuten kuvan,, sovellus lähettää todelliset kuva-tai materiaali tiedot, ei URI-viittausta.

### <a name="size-limits"></a>Koko rajoitukset

Teksti merkki jonoina ja URI-tietoina nämä tieto tyypit eivät sisällä niiden pituutta ennalta määritettyä rajaa.

Binaaritiedot, joita nämä tieto tyypit viittaavat, eivät myöskään sisällä esimääritettyä rajoitusta koon mukaan. Esimerkiksi kamera-ohjaus objektin kautta siepattuun kuvaan, joka on nyt Viitattu nimellä **"appres://..."** , voi olla yhtä suuri ja korkea erotus kyky kuin laitteen kameralla voi koota. Tieto tyyppi ei rajoitu tarkkuutta, kehys nopeutta ja muita määritteitä, mutta tieto välineen toistamista ja sieppaamista varten voi olla omat rajoituksensa.

Kaikkiin tieto kokoihin sovelletaan kuitenkin käytettävissä olevan muistin määrää sovelluksessa. Pöytä tieto koneessa suoritettavat selaimet tukevat yleensä yli 100 Mega tavua tietoja. Laitteen, kuten puhelimen, käytettävissä olevan muistin määrä voi kuitenkin olla huomattavasti pienempi, yleensä 30-70 Mega tavun alueella. Jos haluat tarkistaa, toimiiko sovelluksesi näissä rajoissa, testaa yleisiä tilanteita kaikissa laitteissa, joissa se suoritetaan.

Paras käytäntö on säilyttää tiedot muistissa vain niin kauan kuin on tarpeen. Lataa kuvat tieto kantaan niin pian kuin mahdollista; Lataa kuvat vain, kun sovelluksen käyttäjä pyytää niitä.

## <a name="number-and-currency"></a>Luku ja valuutta

**Luku** -ja **Valuutta** tieto tyypeissä käytetään [IEEE 754-liuku luku standardia](https://en.wikipedia.org/wiki/IEEE_754). Tämä standardi tarjoaa erittäin suuren määrän erilaisia työmääriä – 1,79769 x 10<sup>308</sup> – 1,79769 x 10<sup>308</sup>. Pienin arvo, joka voidaan esittää, on 5 x 10<sup>– 324</sup>.

Pohjaan viittaavat sovellukset voivat tarkalleen edustaa kokonaislukuja (tai kokonaislukuja) välillä – 9 007 199 254 740 991 (– (2<sup>53</sup> – 1)) ja 9 007 199 254 740 991 (2<sup>53</sup> – 1), mukaan lukien. Tämä alue on suurempi kuin tieto kantojen yleisesti käytössä 32-bittinen (tai 4-tavuinen) kokonaislukutieto tyyppi. Kangas sovellukset eivät kuitenkaan voi edustaa 64-bittisiä (tai 8-tavuisia) kokonaislukutietotyyppejä. Haluat ehkä tallentaa numeron teksti kenttään tai käyttää laskettua saraketta, jotta voit kopioida numeron teksti kenttään niin, että se on yhdistetty **teksti** -tieto tyyppiin kangas sovelluksessa. Tällä tavalla voit pitää, näyttää ja syöttää näitä arvoja sekä verrata niitä määrittääksesi, ovatko ne yhtä suuret. et voi kuitenkaan tehdä niille numeerisia lasku toimituksia tässä lomakkeessa.

Liuku lukujen aritmeettinen arvo on likimääräinen, joten se voi toisinaan antaa odottamattomia tuloksia monilla dokumentoiduilla esimerkeillä. Saatat odottaa, että kaava **55/100 * 100** palauttaa tarkalleen 55 ja **(55/100 * 100)-55** , jos haluat palauttaa tarkalleen nollan. Jälkimmäinen kaava palauttaa kuitenkin 7,1054 x 10<sup>– 15</sup>, joka on hyvin pieni mutta ei nolla. Tämä pieni ero ei yleensä aiheuta ongelmia, ja sovellus pyöristää sen pois, kun tulos näytetään. Pienet erot voivat kuitenkin yhdistyä myöhemmissä laskelmissa, ja ne näyttävät antamaan väärän vasta uksen.

Tieto kanta järjestelmät tallentavat usein valuuttoja ja suorittavat lasku toimituksia käyttämällä desimaalimuotoista matematiikkaa, joka tarjoaa pienemmän alueen mutta enemmän tarkkuutta. Oletus arvon mukaan pohjaan liittyvät sovellukset kartan valuutat liuku luku arvoilla ja niiden ulkopuolella. Tästä syystä tulokset saattavat poiketa alkuperäisen kymmen järjestelmä tieto tyypin mukaisista laskelmista. Jos tämän tyyppinen risti riita aiheuttaa ongelmia, haluat ehkä käsitellä näitä arvoja **tekstinä**samalla tavalla kuin aiemmin tässä osiossa kuvatut suuret kokonaisluvut.

## <a name="date-time-and-datetime"></a>Päivä määrä, kellon aika ja DateTime

### <a name="time-zones"></a>Aikavyöhykkeet

Päivä määrä-ja aika-arvot kuuluvat seuraaviin luokkiin:

- **Käyttäjä, paikallinen**: Nämä arvot tallennetaan [UTC (Coordinated Universal Time)](https://en.wikipedia.org/wiki/Coordinated_Universal_Time), mutta sovelluksen käyttäjän aika vyöhyke vaikuttaa siihen, miten sovellus näyttää nämä arvot ja miten sovelluksen käyttäjä määrittää ne. Esimerkiksi sama hetki vaikuttaa Kanadassa eri tavalla kuin käyttäjälle Japanissa.
- **Aika vyöhyke riippumaton**: Sovellus näyttää nämä arvot samalla tavalla ja sovelluksen käyttäjä määrittää ne samalla tavalla aika vyöhykkeestä riippumatta. Sama aika näkyy samalla tavalla Kanadassa käyttäjälle kuin Japanissa. Sovellusten tekijät, jotka eivät odota, että heidän sovelluksiaan suoritetaan eri aika vyöhykkeillä, käyttävät näitä arvoja, koska ne ovat yleisesti ottaen yksinkertaisempia.

Tässä taulukossa on joitakin esimerkkejä:

| Päivä määrän/kellon ajan tyyppi | Tieto kantaan tallennettu arvo | Arvo näytetään ja annettiin 7 tuntia UTC-aika länteen | Arvo näytetään ja annettiin 4 tuntia UTC-ajan itäpuolella |
|--------------------------|------------------------------|------------------------------|
| **Käyttäjän paikallinen** | Sunnuntai 19&nbsp;.&nbsp;toukokuuta2019&nbsp;<br>4:00 AM | Lauantai,&nbsp;18&nbsp;.toukokuuta2019&nbsp;<br>9:00 PM | Sunnuntai 19&nbsp;.&nbsp;toukokuuta2019&nbsp;<br>8:00 AM |
| **Aika vyöhyke, riippumaton** | Sunnuntai 19&nbsp;.&nbsp;toukokuuta2019&nbsp;<br>4:00 AM | Sunnuntai 19&nbsp;.&nbsp;toukokuuta2019&nbsp;<br>4:00 AM | Sunnuntai 19&nbsp;.&nbsp;toukokuuta2019&nbsp;<br>4:00 AM | 

**Käyttäjän paikallisissa** päivä määrä-ja kellon aikoina pohjaan perustuvat sovellukset käyttävät selaimen tai laitteen aika vyöhykettä, mutta mallipohjaiset sovellukset käyttävät käyttäjän asetusta Common Data Service. Nämä asetukset ovat yleensä samat, mutta tulokset eroavat toisistaan, jos nämä asetukset eroavat toisistaan.

Muunna paikallista aikaa UTC-ajaksi ja takaisin uudelleen [**DateAdd**](function-dateadd-datediff.md) -ja [**Time zoneinformation**](function-dateadd-datediff.md) -funktioiden avulla.  Tutustu näiden funktioiden dokumentaation lopussa oleviin esimerkkeihin.

### <a name="numeric-equivalents"></a>Numeric-vastineet

Pohjaan liittyvät sovellukset omistavat ja laskevat kaikki päivä määrä-ja aika-arvot riippumatta siitä, onko **käyttäjä paikallinen** vai **aika vyöhyke** UTC-tilassa. Sovellus kääntää arvot sovelluksen käyttäjän aika vyöhykkeen mukaan, kun ne näytetään ja kun sovelluksen käyttäjä määrittää ne.

Kun kangas sovellus lukee **aika vyöhykkeen riippumattoman** arvon tieto lähteestä tai kirjoittaa tällaisen arvon tieto lähteeseen, sovellus säätää automaattisesti arvoa, joka kompensoi sovelluksen käyttäjän aika vyöhykkeen. Sovellus käsittelee arvoa UTC-arvona, joka on johdonmukainen sovelluksen kaikkien muiden päivä määrä-ja aika-arvojen kanssa. Tämän korva uksen vuoksi alkuperäisen **aika vyöhykkeen riippumaton** arvo tulee näkyviin, kun sovellus muuttaa sovelluksen käyttäjän aika vyöhykkeen UTC-arvoa.

Voit tarkkailla tätä toimintaa tarkemmin käyttämällä [**Value**](function-value.md) -funktiolla pohjana olevaa numeerista arvoa päivä määrä-ja aika-arvolle. Tämä funktio palauttaa päivä määrä/aika-arvon Milli sekunteina, joka on 1. tammi kuuta 1970 00:00:00.000 UTC.

Koska jokainen päivä määrä-ja aika-arvo säilytetään UTC-tilassa, kaavan **arvo (Date (1970, 1, 1))** ei palauta nollaa Useimmissa osissa maailmaa, koska **Date** -funktio palauttaa päivä määrän UTC-aikana. Kaava palauttaisi esimerkiksi 28 800 000 aika vyöhykkeellä, joka on siirtymässä UTC-ajasta kahdeksalla tunnissa. Tämä luku ilmaisee kahdeksan tunnin Milli sekuntien määrän.

Palautetaan esimerkkiin ylhäältä:

| Päivä määrän/kellon ajan tyyppi | Tieto kantaan tallennettu arvo | Arvo näytetään ja annettiin 7 tuntia UTC-aika länteen | **Value** -funktio palauttaa |
|--------------------------|------------------------------|------------------------------|
| **Käyttäjän paikallinen** | Sunnuntai 19&nbsp;.&nbsp;toukokuuta2019&nbsp;<br>4:00 AM | Lauantai,&nbsp;18&nbsp;.toukokuuta2019&nbsp;<br>9:00 PM | 1 558 238 400 000<br> (Sunnuntai&nbsp;19&nbsp;. toukokuuta 2019&nbsp;<br>4:00 UTC) |
| **Aika vyöhyke, riippumaton** | Sunnuntai 19&nbsp;.&nbsp;toukokuuta2019&nbsp;<br>4:00 AM | Sunnuntai 19&nbsp;.&nbsp;toukokuuta2019&nbsp;<br>4:00 AM |1 558 263 600 000<br> (Sunnuntai&nbsp;19&nbsp;. toukokuuta 2019&nbsp;<br>11:00 UTC) |

### <a name="converting-unix-times"></a>Muunnetaan UNIX-aikoja

UNIX-ajat kuvastavat sekuntien määrää 1. tammi kuuta 1970 00:00:00 UTC alkaen. Koska kangas sovellukset käyttävät Milli sekunteja sekuntien sijaan, voit muuntaa ne kahden mukaan kertomalla tai jakamalla 1 000.

Esimerkiksi UNIX-aika on 9. syyskuuta 2001 kello 01:46:40 UTC as 1 000 000 000. Jos haluat näyttää päivä määrä-ja aika-arvon pohjaan nähden, kerro tämä luku arvolla 1 000, jos haluat muuntaa sen Milli sekunteina, ja käyttää sitä sitten [**teksti**](function-text.md) -funktiolla. Kaavan **teksti (1000000000 * 1000, DateTimeFormat. UTC)** palauttaa merkki jonon **2001-09-09T01:46:40.000 z**.

Tämä funktio palauttaa kuitenkin **lauantai 8. syyskuuta 2001 18:46:40,** jos käytät **DateTime Format. LongDateTime24** -muotoa aika vyöhykkeellä, joka on-7 tuntia siirtymää UTC-ajasta (7 tuntia länteen UTC:sta). Tämä tulos esittää **DateTime** -arvon oikein paikallisen aika vyöhykkeen perusteella.

Jos haluat muuntaa UNIX-ajaksi, Jaa tulos **arvosta arvolla** 1 000:
<br>**RoundDown (arvo (UnixTime)/1000, 0)**

Jos tarvitset UNIX-ajan **Date** -arvossa lisä laskelmia tai powerappsin näyttämistä varten, käytä seuraavaa kaavaa:
<br>**DateAdd (päivä määrä (1970, 1, 1), Uniqutime, Seconds)**

### <a name="sql-server"></a>SQL Server

SQL Server sisältää [ **DateTime**-, **Datetime2**-ja muita päivä määrä/aika-tieto tyyppejä,](https://docs.microsoft.com/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql?view=sql-server-2017) jotka eivät sisällä aika vyöhyke siirtymää, eivätkä ilmaise, missä aika vyöhykkeessä ne ovat. Pohjaan perustuvat sovellukset oletetaan, että nämä arvot on tallennettu UTC-muodossa ja että ne ovat **käyttäjän paikallisia**. Jos arvot on tarkoitettu aika vyöhykkeen mukaan riippumattomiksi, voit korjata UTC-käännökset käyttämällä Time [**Zoneoffset**](function-dateadd-datediff.md#converting-to-utc) -funktiolla.

Canvas-sovellukset käyttävät **DateTime-offset** -kentissä olevia aika vyöhyke tietoja muunnettaessa arvoa sovelluksen sisäiseen UTC-esitykseen. Sovellukset käyttävät aina UTC-aikaa aika vyöhykkeenä (Zero Time Zone-siirtymä), kun he kirjoittavat tietoja.

Kangas sovellukset lukevat ja kirjoittavat [**Time**](https://docs.microsoft.com/sql/t-sql/data-types/time-transact-sql) -tieto tyypin arvoja SQL Server teksti merkki jonoina [ISO 8601-kesto muodossa](https://en.wikipedia.org/wiki/ISO_8601#Durations). Sinun täytyy esimerkiksi jäsentää tämä merkki jono muoto ja käyttää [**Time**](function-date-time.md) -funktiolla teksti merkki jonon **"PT2H1M39S"** muuntamista **Time** -arvoksi:

```powerapps-comma
First(
    ForAll(
        MatchAll( "PT2H1M39S"; "PT(?:(?<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" );
        Time( Value( hours ); Value( minutes ); Value( seconds ) )
    )
).Value
```

### <a name="mixing-date-and-time-information"></a>Päivä määrän ja kellon ajan tietojen sekoittaminen

**Päivä määrällä**, **ajalla**ja **DateTime** -kohteella on eri nimet, mutta niillä kaikilla on samat tiedot päivä määristä ja kellon ajoista. 

**Päivämäärä** arvo voi sisältää aika tietoja, jotka ovat yleensä Keski yöllä. **Aika** -arvo voi kuljettaa päivämäärä tietoja, jotka ovat yleensä 1. tammi kuuta 1970. Common Data Service myös tallentaa aika tiedot **vain päivä määrä** -kentän kanssa, mutta ne näyttävät vain päivämäärä tiedot Oletus arvon mukaan. Myös kangas sovellukset erottavat toisistaan nämä tieto tyypit määrittääkseen oletus muotoiluja ja-ohjaus objektin.

Päivä määrä-ja aika-arvojen lisäämistä ja vähentämistä suoraan ei suositella, koska aika vyöhyke ja muut muunnokset saattavat aiheuttaa hämmentäviä tuloksia. Käytä **Value** -funktiota päivä määrä/aika-arvojen muuntamiseen Milli sekunteina ja ota huomioon sovelluksen käyttäjän aika vyöhyke tai Lisää tai vähennä jostakin näistä arvoista [**DateAdd**](function-dateadd-datediff.md) -ja [**DateDiff**](function-dateadd-datediff.md) -funktioiden avulla.

## <a name="option-sets-and-two-options"></a>Asetus joukot ja kaksi vaihto ehtoa

Asetus joukot ja kahden vaihto ehdon tieto tyypit tarjoavat vähintään kaksi vaihto ehtoa, joiden avulla sovellus käyttäjä voi valita. Esimerkiksi tila **uksen tilan** asetus asetus voi tarjota vaihto ehtoja **Uusi**, **Lähetetty**, **Laskutettu**ja **suljettu**. Kahden vaihto ehdon tieto tyyppi tarjoaa vain kaksi vaihto ehtoa.

Molemmat näistä tieto tyypeistä näyttävät niiden nimet teksti merkki jonon yhteydessä. Esimerkiksi selite-ohjaus objektissa näkyy jokin tila uksen tilan vaihto ehdoista, jos ohjaus objektin **Text** -ominaisuudeksi on määritetty kaava, joka viittaa kyseiseen asetus joukkoon. Asetusten nimet voidaan lokalisoida sovelluksen käyttäjille eri sijainneissa.

Kun sovelluksen käyttäjä valitsee vaihto ehdon ja tallentaa tämän muutoksen, sovellus lähettää tiedot tieto kantaan, joka tallentaa tiedot edustukseen, joka on riippumaton kielestä. Asetus joukon asetus lähetetään ja tallennetaan lukuna, ja kahden vaihto ehdon tieto tyypin vaihto ehto lähetetään ja tallennetaan totuus arvona.

Nimet ovat vain näyttö tarkoituksia varten. Et voi tehdä suoria vertailuja otsikoihin, koska ne ovat kielikohtaisia. Sen sijaan kullakin asetus joukko sisältää luetteloinnin, joka toimii pohjana olevan luvun tai totuus arvon kanssa. Et voi esimerkiksi käyttää seuraavaa kaavaa:

`If( ThisItem.OrderStatus = "Active"; ...`

Voit kuitenkin käyttää seuraavaa kaavaa:

`If( ThisItem.OrderStatus = OrderStatus.Active; ...`

Yleisasetuksille (mitkä entiteetit jakavat) asetus joukon luetteloinnin nimi vastaa yleisen asetus joukon nimeä. Paikallisissa asetus joukoissa (jotka on määritetty entiteettiin) nimi voi sisältää entiteetin nimen. Tämä estää risti riidat, jos useilla entiteeteillä on asetus joukkoja, joilla on sama nimi. Esimerkiksi **accounts** -entiteetillä voi olla **orderstatus** -asetus asetus, ja sen nimi voi olla **orderstatus (accounts)** . Nimi sisältää vähintään yhden väli lyöntien ja sulkeiden, joten sinun on ympäröidä se heitto merkeillä, jos viittaat siihen kaavassa.

Lisäksi kahden vaihto ehdon arvot voivat myös käyttäytyä totuus arvo-arvoina. Esimerkiksi kahden asetuksen **Taxstatus** -arvolla voi olla **verovelvolliset** ja **verottomat**nimet, jotka vastaavat arvoa *True* ja *false* . Voit osoittaa tätä kaavaa käyttämällä seuraavaa kaavaa:

`If( ThisItem.Taxable = TaxStatus.Taxable; ...`

Voit myös käyttää tätä vastaavaa kaavaa:

`If( ThisItem.Taxable; ...`
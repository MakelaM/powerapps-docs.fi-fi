---
title: JSON-funktio | Microsoft Docs
description: Viitetiedot, mukaan lukien syntaksi JSON-funktiosta powerappsissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/02/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 74e10a5b073e16ba9f35139441c94e9911446a0f
ms.sourcegitcommit: 2084789802fc5134dbeb888e759cced46019a017
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/06/2019
ms.locfileid: "66736395"
ms.PowerAppsDecimalTransform: true
---
# <a name="json-function-in-powerapps"></a>JSON-funktio powerappsissa

Luo taulukon, tietueen tai arvo JSON-merkkijonon.

## <a name="description"></a>Kuvaus

**JSON** -funktio palauttaa JavaScript Object Notation (JSON) esitys tietorakenne tekstinä niin, että se sopii tai lähetettäessä verkon kautta. [ECMA-404](http://www.ecma-international.org/publications/files/ECMA-ST/ECMA-404.pdf) ja [IETF RFC 8259](https://tools.ietf.org/html/rfc8259) kuvataan muodossa, jota käytetään yleisesti JavaScript ja muut ohjelmointikielille.

Pohjaan sovellusten tuki [tietotyyppejä](data-types.md) , joka tässä taulukossa on lueteltu niiden tekstiesitys tietoja:

| Tietotyyppi | Kuvaus | Tuloksen esimerkki |
|-----------|-------------|---------|
| **Boolean** | *TRUE* tai *false*. | `true` |
| **Väri** | Merkkijono, joka sisältää 8-numeroinen heksadesimaalimuodossa värin. Tämän esityksen käyttää muotoa #*rrggbbaa*, jossa *rr* on punainen komponentti, *gg* on vihreä, *bb* on sininen ja *aa* on alfa-kanavaa. Alfa kanavan **00** on täysin läpinäkyvä ja **ff** on täysin läpinäkymätön. Voit välittää merkkijono [ **ColorValue** ](function-colors.md) funktio.  | `"#102030ff"` |
| **Valuutta** | Luku, joka käyttää asianmukaisen desimaalierottimena käyttäjän kielen. Tieteellistä merkintätapaa käytetään tarvittaessa. | `1,345` |
| **Päivämäärä** | Merkkijono, joka sisältää ISO 8601-kalenterin päivämäärää **VVVV-KK-PP** muodossa. | `"2019-03-31"` |
| **DateTime** | Merkkijono, joka sisältää ISO 8601-päivämäärä ja aika. Päivämäärä ja aika-arvot ovat UTC-muodossa, kuten lopun ”Z” ilmaisee.  | `"2019-03-31T22:32:06.822Z"`  |
| **GUID** | Merkkijono, joka sisältää GUID-arvon. Kirjaimet ovat pieniä. | `"751b58ac-380e-4a04-a925-9f375995cc40"`
| **Kuva, Media** | Jos **IncludeBinaryData** on määritetty, mediatiedostoja on koodattu merkkijono. WWW-viittauksia, jotka käyttävät http: tai HTTPS-protokollaa: URL-rakenteen ei muokata. Muistissa binaaritiedot viittaukset ovat koodattu [”tietoja:*mimetype*; base64...”](https://en.wikipedia.org/wiki/Data_URI_scheme) muodossa. Muistin tiedot sisältävät kuvia, jotka käyttäjät siepata käyttämällä [ **kameran** ](../controls/control-camera.md) ohjausobjekti ja muut viittaukset kanssa appres: ja BLOB-objekti: URL-mallit.| `"data:image/jpeg;base64,/9j/4AA..."` |
| **Numero** | Luku, joka käyttää asianmukaisen desimaalierottimena käyttäjän kielen. Tieteellistä merkintätapaa käytetään tarvittaessa. | `1,345` |
| **Asetus&nbsp;määrittää** | Numeerinen asetusta arvo, ei otsikko, jota käytetään näyttämistä varten. Numeerinen arvo käytetään, koska se on riippumaton kieli.  | `1001` |
| **Time** | Merkkijono, joka sisältää ISO 8601-kalenterin *hh:mm:ss.fff* muodossa.  | `"23:12:49.000"` |
| **Tietue** | Pilkuin erotettu luettelo välillä **{** ja **}** , kentät ja niiden arvojen. Tämä merkintä muistuttaa tietueet pohjaan perustuvat sovellukset, mutta nimi on aina lainausmerkeissä. Tätä muotoa ei tue tietueet, jotka perustuvat monta yhteen-suhteita.  | `{ "First Name": "Fred"; "Age": 21 }` |
| **Taulukko** | Pilkuin erotettu luettelo välillä **[** ja **]** , tietueet. Tätä muotoa ei tue taulukoita, jotka perustuvat yksi-moneen-suhteita.  | `[ { "First Name": "Fred"; "Age": 21 }; { "First Name": "Jean"; "Age": 20 } ]` |
| **Kaksi&nbsp;vaihtoehto** | Kaksi vaihtoehtoa totuusarvo *true* tai *false*, ei otsikko, jota käytetään näyttämistä varten. Looginen arvo käytetään, koska se on riippumaton kieli. | `false` |
| **Hyperlinkin, teksti** | Merkkijono lainausmerkeissä. Funktio escapes upotetun lainausmerkit kenoviivalla, korvaa newlines ”\n” ja tekee muita standard JavaScript-korvausta. | `"This is a string."` |

Määritä valinnainen *muodossa* argumentti hallita, miten luettavissa tulos on ja miten ei tueta ja binary-tietotyypit käsitellään. Oletusarvon mukaan tulos on mahdollisimman tarpeettomia välilyöntejä tai newlines compact ja ei-tuettu tietotyyppejä ja binaaritiedot ei sallita. Voit yhdistää useita muotoja, jos määrität **&** operaattori.

| JSONFormat enum | Kuvaus |
|-----------------|-------------|
| **CD** | Oletus.  Tulos on mahdollisimman lisätty välilyöntejä tai newlines compact. |
| **IndentFour** | Voit parantaa luettavuutta tulos sisältää newline jokaiselle sarakkeelle ja sisäkkäisyystaso ja käyttää neljä välilyönnit jokaisen sisennystaso. |
| **IncludeBinaryData** | Tulos sisältää kuvan, videon ja äänen ClipArt-saraketta. Tätä muotoa huomattavasti kasvattaa tulosten koko ja heikentää sovelluksesi suorituskykyä. |
| **IgnoreBinaryData** | Tulos ei sisällä kuva, video tai ääni ClipArt-sarakkeita. Jos määrität ei kumpaakaan **IncludeBinaryData** tai **IgnoreBinaryData**, funktio antaa tulokseksi virheen, jos se havaitsee binaaritiedot. |
| **IgnoreUnsupportedTypes** | Ei-tuettu tietojen tyypit ovat sallittuja, mutta tulos ei sisällyttää ne. Oletusarvon mukaan ei tueta tietotyypit muodostavat virhe. |

Käytä [ **ShowColumns** ja **DropColumns** ](function-table-shaping.md) Funktiot voit hallita mitä tulos sisältää tietoja ja poistaa tietotyyppejä ei tueta.

Koska **JSON** voi olla muistin ja kuluttaa, voit käyttää tätä funktiota vain [toiminta funktiot](../working-with-formulas-in-depth.md). Voit siepata tulos **JSON** tietoja [muuttujan](../working-with-variables.md), joita voit sitten käyttää tietoja työnkulussa.

Jos sarake on näyttönimi ja looginen nimi, tulos on looginen nimi. Nimet vastaavat kieltä sovelluksen käyttäjälle ja on siksi sovellu tiedonsiirto common-palveluun.

## <a name="syntax"></a>Syntaksi

**JSON**( *DataStructure* [; *muodossa* ])

* *DataStructure* – pakollinen. Muunnettava JSON-tietorakenne.  Taulukoiden, tietueita ja primitiivi arvoja tuetaan, satunnaisia sisäkkäin.
* *Muotoile* – valinnainen.  **JSONFormat** luettelointiarvo. Oletusarvo on **Compact**, joka ei lisää newlines tai välilyöntejä ja estää binaaritiedot ja sarakkeita ei tueta.

## <a name="examples"></a>Esimerkkejä

### <a name="hierarchical-data"></a>Hierarkkiset tiedot

1. Lisää [ **painike** ](../controls/control-button.md) ohjausobjekti ja määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava.

    ```powerapps-comma
    ClearCollect( CityPopulations;
        { City: "London";    Country: "United Kingdom"; Population: 8615000 };
        { City: "Berlin";    Country: "Germany";        Population: 3562000 };
        { City: "Madrid";    Country: "Spain";          Population: 3165000 };
        { City: "Hamburg";   Country: "Germany";        Population: 1760000 };
        { City: "Barcelona"; Country: "Spain";          Population: 1602000 };
        { City: "Munich";    Country: "Germany";        Population: 1494000 }
    );;
    ClearCollect( CitiesByCountry; GroupBy( CityPopulations; "Country"; "Cities" ) )
    ```

1. Valitse painike, kun pidät alhaalla Alt-näppäintä.

    **Kaupungitmaittain** tietorakenne, jossa voit näyttää valitsemalla luodaan kokoelma **kokoelmat** - **tiedoston** valikosta ja valitsemalla sitten nimi kokoelma.

    > [!div class="mx-imgBorder"]
    > ![Kaupungitmaittain kokoelma](media/function-json/cities-grouped.png)

    Voit myös näyttää Tämä kokoelma valitsemalla **tiedoston** > **sovellusasetukset** > **lisäasetukset**  >   **Ota käyttöön kaavarivin tulosnäkymään**, valitsemalla kaavarivin luotavan kokoelman nimeä ja valitsemalla sitten kaavariville-kokoelman nimi viereistä alaspäin osoittavaa nuolta.

    > [!div class="mx-imgBorder"]
    > ![Kokoelman oletuskaava kaavarivillä tulosnäkymään](media/function-json/cities-grouped-resultview.png)

1. Lisää toinen painike ja määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Set( CitiesByCountryJSON; JSON( CitiesByCountry ) )
    ```

    Tämä kaava määrittää yleisen muuttujan **CitiesByCountryJSON** -for JSON-esityksen **Kaupungitmaittain**.

1. Valitse painike, kun pidät alhaalla Alt-näppäintä.

1. Lisää [ **nimen** ](../controls/control-text-box.md) ohjausobjekti ja määritä sen **tekstin** -ominaisuuden arvoksi tämä muuttujaa.

    ```powerapps-comma
    CitiesByCountryJSON
    ```

    Selite näyttää tämän tuloksen kaikki yhdellä rivillä ilman välilyöntejä, sopivan toimittamiseen verkon kautta:

    ```json
    [{"Cities":[{"City":"London","Population":8615000}],"Country":"United Kingdom"},{"Cities":[{"City":"Berlin","Population":3562000},{"City":"Hamburg","Population":1760000},{"City":"Munich","Population":1494000}],"Country":"Germany"},{"Cities":[{"City":"Madrid","Population":3165000},{"City":"Barcelona","Population":1602000}],"Country":"Spain"}]
    ```

1. Muuta toista painiketta kaava tulos helpommin luettavan.

    ```powerapps-comma
    Set( CitiesByCountryJSON; JSON(CitiesByCountry; JSONFormat.IndentFour ))
    ```

1. Valitse toinen painike, kun pidät alhaalla Alt-näppäintä.

    Selite näyttää helpommin luettavan tuloksen.

    ```json
    [
        {
            "Cities": [
                {
                    "City": "London",
                    "Population": 8615000
                }
            ],
            "Country": "United Kingdom"
        },
        {
            "Cities": [
                {
                    "City": "Berlin",
                    "Population": 3562000
                },
                {
                    "City": "Hamburg",
                    "Population": 1760000
                },
                {
                    "City": "Munich",
                    "Population": 1494000
                }
            ],
            "Country": "Germany"
        },
        {
            "Cities": [
                {
                    "City": "Madrid",
                    "Population": 3165000
                },
                {
                    "City": "Barcelona",
                    "Population": 1602000
                }
            ],
            "Country": "Spain"
        }
    ]
    ```

### <a name="images-and-media-in-base64"></a>Kuvien ja Base64 media

1. Lisää [ **kuvan** ](../controls/control-image.md) ohjausobjektin.

    Tämän ohjausobjektin tuo **SampleImage** sitä.

1. Lisää [ **painike** ](../controls/control-button.md) ohjausobjekti ja määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava.

    ```powerapps-comma
    Set( ImageJSON; JSON( SampleImage; JSONFormat.IncludeBinaryData ) )
    ```

1. Valitse painike, kun pidät alhaalla Alt-näppäintä.

1. Lisää selite ja aseta sen **tekstin** -ominaisuuden arvoksi tämä muuttujaa.

    ```powerapps-comma
    ImageJSON
    ```

1. Muuta ohjausobjektin kokoa ja Pienennä fonttikokoa näyttämään eniten tuloksen tarvittaessa.

    Selite näyttää merkkijono, joka **JSON** siepattu funktio.

    ```json
    "data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4NCjxzdmcgdmVyc2lvbj0iMS4xIg0KCSB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB4bWxuczphPSJodHRwOi8vbnMuYWRvYmUuY29tL0Fkb2JlU1ZHVmlld2VyRXh0ZW5zaW9ucy8zLjAvIg0KCSB4PSIwcHgiIHk9IjBweCIgd2lkdGg9IjI3MHB4IiBoZWlnaHQ9IjI3MHB4IiBlbmFibGUtYmFja2dyb3VuZD0ibmV3IDAgMCAyNzAgMjcwIiB4bWw6c3BhY2U9InByZXNlcnZlIj4NCgk8ZyBjbGFzcz0ic3QwIj4NCgkJPHJlY3QgeT0iMC43IiBmaWxsPSIjRTlFOUU5IiB3aWR0aD0iMjY5IiBoZWlnaHQ9IjI2OS4zIi8+DQoJCTxwb2x5Z29uIGZpbGw9IiNDQkNCQ0EiIHBvaW50cz0iMjc3LjksMTg3LjEgMjQ1LDE0My40IDE4OC42LDIwMi44IDc1LDgwLjUgLTQuMSwxNjUuMyAtNC4xLDI3MiAyNzcuOSwyNzIiLz4NCgkJPGVsbGlwc2UgZmlsbD0iI0NCQ0JDQSIgY3g9IjIwMi40IiBjeT0iODQuMSIgcng9IjI0LjQiIHJ5PSIyNC4zIi8+DQoJPC9nPg0KPC9zdmc+"
    ```

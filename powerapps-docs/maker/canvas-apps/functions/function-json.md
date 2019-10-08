---
title: JSON-Funktiot | Microsoft Docs
description: Powerappsin JSON-funktioiden viite tiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/02/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ba852093da05c3fa69cc47b219a0bef65908c170
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992633"
ms.PowerAppsDecimalTransform: true
---
# <a name="json-function-in-powerapps"></a>JSON-Funktiot Powerappsissa

Luo JSON-teksti merkki jonon taulukolle, tietueelle tai arvolle.

## <a name="description"></a>Kuvaus

**JSON** -funktio palauttaa tieto rakenteen JavaScript Object Notation (JSON)-esityksen tekstinä, jotta se sopii tietojen tallentamiseen tai välittämiseen verkon kautta. [ECMA-404](http://www.ecma-international.org/publications/files/ECMA-ST/ECMA-404.pdf) ja [ietf RFC 8259](https://tools.ietf.org/html/rfc8259) kuvailevat muotoa, jota JavaScript ja muut Ohjelmointi Kielet käyttävät laajalti.

Pohjaan liittyvät sovellukset tukevat [tieto tyyppejä](data-types.md) , jotka tässä taulukossa luetellaan, ja niiden tekstin esitys tiedot:

| Tietotyyppi | Kuvaus | Tulos esimerkki |
|-----------|-------------|---------|
| **Totuus arvo** | *True* tai *false*. | `true` |
| **Väri** | Merkki jono, joka sisältää värin kahdeksannumeroisen heksa desimaali esityksen. Tämä esitys kestää muotoa #*rrggbbaa*, jossa *RR* on punainen osa, *GG* on vihreä, *BB* on sininen ja *aa* on alfa kanava. Alpha-kanavalla **00** on täysin läpinäkyvä, ja **FF** on täysin läpinäkymätön. Voit välittää merkki jonon [**Colorvalue**](function-colors.md) -funktiolla.  | `"#102030ff"` |
| **Valuutta** | Luku, joka käyttää asianmukaista desimaalimuotoerotinta käyttäjän kielelle. Tieteellistä merkintää käytetään tarvittaessa. | `1,345` |
| **Päivä määrä** | Merkki jono, joka sisältää päivä määrän ISO 8601 **VVVV-KK-PP** -formaatissa. | `"2019-03-31"` |
| **DateTime** | Merkki jono, joka sisältää ISO 8601-päivä määrän/-kellon ajan. Päivä määrä-ja aika-arvot ovat UTC-muodossa, kun loppu merkki "Z" ilmaisee.  | `"2019-03-31T22:32:06.822Z"`  |
| **GUID** | Merkki jono, joka sisältää GUID-arvon. Kirjaimet ovat pieniä kirjaimia. | `"751b58ac-380e-4a04-a925-9f375995cc40"`
| **Kuva, tieto väline** | Jos **Includebinarydata** on määritetty, tieto väline tiedostot koodataan merkki jonossa. Http:-tai https-verkko viittauksia käyttävät verkko viittaukset: URL-rakennetta ei ole muokattu. Viitta ukset muistissa oleviin binaaritietotietoihin koodataan ["Data:*MimeType*; Base64,..."](https://en.wikipedia.org/wiki/Data_URI_scheme) -muodossa. Muistissa olevat tiedot sisältävät kuvia, jotka käyttäjät sieppaamaan käyttämällä [**kamera**](../controls/control-camera.md) -ohjaus objektia ja muita viitta uksia Appsin: ja BLOB-objektien kanssa: URL-mallit.| `"data:image/jpeg;base64,/9j/4AA..."` |
| **Numero** | Luku, joka käyttää asianmukaista desimaalimuotoerotinta käyttäjän kielelle. Tieteellistä merkintää käytetään tarvittaessa. | `1,345` |
| **Vaihto ehto @ no__t-1asetus** | Asetus joukon luku arvo, ei näyttämisessä käytettävä otsikko. Numero-arvoa käytetään, koska se on kielestä riippumaton.  | `1001` |
| **Aika** | Merkki jono, joka sisältää ISO 8601 *hh:mm: SS. FFF-* muodon.  | `"23:12:49.000"` |
| **Tietue** | Pilkuilla eroteltu luettelo, joka on **{** – **}** kenttien ja niiden arvojen välillä. Tämä merkitsemis tapa muistuttaa, että kangas sovelluksissa on tietue, mutta nimi on aina lainaus merkeissä. Tämä muoto ei tue tietueita, jotka perustuvat moneen-yhteen-suhteisiin.  | `{ "First Name": "Fred"; "Age": 21 }` |
| **Taulukon** | Pilkuilla eroteltu luettelo tietueiden välillä **[** ja **]** . Tämä muoto ei tue taulu koita, jotka perustuvat yhteen moneen-suhteisiin.  | `[ { "First Name": "Fred"; "Age": 21 }; { "First Name": "Jean"; "Age": 20 } ]` |
| **Kaksi @ no__t-1option** | Kahden asetuksen totuus arvo, *tosi* tai *Epätosi*, ei näytettävä otsikko. Totuus arvoa käytetään, koska se on kielestä riippumaton. | `false` |
| **Hyperlinkki, teksti** | Merkki jono lainaus merkkien välissä. Funktio poistuu upotetuista lainaus merkeistä, joilla on Keno viiva, korvaa rivin vaihdot-kohteen "\n" ja tekee muita JavaScript-vakio korvaavia. | `"This is a string."` |

Määritä valinnainen *muoto* -argumentti, joka määrittää, miten lukukelpoinen tulos on ja miten tuettuja ja binaaritietotyyppejä käsitellään. Oletus arvon mukaan tuloste on mahdollisimman pienikokoinen ilman tarpeettomia väli lyöntejä tai rivin vaihtoja, eikä tieto tyyppejä, joita ei tueta, ja binaaritiedot eivät ole sallittuja. Voit yhdistää useita muotoiluja, jos määrität **&-** operaattorin.

| JSONFormat-luettelointi | Kuvaus |
|-----------------|-------------|
| **Compact** | Oletus.  Tuloste on mahdollisimman pienikokoinen ilman lisättyjä välejä tai rivin vaihtoja. |
| **IndentFour** | Luettavuuden parantamiseksi tuloste sisältää NewLine-arvon kullekin sarakkeelle ja sisäkkäisyys tasolle ja käyttää neljää väli lyöntiä kullekin sisennys tasolle. |
| **IncludeBinaryData** | Tulos sisältää kuva-, video-ja ääni leike sarakkeet. Tämä muoto voi merkittävästi suurentaa tuloksen kokoa ja heikentää sovelluksesi suoritus tehoa. |
| **IgnoreBinaryData** | Tulos ei sisällä kuva-, video-tai ääni leike sarakkeita. Jos määrität kumpaakaan **Includebinarydata** -tai **Ignorebinarydata**-arvoa, funktiolla syntyy virhe, jos se havaitsee binaaritietoja. |
| **Ei Ignoneusupportedtypes** | Tieto tyyppejä, joita ei tueta, sallitaan, mutta tulos ei sisällä niitä. Oletus arvon mukaan tieto tyypit, joita ei tueta, tuottavat virheen. |

[ **Showcolumns** -ja **dropcolumns** ](function-table-shaping.md) -funktioiden avulla voit määrittää, mitä tietoja tulos sisältää ja poistaa tieto tyyppejä, joita ei tueta.

Koska **JSON** voi olla sekä muisti-että käsittely teho, voit käyttää tätä funktiota vain [toiminta funktioissa](../working-with-formulas-in-depth.md). Voit siepata **JSON** -tuloksen [muuttujaan](../working-with-variables.md), jota voit käyttää tieto kulussa.

Jos sarakkeella on sekä näyttö nimi että looginen nimi, tulos sisältää loogisen nimen. Näyttö nimet vastaavat sovelluksen käyttäjän kieltä, joten ne eivät sovellu common Service-palvelun tietojen siirtämiseen.

## <a name="syntax"></a>Syntaksi

**JSON**( *datastructure* [; *muoto* ])

* *Datastructure* – pakollinen. JSON-muotoon muunnettava tieto rakenne.  Taulu koita, tietueita ja primitiivisiä arvoja tuetaan mielivaltaisesti sisäkkäin.
* *Muoto* – valinnainen.  **Jsonformat** -luettelointi arvo. Oletus arvo on **Compact**, joka ei lisää rivin vaihtoja tai välejä, ja estää binaaritiedot ja sarakkeet, joita ei tueta.

## <a name="examples"></a>Esimerkkejä

### <a name="hierarchical-data"></a>Hierarkkinen tieto

1. Lisää [**painike**](../controls/control-button.md) -ohjaus objekti ja määritä sen **onselect** -ominaisuudeksi Tämä kaava.

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

1. Valitse painike pitäen Alt-näppäintä painettuna.

    **Citiesbycountry** -kokoelma luodaan käyttäen tätä tieto rakennetta, joka voidaan näyttää valitsemalla **tiedosto-** valikosta **kokoelmat** ja valitsemalla sitten kokoelman nimi.

    > [!div class="mx-imgBorder"]
    > ![CitiesByCountry-kokoelma @ no__t-1

    Voit myös näyttää tämän kokoelman valitsemalla **tiedosto** > **sovellus asetukset** > **lisä asetukset** > **Ota käyttöön kaava rivin tulos näkymä**, valitse kokoelman nimi kaava rivillä ja valitse sitten kaava rivin alla olevan kokoelman nimen vieressä oleva alanuoli.

    > [!div class="mx-imgBorder"]
    > ![Collection kaava rivin tulos näkymässä @ no__t-1

1. Lisää toinen painike ja määritä sen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Set( CitiesByCountryJSON; JSON( CitiesByCountry ) )
    ```

    Tämä kaava määrittää yleisen muuttuja **citiesbycountryjson** -kohteen **citiesbycountry**-kohteen JSON-edustukseen.

1. Valitse painike pitäen Alt-näppäintä painettuna.

1. Lisää [**Selite**](../controls/control-text-box.md) -ohjaus objekti ja aseta sen **Text** -ominaisuudeksi Tämä muuttuja.

    ```powerapps-comma
    CitiesByCountryJSON
    ```

    Selite esittää tämän tuloksen, kaikki yhdellä rivillä ilman väli lyöntejä, jotka soveltuvat verkossa tapahtuvaan siirtoon:

    ```json
    [{"Cities":[{"City":"London","Population":8615000}],"Country":"United Kingdom"},{"Cities":[{"City":"Berlin","Population":3562000},{"City":"Hamburg","Population":1760000},{"City":"Munich","Population":1494000}],"Country":"Germany"},{"Cities":[{"City":"Madrid","Population":3165000},{"City":"Barcelona","Population":1602000}],"Country":"Spain"}]
    ```

1. Muuta toisen painikkeen kaavaa niin, että tuloste on helpommin luettavissa.

    ```powerapps-comma
    Set( CitiesByCountryJSON; JSON(CitiesByCountry; JSONFormat.IndentFour ))
    ```

1. Valitse toinen painike pitäen Alt-näppäintä painettuna.

    Selite sisältää luettavuuden lisä tuloksen.

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

### <a name="images-and-media-in-base64"></a>Kuvat ja tieto väline Base64

1. Lisää [**kuva**](../controls/control-image.md) -ohjaus objekti.

    Tämä ohjaus objekti tuo **Sampleimage** -kohteen sen kanssa.

1. Lisää [**painike**](../controls/control-button.md) -ohjaus objekti ja määritä sen **onselect** -ominaisuudeksi Tämä kaava.

    ```powerapps-comma
    Set( ImageJSON; JSON( SampleImage; JSONFormat.IncludeBinaryData ) )
    ```

1. Valitse painike pitäen Alt-näppäintä painettuna.

1. Lisää selite ja muuta sen **teksti** -ominaisuudeksi Tämä muuttuja.

    ```powerapps-comma
    ImageJSON
    ```

1. Muuta ohjaus objektin kokoa ja pienennä fontin kokoa tarpeen mukaan suurimman tuloksen näyttämiseksi.

    Nimi ilmaisee **JSON** -funktiolla siepatun teksti merkki jonon.

    ```json
    "data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4NCjxzdmcgdmVyc2lvbj0iMS4xIg0KCSB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB4bWxuczphPSJodHRwOi8vbnMuYWRvYmUuY29tL0Fkb2JlU1ZHVmlld2VyRXh0ZW5zaW9ucy8zLjAvIg0KCSB4PSIwcHgiIHk9IjBweCIgd2lkdGg9IjI3MHB4IiBoZWlnaHQ9IjI3MHB4IiBlbmFibGUtYmFja2dyb3VuZD0ibmV3IDAgMCAyNzAgMjcwIiB4bWw6c3BhY2U9InByZXNlcnZlIj4NCgk8ZyBjbGFzcz0ic3QwIj4NCgkJPHJlY3QgeT0iMC43IiBmaWxsPSIjRTlFOUU5IiB3aWR0aD0iMjY5IiBoZWlnaHQ9IjI2OS4zIi8+DQoJCTxwb2x5Z29uIGZpbGw9IiNDQkNCQ0EiIHBvaW50cz0iMjc3LjksMTg3LjEgMjQ1LDE0My40IDE4OC42LDIwMi44IDc1LDgwLjUgLTQuMSwxNjUuMyAtNC4xLDI3MiAyNzcuOSwyNzIiLz4NCgkJPGVsbGlwc2UgZmlsbD0iI0NCQ0JDQSIgY3g9IjIwMi40IiBjeT0iODQuMSIgcng9IjI0LjQiIHJ5PSIyNC4zIi8+DQoJPC9nPg0KPC9zdmc+"
    ```

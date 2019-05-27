---
title: Text-funktio | Microsoft Docs
description: Tietoja PowerAppsin Text-funktiosta, kuten syntaksi ja joitakin esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/14/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 67c0e83245b60345f74912f2f005295c94cc0dd1
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/24/2019
ms.locfileid: "66215944"
---
# <a name="text-function-in-powerapps"></a>PowerAppsin Text-funktio
Muuntaa mitään arvoa ja alustaa tekstimerkkijonon numeron tai päivämäärän/ajan arvo.

## <a name="description"></a>Kuvaus
**Text**-funktio soveltaa numeron tai päivämäärän/kellonajan muotoiluun jotain seuraavan tyyppisistä argumenteista:

* Ennalta määritetty päivämäärän/kellonajan esitystapa, jonka voit määrittää käyttämällä **DateTimeFormat**-luettelointia. Päivämäärien ja kellonaikojen Tämä lähestymistapa on ensisijainen, koska se mukautuu automaattisesti kunkin käyttäjän kielen ja alueen.
* Mukautettua muotoa, joka sisältää merkkijonon paikkamerkkejä, jotka määrittävät esimerkiksi onko luvut Näytä desimaalierottimena ja päivämäärät näyttää kuukauden lyhenteenä kuukauden ja kuukauden lukuna koko nimi. PowerApps tukee samaa paikkamerkkien osajoukkoa, jota Microsoft Excel käyttää. Tämä merkkijono kielen paikkamerkki määrittää kielen, jonka muut paikkamerkit tulkita. Jos mukautettu muoto on piste, esimerkiksi kielen muodossa paikkamerkin määrittää jakso desimaalierottimena (ja-JP) vai tuhaterottimen separator (es-ES).

Lisätietoja on kohdassa [Päivämäärien ja kellonaikojen käsitteleminen](../show-text-dates-times.md).

**Tekstin** funktio muuntaa myös mille tahansa tietotyypille tekstin esityksen default-muodossa. Tämän avulla voit välittää teksti-arvot tekstipohjainen Funktiot, kuten [ **Len**](function-len.md), [ **oikealle**](function-left-mid-right.md), ja [  **IsMatch**](function-ismatch.md).

### <a name="predefined-datetime-formats"></a> Ennalta määritetyt päivämäärän ja kellonajan muotoilut

| Ennalta määritetty muotoilu | Kuvaus |
| --- | --- |
| **DateTimeFormat.LongDate** |Koko vuosi, kuukausi, kuukauden päivä ja viikonpäivä. Kuukausien nimiä ja viikonpäiviä ei lyhennetä. |
| **DateTimeFormat.LongDateTime** |Koko vuosi, kuukausi, kuukauden päivä, viikonpäivä sekä tunnit (12 tunnin kello), minuutit, sekunnit ja AM/PM-merkintä. Kuukausien nimiä ja viikonpäiviä ei lyhennetä. |
| **DateTimeFormat.LongDateTime24** |Koko vuosi, kuukausi, kuukauden päivä, viikonpäivä sekä tunnit (24 tunnin kello), minuutit ja sekunnit. Kuukausien nimiä ja viikonpäiviä ei lyhennetä. |
| **DateTimeFormat.LongTime** |Tunnit (12 tunnin kello), minuutit, sekunnit ja AM/PM. Sama kuin ShortTime. |
| **DateTimeFormat.LongTime24** |Tunnit (24 tunnin kello), minuutit, sekunnit. Sama kuin ShortTime24. |
| **DateTimeFormat.ShortDate** |Nelinumeroinen vuosiluku sekä kaksinumeroinen kuukausi ja kuukauden päivä. |
| **DateTimeFormat.ShortDateTime** |Nelinumeroinen vuosi, kaksinumeroinen kuukausi ja kuukauden päivä sekä tunnit (12 tunnin kello), minuutit, sekunnit ja AM/PM-merkintä. |
| **DateTimeFormat.ShortDateTime24** |Nelinumeroinen vuosi, kaksinumeroinen kuukausi ja kuukauden päivä sekä tunnit (24 tunnin kello), minuutit ja sekunnit. |
| **DateTimeFormat.ShortTime** |Tunnit (12 tunnin kello), minuutit, sekunnit ja AM/PM.  Sama kuin LongTime. |
| **DateTimeFormat.ShortTime24** |Tunnit (24 tunnin kello), minuutit ja sekunnit.  Sama kuin LongTime24. |
| **DateTimeFormat.UTC** |Päivämäärän ja kellonajan arvo muunnetaan UTC-arvoon nykyisen käyttäjän aikavyöhykkeen perusteella ja muotoillaan ISO 8601-standardin mukaisesti. |

### <a name="number-placeholders"></a>Luvun paikkamerkit

| Paikkamerkki | Kuvaus |
| --- | --- |
| **0** (*nolla*) |Näyttää merkityksettömät nollat, jos luvussa on vähemmän numeroita kuin muodossa nollia. Käytä esimerkiksi muotoa **#.00**, jos haluat näyttää luvun **8,9** muodossa **8,90**. |
| **#** |Noudattaa samoja sääntöjä kuin **0** (nolla). **Text**-funktio ei kuitenkaan palauta ylimääräisiä nollia, jos desimaalipilkun jommallakummalla puolella on numeroita vähemmän kuin muotoilussa on ristikkosymboleja (#). Esimerkiksi **8,9** näytetään, jos mukautettu muoto on **#.##** ja muotoiltava numero on **8,9**. |
| **.** (*piste*) |Näyttää luvun desimaalierottimen. Riippuu mukautetun muodon; kieli Katso [yleisiä sovelluksia](#global-apps) lisätietoja. |
| **,** (*pilkku*) |Näyttää ryhmittelyerottimen, jota joissakin kielissä käytetään tuhaterottimena. **Text**-funktio erottaa ryhmät pilkuilla, jos muotoilussa on ristikkomerkkien ( **#** ) tai nollien sisällä oleva pilkku. Riippuu mukautetun muodon; kieli Katso [yleisiä sovelluksia](#global-apps) lisätietoja. |

Jos desimaalipilkun oikealla puolella on enemmän numeroita kuin muodossa on paikkamerkkejä, luku pyöristetään niin moneen desimaaliin kuin muodossa on paikkamerkkejä. Jos desimaalipilkun vasemmalla puolella on enemmän numeroita kuin muodossa on paikkamerkkejä, ylimääräiset numerot näytetään. Jos desimaalipilkun vasemmalla puolella on vain ristikkomerkkejä (#), lukua 1 pienemmän arvot alkavat desimaalipilkulla (esimerkiksi **,47**).

### <a name="date-and-time-placeholders"></a>Päivämäärän ja kellonajan paikkamerkit

|   Paikkamerkki    |   Kuvaus                                                  |
|------------------|----------------------------------------------------------------|
|  **m**   |   Näyttää kuukauden lukuna ilman ensimmäistä nollaa.               |
|  **mm**  |   Näyttää kuukauden lukuna ja käyttää tarvittaessa ensimmäistä nollaa. |
|  **mmm** |   Näyttää kuukauden lyhenteenä (**tam**...**jou**).          |
|                                                                                                   **mmmm**                                                                                                   |                                                                          Näyttää kuukauden koko nimen (**tammikuu**...**joulukuu**).                                                                           |
|                                                                                                    **d**                                                                                                     |                                                                                Näyttää kuukauden päivän ilman ensimmäistä nollaa.                                                                                 |
|                                                                                                    **dd**                                                                                                    |                                                                         Näyttää kuukauden päivän lukuna ja käyttää tarvittaessa ensimmäistä nollaa.                                                                          |
|                                                                                                   **ddd**                                                                                                    |                                                                              Näyttää päivän lyhenteenä (**su**...**la**).                                                                              |
|                                                                                                   **dddd**                                                                                                   |                                                                            Näyttää päivän koko nimen (**sunnuntai**...**lauantai**).                                                                            |
|                                                                                                    **yy**                                                                                                    |                                                                                      Näyttää vuoden kaksinumeroisena lukuna.                                                                                       |
|                                                                                                   **yyyy**                                                                                                   |                                                                                      Näyttää vuoden nelinumeroisena lukuna.                                                                                      |
|                                                                                                    **h**                                                                                                     |                                                                                Näyttää tunnit ilman ensimmäistä nollaa.                                                                                |
|   **hh** | Näyttää tunnit lukuna ja käyttää tarvittaessa ensimmäistä nollaa. Jos muotoiluun sisältyy **AM** tai **PM**, aika näkyy 12 tunnin mukaan. Muussa tapauksessa aika näytetään 24 tunnin mukaan. | 
|  **m**   |   Näyttää minuutit lukuna ilman ensimmäistä nollaa.<br><br>Tämän paikkamerkin on oltava heti **h** tai **hh** koodi tai heti ennen **ss** koodia; muussa tapauksessa **tekstin** palauttaa kuukauden minuuttien sijaan.  |    
| **mm**   | Näyttää minuutit lukuna ja käyttää tarvittaessa ensimmäistä nollaa.<br><br>Tämän paikkamerkin on oltava heti **h** tai **hh** paikkamerkki tai heti ennen **ss** paikkamerkki. Muussa tapauksessa **tekstin** palauttaa kuukauden minuuttien sijaan. |                                                                                                                   
| **s**   |  Näyttää sekunnin lukuna ilman ensimmäistä nollaa.  |
| **ss**  | Näyttää sekunnit lukuna ja käyttää tarvittaessa ensimmäistä nollaa.                                                                        |
|                                                                                                    **f**                                                                                                     |                                                                                         Näyttää sekunnin murto-osat.                                                                                          |
|                                                                                    **AM/PM**, **/ p**                                                                                    |               Näyttää ajan 12 tunnin kellon perusteella. **Tekstin** palauttaa ”AM” tai ”a” kertaa keskiyöstä keskipäivään ja ”PM” tai ”p” keskipäivästä keskiyöhön                |

### <a name="literal-placeholders"></a>Literaalit paikkamerkit
Voit sisällyttää muotoilumerkkijonoon seuraavia merkkejä.  Ne näkyvät **Text**-funktion tuloksessa sellaisenaan. Muita merkkejä varataan tulevia paikkamerkkejä varten, joten niitä ei kannata käyttää.

| Merkki | Kuvaus |
| --- | --- |
| Kaikki valuuttasymbolit |Dollarin, sentin, euron merkit jne. |
| **+** |Plusmerkki |
| **(** |Vasen sulkumerkki |
| **:** |Kaksoispiste |
| **^** |Sirkumfleksi |
| **'** |Heittomerkki |
| **{** |Vasen aaltosulje |
| **<** |Pienempi kuin -merkki |
| **=** |Yhtäläisyysmerkki |
| **-** |Miinusmerkki |
| **/** |Vinoviiva |
| **)** |Oikea sulkumerkki |
| **&** |Et-merkki |
| **~** |Aaltoviiva |
| **}** |Oikea aaltosulje |
| **>** |Suurempi kuin -merkki |
| &nbsp; |Välilyönti |

## <a name="global-apps"></a>Yleiset sovellukset
**Text**-funktio on maailmanlaajuinen. Se tuntee suuren määrän kieliä ja osaa kirjoittaa päivämäärät, kellonajat, valuutat ja numerot kielen mukaan. Onnistuakseen tässä se tarvitsee seuraavat kaksi tietoa:

* **Mukautetun muotoilun kielen:** Tekijöille miten mukautettu muoto tulkitaan tekstin laatijaa? Erotinmerkeillä ( **.** ja **,** ) on eri kielissä eri merkitykset. Jos määrität mukautettua muotoa, voit sisällyttää kielen paikkamerkki tai kestää oletusarvo, joka vastaa sitä kohtaa, johon laitettasi määritetään kielen. Helpottuu, voit käyttää jotakin [ennalta määritettyjä päivämäärän ja kellonajan muotoilut](#predefined-datetime-formats), jotka ovat kieliagnostisia kielen.
* **Tuloksen kieli:** Käyttäjille millä kielellä funktion tulos näkyä? Kuukausien ja viikonpäivien nimet on oltava sovellus, jonka voit määrittää lisäämällä kolmas Valinnainen argumentti käyttäjän kielen mukaisiksi **tekstin** funktio. 

Kumpikin kieli määrittää käyttämällä [kielitunnisteen](function-language.md#language-tags). Voit tarkastella tuettujen kielten luettelo kirjoittamalla **Text (1234 ”,”,)** kaavarivillä tai **lisäasetukset** välilehti oikeanpuoleisessa ruudussa ja sitten selaamalla argumenttiin ehdotettuja kieliasetuksia kolmas argumentti.

### <a name="language-placeholder"></a>Kielen paikkamerkki
Voit käyttää mukautetun muotoilun kielen määrittämiseen seuraavia:

| Paikkamerkki | Kuvaus |
| --- | --- |
| **[$-*LanguageTag*]** |*LanguageTag* on **Language**-funktion palauttama kielitunniste. Se määrittää vain (kuten **[$-en]** englanti), tai se määrittää myös alueella (kuten **[$-en-GB]** -tarkentava aluetunnus). |

Kielen paikkamerkki voi esiintyä missä tahansa kohdassa mukautettavaa muotoilua, mutta vain kerran.

Jos määrität mukautettua muotoa ilman kielen paikkamerkki ja muoto on yleinen epäselvä, nykyisen kielen kielitunnisteen lisätään automaattisesti.  

**[$-en-US]**  oletetaan, jos tämän paikkamerkin ei ole olemassa, kun sovellus suoritetaan. 

> [!NOTE]
> Tulevassa versiossa tämän paikkamerkin syntaksi voi muuttua välttää paikkamerkillä mutta erilainen, joka tukee Excel.

### <a name="result-language-tag"></a>Tuloksen kielitunniste
Tuloksen **tekstin** sisältää kuukausien, arkipäivät, ja AM/PM, ryhmityserottaja sekä sopivaan ryhmään ja desimaalimerkki käännetyt merkkijonot.

Oletusmuotoisesti **Text**-funktio käyttää sitä kieltä, jota sovelluksessa parhaillaan käytetään. **Language**-funktio palauttaa nykyisen käyttäjän kielitunnisteen. Voit ohittaa tämän oletusarvon antamalla kolmannen argumentin kielitunnisteen **tekstin**.

## <a name="syntax"></a>Syntaksi
**Tekstin**( *NumberOrDateTime*, *DateTimeFormatEnum* [, *ResultLanguageTag* ])

* *NumberOrDateTime* – pakollinen. Muotoiltava numero tai päivämäärä/kellonaika.
* *DateTimeFormat* – Pakollinen.  **DateTimeFormat** – Luetteloinnin osa.
* *ResultLanguageTag* – Valinnainen. Kielitunniste, jota käytetään tulostekstiin. Oletusmuotoisesti käytetään nykyisen käyttäjän kieltä.

**Tekstin**( *NumberOrDateTime*, *CustomFormat* [, *ResultLanguageTag* ])

* *Number* – pakollinen. Muotoiltava numero tai päivämäärä/kellonaika.
* *CustomFormat* – pakollinen. Yksi tai useampi paikkamerkki lainausmerkkien sisällä.
* *ResultLanguageTag* – Valinnainen. Kielitunniste, jota käytetään tulostekstiin. Oletusmuotoisesti käytetään nykyisen käyttäjän kieltä.

**Tekstin**( *AnyValue* )

* *AnyValue* – pakollinen. Tekstin esityksen muunnettava arvo. Default-muotoa käytetään.

## <a name="examples"></a>Esimerkkejä
Ellei toisin mainita suorittaa nämä kaavat käyttäjä sijaitsee Yhdysvalloissa ja on valinnut kielekseen englannin kielellä.  **Language**-funktio palauttaa tuloksen "en-US".

### <a name="number"></a>Luku

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Text(&nbsp;1234.59,&nbsp;"####.#"&nbsp;)** |Muotoilee luvun yhden desimaalin tarkkuudella. |"1234.6" |
| **Text(&nbsp;8.9,&nbsp;"#.000"&nbsp;)** |Lisää tarvittaessa nollat numeron desimaaliosan loppuun. |"8.900" |
| **Text(&nbsp;0.631,&nbsp;"0.#"&nbsp;)** |Lisää tarvittaessa kokonaislukuun nollan. |"0.6" |
| **Text(&nbsp;12,&nbsp;"#.0#"&nbsp;)**<br>**Text(&nbsp;1234.568,&nbsp;"#.0#"&nbsp;)** |Lisää numeroon nollan yhden desimaalin tarkkuudella ja lisää toisen desimaalin, jos se syötetään. |"12.0"<br>"1234.57" |
| **Text(&nbsp;12000,&nbsp;"$ #,###"&nbsp;)**<br>**Text(&nbsp;1200000,&nbsp;"$&nbsp;#,###"&nbsp;)** |Sijoittaa lukuun kolmen numeron välein tuhaterottimen ja lisää valuuttasymbolin. |"$&nbsp;12,000"<br>"$&nbsp;1,200,000" |

### <a name="datetime"></a>Päivämäärä/kellonaika
* **2:37:47 PM**, **Monday, November 23, 2015**
* Yhdysvaltain Tyynenmeren aikavyöhyke (UTC-8)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Text( Now(), DateTimeFormat.LongDate )** |Päivämäärä pitkänä merkkijonona, käytössä olevan kielen mukaan esitettynä. |"Monday, November 23, 2015" |
| **Text( Now(), DateTimeFormat.LongDate )** |Päivämäärä pitkänä merkkijonona, käytössä olevan kielen mukaan esitettynä 12 tunnin mukaan. |"Monday, November 23, 2015 2:37:47 PM" |
| **Text( Now(), DateTimeFormat.LongTime24 )** |Päivämäärä pitkänä merkkijonona, käytössä olevan kielen mukaan esitettynä 24 tunnin mukaan. |"14:37:47" |
| **Text( Now(), DateTimeFormat.ShortDate )** |Päivämäärä lyhyenä merkkijonona, käytössä olevan kielen mukaan esitettynä. |"11/23/2015" |
| **Text( Now(), "d-mmm-yy" )** |Esitetään käyttämällä paikkamerkkejä: <ul><li>**d** – yksi- tai kaksinumeroinen kuukauden päivä<li>**-** – tulokseen kopioitu literaalimerkki<li>**mmm** – kolmikirjaiminen kuukauden lyhenne<li>**-** – toinen tulokseen kopioitu literaalimerkki<li>**yy** – vuosiluku kaksinumeroisena lyhenteenä</ul> |"23-Nov-15" |
| **Text (1448318857 * 1000, ”KKK. PP, vvvv (hh: mm: ss AM/PM) ”)** | On näytettävän muodossa Unix-aika-arvon, jos lähdearvo kerrotaan mukaan 1 000. | ”Nov. 23, 2015 (02:47:37 PM)” |

### <a name="global-apps"></a>Yleiset sovellukset

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Text (1234567.89 ”, [$-fr-FR] # ###, ## &euro;”, ”fr-FR”)** | Näyttää välilyönnin ryhmittely erottimena, jossa desimaalierottimena pilkuin ja **&euro;** ja valuuttasymbolina merkkiä. |"1&nbsp;234&nbsp;567,89 &euro;" |
| **Text (1234567,89; ”[$-fr-FR] # ###, ## &euro;”)** | Jos lähdetiedot noudattaa Ranskan mukautettu-käyttämällä desimaalierottimena, muuta Aluekohtaiset asetukset ranska ja argumentit erotetaan toisistaan puolipisteellä pilkku saman tuloksen kuin edellä sijaan. |"1&nbsp;234&nbsp;567,89 &euro;" |
| **Text( Date(2016,1,31), "dddd mmmm d" )** |Palauttaa viikonpäivän, kuukauden ja kuukauden päivän muotoiltuna nykyisen käyttäjän kielen mukaan. Koska paikkamerkit eivät ole kieleen sidottuja, tekstin muotoiluun ei tarvita kielitunnistetta. |”Lauantai&nbsp;tammikuu&nbsp;31” |
| **Text( Date(2016,1,31), "dddd mmmm d", "es-ES" )** |Palauttaa viikonpäivän, kuukauden ja kuukauden päivän kielitunnisteen "es-ES" mukaisesti. |”domingo&nbsp;enero nojalla&nbsp;31” |

### <a name="converting-values-to-text"></a>Arvojen muuntaminen teksti

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Text (&nbsp;1234567.89&nbsp;)** | Muuntaa merkkijonon luvuksi. Ei ole tuhaterottimen erottimet tai hallita ennen tai jälkeen desimaalierottimen; numeroiden määrä Lisää ohjausobjekti Anna luvun paikkamerkit toinen argumentti. | "1234567.89" |
| **Text(&nbsp;DateTimeValue(&nbsp;"01/04/2003"&nbsp;)&nbsp;)** | Muuntaa tekstimerkkijonon päivämäärä ja aika-arvoa. Hallita muuntaminen, anna joko DateTimeFormat-luetteloinnin jäsen tai mukautettu muotoilumerkkijono. | ”1/4/2003 12:00 AM” |
| **Text (&nbsp;true&nbsp;)** | Muuntaa merkkijonon totuusarvo. | "true" |
| **Text (&nbsp;GUID()&nbsp;)** | Muuntaa merkkijonon luotu GUID-arvon.  | "f8b10550-0f12-4f08-9aa3-bb10958bc3ff" |
| **Vasen (&nbsp;teksti (&nbsp;GUID()&nbsp;),&nbsp;4&nbsp;)** | Palauttaa ensimmäiset neljä merkkiä luotu GUID-tunnus. | "2d9c" | 

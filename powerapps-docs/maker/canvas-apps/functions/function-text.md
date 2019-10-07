---
title: Text-funktio | Microsoft Docs
description: Tietoja PowerAppsin Text-funktiosta, kuten syntaksi ja joitakin esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/14/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ac0291abababb807628fa224ba8292daf1064d23
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71991885"
---
# <a name="text-function-in-powerapps"></a>PowerAppsin Text-funktio
Muuntaa minkä tahansa arvon ja muotoilee luvun tai päivä määrä/aika-arvon teksti merkki jonoksi.

## <a name="description"></a>Kuvaus
**Text**-funktio soveltaa numeron tai päivämäärän/kellonajan muotoiluun jotain seuraavan tyyppisistä argumenteista:

* Ennalta määritetty päivämäärän/kellonajan esitystapa, jonka voit määrittää käyttämällä **DateTimeFormat**-luettelointia. Päivä määrien ja kellon aikojen osalta tätä lähestymis tapaa suositellaan, koska se mukautuu automaattisesti kunkin käyttäjän kieleen ja alueeseen.
* Mukautettu muoto, joka sisältää paikka merkkien merkki jonon, joka määrittää esimerkiksi sen, näytetäänkö luvuissa kymmen järjestelmä erotin, ja päivä määrät näyttävät kuukauden koko nimen, kuukauden lyhenteenä tai kuukauden lukuna. PowerApps tukee samaa paikkamerkkien osajoukkoa, jota Microsoft Excel käyttää. Tässä merkki jonossa kielen paikka merkki määrittää kielen, jolla muut paikka merkit tulkitaan. Jos mukautettu muoto sisältää pisteen, esimerkiksi Language-Format-paikka merkki määrittää, onko jakso kymmen järjestelmä erotin (ja-JP) vai tuhaterotin (ES-ES).

Lisätietoja on kohdassa [Päivämäärien ja kellonaikojen käsitteleminen](../show-text-dates-times.md).

**Text** -funktiolla voi myös muuntaa minkä tahansa tieto tyypin teksti esitykseksi käyttäen oletus muotoa. Tämän avulla voit välittää muita kuin teksti arvoja tekstipohjaisia funktioita, kuten [**len**](function-len.md), [**Right**](function-left-mid-right.md)ja [**onmatch**](function-ismatch.md).

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
| **.** (*piste*) |Näyttää luvun desimaalierottimen. Määräytyy mukautetun muodon kielen mukaan. lisä tietoja on Ohje aiheessa [Yleiset sovellukset](#global-apps) . |
| **,** (*pilkku*) |Näyttää ryhmittelyerottimen, jota joissakin kielissä käytetään tuhaterottimena. **Text**-funktio erottaa ryhmät pilkuilla, jos muotoilussa on ristikkomerkkien ( **#** ) tai nollien sisällä oleva pilkku. Määräytyy mukautetun muodon kielen mukaan. lisä tietoja on Ohje aiheessa [Yleiset sovellukset](#global-apps) . |

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
|  **m**   |   Näyttää minuutit lukuna ilman ensimmäistä nollaa.<br><br>Tämän paikka merkin on tultava heti **h** -tai **hh** -koodin jälkeen tai välittömästi ennen **SS** -koodia. muussa tapa uksessa **teksti** palauttaa kuukauden sijasta minuutit.  |    
| **mm**   | Näyttää minuutit lukuna ja käyttää tarvittaessa ensimmäistä nollaa.<br><br>Tämän paikka merkin on oltava heti **h** -tai **hh** -paikka merkin jälkeen tai välittömästi ennen **SS** -paikka merkkiä. Muussa tapa uksessa **teksti** palauttaa kuukauden sijasta minuutit. |                                                                                                                   
| **s**   |  Näyttää sekunnin lukuna ilman ensimmäistä nollaa.  |
| **ss**  | Näyttää sekunnit lukuna ja käyttää tarvittaessa ensimmäistä nollaa.                                                                        |
|                                                                                                    **f**                                                                                                     |                                                                                         Näyttää sekunnin murto-osat.                                                                                          |
|                                                                                    **AM/PM**, **a/p**                                                                                    |               Näyttää ajan 12 tunnin kellon perusteella. **Teksti** palauttaa arvon "am" tai "a" kertaa Keski yöstä Keski päivään ja "PM" tai "p" Keski päivästä Keski yöhön                |

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

* **Mukautetun muodon kieli:** Päättäjille, miten mukautettua muotoa tulisi tulkita? Erotinmerkeillä ( **.** ja **,** ) on eri kielissä eri merkitykset. Jos määrität mukautetun muodon, voit lisätä kielen paikka merkin tai käyttää oletus arvoa, joka vastaa sitä kieltä, johon laitteesi on määritetty. Voit myös käyttää jotain [esimääritettyä päivä määrä/aika-muotoa](#predefined-datetime-formats), joka on kieliagnostikko.
* **Tuloksen kieli:** Käyttäjille, millä kielellä funktion tulos näytetään? Kuukausien ja viikon päivien nimien on oltava sovelluksen käyttäjälle sopivalla kielellä, jonka voit määrittää lisäämällä **teksti** -funktiolla kolmannen valinnaisen argumentin. 

Voit sekä määrittää kielen käyttämällä [kieli koodia](function-language.md#language-tags). Jos haluat tarkastella tuettujen kielten luetteloa, kirjoita **teksti (1234, "",)** kaava riville tai oikeanpuoleisen ruudun **lisä asetukset** -väli lehteen ja selaa sitten kolmannessa argumentissa ehdotettujen aluekohtaisten asetusten luetteloa.

### <a name="language-placeholder"></a>Kielen paikka merkki
Voit käyttää mukautetun muotoilun kielen määrittämiseen seuraavia:

| Paikkamerkki | Kuvaus |
| --- | --- |
| **[$-*LanguageTag*]** |*LanguageTag* on **Language**-funktion palauttama kielitunniste. Se voi määrittää vain kielen (esimerkiksi **[$-EN]** englanniksi), tai se voi myös määrittää alueen (esimerkiksi **[$-en-GB]** määrittämään Isoa-Britanniaa). |

Kielen paikkamerkki voi esiintyä missä tahansa kohdassa mukautettavaa muotoilua, mutta vain kerran.

Jos määrität mukautetun muodon ilman kieli paikka merkkiä ja muoto on moniselitteinen yleisestä näkö kulmasta, nykyisen kielesi kieli tunnus lisätään automaattisesti.  

**[$-en-US]** oletetaan, jos tätä paikka merkkiä ei ole, kun sovelluksesi suoritetaan. 

> [!NOTE]
> Tulevassa versiossa tämän paikka merkin syntaksi voi muuttua, jotta vältetään sekaannukset samanlaisen, mutta eri paikka merkin kanssa, jota Excel tukee.

### <a name="result-language-tag"></a>Tuloksen kielitunniste
**Teksti** sisältää käännettyjä merkki jonoja kuukausia, ARKISIN, AM/PM-nimityksiä sekä sopivia ryhmä-ja desimaalerottimia.

Oletusmuotoisesti **Text**-funktio käyttää sitä kieltä, jota sovelluksessa parhaillaan käytetään. **Language**-funktio palauttaa nykyisen käyttäjän kielitunnisteen. Voit ohittaa tämän Oletus arvon antamalla **tekstille**kolmannen argumentin kieli merkinnän.

## <a name="syntax"></a>Syntaksi
**Teksti**( *numberordatetime*, *datetimesformateum* [, *resultlanguagetunnisteet* ])

* *Numberordatetime* – pakollinen. Muotoiltava numero tai päivämäärä/kellonaika.
* *DateTimeFormat* – Pakollinen.  **DateTimeFormat** – Luetteloinnin osa.
* *ResultLanguageTag* – Valinnainen. Kielitunniste, jota käytetään tulostekstiin. Oletusmuotoisesti käytetään nykyisen käyttäjän kieltä.

**Teksti**( *numberordatedtime*, *Custompformat* [, *resultlanguagetagen* ])

* *Number* – pakollinen. Muotoiltava numero tai päivämäärä/kellonaika.
* *CustomFormat* – pakollinen. Yksi tai useampi paikkamerkki lainausmerkkien sisällä.
* *ResultLanguageTag* – Valinnainen. Kielitunniste, jota käytetään tulostekstiin. Oletusmuotoisesti käytetään nykyisen käyttäjän kieltä.

**Teksti**( *anyvalue* )

* *Anyvalue* – pakollinen. Teksti esitykseen muunnettava arvo. Käytetään oletus muotoa.

## <a name="examples"></a>Esimerkkejä
Ellei toisin määritetä, näitä kaavoja suorittava käyttäjä sijaitsee Yhdysvallat ja on valinnut kieleksi englanninkielisen.  **Language**-funktio palauttaa tuloksen "en-US".

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
| **Teksti (1448318857 * 1000, "mmm. DD, vvvv (hh:mm: SS AM/PM))** | Esittää UNIX-päivä määrä-aika-arvon ihmisen luettavissa olevassa muodossa, jos kerrot lähde arvon arvolla 1 000. | "Nov. 23, 2015 (02:47:37 PM)" |

### <a name="global-apps"></a>Yleiset sovellukset

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Teksti (1234567.89, "[$-FR-FR] # # # #, # # &euro;", "FR-FR")** | Ilmaisee väli lyönnin ryhmittely erottimena, pilkun Desi maalina ja **&euro;** valuutta symbolina. |"1 @ no__t-0234 @ no__t-1567, 89 &euro;" |
| **Teksti (1234567; "[$-FR-FR] # # # #, # # &euro;")** | Jos lähde tiedot ovat Ranskan mukautettuja, jotka käyttävät pilkkua kymmen järjestelmä erottimena, sinun on muutettava alueasetukseksi Ranska ja erotettava argumentit puoli pisteellä pilkun sijaan, jotta saat saman tuloksen kuin yllä. |"1 @ no__t-0234 @ no__t-1567, 89 &euro;" |
| **Text( Date(2016,1,31), "dddd mmmm d" )** |Palauttaa viikonpäivän, kuukauden ja kuukauden päivän muotoiltuna nykyisen käyttäjän kielen mukaan. Koska paikkamerkit eivät ole kieleen sidottuja, tekstin muotoiluun ei tarvita kielitunnistetta. |"Lauantai @ no__t-0January @ no__t-131" |
| **Text( Date(2016,1,31), "dddd mmmm d", "es-ES" )** |Palauttaa viikonpäivän, kuukauden ja kuukauden päivän kielitunnisteen "es-ES" mukaisesti. |"Domingo @ no__t-0enero @ no__t-131" |

### <a name="converting-values-to-text"></a>Muunnetaan arvot tekstiksi

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Teksti (&nbsp;1234567.89 @ no__t-2)** | Muuntaa luvun merkki jonoksi. Desimaali erottimen ennen tai jälkeen olevien numeroiden määrää ei ole tuhaterottimia tai-ohjaus objektia. Lisää hallintaa antaa numeroiden paikka merkit toisena argumenttina. | "1234567,89" |
| **Text (&nbsp;Datetime (&nbsp; "01/04/2003" &nbsp;) &nbsp;)** | Muuntaa päivä määrä-ja aika-arvon teksti merkki jonoksi. Jos haluat hallita muunnosta, anna joko Datemetyformat-luetteloinnin jäsen tai mukautettu muotoilu merkki jono. | "1/4/2003 12:00 AM" |
| **Teksti (&nbsp;true @ no__t-2)** | Muuntaa totuus arvon merkki jonoksi. | totta |
| **Teksti (&nbsp;GUID () &nbsp;)** | Muuntaa luodun GUID-arvon merkki jonoksi.  | "f8b10550-0f12-4f08-9aa3-bb10958bc3ff" |
| **Left (&nbsp;Text (&nbsp;GUID () &nbsp;), &nbsp;4 @ no__t-5)** | Palauttaa luodun GUID-arvon neljä ensimmäistä merkkiä. | "2d9c" | 

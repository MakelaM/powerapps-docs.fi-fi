---
title: Text-funktio | Microsoft Docs
description: Tietoja PowerAppsin Text-funktiosta, kuten syntaksi ja joitakin esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: dab6004afe7350b2375ade21871efe9144b6325b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849289"
---
# <a name="text-function-in-powerapps"></a>PowerAppsin Text-funktio
Muotoilee luvun tai päivämäärän/kellonajan esitystavan.

## <a name="description"></a>Kuvaus
**Text**-funktio soveltaa numeron tai päivämäärän/kellonajan muotoiluun jotain seuraavan tyyppisistä argumenteista:

* Ennalta määritetty päivämäärän/kellonajan esitystapa, jonka voit määrittää käyttämällä **DateTimeFormat**-luettelointia.  Tätä tyyppiä suositellaan päivämäärien ja kellonaikojen muotoiluun, koska se mukautuu automaattisesti kunkin käyttäjän kielen ja sijaintipaikan mukaan.
* Mukautettu muotoilu tarkoittaa merkkijonoa, jossa käytetään paikkamerkkejä osoittamaan, miten päivämäärä ja kellonaika muotoillaan. Paikkamerkit osoittavat näytössä näkyvien numeroiden määrän, käytetäänkö ryhmittelyerottimia ja miten kuukausien nimet esitetään. PowerApps tukee samaa paikkamerkkien osajoukkoa, jota Microsoft Excel käyttää.

Lisätietoja on kohdassa [Päivämäärien ja kellonaikojen käsitteleminen](../show-text-dates-times.md).

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
| **.** (*piste*) |Näyttää luvun desimaalierottimen.  Riippuu mukautetun muodon kielestä; katso lisätietoja kohdasta [Yleisiä sovelluksia](#global-apps). |
| **,** (*pilkku*) |Näyttää ryhmittelyerottimen, jota joissakin kielissä käytetään tuhaterottimena. **Text**-funktio erottaa ryhmät pilkuilla, jos muotoilussa on ristikkomerkkien (**#**) tai nollien sisällä oleva pilkku.  Riippuu mukautetun muodon kielestä; katso lisätietoja kohdasta [Yleisiä sovelluksia](#global-apps). |

Jos desimaalipilkun oikealla puolella on enemmän numeroita kuin muodossa on paikkamerkkejä, luku pyöristetään niin moneen desimaaliin kuin muodossa on paikkamerkkejä. Jos desimaalipilkun vasemmalla puolella on enemmän numeroita kuin muodossa on paikkamerkkejä, ylimääräiset numerot näytetään. Jos desimaalipilkun vasemmalla puolella on vain ristikkomerkkejä (#), lukua 1 pienemmän arvot alkavat desimaalipilkulla (esimerkiksi **,47**).

### <a name="date-and-time-placeholders"></a>Päivämäärän ja kellonajan paikkamerkit

|                                                                                                 Paikkamerkki                                                                                                  |                                                                                                     Kuvaus                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                    **m**                                                                                                     |                                                                               Näyttää kuukauden lukuna ilman ensimmäistä nollaa.                                                                                |
|                                                                                                    **mm**                                                                                                    |                                                                        Näyttää kuukauden lukuna ja käyttää tarvittaessa ensimmäistä nollaa.                                                                         |
|                                                                                                   **mmm**                                                                                                    |                                                                             Näyttää kuukauden lyhenteenä (**tam**...**jou**).                                                                             |
|                                                                                                   **mmmm**                                                                                                   |                                                                          Näyttää kuukauden koko nimen (**tammikuu**...**joulukuu**).                                                                           |
|                                                                                                    **d**                                                                                                     |                                                                                Näyttää kuukauden päivän ilman ensimmäistä nollaa.                                                                                 |
|                                                                                                    **dd**                                                                                                    |                                                                         Näyttää kuukauden päivän lukuna ja käyttää tarvittaessa ensimmäistä nollaa.                                                                          |
|                                                                                                   **ddd**                                                                                                    |                                                                              Näyttää päivän lyhenteenä (**su**...**la**).                                                                              |
|                                                                                                   **dddd**                                                                                                   |                                                                            Näyttää päivän koko nimen (**sunnuntai**...**lauantai**).                                                                            |
|                                                                                                    **yy**                                                                                                    |                                                                                      Näyttää vuoden kaksinumeroisena lukuna.                                                                                       |
|                                                                                                   **yyyy**                                                                                                   |                                                                                      Näyttää vuoden nelinumeroisena lukuna.                                                                                      |
|                                                                                                    **h**                                                                                                     |                                                                                Näyttää tunnit ilman ensimmäistä nollaa.                                                                                |
|                                                                                                    **hh**                                                                                                    | Näyttää tunnit lukuna ja käyttää tarvittaessa ensimmäistä nollaa. Jos muotoiluun sisältyy **AM** tai **PM**, aika näkyy 12 tunnin mukaan. Muussa tapauksessa aika näytetään 24 tunnin mukaan. |
|                                                                                                    **m**                                                                                                     |                                                                         Näyttää minuutit lukuna ilman ensimmäistä nollaa.  > [!NOTE]                                                                          |
|            > **m**- tai **mm** -koodin on oltava heti **h**- tai **hh**-koodin perässä tai heti ennen **ss**-koodia; muussa tapauksessa **Text**-funktio palauttaa kuukauden minuuttien sijaan.            |                                                                                                                                                                                                                     |
|                                                                                                    **mm**                                                                                                    |                                                                   Näyttää minuutit lukuna ja käyttää tarvittaessa ensimmäistä nollaa. > [!NOTE]                                                                   |
| > **m**- tai **mm**-paikkamerkin on oltava heti **h**- tai **hh**-paikkamerkin jälkeen tai heti ennen **ss**-paikkamerkkiä. Muussa tapauksessa **Text**-funktio palauttaa kuukauden minuuttien sijaan. |                                                                                                                                                                                                                     |
|                                                                                                    **s**                                                                                                     |                                                                               Näyttää sekunnin lukuna ilman ensimmäistä nollaa.                                                                               |
|                                                                                                    **ss**                                                                                                    |                                                                        Näyttää sekunnit lukuna ja käyttää tarvittaessa ensimmäistä nollaa.                                                                        |
|                                                                                                    **f**                                                                                                     |                                                                                         Näyttää sekunnin murto-osat.                                                                                          |
|                                                                                    **AM/PM**, **am/pm**, **A/P**, **a/p**                                                                                    |               Näyttää ajan 12 tunnin kellon perusteella. **Text**-funktio palauttaa arvon "AM", "am", "A" tai "a" keskiyöstä keskipäivään ja "PM", "pm", "P" tai "p" keskipäivästä keskiyöhön                |

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
**Text**-funktio on maailmanlaajuinen.  Se tuntee suuren määrän kieliä ja osaa kirjoittaa päivämäärät, kellonajat, valuutat ja numerot kielen mukaan.  Onnistuakseen tässä se tarvitsee seuraavat kaksi tietoa:

* **Mukautettavan muodon kieli:** miten mukautettu muoto tulkitaan tekstin laatijaa varten?  Erotinmerkeillä (**.** ja **,**) on eri kielissä eri merkitykset.  Tämä hoidetaan käyttämällä kielikoodilla varustettua paikkamerkkiä.  Lisäksi [etukäteen määritetyt päivämäärän ja kellonajan muotoilut](#predefined-datetime-formats) ovat kieliagnostisia, eli käytetty kieli ei vaikuta niihin.
* **Tuloksen kieli:** millä kielellä tulos näytetään käyttäjälle?  Kuukausien ja viikonpäivien nimet on muotoiltava sovelluksen käyttäjän kielen mukaisiksi.  Tämä hoidetaan lisäämällä **Text**-funktioon kolmas valinnainen argumentti. 

Kumpaankin näistä määrityksistä liitetään [kielitunniste](function-language.md#language-tags).  Voit tarkastella tuettujen kielten luetteloa kirjoittamalla kaavariville tai lisänäkymään **Text( 1234, "", )** ja selaamalla kolmanteen argumenttiin ehdotettuja kieliasetuksia.

#### <a name="custom-format-language-placeholder"></a>Mukautetun muotoilun kielen paikkamerkki
Voit käyttää mukautetun muotoilun kielen määrittämiseen seuraavia:

| Paikkamerkki | Kuvaus |
| --- | --- |
| **[$-*LanguageTag*]** |*LanguageTag* on **Language**-funktion palauttama kielitunniste.  Se voidaan esittää pelkän kielen muodossa, kuten englannin kielen **[$-en]**, tai siihen voidaan lisätä tarkentava aluetunnus, kuten Ison-Britannian **[$-en-GB]**. |

Kielen paikkamerkki voi esiintyä missä tahansa kohdassa mukautettavaa muotoilua, mutta vain kerran.

Jos et lisää kielen paikkamerkkiä luodessasi kaavaa ja muotoiltu merkkijono on globaalissa mielessä epäselvä, luontityökalu lisää kielen paikkamerkin automaattisesti sen kielen mukaan, joka on parhaillaan käytössä.  

Jos tätä paikkamerkkiä ei löydy, kun sovellus suoritetaan, ohjelma olettaa, että asetus on **[$-en-US]**. 

> [!NOTE]
> Tulevassa versiossa tämän paikkamerkin syntaksi voi muuttua, jotta sitä ei sekoitettaisi Excelin tukemaan paikkamerkkiin, joka on samantyyppinen mutta erilainen.

#### <a name="result-language-tag"></a>Tuloksen kielitunniste
**Text**-funktion tuloksessa näkyy käännetyn kielen mukainen kuukausi, viikonpäivä, AM/PM, ryhmityserottaja ja desimaalimerkki.

Oletusmuotoisesti **Text**-funktio käyttää sitä kieltä, jota sovelluksessa parhaillaan käytetään.  **Language**-funktio palauttaa nykyisen käyttäjän kielitunnisteen.  Voit ohittaa tämän oletuksen lisäämällä **Text**-funktion valinnaiselle kolmannelle argumentille kielitunnisteen.

## <a name="syntax"></a>Syntaksi
**Text**( *Number*, *DateTimeFormatEnum* [, *ResultLanguageTag* ] )

* *Number* – Pakollinen. Muotoiltava numero tai päivämäärä/kellonaika.
* *DateTimeFormat* – Pakollinen.  **DateTimeFormat** – Luetteloinnin osa.
* *ResultLanguageTag* – Valinnainen.  Kielitunniste, jota käytetään tulostekstiin.  Oletusmuotoisesti käytetään nykyisen käyttäjän kieltä.

**Text**( *Number*, *CustomFormat* [, *ResultLanguageTag* ] )

* *Number* – Pakollinen. Muotoiltava numero tai päivämäärä/kellonaika.
* *CustomFormat* – pakollinen. Yksi tai useampi paikkamerkki lainausmerkkien sisällä.
* *ResultLanguageTag* – Valinnainen.  Kielitunniste, jota käytetään tulostekstiin.  Oletusmuotoisesti käytetään nykyisen käyttäjän kieltä.

## <a name="examples"></a>Esimerkkejä
Käyttäjä, joka suorittaa nämä kaavat, sijaitsee Yhdysvalloissa ja on valinnut kielekseen englannin.  **Language**-funktio palauttaa tuloksen "en-US".

### <a name="number"></a>Luku

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Text(&nbsp;1234.59,&nbsp;"####.#"&nbsp;)** |Muotoilee luvun yhden desimaalin tarkkuudella. |"1234.6" |
| **Teksti (&nbsp;8.9,&nbsp;”#. 000”&nbsp;)** |Lisää tarvittaessa nollat numeron desimaaliosan loppuun. |"8.900" |
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

### <a name="global-apps"></a>Yleiset sovellukset

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Text( 1234567.89, "[$-en-US]$ #,###" )** |Tulkitsee pilkun (**,**) tuhaterottimeksi, joka näytetään kolmen merkin välein, ja lisää valuuttamerkin **$**. Koska desimaaleja ei käytetä, arvo pyöristetään suurempaan kokonaislukuun. Tässä tapauksessa **[$-en-US]** on valinnainen, sillä se on oletusarvo. |"$ 1,234,568" |
| **Text( 1234567.89, "[$-es-ES]&euro; #,###" )** |Tulkitsee pilkun (**,**) desimaalierottimeksi ja merkinnän **&euro;** valuuttasymboliksi.  Koska **[$-fr-FR]** määrittää ainoastaan, miten muotoilumerkkijono tulkitaan, desimaalierottimena käytetään oletusmuotoisen en-US-kielitunnisteen mukaista pistettä (**"."**) ja valuuttasymbolina merkkiä **$**. |"$ 1234567.89" |
| **Text( 1234567.89, "[$-es-ES]&euro; #,###", "es-ES" )** |Tulkitsee pilkun (**,**) desimaalierottimeksi.  Tuloksen kielitunnisteeksi on asetettu "fr-FR", joten desimaalierottimena käytetään pilkkua ( **,**) ja valuuttasymbolina merkkiä **&euro;**. |"&euro; 1234567,89" |
| **Text( Date(2016,1,31), "dddd mmmm d" )** |Palauttaa viikonpäivän, kuukauden ja kuukauden päivän muotoiltuna nykyisen käyttäjän kielen mukaan. Koska paikkamerkit eivät ole kieleen sidottuja, tekstin muotoiluun ei tarvita kielitunnistetta. |"Saturday January 31" |
| **Text( Date(2016,1,31), "dddd mmmm d", "es-ES" )** |Palauttaa viikonpäivän, kuukauden ja kuukauden päivän kielitunnisteen "es-ES" mukaisesti. |"domingo enero 31" |


---
title: Onmatch-, Match-ja MatchAll-Funktiot | Microsoft Docs
description: Powerappsin Onmatch-, Match-ja MatchAll-funktioiden viite tiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 08/15/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ac6e5196de03a3c2d292696f1216c443f4c5b7e6
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992665"
ms.PowerAppsDecimalTransform: true
---
# <a name="ismatch-match-and-matchall-functions-in-powerapps"></a>Enmatch-, Match-ja MatchAll-Funktiot Powerappsissa
Testaa vastaavuuden tai poimii teksti merkki jonon osat malliin pohjautuen.

## <a name="description"></a>Kuvaus
**IsMatch**-funktio testaa, vastaako merkkijono hakuarvoa, joka voi koostua normaaleista merkeistä, esimääritetyistä malleista tai [säännönmukaisesta lausekkeesta](#regular-expressions).  **Match** -ja **matchall** -funktiot palauttavat vastaavuudet, mukaan lukien alivastineita.  

Käytä **IsMatch**-funktiota vahvistamaan käyttäjän **[Tekstisyöte](../controls/control-text-input.md)** -ohjausobjektiin syöttämä sisältö. Voit esimerkiksi vahvistaa, onko käyttäjä syöttänyt kelvollisen sähköpostiosoitteen, ennen kuin tulokset tallennetaan tietolähteeseesi. Jos tietue ei vastaa kriteereitäsi, lisää muita ohjausobjekteja, jotka kehottavat käyttäjää korjaamaan sen.

Poimi **vastaavuus** -komennolla ensimmäinen teksti merkki jono, joka vastaa kaavaa ja **matchall** -menetelmää, poimimaan kaikki vastaavat teksti merkki jonot. Voit myös noutaa alivastineita monitasoisten merkki jonojen jäsentämiseen.   

**Match** palauttaa ensimmäisen löydettyjen tietojen tietueen, ja **matchall** palauttaa tietueiden taulukon jokaisesta löydetystä vastaavu usta. Tietue tai tietueet sisältävät seuraavat:

| Sarake | Tyyppi | Kuvaus |
|----|----|----|
| *nimetyt Sub&#8209;Match-tai&#8209;Sub-vastineita* | Text | Kullakin nimettyyn aliotteluun on oma sarakkeensa. Luo nimetty aliottelu käyttämällä **(? &lt;*Name*&gt;** ... **)** säännönmukaisessa lausekkeessa. Jos nimettyyn aliotteluun on sama nimi kuin jollakin esimääritetystä sarakkeesta (alla), alivastaavuus on etusijalla ja varoitus luodaan. Jos haluat välttää tämän varoituksen, nimeä alivastaavuus uudelleen. |
| **FullMatch** | Text | Kaikki täsmäytettiin teksti merkki jono. |
| **StartMatch** | Luku | Vastaavuuden aloitus kohta syöte teksti merkki jonossa. Merkki jonon ensimmäinen merkki palauttaa arvon 1. | 
| **Osavastaavuudet** | Yksisarakkeinen teksti taulukko (sarake **arvo**) | Nimettyjen ja nimeämättömien alivastaavu uksien taulukko siinä järjestyksessä, jossa ne näkyvät säännönmukaisessa lausekkeessa. Yleensä nimetyt alivastineita on helpompi käsitellä, ja niitä kannustetaan. Käytä [**kokeilu**](function-forall.md) funktioita tai [**Last**](function-first-last.md)( [**firstn**](function-first-last.md)( **...** ))-funktioita, jotka toimivat yksittäisellä alivastaavu-funktiolla. Jos säännöllisessä lausekkeessa ei määritetä alivastaavu uksia, tämä taulukko on olemassa, mutta se on tyhjä. |

Nämä funktiot tukevat [**Matchoptions**](#match-options)-ominaisuuksia. Oletus arvon mukaan: 
- Nämä funktiot suorittavat kirjain koon mukaisen vastaavuuden. Käytä **IgnoreCase** -kohdetta kirjain koolla olevien vastaavu uksien suorittamiseen.    
- **Onmatch** vastaa koko teksti merkki jonoa (**Complete** matchoption), kun taas **Match** -ja **matchall** -haku vastaavat mitä tahansa teksti merkki jonon kohtaa (**sisältää** matchoptiota). Käytä **valmis**-, **sisältää**-, **Beginswith**-tai **EndsWith** -menetelmää skenaariosi mukaan.

**IsMatch** palauttaa arvon *tosi*, jos merkkijono vastaa mallia ja arvon *epätosi*, jos se ei vastaa sitä. **Match** palauttaa arvon *tyhjä* , jos vastaavuutta ei löydy, jota voidaan testata käyttämällä [**onblank**](function-isblank-isempty.md) -toimintoa. **Matchall** palauttaa tyhjän taulukon, jos vastaavuutta ei löydy, jota voidaan testata [**IsEmpty**](function-isblank-isempty.md) -funktiolla.

Jos käytät **Matchall** -kohdetta teksti merkki jonon jakamiseen, harkitse **[Split](function-split.md)** -toiminnon käyttämistä, mikä on helppokäyttöisempi ja nopeampi.

## <a name="patterns"></a>Mallit
Näiden funktioiden käyttämisen avain on kuvaavassa rakenteessa. Malli kuvaillaan merkkijonona, joka voi sisältää yhdistelmän seuraavia:

* Tavalliset merkit, kuten **"abc"** tai **"123"** .
* Esimääritetyt mallit, kuten **Letter**, **MultipleDigits** tai **Email**. (**Match**-luettelointi määrittelee nämä mallit.)
* Säännönmukaiset lauseke koodit, kuten **"\d + \s + \d +"** tai **"[a-z] +"** .

Yhdistä nämä elementit käyttämällä [merkki jono-ketjutus operaattoria **&** ](operators.md). Esimerkiksi **"abc" & Digit & "\s+"** on kelvollinen kaava, joka vastaa merkkijonoa, jonka alussa on "a", "b" tai "c", jonka jälkeen on numero väliltä 0–9 ja sitten vähintään yksi välilyöntimerkki.

### <a name="ordinary-characters"></a>Tavalliset merkit
Yksinkertaisin malli on sarja tavallisia merkkejä, joille haetaan täyttä vastaavuutta.

Esimerkiksi kun käytetään yhdessä **Onmatch** -funktion kanssa, merkki jono "Hello" vastaa kaavaa **"Hello"** tarkalleen. Ei enempää tai vähempää. Merkkijono ”hei!” ei vastaa kaavaa, koska lopussa on huuto merkki, ja koska kirjain "h" on virheellinen. (Katso kohdasta [Vastaavuusvalinnat](#match-options) tapoja tämän toiminnon muokkaamiseksi.)

Mallikielessä tietyt merkit on varattu erityistoimintoja varten. Jos haluat käyttää näitä merkkejä, joko etuliite merkkiä **\\** (Keno viiva) osoittamaan, että merkki tulee ottaa kirjaimellisesti, tai käytä jotakin jäljempänä tässä ohje aiheessa kuvatusta valmiista malleista. Erikoismerkit on lueteltu tässä taulukossa:

| Erikoismerkki | Kuvaus |
| --- | --- |
| **.** |piste |
| **?** |kysymysmerkki |
| **&#42;** |tähti |
| **\+** |plus |
| **( )** |sulkeissa |
| **[ ]** |hakasulkeet |
| **{ }** |kaarisulkeet |
| **^** |sirkumfleksi |
| **$** |dollarimerkki |
| **\|** |pystyviiva tai putkimerkki |
| **\\** |kenoviiva |

Voit esimerkiksi saada vastaavuuden ”Hei?” käyttämällä mallia **"Hei\\?"** , jossa on kenoviiva ennen kysymysmerkkiä.

### <a name="predefined-patterns"></a>Esimääritetyt mallit
Esimääritetyt kuviot tarjoavat yksinkertaisen tavan sovittaa yhteen merkki joukosta tai useista merkeistä. Käytä [merkki jono-ketjuttamisoperaattoria **&** ](operators.md) yhdistääksesi omat teksti merkki jonot **Match** Enum-kohteen jäseniin:

| Täsmää luettelointi | Kuvaus | Säännönmukainen lauseke |
| --- | --- | --- |
| **Any** |Vastaa mitä tahansa merkkiä. |`.` |
| **Comma** |Vastaa pilkkua. |`;` |
| **Digit** |Vastaa yhtä numeroa (0–9). |`\d` |
| **Email** |Vastaa sähköpostiosoitetta, joka sisältää ”at”-merkin (”\@”) ja toimialuenimen, joka sisältää pisteen (”.”) |`.+\@.+\\.[^\\.]{2;}` |
| **Hyphen** |Vastaa yhdysmerkkiä. |`\-` |
| **LeftParen** |Vastaa vasenta suljetta ”(”. |`\(` |
| **Letter** |Vastaa kirjainta. |`\p{L}` |
| **MultipleDigits** |Vastaa yhtä tai useampaa merkkiä. |`\d+` |
| **MultipleLetters** |Vastaa yhtä tai useampaa kirjainta. |`\p{L}+` |
| **MultipleNonSpaces** |Vastaa yhtä tai useampaa merkkiä, jotka eivät lisää väli lyöntejä (ei väliä, väli lehteä tai NewLine-kohdetta). |`\S+` |
| **MultipleSpaces** |Vastaa yhtä tai useampaa merkkiä, jotka lisäävät väli lyöntejä (väli lyönti, SARKAIN tai NewLine). |`\s+` |
| **NonSpace** |Vastaa yhtä merkkiä, joka ei ole välilyöntimerkki. |`\S` |
| **OptionalDigits** |Vastaa nollaa, yhtä tai useampaa merkkiä. |`\d*` |
| **OptionalLetters** |Vastaa nollaa, yhtä tai useampaa kirjainta. |`\p{L}*` |
| **OptionalNonSpaces** |Vastaa nollaa, yhtä tai useampaa merkkiä, jotka eivät ole välilyöntimerkkejä. |`\S*` |
| **OptionalSpaces** |Vastaa nollaa, yhtä tai useampaa välilyöntimerkkiä. |`\s*` |
| **Period** |Vastaa pistettä (”.”). |`\.` |
| **RightParen** |Vastaa oikeaa suljetta ”)”. |`\)` |
| **Space** |Vastaa välilyöntimerkkiä. |`\s` |

Esimerkiksi malli **"A" & MultipleDigits** vastaa kirjainta ”A”, jonka jälkeen esiintyy yksi tai useampi numero.  

### <a name="regular-expressions"></a>Säännönmukaiset lausekkeet
Näiden funktioiden käyttöön käytettävä muoto on [säännönmukainen lauseke](https://en.wikipedia.org/wiki/Regular_expression). Tavalliset merkit ja ennalta määritetyt kuviot, jotka on kuvattu aiemmin tässä ohje aiheessa, helpottavat säännönmukaisten lausekkeiden luomista.  

Säännönmukaiset lausekkeet ovat hyvin tehokkaita, ne ovat saatavilla useissa ohjelmointikielissä ja niitä käytetään useisiin eri tarkoituksiin. Ne voivat myös usein näyttää satunnaisen väli merkki sarjan. Tässä artikkelissa ei kuvailla säännönmukaisten lausekkeiden kaikkia puolia, mutta verkossa on käytettävissä runsaasti tietoja, opetus ohjelmia ja työkaluja.  

Säännönmukaisia lausekkeita on eri murteissa, ja PowerApps käyttää JavaScript-murteen varianttia. Lisä tietoja syntaksi on Ohje aiheessa [säännönmukaisen lausekkeen syntaksi](https://msdn.microsoft.com/library/1400241x.aspx) . Nimettyjä alivastaavu uksia (kutsutaan joskus nimettyihin sieppaus ryhmiksi) tuetaan:

- Nimetyt alivastaavuudet: **(? &lt;*nimi*&gt;...)**
- Nimetyt backreferences: **\\K @ no__t-2*Name*&gt;**

Aiemmin tässä ohje aiheessa olevassa **Match** Enum-taulukossa jokainen luettelointi näkyy samalla rivillä kuin vastaava säännönmukainen lauseke.

## <a name="match-options"></a>Vastaavuusvalinnat
Voit muokata näiden funktioiden toimintaa määrittämällä yhden tai useamman vaihto ehdon, jotka voit yhdistää käyttämällä merkki jono-liittämis operaattoria ( **&amp;** ).  

| MatchOptions-luettelointi | Kuvaus | Vaikutus säännöllisessä lausekkeessa |
| --- | --- | --- |
| **BeginsWith** |Mallin on vastattava tekstin alkua. |Lisää säännönmukaisen lausekkeen alkuun **^** -merkin. |
| **Complete** |Oletus kohteelle **Istmatch**. Rakenteen on vastattava koko teksti merkki jonoa alusta loppuun. |Lisää **^** : n alkuun ja **$** : n säännönmukaisen lausekkeen loppuun. |
| **Contains** |Oletus arvo kohteelle **Match** ja **matchall**. Tämän mallin täytyy olla jossakin kohdassa tekstiä mutta sen ei tarvitse olla alussa tai lopussa. |Ei muokkaa säännönmukaista lauseketta. |
| **EndsWith** |Rakenteen on vastattava teksti merkki jonon loppua. |Lisää säännönmukaisen lausekkeen loppuun **$** -merkin. |
| **IgnoreCase** |Käsittelee isoja ja pieniä kirjaimia identtinä. Oletuksena vastaavuuksissa kirjainkoko on merkitsevä. |Ei muokkaa säännönmukaista lauseketta. Tämä asetus vastaa vakio lausekkeiden i-määritettä.  |
| **Multiline** |Etsii vastaavuutta useilta riveiltä. |Ei muokkaa säännönmukaista lauseketta. Tämä asetus vastaa säännönmukaisten lausekkeiden vakio-m-määritettä. |

**Matchall** -menetelmän käyttäminen vastaa vakio lausekkeiden g-määritettä.

## <a name="syntax"></a>Syntaksi
**IsMatch**( *Text*; *Pattern* [; *Options* ] )

* *Text* – Pakollinen. Testattava merkkijono.
* *Pattern* – Pakollinen. Teksti merkki jonona testattava rakenne. Yhdistä määritetyt kuviot, jotka **täsmäävät** -luettelointi määrittää, tai anna säännönmukainen lauseke. *Mallin* on oltava vakio kaava ilman muuttujia, tieto lähteitä tai muita dynaamisia viitta uksia, jotka muuttuvat sovelluksen suorittamisen yhteydessä.
* *Options* – Valinnainen. **Matchoptions** -luettelointi arvojen teksti merkki jono yhdistelmä. Oletuksena käytetään valintaa **MatchOptions.Complete**.

**Vastaavuus**( *teksti*; *muoto* [; *Asetukset* ])

* *Text* – Pakollinen. Vastaavuus teksti merkki jono.
* *Pattern* – Pakollinen. Teksti merkki jonona käytettävä muoto. Yhdistä määritetyt kuviot, jotka **täsmäävät** -luettelointi määrittää, tai anna säännönmukainen lauseke. *Mallin* on oltava vakio kaava ilman muuttujia, tieto lähteitä tai muita dynaamisia viitta uksia, jotka muuttuvat sovelluksen suorittamisen yhteydessä.
* *Options* – Valinnainen. **Matchoptions** -luettelointi arvojen teksti merkki jono yhdistelmä. Oletuksena käytetään **Matchoptions. contains** -arvoa.

**Matchall**( *teksti*; *muoto* [; *Asetukset* ])

* *Text* – Pakollinen. Vastaavuus teksti merkki jono.
* *Pattern* – Pakollinen. Teksti merkki jonona käytettävä muoto. Yhdistä määritetyt kuviot, jotka **täsmäävät** -luettelointi määrittää, tai anna säännönmukainen lauseke. *Mallin* on oltava vakio kaava ilman muuttujia, tieto lähteitä tai muita dynaamisia viitta uksia, jotka muuttuvat sovelluksen suorittamisen yhteydessä.
* *Options* – Valinnainen. **Matchoptions** -luettelointi arvojen teksti merkki jono yhdistelmä. Oletuksena käytetään **Matchoptions. contains** -arvoa.

## <a name="ismatch-examples"></a>Onmatch-esimerkit
### <a name="ordinary-characters"></a>Tavalliset merkit
Kuvitellaan, että sovelluksesi sisältää **Tekstisyöte**-ohjausobjektin nimeltä **TextInput1**. Käyttäjä syöttää tähän ohjausobjektiin arvoja, jotka tallennetaan tietokantaan.   

Käyttäjä kirjoittaa **TextInput1**-kohtaan **Hei maailma**.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| `IsMatch( TextInput1.Text; "Hello world" )` |Testaa, vastaako käyttäjän syöte tarkalleen merkki jonoa "Hello World". |**tosi** |
| `IsMatch( TextInput1.Text; "Good bye" )` |Testaa, vastaako käyttäjän syöte tarkalleen merkki jonoa "Good Bye". |**epätosi** |
| `IsMatch( TextInput1.Text; "hello"; Contains )` |Testaa, sisältääkö käyttäjän syöte sanan "Hello" (kirjain koko on merkitsevä). |**epätosi** |
| `IsMatch( TextInput1.Text; "hello"; Contains & IgnoreCase )` |Testaa, sisältääkö käyttäjän syöte sanan ”hei” (kirjainkoko ei ole merkityksellinen). |**tosi** |

### <a name="predefined-patterns"></a>Esimääritetyt mallit

|                                                            Kaava                                                            |                                                                Kuvaus                                                                |  Tulos   |
|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| `IsMatch( "123-45-7890"; Digit & Digit & Digit & Hyphen & Digit & Digit & Hyphen & Digit & Digit & Digit & Digit )` |                                              Vastaa Yhdysvaltojen sosiaaliturvatunnusta                                               | **tosi**  |
|                                           `IsMatch( "joan@contoso.com"; Email )`                                            |                                                         Vastaa sähköpostiosoitetta                                                          | **tosi**  |
|                              `IsMatch( "123.456"; MultipleDigits & Period & OptionalDigits )`                               |                                   Vastaa, kun kyseessä on numerojono, jonka jälkeen on piste ja sitten nolla tai useampia numeroita.                                   | **tosi**  |
|                                `IsMatch( "123"; MultipleDigits & Period & OptionalDigits )`                                 | Vastaa, kun kyseessä on numerojono, jonka jälkeen on piste ja sitten nolla tai useampia numeroita. Teksti ei näy piste luettelossa, joten tätä kaavaa ei ole täsmäytetty. | **epätosi** |

### <a name="regular-expressions"></a>Säännönmukaiset lausekkeet

|                                                                              Kaava                                                                              |                                                                                                                                  Kuvaus                                                                                                                                   |  Tulos   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
|                                                                    `IsMatch( "986"; "\d+" )`                                                                   |                                                                                                                    Vastaa nollaa suurempaa kokonaislukua.                                                                                                                     | **tosi**  |
|                                                               `IsMatch( "1.02"; "\d+(\.\d\d)?" )`                                                              |                                        Vastaa positiivista valuuttasummaa. Jos syöte sisältää desimaalimuodon, syötteen on sisällettävä myös kaksi aakkosto-merkkiä. Esimerkiksi 3.00 on kelvollinen, mutta 3.1 ei.                                         | **tosi**  |
|                                                            `IsMatch( "-4.95"; "(-)?\d+(\.\d\d)?" )`                                                             |                                                        Vastaa positiivista tai negatiivista valuuttasummaa. Jos syöte sisältää desimaalimuodon, syötteen on sisällettävä myös kaksi aakkosto-merkkiä.                                                        | **tosi**  |
|                                                         `IsMatch( "111-11-1111"; "\d{3}-\d{2}-\d{4}" )`                                                        | Vastaa Yhdysvaltojen sosiaaliturvatunnusta. Vahvistaa annetun syötekentän muodon, tyypin ja pituuden. Vastaavuus merkki jonon on koostuttava kolmesta numealisesta merkistä, joita seuraa viiva, ja sitten kaksi merkkiä, joita seuraa viiva, ja sitten neljä numeroa. | **tosi**  |
|                                                         `IsMatch( "111-111-111"; "\d{3}-\d{2}-\d{4}" )`                                                         |                                                                                               Sama kuin edellisessä esimerkissä, mutta yksi syötteen viiva on väärässä paikassa.                                                                                               | **epätosi** |
|                                         `IsMatch( "AStrongPasswordNot"; "(?!^[0-9]\*$)(?!^[a-zA-Z]\*$)([a-zA-Z0-9]{8,10})" )`                                        |                                        Vahvistaa vahvan Sala sanan, jonka on sisällettävä kahdeksan, yhdeksän tai kymmenen merkkiä, ja lisäksi siinä on oltava vähintään yksi numero ja vähintään yksi aakkos merkki. Merkkijono ei saa sisältää erikoismerkkejä.                                        | **epätosi** |
| `IsMatch( "<https://microsoft.com>"; "(ht&#124;f)tp(s?)\:\/\/\[0-9a-zA-Z\]([-.\w]\*[0-9a-zA-Z])\*(:(0-9)\*)\*(\/?)([a-zA-Z0-9\-\.\?\,\'\/\\\+&%\$#_]\*)?" )` |                                                                                                                     Vahvistaa http-, https- tai ftp-url-osoitteen.                                                                                                                      | **tosi**  |

## <a name="match-and-matchall-examples"></a>Match-ja MatchAll-esimerkit

| Kaava | Kuvaus | Tulos |
|--------|------------|-----------|
| `Match( "Bob Jones <bob.jones@contoso.com>"; "<(?<email>" & Match.Email & ")>"` | Poimii vain yhteys tietojen Sähkö posti osan.  | {<br>Sähkö posti: &nbsp; "bob.jones@contoso.com",<br>FullMatch: &nbsp; "&lt; @ no__t-2 >",<br>Osavastaavuudet: &nbsp; [&nbsp; "bob.jones@contoso.com" &nbsp;]<br>StartMatch: 11<br>}  
| `Match( "Bob Jones <InvalidEmailAddress>"; "<(?<email>" & Match.Email & ")>"` | Poimii vain yhteys tietojen Sähkö posti osan. Mitään oikeudellista osoitetta ei löydy (@-merkki ei ole), joten funktio palauttaa *tyhjän*. | *tyhjä* |  
| `Match( Language(); "(<language>\w{2})(?:-(?<script>\w{4}))?(?:-(?<region>\w{2}))?" )` | Poimii **[kieli-funktiolla](function-language.md)** palauttavan kieli merkinnän kieli-, komento sarja-ja alue osat. Nämä tulokset kuvastavat Yhdysvallat; Lue lisää esimerkkejä [ **kieli** funktioiden ohjeista](function-language.md) .  **(?:** Operaattori ryhmittelee merkit luomatta toista alivastaavuutta. | {<br>kieli: "En",<br>komento sarja: *tyhjä*, <br>alue "US",<br>FullMatch: "en-US", <br>Osavastaavuudet: ["En", "", "US"], <br>StartMatch: 1<br>} 
| `Match( "PT2H1M39S"; "PT(?:<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" )` | Poimii tunnit, minuutit ja sekunnit ISO 8601-kesto arvosta. Poimitut luvut ovat yhä teksti merkki jonossa; Muunna [**arvo**](function-value.md) -funktiolla luku-funktiolla ennen matemaattisten toimintojen suorittamista.  | {<br> tunnit "2",<br>minuuttia "1",<br>sekuntia "39",<br>FullMatch: "PT2H1M39S",<br>Osavastaavuudet: &nbsp; [&nbsp; "2", &nbsp; "1", &nbsp; "39" &nbsp;],<br>StartMatch: 1<br>} |

Let's siirtyä tähän viimeiseen esimerkkiin. Jos halusit muuntaa tämän merkki jonon päivä määrä-ja aika-arvoksi käyttämällä **[Time](function-date-time.md)** -funktiolla, sinun on välitettävä nimetyt alivastaavuudet yksitellen. Voit tehdä tämän käyttämällä **[with-](function-with.md)** toimintoa, joka toimii palautusten **täsmäävän** tietueen kanssa:

``` powerapps-comma
With( 
    Match( "PT2H1M39S"; "PT(?:(?<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" ); 
    Time( Value( hours ); Value( minutes ); Value( seconds ) )
)
```

Lisää näitä esimerkkejä varten [painike](../controls/control-button.md) -ohjaus objekti, määritä sen **onselect** -ominaisuudeksi Tämä kaava ja valitse sitten painike:

``` powerapps-comma
Set( pangram; "The quick brown fox jumps over the lazy dog." )
```
 
| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| `Match( pangram; "THE"; IgnoreCase )` | Etsi kaikki kohteen "THE" vastaavuudet **panggram** -muuttujan sisältämistä teksti merkki jonosta. Merkki jono sisältää kaksi vastaavuutta, mutta vain ensimmäinen palautetaan, koska käytät **vastaavuutta** etkä **matchall**-kohdetta. SubMatches-sarake on tyhjä, koska alivastaavu uksia ei määritetty.  | {<br>FullMatch: "The",<br>Osavastaavuudet: [&nbsp;],<br>StartMatch: 32<br>} |
| `MatchAll( pangram; "the" )` | Etsi kaikki kohteen "The" vastaavuudet **panggram** -muuttujan sisältämistä teksti merkki jonosta. Testissä kirjain koko on merkitsevä, joten vain toinen esiintymä löytyi. SubMatches-sarake on tyhjä, koska alivastaavu uksia ei määritetty.  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-the-one.png) |
| `MatchAll( pangram; "the"; IgnoreCase )` | Etsi kaikki kohteen "The" vastaavuudet **panggram** -muuttujan sisältämistä teksti merkki jonosta. Tässä tapa uksessa testissä kirjain koolla ei ole merkitystä, joten sanan molemmat esiintymät löytyvät. SubMatches-sarake on tyhjä, koska alivastaavu uksia ei määritetty.  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-the-two.png) |
| `MatchAll( pangram; "\b\wo\w\b" )` | Etsii kaikki kolmikirjaimiset sanat, joiden keskellä on "o". Ota huomioon, että "Brown" ohitetaan, koska se ei ole kolmikirjaiminen sana, joten se ei vastaa "\b" (sanan rajaa).  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-fox-dog.png) |
| `Match( pangram; "\b\wo\w\b\s\*(?<between>\w.+\w)\s\*\b\wo\w\b" )` | Vastaa kaikkia merkkejä "Fox" ja "Dog" välillä. | {<br>välillä: &nbsp; "hyppää @ no__t-1over @ no__t-2The @ no__t-3lazy",<br>FullMatch: &nbsp; "Fox @ no__t-1jumps @ no__t-2over @ no__t-3The @ no__t-4lazy @ no__t-5dog",<br>Osavastaavuudet: ["hyppää yli laiska"],<br>StartMatch: 17<br> } |

Jos haluat tarkastella valikoiman **Matchall** -tuloksia valikoimassa:

1. Lisää tyhjään näyttöön tyhjä pystysuuntainen **[valikoima](../controls/control-gallery.md)** -ohjaus objekti.

2. Valitse valikoiman **Items** -ominaisuudeksi **matchall (pangram, "\w +")** tai **Matchall (Pangram, multipleelementers)** .

    ![](media/function-ismatch/pangram-gallery1.png)

3. Valitse valikoiman malli valitsemalla Lisää kohde Lisää-väli lehdestä valikoima-ohjaus objektin keskeltä. 

5. Lisää **[otsikko](../controls/control-text-box.md)** -ohjaus objekti valikoiman malliin.  

4. Valitse otsikon **teksti** -ominaisuudeksi **Thisitem. fullmatch**.  
 
    Valikoima on täytetty esimerkki tekstin jokaisella sanalla.  Muuta valikoiman mallin ja selite-ohjaus objektin kokoa, jotta voit tarkastella kaikkia sanoja yhdessä näytössä.

    ![](media/function-ismatch/pangram-gallery2.png)

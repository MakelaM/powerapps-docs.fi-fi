---
title: IsMatch, vastaavuus ja MatchAll | Microsoft Docs
description: Viitetiedot, mukaan lukien syntaksi IsMatch ja MatchAll Match-Funktiot powerappsissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/15/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7141d3b9a2ba6bf18bffe1756d0d7de048606cad
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61563055"
ms.PowerAppsDecimalTransform: true
---
# <a name="ismatch-match-and-matchall-functions-in-powerapps"></a>IsMatch ja MatchAll Match-Funktiot powerappsissa
Testaa vastaavuus tai otteet osan merkkijonon kuviota perusteella.

## <a name="description"></a>Kuvaus
**IsMatch**-funktio testaa, vastaako merkkijono hakuarvoa, joka voi koostua normaaleista merkeistä, esimääritetyistä malleista tai [säännönmukaisesta lausekkeesta](#regular-expressions).  **Vastaavuus** ja **MatchAll** funktiot palauttavat mitä oli määritetty, mukaan lukien alimerkkijonon vastaavuudet.  

Käytä **IsMatch**-funktiota vahvistamaan käyttäjän **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjektiin syöttämä sisältö. Voit esimerkiksi vahvistaa, onko käyttäjä syöttänyt kelvollisen sähköpostiosoitteen, ennen kuin tulokset tallennetaan tietolähteeseesi. Jos tietue ei vastaa kriteereitäsi, lisää muita ohjausobjekteja, jotka kehottavat käyttäjää korjaamaan sen.

Käytä **vastaa** poimia ensimmäinen tekstimerkkijono, joka vastaa kuviota ja **MatchAll** Pura kaikki, jotka vastaavat merkkijonoja. Voit myös poimia alimerkkijonon vastaavuudet jäsentäminen monimutkaisia merkkijonoja.   

**Vastaa** palauttaa tietueen, ensimmäinen vastaavuus löytyi, tiedon ja **MatchAll** palauttaa tietueet taulukon jokainen vastaavuus löytyi. Tietue tai tietueet sisältää:

| Sarake | Tyyppi | Kuvaus |
|----|----|----|
| *nimeltä sub&#8209;vastaa tai sub&#8209;vastaa* | Text | Kukin nimetty alimerkkijonon vastaavuus on oma sarake. Luo nimetty alimerkkijonon vastaavuus käyttämällä **(?&lt; *nimi*&gt;**... **)** säännöllisessä lausekkeessa. Jos nimettyä alimerkkijonon vastaavuus on sama nimi kuin yksi ennalta määritetyt sarakkeet (alla), alimerkkijonon vastaavuus on etusijalla ja varoitus luodaan. Tämä varoitus välttämiseksi nimeä alimerkkijonon vastaavuus. |
| **FullMatch** | Text | Kaikki merkkijono, joka on kohdistettu. |
| **StartMatch** | Luku | Syötteen merkkijonosta vastaavuus aloituskohta. Merkkijonon ensimmäinen merkki palauttaa 1. | 
| **Alivastineiden** | Tekstin yhden sarakkeen taulukko (sarake **arvo**) | Nimettyjä ja nimeämättömiä järjestyksessä, jossa ne näkyvät säännönmukainen lauseke alimerkkijonon vastaavuudet taulukko. Yleensä nimetty alimerkkijonon vastaavuudet on helpompi käyttää, ja kehotetaan valmistautumaan. Käytä [ **ForAll** ](function-forall.md) funktio tai [ **viimeisen**](function-first-last.md)( [ **FirstN**](function-first-last.md)() **...**  )) funktioita yksittäisten alimerkkijonon vastaavuus käsittelemiseen. Jos aliraportti vastaavuuksia ei määritetty säännönmukainen lauseke, tämä taulukko on olemassa, mutta se on tyhjä. |

Nämä funktiot tue [ **MatchOptions**](#match-options). Oletusarvoisesti: 
- Nämä funktiot suorittaa kirjainkoko. Käytä **IgnoreCase** kirjainkoko ei merkitsevä vastaavuudet suorittamiseen.    
- **IsMatch** vastaa koko merkkijono (**valmiina** MatchOption), kun **vastaa** ja **MatchAll** Hae merkkijono (vastaavuutta **Sisältää** MatchOption). Käytä **valmiina**, **sisältää**, **BeginsWith**, tai **EndsWith** tapauksen tarpeisiin.

**IsMatch** palauttaa arvon *tosi*, jos merkkijono vastaa mallia ja arvon *epätosi*, jos se ei vastaa sitä. **Vastaa** palauttaa *tyhjä* Jos vastaavuutta ei löydy, sitä voidaan testata [ **IsBlank** ](function-isblank-isempty.md) funktio. **MatchAll** palauttaa tyhjän taulukon, jos vastaavuutta ei löydy, sitä voidaan testata [ **IsEmpty** ](function-isblank-isempty.md) funktio.

Jos käytät **MatchAll** jakaa merkkijonon, harkitse **[Jaa](function-split.md)** funktio, joka käyttää helpompi ja nopeampi.

## <a name="patterns"></a>Mallit
Näiden funktioiden käyttäminen avain on tärkeää kuvailla malli, johon syötettä verrataan. Malli kuvaillaan merkkijonona, joka voi sisältää yhdistelmän seuraavia:

* Tavalliset merkit, kuten **"abc"** tai **"123"**.
* Esimääritetyt mallit, kuten **Letter**, **MultipleDigits** tai **Email**. (**Match**-luettelointi määrittelee nämä mallit.)
* Säännöllinen lauseke koodit, kuten **”\d+\s+\d+”** tai **”[a – z] +”**.

Yhdistä näitä elementtejä käyttämällä [merkkijonon yhdistämisoperaattoria **&** ](operators.md). Esimerkiksi **"abc" & Digit & "\s+"** on kelvollinen kaava, joka vastaa merkkijonoa, jonka alussa on "a", "b" tai "c", jonka jälkeen on numero väliltä 0–9 ja sitten vähintään yksi välilyöntimerkki.

### <a name="ordinary-characters"></a>Tavalliset merkit
Yksinkertaisin malli on sarja tavallisia merkkejä, joille haetaan täyttä vastaavuutta.

Esimerkiksi käytettäessä **IsMatch** funktio, merkkijono ”Hei” vastaa mallia **”Hello”** tarkalleen. Ei enempää tai vähempää. Merkkijono ”hei!” ei vastaa mallia vuoksi pään huutomerkin ja ”h”-kirjaimen väärän. (Katso kohdasta [Vastaavuusvalinnat](#match-options) tapoja tämän toiminnon muokkaamiseksi.)

Mallikielessä tietyt merkit on varattu erityistoimintoja varten. Jos haluat käyttää näitä merkkejä, joko etuliite-merkin **\\** (kenoviiva) ilmaisemaan, että merkki tulee tulkita kirjaimellisesti tai käytä jotakin esimääritetyt mallit, jotka kuvataan myöhemmin tässä aiheessa. Erikoismerkit on lueteltu tässä taulukossa:

| Erikoismerkki | Kuvaus |
| --- | --- |
| **.** |piste |
| **?** |kysymysmerkki |
| **&#42;** |tähti |
| **\+** |plus |
| **( )** |Sulkeiden |
| **[ ]** |hakasulkeet |
| **{ }** |kaarisulkeet |
| **^** |sirkumfleksi |
| **$** |dollarimerkki |
| **\|** |pystyviiva tai putkimerkki |
| **\\** |kenoviiva |

Voit esimerkiksi saada vastaavuuden ”Hei?” käyttämällä mallia **"Hei\\?"**, jossa on kenoviiva ennen kysymysmerkkiä.

### <a name="predefined-patterns"></a>Esimääritetyt mallit
Esimääritetyt mallit tarjoavat yksinkertaisen tavan vastaamaan joko yksi merkeistä tai usean merkin sarjalle jakson. Käytä [merkkijonon yhdistämisoperaattoria **&** ](operators.md) omien merkkijonojen jäsenten kanssa **vastaavuus** enum:

| Match-luettelointi | Kuvaus | Säännönmukainen lauseke |
| --- | --- | --- |
| **Any** |Vastaa mitä tahansa merkkiä. |`.` |
| **Comma** |Vastaa pilkkua. |`;` |
| **Digit** |Vastaa yhtä numeroa (0–9). |`\d` |
| **Email** |Vastaa sähköpostiosoitetta, joka sisältää ”at”-merkin (”\@”) ja toimialuenimen, joka sisältää pisteen (”.”) |`.+\@.+\\.[^\\.]{2;}` |
| **Hyphen** |Vastaa yhdysmerkkiä. |`\-` |
| **LeftParen** |Vastaa vasenta suljetta ”(”. |`\(` |
| **Letter** |Vastaa kirjainta. |`\p{L}` |
| **MultipleDigits** |Vastaa yhtä tai useampaa numeroa. |`\d+` |
| **MultipleLetters** |Vastaa yhtä tai useampaa kirjainta. |`\p{L}+` |
| **MultipleNonSpaces** |Vastaa vähintään yhden merkin, joka ei ole välilyöntimerkki (ei välilyönti, SARKAIN tai rivivaihto). |`\S+` |
| **MultipleSpaces** |Vastaa vähintään yhden merkin, joka välilyöntimerkki (välilyönti, SARKAIN tai rivivaihto). |`\s+` |
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
Malli, joka käyttää näitä funktioita on [säännönmukainen lauseke](https://en.wikipedia.org/wiki/Regular_expression). Tavalliset merkit ja esimääritetyt mallit, jotka on kuvattu aiemmin tässä aiheessa apua rakentamaan säännönmukaisen lausekkeen.  

Säännönmukaiset lausekkeet ovat hyvin tehokkaita, ne ovat saatavilla useissa ohjelmointikielissä ja niitä käytetään useisiin eri tarkoituksiin. Ne näyttävät myös usein välimerkkien satunnaisen järjestyksen. Tässä artikkelissa ei kuvailla kaikkia Säännönmukaisten lausekkeiden ominaisuuksia, mutta paljon tietoja, opetusohjelmia, ja työkalut ovat käytettävissä verkossa.  

Säännönmukaiset lausekkeet ovat eri kielioppivaihtoehtoja PowerApps käyttää-JavaScript-kieliopin muunnelmaa. Katso [regular lausekkeen syntaksi](http://msdn.microsoft.com/library/1400241x.aspx) johdanto syntaksi. Nimetty alimerkkijonon vastaavuudet (kutsutaan nimetty sieppaus ryhmät) tuetaan:

- Nimeltä alimerkkijonon vastaavuudet: **(?&lt; *nimi* &gt; ...)**
- Nimeltä backreferences:  **\\k&lt;*nimi*&gt;**

Tässä **vastaavuus** luetteloinnin taulukon tämän ohjeaiheen luetteloinnit näkyy samalle riville kuin sen vastaava säännönmukainen lauseke.

## <a name="match-options"></a>Vastaavuusvalinnat
Voit muokata näitä funktioita toimintaa määrittämällä yhden tai useamman valinnan, joita voidaan yhdistellä käyttämällä merkkijonon-yhdistämisoperaattoria (**&amp;**).  

| MatchOptions-luettelointi | Kuvaus | Vaikutus säännönmukaiseen lausekkeeseen |
| --- | --- | --- |
| **BeginsWith** |Mallin on vastattava tekstin alkua. |Lisää säännönmukaisen lausekkeen alkuun **^**-merkin. |
| **Complete** |Oletusarvo **IsMatch**. Tämän mallin täytyy vastata koko tekstiä alusta loppuun-merkkijonon. |Lisää **^** alkuun ja **$** säännönmukaisen lausekkeen loppuun. |
| **Contains** |Oletusarvo **vastaavuus** ja **MatchAll**. Tämän mallin täytyy olla jossakin kohdassa tekstiä mutta sen ei tarvitse olla alussa tai lopussa. |Ei muokkaa säännönmukaista lauseketta. |
| **EndsWith** |Tämän mallin täytyy vastata tekstin merkkijonon loppuun. |Lisää säännönmukaisen lausekkeen loppuun **$**-merkin. |
| **IgnoreCase** |Käsittelee isoja ja pieniä kirjaimia kuin identtiset. Oletuksena vastaavuuksissa kirjainkoko on merkitsevä. |Ei muokkaa säännönmukaista lauseketta. Tämä vaihtoehto on vastaava säännönmukaiset lausekkeet standard ”i”-määrite.  |
| **Multiline** |Etsii vastaavuutta useilta riveiltä. |Ei muokkaa säännönmukaista lauseketta. Tämä vaihtoehto on vastaava säännönmukaiset lausekkeet standard ”m”-määrite. |

Käyttämällä **MatchAll** vastaa standard ”g” muokkaaja säännönmukaiset lausekkeet varten.

## <a name="syntax"></a>Syntaksi
**IsMatch**( *Text*; *Pattern* [; *Options* ] )

* *Text* – Pakollinen. Testattava merkkijono.
* *Pattern* – Pakollinen. Testattava merkkijonona malli. Yhdistä esimääritetyt mallit, joka **vastaavuus** enum määrittää tai anna säännönmukainen lauseke. *Malli* on oltava yhtenäinen kaavan ilman muuttujia, tietolähteitä tai muita dynamic viittaa muutokset sovelluksen suorittamiseksi.
* *Options* – Valinnainen. Merkkijono yhdistelmän **MatchOptions** luetteloinnin arvoista. Oletuksena käytetään valintaa **MatchOptions.Complete**.

**Vastaavuus**( *tekstin*; *malli* [; *asetukset* ])

* *Text* – Pakollinen. Vastaamaan merkkijono.
* *Pattern* – Pakollinen. Malli, johon merkkijonona. Yhdistä esimääritetyt mallit, joka **vastaavuus** enum määrittää tai anna säännönmukainen lauseke. *Malli* on oltava yhtenäinen kaavan ilman muuttujia, tietolähteitä tai muita dynamic viittaa muutokset sovelluksen suorittamiseksi.
* *Options* – Valinnainen. Merkkijono yhdistelmän **MatchOptions** luetteloinnin arvoista. Oletusarvon mukaan **MatchOptions.Contains** käytetään.

**MatchAll**( *tekstin*; *malli* [; *asetukset* ])

* *Text* – Pakollinen. Vastaamaan merkkijono.
* *Pattern* – Pakollinen. Malli, johon merkkijonona. Yhdistä esimääritetyt mallit, joka **vastaavuus** enum määrittää tai anna säännönmukainen lauseke. *Malli* on oltava yhtenäinen kaavan ilman muuttujia, tietolähteitä tai muita dynamic viittaa muutokset sovelluksen suorittamiseksi.
* *Options* – Valinnainen. Merkkijono yhdistelmän **MatchOptions** luetteloinnin arvoista. Oletusarvon mukaan **MatchOptions.Contains** käytetään.

## <a name="ismatch-examples"></a>IsMatch esimerkkejä
### <a name="ordinary-characters"></a>Tavalliset merkit
Kuvitellaan, että sovelluksesi sisältää **Tekstisyöte**-ohjausobjektin nimeltä **TextInput1**. Käyttäjä syöttää tähän ohjausobjektiin arvoja, jotka tallennetaan tietokantaan.   

Käyttäjä kirjoittaa **TextInput1**-kohtaan **Hei maailma**.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| `IsMatch( TextInput1.Text; "Hello world" )` |Testaa, käyttäjä, vastaako käyttäjän syöte tarkalleen merkkijonoa ”Hei maailma”. |**tosi** |
| `IsMatch( TextInput1.Text; "Good bye" )` |Testaa, käyttäjä, vastaako käyttäjän syöte tarkalleen merkkijonoa ”Hyvästi”. |**epätosi** |
| `IsMatch( TextInput1.Text; "hello"; Contains )` |Testaa, sisältääkö käyttäjän syöte sanan ”Hei” (kirjainkoko on merkitsevä). |**epätosi** |
| `IsMatch( TextInput1.Text; "hello"; Contains & IgnoreCase )` |Testaa, sisältääkö käyttäjän syöte sanan ”hei” (kirjainkoko ei ole merkityksellinen). |**tosi** |

### <a name="predefined-patterns"></a>Esimääritetyt mallit

|                                                            Kaava                                                            |                                                                Kuvaus                                                                |  Tulos   |
|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| `IsMatch( "123-45-7890"; Digit & Digit & Digit & Hyphen & Digit & Digit & Hyphen & Digit & Digit & Digit & Digit )` |                                              Vastaa Yhdysvaltojen sosiaaliturvatunnusta                                               | **tosi**  |
|                                           `IsMatch( "joan@contoso.com"; Email )`                                            |                                                         Vastaa sähköpostiosoitetta                                                          | **tosi**  |
|                              `IsMatch( "123.456"; MultipleDigits & Period & OptionalDigits )`                               |                                   Vastaa, kun kyseessä on numerojono, jonka jälkeen on piste ja sitten nolla tai useampia numeroita.                                   | **tosi**  |
|                                `IsMatch( "123"; MultipleDigits & Period & OptionalDigits )`                                 | Vastaa, kun kyseessä on numerojono, jonka jälkeen on piste ja sitten nolla tai useampia numeroita. Ajan ei näy teksti, joka vastaa, jotta tämä malli ei vastannut. | **epätosi** |

### <a name="regular-expressions"></a>Säännönmukaiset lausekkeet

|                                                                              Kaava                                                                              |                                                                                                                                  Kuvaus                                                                                                                                   |  Tulos   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
|                                                                    `IsMatch( "986"; "\d+" )`                                                                   |                                                                                                                    Vastaa kokonaisluku, joka on suurempi kuin nolla.                                                                                                                     | **tosi**  |
|                                                               `IsMatch( "1.02"; "\d+(\.\d\d)?" )`                                                              |                                        Vastaa positiivista valuuttasummaa. Jos syöte sisältää desimaalierottimen, syötteen täytyy myös sisältää kaksi numeroa desimaalipisteen jälkeen. Esimerkiksi 3.00 on kelvollinen, mutta 3.1 ei.                                         | **tosi**  |
|                                                            `IsMatch( "-4.95"; "(-)?\d+(\.\d\d)?" )`                                                             |                                                        Vastaa positiivista tai negatiivista valuuttasummaa. Jos syöte sisältää desimaalierottimen, syötteen täytyy myös sisältää kaksi numeroa desimaalipisteen jälkeen.                                                        | **tosi**  |
|                                                         `IsMatch( "111-11-1111"; "\d{3}-\d{2}-\d{4}" )`                                                        | Vastaa Yhdysvaltojen sosiaaliturvatunnusta. Vahvistaa annetun syötekentän muodon, tyypin ja pituuden. Vastattavan merkkijonon täytyy sisältää kolme numeroa, viiva, sitten kaksi numeroa, viiva mukaan ja sitten neljä numeroa. | **tosi**  |
|                                                         `IsMatch( "111-111-111"; "\d{3}-\d{2}-\d{4}" )`                                                         |                                                                                               Sama kuin edellisessä esimerkissä, mutta yksi syötteen viiva on väärässä paikassa.                                                                                               | **epätosi** |
|                                         `IsMatch( "AStrongPasswordNot"; "(?!^[0-9]\*$)(?!^[a-zA-Z]\*$)([a-zA-Z0-9]{8,10})" )`                                        |                                        Vahvistaa vahvan salasanan, jonka täytyy sisältää 8, 9 tai 10 merkkiä sekä vähintään yhden numeron ja vähintään yhden kirjaimen. Merkkijono ei saa sisältää erikoismerkkejä.                                        | **epätosi** |
| `IsMatch( "<http://microsoft.com>"; "(ht&#124;f)tp(s?)\:\/\/\[0-9a-zA-Z\]([-.\w]\*[0-9a-zA-Z])\*(:(0-9)\*)\*(\/?)([a-zA-Z0-9\-\.\?\,\'\/\\\+&%\$#_]\*)?" )` |                                                                                                                     Vahvistaa http-, https- tai ftp-url-osoitteen.                                                                                                                      | **tosi**  |

## <a name="match-and-matchall-examples"></a>Vastaavuus ja MatchAll esimerkkejä

| Kaava | Kuvaus | Tulos |
|--------|------------|-----------|
| `Match( "Bob Jones <bob.jones@contoso.com>"; "<(?<email>" & Match.Email & ")>"` | Poimii vain sähköposti osuus yhteystiedot.  | {<br>sähköposti:&nbsp;”bob.jones@contoso.com”,<br>FullMatch:&nbsp;"&lt;bob.jones@contoso.com>",<br>Alivastineiden:&nbsp;[&nbsp;”bob.jones@contoso.com”&nbsp;],<br>StartMatch: 11<br>}  
| `Match( "Bob Jones <InvalidEmailAddress>"; "<(?<email>" & Match.Email & ")>"` | Poimii vain sähköposti osuus yhteystiedot. Juridiset osoitetta ei löydy (ei ole @-merkkiä), joten funktio palauttaa *tyhjä*. | *tyhjä* |  
| `Match( Language(); "(<language>\w{2})(?:-(?<script>\w{4}))?(?:-(?<region>\w{2}))?" )` | Otteet kielen kielen, komentosarjan ja alueen osan tunniste, **[kielen](function-language.md)** funktio palauttaa. Nämä tulokset kuvastavat Yhdysvallat. Katso [ **kielen** funktion dokumentaatio](function-language.md) Lisää esimerkkejä.  **(?:** Operaattorin ryhmät merkkiä luomatta toinen alimerkkijonon vastaavuus. | {<br>kieli: ”en”<br>komentosarjan: *tyhjä*, <br>alue: "US",<br>FullMatch: "en-US", <br>Alivastineiden: [”en” ”,”, ”US”], <br>StartMatch: 1<br>} 
| `Match( "PT2H1M39S"; "PT(?:(<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" )` | Poimii tunnit, minuutit ja sekunnit ISO 8601-kestoarvo. Poimittu numerot ovat edelleen merkkijonossa. Käytä [ **arvo** ](function-value.md) funktio muuntaa luvuksi, ennen kuin se suoritetaan matemaattiset laskutoimitukset.  | {<br> tunnit: "2",<br>minuuttia: "1",<br>sekuntia: "39",<br>FullMatch: ”PT2H1M39S”<br>Alivastineiden:&nbsp;[&nbsp;”2”&nbsp;”1”&nbsp;”39”&nbsp;],<br>StartMatch: 1<br>} |

Oletetaan, että porautua kyseiseen viimeinen esimerkki. Halua päivämäärä/aika-arvo käyttämällä tämän merkkijonon muuntaminen **[aika](function-date-time.md)** funktio, sinun on välitettävä-nimetty alimerkkijonon vastaavuudet erikseen. Voit tehdä tämän, voit määrittää **[ForAll](function-forall.md)** funktio käsittelee ensimmäisen tietueen, jotka **MatchAll** palauttaa:

``` powerapps-comma
First( 
    ForAll( 
        MatchAll( "PT2H1M39S"; "PT(?:(?<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" ); 
        Time( Value( hours ); Value( minutes ); Value( seconds ) )
    )
).Value
```

Näissä esimerkeissä Lisää [painike](../controls/control-button.md) ohjausobjekti, määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava ja valitse sitten painike:

``` powerapps-comma
Set( pangram; "The quick brown fox jumps over the lazy dog." )
```
 
| Kaava | Kuvaus | Tulos |
|---------|-------------|--------|
| `Match( pangram; "THE"; IgnoreCase )` | Etsi teksti ”niitä” kaikki vastaavuudet merkkijono, joka **pangram** muuttujan sisältää. Merkkijono sisältää kaksi vastaavuuksia, mutta vain ensimmäinen palautetaan, koska käytät **vastaavuus** ja ei **MatchAll**. Alivastineiden-sarake on tyhjä, koska alimerkkijonon vastaavuuksia ei määritetty.  | {<br>FullMatch: ””<br>Alivastineiden: [&nbsp;],<br>StartMatch: 32<br>} |
| `MatchAll( pangram; "the" )` | Näytä kaikki kohteet tekstin ”the”-merkkijono, joka **pangram** muuttujan sisältää. Testaa kirjainkoko on merkitsevä, joten vain toinen kohteen ”the” esiintymä löytyi. Alivastineiden-sarake on tyhjä, koska alimerkkijonon vastaavuuksia ei määritetty.  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-the-one.png) |
| `MatchAll( pangram; "the"; IgnoreCase )` | Näytä kaikki kohteet tekstin ”the”-merkkijono, joka **pangram** muuttujan sisältää. Tässä tapauksessa testin on kirjainkoko ei ole merkitsevä, joten sekä sanan esiintymät. Alivastineiden-sarake on tyhjä, koska alimerkkijonon vastaavuuksia ei määritetty.  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-the-two.png) |
| `MatchAll( pangram; "\b\wo\w\b" )` | Etsii kaikkia kolmikirjaiminen sanoja, jotka ”o” keskellä. Huomaa, että ”tummanruskea” on pois, koska se ei ole kolmikirjaiminen sanan ja vuoksi epäonnistuu vastaamaan ”\b” (word raja).  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-fox-dog.png) |
| `Match( pangram; "\b\wo\w\b\s\*(?<between>\w.+\w)\s\*\b\wo\w\b" )` | Vastaa kaikki merkit välillä ”fox” ja ”koira”. | {<br>between:&nbsp;"jumps&nbsp;over&nbsp;the&nbsp;lazy",<br>FullMatch:&nbsp;"fox&nbsp;jumps&nbsp;over&nbsp;the&nbsp;lazy&nbsp;dog",<br>Alivastineiden: [”Hyppää kautta palvelinrakenteen”],<br>StartMatch: 17<br> } |

Jotta näet tulokset **MatchAll** valikoimassa:

1. Lisää tyhjä näyttö, tyhjä pystysuuntainen **[valikoiman](../controls/control-gallery.md)** ohjausobjektin.

2. Määritä valikoiman **kohteet** ominaisuudeksi **MatchAll (pangram, ”\w+”)** tai **MatchAll (pangram MultipleLetters)**.

    ![](media/function-ismatch/pangram-gallery1.png)

3. Valitse ”Lisää kohde Lisää-välilehdestä” ja valitse haluamasi valikoiman mallipohja valikoima-ohjausobjektin keskellä. 

5. Lisää **[nimen](../controls/control-text-box.md)** ohjausobjektin valikoiman mallipohjaa.  

4. Määritä selitteen **tekstin** ominaisuudeksi **ThisItem.FullMatch**.  
 
    Valikoiman tulee kunkin sanan parantaakseen esimerkkiteksti.  Muuta valikoiman mallipohjaa ja nimi-ohjausobjektin näkyviin kaikki sanat yhdessä näytössä.

    ![](media/function-ismatch/pangram-gallery2.png)

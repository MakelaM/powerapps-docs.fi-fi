---
title: IsMatch-funktio | Microsoft Docs
description: PowerAppsin IsMatch-funktion viitetiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 02/05/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f7612b648b3f1f5228fce93054f8732ec47767a8
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833512"
---
# <a name="ismatch-function-in-powerapps"></a>IsMatch-funktio PowerAppsissa
Testaa, vastaako merkkijono hakuarvoa.

## <a name="description"></a>Kuvaus
**IsMatch**-funktio testaa, vastaako merkkijono hakuarvoa, joka voi koostua normaaleista merkeistä, esimääritetyistä malleista tai [säännönmukaisesta lausekkeesta](#regular-expressions).  

Käytä **IsMatch**-funktiota vahvistamaan käyttäjän **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjektiin syöttämä sisältö. Voit esimerkiksi vahvistaa, onko käyttäjä syöttänyt kelvollisen sähköpostiosoitteen, ennen kuin tulokset tallennetaan tietolähteeseesi. Jos tietue ei vastaa kriteereitäsi, lisää muita ohjausobjekteja, jotka kehottavat käyttäjää korjaamaan sen.

**IsMatch** suorittaa oletuksena tarkistuksen koko merkkijonolle niin, että kirjainkoko on merkitsevä. Voit muokata tätä toimintaa määrittämällä yhden tai useamman [**MatchOptions**](#match-options)-vaihtoehdon.

**IsMatch** palauttaa arvon *tosi*, jos merkkijono vastaa mallia ja arvon *epätosi*, jos se ei vastaa sitä.

## <a name="patterns"></a>Mallit
**IsMatch**-funktion käytössä on tärkeää kuvailla malli, johon syötettä verrataan. Malli kuvaillaan merkkijonona, joka voi sisältää yhdistelmän seuraavia:

* Tavalliset merkit, kuten **"abc"** tai **"123"**.
* Esimääritetyt mallit, kuten **Letter**, **MultipleDigits** tai **Email**. (**Match**-luettelointi määrittelee nämä mallit.)
* Säännöllisen lausekkeen koodit, kuten **"\d+\s+\d+"** tai **"[a-z]+"**.

Yhdistä näitä elementtejä käyttämällä [merkkijonon yhdistämisoperaattoria **&**](operators.md). Esimerkiksi **"abc" & Digit & "\s+"** on kelvollinen kaava, joka vastaa merkkijonoa, jonka alussa on "a", "b" tai "c", jonka jälkeen on numero väliltä 0–9 ja sitten vähintään yksi välilyöntimerkki.

### <a name="ordinary-characters"></a>Tavalliset merkit
Yksinkertaisin malli on sarja tavallisia merkkejä, joille haetaan täyttä vastaavuutta.

Esimerkiksi merkkijono ”Hei” vastaa täysin mallia **"Hei"**. Ei enempää tai vähempää. Merkkijono ”hei!” ei vastaa mallia lopussa olevan huutomerkin ja ”h”-kirjaimen väärän kirjainkoon vuoksi. (Katso kohdasta [Vastaavuusvalinnat](#match-options) tapoja tämän toiminnon muokkaamiseksi.)

Mallikielessä tietyt merkit on varattu erityistoimintoja varten. Jos haluat käyttää näitä merkkejä mallissa, lisää merkin vasemmalle puolelle **\\** (kenoviiva) ilmaisemaan, että merkki tulee tulkita kirjaimellisesti tai käytä yhtä esimääritetyistä malleista. Erikoismerkit on lueteltu tässä taulukossa:

| Erikoismerkki | Kuvaus |
| --- | --- |
| **.** |piste |
| **?** |kysymysmerkki |
| **&#42;** |tähti |
| **\+** |plus |
| **( )** |sulkeet |
| **[ ]** |hakasulkeet |
| **{ }** |kaarisulkeet |
| **^** |sirkumfleksi |
| **$** |dollarimerkki |
| **&#124;** |pystyviiva tai putkimerkki |
| **\\** |kenoviiva |

Voit esimerkiksi saada vastaavuuden ”Hei?” käyttämällä mallia **"Hei\\?"**, jossa on kenoviiva ennen kysymysmerkkiä.

### <a name="predefined-patterns"></a>Esimääritetyt mallit
Esimääritettyjen mallien avulla voidaan yksinkertaisesti etsiä vastaavuuksia yhdelle merkkijoukon merkeistä tai usean merkin sarjalle. Käytä [merkkijonon yhdistämisoperaattoria **&**](operators.md) omien merkkijonojen yhdistämiseksi **Match**-luetteloinnin jäsenten kanssa:

| Match-luettelointi | Kuvaus | Säännönmukainen lauseke |
| --- | --- | --- |
| **Any** |Vastaa mitä tahansa merkkiä. |**.** |
| **Comma** |Vastaa pilkkua. |**,** |
| **Digit** |Vastaa yhtä numeroa (0–9). |**\\d** |
| **Email** |Vastaa sähköpostiosoitetta, joka sisältää ”at”-merkin (”\@”) ja toimialuenimen, joka sisältää pisteen (”.”) |**.+\@.+\\.[^\\.]{2,}** |
| **Hyphen** |Vastaa yhdysmerkkiä. |**\\-** |
| **LeftParen** |Vastaa vasenta suljetta ”(”. |**\\(** |
| **Letter** |Vastaa kirjainta. |**\\p{L}** |
| **MultipleDigits** |Vastaa yhtä tai useampaa numeroa. |**\\d+** |
| **MultipleLetters** |Vastaa yhtä tai useampaa kirjainta. |**\\p{L}+** |
| **MultipleNonSpaces** |Vastaa yhtä tai useampaa merkkiä, joka ei ole välilyöntimerkki (välilyönti, sarkain, uusi rivi). |**\\S+** |
| **MultipleSpaces** |Vastaa yhtä tai useampaa välilyöntimerkkiä (välilyönti, sarkain, uusi rivi). |**\\S+** |
| **NonSpace** |Vastaa yhtä merkkiä, joka ei ole välilyöntimerkki. |**\\S** |
| **OptionalDigits** |Vastaa nollaa, yhtä tai useampaa merkkiä. |**\\d** |
| **OptionalLetters** |Vastaa nollaa, yhtä tai useampaa kirjainta. |**\\p{L}** |
| **OptionalNonSpaces** |Vastaa nollaa, yhtä tai useampaa merkkiä, jotka eivät ole välilyöntimerkkejä. |**\\S** |
| **OptionalSpaces** |Vastaa nollaa, yhtä tai useampaa välilyöntimerkkiä. |**\\s** |
| **Period** |Vastaa pistettä (”.”). |**\\.** |
| **RightParen** |Vastaa oikeaa suljetta ”)”. |**\\)** |
| **Space** |Vastaa välilyöntimerkkiä. |**\\s** |

Esimerkiksi malli **"A" & MultipleDigits** vastaa kirjainta ”A”, jonka jälkeen esiintyy yksi tai useampi numero.  

### <a name="regular-expressions"></a>Säännönmukaiset lausekkeet
**IsMatch**-funktion käyttämä malli on *säännönmukainen lauseke*. Yllä kuvatut tavalliset merkit ja esimääritetyt mallit auttavat rakentamaan säännönmukaisen lausekkeen.  

Säännönmukaiset lausekkeet ovat hyvin tehokkaita, ne ovat saatavilla useissa ohjelmointikielissä ja niitä käytetään useisiin eri tarkoituksiin. Tässä artikkelissa ei voida kuvailla kaikkia säännönmukaisten lausekkeiden ominaisuuksia, mutta verkossa on saatavilla suuri määrä tietoja ja oppaita.  

Säännönmukaisille lausekkeille on eri kielioppivaihtoehtoja. PowerApps käyttää JavaScript-kieliopin muunnelmaa. Katso lisätietoja kohdasta [säännönmukaisen lausekkeen syntaksi](http://msdn.microsoft.com/library/1400241x.aspx).

Yllä olevan **Match**-luetteloinnin taulukon luetteloinnit laajentuvat säännönmukaisiksi lausekkeiksi ja ”Säännönmukainen lauseke” -sarakkeen merkkijono määrittelee kyseisen lausekkeen.

## <a name="match-options"></a>Vastaavuusvalinnat
Voit muokata **IsMatch**-funktion toimintaa määrittämällä yhden tai useamman valinnan, joita voidaan yhdistellä käyttämällä merkkijonon yhdistämisoperaattoria (**&amp;**).  

**IsMatch** testaa oletuksena koko merkkijonon täyttä vastaavuutta.

| MatchOptions-luettelointi | Kuvaus | Vaikutus säännönmukaiseen lausekkeeseen |
| --- | --- | --- |
| **BeginsWith** |Mallin on vastattava tekstin alkua. |Lisää säännönmukaisen lausekkeen alkuun **^**-merkin. |
| **Complete** |Oletus.  Tämän mallin täytyy vastata koko tekstiä alusta loppuun. |Lisää säännönmukaisen merkkijonon alkuun **^**-merkin ja loppuun **$**-merkin. |
| **Contains** |Tämän mallin täytyy olla jossakin kohdassa tekstiä mutta sen ei tarvitse olla alussa tai lopussa. |Ei muokkaa säännönmukaista lauseketta. |
| **EndsWith** |Tämän mallin täytyy vastata tekstin loppua. |Lisää säännönmukaisen lausekkeen loppuun **$**-merkin. |
| **IgnoreCase** |Käsittelee kirjaimia niin, että kirjainkoko ei ole merkitsevä. Oletuksena vastaavuuksissa kirjainkoko on merkitsevä. |Ei muokkaa säännönmukaista lauseketta. |
| **Multiline** |Etsii vastaavuutta useilta riveiltä. |Ei muokkaa säännönmukaista lauseketta. |

## <a name="syntax"></a>Syntaksi
**IsMatch**( *Text*, *Pattern* [, *Options* ] )

* *Text* – Pakollinen.  Testattava merkkijono.
* *Pattern* – Pakollinen.  Testattava malli merkkijonona.  Yhdistele **Match**-luetteloinnin määrittelemiä malleja tai anna säännönmukainen lauseke.
* *Options* – Valinnainen.  Merkkijonoyhdistelmä **MatchOptions**-luetteloinnin arvoista.  Oletuksena käytetään valintaa **MatchOptions.Complete**.

## <a name="examples"></a>Esimerkkejä
### <a name="ordinary-characters"></a>Tavalliset merkit
Kuvitellaan, että sovelluksesi sisältää **Tekstisyöte**-ohjausobjektin nimeltä **TextInput1**.  Käyttäjä syöttää tähän ohjausobjektiin arvoja, jotka tallennetaan tietokantaan.   

Käyttäjä kirjoittaa **TextInput1**-kohtaan **Hei maailma**.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **IsMatch( TextInput1.Text, "Hei maailma" )** |Testaa, vastaako käyttäjän syöte tarkalleen merkkijonoa ”Hei maailma”. |**tosi** |
| **IsMatch( TextInput1.Text, "Hyvästi" )** |Testaa, vastaako käyttäjän syöte tarkalleen merkkijonoa ”Hyvästi”. |**epätosi** |
| **IsMatch( TextInput1.Text, "hei", Contains )** |Testaa, sisältääkö käyttäjän syöte sanan ”hei” (kirjainkoko on merkityksellinen). |**epätosi** |
| **IsMatch( TextInput1.Text, "hei", Contains & IgnoreCase )** |Testaa, sisältääkö käyttäjän syöte sanan ”hei” (kirjainkoko ei ole merkityksellinen). |**tosi** |

### <a name="predefined-patterns"></a>Esimääritetyt mallit

|                                                            Kaava                                                            |                                                                Kuvaus                                                                |  Tulos   |
|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| **IsMatch( "123-45-7890", Digit & Digit & Digit & Hyphen & Digit & Digit & Hyphen & Digit & Digit & Digit & Digit & Digit )** |                                              Vastaa Yhdysvaltojen sosiaaliturvatunnusta                                               | **tosi**  |
|                                           **IsMatch( "joan@contoso.com", Email )**                                            |                                                         Vastaa sähköpostiosoitetta                                                          | **tosi**  |
|                              **IsMatch( "123.456", MultipleDigits & Period & OptionalDigits )**                               |                                   Vastaa, kun kyseessä on numerojono, jonka jälkeen on piste ja sitten nolla tai useampia numeroita.                                   | **tosi**  |
|                                **IsMatch( "123", MultipleDigits & Period & OptionalDigits )**                                 | Vastaa, kun kyseessä on numerojono, jonka jälkeen on piste ja sitten nolla tai useampia numeroita. Tekstissä ei ole pistettä, joten tälle mallille ei löydy vastaavuutta. | **epätosi** |

### <a name="regular-expressions"></a>Säännönmukaiset lausekkeet

|                                                                              Kaava                                                                              |                                                                                                                                  Kuvaus                                                                                                                                   |  Tulos   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
|                                                                    **IsMatch( "986", "\d+" )**                                                                    |                                                                                                                    Vastaa kokonaislukua, joka on suurempi kuin nolla.                                                                                                                     | **tosi**  |
|                                                               **IsMatch( "1.02", "\d+(\.\d\d)?" )**                                                               |                                        Vastaa positiivista valuuttasummaa. Jos syöte sisältää desimaalierottimen, syötteen täytyy myös sisältää 2 numeroa sen jälkeen. Esimerkiksi 3.00 on kelvollinen, mutta 3.1 ei.                                         | **tosi**  |
|                                                            **IsMatch( "-4.95", "(-)?\d+(\.\d\d)?" )**                                                             |                                                        Vastaa positiivista tai negatiivista valuuttasummaa. Jos syöte sisältää desimaalierottimen, syötteen täytyy myös sisältää 2 numeroa sen jälkeen.                                                        | **true**  |
|                                                         **IsMatch( "111-11-1111", "\d{3}-\d{2}-\d{4}" )**                                                         | Vastaa Yhdysvaltojen sosiaaliturvatunnusta.  Vahvistaa annetun syötekentän muodon, tyypin ja pituuden. Vastattavan merkkijonon täytyy sisältää 3 numeroa, joiden perässä on viiva, sitten 2 numeroa, viiva ja 4 numeroa. | **true**  |
|                                                         **IsMatch( "111-111-111", "\d{3}-\d{2}-\d{4}" )**                                                         |                                                                                               Sama kuin edellisessä esimerkissä, mutta yksi syötteen viiva on väärässä paikassa.                                                                                               | **false** |
|                                         **IsMatch( "weakpassword", "(?!^[0-9]\*$)(?!^[a-zA-Z]\*$)([a-zA-Z0-9]{8,10})" )**                                         |                                        Vahvistaa vahvan salasanan, jonka täytyy sisältää 8, 9 tai 10 merkkiä sekä vähintään yhden numeron ja yhden kirjaimen. Merkkijono ei saa sisältää erikoismerkkejä.                                        | **epätosi** |
| **IsMatch( "<http://microsoft.com>", "(ht&#124;f)tp(s?)\:\/\/\[0-9a-zA-Z\]([-.\w]\*[0-9a-zA-Z])\*(:(0-9)\*)\*(\/?)([a-zA-Z0-9\-\.\?\,\'\/\\\+&amp;%\$#_]\*)?" )** |                                                                                                                     Vahvistaa http-, https- tai ftp-url-osoitteen.                                                                                                                      | **tosi**  |


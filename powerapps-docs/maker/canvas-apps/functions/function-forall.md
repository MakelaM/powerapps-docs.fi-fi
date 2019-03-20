---
title: ForAll-funktio | Microsoft Docs
description: PowerAppsin ForAll-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/26/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f538d785b9655b94a44a79c3299e979bbfe88883
ms.sourcegitcommit: ba5542ff1c815299baa16304c6e0b5fed936e776
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54308773"
---
# <a name="forall-function-in-powerapps"></a>ForAll-funktio PowerAppsissa
Laskee arvot ja suorittaa toiminnot [taulukon](../working-with-tables.md) kaikille [tietueille](../working-with-tables.md#records).

## <a name="description"></a>Kuvaus
**ForAll**-funktio arvioi kaavan taulukon kaikille tietueille.  Kaava voi laskea arvon ja suorittaa toimintoja, kuten tietojen muokkaus tai yhteyden käyttäminen.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

### <a name="return-value"></a>Paluuarvo
Jokaisen kaavan arvioinnin tulos palautetaan taulukossa samassa järjestyksessä kuin syöttötaulukko.

Jos kaavan tulos on yksi arvo, tuloksena saatavassa taulukossa on yksi sarake.  Jos kaavan tulos on tietue, tuloksena saatava taulukko sisältää tietueet, joissa on samat sarakkeet kuin tulostietueessa.  

Jos kaavan tulos on *tyhjä* arvo, tulostaulukossa ei ole tietuetta kyseiselle syöttötietueelle.  Tässä tapauksessa tulostaulukossa on vähemmän tietueita kuin lähdetaulukossa.

### <a name="taking-action"></a>Toimenpiteet
Kaava voi sisältää funktioita, jotka suorittavat toiminnon, kuten tietolähteen tietueiden muokkaaminen **[Patch](function-patch.md)**- ja **[Collect](function-clear-collect-clearcollect.md)**-funktioilla.  Kaava voi myös kutsua menetelmiä yhteyksillä.  Tietuetta kohden voidaan suorittaa useita toimintoja [**;**-operaattorilla](operators.md). Et voi muokata taulukkoa, joka on **ForAll**-funktion kohde.

Kun kirjoitat kaavaa, pidä mielessä, että tietueita voidaan käsitellä missä tahansa järjestyksessä, ja kun mahdollista, rinnakkain.  Taulukon ensimmäinen tietue voidaan käsitellä viimeisen tietueen jälkeen.  Pyri välttämään järjestysriippuvuuksia.  Tästä syystä **ForAll**-funktion sisällä ei voida käyttää funktioita **[UpdateContext](function-updatecontext.md)**, **[Clear](function-clear-collect-clearcollect.md)** ja **[ClearCollect](function-clear-collect-clearcollect.md)**, koska ne voisivat helposti sisältää muuttujia, joihin tämä vaikuttaisi.  Voit käyttää **[Collect](function-clear-collect-clearcollect.md)**-funktiota, mutta tietueiden lisäämisjärjestys on määrittämätön.

Useat tietolähteitä muokkaavat funktiot, kuten **Collect**, **Remove** ja **Update**, antavat paluuarvonaan muutetun tietolähteen.  Nämä paluuarvot voivat olla suuria ja kuluttaa merkittävästi resursseja, jos ne palautetaan jokaiselle **ForAll**-taulukon tietueelle.  Nämä paluuarvot eivät myöskään välttämättä vastaa odotuksiasi, sillä **ForAll** voi toimia rinnakkain ja sivuvaikutuksena funktiot eivät välttämättä saa odotettuja tuloksia.  Onneksi jos **ForAll**-funktion paluuarvoa ei tosiasiassa käytetä, kuten tietojen muokkausfunktioille on usein tyypillistä, paluuarvoa ei luoda, mikä eliminoi resurssi- ja järjestysongelmat.  Jos kuitenkin käytät **ForAll**-funktion ja jonkin tietolähteen palauttavan funktion tulosta, harkitse tuloksen rakennetta tarkkaan ja testaa toimintoa ensin pienillä tietojoukoilla.  

### <a name="alternatives"></a>Vaihtoehtoja
Monet PowerAppsin funktiot voivat käsitellä yhden tai useamman arvon kerrallaan yhden sarakkeen taulukon avulla.  Esimerkiksi **Len**-funktio voi käsitellä tekstiarvoista muodostuvan taulukon ja palauttaa pituuksien taulukon samalla tavalla kuin **ForAll** voi.  Tämä voi poistaa **ForAll**-funktion tarpeen monissa tapauksissa, ja se voi olla myös tehokkaampi ja helpompi lukea.

Toinen huomioon otettava seikka on, että **ForAll** ei ole delegoitavissa, toisin kuin muut funktiot, kuten **Filter**.  

### <a name="delegation"></a>Delegointi
[!INCLUDE [delegation-no-one](../../../includes/delegation-no-one.md)]

## <a name="syntax"></a>Syntaksi
**ForAll**( *Taulukko*, *Kaava* )

* *Taulukko* – Pakollinen. Taulukko, jolle toiminto suoritetaan.
* *Kaava* – Pakollinen.  *Taulukon* kaikkien tietueiden arviointiin käytettävä kaava.

## <a name="examples"></a>Esimerkkejä
### <a name="calculations"></a>Laskutoimitukset
Seuraavissa esimerkeissä käytetään **Squares**-[tietolähdettä](../working-with-data-sources.md):

![](media/function-forall/squares.png)

Voit luoda tämän tietolähteen kokoelmana asettamalla jonkin **painike**-ohjausobjektin **OnSelect**-ominaisuudeksi tämän kaavan, avaamalla esikatselutilan ja sitten napsauttamalla tai napauttamalla painiketta:

`ClearCollect( Squares, [ "1", "4", "9" ] )`

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **ForAll(&nbsp;Squares, Sqrt(&nbsp;Value&nbsp;)&nbsp;)**<br><br>**Sqrt(&nbsp;Squares&nbsp;)** |Laskee kaikille syöttötaulukon tietueille **Value**-sarakkeen neliöjuuren.  **Sqrt**-funktiota voidaan käyttää yhden sarakkeen taulukolle, joten tämä esimerkki voidaan toteuttaa käyttämättä **ForAll**-funktiota. |<style> img { max-width: none } </style> ![](media/function-forall/sqrt.png) |
| **ForAll(&nbsp;Squares, Power(&nbsp;Value,&nbsp;3&nbsp;)&nbsp;)** |Nostaa kaikkien syöttötaulukon tietueiden **Value**-sarakkeen kolmanteen potenssiin.  **Power**-funktio ei tue yhden sarakkeen taulukoita. Siksi tässä tapauksessa täytyy käyttää **ForAll**-funktiota. |<style> img { max-width: none } </style> ![](media/function-forall/power3.png) |

### <a name="using-a-connection"></a>Yhteyden käyttäminen
Seuraavissa esimerkeissä käytetään **Expressions**[-tietolähdettä](../working-with-data-sources.md):

![](media/function-forall/translate.png)

Voit luoda tämän tietolähteen kokoelmana asettamalla jonkin **painike**-ohjausobjektin **OnSelect**-ominaisuudeksi tämän kaavan, avaamalla esikatselutilan ja sitten napsauttamalla tai napauttamalla painiketta:

`ClearCollect( Expressions, [ "Hello", "Good morning", "Thank you", "Goodbye" ] )`

Tämä esimerkki käyttää myös [Microsoft Translator](../connections/connection-microsoft-translator.md) -yhteyttä.  Katso tämän yhteyden lisäämiseksi sovellukseesi [yhteyksien hallintaa](../add-manage-connections.md) käsittelevä aihe.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **ForAll( Expressions, MicrosoftTranslator.Translate( Value, "es" ) )** |Kaikkien Expressions-taulukon tietueiden **Value**-sarakkeen sisältö käännetään espanjaksi (lyhenne ”es”). |<style> img { max-width: none } </style> ![](media/function-forall/translate-es.png) |
| **ForAll( Expressions, MicrosoftTranslator.Translate( Value, "fr" ) )** |Kaikkien Expressions-taulukon tietueiden **Value**-sarakkeen sisältö käännetään ranskaksi (lyhenne ”fr”). |<style> img { max-width: none } </style> ![](media/function-forall/translate-fr.png) |

### <a name="copying-a-table"></a>Taulukon kopioiminen
Joskus tietoja täytyy suodattaa, muovata, lajitella tai muokata.  PowerAppsissa on tätä varten useita funktioita, kuten **Filter**, **AddColumns**, ja **Sort**.  PowerApps käsittelee jokaista taulukkoa arvona ja mahdollistaa sen kulun kaavojen läpi helposti.      

Joskus on myös tarve tehdä kopio tästä tuloksesta myöhempää käyttöä varten.  Joskus saatat myös haluta siirtää tietoja yhdestä tietolähteestä toiseen.  PowerApps sisältää **Collect**-funktion tietojen kopiointia varten.

Mieti kuitenkin ennen kopion tekemistä, onko se varmasti tarpeen.  Useissa tapauksissa ratkaisuksi riittää pohjana olevan tietolähteen suodatus tai muovaaminen kaavalla tarpeen mukaan. Kopion tekemisen haittapuolia ovat:

* Jos samasta tiedosta on kaksi kopiota, ne eivät välttämättä pysy synkronoituna.  
* Kopion tekeminen voi käyttää paljon tietokoneen muistia, verkon kaistanleveyttä ja aikaa.  
* Useimmissa tietolähteissä kopioimista ei voi delegoida, mikä rajoittaa siirrettävien tietojen määrää.      

Seuraavissa esimerkeissä käytetään **Products**[-tietolähdettä](../working-with-data-sources.md):

![](media/function-forall/prod.png)

Voit luoda tämän tietolähteen kokoelmana asettamalla jonkin **painike**-ohjausobjektin **OnSelect**-ominaisuudeksi tämän kaavan, avaamalla esikatselutilan ja sitten napsauttamalla tai napauttamalla painiketta:

```powerapps-dot
ClearCollect( Products, 
    Table( 
        { Product: "Widget",    'Quantity Requested': 6,  'Quantity Available': 3 }, 
        { Product: "Gadget",    'Quantity Requested': 10, 'Quantity Available': 20 },
        { Product: "Gizmo",     'Quantity Requested': 4,  'Quantity Available': 11 },
        { Product: "Apparatus", 'Quantity Requested': 7,  'Quantity Available': 6 } 
    )
)
```

Tavoitteena on käyttää työskentelyyn johdettua taulukkoa, joka sisältää vain ne kohteet, joita on pyydetty enemmän kuin on saatavilla ja joita täytyy tilata:

![](media/function-forall/prod-order.png)  

Voimme suorittaa tämän tehtävän eri tavoilla, joista kaikki tuottavat saman lopputuloksen ja joilla kaikilla on omat hyvät ja huonot puolensa.

#### <a name="table-shaping-on-demand"></a>Taulukon muovaaminen pyydettäessä
Älä tee kopiota!  Voimme käyttää seuraavaa kaavaa kaikkialla, missä sitä tarvitsemme:

```powerapps-dot
// Table shaping on demand, no need for a copy of the result
ShowColumns( 
    AddColumns( 
        Filter( Products, 'Quantity Requested' > 'Quantity Available' ), 
        "Quantity To Order", 'Quantity Requested' - 'Quantity Available' 
    ), 
    "Product", 
    "Quantity To Order"
)
```

**Filter**- ja **AddColumns**-funktiot luovat [tietuealueen](../working-with-tables.md#record-scope), jonka avulla suoritetaan vertailu- ja vähennystoiminnot jokaisen tietueen **”Quantity Requested”**- ja **”Quantity Available”** -kentille tässä järjestyksessä.

Tässä esimerkissä **Filter**-funktio voidaan delegoida.  Tämä on tärkeää, sillä se voi hakea kaikki kriteerit täyttävät tuotteet, vaikka tämä merkitsisi vain muutamaa tietuetta miljoonien tietueiden taulukossa.  Tällä hetkellä **ShowColumns**- ja **AddColumns**-funktioita ei voi delegoida, joten varsinainen tilausta vaativien tuotteiden määrä on rajoitettu.  Jos tiedät, että tämä tulos on aina suhteellisen pieni, tämä menetelmä on sopiva.

Ja koska emme tehneet kopiota, ei ole olemassa ylimääräistä tietojen kopiota, jota täytyisi hallita tai joka voisi vanhentua.  

#### <a name="forall-on-demand"></a>ForAll pyydettäessä
Toinen menetelmä on käyttää **ForAll**-funktiota taulukkoa muovaavien funktioiden korvikkeena:

```powerapps-dot
ForAll( Products, 
    If( 'Quantity Requested' > 'Quantity Available', 
        { 
            Product: Product, 
            'Quantity To Order': 'Quantity Requested' - 'Quantity Available' 
        } 
    ) 
)
```

Tämä kaava voi olla joillekin yksinkertaisempi lukea ja kirjoittaa.

Mikään **ForAll**-funktion osa ei ole delegoitavissa.  Vain ensimmäinen **Products**-taulukon osa arvioidaan, mikä voi olla ongelma hyvin suuren taulukon tapauksessa.  Koska edellisessä esimerkissä **Filter**-funktio voidaan delegoida, se voi olla parempi vaihtoehto suurille tietojoukoille.

#### <a name="collect-the-result"></a>Tuloksen kerääminen
Joissakin tapauksissa voi olla tarpeen kopioida tiedot.  Tietoja voi olla tarpeen siirtää yhdestä tietolähteestä toiseen.  Tässä esimerkissä tilaukset lähetetään toimittajan järjestelmän **NewOrder**-taulukon kautta.  Nopeita käyttäjän toimia varten voi olla tarpeen tallentaa välimuistiin paikallinen kappale, jotta vältytään palvelinviiveiltä.

Käytämme samaa taulukon muovaamista kuin kahdessa edellisessä esimerkissä, mutta kaappaamme tulokset kokoelmaan:

```powerapps-dot
ClearCollect( NewOrder, 
    ShowColumns( 
        AddColumns( 
            Filter( Products, 'Quantity Requested' > 'Quantity Available' ), 
            "Quantity To Order", 'Quantity Requested' - 'Quantity Available' 
        ), 
        "Product", 
        "Quantity To Order"
    )
)
```

```powerapps-dot
ClearCollect( NewOrder, 
    ForAll( Products, 
        If( 'Quantity Requested' > 'Quantity Available', 
            { 
                Product: Product, 
                'Quantity To Order': 'Quantity Requested' - 'Quantity Available' 
            } 
        } 
    )
)
```

**ClearCollect**- ja **Collect**-funktioita ei voi delegoida.  Tämän vuoksi tällä menetelmällä ei voida siirtää suuria määriä tietoja.

#### <a name="collect-within-forall"></a>ForAll-funktion sisäinen Collect-funktio
Lopuksi voimme suorittaa **Collect**-funktion suoraan **ForAll**-funktion sisällä:

```powerapps-dot
Clear( ProductsToOrder ); 
ForAll( Products, 
    If( 'Quantity Requested' > 'Quantity Available', 
        Collect( NewOrder,  
            { 
                Product: Product, 
                'Quantity To Order': 'Quantity Requested' - 'Quantity Available' 
            } 
        )
    )
)
```

Muistutuksena **ForAll**-funktiota ei voi tällä hetkellä delegoida.  Jos **Products**-taulukkomme on suuri, **ForAll** tarkastelee vain tietueidemme ensimmäistä joukkoa, joten meiltä saattaa jäädä huomaamatta tuotteita, joita täytyy tilata.  Tämä menetelmä sopii kuitenkin taulukoille, joiden tiedämme säilyvän pieninä.

Huomaa, että emme kaappaa **ForAll**-funktion tulosta.  Sisältä päin tehdyt **Collect**-funktiokutsut palauttavat kaikille tietueille **NewOrder**-tietolähteen, mikä voisi merkitä suurta tietomäärää, jos se kaapattaisiin.  


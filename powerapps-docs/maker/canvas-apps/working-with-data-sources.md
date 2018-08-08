---
title: Pohjaan perustuvien sovellusten tietolähteiden ymmärtäminen | Microsoft Docs
description: Viitetietoja yhteyksien ja tietolähteiden käyttämiseen pohjaan perustuvissa sovelluksissa.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 03/08/2017
ms.author: gregli
ms.openlocfilehash: a4dd3d2d21aa8e4f8501c9bc9812ba6658683f03
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/02/2018
ms.locfileid: "39470381"
---
# <a name="understand-data-sources-for-canvas-apps-in-powerapps"></a>Pohjaan perustuvien sovellusten tietolähteiden ymmärtäminen PowerAppsissa

PowerAppsissa useimmat pohjaan perustuvat sovellukset käyttävät ulkoisia tietoja eli **tietolähteitä**, jotka on tallennettu pilvipalveluihin. Yleinen esimerkki on taulukko Excel-tiedostossa, joka on tallennettu OneDrive for Businessiin. Sovellukset käyttävät näitä tietolähteitä käyttämällä **yhteyksiä**.

Tässä artikkelissa käsitellään erilaisia tietolähteitä ja taulukkotietolähteiden käyttämistä.

On helppoa luoda sovellus, joka suorittaa perustason lukemisen ja kirjoittamisen tietolähteeseen. Joskus tarvitset kuitenkin parempia hallintakeinoja tiedon kulkuun sovelluksiisi ja sovelluksistasi.  Tässä artikkelissa kuvataan, miten **[Patch](functions/function-patch.md)**-, **[DataSourceInfo](functions/function-datasourceinfo.md)**-, **[Validate](functions/function-validate.md)**- ja **[Errors](functions/function-errors.md)**-funktiot tarjoavat parempaa hallintaa.

## <a name="kinds-of-data-sources"></a>Tietolähdetyypit

Tietolähteet voidaan yhdistää pilvipalveluun, tai ne voivat olla sovelluksen paikallisia tietolähteitä.

### <a name="connected-data-sources"></a>Yhdistetyt tietolähteet

Yleisin tietolähde on **taulukko**, jota voit käyttää tiedon hakemiseen ja tallentamiseen. Voit käyttää tietolähteiden **liitoksia** tietojen lukemiseen ja kirjoittamiseen Microsoft Excel -työkirjoihin, SharePoint-luetteloihin, SQL-taulukoihin ja moniin muihin muotoihin, jotka voidaan tallentaa pilvipalveluihin, kuten OneDrive for Businessiin, DropBoxiin ja SQL Serveriin.

Taulukkojen lisäksi muita tietolähteitä ovat sähköposti, kalenterit, Twitter ja ilmoitukset, mutta tässä artikkelissa ei käsitellä näitä tietolähteitä.

### <a name="local-data-sources"></a>Paikalliset tietolähteet

Käyttämällä **[Valikoima](controls/control-gallery.md)**-, **[Näytä lomake](controls/control-form-detail.md)**- ja **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekteja on helppoa luoda sovellus, joka lukee ja kirjoittaa tietoa tietolähteestä.  Pääset alkuun lukemalla artikkelin [Tutustu tietolomakkeisiin](working-with-forms.md).  

Kun pyydät PowerAppsia luomaan sovelluksen tiedoista, näitä ohjausobjekteja käytetään. Sovellus käyttää taustalla sisäistä taulukkoa tietolähteestä tulevien tietojen tallentamiseen ja muokkaamiseen.

[Kokoelma](working-with-data-sources.md#collections) on erityinen tietolähde. Se tallennetaan paikallisesti sovellukseen eikä sillä ole tukena yhteyttä pilvipalveluun, joten saman käyttäjän tai eri käyttäjien tietoja ei voi jakaa laitteiden välillä. Kokoelmia voidaan ladata ja tallentaa paikallisesti.

### <a name="kinds-of-tables"></a>Taulukkotyypit

PowerApps-sovelluksen sisäiset taulukot ovat kiinteitä arvoja, kuten numero tai merkkijono on arvo. Sisäisiä taulukoita ei tallenneta mihinkään, ja ne ovat olemassa vain sovelluksen muistissa. Et voi muokata taulukon rakennetta tai tietoa suoraan. Voit sen sijaan luoda uuden taulukon käyttämällä kaavaa. Kaavan avulla voit tehdä muokatun kopion alkuperäisestä taulukosta.

Ulkoiset taulukot tallennetaan tietolähteeseen myöhempää hakemista ja jakamista varten.  PowerApps tarjoaa tallennetun tiedon lukemiseen ja kirjoittamiseen tarkoitettuja yhteyksiä.  Voit käyttää useita tietotaulukoita yhteyden sisällä.  Valitset sovelluksessa käytettävät taulukot, ja niistä jokaisesta tulee erillinen *tietolähde*.  

Saat lisätietoja [Taulukoiden käsitteleminen](working-with-tables.md) -kohdasta, jossa kerrotaan sisäisistä taulukoista yksityiskohtaisemmin. Kohdasta on myös hyötyä pilvipalvelussa olevien ulkoisten taulukoiden kanssa.

## <a name="working-with-tables"></a>Taulukoiden käsitteleminen
Voit käyttää taulukon tietolähteitä samalla tavalla kuin sisäistä PowerApps-taulukkoa.  Sisäisen taulukon tavoin jokaisella tietolähteellä on [tietueet](working-with-tables.md#records), [sarakkeet](working-with-tables.md#columns) ja ominaisuudet, joita voit käyttää kaavoissa. Lisäksi:

* Tietolähteellä on samat sarakenimet ja tietotyypit kuin yhteyden pohjalla olevalla taulukolla.
  
    > [!NOTE]
  > SharePoint- ja Excel-tietolähteissä, joissa on välilyönnin sisältäviä sarakenimiä, PowerApps korvaa välilyönnit merkkijonolla **\_x0020\_**. Esimerkiksi, **”Sarakkeen Nimi”** SharePointissa tai Excelissä näkyy muodossa **”Sarakkeen_x0020_Nimi”** PowerAppsissa, kun se näytetään tietoasettelussa tai sitä käytetään kaavassa.
* Tietolähde ladataan palvelusta automaattisesti, kun sovellus ladataan.  Voit pakottaa tietojen päivityksen käyttämällä **[Refresh](functions/function-refresh.md)**-funktiota.
* Kun käyttäjät suorittavat sovelluksen, he voivat luoda, muokata ja poistaa tietueita ja siirtää muutokset takaisin palvelussa pohjalla olevaan taulukkoon.
  * Tietueita voidaan luoda **[Patch](functions/function-patch.md)**- ja **[Collect](functions/function-clear-collect-clearcollect.md)**-funktioilla.  
  * Tietueita voidaan muokata **[Patch](functions/function-patch.md)**-, **[Update](functions/function-update-updateif.md)**- ja **[UpdateIf](functions/function-update-updateif.md)**-funktioilla.
  * Tietueita voidaan poistaa **[Remove](functions/function-remove-removeif.md)**- ja **[RemoveIf](functions/function-remove-removeif.md)**-funktioilla.
  * Tietolähteen käsittelyssä ilmenevät virheet ovat saatavilla **[Errors](functions/function-errors.md)**-funktiolla.
* **[DataSourceInfo](functions/function-datasourceinfo.md)**-, **[Defaults](functions/function-defaults.md)**- ja **[Validate](functions/function-validate.md)**-funktiot tarjoavat tietolähteestä tietoja, joiden avulla voit optimoida käyttökokemuksen.

### <a name="creating-data-sources"></a>Tietolähteiden luominen
PowerAppsia ei voi käyttää yhdistetyn tietolähteen luomiseen tai sen rakenteen muokkaamiseen. Tietolähteen on oltava palvelussa valmiina. Jotta voit esimerkiksi luoda taulukon OneDriveen tallennetussa Excel-työkirjassa, käytät ensin Excel Onlinea OneDrivessa työkirjan luomiseen. Seuraavaksi luot siihen yhteyden sovelluksestasi.  

Kokoelmatietolähteitä *voidaan* myös luoda ja muokata sovelluksen sisällä, mutta ne ovat vain väliaikaisia.

### <a name="display-one-or-more-records"></a>Yhden tai usean tietueen näyttäminen
![](media/working-with-data-sources/reading-from-a-datasource.png) Yllä olevassa kaaviossa näkyy tiedon kulku, kun sovellus lukee tiedot tietolähteestä:

* Tiedot tallennetaan ja jaetaan tallennuspalvelun kautta (tässä tapauksessa Office 365 -sivuston SharePoint-luettelo).
* Yhteys asettaa nämä tiedot sovelluksen käytettäväksi.  Yhteys suorittaa käyttäjän todentamisen, jotta tietoja voidaan käyttää.
* Kun sovellus käynnistetään tai **[Refresh](functions/function-refresh.md)**-funktiota painetaan, tiedot haetaan paikallista käyttöä varten yhteydestä sovelluksen tietolähteeseen.
* Kaavoja käytetään tietojen lukemiseen ja niiden paljastamiseen käyttäjän näkemissä ohjausobjekteissa. Voit näyttää tietolähteen tietueet käyttämällä valikoimaa näytöllä ja liittämällä **[Items](controls/properties-core.md)**-ominaisuuden tietolähteeseen: **Gallery.Items = DataSource**.  Ohjausobjekteja liitetään valikoiman sisällä ja valikoimaan käyttämällä ohjausobjektien **[Default](controls/properties-core.md)**-ominaisuutta.  
* Tietolähde on myös taulukko.  Voit siis käyttää **[Filter](functions/function-filter-lookup.md)**-, **[Sort](functions/function-sort.md)**-, **[AddColumns](functions/function-table-shaping.md)**-funktioita ja muita funktioita tietolähteen säätämiseen ja täydentämiseen ennen sen käyttämistä kokonaisuudessaan.  Voit myös käyttää **[Lookup](functions/function-filter-lookup.md)**-, **[First](functions/function-first-last.md)**-, **[Last](functions/function-first-last.md)**-funktioita ja muita funktioita yksittäisten tietueiden käsittelemiseen.

### <a name="modify-a-record"></a>Tietueen muokkaaminen
Edellisessä osiossa sait tietää, miten tietolähdettä luetaan.  Huomaa, että yllä olevassa kaaviossa olevat nuolet ovat yksi tapa.  Muutoksia tietolähteeseen ei siirretä takaisin samojen kaavojen kautta, joilla tieto haettiin.  Niiden sijaan käytetään uusia kaavoja.  Usein tietueen muokkaamiseen käytetään eri näyttöä kuin tietueiden selaamiseen, erityisesti mobiililaitteessa.

Huomaa: jotta voit muokata tietolähteen olemassa olevaa tietuetta, tietueen on oltava peräisin tietolähteestä.  Tietue on voinut kulkea valikoiman, [kontekstimuuttujan](working-with-variables.md#create-a-context-variable) ja useiden kaavojen läpi, mutta sen alkuperän tulisi olla jäljitettävissä takaisin tietolähteeseen.  Tämä on tärkeää, koska tietueen mukana kulkee lisätietoa, joka yksilöi sen ja varmistaa, että muokkaat oikeaa tietuetta.    

![](media/working-with-data-sources/writing-to-a-datasource.png) Yllä olevassa kaaviossa näkyy tiedonkulku tietolähteen päivittämisessä:

* **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekti tarjoaa säilön syötteen korteille, jotka koostuvat käyttäjäsyötteen ohjausobjekteista, kuten tekstinsyötön ohjausobjektista tai liukusäätimestä.  **[Tietolähde](controls/control-form-detail.md)**- ja **[Kohde](controls/control-form-detail.md)**-ominaisuuksia käytetään muokattavan tietueen tunnistamiseen.
* Jokaisella syötteen kortilla on **[Default](controls/properties-core.md)**-ominaisuus, joka asetetaan yleensä lomakkeen **ThisItem**-tietueen kenttään.  Tämän jälkeen syötteen kortissa olevat ohjausobjektit saavat syötearvonsa **[Default](controls/properties-core.md)**-ominaisuudesta.  Sinun ei yleensä tarvitse muokata tätä.
* Jokainen syötteen kortti paljastaa **[Update](controls/control-card.md)**-ominaisuuden.  Tämä ominaisuus yhdistää käyttäjän syötteen tietueen tiettyyn kenttään takaisin tietolähteeseen kirjoittamista varten.  Sinun ei yleensä tarvitse muokata tätä.
* Näytön painike tai kuvan ohjausobjekti antaa käyttäjän tallentaa muutokset tietueeseen.  Ohjausobjektin **[OnSelect](controls/properties-core.md)**-kaava kutsuu **[SubmitForm](functions/function-form.md)**-funktion suorittamaan tämän tehtävän.  **[SubmitForm](functions/function-form.md)** lukee korttien kaikki **[Update](controls/control-card.md)**-ominaisuudet ja kirjoittaa niiden avulla takaisin tietolähteeseen.
* Joskus voi esiintyä ongelmia.  Verkkoyhteys on saattanut katketa tai palvelu voi tehdä todennustarkistuksen, josta sovellus ei ole tiennyt.  Lomakkeen ohjausobjektin **Error**- ja **[ErrorKind](controls/control-form-detail.md)**-ominaisuudet tuovat tämän tiedon käytettäväksi, jotta voit näyttää sen käyttäjälle.  

Voit hallita prosessia tarkemmin käyttämällä myös **[Patch](functions/function-patch.md)**- ja **[Errors](functions/function-errors.md)**-funktiota.  **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekti paljastaa **[Updates](controls/control-form-detail.md)**-ominaisuuden, jotta voit lukea lomakkeessa olevien kenttien arvot.  Voit käyttää tätä ominaisuutta myös kutsuaksesi mukautetun liittimen ohittaen **Patch**- ja **SubmitForm**-funktiot kokonaan.

### <a name="validation"></a>Vahvistus
Ennen kuin teet muutoksen tietueeseen, sovelluksen tulee tehdä kaikki mahdollinen varmistaakseen, että muutos on hyväksyttävä.  Tähän on kaksi syytä:

* *Välitön palaute käyttäjälle*.  Paras hetki korjata ongelma on heti sen tapahtuessa, kun se on käyttäjällä tuoreessa muistissa.  Jokaisella kosketuksella tai näppäinpainalluksella voi tulla esiin punaista tekstiä, joka yksilöi ongelman syöttämisessä.
* *Vähemmän verkkoliikennettä ja pienempi käyttäjän viive*.  Mitä enemmän sovelluksessa havaitaan ongelmia, sitä vähemmän tarvitaan ongelmien tunnistamiseen ja ratkaisemiseen liittyviä verkkokeskusteluita.  Jokainen keskustelu vie aikaa, jolloin käyttäjän on odotettava, ennen kuin hän voi jatkaa.

PowerApps tarjoaa vahvistamiseen kaksi työkalua:

* Tietolähde voi antaa tietoja siitä, mikä kelpaa ja mikä ei.  Esimerkiksi numeroilla voi olla pienin ja suurin arvo, ja kuhunkin kohtaan voidaan edellyttää yhtä tai useampaa merkintää.  Voit käyttää näitä tietoja **[DataSourceInfo](functions/function-datasourceinfo.md)**-funktiolla.  
* **[Validate](functions/function-validate.md)**-funktio käyttää samoja tietoja tarkistaakseen yksittäisen sarakkeen tai koko tietueen arvon.

### <a name="error-handling"></a>Virheenkäsittely
Erinomaista, olet vahvistanut tietueesi.  On aika päivittää tietue **[Patch](functions/function-patch.md)**-funktiolla!

Voit silti edelleen törmätä ongelmiin.  Verkko ei toimi, vahvistus palvelussa epäonnistuu tai käyttäjällä ei ole oikeita oikeuksia – tässä vain muutamia ongelmia, joita sovelluksesi saattaa kohdata.  Sen täytyy vastata asianmukaisesti virhetilanteisiin, antaa käyttäjälle palautetta sekä tarjota ohjeita virheen korjaamiseen.  

Kun virheitä esiintyy tietolähteessä, sovelluksesi tallentaa virheen tiedot automaattisesti ja asettaa ne **[Errors](functions/function-errors.md)**-funktiolla käytettäviksi.  Virheet liittyvät tietueisiin, joissa ongelmat esiintyivät.  Jos käyttäjä voi korjata ongelman, kuten vahvistusongelman, hän voi lähettää tietueen uudelleen, jolloin virheet poistetaan.

Jos virhe esiintyy, kun tietue luodaan **[Patch](functions/function-patch.md)**- tai **[Collect](functions/function-clear-collect-clearcollect.md)**-funktiolla, ei ole tietuetta, johon virheet voitaisiin liittää.  Tässä tapauksessa **[Patch](functions/function-patch.md)** palauttaa *tyhjän*, ja sitä voi käyttää tietueargumenttina **[Errors](functions/function-errors.md)**-funktioon.  Luontivirheet tyhjennetään seuraavalla toiminnolla.

**[Errors](functions/function-errors.md)**-funktio palauttaa virhetietotaulukon.  Nämä tiedot voivat sisältää saraketietoja, jos virhe voidaan yhdistää tiettyyn sarakkeeseen.  Käytä saraketason virheviestejä otsikon ohjausobjekteissa, jotka ovat lähellä paikkaa, jossa sarake sijaitsee muokkausruudulla.  Käytä tietuetason virheviestejä, kun virhetaulukon **Sarake** on *tyhjä*, lähellä koko tietueen **Tallenna**-painiketta.  

### <a name="working-with-large-data-sources"></a>Suurten tietolähteiden käsitteleminen
Kun olet luomassa raportteja suurista tietolähteistä (mahdollisesti miljoonia tietueita), haluat minimoida verkkoliikenteen. Oletetaan, että haluat raportin kaikista New York Cityn asiakkaista, joiden Tilakoodi on ”Platina”. Ja että asiakastaulukkosi sisältää miljoonia tietueita.

**Et** halua tuoda näitä miljoonia asiakkaita sovellukseesi ja valita sitten haluamiasi asiakkaita. Haluat sen sijaan, että tämä valinta tehdään pilvipalvelussa, johon taulukkosi on tallennettu, ja vain valitut tietueet lähetetään verkon kautta.

Monet – mutta eivät kaikki – tietueiden valitsemiseen käytettävät funktiot voidaan *delegoida*. Tämä tarkoittaa, että ne suoritetaan pilvipalvelun sisällä. Ohjeet ovat kohdassa [Delegointi](delegation-overview.md).

## <a name="collections"></a>Kokoelmat
Kokoelmat ovat erityinen tietolähdetyyppi.  Ne tallennetaan paikallisesti sovellukseen, eikä niillä ole tukena pilvipalveluyhteyttä. Näin ollen saman käyttäjän tai eri käyttäjien tietoja ei voi jakaa laitteiden välillä.  Kokoelmat toimivat samalla tavoin kuin muut tietolähteet muutamaa poikkeusta lukuun ottamatta:

* Kokoelmia voidaan luoda dynaamisesti **[Collect](functions/function-clear-collect-clearcollect.md)**-funktiolla.  Yhteyspohjaisista tietolähteistä poiketen niitä ei tarvitse muodostaa etukäteen.
* Kokoelman sarakkeita voidaan muokata milloin tahansa käyttämällä **[Collect](functions/function-clear-collect-clearcollect.md)**-funktiota.
* Kokoelmat sallivat tietueiden kaksoiskappaleet.  Kokoelmassa voi olla useampia kopioita samasta tietueesta.  Funktiot, kuten **[Remove](functions/function-remove-removeif.md)**, toimivat ensimmäisen löytämänsä osuman kohdalla, ellei **All**-argumenttia ole annettu.
* Voit käyttää **[SaveData](functions/function-savedata-loaddata.md)**- ja **[LoadData](functions/function-savedata-loaddata.md)**-funktioita kokoelman kopion tallentamiseen ja lataamiseen uudelleen.  Tiedot tallennetaan yksityiseen sijaintiin, jota muut käyttäjät, sovellukset tai laitteet eivät voi käyttää.
* **[Vie](controls/control-export-import.md)**- ja **[Tuo](controls/control-export-import.md)**-ohjausobjektien avulla voit tallentaa ja ladata valikoiman kopion uudelleen tiedostoon, jota käyttäjä voi käyttää.  

Lisätietoja kokoelman käyttämisestä tietolähteenä on kohdassa [Kokoelman luominen ja päivittäminen](create-update-collection.md).

Kokoelmia käytetään yleisesti sovelluksen yleisen tilan ylläpitämiseen.  Kohdassa [Muuttujien käyttäminen](working-with-variables.md) on lisätietoja tilan hallinnan asetuksista.


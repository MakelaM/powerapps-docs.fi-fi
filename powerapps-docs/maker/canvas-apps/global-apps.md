---
title: Globaalin tuen kehittäminen pohjaan perustuville sovelluksille | Microsoft Docs
description: PowerAppsilla voit luoda sovelluksia, joita käytetään maailmanlaajuisesti.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ee2e2b854b56dadfd63b35a984e92db2ca515093
ms.sourcegitcommit: 8bad6bff1b3397b21654df4a9357dd0180fbcfe6
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/06/2019
ms.locfileid: "65046064"
---
# <a name="build-global-support-into-canvas-apps"></a>Globaalin tuen kehittäminen pohjaan perustuville sovelluksille
PowerApps on maailmanlaajuinen tuote. Pohjaan perustuvia sovelluksia voi kehittää käytettäväksi monilla kielillä ja alueilla.

Sovelluksia luotaessa ja käytettäessä PowerAppsin näyttämä teksti on käännetty useille eri kielille.  Näet valikkokohtia, valintaikkunoita, valintanauhan välilehtiä ja muuta tekstiä omalla kielelläsi.  Päivämäärien ja numeroiden kirjoittaminen ja näyttäminen on myös sovitettu omaan kieleesi ja alueeseesi.  Esimerkiksi joitakin alueiden maailman käyttö **.** (piste) desimaalierottimena, kun taas toisilla **,** (pilkku).  

Myös luomasi sovellukset voivat olla maailmanlaajuisia.  Käytä **[Language](functions/function-language.md)**-, **[Text](functions/function-text.md)**, **[Value](functions/function-value.md)**-, **[DateValue](functions/function-datevalue-timevalue.md)**-funktioita ja muita funktioita määrittämään, mitä näytetään ja käytetään syötteenä eri kielissä.   

## <a name="language-settings"></a>Kieliasetukset
Kun käytössä on alkuperäinen studio tai soitin, isännän käyttöjärjestelmä määrittää käytetyn kielen.  Windowsissa asetuksia voi muuttaa kohdassa Kaikki asetukset > Aika ja kieli.  Windows antaa sinun määrittää desimaalierottimena käytettävät merkit ohittaen kieliasetuksen.  

Kun käytetään verkkotoimintoja, käytettävä kieli määräytyy selaimen mukaan.  Useimmat selaimet käyttävät isännän käyttöjärjestelmän asetuksia. Jotkin selaimet antavat asettaa kielen manuaalisesti.

## <a name="authoring-environment"></a>Luontiympäristö
Luontiympäristö sopeutuu tekijän kieliasetukseen.  Itse sovellus tallennetaan ottaen useita kieliä huomioon, jotta eri kieliä käyttävät tekijät voivat muokata samaa sovellusta.

### <a name="names-in-formulas"></a>Nimet kaavoissa
Useimmat kaavan osat ovat aina englanniksi:

* Funktio nimet: **Jos**, **siirtyä**, **kerätä**,...
* Ohjausobjektin ominaisuusnimet: **Screen.Fill**, **Button.OnSelect**, **Textbox.Font**,...
* Luettelointinimet: **Color.Aqua**, **DataSourceInfo.MaxValue**, **FontWeight.Bold**...
* Signaalin tietueiden: **Compass.Heading**, **sijainti. Latitude**, **App.ActiveScreen**, ...
* Operaattorit: **Ylemmän tason**, **-**, **exactIn**,...

Kun luontiympäristö lokalisoidaan, ohjausobjektin ja muiden objektien nimet näkyvät tekijän omalla kielellä.  Espanjaksi jotkin ohjausobjektin nimet näkyvät seuraavasti:

![](media/global-apps/insert-controls-es.png)

Kun lisäät jonkin näistä sovellukseen, sen nimi on oletuksena englanninkielinen.  Tämä tehdään, jotta ohjausobjektin ominaisuuksien nimet ja kaavan muut osat vastaavat toisiaan.  Esimerkiksi yllä listattu **Casilla** lisätään nimellä **Checkbox1**.  

Kun ohjausobjekti on lisätty, voit muuttaa nimen haluamaksesi.  Kun se on valittu, vasemmassa laidassa oleva Sisältö-valintanauha näyttää ohjausobjektin nimen.  Nimen valitseminen avaa tekstiruudun, jossa voit muokata nimeä:

![](media/global-apps/control-rename.png)

Voit halutessasi antaa ohjausobjektille uuden nimen, **Casilla1**.  Punainen koukeroviiva, jonka tässä tapauksessa selain näyttää, ilmaisee, että nimi ei ole espanjankielinen sana, eikä sitä tarvitse huomioida.

Voit käyttää haluamiasi nimiä seuraaville:

* Ohjausobjektien nimet
* Kokoelmien nimet
* Kontekstimuuttujien nimet

### <a name="formula-separators-and-chaining-operator"></a>Kaavaerottimet ja ketjutusoperaattori
Jotkin [erottimet ja operaattorit](functions/operators.md) siirtyvät tekijän kielen desimaalierottimesta riippuen:

| Tekijän kielen desimaalierotin | PowerAppsin desimaalierotin | PowerAppsin luetteloerotin | PowerAppsin ketjutusoperaattori |
| --- | --- | --- | --- |
| **.** (piste) |**.** (piste) |**,** (pilkku) |**;** (puolipiste) |
| **,** (pilkku) |**,** (pilkku) |**;** (puolipiste) |**;;** (kaksinkertainen puolipiste) |

Powerappsin luetteloerotin muutos vastaa mitä Excel-luetteloerottimelle tapahtuu.  Se vaikuttaa

* argumentteihin funktiokutsuissa.
* kenttiin [tietueessa](working-with-tables.md#elements-of-a-table).
* tietueisiin [arvotaulukossa](working-with-tables.md#inline-syntax).

Otetaan esimerkiksi ilmaista kielen ja alueen, kuten japanin tai Yhdistyneessä kuningaskunnassa desimaalierottimena käytetään piste seuraava kaava:

![PowerApps-kaavassa, jos Avaa sulkeen slider1 piste arvo on suurempi kuin 12 piste 59 pilkuin Ilmoita Avaa sulkeen ”kelvolliset”! Sulje pilkuin onnistui sulkeen puolipistein Navigate Avaa sulkeen ”NextScreen” pilkuin ei mitään Sulje sulkeen pilkuin Ilmoita Avaa sulkeen ”virheellinen, yritä uudelleen” pilkuin virhe Sulje sulkeen Sulje sulkeen](media/global-apps/operators-dot.png)

Nyt tarkastella tämän saman kaavan kieli ja alue, jossa kuten ranska tai Espanja desimaalierottimena käytetään pilkkua:

![PowerApps-kaavassa, jos Avaa sulkeen slider1 piste arvo on suurempi kuin 12 pilkuin 59 puolipistein Ilmoita Avaa sulkeen ”kelvolliset”! Sulje puolipistein onnistui sulkeen Navigate Avaa sulkeen ”NextScreen” None Sulje sulkeen puolipistein kaksinkertainen puolipiste puolipistein Ilmoita Avaa sulkeen ”virheellinen, yritä uudelleen” puolipistein virhe Sulje sulkeen Sulje sulkeen](media/global-apps/operators-comma.png)

Korostuksen näyttää operaattorit, joita vaihtaa kaksi versiota.  Huomaa, että ominaisuuden valintaoperaattori **.** (piste)- **Slider1.Value** on aina sama desimaalierottimesta desimaalierottimena on.

Kaava ei muutu sisäisesti, vain sen näyttötapa ja tekijän muokkaustapa muuttuvat.  Kahta eri kieltä käyttävät käyttäjät voivat näyttää ja muokata samaa kaavaa, jolloin kumpikin näkee oman kielensä mukaiset erottimet ja operaattorit.

## <a name="creating-a-global-app"></a>Yleisen sovelluksen luominen
Luomasi sovellus voi sopeutua eri kieliin tarjoten erinomaisen käyttökokemuksen käyttäjille ympäri maailman.

### <a name="language-function"></a>Language-funktio
**[Language](functions/function-language.md)**-funktio palauttaa nykyisen käyttäjän kielitunnisteen.  Esimerkiksi tämä funktio palauttaa arvon **"en-GB"** käyttäjille Yhdistyneessä kuningaskunnassa ja arvon **"de-DE"** käyttäjille Saksassa.  

Voit käyttää **Language**-funktiota esimerkiksi käännetyn tekstin näyttämiseen käyttäjille.  Sovellus voi sisältää taulukon sovelluksen käännetyistä arvoista:

![](media/global-apps/loc-table.png)

Tämän jälkeen voit käyttää esimerkiksi seuraavaa kaavaa käännettyjen merkkijonojen hakemiseen taulukosta:

**LookUp( Table1, TextID = "Hello" && (LanguageTag = Left( Language(), 2 ) || IsBlank( LanguageTag ))).LocalizedText**  

Huomaa, että käännetyt merkkijonot voivat olla muissa kielissä huomattavasti pidempiä kuin omassa kielessäsi.  Monissa tapauksissa käyttöliittymäsi merkkijonot näyttävien selitteiden ja muiden elementtien tulee olla leveämpiä.

Jos haluat lisätietoja, katso **[Language](functions/function-language.md)**-funktion dokumentaatio.

### <a name="formatting-numbers-dates-and-times"></a>Numerojen, päivämäärien ja aikojen muotoilu
Numerot, päivämäärät ja kellonajat kirjoitetaan eri muodoissa eri puolilla maailmaa.  Pilkkujen ja desimaalien merkitys sekä kuukauden, päivän ja vuoden järjestys vaihtelevat sijainnista riippuen.   

**[Text](functions/function-text.md)**-funktio muotoilee numerot ja päivämäärät käyttämällä käyttäjän kieliasetusta.

**Text** edellyttää muotoilumerkkijonoa sen selvittämiseksi, kuinka haluat muotoilla numeron tai päivämäärän.  Tämä muotoilumerkkijono voi olla kahdentyyppinen:

* **Yleinen luettelointi.**  Esimerkiksi **Text( Now(), DateTimeFormat.LongDate )**.  Tämä kaava muotoilee nykyisen päivämäärän kieleen sopivaan muotoon.  Tämä on muotoilumerkkijonon ensisijainen määritystapa.
* **Mukautettu muotoilumerkkijono.**  Esimerkiksi **Text( Now(), "[$-en-US]dddd, mmmm dd, yyyy" )** näyttää saman tekstin kuin luettelointi, kun käytössä on kieli "en-US".  Mukautetun muotoilumerkkijonon etu on, että voit määrittää täsmälleen mitä tahdot.

"[$-en-US]" mukautetun muotoilumerkkijonon edessä kertoo **Text**-funktiolle, millä kielellä mukautettu muotoilumerkkijono tulkitaan.  Tämä lisätään puolestasi, ja sen oletusarvo on luontikielesi.  Yleensä sinun ei tarvitse muuttaa tätä.  Siitä on hyötyä, kun eri kieliä käyttävät tekijät muokkaavat samaa sovellusta.

**Text**-funktion kolmas argumentti määrittää, mitä kieltä käytetään funktion tuloksessa.  Oletusarvo on nykyisen käyttäjän kieliasetus.

Jos haluat lisätietoja, katso **[Text](functions/function-text.md)**-funktion dokumentaatio.      

### <a name="reading-numbers-dates-and-times"></a>Numerojen, päivämäärien ja aikojen lukeminen
Käyttäjän antamien numerojen, päivämäärien ja aikojen lukemiseen on kolme funktiota:

* **[Arvo](functions/function-value.md)**: Muuntaa tekstimerkkijonon numeron numeroarvoksi.
* **[DateValue](functions/function-datevalue-timevalue.md)**: Muuntaa päivämääräarvon merkkijonossa päivämäärä-ja aika-arvoa.  Tekstimerkkijonossa määritetty aika ohitetaan.
* **[TimeValue](functions/function-datevalue-timevalue.md)**: Muuntaa aika-arvon tekstimerkkijonossa päivämäärä ja aika-arvoa.  Tekstimerkkijonossa määritetty päivämäärä ohitetaan.
* **[DateTimeValue](functions/function-datevalue-timevalue.md)**: Muuntaa tekstimerkkijonon päivämäärä ja aika-arvon päivämäärä ja aika-arvoa.  

Jos olet käyttänyt Exceliä, nämä kaikki funktiot yhdistetään yhdeksi **Value**-funktioksi.  Ne on eroteltu tässä, koska PowerApps käyttää erityyppisiä päivämäärä- ja aika-arvoja ja numeroja.

Kaikilla näillä funktioilla on samat argumentit:

* *Merkkijono, pakollinen*: Käyttäjän antama merkkijono. Merkkijono esimerkiksi kirjoittaa **Tekstisyöte**-ohjausobjektiin ja lukee ohjausobjektista **Teksti**-ominaisuudella.
* *Kieli, valinnainen*: Kieli, jota tulkita *merkkijonon*.  Oletusarvoisesti tämä on käyttäjän kieliasetus.

Esimerkki:

* **Value( "12,345.678", "en-US" )** tai **Value( "12,345.678" )**, kun käyttäjän kieli on "en-US", palauttaa numeron **12345.678** valmiina laskutoimituksia varten.
* **DateValue( "1/2/01", "es-ES" )** tai **DateValue( "1/2/01" )**, kun käyttäjän kieli on "es-ES", palauttaa päivämäärä- ja aika-arvon **1.2.2001 keskiyöllä**.
* **TimeValue( "11:43:02", "fr-FR" )** tai **DateValue( "11:43:02" )**, kun käyttäjän kieli on "fr-FR", palauttaa päivämäärä- ja aika-arvon **1.1.1970 kello 11.43:02**.
* **TimeDateValue( "11:43:02 1/2/01", "de-DE" )** tai **DateValue( "11:43:02" )**, kun käyttäjän kieli on "de-DE", palauttaa päivämäärä- ja aika-arvon **1.2.2001 kello 11.43:02**.

Jos haluat lisätietoja, katso **[Value](functions/function-value.md)**- ja **[DateValue-, TimeValue- ja DateTimeValue](functions/function-datevalue-timevalue.md)**-funktiot sekä [päivämäärien ja aikojen käsitteleminen](show-text-dates-times.md).

### <a name="calendar-and-clock-information"></a>Tietoja kalenterista ja kellosta
**[Calendar](functions/function-clock-calendar.md)**- ja **[Clock](functions/function-clock-calendar.md)**-funktiot tarjoavat kalenteri- ja kellotietoja käyttäjän nykyisellä kielellä.  

Voit käyttää näitä funktioita muun muassa valinnat sisältävän **Avattava valikko** -ohjausobjektin tarjoamiseksi.  

Jos haluat lisätietoja, katso **[Calendar](functions/function-clock-calendar.md)**- ja **[Clock](functions/function-clock-calendar.md)**-funktioiden dokumentaatio.

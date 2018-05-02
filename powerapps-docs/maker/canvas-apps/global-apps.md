---
title: Yleinen tuki | Microsoft Docs
description: Luo sovelluksia, joita käytetään maailmanlaajuisesti.
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: gregli
ms.openlocfilehash: 57f2b9a23207c2c866738ac40f46a37747fcd54d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="global-support"></a>Yleinen tuki
PowerApps on maailmanlaajuinen tuote.  Voit luoda ja käyttää sovelluksia useilla eri kielillä ja alueilla.

Sovelluksia luotaessa ja käytettäessä PowerAppsin näyttämä teksti on käännetty useille eri kielille.  Näet valikkokohtia, valintaikkunoita, valintanauhan välilehtiä ja muuta tekstiä omalla kielelläsi.  Päivämäärien ja numeroiden kirjoittaminen ja näyttäminen on myös sovitettu omaan kieleesi ja alueeseesi.  Esimerkiksi pistettä "." käytetään desimaalierottimena joillain alueilla, kun taas toisilla alueilla käytetään pilkkua ",".  

Myös luomasi sovellukset voivat olla maailmanlaajuisia.  Käytä **[Language](functions/function-language.md)**-, **[Text](functions/function-text.md)**, **[Value](functions/function-value.md)**-, **[DateValue](functions/function-datevalue-timevalue.md)**-funktioita ja muita funktioita määrittääksesi, mitä näytetään ja käytetään syötteenä eri kielissä.   

## <a name="language-settings"></a>Kieliasetukset
Kun käytössä on alkuperäinen studio tai soitin, isännän käyttöjärjestelmä määrittää käytetyn kielen.  Windowsissa asetuksia voi muuttaa kohdassa Kaikki asetukset ja Aika ja kieli.  Windows antaa sinun määrittää desimaalierottimena käytettävät merkit ohittaen kieliasetuksen.  

Kun käytetään verkkotoimintoja, käytettävä kieli määräytyy selaimen mukaan.  Useimmat selaimet käyttävät isännän käyttöjärjestelmän asetuksia. Jotkin selaimet antavat asettaa kielen manuaalisesti.

## <a name="authoring-environment"></a>Luontiympäristö
Luontiympäristö sopeutuu tekijän kieliasetukseen.  Itse sovellus tallennetaan ottaen useita kieliä huomioon, jotta eri kieliä käyttävät tekijät voivat muokata samaa sovellusta.

### <a name="names-in-formulas"></a>Nimet kaavoissa
Useimmat kaavan osat ovat aina englanniksi:

* Funktionimet: **If**, **Navigate**, **Collect**, ...
* Ohjausobjektin ominaisuusnimet: **Screen.Fill**, **Button.OnSelect**, **Textbox.Font**, ...
* Luettelointinimet: **Color.Aqua**, **DataSourceInfo.MaxValue**, **FontWeight.Bold**...
* Signaalitietueet: **Compass.Heading**, **Location. Latitude**, **App.ActiveScreen**, ...
* Operaattorit: **Parent**, **in**, **exactIn**, ...

Kun luontiympäristö lokalisoidaan, ohjausobjektin ja muiden objektien nimet näkyvät tekijän omalla kielellä.  Espanjaksi jotkin ohjausobjektin nimet näkyvät seuraavasti:

![](media/global-apps/insert-controls-es.png)

Kun lisäät jonkin näistä sovellukseen, sen nimi on oletuksena englanninkielinen.  Tämä tehdään, jotta ohjausobjektin ominaisuuksien nimet ja kaavan muut osat vastaavat toisiaan.  Esimerkiksi yllä listattu **Casilla** lisätään nimellä **Checkbox1**.  

Kun ohjausobjekti on lisätty, voit muuttaa nimen haluamaksesi.  Kun se on valittu, vasemmassa laidassa oleva Sisältö-valintanauha näyttää ohjausobjektin nimen.  Nimen valitseminen avaa tekstiruudun, jossa voit muokata nimeä:

![](media/global-apps/control-rename.png)

Voit halutessasi antaa ohjausobjektille uuden nimen, **Casilla1**.  Punainen koukeroviiva, jonka tässä tapauksessa selain näyttää, ilmaisee, että nimi ei ole espanjankielinen sana, eikä sitä tarvitse huomioida.

Voit käyttää haluamiasi nimiä seuraaville:

* Ohjausobjektin nimet
* Kokoelman nimet
* Kontekstimuuttujan nimet

### <a name="formula-separators-and-chaining-operator"></a>Kaavaerottimet ja ketjutusoperaattori
Jotkin [erottimet ja operaattorit](functions/operators.md) siirtyvät tekijän kielen desimaalierottimesta riippuen:

| Tekijän kielen desimaalierotin | PowerAppsin desimaalierotin | PowerAppsin luetteloerotin | PowerAppsin ketjutusoperaattori |
| --- | --- | --- | --- |
| **.** (piste) |**.** (piste) |**,** (pilkku) |**;** (puolipiste) |
| **,** (pilkku) |**,** (pilkku) |**;** (puolipiste) |**;;** (kaksinkertainen puolipiste) |

Muutos PowerApps-luetteloerottimessa vaikuttaa myös siihen, mitä Excel-luetteloerottimelle tapahtuu.  Se vaikuttaa

* argumentteihin funktiokutsuissa
* kenttiin [tietueessa](working-with-tables.md#elements-of-a-table)
* tietueisiin [arvotaulukossa](working-with-tables.md#inline-syntax).

Katso esimerkiksi seuraavaa "en-US"-muotoista kaavaa:

**If( Slider1.Value > 12.59, UpdateContext( { Validation: true, MovingOn: 1 } ); Navigate( "NextScreen", "" ), UpdateContext( { Validation: false } ) )**

Kielessä, jossa "," on desimaalierottimena, kaava näkyy tekijälle seuraavassa muodossa:

**If( Slider1.Value > 12,59; UpdateContext( { Validation: true; MovingOn: 1 } );; Navigate( "NextScreen", "" ); UpdateContext( { Validation: false } ) )**

Huomaa, että ominaisuuden valintaoperaattori **.** kohdassa **Slider1.Value** on aina sama desimaalierottimesta riippumatta.

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

**Text** edellyttää muotoilumerkkijonoa selvittääkseen, miten haluat muotoilla numeron tai päivämäärän.  Tämä muotoilumerkkijono voi olla kahdentyyppinen:

* **Yleinen luettelointi.**  Esimerkiksi **Text( Now(), DateTimeFormat.LongDate )**.  Tämä kaava muotoilee nykyisen päivämäärän kieleen sopivaan muotoon.  Tämä on muotoilumerkkijonon ensisijainen määritystapa.
* **Mukautettu muotoilumerkkijono.**  Esimerkiksi **Text( Now(), "[$-en-US]dddd, mmmm dd, yyyy" )** näyttää saman tekstin kuin luettelointi, kun käytössä on kieli "en-US".  Mukautetun muotoilumerkkijonon etu on, että voit määrittää täsmälleen mitä tahdot.

"[$-en-US]" mukautetun muotoilumerkkijonon edessä kertoo **Text**-funktiolle, millä kielellä mukautettu muotoilumerkkijono tulkitaan.  Tämä lisätään puolestasi, ja sen oletusarvo on luontikielesi.  Yleensä sinun ei tarvitse muuttaa tätä.  Siitä on hyötyä, kun eri kieliä käyttävät tekijät muokkaavat samaa sovellusta.

**Text**-funktion kolmas argumentti määrittää, mitä kieltä käytetään funktion tuloksessa.  Oletusarvo on nykyisen käyttäjän kieliasetus.

Jos haluat lisätietoja, katso **[Text](functions/function-text.md)**-funktion dokumentaatio.      

### <a name="reading-numbers-dates-and-times"></a>Numerojen, päivämäärien ja aikojen lukeminen
Käyttäjän antamien numerojen, päivämäärien ja aikojen lukemiseen on kolme funktiota:

* **[Value](functions/function-value.md)** – muuntaa tekstimerkkijonon numeron numeroarvoksi.
* **[DateValue](functions/function-datevalue-timevalue.md)** – muuntaa päivämääräarvon merkkijonossa päivämäärä- ja aika-arvoksi.  Tekstimerkkijonossa määritetty aika ohitetaan.
* **[TimeValue](functions/function-datevalue-timevalue.md)** – muuntaa aika-arvon merkkijonossa päivämäärä- ja aika-arvoksi.  Tekstimerkkijonossa määritetty päivämäärä ohitetaan.
* **[DateTimeValue](functions/function-datevalue-timevalue.md)** – muuntaa päivämäärä- ja aika-arvon tekstimerkkijonossa päivämäärä- ja aika-arvoksi.  

Jos olet käyttänyt Exceliä, nämä kaikki funktiot yhdistetään yhdeksi **Value**-funktioksi.  Ne on eroteltu tässä, koska PowerApps käyttää erityyppisiä päivämäärä- ja aika-arvoja ja numeroja.

Kaikilla näillä funktioilla on samat argumentit:

* *Merkkijono, pakollinen*: Käyttäjän antama merkkijono. Merkkijono esimerkiksi kirjoittaa **Tekstisyöte**-ohjausobjektiin ja lukee ohjausobjektista **Teksti**-ominaisuudella.
* *Kieli, valinnainen*: Kieli, jolla *Merkkijono* tulkitaan.  Oletusarvoisesti tämä on käyttäjän kieliasetus.

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

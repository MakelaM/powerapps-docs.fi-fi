---
title: Globaalin tuen kehittäminen pohjaan perustuville sovelluksille | Microsoft Docs
description: PowerAppsilla voit luoda sovelluksia, joita käytetään maailmanlaajuisesti.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8df786dfea77849f41992c704d69d214df73d13a
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983243"
ms.PowerAppsDecimalTransform: true
---
# <a name="build-global-support-into-canvas-apps"></a>Globaalin tuen kehittäminen pohjaan perustuville sovelluksille
PowerApps on maailmanlaajuinen tuote. Pohjaan perustuvia sovelluksia voi kehittää käytettäväksi monilla kielillä ja alueilla.

Sovelluksia luotaessa ja käytettäessä PowerAppsin näyttämä teksti on käännetty useille eri kielille.  Näet valikkokohtia, valintaikkunoita, valintanauhan välilehtiä ja muuta tekstiä omalla kielelläsi.  Päivämäärien ja numeroiden kirjoittaminen ja näyttäminen on myös sovitettu omaan kieleesi ja alueeseesi.  Esimerkiksi joillakin alueilla maailmassa käytetään **.** (piste tai piste) Desi maalina erottimena, kun taas toiset käyttävät **,** (pilkku).  

Myös luomasi sovellukset voivat olla maailmanlaajuisia.  Käytä **[Language](functions/function-language.md)** -, **[Text](functions/function-text.md)** , **[Value](functions/function-value.md)** -, **[DateValue](functions/function-datevalue-timevalue.md)** -funktioita ja muita funktioita määrittämään, mitä näytetään ja käytetään syötteenä eri kielissä.   

## <a name="language-settings"></a>Kieliasetukset
Kun käytössä on alkuperäinen studio tai soitin, isännän käyttöjärjestelmä määrittää käytetyn kielen.  Windowsissa asetuksia voi muuttaa kohdassa Kaikki asetukset > Aika ja kieli.  Windows antaa sinun määrittää desimaalierottimena käytettävät merkit ohittaen kieliasetuksen.  

Kun käytetään verkkotoimintoja, käytettävä kieli määräytyy selaimen mukaan.  Useimmat selaimet käyttävät isännän käyttöjärjestelmän asetuksia. Jotkin selaimet antavat asettaa kielen manuaalisesti.

## <a name="authoring-environment"></a>Luontiympäristö
Luontiympäristö sopeutuu tekijän kieliasetukseen.  Itse sovellus tallennetaan ottaen useita kieliä huomioon, jotta eri kieliä käyttävät tekijät voivat muokata samaa sovellusta.

### <a name="names-in-formulas"></a>Nimet kaavoissa
Useimmat kaavan osat ovat aina englanniksi:

* Funktioiden nimet: **Jos**, **Navigoi**, **Kerää**,...
* Ohjaus objektin ominaisuuksien nimet: **Screen. Fill**, **Button. onselect**, **TextBox. Font**,...
* Luetteloinnin nimet: **Color. Aqua**, **datatourceinfo. MaxValue**, **fontweight. Bold**...
* Signaali tietueet: **Compass. Heading**, **location. Latitude**, **App.ActiveScreen**, ...
* Operaattorit **Parent**, **in**, **EXACTin**,...

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
| **.** (piste tai piste) |**.** (piste tai piste) |**,** (pilkku) |**;** (puolipiste) |
| **,** (pilkku) |**,** (pilkku) |**;** (puolipiste) |**;;** (kaksinkertainen puolipiste) |

Powerappsin List-erottimen muutos on johdonmukainen sen kanssa, mitä Excel-luetteloerottimessa tapahtuu.  Se vaikuttaa

* argumentteihin funktiokutsuissa.
* kenttiin [tietueessa](working-with-tables.md#elements-of-a-table).
* [Taulukon](working-with-tables.md#inline-value-tables)tietueet.

Harkitse esimerkiksi seuraavaa kaavaa, joka ilmaistaan kielellä ja alueella, joka käyttää pistettä tai jaksoa erottimena, kuten Japanissa tai Isossa-Britanniassa:

![Powerapps-kaava, jos Open sulkeen slider1 dot-arvo on suurempi kuin 12 dot 59 Comma Ilmoita Open sulkeen "kelpaa!" Comma Success Close sulkeen semi-kaksoispiste siirtyä Open sulkeen "nextscreen" Comma mikään Close sulkeen Comma Ilmoita Open sulkeen "virheellinen, yritä uudelleen" Comma Error Close sulkeen Close sulkeen](media/global-apps/operators-dot.png)

Näytä nyt tämä sama kaava kielellä ja alueella, jossa pilkkua käytetään kymmen järjestelmä erottimessa, kuten Ranskassa tai Espanjassa:

![Powerapps-kaava, jos Open sulkeen slider1 dot-arvo on suurempi kuin 12, 59 puoli pisteellä ilmoitus Open sulkeen "kelpaa!" Semi-kaksoispiste menestys Close sulkeen kaksinkertainen semi-kaksoispiste siirtyä Open sulkeen "nextscreen" semi-Colon None Close sulkeen semi-kaksoispiste ilmoittamaan Open sulkeen "virheellinen, yritä uudelleen" puoli pistettä virhe Sulje sulkeen Close sulkeen](media/global-apps/operators-comma.png)

Korosta näytetään operaattorit, jotka muuttuvat kahden version välillä.  Huomaa, että ominaisuuden valintaoperaattori **.** (piste tai piste) kohteessa **Slider1. arvo** on aina sama riippumatta siitä, mikä on desimaalierotin.

Kaava ei muutu sisäisesti, vain sen näyttötapa ja tekijän muokkaustapa muuttuvat.  Kahta eri kieltä käyttävät käyttäjät voivat näyttää ja muokata samaa kaavaa, jolloin kumpikin näkee oman kielensä mukaiset erottimet ja operaattorit.

## <a name="creating-a-global-app"></a>Yleisen sovelluksen luominen
Luomasi sovellus voi sopeutua eri kieliin tarjoten erinomaisen käyttökokemuksen käyttäjille ympäri maailman.

### <a name="language-function"></a>Language-funktio
**[Language](functions/function-language.md)** -funktio palauttaa nykyisen käyttäjän kielitunnisteen.  Esimerkiksi tämä funktio palauttaa arvon **"en-GB"** käyttäjille Yhdistyneessä kuningaskunnassa ja arvon **"de-DE"** käyttäjille Saksassa.  

Voit käyttää **Language**-funktiota esimerkiksi käännetyn tekstin näyttämiseen käyttäjille.  Sovellus voi sisältää taulukon sovelluksen käännetyistä arvoista:

![](media/global-apps/loc-table.png)

Tämän jälkeen voit käyttää esimerkiksi seuraavaa kaavaa käännettyjen merkkijonojen hakemiseen taulukosta:

**LookUp( Table1; TextID = "Hello" && (LanguageTag = Left( Language(); 2 ) || IsBlank( LanguageTag ))).LocalizedText**  

Huomaa, että käännetyt merkkijonot voivat olla muissa kielissä huomattavasti pidempiä kuin omassa kielessäsi.  Monissa tapauksissa käyttöliittymäsi merkkijonot näyttävien selitteiden ja muiden elementtien tulee olla leveämpiä.

Jos haluat lisätietoja, katso **[Language](functions/function-language.md)** -funktion dokumentaatio.

### <a name="formatting-numbers-dates-and-times"></a>Numerojen, päivämäärien ja aikojen muotoilu
Numerot, päivämäärät ja kellonajat kirjoitetaan eri muodoissa eri puolilla maailmaa.  Pilkkujen ja desimaalien merkitys sekä kuukauden, päivän ja vuoden järjestys vaihtelevat sijainnista riippuen.   

**[Text](functions/function-text.md)** -funktio muotoilee numerot ja päivämäärät käyttämällä käyttäjän kieliasetusta.

**Text** edellyttää muotoilumerkkijonoa sen selvittämiseksi, kuinka haluat muotoilla numeron tai päivämäärän.  Tämä muotoilumerkkijono voi olla kahdentyyppinen:

* **Yleinen luettelointi.**  Esimerkiksi **Text( Now(); DateTimeFormat.LongDate )** .  Tämä kaava muotoilee nykyisen päivämäärän kieleen sopivaan muotoon.  Tämä on muotoilumerkkijonon ensisijainen määritystapa.
* **Mukautettu muotoilumerkkijono.**  Esimerkiksi **Text( Now(); "[$-en-US]dddd, mmmm dd, yyyy" )** näyttää saman tekstin kuin luettelointi, kun käytössä on kieli "en-US".  Mukautetun muotoilumerkkijonon etu on, että voit määrittää täsmälleen mitä tahdot.

"[$-en-US]" mukautetun muotoilumerkkijonon edessä kertoo **Text**-funktiolle, millä kielellä mukautettu muotoilumerkkijono tulkitaan.  Tämä lisätään puolestasi, ja sen oletusarvo on luontikielesi.  Yleensä sinun ei tarvitse muuttaa tätä.  Siitä on hyötyä, kun eri kieliä käyttävät tekijät muokkaavat samaa sovellusta.

**Text**-funktion kolmas argumentti määrittää, mitä kieltä käytetään funktion tuloksessa.  Oletusarvo on nykyisen käyttäjän kieliasetus.

Jos haluat lisätietoja, katso **[Text](functions/function-text.md)** -funktion dokumentaatio.      

### <a name="reading-numbers-dates-and-times"></a>Numerojen, päivämäärien ja aikojen lukeminen
Käyttäjän antamien numerojen, päivämäärien ja aikojen lukemiseen on kolme funktiota:

* **[Arvo](functions/function-value.md)** : Muuntaa teksti merkki jonon luvun luku arvoksi.
* **[DateValue](functions/function-datevalue-timevalue.md)** : Muuntaa teksti merkki jonon päivämäärä arvon päivä määrä-ja aika-arvoksi.  Tekstimerkkijonossa määritetty aika ohitetaan.
* Aika **[arvo](functions/function-datevalue-timevalue.md)** : Muuntaa teksti merkki jonon aika-arvon päivä määrä-ja aika-arvoksi.  Tekstimerkkijonossa määritetty päivämäärä ohitetaan.
* **[DateTime-arvo](functions/function-datevalue-timevalue.md)** : Muuntaa teksti merkki jonon päivä määrä-ja aika-arvon päivä määrä-ja aika-arvoksi.  

Jos olet käyttänyt Exceliä, nämä kaikki funktiot yhdistetään yhdeksi **Value**-funktioksi.  Ne on eroteltu tässä, koska PowerApps käyttää erityyppisiä päivämäärä- ja aika-arvoja ja numeroja.

Kaikilla näillä funktioilla on samat argumentit:

* *Merkki jono, pakollinen*: Merkki jono käyttäjältä. Merkkijono esimerkiksi kirjoittaa **Tekstisyöte**-ohjausobjektiin ja lukee ohjausobjektista **Teksti**-ominaisuudella.
* *Kieli, valinnainen*: Kieli, jolla *merkki jono*tulkitaan.  Oletusarvoisesti tämä on käyttäjän kieliasetus.

Esimerkki:

* **Value( "12,345.678"; "en-US" )** tai **Value( "12,345.678" )** , kun käyttäjän kieli on "en-US", palauttaa numeron **12345.678** valmiina laskutoimituksia varten.
* **DateValue( "1/2/01"; "es-ES" )** tai **DateValue( "1/2/01" )** , kun käyttäjän kieli on "es-ES", palauttaa päivämäärä- ja aika-arvon **1.2.2001 keskiyöllä**.
* **TimeValue( "11:43:02"; "fr-FR" )** tai **DateValue( "11:43:02" )** , kun käyttäjän kieli on "fr-FR", palauttaa päivämäärä- ja aika-arvon **1.1.1970 kello 11.43:02**.
* **TimeDateValue( "11:43:02 1/2/01"; "de-DE" )** tai **DateValue( "11:43:02" )** , kun käyttäjän kieli on "de-DE", palauttaa päivämäärä- ja aika-arvon **1.2.2001 kello 11.43:02**.

Jos haluat lisätietoja, katso **[Value](functions/function-value.md)** - ja **[DateValue-, TimeValue- ja DateTimeValue](functions/function-datevalue-timevalue.md)** -funktiot sekä [päivämäärien ja aikojen käsitteleminen](show-text-dates-times.md).

### <a name="calendar-and-clock-information"></a>Tietoja kalenterista ja kellosta
**[Calendar](functions/function-clock-calendar.md)** - ja **[Clock](functions/function-clock-calendar.md)** -funktiot tarjoavat kalenteri- ja kellotietoja käyttäjän nykyisellä kielellä.  

Voit käyttää näitä funktioita muun muassa valinnat sisältävän **Avattava valikko** -ohjausobjektin tarjoamiseksi.  

Jos haluat lisätietoja, katso **[Calendar](functions/function-clock-calendar.md)** - ja **[Clock](functions/function-clock-calendar.md)** -funktioiden dokumentaatio.

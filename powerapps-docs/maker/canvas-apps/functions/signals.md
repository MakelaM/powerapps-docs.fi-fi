---
title: Acceleration-, App-, Compass-, Connection- ja Location-signaalit | Microsoft Docs
description: Viitetietoja Acceleration-, App-, Compass-, Connection- ja Location-tunnistimista, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 147766eb9e9b17698882241e8eb3bd0ae7ba7e78
ms.sourcegitcommit: 0dbbf53aea319e53edadc1d3a9efa5728856ebd8
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/19/2019
ms.locfileid: "58172629"
---
# <a name="acceleration-app-compass-connection-and-location-signals-in-powerapps"></a>Acceleration-, App-, Compass-, Connection- ja Location-signaalit PowerAppsissa
Palauttavat tietoja sovelluksen ympäristöstä, kuten käyttäjän sijainnin maailmassa ja tiedon siitä, mikä näyttö näytetään.  

## <a name="description-and-syntax"></a>Kuvaus ja syntaksi
Kaikki signaalit palauttavat [tietueen](../working-with-tables.md#records) tiedoista. Voit käyttää tietoja ja tallentaa ne tietueeksi. Voit myös poimia yksittäisiä ominaisuuksia käyttämällä **.** [-operaattoria](operators.md).

> [!NOTE]
> **Acceleration** ja **kompassi** funktiot palauttavat tarkat arvot soitin, kuten iOS: lle tai Androidille, mutta kun ne palauttavat nolla-arvojen luot tai muokkaat sovelluksen selaimessa.

### <a name="acceleration"></a>Acceleration
**Acceleration**-signaali palauttaa laitteen kiihtyvyyden kolmessa ulottuvuudessa suhteessa laitteen näyttöön. Kiihtyvyys mitataan *g*-yksikköinä 9,81 m/s<sup>2</sup> tai 32,2 ft/s<sup>2</sup> (maan vetovoiman aiheuttama kiihtyvyys maan pinnalla).

| Ominaisuus | Kuvaus |
| --- | --- |
| **Acceleration.X** |Oikealle ja vasemmalle.  Oikea on positiivinen luku. |
| **Acceleration.Y** |Eteenpäin ja taaksepäin.  Eteenpäin on positiivinen luku. |
| **Acceleration.Z** |Ylös ja alas.  Ylös on positiivinen luku. |

### <a name="app"></a>App
**App**-signaali palauttaa tietoja käynnissä olevasta sovelluksesta.

| Ominaisuus | Kuvaus |
| --- | --- |
| **App.ActiveScreen** | Näkyvissä oleva näyttö. Palauttaa näytön ohjausobjektin, jota voit käyttää viittaamaan näytön ominaisuuksiin tai vertaamaan toiseen näyttöön määrittääksesi, mikä näyttö näytetään. Voit muuttaa näytettävää näyttöä **[takaisin](function-navigate.md)** tai **[Navigate](function-navigate.md)** funktio. |
| **App.Width** | Palauttaa leveys-ikkunan, jossa sovellus on käynnissä. Voit käyttää tätä ominaisuutta kaavassa, kun määrität **leveys** reagoiva sovelluksen rakentaminen näytön ominaisuus.  |
| **App.Height** | Palauttaa ikkunan, jossa sovellus on käynnissä korkeuden. Voit käyttää tätä ominaisuutta kaavassa, kun määrität **korkeus** reagoiva sovelluksen rakentaminen näytön ominaisuus. |
| **App.DesignWidth** | Palauttaa sovelluksen leveys PowerApps Studio. Voit käyttää tätä ominaisuutta kaavassa, kun määrität **leveys** ominaisuuden näytön, varmista, että Vähimmäisleveys reagoiva sovelluksessa.  |
| **App.DesignHeight** | Palauttaa sovelluksen korkeus PowerApps Studio. Voit käyttää tätä ominaisuutta kaavassa, kun määrität **korkeus** ominaisuuden näytön, varmista, että vähimmäiskorkeus reagoiva sovelluksessa.  |

**Sovelluksen** objekti on myös [toimintakaavassa](../working-with-formulas-in-depth.md) , johon voit asettaa.

| Ominaisuus  | Kuvaus |
| --- | --- |
| **OnStart** | Sovellus, kun käyttäjä käynnistää sen toiminta. Tätä ominaisuutta käytetään yleisesti ja tietoja välimuistiin kokoelmiin kanssa **[kerätä](function-clear-collect-clearcollect.md)** funktio, Määritä muuttujat **[määrittää](function-set.md)** funktio ja ensimmäinen näyttö ja siirry **[Navigate](function-navigate.md)** funktio. Kaava lasketaan, ennen kuin ensimmäinen näyttö näytetään. Yhtään näyttöä ei ladattu, joten et voi määrittää kontekstimuuttujan kanssa **[UpdateContext](function-updatecontext.md)** funktio. Voit kuitenkin välittää kontekstimuuttujia kanssa **Navigate** funktio. |

**Sovelluksen** näkyy vasemmassa siirtymisruudussa ohjausobjektien hierarkkisessa luettelossa yläosassa ja voit valita tämän objektin näytössä on ohjausobjekti, kuten. Kun olet valinnut objektia, voit tarkastella ja muokata sen ominaisuuksia, jos valitset kyseisen ominaisuuden vasemmalla puolella kaavarivin avattavasta-luettelosta.  

Kun muutat **OnStart** ominaisuutta, voit testata sitä hiiri **sovelluksen** objektin vasemmasta siirtymisruudusta, valitsemalla kolme pistettä (...), joka näkyy ja valitsemalla sitten **suorittaa OnStart**. Toisin kuin kun sovellusta ladataan ensimmäistä kertaa olemassa oleviin kokoelmiin ja muuttujat jo määritetään. Käytä **[ClearCollect](function-clear-collect-clearcollect.md)** funktion sijaan **kerätä** funktion tyhjä alkaa kokoelmat.

 ![Suorita OnStart kanssa sovelluksen kohteen pikavalikko](media/appobject-runonstart.png)

### <a name="compass"></a>Compass
**Compass**-signaali palauttaa näytön ylälaidan kompassisuunnan. Suunta perustuu magneettiseen pohjoiseen.

| Ominaisuus | Kuvaus |
| --- | --- |
| **Compass.Heading** |Suunta asteina.  Palauttaa luvun väliltä 0–360. 0 on pohjoinen. |

### <a name="connection"></a>Connection
**Connection**-signaali palauttaa tietoja verkkoyhteydestä. Jos käytät käytön mukaan laskutettavaa yhteyttä, sinun kannattaa rajoittaa verkon kautta lähetettävän ja vastaanotettavan tiedon määrää.

| Ominaisuus | Kuvaus |
| --- | --- |
| **Connection.Connected** |Palauttaa totuusarvon **true** tai **false**, joka ilmaisee, onko laite yhdistetty verkkoon. |
| **Connection.Metered** |Palauttaa totuusarvon **true** tai **false**, joka ilmaisee, onko yhteys käytön mukaan laskutettava. |

### <a name="location"></a>Location
**Location**-signaali palauttaa laitteen sijainnin GPS-järjestelmän ja laitteen muiden tietojen, kuten maston viestinnän ja IP-osoitteen, perusteella.

Kun käyttäjä käyttää sijaintitietoja ensimmäisen kerran, laite voi pyytää käyttäjää sallimaan näiden tietojen käytön.

Kun sijainti muuttuu, sijainnin riippuvaisuudet lasketaan jatkuvasti uudelleen. Tämä kuluttaa laitteen akun virtaa. Akun säästämiseksi voit käyttää **[Enable](function-enable-disable.md)**- ja **[Disable](function-enable-disable.md)**-funktioita ottaaksesi sijaintipäivitykset käyttöön ja poistaaksesi ne käytöstä. Sijainti on automaattisesti poistettu käytöstä, jos näytetty näyttö ei ole riippuvainen sijaintitiedoista.

| Ominaisuus | Kuvaus |
| --- | --- |
| **Location.Altitude** |Palauttaa luvun, joka ilmaisee korkeutta merenpinnan yläpuolella jalkoina mitattuna. |
| **Location.Latitude** |Palauttaa luvun väliltä -90–90, joka ilmaisee leveysasteen mitattuna asteina päiväntasaajalta. Positiivinen luku ilmaisee päiväntasaajan pohjoispuolella olevaa sijaintia. |
| **Location.Longitude** |Palauttaa luvun väliltä 0–180, joka ilmaisee pituusasteen mitattuna asteina länteen Greenwichistä, Englannista. |

## <a name="examples"></a>Esimerkkejä
Heidän kentässä syöttäjä heittää laitteen puhelimella-syöttäjän kummulta siepparille. Puhelin on suorassa linjassa suhteessa maahan, näytön yläosa on siepparia kohden eikä syöttäjä lisää heittoon kierrettä. Tässä sijainnissa puhelimessa on käytön mukaan laskutettava mobiiliverkkopalvelu, mutta ei Wi-Fi-yhteyttä. **PlayBall**-näyttö tulee näkyviin.   

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Location.Latitude** |Palauttaa nykyisen sijainnin leveysasteen. Kartan koordinaatteina 47.591 N, 122.333 W. sijaitsee kenttä |47.591<br><br>Leveysaste muuttuu jatkuvasti, kun pallo kulkee syöttäjän ja siepparin välillä. |
| **Location.Longitude** |Palauttaa nykyisen sijainnin pituusasteen. |122.333<br><br>Pituusaste muuttuu jatkuvasti, kun pallo kulkee syöttäjän ja siepparin välillä. |
| **Location** |Palauttaa nykyisen sijainnin leveysasteen ja pituusasteen tietueena. |{&nbsp;Latitude:&nbsp;47.591, Longitude:&nbsp;122.333&nbsp;} |
| **Compass.Heading** |Palauttaa näytön ylälaidan kompassisuunnan. Tämä kenttä on Kotipesä on kutakuinkin Latinalainen Amerikka syöttäjän kummulta. |230.25 |
| **Acceleration.X** |Palauttaa laitteen kiihtyvyyden sivuttain. Syöttäjä heittää puhelimen suoraan eteenpäin suhteessa näytön ylälaitaan, joten laite ei kiihdy sivuttain. |0 |
| **Acceleration.Y** |Palauttaa laitteen kiihtyvyyden edestä taaksepäin. Syöttäjä saa heittäessään laitteen kiihtymään aluksi voimakkaasti, niin että sen nopeus kasvaa nollasta 90 mailiin tunnissa (132 jalkaa sekunnissa) puolessa sekunnissa. Kun laite on ilmassa (eikä ilmanvastusta huomioida), laite ei kiihdy enempää. Laitteen kiihtyvyys hidastuu, kun sieppari ottaa kopin, ja lopulta laitteen liike pysähtyy. |8.2, kun syöttäjä heittää laitteen.<br><br>0, kun laite on ilmassa.<br><br>-8.2, kun sieppari ottaa laitteesta kopin. |
| **Acceleration.Z** |Palauttaa laitteen kiihtyvyyden alhaalta ylöspäin. Kun laite on ilmassa, painovoiman vaikutukset vaikuttavat siihen. |0, ennen kuin syöttäjä heittää laitteen.<br><br>1, kun laite on ilmassa.<br><br>0, kun sieppari on ottanut laitteesta kopin. |
| **Acceleration** |Palauttaa kiihtyvyyden tietueena. |{ X: 0, Y: 264, Z: {0} kuin syöttäjä heittää laitteen. |
| **Connection.Connected** |Palauttaa totuusarvon, joka ilmaisee, onko laite yhdistetty verkkoon |**true** |
| **Connection.Metered** |Palauttaa totuusarvon, joka ilmaisee, onko yhteys käytön mukaan laskutettava |**true** |
| **App.ActiveScreen = PlayBall** |Palauttaa totuusarvon, joka ilmaisee, näytetäänkö **PlayBall**. |**true** |
| **App.ActiveScreen.Fill** |Palauttaa näkyvissä olevan näytön taustavärin. |**Color.Green** |


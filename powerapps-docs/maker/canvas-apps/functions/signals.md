---
title: Acceleration-, App-, Compass-, Connection- ja Location-signaalit | Microsoft Docs
description: Viitetietoja Acceleration-, App-, Compass-, Connection- ja Location-tunnistimista, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/29/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a06217470482eccdf368279eaabcd297bbf73ce5
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983355"
---
# <a name="acceleration-app-compass-connection-and-location-signals-in-powerapps"></a>Acceleration-, App-, Compass-, Connection- ja Location-signaalit PowerAppsissa

Palauttavat tietoja sovelluksen ympäristöstä, kuten käyttäjän sijainnin maailmassa ja tiedon siitä, mikä näyttö näytetään.

## <a name="description-and-syntax"></a>Kuvaus ja syntaksi

Signaalit ovat arvoja, jotka voivat muuttua milloin tahansa, riippumatta siitä, miten käyttäjä voi olla vuoro vaikutuksessa sovelluksen kanssa. Signaaleihin perustuvat kaavat laskevat automaattisesti uudelleen, kun nämä arvot muuttuvat.

Signaalit palauttavat tiedot yleensä [](../working-with-tables.md#records) . Voit käyttää tietoja ja tallentaa ne tietueeksi. Voit myös poimia yksittäisiä ominaisuuksia käyttämällä **.** [-operaattoria](operators.md).

> [!NOTE]
> **Kiihdytyksen** ja **kompassin** funktiot palauttavat tarkkoja arvoja alkuperäisessä soittimessa, kuten iOS:ssä tai Androidissa, mutta nämä funktiot palauttavat nolla-arvot, kun luot tai muokkaat sovellusta selaimessa.

### <a name="acceleration"></a>Acceleration

**Acceleration**-signaali palauttaa laitteen kiihtyvyyden kolmessa ulottuvuudessa suhteessa laitteen näyttöön. Kiihtyvyys mitataan *g*-yksikköinä 9,81 m/s<sup>2</sup> tai 32,2 ft/s<sup>2</sup> (maan vetovoiman aiheuttama kiihtyvyys maan pinnalla).

| Ominaisuus | Kuvaus |
| --- | --- |
| **Acceleration.X** |Oikealle ja vasemmalle.  Oikea on positiivinen luku. |
| **Acceleration.Y** |Eteenpäin ja taaksepäin.  Eteenpäin on positiivinen luku. |
| **Acceleration.Z** |Ylös ja alas.  Ylös on positiivinen luku. |

### <a name="app"></a>App

Muiden ominaisuuksien joukossa **sovellus** -objekti sisältää signaalin, joka ilmaisee, mitä näyttöä näytetään.

| Ominaisuus | Kuvaus |
| --- | --- |
| **App.ActiveScreen** |Näyttö, joka näytetään. Palauttaa näyttö objektin, jonka avulla voit viitata näytön ominaisuuksiin tai verrata toiseen näyttöön, jotta voit määrittää, mitä näyttöä näytetään. Voit käyttää **[Back](function-navigate.md)** -tai **[Navigate](function-navigate.md)** -toimintoa vaihtaaksesi näyt-näyttöä. |

Lisätietoja: [ **Sovellus** objektin](object-app.md) dokumentaatio.

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

Kun sijainti muuttuu, sijainnin riippuvaisuudet lasketaan jatkuvasti uudelleen. Tämä kuluttaa laitteen akun virtaa. Akun säästämiseksi voit käyttää **[Enable](function-enable-disable.md)** - ja **[Disable](function-enable-disable.md)** -funktioita ottaaksesi sijaintipäivitykset käyttöön ja poistaaksesi ne käytöstä. Sijainti on automaattisesti poistettu käytöstä, jos näytetty näyttö ei ole riippuvainen sijaintitiedoista.

| Ominaisuus | Kuvaus |
| --- | --- |
| **Location.Altitude** |Palauttaa luvun, joka ilmaisee korkeutta merenpinnan yläpuolella jalkoina mitattuna. |
| **Location.Latitude** |Palauttaa luvun väliltä -90–90, joka ilmaisee leveysasteen mitattuna asteina päiväntasaajalta. Positiivinen luku ilmaisee päiväntasaajan pohjoispuolella olevaa sijaintia. |
| **Location.Longitude** |Palauttaa luvun väliltä 0–180, joka ilmaisee pituusasteen mitattuna asteina länteen Greenwichistä, Englannista. |

## <a name="examples"></a>Esimerkkejä
Baseball-kentässä syöttäjä heittää puhelimen syöttäjän röykkiöstä siepparin koti levylle. Puhelin on suorassa linjassa suhteessa maahan, näytön yläosa on siepparia kohden eikä syöttäjä lisää heittoon kierrettä. Tässä sijainnissa puhelimessa on käytön mukaan laskutettava mobiiliverkkopalvelu, mutta ei Wi-Fi-yhteyttä. **PlayBall**-näyttö tulee näkyviin.   

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Location.Latitude** |Palauttaa nykyisen sijainnin leveysasteen. Kenttä sijaitsee kartan koordinaatteina 47,591 N, 122,333 W. |47.591<br><br>Leveysaste muuttuu jatkuvasti, kun pallo kulkee syöttäjän ja siepparin välillä. |
| **Location.Longitude** |Palauttaa nykyisen sijainnin pituusasteen. |122.333<br><br>Pituusaste muuttuu jatkuvasti, kun pallo kulkee syöttäjän ja siepparin välillä. |
| **Location** |Palauttaa nykyisen sijainnin leveysasteen ja pituusasteen tietueena. |{&nbsp;Latitude:&nbsp;47.591, Longitude:&nbsp;122.333&nbsp;} |
| **Compass.Heading** |Palauttaa näytön ylälaidan kompassisuunnan. Tässä kentässä koti kilpi on suunnilleen lounaaseen kannun röykkiö. |230.25 |
| **Acceleration.X** |Palauttaa laitteen kiihtyvyyden sivuttain. Syöttäjä heittää puhelimen suoraan eteenpäin suhteessa näytön ylälaitaan, joten laite ei kiihdy sivuttain. |0 |
| **Acceleration.Y** |Palauttaa laitteen kiihtyvyyden edestä taaksepäin. Syöttäjä saa heittäessään laitteen kiihtymään aluksi voimakkaasti, niin että sen nopeus kasvaa nollasta 90 mailiin tunnissa (132 jalkaa sekunnissa) puolessa sekunnissa. Kun laite on ilmassa (eikä ilmanvastusta huomioida), laite ei kiihdy enempää. Laitteen kiihtyvyys hidastuu, kun sieppari ottaa kopin, ja lopulta laitteen liike pysähtyy. |8.2, kun syöttäjä heittää laitteen.<br><br>0, kun laite on ilmassa.<br><br>-8.2, kun sieppari ottaa laitteesta kopin. |
| **Acceleration.Z** |Palauttaa laitteen kiihtyvyyden alhaalta ylöspäin. Kun laite on ilmassa, painovoiman vaikutukset vaikuttavat siihen. |0, ennen kuin syöttäjä heittää laitteen.<br><br>1, kun laite on ilmassa.<br><br>0, kun sieppari on ottanut laitteesta kopin. |
| **Acceleration** |Palauttaa kiihtyvyyden tietueena. |X 0, KY: 264, Z: 0}, koska syöttäjä heittää laitteen. |
| **Connection.Connected** |Palauttaa totuusarvon, joka ilmaisee, onko laite yhdistetty verkkoon |**true** |
| **Connection.Metered** |Palauttaa totuusarvon, joka ilmaisee, onko yhteys käytön mukaan laskutettava |**true** |
| **App.ActiveScreen = PlayBall** |Palauttaa totuusarvon, joka ilmaisee, näytetäänkö **PlayBall**. |**true** |
| **App.ActiveScreen.Fill** |Palauttaa näkyvissä olevan näytön taustavärin. |**Color.Green** |


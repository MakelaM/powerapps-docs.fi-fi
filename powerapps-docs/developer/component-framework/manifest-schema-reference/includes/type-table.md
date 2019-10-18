---
title: Tyyppi taulukko | Microsoft Docs
description: ''
keywords: ''
ms.author: nabuthuk
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
ms.assetid: 41ea27ac-65b6-45a4-ae03-5f8d02dfc67b
ms.openlocfilehash: 058580b8f39417ccc5e77e7ac96a51bfc95939a1
ms.sourcegitcommit: 63ea15e2f861d43333aacda19230cd8922d7bdfd
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/01/2019
ms.locfileid: "72338754"
---
|Value|Kuvaus|
|--|--|
|`Currency`|Rahamääräiset arvot välillä-922 337 203 685 477 ja 922 337 203 685 477 voivat olla tässä kentässä. Voit määrittää tarkkuuden tason tai määrittää, että tarkkuus määräytyy tietyn valuutan tai organisaation käyttämän yksittäisen vakio tarkkuuden mukaan.|
|`DateAndTime.DateAndTime`|Näyttää päivä määrän ja kellon ajan.|
|`DateAndTime.DateOnly`|Näyttää vain päivä määrän.|
|`Decimal`|Enintään 10 Desi maalin tarkkuudella voidaan käyttää arvoja välillä-100 000 000 000 ja-100 000 000 000 voi olla tässä kentässä. Voit määrittää tarkkuus tason sekä enimmäis-ja vähimmäisarvot.|
|`Enum`|Luetteloitu tieto tyyppi.|
|`FP`|Enintään viittä Desi maalien tarkkuutta voidaan käyttää arvojen välillä-100 000 000 000 ja-100 000 000 000 voi olla tässä kentässä. Voit määrittää tarkkuus tason sekä enimmäis-ja vähimmäisarvot. |
|`Multiple`|Tämä kenttä voi sisältää enintään 1 048 576 teksti merkkiä. Voit valita enimmäispituuden, joka on pienempi kuin tämä. Kun lisäät tämän kentän lomakkeeseen, voit määrittää kentän koon.|
|`OptionSet`|Tässä kentässä on joukko vaihto ehtoja. Kussakin asetuksessa on numeroarvo ja otsikko. Kun tämä kenttä lisätään lomakkeeseen, se näyttää ohjaus objektin, jonka avulla käyttäjät voivat valita vain yhden vaihto ehdon. |
|`SingleLine.Email`|Teksti tarjoaa mailto-linkin käyttäjän Sähkö posti sovelluksen avaamista varten.|
|`SingleLine.Phone`|Verkko sovelluksessa kentät ovat käytettävissä, kun ne käynnistävät puheluja joko Skypellä tai Lyncillä, jos asiakas on asennettu tieto koneeseesi. Puhelin palvelun tarjoajan valinta on järjestelmä asetusten Yleiset-väli lehden alareunassa. Dynamics 365 for tableteille Skype on ainoa käytettävissä oleva puhelin palvelu.|
|`SingleLine.Text`|Tämä vaihto ehto näyttää vain tekstin.|
|`SingleLine.TextArea`|Tätä muotoilu asetusta voidaan käyttää näyttämään useita teksti rivejä. Mutta enintään 4000 merkkiä, useita teksti rivejä-kenttä on parempi vaihto ehto, jos odotetaan suuria määriä tekstiä.|
|`SingleLine.Ticker`|Useimmissa kielissä teksti otetaan käyttöön linkkinä, joka avaa MSN Money-verkkosivuston, joka näyttää tiedot osake symbolin edustaman osakkeen hinnasta. Tietyillä Itä-Aasian kielillä ikkuna avaa Bing-haku tulokset symbolia varten.|
|`SingleLine.URL`|Teksti sisältää hyperlinkin, joka avaa määritetyn sivun. Teksti, joka ei ala käyttäen kelvollista protokollaa, on "http://". Vain HTTP-, HTTPS-, FTP-, FTPS-, ONENOTE-ja TEL-protokollat sallitaan tässä kentässä.|
|`TwoOptions`|Tässä kentässä on kaksi vaihto ehtoa. Kullakin asetuksella on numero arvo 0 tai 1, joka vastaa virheellistä tai todellista arvoa. Jokaisella asetuksella on myös otsikko, jotta tosi-tai EPÄTOSI-arvot voidaan esittää muodossa Yes ja No, Hot ja Cold, on ja off tai minkä tahansa haluamasi nimi parin.|
|`Whole.None`|Tämä vaihto ehto näyttää vain luvun.|

## <a name="value-elements-that-are-not-supported"></a>Arvo elementit, joita ei tueta

Seuraavia `of-type` määrite arvoja ei tueta tällä hetkellä:

|Value|Kuvaus|
|-----|------|
|`Whole.Duration`|Tätä muotoilu asetusta voidaan käyttää näyttämään kesto vaihtoehtojen luettelo. Tieto kantaan tallennetut tiedot ovat kuitenkin aina minuuttien määrä. Kenttä näyttää avattavasta luettelo ruudusta ja tarjoaa ehdotettuja vaihto ehtoja, kuten 1 minuutin, 15 minuuttia ja 30 minuuttia aina 3 päivään. Käyttäjät voivat valita nämä vaihto ehdot. Käyttäjät voivat kuitenkin myös kirjoittaa muutamassa minuutissa, ja se ratkaistaan kyseisenä ajan jaksona.|
|`Whole.Timezone`|Tämä vaihto ehto näyttää Valitse luettelon aika vyöhykkeistä, kuten (GMT-12:00) International Date Line West ja (GMT-08:00) Pacific Time (Yhdysvallat & Kanada). Kukin näistä alueista on tallennettu lukuna. Esimerkiksi aika vyöhykkeellä (GMT-08:00) Tyynenmeren normaaliaika (Yhdysvallat & Kanada) TimeZoneCode on 4. Lisä tietoja: [Timezonecode-luokka (SDK-kokoonpano)](https://docs.microsoft.com/en-us/previous-versions/dynamics-crm4/developers-guide/bb959779(v=msdn.10))|
|`Whole.Language`|Tämä vaihto ehto näyttää luettelon organisaatiollesi valmisteltuja kieliä. Arvot näytetään avattavassa kielen nimien luettelona, mutta tiedot tallennetaan numeroksi LCID-koodien avulla. Kielikoodit ovat neli- tai viisinumeroisia aluekohtaisten asetusten tunnuksia. Kelvolliset aluetunnukset löydät ohjeaiheesta [Aluekohtaisten asetusten tunnusten (LCID) kaavio](https://docs.microsoft.com/en-us/previous-versions/windows/embedded/ms912047(v=winembedded.10)).|
|`Lookup.Simple`|Sallii yksittäisen viitta uksen tiettyyn entiteettiin. Kaikki mukautetut haut ovat tätä tyyppiä.|
|`Lookup.Customer`|Sallii yksittäisen viitta uksen joko tiliin tai yhteyshenkilö tietueeseen. Nämä haut ovat käytettävissä mahdollisuus-, tapaus-, tarjous-, tilaus-ja lasku-entiteeteille. Näillä entiteeteillä on myös erilliset tili-ja yhteyshenkilö haut, joita voit käyttää, jos asiakkaasi ovat aina yksi tyyppi. Voit myös sisällyttää sen sen sijaan, että käyttäisit asiakas hakua.|
|`Lookup.Owner`|Sallii yksittäisen viitta uksen joko joukkueeseen tai käyttäjä tietueeseen. Kaikilla ryhmän tai käyttäjän omistamilla entiteeteillä on jokin näistä.|
|`Lookup.PartyList`|Sallii useita viitta uksia useisiin entiteetteihin. Nämä haut löytyvät Sähkö posti **-entiteetin** vastaanottaja-ja **kopio** -kentistä. Niitä käytetään myös puhelin-ja tapaamis entiteeteissä.|
|`Lookup.Regarding`|Sallii yksittäisen viitta uksen useisiin entiteetteihin. Nämä haut löytyvät aktiviteetit-kohdassa käytettävälle liittyen-kentästä.|
|`MultiSelectOptionSet`|Voit mukauttaa lomakkeita (pää-, Pikaluonti-ja pikanäkymää) ja Sähkö posti malleja lisäämällä useita valinta kenttiä. Kun lisäät Monivalintaisen asetus joukko kentän, voit määrittää useita arvoja, jotka ovat käytettävissä käyttäjien valittavissa. Kun käyttäjät täyttävät lomakkeen, he voivat valita yhden, useamman tai kaikki avattavassa luettelo kohdassa näytettävät arvot.|

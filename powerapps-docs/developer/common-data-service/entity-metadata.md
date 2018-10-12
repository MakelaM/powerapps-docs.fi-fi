---
title: Entiteettien metatiedot | Microsoft Docs
description: Tutustu entiteettien metatietojen käyttöön Common Data Service for Appsissa.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 60fafa90df656bb6d135a8cf7e2c2f3b4f8457da
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42840742"
---
# <a name="entity-metadata"></a>Kohteiden metatiedot

Jokainen entiteetti tarjoaa mahdollisuuden tallentaa jäsennettyjä tietoja. Kehittäjien näkökulmasta entiteetit vastaavat luokkia, joita he käyttävät käsitellessään tietoja Common Data Service for Appsissa.

## <a name="entity-names"></a>Entiteettien nimet
Jokaiselle entiteetille määritetään yksilöivä nimi, kun se luodaan. Tämä nimi esitetään monella tavalla:

|Nimen ominaisuus |Kuvaus|
|---------|---------|
|`SchemaName`|Tavallisesti isolla alkukirjaimella kirjoitettu versio loogisesta nimestä, esim. Tili|
|`CollectionSchemaName`|Rakenteen nimi monikkomuodossa, esim. Tilit|
|`LogicalName`|Rakenteen nimi pienillä kirjaimilla, esim. tili|
|`LogicalCollectionName`|Rakennekokoelman nimi pienillä kirjaimilla, esim. tilit|
|`EntitySetName`|Käytetään kokoelmien tunnistamiseen WWW-ohjelmointirajapinnan tapauksessa. On oletusarvoisesti sama kuin loogisen kokoelman nimi.<br />Entiteettijoukon nimeä on mahdollista muuttaa päivittämällä ohjelmallisesti metatietoja. Tämä tulee kuitenkin tehdä ennen WWW-ohjelmointirajapinnan koodin kirjoittamista entiteetille. Lisätietoja: [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: WWW-ohjelmointirajapinnan tyypit ja toiminnot > Entiteettijoukon nimen muuttaminen](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations#change-the-name-of-an-entity-set)|

> [!NOTE]
> Kun luot mukautetun entiteetin, valitsemasi nimen eteen liitetään sen ratkaisun julkaisijan, jossa entiteetti luotiin, mukautuksen etuliitearvo. Et voi muuttaa entiteetin nimiä entiteetin luomisen jälkeen entiteettijoukon nimeä lukuun ottamatta. Jos haluat ratkaisusi metatiedoille yhdenmukaiset nimet, sinun tulee luoda ne luomassasi ratkaisussa, johon liittyy ratkaisun julkaisija, joka sisältää haluamasi mukautuksen etuliitteen. Lisätietoja: [Ratkaisun julkaisijan ja ratkaisun luominen](introduction-solutions.md#create-a-solution-publisher-and-solution)

Jokaisella entiteetillä on myös kolme ominaisuutta, jotka voivat näyttää lokalisoituja arvoja:


|Nimi  |Kuvaus  |
|---------|---------|
|`DisplayName`|Tavallisesti sama kuin rakenteen nimi, mutta voi sisältää välilyöntejä, esim. Tili|
|`DisplayCollectionName`|Näyttönimi monikkomuodossa, esim. Tilit|
|`Description`|Lyhyt entiteettiä kuvaava lause, esim. *Yritys, joka edustaa asiakasta tai mahdollista asiakasta. Yhtiö, jota laskutetaan liiketoimintatapahtumissa.*|

Nämä ovat lokalisoitavat arvot, joita käytetään viittaamaan sovelluksen entiteetteihin. Näitä arvoja voidaan muuttaa milloin tahansa. Jos haluat lisätä tai muokata lokalisoituja arvoja, katso [Dynamics 365 -mukautusopas: Mukautetun entiteetin ja kenttätekstin kääntäminen muille kielille](/dynamics365/customer-engagement/customize/export-customized-entity-field-text-translation).


## <a name="primary-key"></a>Perusavain

`PrimaryIdAttribute`-ominaisuuden arvo on sen määritteen nimi, joka on entiteetin perusavain.

Kaikilla entiteeteillä on oletusarvoisesti määritteenä yksilöllinen GUID-tunnus. Sitä kutsutaan yleensä *&lt; entiteetin loogiseksi nimeksi &gt;*+ `Id`.

## <a name="primary-name"></a>Ensisijainen nimi

`PrimaryNameAttribute`-ominaisuuden arvo on sen määritteen looginen nimi, joka tallentaa entiteettitietueen identifioivan merkkijonoarvon. Tämä on se arvo, joka näkyy linkissä, jota käytetään tietueen avaamiseen käyttöliittymässä.

**Esimerkki**: Yhteyshenkilö-entiteetti käyttää `fullname`-määritettä ensisijaisena nimimääritteenä.

> [!NOTE]
> Kaikilla entiteeteillä ei ole ensisijaista nimeä. Joitain entiteettejä ei ole tarkoitettu näkymään käyttöliittymässä.

## <a name="entity-images"></a>Entiteetin kuvat

`PrimaryImageAttribute`-ominaisuuden arvo on entiteettitietueen kuvatiedot tallentavan määritteen looginen nimi. Jokaisella entiteetillä voi olla vain yksi kuvamäärite, ja tämän määritteen looginen nimi on aina `entityimage`.

**Esimerkki**: [Yhteyshenkilö-entiteetin](reference/entities/contact.md) [EntityImage](reference/entities/contact.md#BKMK_EntityImage)-määrite voi tallentaa yhteyshenkilön kuvan.

Suorituskykysyistä entiteetin kuvat eivät sisälly noutotoimintoihin, ellei tätä pyydetä eksplisiittisesti.

Jokaisella entiteetillä, joka tukee entiteetin kuvia, on kolme tukevaa määritettä.

|SchemaName|Tyyppi|Kuvaus|
|--|--|--|
|`EntityImage_Timestamp` |`BigIntType`|Arvo edustaa kuvan viimeistä päivitysajankohtaa, ja sitä käytetään apuna sen varmistamisessa, että asiakas on ladannut ja tallentanut välimuistiin kuvan uusimman version.|
|`EntityImage_URL`|`StringType`|Absoluuttinen URL-osoite entiteetin kuvan näyttämiseksi asiakassovelluksessa.|
|`EntityImageId`|`UniqueIdentifierType`|Kuvan yksilöivä tunniste|

Lisätietoja: 
- [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Kuvan määritteet](/dynamics365/customer-engagement/developer/image-attributes)
- [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Näyte: entiteetin kuvien määrittäminen ja noutaminen](/dynamics365/customer-engagement/developer/sample-set-retrieve-entity-images)

> [!NOTE]
> Tämä on eri asia kuin kuvake, joka edustaa entiteettiä malliin perustuvissa sovelluksissa. `IconVectorName`-ominaisuus sisältää SVG-verkkoresurssin, joka määrittää tämän nimen.

## <a name="types-of-entities"></a>Entiteettien tyypit

Entiteettien toiminnot ja toimintatapa määräytyvät useiden entiteetin ominaisuuksien mukaan. Useimmat näistä ominaisuuksista ovat melko yksinkertaisia, ja niillä on kuvaavat nimet. Seuraavat neljä ominaisuustyyppiä vaativat hieman lisäselityksiä: *Omistajuus*, *Toimintaentiteetit*, *ActivityParty-entiteetti* ja *Alientiteetit*.

### <a name="entity-ownership"></a>Entiteetin omistajuus

Entiteetit voidaan luokitella sen mukaan, miten niiden sisältämät tiedot omistetaan. Tämä on tärkeä käsite, joka liittyy siihen, miten suojausta sovelletaan entiteetteihin. Nämä tiedot ovat `OwnershipType`-ominaisuudessa. Seuraavassa taulukossa kuvataan eri omistajuustyypit:

|Omistajuuden tyyppi  |Kuvaus  |
|---------|---------|
|Liiketoiminta|Tiedot kuuluvat liiketoimintayksikölle. Tietojen käyttöoikeudet voidaan määrittää liiketoimintayksikön tasolla.|
|Ei mitään|Toinen entiteetti ei omista tietoja.|
|Organisaatio|Tiedot kuuluvat organisaatiolle. Tietojen käyttöoikeudet määritetään organisaation tasolla.|
|Käyttäjä tai ryhmä|Tiedot kuuluvat käyttäjälle tai ryhmälle. Toimintoja, jotka voidaan suorittaa näissä tietueissa, voidaan hallita käyttäjätasolla.|

Kun luot uusia entiteettejä, valittavissa ovat vain seuraavat omistajuusvaihtoehdot: **Organisaatio** tai **Käyttäjä tai ryhmä**. Kun olet tehnyt tämän asetuksen valinnan, et voi muuttaa sitä. Valitse **Käyttäjä tai ryhmä**, jos haluat hallita mahdollisimman tarkasti sitä, kuka voi katsella tietueita tai suorittaa niissä toimintoja. Valitse **Organisaatio**, jos näin tarkka hallinnan taso ei ole tarpeen. 

### <a name="activity-entities"></a>Toimintoentiteetit

Toiminto on tehtävä, jonka käyttäjä suorittaa tai joka hänen tulee suorittaa. Toiminto on mikä tahansa toiminto, josta voidaan tehdä merkintä kalenteriin. 

Toiminnot mallinnetaan eri tavoin kuin muunlaiset liiketoimintatietoja tallentavat entiteetit. Toimintoja koskevat tiedot näkyvät usein yhdessä luettelossa, mutta jokainen toimintotyyppi vaatii yksilöiviä ominaisuuksia. Sen sijaan, että yksittäisellä toimintoentiteetillä olisi kaikki mahdolliset ominaisuudet, käytettävissä on erityyppisiä toimintoentiteettejä, joista kukin perii ominaisuuksia perustason [ActivityPointer-entiteetiltä](reference/entities/activitypointer.md). Näiden entiteettien `IsActivity`-ominaisuuden arvoksi on asetettu ”tosi”.


|Entiteetti |Kuvaus  |
|---------|---------|
|[Appointment](reference/entities/appointment.md)|Sitoumus, joka edustaa aikaväliä, jolle on määritetty aloitus- ja lopetusajat ja kesto.|
|[Email](reference/entities/email.md)|Toiminto, joka suoritetaan sähköpostiprotokollien välityksellä.|
|[Fax](reference/entities/fax.md)|Toiminto, joka seuraa faksipuhelun lopputulosta ja sivumäärää ja valinnaisesti tallentaa tiedoston sähköisen kopion.|
|[Letter](reference/entities/letter.md)|Toiminto, joka seuraa kirjeen toimitusta perille. Toiminto voi sisältää kirjeen sähköisen kopion.|
|[PhoneCall](reference/entities/phonecall.md)|Toiminto puhelun seuraamista varten.|
|[RecurringAppointmentMaster](reference/entities/recurringappointmentmaster.md)|Toistuvien tapaamisten sarjan päätapaaminen.|
|[SocialActivity](reference/entities/socialactivity.md)|Vain sisäiseen käyttöön.|
|[Task](reference/entities/task.md)|Yleinen toiminto, joka edustaa suoritettavaa työtehtävää.|

Aina, kun käyttäjä luo jonkin tällaisista toimintoentiteettitietueista, vastaava `ActivityPointer`-entiteettitietue luodaan käyttäen samaa yksilöllisenä tunnisteena toimivaa `ActivityId`-määritearvoa. Et voi luoda, päivittää tai poistaa `ActivityPointer`-entiteetin esiintymiä, mutta voit noutaa niitä. Tämä mahdollistaa kaikentyyppisten toimintojen esittämisen yhdessä luettelossa.

Voit luoda mukautetun toiminnon entiteettejä, jotka toimivat samalla tavalla.
<!-- TODO: Add link to topic about creating an activity entity -->

### <a name="activityparty-entity"></a>ActivityParty-entiteetti

Tämän entiteetin avulla lisätään rakenne toimintoentiteettien `PartyListType`-määritteisiin, jotka sisältävät viittauksia muihin entiteetteihin. Käytät tätä entiteettiä, kun määrität arvoja toimintoentiteettien määritteille, kuten `Email.to` tai `PhoneCall.from`. [ActivityParty-entiteetin](reference/entities/activityparty.md) sisällä voit asettaa [ParticipationTypeMask](reference/entities/activityparty.md#BKMK_ParticipationTypeMask)-määritteen, joka määrittää viittauksen roolin. Rooleja ovat muun muassa `Sender`, `ToRecipient` ja `Organizer`.

Voit suorittaa `ActivityParty`-entiteettiä koskevan kyselyn, mutta et voi luoda, noutaa, päivittää tai poistaa toiminnon osapuolta sen toiminnon ulkopuolella, johon osapuoli liittyy.
Lisätietoja: 
- [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: ActivityParty-entiteetti](/dynamics365/customer-engagement/developer/activityparty-entity).


### <a name="child-entities"></a>Alientiteetit

Entiteeteille, joiden `IsChildEntity`-ominaisuus on tosi, ei koskaan määritetä oikeuksia eivätkä ne voi koskaan olla käyttäjän tai ryhmän omistamia. Toiminnot, jotka alientiteetille voidaan suorittaa, ovat sidoksissa entiteettiin, johon alientiteetit liittyvät monta-yhteen-suhteen kautta. Käyttäjät voivat suorittaa toimintoja alientiteeteille ainoastaan, jos he voivat suorittaa saman toiminnon myös niihin liittyvälle entiteetille. Alientiteetit poistetaan automaattisesti, kun entiteettitietue, josta ne ovat riippuvaisia, poistetaan.

Esimerkiksi `PostComment`, `PostLike`, ja `PostRole` ovat `Post`-entiteetin alientiteettejä.

## <a name="entity-keys"></a>Entiteettiavaimet

Jokainen vaihtoehtoinen avainmääritys kuvaa yhtä tai useampaa määritettä, jotka yhdessä yksilöivät entiteetin esiintymän. Vaihtoehtoisia avaimia käytetään yleensä vain integroinnissa ulkoisiin järjestelmiin. Voit määrittää vaihtoehtoisia avaimia tietueen yksilöimistä varten. Tästä on hyötyä silloin, kun tiedot integroidaan järjestelmään, joka ei tue yksilöllisiä GUID-tunnisteavaimia. Voit yksilöidä entiteetin määrittämällä yksittäisen kentän arvon tai kentän arvojen yhdistelmän. Vaihtoehtoisen avaimen lisääminen asettaa näille määritteille yksilöllisyysrajoituksen. Et voi luoda tai päivittää toista entiteettitietuetta siten, että se sisältäisi samat arvot.

Lisätietoja: 
 - [Dynamics 365 asiakkaalle suunnattu mukautusopas: Vaihtoehtoisten avainten määrittäminen Dynamics 365 -tietueisiin viittaamista varten](/dynamics365/customer-engagement/customize/define-alternate-keys-reference-records)
 - [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Vaihtoehtoisten avaimien määrittäminen entiteetille ja Kehittäjän opas: Dynamics 365:n tietojen synkronointi ulkoisten järjestelmien kanssa](/dynamics365/customer-engagement/developer/synchronize-dynamics-365-data-with-external-systems)

## <a name="entity-states"></a>Entiteetin tilat

Useimmilla entiteeteillä on kaksi ominaisuutta tietueen tilan seuraamista varten. Nämä ovat `StateCode`, jota kutsutaan **tilaksi** malliin perustuvissa sovelluksissa, ja `StatusCode`, jota kutsutaan **tilan syyksi** malliin perustuvissa sovelluksissa. 

Molemmat määritteet sisältävät joukon asetuksia, jotka osoittavat kelpaavat arvot. `StateCode`- ja `StatusCode`-määritearvot on linkitetty siten, että vain tietyt `StatusCode`-asetukset kelpaavat tietylle `StateCode`-määritteelle.

Tämä voi vaihdella entiteetin mukaan, mutta useiden entiteettien yleinen malli ja mukautettujen entiteettien oletusmalli on seuraava:

|StateCode-asetukset  |StatusCode-asetukset  |
|---------|---------|
|0: Käytössä|1: Käytössä|
|1: Ei käytössä|2: Ei käytössä|

Joillakin entiteeteillä on poikkeavia asetusjoukkoja. 

**Esimerkki**: `PhoneCall`-entiteetti `StateCode` ja `StatusCode`-asetukset


|`StateCode`|`StatusCode`|
|---------|---------|
|0: Avoin|1: Avoin|
|1: Valmis|2: Suoritettu <br />4: Vastaanotettu|
|2: Peruutettu|3: Peruutettu|

Tietyn entiteetin kelpaavien tilakoodien joukkoa ei voi mukauttaa, mutta tilan syyn koodit ovat mukautettavissa. Voit lisätä ylimääräisiä `StatusCode`-asetuksia vastaavalle `StateCode`lle.

Mukautettujen entiteettien tapauksessa voit määrittää lisäehtoja kelpaaville siirtymille tilojen välillä. Lisätietoja: 
- [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Entiteetin määritteiden metatietojen mukauttaminen](/dynamics365/customer-engagement/developer/customize-entity-attribute-metadata)
- [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Mukautetun tilamallin siirrosten määrittäminen](/dynamics365/customer-engagement/developer/define-custom-state-model-transitions).

### <a name="see-also"></a>Katso myös

[Common Data Service for Apps -entiteetit](entities.md)

---
title: Määritteiden metatiedot | Microsoft Docs
description: Tutustu määritteiden metatietojen käyttöön Common Data Service for Apps-palvelussa.
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
ms.date: 03/12/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: f6fcf3ba1e8e9773df65ac566a9d5c798f4d13a9
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42859157"
---
# <a name="attribute-metadata"></a>Määritteiden metatiedot

Entiteetit sisältävät kokoelman määritteitä, jotka edustavat kuhunkin tietueeseen sisällytettävissä olevia tietoja. Kehittäjien täytyy tuntea eri määritetyypit ja niiden käyttötavat. 

Lisätietoja: [Dynamics 365 Customer Engagementin kehittäjän opas: entiteettien määritteiden esittely](/dynamics365/customer-engagement/developer/introduction-entity-attributes)

## <a name="attribute-names"></a>Määritteiden nimet

Kuten entiteeteille, jokaiselle määritteelle määritetään yksilöllinen nimi luomisen yhteydessä. Tämä nimi esitetään monella tavalla:


|Nimi |Kuvaus  |
|---------|---------|
|`SchemaName`|Tämä on yleensä loogisen nimen Pascal-muotoinen versio: esimerkiksi `AccountNumber`.|
|`LogicalName`|Tämä on nimi pelkin pienin kirjaimin: esimerkiksi  `accountnumber`.|

Kun luot mukautetun määritteen, valitsemasi nimen eteen liitetään siihen ratkaisuun yhdistetyn ratkaisujulkaisijan mukautusetuliitteen arvo, jossa määrite on luotu.

Et voi muuttaa määritteen nimeä sen luomisen jälkeen.

Jokaisella määritteellä on kaksi ominaisuutta, jotka voivat näyttää lokalisoituja arvoja. Näillä arvoilla viitataan sovellukseen määritteisiin.

|Nimi |Kuvaus  |
|---------|---------|
|`DisplayName`|Yleensä tämä on sama kuin rakenteen nimi, mutta voi sisältää välilyöntejä: esimerkiksi **Account Number**.|
|`Description`|Tämä on lyhyt lause, joka kuvaa määritettä tai antaa ohjeita käyttäjälle. Tämä voi olla esimerkiksi *Kirjoita tilin tunnusnumero tai koodi, jos haluat hakea ja tunnistaa tilin nopeasti järjestelmänäkymissä.*<br />Malliin perustuvissa sovelluksissa nämä tiedot näytetään, kun käyttäjä siirtää hiiren osoittimen tämän määritteen kentän kohdalle lomakkeessa.|


Nämä ovat lokalisoitavat arvot, joilla viitataan sovelluksen määritteisiin. Näitä arvoja voi muuttaa milloin tahansa. Jos haluat lisätä tai muokata lokalisoituja arvoja, tutustu [Dynamics 365 Customer Engagementin mukautusoppaan seuraavaan kohtaan: mukautetun entiteetin ja kenttätekstin kääntäminen muille kielille](/dynamics365/customer-engagement/customize/export-customized-entity-field-text-translation).

## <a name="attribute-types"></a>Määritetyypit

`AttributeTypeName`-ominaisuus kuvaa määritetyypin. Tämä ominaisuus sisältää `AttributeTypeDisplayName`-tyyppisen arvon, joka tarjoaa selitteen kaikille eri määritetyypeille. 

> [!NOTE]
> Älä anna `AttributeType`-ominaisuuden hämmentää sinua. Tämän vanhemman ominaisuuden arvot sovitetaan yleensä `AttributeTypeName`-ominaisuuden kanssa, mutta `ImageType`-ominaisuudet näytetään `Virtual`-ominaisuuksina. Viittaa `AttributeTypeName`-ominaisuuteen `AttributeType`-ominaisuuden sijasta.

Huomioi seuraavassa taulukossa nämä:

- Nämä tyypit ryhmitellään luokittain vertailtavaksi.
- Jokaista `AttributeTypeDisplayName`-arvoa vastaava .NET-kokoonpanosta [AttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.attributemetadata)-määritteestä johdettu luokka on myös mukana, jos sellainen on käytettävissä. Näiden tyyppien ja `AttributeTypeDisplayName`-selitteen välinen suhde ei ole 1:1-suhde.
- Niissä määritetyypeissä, jotka voidaan luoda mukautettuina määritteinä, on mukana vastaava selite, joka näytetään käyttöliittymässä.


|Luokka|AttributeTypeDisplayName- tai<br />AttributeMetadata-tyyppi|Voidaan luoda /<br />selite|Kuvaus  |
|---------|---------|---------|---------|
|Luokittelu|`BooleanType`<br />[BooleanAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.booleanattributemetadata)|Kyllä<br />**Kaksi vaihtoehtoa**|Sisältää valitun asetuksen arvon kahdesta vaihtoehdosta, jotka yleensä ilmaisevat tosi/epätosi-arvoa.<br />Lisätiedot: [Asetusjoukot](#option-sets)|
|Luokittelu|`EntityNameType`<br />[EntityNameAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.entitynameattributemetadata)|Ei|Sisältää asetusarvon, joka vastaa järjestelmän entiteettiä. Tämä on vain sisäiseen käyttöön.|
|Luokittelu|`MultiSelectPicklistType`<br />[MultiSelectPicklistAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.multiselectpicklistattributemetadata)|Kyllä<br />**Monivalinta-asetusjoukko**|Sisältää useita valittuja asetusarvoja, joista voidaan valita useita vaihtoehtoja.<br />Lisätiedot: <br />[Asetusjoukot](#option-sets)<br />[Dynamics 365 Customer Engagementin kehittäjän opas: monivalintaisen valintaluettelon määritteet](/dynamics365/customer-engagement/developer/multi-select-picklist)|
|Luokittelu|`PicklistType`<br />[PicklistAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.picklistattributemetadata)|Kyllä<br />**Asetusjoukko**|Sisältää valitun asetusarvon, jossa voidaan valita yksi vaihtoehto.<br />Lisätiedot: [Asetusjoukot](#option-sets)|
|Luokittelu|`StateType`<br />[StateAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.stateattributemetadata)|Ei|Sisältää asetusarvon, joka kuvaa entiteettitietueen tilaa.<br />Lisätiedot: [Asetusjoukot](#option-sets)|
|Luokittelu|`StatusType`<br />[StatusAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.statusattributemetadata)|Ei|Sisältää asetusarvon, joka kuvaa entiteettitietueen tilan syytä.<br />Lisätiedot: [Asetusjoukot](#option-sets)|
|Kokoelma|`CalendarRulesType`|Ei|Sisältää kokoelman `CalendarRules`-entiteettitietueita.<br />Mikään määrite ei käytä tätä tyyppiä. Kun välityspalvelinta luodaan, koodin luontityökalu luo kaksi simuloitua määritettä, jotka eivät sisälly metatietoihin. Nämä määritteet edustavat näkymää kalenterisääntötietueista, jotka on yhdistetty yhdestä moneen -suhteella entiteettitietueeseen.|
|Kokoelma|`PartyListType`|Ei|Sisältää kokoelman `ActivityParty`-entiteettitietueita.<br />Lisätiedot: [ActivityParty-entiteetti](#activityparty-entity)|
|Päivämäärä ja aika|`DateTimeType`<br />[DateTimeAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.datetimeattributemetadata)|Kyllä<br />**Päivämäärä ja aika**|Tämä sisältää päivämäärän ja ajan arvon.<br />Kaikki päivämäärän ja ajan määritteet tukevat arvoja jopa ajankohtaan 1.1.1753 klo 0.00 saakka.|
|Kuva|`ImageType`<br />[ImageAttributeMetadata]()|Kyllä<br />**Kuva**|Sisältää tiedot, jotka tukevat entiteettitietueen kuvatietojen hakemista.<br />Lisätiedot: [Entiteettikuvat](entity-metadata.md#entity-images)|
|Hallittu ominaisuus|`ManagedPropertyType`<br />[ManagedPropertyAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.imageattributemetadata)|Ei|Sisältää tiedot, jotka kuvaavat sitä, voiko entiteettitietueeseen tallennettua ratkaisukomponenttia mukauttaa, kun se on mukana hallitussa ratkaisussa.<br />Lisätiedot: [Hallitut ominaisuudet](introduction-solutions.md#managed-properties)|
|Määrä|`BigIntType`<br />[BigIntAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.bigintattributemetadata)|Ei|Sisältää `BigInt`-arvon. Tämä on vain sisäiseen käyttöön.|
|Määrä|`DecimalType`<br />[DecimalAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.decimalattributemetadata)|Kyllä<br />**Desimaaliluku**|Sisältää `Decimal`-arvon. `Precision`-ominaisuus määrittää tarkkuustason.|
|Määrä|`DoubleType`<br />[DoubleAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.doubleattributemetadata)|Kyllä<br />**Liukuluku**|Sisältää `Double`-arvon. `Precision`-ominaisuus määrittää tarkkuustason.|
|Määrä|`IntegerType`<br />[IntegerAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.integerattributemetadata)|Kyllä<br />**Kokonaisluku**|Sisältää `Int`-arvon.|
|Määrä|`MoneyType`<br />[MoneyAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.moneyattributemetadata)|Kyllä<br />**Valuutta**|Sisältää `Decimal`-arvon. `PrecisionSource`-ominaisuus määrittää sen, missä tarkkuustaso määritetään.<br />0: `Precision`-ominaisuus<br />1: `Organization.PricingDecimalPrecision`-määrite<br />2: entiteettitietueen `TransactionCurrency.CurrencyPrecision`-määrite|
|Viittaus|`CustomerType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Kyllä<br />**Asiakas**|Sisältää viittauksen joko tilin tai yhteystiedon entiteettitietueeseen.|
|Viittaus|`LookupType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Kyllä<br />**Haku**|Sisältää viittauksen entiteettitietueeseen. Kelvollisten tietueiden loogiset nimet tallennetaan yleensä määritteen `Targets`-ominaisuuteen.|
|Viittaus|`OwnerType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Ei|Sisältää viittauksen joko käyttäjän tai tiimin entiteettitietueeseen.|
|Merkkijono|`MemoType`<br />[MemoAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.memoattributemetadata)|Kyllä<br />**Useita tekstirivejä**|Sisältää merkkijonoarvon, joka on tarkoitettu näytettäväksi monirivisessä tekstiruudussa.|
|Merkkijono|`StringType`<br />[StringAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.stringattributemetadata)|Kyllä<br />**Yksi tekstirivi**|Sisältää merkkijonoarvon, joka on tarkoitettu näytettäväksi yksirivisessä tekstiruudussa.|
|Yksilöllinen tunniste|`UniqueidentifierType`<br />[UniqueIdentifierAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.uniqueidentifierattributemetadata)|Ei|Sisältää yksilöllisen GUID-tunnuksen arvon.|
|Virtuaalinen|`VirtualType`|Ei|Näitä määritteitä ei voi käyttää koodissa, joten ne voi yleensä jättää huomiotta.|


## <a name="supported-operations-and-form-usage-for-attributes"></a>Määritteiden tuetut toiminnot ja käyttö lomakkeissa

Jokaisella määritteellä on totuusarvo-ominaisuuksia, jotka kuvaavat sitä, millaisissa toiminnoissa se voi olla mukana ja miten sitä voi käyttää lomakkeessa.

|Ominaisuus|Kuvaus|
|--|--|
|`IsRequiredForForm`|Määrittää, täytyykö määritteen olla mukana kenttänä lomakkeessa.|
|`IsValidForCreate`|Määrittää, voiko määritteen arvon määrittää luontitoiminnolla.|
|`IsValidForForm`|Määrittää, voiko määrite olla mukana kenttänä lomakkeessa.|
|`IsValidForRead`|Määrittää, voidaanko määritteen arvo hakea.|
|`IsValidForUpdate`|Määrittää, voiko määritteen arvon määrittää päivitystoiminnolla.|

Jos yrität määrittää luonti- tai päivitystoiminnolla sellaisen määritteen arvon, joka ei ole kelvollinen tällaiselle toiminnolla, arvo ohitetaan.
Jos yrität hakea määritteen, jonka lukeminen ei ole mahdollista, järjestelmä palauttaa null-arvon.


## <a name="attribute-requirement-level"></a>Määritteiden vaatimustaso

`RequiredLevel` on hallittu totuusarvo-ominaisuus, joka kuvaa sitä, onko määritteen arvo pakollinen.

Tälle ominaisuudelle voi määrittää seuraavat arvot:

|Nimi|Arvo|Käyttöliittymän selite|Kuvaus|
|--|--|--|--|
|`None`|0|**Valinnainen**|Mitään vaatimuksia ei ole määritetty.|
|`SystemRequired`|1|**Järjestelmän edellyttämä**|Tällä määritteellä täytyy olla arvo.|
|`ApplicationRequired`|2|**Yrityksen edellyttämä**|Yritys edellyttää, että tällä määritteellä on arvo.|
|`Recommended`|3|**Suositeltava**|Tälle määritteelle suositellaan arvoa.|

Common Data Service for Apps valvoo `SystemRequired`-asetuksen käyttöä vain järjestelmän luomissa määritteissä. Mukautettuja määritteitä ei voi määrittää käyttämään `SystemRequired`-asetusta. 

Malliin perustuvat sovellukset valvovat `ApplicationRequired`-asetuksen käyttöä. Ne esittävät `Recommended`-asetuksen eri tavalla. Mukautettujen asiakasohjelmien kehittäjät voivat näiden tietojen avulla edellyttää samankaltaisia vahvistuksia tai esitysvaihtoehtoja.

Koska tämä on hallittu ominaisuus, hallitun ratkaisun julkaisijana voit päättää, voivatko ratkaisusi käyttäjät muokata näitä määritteiden asetuksia ratkaisussasi.

Lisätiedot: [Hallitut ominaisuudet](introduction-solutions.md#managed-properties)


## <a name="rollup-and-calculated-attributes"></a>Koostetut ja lasketut määritteet

Koostettujen ja laskettujen määritteiden ansiosta käyttäjien ei tarvitse tehdä laskutoimituksia manuaalisesti, jolloin he voivat keskittyä työhönsä. Järjestelmänvalvojat voivat määrittää kentän sisältämään arvon monista yleisistä laskutoimituksista ilman kehittäjän apua. Kehittäjät voivat suorittaa näitä laskutoimituksia järjestelmän toiminnoilla, minkä ansiosta heidän ei tarvitse kirjoittaa omaa koodia niille.

Lisätiedot: 
- [Dynamics 365 Customer Engagementin mukautusopas: arvoja koostavien koostekenttien määrittäminen](/dynamics365/customer-engagement/customize/define-rollup-fields)
- [Dynamics 365 Customer Engagementin mukautusopas: lasketut ja koostetut määritteet](/dynamics365/customer-engagement/customize/define-calculated-fields)
- [Dynamics 365 Customer Engagementin kehittäjän opas: lasketut ja koostetut määritteet](/dynamics365/customer-engagement/developer/calculated-rollup-attributes)

## <a name="attribute-format"></a>Määritemuoto

Määritteen muotoarvot määrittävät, miten se näytetään malliin perustuvissa sovelluksissa. Mukautettujen sovellusten kehittäjät voivat luoda samanlaisia toimintatapoja näiden tietojen avulla.

### <a name="integer-formats"></a>Kokonaislukumuodot

`Format`-ominaisuuden ja kokonaislukumääritteiden avulla voit näyttää vaihtoehtoisia käyttöliittymätoteutuksia tälle tyypille.

|Asetus|Kuvaus|
|--|--|
|`None`|Näyttää tekstiruudun numeroarvon muokkaamiseksi.|
|`Duration`|Näyttää avattavan luettelon, joka sisältää aikavälejä. Käyttäjä voi valita arvon luetteloista tai antaa minuuttimäärän kokonaislukuarvona.|
|`TimeZone`|Näyttää aikavyöhykeluettelon sisältävän avattavan valikon.|
|`Language`|Näyttää avattavan luettelon, joka sisältää luettelon organisaatiossa käyttöön otetuista kielistä. Jos mitään muita kieliä ei ole otettu käyttöön, peruskieli on ainut vaihtoehto. Arvo tallennetaan kielen LCID-arvona.|

### <a name="string-formats"></a>Merkkijonomuodot

`FormatName`-ominaisuuden ja merkkijonomääritteiden avulla voit määrittää arvoja [StringFormatName-luokasta](/dotnet/api/microsoft.xrm.sdk.metadata.stringformatname). Näin voit hallita merkkijonomääritteen muotoilua.

|Nimi|Kuvaus|
|--|--|
|`Email`|Lomakekenttä vahvistaa tekstiarvon sähköpostiosoitteeksi ja luo mailto-linkin kenttään.|
|`PhoneNumber`|Lomakekenttä sisältää linkin Skype-puhelun soittamiseksi.|
|`PhoneticGuide`|Tämä on vain sisäiseen käyttöön.|
|`Text`|Lomake näyttää tekstiruudun.|
|`TextArea`|Lomake näyttää tekstialuekentän.|
|`TickerSymbol`|Lomake näyttää linkin, joka näyttää osakkeen kaupankäyntitunnuksen.|
|`URL`|Lomake näyttää linkin URL-osoitteen avaamiseksi.|
|`VersionNumber`|Tämä on vain sisäiseen käyttöön.|

### <a name="date-and-time-formats"></a>Päivämäärän ja kellonajan muodot

`DateTimeBehavior`-ominaisuus määrittää päivämäärän ja ajan määritteiden toiminnan.
Vaihtoehtoja on kolme:

|Asetus|Lyhyt kuvaus|
|--|--|
|`UserLocal`|Tallentaa päivämäärän ja ajan UTC-arvona järjestelmään.|
|`DateOnly`|Tallentaa todellisen päivämäärä-arvon ja aika-arvon järjestelmään muodossa 12:00 AM (00:00:00).|
|`TimeZoneIndependent`|Tallentaa todellisen päivämäärän ja ajan arvot järjestelmään käyttäjän aikavyöhykkeestä riippumatta.|

`Format`-ominaisuudella voit hallita, miten arvo näytetään malliin perustuvassa sovelluksessa riippumatta `DateTimeBehavior`-määritteestä.

|Asetus|Kuvaus|
|--|--|
|DateAndTime|Näyttää koko päivämäärän ja ajan.|
|DateOnly|Näyttää vain päivämäärän.|

Lisätiedot: [Dynamics 365 Customer Engagementin kehittäjän opas: päivämäärän ja ajan määritteen toiminta ja muoto](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute)

## <a name="auto-number-attributes"></a>Automaattinumeroidut määritteet

Voit lisätä automaattinumeroidun määritteen mille tahansa entiteetille. Tällä hetkellä voit lisätä määritteen ohjelmallisesti. Tällaisten määritteiden lisääminen ei ole mahdollista käyttöliittymässä.
Lisätiedot: [Dynamics 365 Customer Engagementin kehittäjän opas: automaattinumeroitujen määritteiden luominen](/dynamics365/customer-engagement/developer/create-auto-number-attributes)

## <a name="option-sets"></a>Asetusjoukot

Nämä ovat ne määritteet, jotka näyttävät joukon asetuksia, jotka voivat viitata asetusjoukkoon, jonka määrite voi määrittää, tai voivat viitata eri asetusjoukkoon, joka voidaan jakaa useiden määritteiden kesken. Tästä on hyötyä erityisesti silloin, kun yhden määritteen arvot koskevat myös muita määritteitä. Kun viittaat yleiseen asetusjoukkoon, voit ylläpitää asetuksia yhdessä paikassa. Jaettavissa olevat asetusjoukot ovat *yleisiä* asetusjoukkoja. Määritteessä määritetyt asetusjoukot ovat taas *paikallisia*.

### <a name="retrieve-options-data"></a>Asetustietojen hakeminen
Organisaatiopalvelu tarjoaa pyyntöluokat, joilla voit hakea määritteen käyttämät asetukset.

#### <a name="use-the-organization-service-to-retrieve-options"></a>Asetusten hakeminen organisaatiopalvelun avulla

Jokainen asetuksia sisältävä määrite perii kohteesta [EnumAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.enumattributemetadata) ja sisältää [OptionSet-ominaisuuden](/dotnet/api/microsoft.xrm.sdk.metadata.enumattributemetadata.optionset). Tämä ominaisuus sisältää kohteen [OptionSetMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.optionsetmetadata), joka sisältää asetukset [Options-ominaisuudessa](/dotnet/api/microsoft.xrm.sdk.metadata.optionsetmetadata.options). 

Organisaatiopalvelun ansiosta voit hakea tietoja asetusjoukoista seuraavien viestien avulla:

|Pyyntöluokka|Kuvaus|
|--|--|
|[RetrieveAllOptionSetsRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrievealloptionsetsrequest) |Hakee tiedot kaikista *yleisistä* asetusjoukoista.|
|[RetrieveAttributeRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrieveattributerequest) |Hakee tiedot määritteestä, joka sisältää minkä tahansa *paikallisen* asetusjoukon.|
|[RetrieveMetadataChangesRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrievemetadatachangesrequest) |Hakee metatiedot perustuen kyselyyn, joka voi sisältää *paikallisia* asetusjoukkoja.<br />Lisätiedot: [Metatietojen hakeminen ja muutosten tunnistaminen](/dynamics365/customer-engagement/developer/retrieve-detect-changes-metadata)|
|[RetrieveOptionSetRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrieveoptionsetrequest) |Hakee tiedot *yleisestä* asetusjoukosta.|

Lisätietoja: 
- [Esimerkki: määritteiden valintaluettelon metatietojen kirjoittaminen tiedostoon](/dynamics365/customer-engagement/developer/org-service/sample-dump-attribute-picklist-metadata-file)
- [Dynamics 365 Customer Engagementin kehittäjän opas: yleisten asetusjoukkojen mukauttaminen](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets)

#### <a name="use-the-web-api-to-retrieve-options"></a>Asetusten hakeminen verkko-ohjelmointirajapinnalla

Verkko-ohjelmointirajapinta tarjoaa RESTful-tyylisen tavan kysellä asetusten arvoja. Voit hakea paikalliset tai yleiset asetukset hakemalla määritteet entiteetistä. Seuraava esimerkki palauttaa [OptionSetMetadata](/dynamics365/customer-engagement/web-api/optionsetmetadata)-määritteen asetuksille, jotka sisältyvät [Account](reference/entities/account.md).[AccountCategoryCode-ominaisuuteen](reference/entities/account.md#BKMK_AccountCategoryCode).

`GET <organization url>/api/data/v9.0/EntityDefinitions(LogicalName='account')/Attributes(LogicalName='accountcategorycode')/Microsoft.Dynamics.CRM.PicklistAttributeMetadata?$select=LogicalName&$expand=OptionSet`

Verkko-ohjelmointirajapinnalla voit käyttää myös [RetrieveMetadataChanges-funktiota](/dynamics365/customer-engagement/web-api/retrievemetadatachanges).

Lisätiedot: [Dynamics 365 Customer Engagementin kehittäjän opas: metatietojen kyseleminen verkko-ohjelmointirajapinnan avulla EntityMetadata-määritteitä kyselemällä](/dynamics365/customer-engagement/developer/webapi/query-metadata-web-api#querying-entitymetadata-attributes)



## <a name="attribute-mapping"></a>Määritteiden yhdistäminen

Kun luot uuden entiteettitietueen olemassa olevan entiteettitietueen kontekstiin, voit siirtää automaattisesti tietyt arvot olemassa olevasta tietueesta oletusarvoiksi uuteen entiteettitietueeseen. Tämä helpottaa tietojen lisäämistä malliin perustuvien sovellusten käyttäjille. Käyttäjät näkevät yhdistetyt arvot ja he voivat muokata niitä ennen entiteetin tallentamista.

Mukautettuja asiakasohjelmia luovat kehittäjät voivat toteuttaa tämän saman `InitializeFrom`-viestillä (organisaatiopalvelun [InitializeFromRequest-luokka](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest) tai verkko-ohjelmointirajapinnan [InitializeFrom-funktio](/dynamics365/customer-engagement/web-api/initializefrom)), jolla he voivat hakea entiteettitiedot määritetyistä oletusarvoista.

Lisätietoja 
- [Dynamics 365 Customer Engagementin mukautusopas: entiteettikenttien yhdistäminen](/dynamics365/customer-engagement/customize/map-entity-fields#BKMK_mappingEntityFields)
- [Dynamics 365 Customer Engagementin kehittäjän opas: entiteettien ja määritteiden yhdistämisen mukauttaminen](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)

### <a name="see-also"></a>Katso myös

[Common Data Service for Apps -entiteetit](entities.md)

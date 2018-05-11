---
title: PowerApps-asiakastietoihin kohdistuvien Data Subject Rights (DSR) -pyyntöihin vastaaminen | Microsoft Docs
description: Ohjeet PowerApps-asiakastietoihin liittyviin DSR-pyyntöihin vastaamiseen
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms-topic: article
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/23/2018
ms.author: jamesol
ms.openlocfilehash: 567a1e5d93d21fc315fe61b965ffb9005111172c
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-powerapps-customer-data"></a>PowerApps-asiakastietojen rekisteröityjen tietopyyntöihin vastaaminen

## <a name="introduction-to-dsr-requests"></a>Rekisteröityjen tietopyyntöjen johdanto
Euroopan unionin (EU) yleinen tietosuoja-asetus (GDPR) antaa ihmisille (joita kutsutaan *asetuksessa rekisteröidyiksi*) oikeudet hallita henkilötietoja, joita työnantaja tai muu organisaatio tai virasto (jota kutsutaan *henkilötietorekisterinpitäjäksi* tai vain *rekisterinpitäjäksi*) on heistä kerännyt. Yleinen tietosuoja-asetus määrittää henkilötiedoiksi hyvin yleisesti mitkä tahansa tiedot, jotka liittyvät tunnistettuun tai tunnistettavissa olevaan luonnolliseen henkilöön. GPDR antaa rekisteröidyille oikeuden seuraaviin toimiin heidän henkilökohtaisiin tietoihinsa liittyen:

* Kopion saaminen
* Pyytää korjauksia
* Rajoittaa käsittelyä
* Poistaminen
* Saada tiedot sähköisessä muodossa niin, että ne voidaan siirtää toiselle ohjaajalle

Rekisteröidyn rekisterinpitäjälle tekemää virallista pyyntöä ryhtyä toimiin henkilötietoihin liittyen kutsutaan rekisteröidyn tietopyynnöksi (Data Subject Rights, DSR).

Tässä asiakirjassa kerrotaan, miten Microsoft valmistautuu yleiseen tietosuoja-asetukseen. Annamme myös esimerkkejä toimenpiteistä, joihin voit ryhtyä täyttääksesi yleisen tietosuoja-asetuksen vaatimukset, kun käytät PowerApps-sovelluksia, Microsoft Flow’ta ja Common Data Service for Appsia. Opit, miten Microsoftin tuotteet, palvelut ja hallintatyökalut auttavat rekisterinpitäjiä etsimään Microsoftin pilvipalveluissa olevia henkilötietoja ja suorittamaan niille toimintoja, jotta ne voivat vastata rekisteröityjen tietopyyntöihin.

Tässä artikkelissa käsitellään seuraavia toimintoja:

* **Etsiminen**: Haku- ja etsintätyökalulla voit etsiä helpommin asiakastietoja, jotka saattavat olla rekisteröidyn tietopyynnön kohteena. Kun mahdollisesti oleelliset tiedostot on kerätty, voit suorittaa niille rekisteröidyn tietopyynnön toimintoja, jotka kuvataan seuraavissa vaiheissa ja joilla voit vastata pyyntöön. Voit myös tulla siihen tulokseen, että pyyntö ei täytä organisaatiosi vaatimuksia rekisteröidyn tietopyyntöön vastaamiselle.

* **Tarkistaminen**: hae Microsoftin pilvipalveluihin tallennetut henkilötiedot ja ota niistä pyydettäessä kopio, jonka voit toimittaa rekisteröidylle.

* **Korjaaminen**: tee henkilötietoihin muutoksia tai suorita niille muita pyydettyjä toimintoja soveltuvin osin.

* **Rajoittaminen**: Rajoita henkilötietojen käsittelyä joko poistamalla erilaisten verkkopalveluiden käyttöoikeuksia tai poistamalla halutut palvelut käytöstä, jos se on mahdollista. Voit poistaa tietoja Microsoftin pilvipalveluista ja tallentaa ne paikallisesti tai muuhun sijaintiin.

* **Poistaminen**: poista Microsoftin pilvipalveluihin tallennetut henkilötiedot pysyvästi.

* **Vieminen**: toimita rekisteröidyn henkilötietojen kopio sähköisessä (koneluettavassa) muodossa rekisteröidylle.

## <a name="discover"></a>Etsintä
Ensimmäinen askel rekisteröidyn tietopyyntöön vastaamisessa on pyynnön kohteena olevan henkilön henkilötietojen etsiminen. Ensimmäisessä vaiheessa&mdash; siis etsit ja tarkistat kyseessä olevat henkilötiedot&mdash;. Näin voit määrittää, täyttääkö rekisteröidyn tietopyyntö organisaatiosi vaatimukset ja sitten tämän perusteella noudattaa pyyntöä tai hylätä sen. Kun löydät ja tarkistat kyseessä olevat henkilötiedot, voit esimerkiksi tulla siihen tulokseen, että pyyntö ei täytä organisaatiosi vaatimuksia, koska pyynnön noudattaminen saattaisi vaikuttaa kielteisesti muiden oikeuksiin ja vapauksiin.

### <a name="step-1-find-personal-data-for-the-user-in-powerapps"></a>Vaihe 1: käyttäjän henkilötietojen etsiminen PowerApps-sovelluksissa
Alla on yhteenveto niistä PowerApps-resurssityypeistä, jotka sisältävät käyttäjien henkilötietoja.

Henkilötietoja sisältävät resurssit |    Tarkoitus
--- | ---
Ympäristö |   Ympäristö on tila, jossa voit tallentaa, hallita ja jakaa organisaatiosi yritystietoja, -sovelluksia ja -työnkulkuja. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872239)
Ympäristön käyttöoikeudet | Käyttäjille määritetään ympäristöön roolit, jotka antavat heille tietyt käyttö- ja hallintaoikeudet ympäristössä. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872240)
Piirtoalusta-sovellus  | Eri käyttöympäristöille soveltuvia yrityssovelluksia, jotka voidaan luoda tyhjälle piirtoalustalle ja jotka voidaan yhdistää yli 200 tietolähteeseen. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872241)
Piirtoalusta-sovelluksen käyttöoikeudet  | Piirtoalusta-sovelluksia voidaan jakaa organisaation käyttäjien kanssa. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872242)
Yhteys  | Yhdistimet käyttävät yhteyksiä, jotka mahdollistavat yhteydet ohjelmointirajapintoihin, järjestelmiin, tietokantoihin jne. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872243)
Yhteyksien käyttöoikeudet  | Tietyntyyppiset yhteydet voidaan jakaa organisaation käyttäjien kanssa. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872244)
Mukautettu yhdistin    | Käyttäjä voi luoda mukautettuja yhdistimiä, joilla voidaan käyttää tietolähteitä, joiden käyttö ei ole mahdollista PowerApps-vakioyhdistimillä. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872245)
Mukautettujen yhdistimien käyttöoikeudet    | Mukautettuja yhdistimiä voidaan jakaa organisaation käyttäjien kanssa. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872246)
PowerApps-sovellusten käyttäjien ja käyttäjäsovellusten asetukset    | PowerApps-sovellukset tallentavat useita käyttäjien asetuksia, joiden avulla tarjotaan PowerApps-sovellusten suorituksenaikaisia palveluita ja portaalipalveluita.
PowerApps-ilmoitukset | PowerApps lähettää käyttäjille useita erilaisia ilmoituksia, esimerkiksi siitä, kun sovellus jaetaan heidän kanssaan tai kun Sovellusten CDS -vientitoiminto on suoritettu.
Yhdyskäytävä | Yhdyskäytävät ovat paikallisia tietoyhdyskäytäviä, joita käyttäjä voi asentaa siirtääkseen nopeasti ja turvallisesti PowerApps-sovelluksen ja sellaisen tietolähteen välillä, joka ei ole pilvessä. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872247)
Yhdyskäytävien käyttöoikeudet | Yhdyskäytäviä voidaan jakaa organisaation käyttäjien kanssa. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872249)
Mallipohjaiset sovellukset ja mallipohjaisten sovellusten käyttöoikeudet  | Mallipohjainen sovelluskehitys on komponenttikeskeinen sovelluskehitystapa. Mallipohjaiset sovellukset ja niiden käyttäjien käyttöoikeudet tallennetaan tietoihin sovellusten CDC for Apps -tietokantaan.  [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872248)

PowerApps tarjoaa seuraavat tavat etsiä tietyn käyttäjän henkilötietoja:

- **Sivustot**: [PowerApps site](https://web.powerapps.com), [PowerApps Admin center](https://admin.powerapps.com/) ja [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)
- **PowerShell**: PowerApps-sovellusten cmdlet-komennot ([sovelluskehittäjille](https://go.microsoft.com/fwlink/?linkid=871448) sekä [järjestelmänvalvojille](https://go.microsoft.com/fwlink/?linkid=871804)) ja [paikallisten yhdyskäytävien cmdlet-komennot.](https://go.microsoft.com/fwlink/?linkid=872238)

Jos haluat tarkemmat ohjeet siihen, miten voit etsiä tietyn käyttäjän henkilötietoja kustakin mainituista resurssityypeistä yllä mainituilla tavoilla, lue ohjeartikkeli [Vastaaminen DSR-pyyntöihin viedä asiakastietoja PowerApps-sovelluksista](powerapps-gdpr-export-dsr.md).

Kun löydät tiedot, voit suorittaa niille tiettyjä toimintoja vastataksesi rekisteröidyn tietopyyntöön.

### <a name="step-2-find-personal-data-for-the-user-in-microsoft-flow"></a>Vaihe 2: käyttäjän henkilötietojen etsiminen Microsoft Flow’ssa
PowerApps-käyttöoikeudet sisältävät aina Microsoft Flow -ominaisuudet. Sen lisäksi, että Microsoft Flow sisältyy PowerAppsin käyttöoikeuksiin, se on saatavilla erillisenä palvelunakin.

Saat lisätietoja Microsoft Flow -palvelua käyttäneiden käyttäjien tietojen löytämisestä ohjeartikkelista [GPDR DSR:ien suorittaminen Microsoft Flow’n asiakastiedoille](https://go.microsoft.com/fwlink/?linkid=872250).

> [!IMPORTANT]
> Suosittelemme, että järjestelmänvalvoja suorittaa tämän vaiheen PowerApps-käyttäjän puolesta.

### <a name="step-3-find-personal-data-for-the-user-in-instances-of-cds-for-apps"></a>Vaihe 3: käyttäjän henkilötietojen etsiminen CDC for Appsin käyttäjäesiintymistä
Tietyt PowerApps-käyttöoikeudet, esimerkiksi PowerAppsin yhteisön palvelupaketti, antavat organisaatiosi käyttäjille mahdollisuuden luoda sovellusten CDS:n esiintymiä sekä luoda ja kehittää sovelluksia sovellusten CDS:n avulla. PowerAppsin yhteisön palvelupaketti on maksuton käyttöoikeus, jolla käyttäjät voivat kokeilla sovellusten CDS:ää yksittäisessä ympäristössä. [PowerAppsin hinnoittelusivulta](https://powerapps.microsoft.com/pricing/) saat lisätietoa kapasiteeteista, jotka kukin PowerApps-käyttöoikeus sisältää.

Saat lisätietoja CDC for Appsin tallentamien henkilötietojen löytämisestä ohjeartikkelista [DSR:ien suorittaminen CDC for Appsin asiakastiedoille](common-data-service-gdpr-dsr-guide.md).

> [!IMPORTANT]
> Suosittelemme, että järjestelmänvalvoja suorittaa tämän vaiheen PowerApps-käyttäjän puolesta.

## <a name="rectify"></a>Korjaaminen
Jos rekisteröity pyytää sinua korjaamaan henkilötietoja, joita organisaatiosi tietoihin sisältyy, sinun ja organisaatiosi täytyy päättää, hyväksyttekö pyynnön. Tietojen korjaaminen saattaa tarkoittaa henkilötietojen muokkaamista ja poistamista tiedostossa tai muussa kohteessa.

Azure Active Directoryn avulla voit hallita PowerAppsissa olevia loppukäyttäjiesi käyttäjätietoja (henkilötietoja). Yritysasiakkaat voivat hallita rekisteröityjen korjauspyyntöjä, esimerkiksi tietyn Microsoft-palvelun rajoitetuilla muokkaustoiminnoilla. Rekisterinpitäjänä Microsoft ei tarjoa mahdollisuutta korjata järjestelmän luomia lokeja, sillä ne kuvaavat faktapohjaisia toimintoja ja täten Microsoftin palveluiden tapahtumien historiatietoja. Lisätietoja on ohjeaiheessa [GDPR: rekisteröityjen tietopyynnöt (DSR-pyynnöt)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="restrict"></a>Rajoittaminen
Rekisteröidyt voivat pyytää sinua rajoittamaan henkilötietojensa käsittelyä.  Tarjoamme sekä olemassa olevia ohjelmointirajapintoja että käyttöliittymiä.  Niiden avulla yritysasiakkaan järjestelmänvalvoja voi hallita tällaisia rekisteröityjen tietopyyntöjä viemällä ja poistamalla tietoja. Asiakas voi pyytää seuraavia:

* Asiakas voi pyytää kopiota käyttäjän henkilötiedoista. Tämä käsittää

    - tilit
    - järjestelmän luomat lokit
    - liittyvät lokit.

* Asiakas voi pyytää tilin ja siihen liittyvien tietojen poistamista Microsoftin järjestelmistä.

## <a name="export"></a>Vieminen
Oikeus tietojen siirtämiseen antaa rekisteröidylle oikeuden pyytää kopiota henkilötiedoistaan sähköisessä muodossa (yleensä tämä on jäsennelty, yleisesti käytetty, koneluettava ja yhteentoimiva muoto), jossa tiedot voidaan siirtää toiselle rekisterinpitäjälle.

Lisätietoja on ohjeaiheessa [DSR-vientipyyntöjen suorittaminen PowerApps-asiakastiedoille](powerapps-gdpr-export-dsr.md).

## <a name="delete"></a>Poistaminen
Käyttäjän oikeus tietojensa poistamiseen organisaation asiakastiedoista on yleisen tietosuoja-asetuksen keskeisimpiä oikeuksia. Henkilötietojen poistaminen käsittää järjestelmän luomat lokit, mutta ei valvontalokitietoja.

PowerApps tarjoaa käyttäjille mahdollisuuden luoda toimialakohtaisia sovelluksia, jotka ovat tärkeä osa organisaation päivittäistä toimintaa. Kun käyttäjä poistuu organisaatiosi palveluksesta, sinun täytyy tarkistaa tiedot manuaalisesti ja päättää, täytyykö tietyt tiedot ja hänen luomansa resurssit poistaa. Muut asiakastiedot poistetaan automaattisesti, kun käyttäjän tili poistetaan Microsoft Azure Active Directorysta.

Lisätietoja on ohjeaiheessa [DSR-poistopyyntöjen suorittaminen PowerApps-asiakastiedoille](powerapps-gdpr-delete-dsr.md).

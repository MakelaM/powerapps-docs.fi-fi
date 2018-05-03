---
title: 'PowerApps: opas asiakkaiden luomien tietojen rekisteröityjen tietopyynnöille | Microsoft Docs'
description: 'PowerApps: opas asiakkaiden luomien tietojen rekisteröityjen tietopyynnöille'
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
ms.date: 04/17/2018
ms.author: jamesol
ms.openlocfilehash: 823c14d0677ef96c48a26e2488bac1c91bbea225
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/20/2018
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-powerapps-customer-data"></a>PowerApps-asiakastietojen rekisteröityjen tietopyyntöihin vastaaminen

## <a name="introduction-to-dsr-requests"></a>Rekisteröityjen tietopyyntöjen johdanto
Osana pyrkimyksiämme auttaa sinua täyttämään yleisen tietosuoja-asetuksen vaatimukset olemme luoneet tämän asiakirjan, jolla voit valmistautua asetukseen. Tässä asiakirjassa kerrotaan, miten valmistaudumme yleiseen tietosuoja-asetukseen, mutta se sisältää myös esimerkkejä toimenpiteistä, joihin voit ryhtyä jo tänään Microsoftin kanssa täyttääksesi yleisen tietosuoja-asetuksen vaatimukset käyttäessäsi PowerApps-sovelluksia, Microsoft Flow’ta ja sovellusten Common Data Serviceä.

Euroopan unionin yleinen tietosuoja-asetus antaa ihmisille (joita kutsutaan asetuksessa rekisteröidyiksi) oikeudet hallita henkilötietoja, joita työnantaja tai muu organisaatio tai virasto (jota kutsutaan rekisterinpitäjäksi) on heistä kerännyt. Yleinen tietosuoja-asetus määrittää henkilötiedoiksi hyvin yleisesti mitkä tahansa tiedot, jotka liittyvät tunnistettuun tai tunnistettavissa olevaan luonnolliseen henkilöön. Yleinen tietosuoja-asetus antaa rekisteröidyille tietyt oikeudet henkilötietoihinsa. Näitä oikeuksia ovat oikeus tarkistaa henkilötiedot, oikeus pyytää henkilötietojen korjaamista, oikeus rajoittaa henkilötietojen käsittelyä, oikeus pyytää henkilötietojen poistamista ja oikeus vastaanottaa henkilötiedot sähköisessä muodossa, jotta ne voidaan siirtää toiselle rekisterinpitäjälle. Rekisteröidyn rekisterinpitäjälle tekemää virallista pyyntöä ryhtyä toimiin henkilötietoihin liittyen kutsutaan rekisteröidyn tietopyynnöksi.

Tässä oppaassa käsitellään sitä, miten Microsoftin tuotteet, palvelut ja hallintatyökalut auttavat rekisterinpitäjiä etsimään henkilötietoja ja suorittamaan niille toimintoja, jotta ne voivat vastata rekisteröityjen tietopyyntöihin. Erityisesti käsittelemme sitä, miten voit etsiä ja käyttää Microsoftin pilvipalveluihin tallennettuja henkilötietoja sekä suorittaa niille toimenpiteitä. Alla on lyhyt yleiskuvaus tässä oppaassa käsiteltävistä prosesseista:

1. **Etsiminen**: Haku- ja etsintätyökalulla voit etsiä helpommin asiakastietoja, jotka saattavat olla rekisteröidyn tietopyynnön kohteena. Kun mahdollisesti oleelliset tiedostot on kerätty, voit suorittaa niille rekisteröidyn tietopyynnön toimintoja, jotka kuvataan seuraavissa vaiheissa ja joilla voit vastata pyyntöön. Voit myös tulla siihen tulokseen, että pyyntö ei täytä organisaatiosi vaatimuksia rekisteröidyn tietopyyntöön vastaamiselle.

1. **Tarkistaminen**: hae Microsoftin pilvipalveluihin tallennetut henkilötiedot ja ota niistä pyydettäessä kopio, jonka voit toimittaa rekisteröidylle.

1. **Korjaaminen**: tee henkilötietoihin muutoksia tai suorita niille muita pyydettyjä toimintoja soveltuvin osin.

1. **Rajoittaminen**: Rajoita henkilötietojen käsittelyä joko poistamalla erilaisten verkkopalveluiden käyttöoikeuksia tai poistamalla halutut palvelut käytöstä, jos se on mahdollista. Voit poistaa tietoja Microsoftin pilvipalveluista ja tallentaa ne paikallisesti tai muuhun sijaintiin.

5. **Poistaminen**: poista Microsoftin pilvipalveluihin tallennetut henkilötiedot pysyvästi.

6. **Vieminen**: toimita rekisteröidyn henkilötietojen kopio sähköisessä (koneluettavassa) muodossa rekisteröidylle.

Kussakin tämän oppaan osiossa esitellään tekniset toimintatavat, joilla rekisterinpitäjäorganisaatio voi reagoida rekisteröidyn henkilötietopyyntöön Microsoftin pilvipalvelussa.

## <a name="discover"></a>Etsiminen
Ensimmäinen askel rekisteröidyn tietopyyntöön vastaamisessa on pyynnön kohteena olevan henkilön henkilötietojen etsiminen. Ensimmäisessä vaiheessa siis etsit ja tarkistat kyseessä olevat henkilötiedot. Näin voit määrittää, täyttääkö rekisteröidyn tietopyyntö organisaatiosi vaatimukset ja sitten tämän perusteella noudattaa pyyntöä tai hylätä sen. Kun löydät ja tarkistat kyseessä olevat henkilötiedot, voit esimerkiksi tulla siihen tulokseen, että pyyntö ei täytä organisaatiosi vaatimuksia, koska pyynnön noudattaminen saattaisi vaikuttaa kielteisesti muiden oikeuksiin ja vapauksiin.

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
PowerApps-ilmoitukset | PowerApps-sovellukset lähettävät käyttäjille useita erilaisia ilmoituksia, esimerkiksi siitä, kun sovellus jaetaan heidän kanssaan tai kun sovellusten Common Data Servicen vientitoiminto on suoritettu.
Yhdyskäytävä | Yhdyskäytävät ovat paikallisia tietoyhdyskäytäviä, joita käyttäjä voi asentaa siirtääkseen nopeasti ja turvallisesti PowerApps-sovelluksen ja sellaisen tietolähteen välillä, joka ei ole pilvessä. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872247)
Yhdyskäytävien käyttöoikeudet | Yhdyskäytäviä voidaan jakaa organisaation käyttäjien kanssa. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872249)
Mallipohjaiset sovellukset ja mallipohjaisten sovellusten käyttöoikeudet  | Mallipohjainen sovelluskehitys on komponenttikeskeinen sovelluskehitystapa. Mallipohjaiset sovellukset ja niiden käyttäjien käyttöoikeudet tallennetaan tietoihin sovellusten Common Data Servicen tietokantaan.  [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=872248)

PowerApps tarjoaa seuraavat tavat etsiä tietyn käyttäjän henkilötietoja:

- **Sivustot**: [PowerApps-sivusto](https://web.powerapps.com), [PowerApps-hallintakeskus](https://admin.powerapps.com/) ja [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)
- **PowerShell**: PowerApps-sovellusten cmdlet-komennot ([sovelluskehittäjille](https://go.microsoft.com/fwlink/?linkid=871448) sekä [järjestelmänvalvojille](https://go.microsoft.com/fwlink/?linkid=871804)) ja [paikallisten yhdyskäytävien cmdlet-komennot.](https://go.microsoft.com/fwlink/?linkid=872238)

Jos haluat tarkemmat ohjeet siihen, miten voit etsiä tietyn käyttäjän henkilötietoja kustakin mainituista resurssityypeistä yllä mainituilla tavoilla, lue ohjeartikkeli [Asiakastietojen vieminen PowerApps-sovelluksissa]( https://go.microsoft.com/fwlink/?linkid=871888).

Kun löydät tiedot, voit suorittaa niille tiettyjä toimintoja vastataksesi rekisteröidyn tietopyyntöön.

### <a name="step-2-find-personal-data-for-the-user-in-microsoft-flow"></a>Vaihe 2: käyttäjän henkilötietojen etsiminen Microsoft Flow’ssa
PowerApps-käyttöoikeudet sisältävät aina Microsoft Flow -toiminnot. Sen lisäksi, että Microsoft Flow sisältyy PowerAppsin käyttöoikeuksiin, se on saatavilla myös erillisenä palveluna.
Saat lisätietoja Microsoft Flow -palvelun tallentamien henkilötietojen etsimisestä ohjeartikkelista Rekisteröidyn tietopyyntöjen suorittaminen Microsoft Flow’n asiakastiedoille.

> [!IMPORTANT]
> Suosittelemme, että järjestelmänvalvoja suorittaa tämän vaiheen PowerApps-käyttäjän puolesta.

### <a name="step-3-find-personal-data-for-the-user-in-instances-of-common-data-service-cds-for-apps"></a>Vaihe #3: käyttäjän henkilötietojen etsiminen sovellusten Common Data Servicen (CDS) käyttäjäesiintymistä
Tietyt PowerApps-käyttöoikeudet, esimerkiksi PowerAppsin yhteisön palvelupaketti, antavat organisaatiosi käyttäjille mahdollisuuden luoda sovellusten CDS:n esiintymiä sekä luoda ja kehittää sovelluksia sovellusten CDS:n avulla. PowerAppsin yhteisön palvelupaketti on maksuton käyttöoikeus, jolla käyttäjät voivat kokeilla sovellusten CDS:ää yksittäisessä ympäristössä. [PowerAppsin hinnoittelusivulta](https://powerapps.microsoft.com/pricing/) saat lisätietoa kapasiteeteista, jotka kukin PowerApps-käyttöoikeus sisältää.

Saat lisätietoja sovellusten CDS:n tallentamien henkilötietojen etsimisestä ohjeartikkelista Rekisteröidyn tietopyyntöjen Common Data Servicen asiakastiedoille.

> [!IMPORTANT]
> Suosittelemme, että järjestelmänvalvoja suorittaa tämän vaiheen PowerApps-käyttäjän puolesta.

## <a name="rectify"></a>Korjaaminen
Jos rekisteröity pyytää sinua korjaamaan henkilötietoja, joita organisaatiosi tietoihin sisältyy, sinun ja organisaatiosi täytyy päättää, hyväksyttekö pyynnön. Tietojen korjaaminen saattaa tarkoittaa henkilötietojen muokkaamista ja poistamista tiedostossa tai muussa kohteessa.

PowerApps sisältää riippuvuuksia Azure Active Directoryyn henkilöllisyyden määrittämiseksi. Henkilöllisyydet sisältävät henkilötietoja, joten niitä voidaan muokata Azure Active Directoryssa. Yritysasiakkaat voivat hallita rekisteröityjen korjauspyyntöjä, esimerkiksi rajoitetuilla muokkaustoiminnoilla tietyn Microsoft-palvelun luoteen mukaisesti.  Rekisterinpitäjänä Microsoft ei tarjoa mahdollisuutta korjata järjestelmän luomia lokeja, sillä ne ovat faktapohjaisia toimintoja ja täten Microsoftin palveluiden tapahtumien historiatietoja. Saat lisätietoja [Office 365 Service Trust Portalin](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) Azuren rekisteröityjen tietopyyntöjen yleisen tietosuoja-asetuksen mukaisista ohjeista.

## <a name="restrict"></a>Rajoittaminen
Rekisteröidyt voivat pyytää sinua rajoittamaan henkilötietojensa käsittelyä.  Tarjoamme sekä olemassa olevia ohjelmointirajapintoja että käyttöliittymiä.  Niiden avulla yritysasiakkaan järjestelmänvalvoja voi hallita tällaisia rekisteröityjen tietopyyntöjä viemällä ja poistamalla tietoja. Asiakas voi pyytää seuraavia:

- Asiakas voi pyytää kopiota käyttäjän henkilötiedoista. Tämä käsittää

    - tilit
    - järjestelmän luomat lokit
    - liittyvät lokit.
- Asiakas voi pyytää tilin ja siihen liittyvien tietojen poistamista Microsoftin järjestelmistä.

## <a name="export"></a>Vieminen
Oikeus tietojen siirtämiseen antaa rekisteröidylle oikeuden pyytää kopiota henkilötiedoistaan sähköisessä muodossa (yleensä tämä on jäsennelty, yleisesti käytetty, koneluettava ja yhteentoimiva muoto), jolla tiedot voidaan siirtää toiselle rekisterinpitäjälle.

Saat lisätietoja ohjeartikkelista [Rekisteröityjen tietopyyntöjen vientitoimintojen suorittaminen PowerApps-asiakastiedoille](https://go.microsoft.com/fwlink/?linkid=871888).

## <a name="delete"></a>Poistaminen
Käyttäjän oikeus tietojensa poistamiseen organisaation asiakastiedoista on yleisen tietosuoja-asetuksen keskeisimpiä oikeuksia. Henkilötietojen poistaminen käsittää järjestelmän luomat lokit, mutta ei valvontalokitietoja.

PowerApps tarjoaa käyttäjille mahdollisuuden luoda toimialakohtaisia sovelluksia, jotka ovat tärkeä osa organisaation päivittäistä toimintaa. Kun käyttäjä poistuu organisaatiosi palveluksesta, sinun täytyy tarkistaa tiedot manuaalisesti ja päättää, täytyykö tietyt tiedot ja hänen luomansa resurssit poistaa. Muut asiakastiedot poistetaan automaattisesti, kun käyttäjän tili poistetaan Microsoft Azure Active Directorysta.

Saat lisätietoja ohjeartikkelista [Rekisteröityjen tietopyyntöjen poistotoimintojen suorittaminen PowerApps-asiakastiedoille](https://go.microsoft.com/fwlink/?linkid=871883).

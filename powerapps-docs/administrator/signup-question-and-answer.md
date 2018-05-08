---
title: Lisenssien hallinta organisaatiossani | Microsoft Docs
description: Yleisiä kysymyksiä ja vastauksia lisensseistä, hallinnasta ja käyttäjien rekisteröitymisestä PowerAppsiin Office 365 -vuokraajassasi
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: jamesol
ms.openlocfilehash: 5d6db5bded909387b5bc4ef15dc0bf6c163bfa7a
ms.sourcegitcommit: 078ba325480147e6e4da61e319ed53219f1c5cfc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/06/2018
---
# <a name="manage-licenses-in-my-org"></a>Lisenssien hallinta organisaatiossani
Tässä aiheessa kuvataan, miten organisaatiosi käyttäjät voivat saada PowerAppsin käyttöoikeuden ja miten voit hallita pääsyä PowerApps-palveluun.

## <a name="sign-up-for-powerapps"></a>PowerAppsiin rekisteröityminen
### <a name="what-is-powerapps"></a>Mikä on PowerApps?
Microsoft PowerAppsin avulla käyttäjät voivat luoda sovelluksia Windows-, iOS- ja Android-mobiililaitteille. Näiden sovellusten avulla voit luoda yhteyksiä yleisiin SaaS-palveluihin, kuten Twitter, Office 365, Dropbox ja Excel.

### <a name="how-do-users-sign-up-for-powerapps"></a>Miten käyttäjät voivat rekisteröityä PowerAppsiin?
Organisaatiosi yksittäisten käyttäjien ainoa rekisteröitymisvaihtoehto on PowerAppsin palvelupaketin 2 kokeiluversio, jota varten he voivat rekisteröityä PowerApps-verkkosivustolla:

##### <a name="option-1"></a>Vaihtoehto 1
Käyttäjät voivat rekisteröityä osoitteessa [powerapps.microsoft.com](https://powerapps.microsoft.com). Käyttäjien tulee valita vaihtoehto **Sign up free** ja toteuttaa PowerAppsin rekisteröitymisvaiheet osoitteessa [portal.office.com](https://portal.office.com/Start?sku=powerapps).

##### <a name="option-2"></a>Vaihtoehto 2
Käyttäjät voivat rekisteröityä osoitteessa [powerapps.microsoft.com](https://powerapps.microsoft.com). Käyttäjien tulee valita vaihtoehto **Sign in**, kirjautua sisään työ- tai koulutileilleen ja rekisteröityä PowerAppsin palvelupaketin 2 kokeiluversiota varten hyväksymällä PowerAppsin käyttöehdot.    

Kun organisaatiosi käyttäjä rekisteröityy PowerAppsiin, hän saa automaattisesti PowerApps-lisenssin.

> [!NOTE]
> Käyttäjät, jotka hankkivat kokeiluversion lisenssin PowerAppsin kautta, eivät näy Office 365 -hallintaportaalissa PowerAppsin palvelupaketin 2 kokeiluversion käyttäjinä (ellei heillä ole toista Office 365:n, Dynamics 365:n tai PowerAppsin lisenssiä).

Katso lisätietoja [Omatoiminen kirjautuminen PowerAppsiin](../maker/signup-for-powerapps.md) -osiosta.

### <a name="how-can-users-in-my-organization-gain-access-to-powerapps"></a>Miten organisaationi käyttäjät voivat saada pääsyn PowerAppsiin?
Organisaatiosi käyttäjät voivat saada pääsyn PowerAppsiin kolmella eri tavalla:

* He voivat rekisteröityä omatoimisesti PowerAppsin palvelupaketin 2 kokeiluversion käyttäjiksi, kuten [Miten käyttäjät voivat rekisteröityä PowerAppsiin?](#how-do-users-sign-up-for-powerapps) -osiossa kerrotaan.
* Voit antaa heille PowerApps-lisenssin Office 365 -hallintaportaalissa.
* Käyttäjälle on annettu Office 365- ja Dynamics 365 -sopimukset, joihin sisältyy pääsy PowerApps-palveluun. Katso [PowerAppsin hinnoittelusivulta](https://powerapps.microsoft.com/pricing) luettelo Office 365- ja Dynamics 365 -sopimuksista, joihin sisältyy PowerApps-ominaisuudet.

### <a name="can-i-block-users-in-my-organization-from-signing-up-for-powerapps"></a>Voinko estää organisaationi käyttäjiä kirjautumasta PowerAppsiin?
Kuka tahansa voi kokeilla 30 päivän ajan Microsoft PowerAppsin palvelupaketin 2 ominaisuuksia. Tästä ei aiheudu mitään kustannuksia, kuten [Miten käyttäjät voivat rekisteröityä PowerAppsiin?](#how-do-users-sign-up-for-powerapps) -osiossa kerrotaan.  Tämä vaihtoehto on saatavilla kenelle tahansa vuokraajan käyttäjälle, eikä järjestelmänvalvoja voi estää sitä.  Käyttäjän kokeilun päätyttyä käyttäjä menettää PowerAppsin palvelupaketin 2 ominaisuuksien käyttöoikeudet.  

Jos käyttäjä hankkii 30 päivän kokeiluversion Microsoft PowerAppsin palvelupaketista 2, etkä halua tukea käyttäjää organisaation sisältä, tästä ei voi millään tavalla aiheutua kustannuksia yrityksellesi. Kun käyttäjä rekisteröityy Microsoft PowerAppsiin, kyseessä on tämän henkilön ja Microsoftin välinen suora sopimussuhde, aivan kuten Microsoftin julkisissa pilvipalveluissa (esimerkiksi Bing, Wunderlist, OneDrive tai Outlook.com), eikä tämä tarkoita millään tavalla, että palvelun tarjoaisi sinun organisaatiosi.

Lisäksi, jos yrityksesi haluaa rajoittaa vain organisaatiolle kuuluvien tietojen käyttöä Microsoft PowerAppsin sisällä, se on mahdollista tietojen menetyksen estämiskäytäntöjen (DPL) avulla. Katso lisätietoja [tietojen menetyksen estämiskäytännöistä (DLP)](prevent-data-loss.md).

## <a name="administration-of-powerapps"></a>PowerAppsin hallinta
### <a name="why-has-the-powerapps-icon-appeared-in-the-office-365-app-launcher"></a>Miksi PowerApps-kuvake näkyy Office 365 -sovelluksen käynnistyksen yhteydessä?
Microsoft PowerApps on olennainen osa Office 365 -pakettia ja käytössä palveluna osana nykyistä Office 365 -SKU:ta. Kuvake näkyy käynnistysnäytöllä kohdassa Kaikki sovellukset, sillä käyttäjät ympäri maailmaa voivat nyt käyttää Microsoft PowerAppsia. Katso [Käyttöoikeuksien yleiskatsauksesta](pricing-billing-skus.md), mihin Office 365 -SKU:ihin kuuluu nykyään PowerApps.

Lue seuraava osio, jos haluat poistaa PowerApps-ruudun oletuksena Kaikki sovellukset -kohdasta.

### <a name="how-do-i-remove-powerapps-from-existing-users"></a>Miten voin poistaa PowerAppsin nykyisiltä käyttäjiltä?
Jos käyttäjälle on annettu PowerAppsin palvelupaketin 1 tai PowerAppsin palvelupaketin 2 lisenssi, voit suorittaa seuraavat vaiheet PowerApps-käyttöoikeuden poistamiseksi kyseiseltä käyttäjältä:

1. Siirry [Office 365 -hallintaportaaliin](https://portal.microsoftonline.com/).

2. Valitse vasemmassa siirtymispalkissa **Käyttäjät** ja valitse sitten **Aktiiviset käyttäjät**.

3. Etsi käyttäjä, jolta haluat poistaa lisenssin, ja valitse sitten hänen nimensä.

4. Valitse käyttäjätietoruudun **Tuotteiden lisenssit** -kohdassa **Muokkaa**.

5. Etsi lisenssi **Microsoft PowerAppsin palvelupaketti 1** tai **Microsoft PowerAppsin palvelupaketti 2**, valitse **Pois päältä** ja sitten **Tallenna**.

    ![](./media/signup-question-and-answer/remove-license.png)

Jos käyttäjillä on pääsy PowerAppsiin Office 365- ja Dynamics 365 -sopimuksen lisenssien kautta, voit estää heiltä PowerApps-palvelun käytön näin:

1. Siirry [Office 365 -hallintaportaaliin](https://portal.microsoftonline.com/).

2. Valitse vasemmassa siirtymispalkissa **Käyttäjät** ja valitse sitten **Aktiiviset käyttäjät**.

3. Etsi käyttäjä, jolta haluat estää käytön, ja valitse sitten heidän nimensä.

4. Valitse käyttäjätietoruudun **Tuotteiden lisenssit** -kohdassa **Muokkaa**.

5. Laajenna käyttäjän Office 365- tai Dynamics 365 -lisenssiä, estä pääsy **PowerApps Office 365:a varten** -palveluun tai **PowerApps Dynamics 365:a varten** -palveluun ja valitse sitten **Tallenna**.

    ![](./media/signup-question-and-answer/remove-service-plan.png)

Lisenssien joukkopoistaminen on myös mahdollista PowerShellin avulla. Katso [Lisenssien poistaminen käyttäjätileiltä Office 365 PowerShellin avulla](https://technet.microsoft.com/library/dn771774.aspx) -osiosta yksityiskohtainen esimerkki.   Lisää ohjeita palveluiden joukkopoistamiseen lisensseistä löytyy [Palveluiden käytön estäminen Office 365 PowerShellin avulla](https://technet.microsoft.com/library/dn771769.aspx) -osiosta.

Kun PowerApps-lisenssi tai -palvelu poistetaan organisaatiosi käyttäjältä, myös PowerApps- ja Dynamics 365 -kuvakkeet poistuvat käyttäjältä seuraavista sijainneista:

* [Office.com](https://office.com)

    ![](./media/signup-question-and-answer/office-home.png)
* Office 365:n AppLauncher-vohveli

    ![](./media/signup-question-and-answer/office-waffle.png)

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data-using-powerapps"></a>Kuinka voin rajoittaa käyttäjien pääsyä organisaationi yritystietoihin PowerAppsin avulla?
PowerAppsin avulla voit luoda tietovyöhykkeitä yritystiedoille ja muille tiedoille, kuten alempana näytetään.  Kun nämä tietojen menetyksen estämiskäytännön vaiheet on toteutettu, käyttäjät eivät pysty suunnittelemaan tai suorittamaan PowerAppsia, jossa yhdistyvät yritystiedot ja muut tiedot. Katso lisätietoja [tietojen menetyksen estämiskäytännöistä (DLP)](prevent-data-loss.md).

![](./media/signup-question-and-answer/data-loss-prevention-policy.png)

### <a name="why-did-10000-licenses-for-microsoft-powerapps-show-up-in-my-office-365-tenant"></a>Miksi Office 365 -vuokraajassani näkyy 10 000 Microsoft PowerApps - lisenssiä?
Kelvollisten organisaatioiden käyttäjillä on oikeus kokeilla 30 päivän ajan Microsoft PowerAppsin palvelupakettia 2. Nämä kokeiluversioiden lisenssit ovat vuokraajasi saatavilla oleva, uusien PowerApps-käyttäjien kapasiteetti. Näistä lisensseistä ei veloiteta maksua. Office 365 -hallintaportaalissa saattaa näkyä 10 000 PowerApps-lisenssin (kokeiluversioita) kapasiteetti erityisesti kahdesta mahdollisesta syystä:

* Jos vähintään yksi vuokraajasi käyttäjä osallistui PowerAppsin julkiseen esikatseluun, joka pidettiin huhtikuusta 2016 lokakuuhun 2016, näet 10 000 lisenssiä, joilla on luokitus ”Microsoft PowerApps ja logiikkavuot”.

    ![](./media/signup-question-and-answer/licenses_2.png)
* Jos vähintään yksi vuokraajasi käyttäjä on hankkinut PowerAppsin palvelupaketin 2 kokeiluversion käymällä läpi kokeilurekisteröitymisen [Miten käyttäjät voivat rekisteröityä PowerAppsiin?](#how-do-users-sign-up-for-powerapps) -osiossa esitellyn **Vaihtoehdon 1**, näet 10 000 lisenssiä, joilla on luokitus ”Microsoft PowerApps ja vuo”.

    ![](./media/signup-question-and-answer/licenses_1.png)

Voit päättää antaa itse lisälisenssejä käyttäjille Office 365 -hallintaportaalin kautta, mutta ota huomioon, että nämä ovat Microsoft PowerAppsin palvelupaketin 2 kokeiluversion lisenssejä, ja ne vanhenevat 30 päivän kuluessa siitä, kun ne on annettu käyttäjälle.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Onko tämä ilmaista? Pitääkö minun maksaa näistä lisensseistä?
Nämä ovat kokeiluversion maksuttomia lisenssejä, joita organisaatiosi käyttäjät voivat kokeilla 30 päivän ajan Microsoft PowerAppsin palvelupaketin 2 osalta.

### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Miten tämä muuttaa tapaa, jolla hallinnoin tällä hetkellä organisaationi käyttäjien käyttäjätietoja?
Jos organisaatiossasi on jo käytössä Office 365 -ympäristö, ja kaikilla käyttäjillä organisaatiossasi on Office 365 -tilit, käyttäjätietojen hallinnointi ei muutu.

Jos organisaatiossasi on jo käytössä Office 365 -ympäristö, mutta kaikilla käyttäjillä organisaatiossasi ei ole Office 365 -tiliä, luomme käyttäjätilin vuokraajaan ja myönnämme lisenssejä käyttäjän työn tai koulun sähköpostiosoitteen perusteella. Tämä tarkoittaa sitä, että niiden käyttäjien, joiden tietoja hallinnoit tietyllä hetkellä, lukumäärä kasvaa, kun organisaatiosi käyttäjät rekisteröityvät palveluun.

Jos organisaatiollasi ei ole sähköpostisi toimialueeseen liitettyä Office 365 -ympäristöä, käyttäjätietojen hallinnointitapa ei muutu. Käyttäjät lisätään uuteen vain pilvi -käyttäjähakemistoon, ja sinulla on mahdollisuus ottaa tiedot hallintaasi vuokraajan järjestelmänvalvojana ja hallinnoida tietoja.

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Millä tavalla Microsoftin käyttäjiäni varten luomaa vuokraajaa voi hallinnoida?
Jos Microsoft on luonut vuokraajan, voit vaatia vuokraajaa käyttöösi ja hallinnoida sitä seuraavien vaiheiden avulla:

1. Liity vuokraajaan kirjautumalla PowerAppsiin samalla sähköpostiosoitteesi toimialueella, joka vastaa sen vuokraajan toimialuetta, jota haluat hallinnoida. Jos Microsoft on esimerkiksi luonut contoso.com-vuokraajan, liity vuokraajaan sähköpostiosoitteella, joka päättyy seuraavasti: @contoso.com
2. Ota järjestelmänvalvojan oikeutesi käyttöön vahvistamalla toimialueen omistajuus: kun olet kirjautunut sisään vuokraajaan, voit antaa itsellesi järjestelmänvalvojan oikeudet vahvistamalla toimialueen omistajuuden. Toimi seuraavasti:
3. Siirry kohteeseen [https://portal.office.com](https://portal.office.com/Start?sku=powerapps).
4. Valitse sovelluksen käynnistyskuvake vasemmasta yläkulmasta ja sitten Järjestelmänvalvoja.
5. Lue ohjeet **Ryhdy järjestelmänvalvojaksi** -sivustolta ja valitse sitten **Kyllä, haluan ryhtyä järjestelmänvalvojaksi**.  

> [!NOTE]
> Jos tämä vaihtoehto ei ole näkyvillä, Office 365 -järjestelmänvalvoja on jo määritetty.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Jos minulla on useita toimialueita, voinko hallinnoida Office 365 -vuokraajaa, johon käyttäjät on lisätty?
Jos et tee mitään toimenpiteitä, vuokraaja luodaan jokaista käyttäjän sähköpostin toimialuetta ja alitoimialuetta varten.

Jos haluat, että kaikki käyttäjät sijaitsevat samassa vuokraajassa riippumatta käyttäjien sähköpostiosoitteen tunnisteista:  

* Luo kohdevuokraaja etukäteen tai käytä olemassa olevaa vuokraajaa. Lisää kaikki olemassa olevat toimialueet ja alitoimialueet, jotka haluat yhdistää siihen vuokraajaan. Sitten kaikki käyttäjät, joiden sähköpostiosoitteet päättyvät niihin toimialueisiin ja alitoimialueisiin, liittyvät automaattisesti kohdevuokraajaan rekisteröitymisen yhteydessä.

> [!IMPORTANT]
> Ei ole olemassa tuettua automaattista mekanismia käyttäjien poistamiseksi kaikista vuokraajista, kun ne on luotu. Lue toimialueiden lisäämisestä yksittäiseen Office 365 -vuokraajaan [Käyttäjien ja toimialueen lisääminen Office 365:een](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7) -osiosta.

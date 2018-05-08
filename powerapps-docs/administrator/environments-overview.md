---
title: Ympäristöjen yleiskatsaus | Microsoft Docs
description: Mitä ympäristöt ovat, ja miten niitä käytetään?
services: powerapps
suite: powerapps
documentationcenter: na
author: manasmams
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 4b71f931aa3e8263166d52b68ba375917405c2b8
ms.sourcegitcommit: 078ba325480147e6e4da61e319ed53219f1c5cfc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/06/2018
---
# <a name="environments-overview"></a>Ympäristöjen yleiskatsaus
Ympäristö on tila, jossa voit tallentaa, hallita ja jakaa organisaatiosi yritystietoja, sovelluksia ja työnkulkuja. Lisäksi niitä käytetään säilöinä erillisille sovelluksille, joilla voi olla eri rooleja, suojausvaatimuksia tai kohdekäyttäjäryhmiä. Ympäristöjen hyödyntämistapa riippuu organisaatiosta ja kehitettävistä sovelluksista. Esimerkki:

* Voit käyttää sovellusten luomiseen halutessasi vain yhtä ympäristöä.
* Voit luoda erillisiä ympäristöjä, joihin sovellusten testi- ja tuoteversiot ryhmitellään.
* Voit luoda erillisiä ympäristöjä, jotka vastaavat yrityksesi tiettyjä ryhmiä tai osastoja. Kukin ympäristö sisältää kullekin käyttäjäryhmälle olennaiset tiedot ja sovellukset.
* Voit myös luoda erillisiä ympäristöjä yrityksen yleisille haaroille.  

## <a name="environment-scope"></a>Ympäristön vaikutusalue
Jokainen ympäristö luodaan Azure AD -vuokraajan alaisuudessa. Ympäristön resursseihin pääsevät käsiksi vain kyseisessä vuokraajassa olevat käyttäjät. Ympäristö sidotaan myös maantieteelliseen sijaintiin, kuten Yhdysvaltoihin. Tietyssä ympäristössä luotu sovellus reititetään vain kyseisen maantieteellisen alueen palvelinkeskuksiin. Myös ympäristössä luodut kohteet (esimerkiksi yhteydet, yhdyskäytävät ja Microsoft Flow -työnkulut) sidotaan ympäristön sijaintiin.

Jokaisella ympäristöllä voi olla enintään yksi Common Data Service -tietokanta, joka tarjoaa tallennustilaa sovelluksille. Mahdollisuus luoda tietokanta ympäristölle riippuu PowerAppsiin ostamastasi käyttöoikeudesta ja käyttöoikeudestasi kyseisessä ympäristössä. Lisätietoja löytyy kohdasta [Hinnoittelutiedot](pricing-billing-skus.md).

Kun luot sovelluksen ympäristössä, sovelluksella on lupa muodostaa yhteys vain samassa ympäristössä käytössä oleviin tietolähteisiin. Näihin tietolähteisiin kuuluvat muun muassa yhteydet, yhdyskäytävät, työnkulut ja Common Data Service -tietokannat.  Seuraavassa esimerkkitilanteessa olet luonut kaksi ympäristöä nimeltä ”Testi” ja ”Kehitys” sekä Common Data Service -tietokannan molempiin ympäristöihin. Jos luot sovelluksen testiympäristössä, se voi muodostaa yhteyden ainoastaan testitietokantaan, ei kehitystietokantaan.

Resursseja voidaan myös siirtää ympäristöstä toiseen erillisellä prosessilla. Lisätietoja saat kohdasta [Resurssien siirtäminen](environment-and-tenant-migration.md).

![](./media/environments-overview/Environments.png)

## <a name="environment-permissions"></a>Ympäristön käyttöoikeudet
Ympäristöillä on kaksi sisäistä roolia, jotka pääsevät käsiksi ympäristön käyttöoikeuksiin:

* Ympäristön järjestelmänvalvoja pystyy suorittamaan kaikki ympäristön järjestelmänvalvojan toiminnot, mukaan lukien:

    * ympäristön järjestelmänvalvojan tai ympäristön tekijän roolin lisääminen tai poistaminen käyttäjältä ja ryhmältä

    * Common Data Service -tietokannan valmisteleminen ympäristölle

    * kaikkien ympäristössä luotujen resurssien tarkasteleminen ja hallitseminen

    * tietojen menetyksen estämiskäytäntöjen määrittäminen. Lisätietoa saat kohdasta [Tietojen menetyksen estämiskäytännöt](prevent-data-loss.md).

    Kun olet luonut tietokannan ympäristössä, voit käyttää järjestelmänvalvojan roolia ympäristön järjestelmänvalvojan sijaan.

* Ympäristön tekijä -rooli voi luoda resursseja ympäristössä. Resursseja ovat esimerkiksi sovellukset, yhteydet, mukautetut liittimet, yhdyskäytävät ja Microsoft Flow -työnkulut.

Ympäristön tekijät voivat myös jakaa ympäristössä luomiaan sovelluksia muille käyttäjille organisaatiossa. Tämä tapahtuu jakamalla sovellus yksittäiselle käyttäjälle, käyttöoikeusryhmälle tai kaikille organisaation käyttäjille. Lisätietoja saat kohdasta [Sovelluksen jakaminen PowerAppsissa](../maker/canvas-apps/share-app.md).

Ympäristön rooleihin määritetyt käyttäjät tai ryhmät eivät saa automaattisesti käyttöoikeutta ympäristön tietokantaan (jos sellainen on olemassa), vaan tietokannan omistajan täytyy antaa se erikseen. Lisätietoa saat kohdasta [Määritä tietokannan suojaus](database-security.md).

Ympäristön järjestelmänvalvoja voi määrittää käyttäjän tai käyttöoikeusryhmän jompaankumpaan näistä rooleista [PowerAppsin hallintakeskuksessa][1]. Lisätietoja on [PowerAppsin Ympäristöjen hallinta](environments-administration.md) -osiossa.

![](./media/environments-overview/EnvironmentRoles.png)

## <a name="the-default-environment"></a>Oletusympäristö
PowerApps luo automaattisesti yhden oletusympäristön jokaiselle vuokraajalle. Oletusympäristö jaetaan kaikille käyttäjille kyseisessä vuokraajassa. Kun uusi käyttäjä rekisteröityy PowerAppsiin, hänet lisätään automaattisesti oletusympäristön tekijän rooliin. Oletusympäristö luodaan oletusarvoisesti AAD-vuokraajan oletusaluetta lähimpänä olevalle alueelle.

> [!NOTE]
> Oletusympäristön ympäristön järjestelmänvalvoja -rooliin ei lisätä automaattisesti yhtään käyttäjää. Lisätietoja on [PowerAppsin Ympäristöjen hallinta](environments-administration.md) -kohdassa.
>
>

Oletusympäristö nimetään seuraavasti: ”{Azure AD -vuokraajan nimi} (oletus)”

![](./media/environments-overview/DefaultEnvironment.png)

## <a name="production-and-trial-environments"></a>Tuotanto- ja kokeiluympäristöt
Voit luoda ympäristöjä eri tarkoituksiin. Kokeiluympäristö on tarkoitettu ympäristön ja tietokannan kokeiluun Common Data Service -kokemuksen kanssa. Se vanhentuu tietyn ajan kuluessa. Lisätietoja on [PowerAppsin Ympäristöjen hallinta](environments-administration.md) -osiossa.

## <a name="choosing-an-environment"></a>Ympäristön valitseminen
Ympäristöjen myötä näet nyt uuden kokemuksen, kun saavut osoitteeseen [https://web.powerapps.com](https://web.powerapps.com).  Sovellukset, yhteydet ja muut sivustolla näytettävät kohteet suodatetaan nyt nykyisen valittuna olevan ympäristön perusteella.  Nykyinen ympäristö näytetään otsikon oikean reunan lähellä olevassa ympäristövalitsimessa. Jos haluat valita eri ympäristöön, napsauta tai napauta valitsinta, jolloin näkyviin tulee luettelo käytettävissä olevista ympäristöistä. Napsauta tai napauta ympäristöä, jonka haluat ottaa käyttöön.

Ympäristö näytetään valitsimessa, jos jokin seuraavista ehdoista täyttyy:

* Olet ympäristön järjestelmänvalvoja kyseisessä ympäristössä.
* Olet ympäristön tekijä kyseisessä ympäristössä.
* Et ole ympäristön järjestelmänvalvoja tai ympäristön tekijä kyseisessä ympäristössä, mutta sinulle on annettu osallistuja-käyttöoikeus vähintään yhteen ympäristössä olevaan sovellukseen. Lisätietoja saat kohdasta [sovelluksen jakaminen](../maker/canvas-apps/share-app.md). Tässä tapauksessa et voi luoda sovelluksia tässä ympäristössä. Voi vain muokata nykyisiä sovelluksia, jotka on jaettu kanssasi.

![](./media/environments-overview/EnvironmentPicker.png)

## <a name="creating-an-environment"></a>Ympäristön luominen
### <a name="who-can-create-environments"></a>Kuka voi luoda ympäristöjä?
Käyttöoikeutesi määrittää, voitko luoda ympäristöjä.

| Käyttöoikeus | Ympäristön luonti sallitaan |
| --- | --- |
| PowerApps P2 |√ (kaksi tuotantoympäristöä ja kaksi kokeiluympäristöä)|
| PowerApps P2 -kokeilu |√ (kaksi kokeiluympäristöä)|
| PowerApps P1 |x |
| PowerApps P1 -kokeilu |x |
| Dynamics 365 -palvelupaketit |x |
| Office 365 -palvelupaketit |x |
| Dynamics 365 -sovellukset ja Teams-palvelupaketit |x |


### <a name="where-can-environments-be-created"></a>Missä ympäristöjä luodaan?
Voit luoda uusia ympäristöjä osoitteessa [PowerApps.com][2] tai [PowerAppsin hallintakeskuksesta][1]. Jos luot ympäristön, sinut lisätään automaattisesti kyseisen ympäristön järjestelmänvalvojaksi. Voit osallistua ympäristön järjestelmänvalvojan tai ympäristön tekijän rooleissa useisiin eri ympäristöihin, joiden määrää ei ole rajoitettu. Lisätietoja ympäristöistä on [PowerAppsin Ympäristöjen hallinta](environments-administration.md) -kohdassa. Katso ympäristön luomista koskevat ohjeet [Ympäristön luominen](create-environment.md) -osiossa.

![](./media/environments-overview/CreateEnvironmentDialog-New.png)


## <a name="managing-environments-for-your-organization"></a>Organisaation ympäristöjen hallinta
PowerApps-hallintakeskuksessa voit hallita kaikkia ympäristöjä, jotka olet luonut tai joihin sinut on lisätty ympäristön järjestelmänvalvojaksi. PowerApps-hallintakeskuksesta käsin pystyt suorittamaan kaikki ympäristöä koskevat hallinnalliset toiminnot, mukaan lukien:

* ympäristön järjestelmänvalvojan tai ympäristön tekijän roolin lisääminen tai poistaminen käyttäjältä ja ryhmältä.  Lisätietoja on [PowerAppsin Ympäristöjen hallinta](environments-administration.md) -osiossa.
* Common Data Service -tietokannan valmisteleminen ympäristölle Lisätietoja on [Common Data Service -tietokannan luominen](create-database.md) -osiossa.
* Tietojen menetyksen estämiskäytäntöjen määrittäminen Lisätietoa saat kohdasta [Tietojen menetyksen estämiskäytännöt](prevent-data-loss.md).
* Tietokannan suojauskäytäntöjen määrittäminen (avataan tai rajoitetaan tietokantarooleilla) Lisätietoa saat kohdasta [Määritä tietokannan suojaus](database-security.md).
* Azure AD -vuokraajat, joilla on yleinen järjestelmänvalvoja -rooli (myös yleinen Office 365 -järjestelmänvalvojan rooli), voivat myös hallita kaikkia ympäristöjä, jotka on luotu heidän vuokraajakäytännöissään ja määritetyissä vuokraajan laajuisissa käytännöissä PowerApps-hallintakeskuksesta käsin.

<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://aka.ms/cdspreviewtoga

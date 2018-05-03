---
title: Common Data Service for Apps | Microsoft Docs
description: Johdanto sovelluksille tarkoitettuun Common Data Service for Apps -palveluun, entiteetteihin ja palvelinpuolen logiikkaan.
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: 939be0cc43e03836d97049addcff27a8e4b063a0
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/28/2018
---
# <a name="common-data-service-for-apps"></a>Microsoft Common Data Service for Apps

Common Data Servicen avulla voit turvallisesti tallentaa ja hallita tietoja, joita käytetään itse kehittämissäsi tai Microsoftin ja sovelluksen tarjoajien sovelluksissa. Common Data Servicessä tiedot tallennetaan vakioentiteetteihin ja mukautettuihin entiteetteihin. Entiteetti on kenttäjoukko, jota käytetään tietojen tallentamiseen samaan tapaan kuin tietokannan taulukoita. Kun tietosi on tallennettu, voit kehittää niiden avulla monipuolisia sovelluksia Microsoft PowerAppsissa:

* Hyödynnä olemassa olevia vakioentiteettejä tai luo skenaariota tai sovellusta tukevia mukautettuja entiteettejä.
* Luo suoraan Common Data Serviceen tukeutuvia PowerApps-sovelluksia ja Flow-työnkulkuja.
* Lisää mukautettuja kenttiä ja suhteita lisätietoja tarvitseviin vakioentiteetteihin.
* Luo entiteetteihin laskettuja kenttiä ja koontikenttiä, jotka yhdenmukaistavat kaikkien sovellusten ja analyysien laskutoimitukset.
* Määritä liiketoimintasääntöjä, joilla takaat entiteettien sisältämien tietojen korkealaatuisuuden tietoja käyttävästä tai muokkaavasta sovelluksesta riippumatta.
* Luo työnkulkuja ja hyödynnä Microsoft Flow -integraatio, jotta voit suorittaa lisää tietoihin perustuvia toimintoja ja liiketoimintaprosesseja.
* Sisällytä kehittämääsi sovellukseen vakioentiteettejä ja mukautettuja entiteettejä. Se on yhtä helppoa kuin tietojen lisääminen muissa lähteissä.
* Yhdistä Microsoft Excel -tiedostoissa oleviin tietoihisi Common Data Servicen tuottavuusapuohjelmien avulla.
* Tuo ja synkronoi tietosi helposti Power Query -apuohjelmalla.
* Suojaa organisaation sisäiset tiedot vakioentiteettien ja mukautettujen entiteettien käyttöoikeuksia rajoittavalla roolipohjaisella suojauksella.
* Tue tietojasi ja sovelluksiasi maailmanlaajuisesti kääntämällä entiteettien ja kenttien nimet käyttäjän kielelle.

Jokaisessa entiteetissä on joukko tietueita, joita käyttäjät voivat käyttöoikeuksistaan riippuen luoda, lukea, päivittää ja poistaa. Voit luoda entiteettien välille suhteita ja mahdollistaa siten tiedon etsimisen yhdestä entiteetistä toisen entiteetin tietueen perusteella. Voit esimerkiksi luoda mukautetun entiteetin, joka seuraa tapahtumia, joihin asiakas on osallistunut. Lisäämällä asiakkaan mukautettuun entiteettiin hakukenttänä muodostat kahden entiteetin välille suhteen, jota voidaan hyödyntää sovelluksessasi ja raportoinnissa.

Lisätietoja Common Data Servicen käyttöön tarvittavan palvelupaketin ostamisesta on kohdassa [Hinnoittelutiedot](../../administrator/pricing-billing-skus.md).

## <a name="why-use-the-common-data-service-for-apps"></a>Miksi Common Data Service for Apps -palvelua kannattaa käyttää?
Common Data Servicen vakioentiteetit ja mukautetut entiteetit tarjoavat turvallisen pilvipohjaisen tallennusvaihtoehdon tiedoillesi. Entiteettien avulla voit luoda tietojen yrityskeskeisen määrityksen, jota voidaan käyttää sovelluksissa. Jos et ole varma, ovatko entiteetit paras vaihtoehto, huomioi seuraavat edut:

* **Helppo hallita** – Metatiedot ja tiedot on tallennettu pilvipalveluun. Sinun ei tarvitse huolehtia tallentamisen yksityiskohdista.
* **Helppo jakaa** – Voit jakaa tietoja helposti työtovereidesi kanssa, koska PowerApps hallitsee käyttöoikeuksia.
* **Helppo suojata** – Tiedot tallennetaan turvallisesti, ja käyttäjät näkevät ne vain, jos annat heille käyttöoikeuden. Roolipohjaisen suojauksen avulla voit hallita, kuka organisaatiossa voi käyttää entiteettejä.
* **Monipuoliset metatiedot** – Tietotyyppejä ja suhteita hyödynnetään suoraan PowerAppsissa. Esimerkiksi kenttätyypin määrittäminen URL-osoitteeksi esittää tietosi hyperlinkkinä sovelluksessa.
* **Logiikka ja vahvistus** – Varmista tietojen laatu ja liiketoimintaprosessien sujuvuus määrittämällä laskettuja kenttiä, liiketoimintasääntöjä, työnkulkuja ja liiketoimintaprosessien työnkulkuja.
* **Tuottavuustyökalut** – Entiteetit ovat käytettävissä Microsoft Excelin apuohjelmissa. Ne lisäävät tuottavuutta ja varmistavat, että tiedot ovat käytettävissä.

Kun kehität sovellusta, voit käyttää vakioentiteettejä, mukautettuja entiteettejä tai molempia. Jos tiettyyn tarkoitukseen on olemassa sopiva vakioentiteetti, käytä sitä sovelluksessasi. Älä kehitä samalla tavalla toimivaa mukautettua entiteettiä. Jos tehtävään riittäisi muutamalla muutoksella varusteltu vakioentiteetti, voit lisätä siihen tarvitsemasi kentät.

* Common Data Service tarjoaa vakioentiteetit oletusarvona. Vakioentiteetit on suunniteltu parhaiden käytäntöjen mukaisesti sieppaamaan yleisimmät organisaatiossa käytetyt käsitteet, kuten yhteystiedot, tilit ja tuotteet. Täydellinen luettelo entiteeteistä on kohdassa [Vakioentiteetit](data-platform-intro.md#standard-entities).
* Voit laajentaa vakioentiteettien toimintoja luomalla yhden tai useamman mukautetun entiteetin, joihin tallennat organisaation yksilöllisiä tietoja. Lisätietoja on kohdassa [Mukautetun entiteetin luominen](create-custom-entity.md).

> [!NOTE]
> Jos mahdollista, käytä vakioentiteettejä (lisää tarvittaessa mukautettuja kenttiä). Siten varmistat, että myöhemmin hyödyt näihin entiteetteihin liittyvistä uusista ominaisuuksista ja sovelluksista.

## <a name="interacting-with-entities"></a>Entiteettien käyttäminen

Kaikissa käyttämissäsi vakioentiteeteissä ja mukautetuissa entiteeteissä on käytettävissä lukuisia elementtejä ja erilaisia toimintoja. Valitse sopivat ominaisuudet liiketoiminnan skenaarion monimutkaisuudesta riippuen. Jos haluat nähdä ympäristössäsi käytettävissä olevat entiteetit, kirjaudu sisään [PowerAppsiin](https://web.powerapps.com) ja valitse vasemmasta valikosta ensin Tiedot ja sitten Entiteetit.

![Entiteetin tiedot](./media/data-platform-cds-intro/entitylist.png "Entiteetin tiedot")

* Jokaiseen **kenttään** voi määrittää kerättävän tiedon sekä tietotyypin tai muodon, jossa tiedot haluaa näyttää. Kentät muistuttavat tietokantojen tai Excelin sarakkeita.
* Vaihtoehtoiset **avaimet** mahdollistavat entiteetin tietueiden tehokkaan ja tarkan haun ja käytön, kun käytössä ei ole tavallista yksilöivää tunnistetta. Tämä on tärkeää, kun käytetään Business Key -avainta tai integroidutaan ulkoisen järjestelmän kanssa.
* Jokaisella entiteetillä voi olla useita **suhteita** muihin entiteetteihin. Ne tukevat entiteetteihin kohdistuvia haku- ja kyselytoimintoja. Luotavia suhteita on erilaisia: monen suhde yhteen, yhden suhde moneen ja monen suhde moneen.
* **Näkymien** ansiosta jokainen entiteetti voidaan näyttää monella eri tapaa. Voit esimerkiksi valita esillä olevat kentät sekä tietojen suodatus- ja lajittelutavan. Nämä esitykset tallennetaan näkyminä ja ovat eri sovellusten käytössä. Ehkä esimerkiksi haluat, että sovelluksesi näyttää vain aktiiviset tilit. Valitse siinä tapauksessa näkymä, jonka suodattimet on ennalta määritetty näyttämään vain aktiiviset tilit. Siten et joudu määrittämään suodatinta erikseen jokaisessa entiteettiä käyttävässä sovelluksessa.
* **Liiketoimintasääntöjen** avulla voit vahvistaa entiteeteissä luodut ja päivitetyt tiedot. Siten varmistat tietojen hyvän laadun. Kukin liiketoimintasääntö voi vahvistaa tietoja monessa kentässä ja entiteetissä sekä käynnistää varoitus- ja virheilmoituksia riippumatta siitä, millä sovelluksella tiedot luotiin.
* Common Data Serviceen tallennetut **tiedot** ovat käytettävissä PowerApps-portaalin, PowerAppsin, Microsoft Excelin ja kehittäjille tarkoitetun verkon ohjelmointirajapinnan kautta.

### <a name="system-fields"></a>Järjestelmäkentät
Kaikki entiteetit, sekä vakiokentät että mukautetut kentät, luodaan joukolla vain luku -kenttiä. Näitä kenttiä ei voi muuttaa tai poistaa eikä niille voi asettaa arvoa. Tärkeimmät järjestelmäkentät:

## <a name="logic-and-validation"></a>Logiikka ja vahvistus

Common Data Servicessä olevat entiteetit voivat hyödyntää monipuolista palvelinpuolen logiikkaa ja vahvistusta. Niillä varmistetaan tiedon laatu ja vähennetään koodin toistamista yksittäisissä sovelluksissa, jotka luovat ja käyttävät tietoja entiteetissä.

* **Liiketoimintasäännöt** voivat vahvistaa tietoja monessa kentässä ja entiteetissä sekä käynnistää varoitus- ja virheilmoituksia riippumatta siitä, millä sovelluksella tiedot luotiin. Lisätietoja on kohdassa [Liiketoimintasäännön luominen](./data-platform-create-business-rule.md).
* **Liiketoimintaprosessien työnkulut** ohjaavat käyttäjiä ja varmistavat siten, että tietojen syöttö on johdonmukaista ja noudattaa aina samoja vaiheita. Liiketoimintaprosessien työnkulkuja tukevat tällä hetkellä vain mallipohjaiset sovellukset. Lisätietoja on kohdassa [Liiketoimintaprosessien työnkulkujen yleiskatsaus](/dynamics365/customer-engagement/customize/business-process-flows-overview).
* **Työnkulkujen** avulla voit automatisoida liiketoimintaprosesseja ilman vuorovaikutusta käyttäjän kanssa. Lisätietoja on kohdassa [Työnkulkujen yleiskatsaus](/dynamics365/customer-engagement/customize/workflow-processes).
* **Liiketoimintalogiikan koodi** tukee kehittyneempiä kehittelyskenaarioita, joissa sovelluksen toimintaa laajennetaan suoraan koodilla. Lisätietoja on kohdassa [Sovella liiketoimintalogiikkaa koodin avulla](../../developer/common-data-service/apply-business-logic-with-code.md).

## <a name="getting-data-into-the-common-data-service"></a>Tietojen nouto Common Data Serviceen

Tietoja voi alkaa noutaa Common Data Serviceen monella tapaa:

* Luo PowerApp-sovellus tai Flow-työnkulku tietojen luomista varten.
* Yhdistä verkossa tai lähiverkossa olevaan tietolähteeseen Power Query -apuohjelmalla ja tuo tiedot suoraan Common Data Serviceen. Power Queryn avulla voit myös luoda tietolähteen rakenteeseen pohjautuvia entiteettejä ja muuntaa tietoja tuonnin yhteydessä. Lisätietoja on kohdassa [Tietojen lisääminen Common Data Servicessä olevaan entiteettiin Power Queryn avulla](./data-platform-cds-newentity-pq.md).

## <a name="developer-capabilities"></a>Kehittäjän mahdollisuudet

[PowerApps](https://web.powerapps.com)-portaalin kautta käytettävissä olevien ominaisuuksien lisäksi Common Data Service tarjoaa kehittäjille myös muita toimintoja. Kehittäjät voivat esimerkiksi käyttää metatietoja ja tietoja ohjelmallisesti entiteettien ja liiketoimintalogiikan luomiseen ja tietojen kanssa vuorovaikuttamiseen. Lisätietoja on kohdassa [Common Data Service for Apps Developer -palvelun yleiskatsaus](../../developer/common-data-service/overview.md)

## <a name="get-started"></a>Aloita
Kokeile luomalla sovellus vakioentiteetin avulla. Tai [luo ensin mukautettu entiteetti](create-custom-entity.md) ja sen jälkeen sitä käyttävä [sovellus](../canvas-apps/data-platform-create-app.md).

## <a name="privacy-notice"></a>Tietosuojailmoitus
Microsoft PowerApps Common Data Model kerää ja tallentaa mukautettuja entiteettejä ja kenttien nimiä diagnostiikkajärjestelmäämme.  Näiden tietojen avulla parannamme asiakkaille tarjottavaa yleistä tietomallia. Tekijöiden luomat entiteettien ja kenttien nimet auttavat meitä ymmärtämään Microsoft PowerApps -yhteisössä yleisiä skenaarioita ja havaitsemaan palvelun vakioentiteettitarjonnan puutteita, kuten organisaatioihin liittyviä rakenteita. Microsoft ei avaa eikä käytä näihin entiteetteihin liittyvien tietokantataulukoiden tietoja eikä niitä replikoida tietokannan luomisalueen ulkopuolelle. Huomaa kuitenkin, että mukautetut entiteettien nimet ja kentät saatetaan replikoida monelle alueelle ja poistetaan tietojen säilytyskäytäntöjemme mukaisesti. Microsoft on sitoutunut takaamaan käyttäjien tietosuojan [luottamuskeskuksessa](https://www.microsoft.com/trustcenter/Privacy/default.aspx) kuvaillulla tavalla.


---
title: Mikä on Microsoft Common Data Service for Apps? | Microsoft Docs
description: Johdanto sovelluksille tarkoitettuun Common Data Service (CDS) for Apps -palveluun, entiteetteihin ja palvelinpuolen logiikkaan.
author: SKjerland
manager: kfile
ms.service: powerapps
ms.topic: overview
ms.component: cds
ms.date: 05/01/2018
ms.author: sharik
ms.openlocfilehash: a2dea7da0cc87ad016d5eff6e04b9e03e66341db
ms.sourcegitcommit: b3b6118790d6b7b4285dbcb5736e55f6e450125c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/15/2018
---
# <a name="what-is-common-data-service-for-apps"></a>Mikä on Microsoft Common Data Service for Apps?
Common Data Service (CDS) for Apps -palvelussa voit säilyttää ja hallita liiketoimintasovellustesi käyttämiä tietoja turvallisesti. CDS for Appsin tiedot tallennetaan joukkoon entiteettejä. *Entiteetti* on tietuejoukko, jota käytetään tietojen tallentamiseen samoin kuin taulukossa säilytetään tietoja tietokannassa. CDS for Apps sisältää peruskokoelman vakioentiteettejä, jotka kattavat tyypilliset tilanteet, mutta voit lisäksi luoda mukautettuja entiteettejä oman organisaatiosi tarpeisiin ja täyttää ne tiedoilla Power Querya käyttämällä. Sovellusten tekijät voivat sen jälkeen rakentaa PowerAppsissa runsaita sovelluksia tietojen avulla.

Lisätietoja CDC for Appsin käyttöön tarvittavan palvelupaketin ostamisesta on kohdassa [Hinnoittelutiedot](../../administrator/pricing-billing-skus.md).

## <a name="why-use-common-data-service-for-apps"></a>Miksi Common Data Service for Apps -palvelua kannattaa käyttää?
CDC for Appsin vakioentiteetit ja mukautetut entiteetit tarjoavat turvallisen pilvipohjaisen tallennusvaihtoehdon tiedoillesi. Entiteettien avulla voit luoda organisaation tietojen yrityskeskeisen määrityksen, jota voidaan käyttää sovelluksissa. Jos et ole varma, ovatko entiteetit paras vaihtoehto, huomioi seuraavat edut:

* **Helppo hallita** &ndash;Metatiedot ja tiedot on tallennettu pilvipalveluun. Sinun ei tarvitse huolehtia tallentamisen yksityiskohdista.
* **Helppo jakaa** &ndash;Voit jakaa tietoja helposti työtovereidesi kanssa &mdash; PowerApps hallitsee käyttöoikeuksia.
* **Helppo suojata** &ndash;Tiedot tallennetaan turvallisesti, ja käyttäjät näkevät ne vain, jos annat heille käyttöoikeuden. Roolipohjaisen suojauksen avulla voit hallita, kuka organisaatiossa voi käyttää entiteettejä.
* **Monipuoliset metatiedot** &ndash;Tietotyyppejä ja suhteita hyödynnetään suoraan PowerAppsissa. Esimerkiksi kenttätyypin määrittäminen URL-osoitteeksi esittää tietosi hyperlinkkinä sovelluksessa.
* **Logiikka ja vahvistus** &ndash; Varmista tietojen laatu ja liiketoimintaprosessien sujuvuus määrittämällä laskettuja kenttiä, liiketoimintasääntöjä, työnkulkuja ja liiketoimintaprosessien työnkulkuja.
* **Tuottavuustyökalut** &ndash; Entiteetit ovat käytettävissä Microsoft Excelin apuohjelmissa. Ne lisäävät tuottavuutta ja varmistavat, että tiedot ovat käytettävissä.

## <a name="interacting-with-entities"></a>Entiteettien käyttäminen
Kun kehität sovellusta, voit käyttää vakioentiteettejä, mukautettuja entiteettejä tai molempia. CDC for Apps tarjoaa vakioentiteetit oletusarvona. Vakioentiteetit on suunniteltu parhaiden käytäntöjen mukaisesti tallentamaan yleisimmät organisaatiossa käytetyt käsitteet ja skenaariot.

![Näyttökuva, jossa esitetään luettelo entiteeteistä.](./media/data-platform-cds-intro/entitylist.png "Entiteettiluettelo")

Täydellinen luettelo entiteeteistä on kohdassa [Lisätiedot kohteista](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/reference/about-entity-reference).

Voit laajentaa vakioentiteettien toimintoja luomalla yhden tai useamman mukautetun entiteetin, joihin tallennat organisaation yksilöllisiä tietoja. Lisätietoja on kohdassa [Mukautetun entiteetin luominen](create-custom-entity.md).

## <a name="logic-and-validation"></a>Logiikka ja vahvistus
CDS for Appsissa olevat entiteetit voivat hyödyntää monipuolista palvelinpuolen logiikkaa ja vahvistusta. Niillä varmistetaan tiedon laatu ja vähennetään koodin toistamista yksittäisissä sovelluksissa, jotka luovat ja käyttävät tietoja entiteetissä.

* **Liiketoimintasäännöt** vahvistavat tietoja monessa kentässä ja entiteetissä sekä käynnistävät varoitus- ja virheilmoituksia riippumatta siitä, millä sovelluksella tiedot on luotu. Lisätietoja on kohdassa [Liiketoimintasäännön luominen](./data-platform-create-business-rule.md).
* **Liiketoimintaprosessien työnkulut** ohjaavat käyttäjiä ja varmistavat siten, että tietojen syöttö on johdonmukaista ja samat vaiheet tehdään aina. Liiketoimintaprosessien työnkulkuja tukevat tällä hetkellä vain mallipohjaiset sovellukset. Lisätietoja on kohdassa [Liiketoimintaprosessien työnkulkujen yleiskatsaus](/dynamics365/customer-engagement/customize/business-process-flows-overview).
* **Työnkulkujen** avulla voit automatisoida liiketoimintaprosesseja ilman käyttäjän vuorovaikutusta. Lisätietoja on kohdassa [Työnkulkujen yleiskatsaus](/dynamics365/customer-engagement/customize/workflow-processes).
* **Liiketoimintalogiikan koodi** tukee kehittyneitä kehittelyskenaarioita, joissa sovelluksen toimintaa laajennetaan suoraan koodilla. Lisätietoja on kohdassa [Sovella liiketoimintalogiikkaa koodin avulla](../../developer/common-data-service/apply-business-logic-with-code.md).

## <a name="developer-capabilities"></a>Kehittäjän mahdollisuudet
[PowerApps](https://web.powerapps.com)-portaalin kautta käytettävissä olevien ominaisuuksien lisäksi CDC for Apps tarjoaa kehittäjille myös muita toimintoja. Kehittäjät voivat esimerkiksi käyttää metatietoja ja tietoja ohjelmallisesti entiteettien ja liiketoimintalogiikan luomiseen ja tietojen kanssa vuorovaikuttamiseen. Lisätietoja on kohdassa [Common Data Service for Apps Developer -palvelun yleiskatsaus](../../developer/common-data-service/overview.md)

## <a name="next-steps"></a>Seuraavat vaiheet
CDS for Appsin käytön aloittaminen:
* [Luo sovellus Common Data Service -tietokannan avulla](../canvas-apps/data-platform-create-app-scratch.md).
* [Luo mukautettu kohde](create-custom-entity.md) ja sen jälkeen [luo sovellus, joka käyttää kyseistä kohdetta](../canvas-apps/data-platform-create-app.md).
* [Yhdistä verkossa tai lähiverkossa olevaan tietolähteeseen Power Query -apuohjelmalla](./data-platform-cds-newentity-pq.md) ja tuo tiedot suoraan CDS for Appsiin.

## <a name="privacy-notice"></a>Tietosuojailmoitus
Microsoft PowerAppsin yleisen tietomallin avulla Microsoft kerää ja tallentaa mukautettuja entiteettien ja kenttien nimiä diagnostiikkajärjestelmiimme. Näiden tietojen avulla parannamme asiakkaille tarjottavaa yleistä tietomallia. Sovellustekijöiden antamat entiteettien ja kenttien nimet auttavat meitä ymmärtämään Microsoft PowerApps -yhteisössä yleisiä skenaarioita ja havaitsemaan palvelun vakioentiteettitarjonnan puutteita, kuten organisaatioihin liittyviä rakenteita. Microsoft ei avaa eikä käytä näihin entiteetteihin liittyvien tietokantataulukoiden tietoja, eikä niitä replikoida tietokannan luomisalueen ulkopuolelle. Huomaa kuitenkin, että mukautetut entiteettien nimet ja kentät voidaan replikoida monelle alueelle ja poistetaan tietojen säilytyskäytäntöjemme mukaisesti. Microsoft on sitoutunut takaamaan käyttäjien tietosuojan [luottamuskeskuksessa](https://www.microsoft.com/trustcenter/Privacy/default.aspx) kuvaillulla tavalla.

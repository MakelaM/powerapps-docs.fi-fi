---
title: Mikä on Common Data Service? | Microsoft Docs
description: 'Johdanto Common Data Serviceen, entiteetteihin ja palvelinpään logiikkaan.'
author: clwesene
manager: kfile
ms.service: powerapps
ms.topic: overview
ms.component: cds
ms.date: 05/01/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="what-is-common-data-service"></a>Mikä on Common Data Service?
Common Data Servicen avulla voit turvallisesti tallentaa ja hallinnoida liiketoimintasovelluksissa käytettäviä tietoja. Common Data Servicen tiedot tallennetaan entiteettijoukkoon. *Entiteetti* on tietuejoukko, johon tallennetaan tietoja samaan tapaan kuin taulukkoon tallennetaan tietokannan tietoja. Common Data Service sisältää vakioentiteettien perusjoukon, joka kattaa tavalliset skenaariot. Voit myös luoda organisaatiokohtaisia mukautettuja entiteettejä ja täyttää ne tiedoilla Power Queryn avulla. Sovelluksen tekijät voivat luoda näitä tietoja käyttämällä monipuolisia sovelluksia PowerAppsin avulla.

![Yrityssovellusympäristön yleiskatsauksen sisältävä näyttökuva.](./media/data-platform-cds-intro/platform.png "Ympäristön yleiskatsaus")

Lisätietoja palvelupaketin ostamisesta Common Data Servicen käyttämistä varten on kohdassa [Hinnoittelutiedot](../../administrator/pricing-billing-skus.md).

## <a name="why-use-common-data-service"></a>Miksi Common Data Serviceä kannattaa käyttää?
Common Data Servicen vakioentiteetit ja mukautetut entiteetit tarjoavat tietojen turvallisen pilvipohjaisen tallennusvaihtoehdon. Entiteettien avulla voit luoda organisaation tietojen liiketoimintakohtaisen määrityksen sovelluskäyttöä varten. Jos et ole varma siitä, ovatko entiteetit paras vaihtoehto yrityksellesi, tutustu seuraaviin hyötyihin:

* **Hallinnointi on helppoa** &ndash; Sekä metatiedot että tiedot tallennetaan pilveen. Tallentamiseen liittyviä huolia ei enää ole.
* **Suojaaminen on helppoa** &ndash; Tiedot suojataan niin, että käyttäjät näkevät vain tietoja, joiden käyttöoikeudet heillä on. Rooliperusteinen suojaus mahdollistaa organisaation käyttäjien entiteettien käyttöoikeuksien hallinnan.
* **Dynamics 365 -tietojen käyttöoikeus** &ndash; Dynamics 365 -sovellusten tiedot tallennetaan myös Common Data Serviceen. Voit siis luoda nopeasti Dynamics 365 -tietoja hyödyntäviä sovelluksia ja laajentaa sovelluksia PowerAppsin avulla.
* **Monipuoliset metatiedot** &ndash; Tietotyyppejä ja suhteita hyödynnetään suoraan PowerAppsissa.
* **Logiikka ja tarkistaminen** &ndash; Voit määrittää laskettuja kenttiä, liiketoimintasääntöjä, työnkulkuja ja liiketoimintaprosesseja tietojen laadun varmistamiseksi ja liiketoimintaprosessien tehostamiseksi.
* **Tuottavuustyökalut** &ndash; Entiteetit ovat Microsoft Excelin apuohjelmissa. Niiden avulla voi parantaa tuottavuutta ja varmistaa tietojen käytettävyys.

## <a name="dynamics-365-and-the-common-data-service"></a>Dynamics 365 ja Common Data Service

Dynamics 365 -sovellukset, kuten Dynamics 365 for Sales, Service tai Talent, tallentavat ja suojaavat myös sovellusten käyttämiä tietoja Common Data Servicen avulla. Voit luoda sovelluksia suoraan Dynamics 365:ssä käytössä oleville pääliiketoimintatiedoille PowerAppsin ja Common Data Servicen avulla ilman integrointia.

* **Sovellusten luominen Dynamics 365 -tietojen avulla** &ndash; Voit luoda sovelluksia nopeasti liiketoimintatietojen avulla PowerAppsissa tai Pro Developer SDK:n avulla.
* **Uudelleen käytettävän liiketoimintalogiikan ja säännön hallinta** &ndash; Liiketoimintasäännöt ja -logiikka, joka on jo määritetty Dynamics 365 -entiteeteissä, kohdistetaan PowerAppsiin. Näin varmistetaan tietojen yhdenmukaisuus siitä huolimatta, miten tai minkä sovelluksen kautta käyttäjät käyttävät tietoja.
* **Uudelleen käytettävät taidot Dynamics 365:ssä ja PowerAppsissa** &ndash; Käyttäjät, joilla oli määritettyjä osaamisalueita aiemmin PowerAppsissa tai Dynamics 365:ssä, voivat nyt hyödyntää näitä osaamisalueita uudessa Common Data Service -ympäristössä. Esimerkiksi entiteettien lomakkeiden ja kaavioiden luominen on nyt yhteistä kaikkialla sovelluksessa.

    > [!NOTE]
    > Dynamics 365 for Finance and Operations vaatii tällä hetkellä tietojen integroijan määrityksen. Se mahdollistaa Finance and Operations -liiketoimintatietojen käyttämisen Common Data Servicessä.

## <a name="integrating-data-into-the-common-data-service"></a>Tietojen integroiminen Common Data Service -palveluun

Sovelluksen luominen käsittää yleensä usean lähteen tietoja. Joskus tämä tehdään sovellustasolla. Joissakin tapauksissa tietojen integroiminen yleiseen tallennuspaikkaan helpottaa sovellusten luomista. Tällöin on myös yksi logiikkajoukko, jonka avulla tietoja ylläpidetään ja käytetään. Common Data Service mahdollistaa tietojen integroinnin useista lähteistä yhteen tallennuspaikkaan, jota voi käyttää PowerApps-, Flow- ja Power BI -sovelluksessa yhdessä Dynamics 365 -sovellusten tietojen kanssa.

* **Ajoitettu integrointi muiden järjestelmien kanssa** &ndash; Muissa sovelluksissa säilytettävät tiedot voidaan synkronoida säännöllisesti Common Data Servicen kanssa. Näin voit hyödyntää muiden sovellusten tietoja PowerAppsissa.
* **Tietojen muuntaminen ja tuominen PowerQueryn avulla** &ndash; Tietojen muuntaminen samalla, kun niitä tuodaan Common Data Service -sovellukseen, voidaan tehdä PowerQueryn avulla useista online-tietolähteistä. Se on yleinen työkalu, jota käytetään Excelissä ja Power BI:ssä.
* **Tietojen kertatuonti** &ndash; Excel- ja CSV-tiedostojen yksinkertainen tuontia ja vientiä voidaan käyttää kerran tai silloin tällöin tapahtuvassa tuonnissa Common Data Serviceen.

Lisätietoja tietojen integroinnista Common Data Serviceen on kohdassa [Tietojen lisääminen entiteettiin Common Data Servicessä Power Queryn avulla](data-platform-cds-newentity-pq.md).

## <a name="interacting-with-entities"></a>Entiteettien käyttäminen
Voit käyttää sovelluksen kehittämisessä vakioentiteettejä, mukautettuja entiteettejä tai molempia. Common Data Service sisältää oletusarvoisesti vakioentiteetit. Ne on suunniteltu parhaiden käytäntöjen mukaisesti niin, että ne sieppaavat suurimman osan organisaation yleisistä käsitteistä ja skenaarioista.

![Entiteettiluettelon sisältävä näyttökuva.](./media/data-platform-cds-intro/entitylist.png "Entiteettiluettelo")

Entiteettien täydellinen luettelo on kohdassa [Entiteettiviittaus](https://docs.microsoft.com/powerapps/developer/common-data-service/reference/about-entity-reference).

Voit laajentaa vakioentiteettien toimintoja luomalla vähintään yhden mukautetun entiteetin, johon tallennetaan organisaatiokohtaisia tietoja. Lisätietoja: [Mukautetun entiteetin luominen](create-custom-entity.md).

## <a name="logic-and-validation"></a>Logiikka ja tarkistaminen
Common Data Servicen entiteetit voivat hyödyntää monipuolista palvelinpään logiikkaa ja tarkistamista. Näin varmistetaan tietojen laatu ja vähennetään koodin toistoa kussakin sovelluksessa, joka luo ja käyttää entiteetin tietoja.

* **Liiketoimintasäännöt** tarkistavat useiden kenttien ja entiteettien tiedot ja tuo näyttöön varoitus- ja virhesanomat siitä huolimatta, luoko käytetty sovellus tietoja. Lisätietoja on kohdassa [Liiketoimintasäännön luominen](./data-platform-create-business-rule.md).
* **Liiketoimintaprosessit** ohjaavat käyttäjiä varmistamaan tietojen yhdenmukaisen syöttämisen ja samojen vaiheiden seuraamisen joka kerta. Liiketoimintaprosesseja tuetaan tällä hetkellä vain mallipohjaisissa sovelluksissa. Lisätietoja on kohdassa [Liiketoimintaprosessien yleiskatsaus](/dynamics365/customer-engagement/customize/business-process-flows-overview).
* **Työnkulkujen** avulla on mahdollista automatisoida liiketoimintaprosessit ilman käyttäjien toimia. Lisätietoja on kohdassa [Työnkulkujen yleiskatsaus](/dynamics365/customer-engagement/customize/workflow-processes).
* **Liiketoimintalogiikka ja koodi** tukee sovelluskehittäjän edistyneitä skenaarioita, joiden avulla sovellus voidaan laajentaa suoraan koodin avulla. Lisätietoja on kohdassa [Liiketoimintalogiikan käyttäminen koodin kanssa](../../developer/common-data-service/apply-business-logic-with-code.md).

## <a name="developer-capabilities"></a>Sovelluskehittäjän ominaisuudet
[PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-portaalissa käytettävien toimintojen lisäksi, Common Data Service sisältää myös sovelluskehittäjille tarkoitettuja toimintoja, joiden avulla voi käyttää metatietoja ja tietoja ohjelmoidusti entiteettien ja liiketoimintatietojen luomiseksi sekä tietojen käyttämiseksi. Lisätietoja on kohdassa [Common Data Servicen sovelluskehittäjän yleiskatsaus](../../developer/common-data-service/overview.md)

## <a name="next-steps"></a>Seuraavat vaiheet
Common Data Servicen käytön aloittaminen:
* [Sovelluksen luominen Common Data Service -tietokannan avulla](../canvas-apps/data-platform-create-app-scratch.md).
* [Luo mukautettu entiteetti](create-custom-entity.md) ja sitten [kyseistä entiteettiä käyttävä sovellus](../canvas-apps/data-platform-create-app.md).
* [Käytä Power Query -sovellusta](./data-platform-cds-newentity-pq.md), kun haluat muodostaa yhteyden online- tai paikalliseen tietolähteeseen ja tuoda tiedot suoraan Common Data Serviceen.

## <a name="privacy-notice"></a>Tietosuojatiedot
Microsoft PowerAppsin Common Data Model -ratkaisun avulla Microsoft kerää ja tallentaa mukautettuja entiteettejä ja kenttänimiä diagnostiikkajärjestelmiin. Näiden tietojen avulla parannamme asiakkaiden käytössä olevaa Common Data Model -ratkaisua. Entiteettien ja kenttien nimet, joita sovellusten tekijät luovat, auttavat meitä ymmärtämään Microsoft PowerApps -yhteisön yleisiä skenaarioita ja saamaan selville palvelun entiteetin vakiokattavuuden puutteita, kuten organisaation liittyvissä malleissa. Microsoft ei käytä näihin entiteetteihin liittyvien tietokantataulukoiden tietoja eikä replikoi niitä sen alueen ulkopuolelle, jossa tietokanta on valmisteltu. Huomaa kuitenkin, että mukautetun entiteetin ja kenttien nimet voidaan replikoida alueilla. Ne poistetaan tietojen säilytyskäytäntöjen mukaisesti. Microsoft pyrkii takaamaan tietoturvasi [valvontakeskuksessa](https://www.microsoft.com/trustcenter/Privacy/default.aspx) esitetyllä tavalla.

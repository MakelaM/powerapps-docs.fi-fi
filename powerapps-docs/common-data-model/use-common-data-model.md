---
title: Kehittäminen Common Data Modelin avulla | Microsoft Docs
description: Tietoja Common Data Modelin käytöstä sovellusten ja ratkaisujen kehittämiseen.
author: RobertBruckner
ms.service: powerapps
ms.topic: article
ms.date: 07/24/2018
ms.author: robruc
ms.openlocfilehash: 6e99fbe13d9b6e3acdd0cfdd08662676a321471c
ms.sourcegitcommit: abe4d4728db7f56088f618af5b820af78e7099c9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332072"
---
# <a name="how-to-use-the-common-data-model"></a>Common Data Modelin käyttö

**Common Data Modelin (CDM)** avulla voit laittaa tiedot muotoihin, jota vastaavat yleisesti käytettyjä ja ymmärrettyjä käsitteitä ja toimintoja. Voit tehdä tiedoista kyselyjä, käyttää niitä uudelleen ja käyttää niitä yhdessä samaa muotoa käyttävien muiden yritysten ja sovellusten kanssa. Vastaavasti kuin tieto AA-pariston koosta ja muodosta, jotta niitä voidaan käyttää kaikissa kaukosäätimissä, CDM määrittää *Yhteystiedon* (esimerkiksi) koon ja muodon, jotta sovelluskehittäjät ja liiketoimintakumppanit tietävät, miten tietoja käytetään. Tiedon ansiosta sovellustesi päälle voidaan kehittää lisätoimintoja (tai yhteistoimintoja) kätevästi ja luotettavasti. Koska CDM on standardientiteettien avoimen lähdekoodin määritelmä, kiinnostuneiden kehittäjien yhteisö ymmärtää rakennemääritykset ja voi osallistua niiden käyttämiseen.

Nykyisin CDM:ää käytetään Common Data Service (CDS) for Appsissa, joka tukee Dynamicsia ja PowerAppsia sekä Power BI:n tietojen valmisteluominaisuuksia. Näin voidaan luoda rakenteellisia tiedostoja Azure Data Lakessa.

![Common Data Model ja CDS for Apps](media/cdm-with-cds.png)

Voit käyttää CDM:ää ja CDS for Appsia seuraavilla tavoilla:

-   **Tietojen turvallinen tallennus ja hallinta CDM-muodossa**: Voit käyttää CDS for Appsia tietojen turvalliseen tallennukseen ja hallintaan standardoidussa CDM-muodossa. Näin voit käyttää kyseisiä tietoja Microsoftin sovelluksissa ja palveluissa, kuten Dynamicsissa, PowerAppsissa, Flow’ssa, Power BI:ssä tai omissa mukautetuissa sovelluksissasi.

-   **Mukautettujen CDM-entiteettien luominen**: CDM on laajentuva, joten voit luoda entiteettejä, joita ei ole vielä CDM:ssä. Saat omalle organisaatiollesi mukautettuja entiteettejä, jotka voit täyttää olemassa olevilla tiedoillasi käyttämällä **Power Querya**. Näin voit hyödyntää CDM:ää ja mukauttaa sen liiketoimintaasi.

-   **Omien tietosäilöjen luominen**: Voit luoda tietosäilöjä, joissa noudatetaan **Common Data Model (CDM)** -rakennetta, ja muodostaa yhteyden kyseisiin tietolähteisiin Microsoftin tietoliittimillä. Tämän ansiosta voit luoda mukautettuja liiketoiminta-aluesovelluksia, joissa käytetään tai jaetaan CDM-tietojasi riippumatta siitä, mistä tiedot ovat peräisin tai mihin ne on tallennettu.

-   **Merkityksellisten tietojen johtaminen ja jakaminen nopeasti Power BI:n avulla**: Voit käyttää Power BI:n kehittyneitä tietojen valmistelupalveluja, jotka muodostavat yhteyden CDM-tietosäilöihisi (esimerkiksi tietoihin, jotka olet lisännyt CDS for Appsiin), ja luoda raportteja ja koontinäyttöjä. Sen jälkeen voit luoda raportteja laativia sovelluksia, jotka hakevat automaattisesti CDM-tietosi mukautettujen merkityksellisten tietojen saamiseksi organisaation henkilöitä ja ryhmiä varten.

-   **Mukautettujen ja silti koko organisaation laajuisten raporttien luominen Power BI:ssä**: Voit käyttää sovelluksia, jotka luovat automaattisesti mukautettuja raportteja, jotka voit sijoittaa Power BI:n työtiloihin organisaation käyttäjiä ja muita varten.

Microsoftin jatkaessa CDM:n laajentamista kumppaneiden ja alan asiantuntijoiden kanssa uudet toimialat, kuten terveydenhoitoala, voivat hyödyntää CDM:ää ja ympäristöjä, jotka tukevat sitä.

## <a name="data-integration-and-power-query-online"></a>Tietojen integrointi ja Power Query Online

Molemmat tällä hetkellä CDM:ää tukevat ympäristöt tarjoavat myös tietojen integroinnin Power Query Onlinella. Sen ansiosta käyttäjät voivat tuoda tietoja eri lähteistä, muuntaa ne tarvittaessa ja yhdistää ne CDM:n vakioentiteetteihin tai luoda mukautettuja entiteettejä. Power Query Online hyödyntää samaa visualisointia ja omatoimista tietojen valmistelutyökalua kuin Excelin ja Power BI Desktopin Power Querykin, joten nykyiset käyttäjät oppivat käytön nopeasti.

![Tietojen yhdistäminen entiteetteihin CDM:ssä](media/cdm-map-entities.png)

## <a name="common-data-service-for-apps"></a>Microsoft Common Data Service for Apps

CDS for Appsin avulla voit aloittaa sovellusten käytön nopeasti käyttämällä CDM:n sisäistä liiketoimintalogiikkaa, suojausta ja integrointia. Ympäristön avulla voit

-   **hyödyntää pakattuja yrityssovelluksia**: Monet Microsoft Dynamics -ratkaisut ja monet kolmannen osapuolen sovellukset on kehitetty Common Data Service for Appsin pohjalta tai sitä hyödynnetään niissä. Kun tiedot ovat CDM:ssä, voit hyödyntää näitä paketoituja sovelluksia.

-   **päästä käyttämään mukautettuja ratkaisuja**: CMD-muotoon perehtyneet ja sitä käyttävät kehittäjät ovat luoneet kokonaisen ekosysteemin laajennuksia ja valmiita sovelluksia. Lisätietoja on artikkelissa [Ratkaisuihin tutustuminen](https://docs.microsoft.com/powerapps/developer/common-data-service/introduction-solutions).

Aikomuksistasi riippumatta CDM sijoittaa tiedot yleiseen muotoon, jotta sen käyttäminen, jakaminen ja analysoiminen on helppoa.

**CDS for Apps -resurssit**

-   [Mikä CDS for Apps on?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)

-   [Tietojen lisääminen CDS for Appsissa olevaan entiteettiin Power Queryn avulla](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-cds-newentity-pq)

-   [Ratkaisuihin tutustuminen](https://docs.microsoft.com/powerapps/developer/common-data-service/introduction-solutions)

-   [Luo mallipohjainen sovellus](https://docs.microsoft.com/powerapps/maker/model-driven-apps/model-driven-app-overview)

-   [Luo pohjaan perustuva sovellus](https://docs.microsoft.com/powerapps/maker/canvas-apps/getting-started)

-   [Luo CDS for Appsia käyttävät työnkulku](https://docs.microsoft.com/flow/common-data-model-intro)


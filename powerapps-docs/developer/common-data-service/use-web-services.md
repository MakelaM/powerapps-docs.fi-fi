---
title: Common Data Service for Apps -verkkopalveluiden käyttäminen | Microsoft Docs
description: Lue, miten kehittäjät voivat käyttää Common Data Service for Apps -verkkopalveluita.
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
ms.date: 02/26/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 7e9e14a9d44a3326fb8ac32b11e46b61cc119c27
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42854434"
---
# <a name="use-common-data-service-for-apps-web-services"></a>Käytä Common Data Servicea sovellusten verkkopalveluita varten

Common Data Service for Apps tarjoaa kaksi verkkopalvelua, joilla tietoja voi käsitellä. Valitse vaatimuksiisi ja taitoihisi parhaiten sopiva vaihtoehto. Lisätietoja: [Dynamics 365 -asiakkaalle suunnattu kehittäjän opas: Dynamics 365 Customer Engagement -kehitystyylin valitseminen](/dynamics365/customer-engagement/developer/choose-development-style)

## <a name="web-api"></a>WWW-ohjelmointirajapinta
WWW-ohjelmointirajapinta on OData v4 RESTful -päätepiste. Käytä tätä mille tahansa ohjelmointikielelle, joka tukee HTTP-pyyntöjä ja OAuth 2.0 -todennusta.

Lisätietoja: [Dynamics 365 -asiakkaalle suunnattu kehittäjän opas: Dynamics 365 Customer Engagement -verkko-ohjelmointirajapinnan käyttäminen](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)

## <a name="organization-service"></a>Organisaatiopalvelu

Organisaatiopalvelu on keskeinen osa Common Data Service for Apps -käyttöympäristöä. Se on Windows Communication Foundation (WCF) -palvelu ja se paljastaa tällä hetkellä vain SOAP-päätepisteen. .NET-kehittäjät voivat käyttää SDK-kokoonpanoja tietotoimintojen suorittamiseen. Laajennuksessa organisaatiopalvelu on ainoa vaihtoehto SDK-kokoonpanojen kautta.
> [!NOTE]
> Kehittäjät voivat käyttää organisaatiopalvelun SOAP-päätepistettä käyttämättä .NET SDK -kokoonpanoja, mutta WWW-ohjelmointirajapinnan RESTful-luonteen ansiosta se on huomattavasti parempi vaihtoehto.

Lisätietoja: [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Dynamics 365 organisaatiopalvelujen käyttö](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-organization-service)

## <a name="about-the-web-services-and-the-platform"></a>Tietoja verkkopalveluista ja ympäristöstä

Ympäristön määrittävän organisaatiopalvelun tunnistaminen on tärkeää. WWW-ohjelmointirajapinta tarjoaa RESTful-ohjelmointikokemuksen, mutta loppujen lopuksi kaikki datatoiminnot kulkevat taustalla olevan organisaatiopalvelun kautta. 

Organisaatiopalvelu määrittää tuetut toiminnot sanomina. Kullakin sanomalla on nimi. SDK-kokoonpanoissa kullakin sanomalla on vastaava *&lt;sanomanimi&gt;*`Request` ja *&lt;sanomanimen&gt;*`Response` luokka. [IOrganizationService-käyttöliittymä](/dotnet/api/microsoft.xrm.sdk.iorganizationservice) `Microsoft.Xrm.Sdk.dll`:ssä määrittää useita apumenetelmiä yleisiä CRUD-toimintoja varten sekä [Suorita-menetelmän](/dotnet/api/microsoft.xrm.sdk.iorganizationservice.execute), jonka avulla sanomat voidaan käynnistää. Kaikissa sanomissa käytetään taustalla olevaa [OrganizationRequest-luokkaa](/dotnet/api/microsoft.xrm.sdk.organizationrequest).

WWW-ohjelmointirajapinta tarjoaa samat toiminnot kuin organisaatiopalvelu, mutta se esittää ne RESTful-tyylillä OData v4 -protokollan avulla. OData v4 tarjoaa nimetyt toiminnot *funktioiden* tai *toimintojen* kautta. Lähes jokainen organisaatiopalvelussa käytettävissä oleva sanoma paljastuu vastaavalla nimellä olevaksi funktioksi tai toiminnoksi. Kyseiset sanomat, jotka vastaavat CRUD-toimintoja, eivät ole käytettävissä WWW-ohjelmointirajapinnassa, koska RESTful-palveluna niiden käyttöönotot tehdään GET-, POST-, PATCH- ja DELETE HTTP -menetelmillä.

Organisaatiopalvelun SOAP-päätepisteen .NET SDK -kokoonpanot suunniteltiin siten, että ne vastaavat pitkälti taustalla olevia organisaatiopalveluita [IOrganizationService-käyttöliittymän](/dotnet/api/microsoft.xrm.sdk.iorganizationservice) perusteella. Ne eivät kuitenkaan ole samoja komponentteja, eikä niitä pidä sekoittaa toisiinsa. 

Organisaatiopalvelun SOAP-päätepiste esiteltiin vuonna 2011. Microsoft on ilmoittanut sen vanhentumisesta. Tämä tarkoittaa sitä, että se toimii edelleen ja sitä tuetaan yhä, kunnes se poistetaan. Microsoft on myös ilmoittanut, että .NET SDK -kokoonpanot päivitetään, joten ne toimivat myös sen jälkeen, kun SOAP-päätepiste on poistettu. Tämä tarkoittaa sitä, että päivitetyt SDK-kokoonpanot ovat käytettävissä ennen kuin SOAP-päätepiste poistetaan. Kehittäjien on päivitettävä koodinsa käyttämään näitä uusia kokoonpanoja jossakin vaiheessa tulevaisuudessa.

## <a name="discovery-services"></a>Resurssienetsintäpalvelut

Kukin Common Data Service for Apps -käyttäjä saattaa pystyä käyttämään useita Common Data Service for Apps -esiintymiä. Resurssienetsintäpalvelujen avulla voit kirjoittaa koodin ja tarjota käyttäjille esiintymäluettelon, jonka kautta käyttäjät voivat muodostaa yhteyden käytössä olevan Microsoft-tilin perusteella. Jokainen esiintymä sisältää URL-osoitteen, jonka avulla voit muodostaa yhteyden valittuun esiintymään. 

Resurssienetsintäpalvelua käytetään WWW-ohjelmointirajapinnan tai organisaatiopalvelun kautta.

- Lisätietoja WWW-ohjelmointirajapinnasta: [Dynamics 365 -asiakkaalle suunnattu kehittäjän opas: organisaation URL-osoitteen löytäminen WWW-ohjelmointirajapinnan avulla](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)
- Lisätietoja organisaatiopalvelusta: [Dynamics 365 -asiakkaalle suunnattu kehittäjän opas: organisaation URL-osoitteen löytäminen organisaatiopalvelun avulla](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)

## <a name="use-custom-actions"></a>Mukautettujen toimintojen käyttäminen

Yksi prosesseissa käytettävissä oleva määrittävä vaihtoehto on luoda *mukautettu toiminto*. Mukautettu toiminto tarkoittaa käytännössä uuden sanoman luomista organisaatiopalvelussa. Mukautettujen toimintojen avulla voit yhdistää tietyt toiminnot nimetyksi uudelleenkäytettäväksi toiminnoksi. Voit esimerkiksi luoda uuden sanoman nimeltä *new_Escalate*, jossa yhdistyy sarja vakiotoimintoja, jotka osallistuvat ilmoituksen lähettämiseen oikeille henkilöille, kun tärkeä asiakas kohtaa vakavan ongelman.

Kun määrität mukautetun toiminnon, valitset toiminnolle allekirjoituksen määrittämällä syöttöparametrit ja ominaisuudet, jotka sisällytetään jokaiseen palautettavaan tulokseen. Mukautetut toiminnot voidaan sen jälkeen käynnistää määritetystä prosessista suunnittelutoiminnon tai koodin avulla. 

Mukautettujen toimintojen ainutlaatuinen arvo on siinä, että niiden sisältämiä määrättyjä toimintoja voidaan muokata myös muun kuin kehittäjän toimesta suunnittelutoiminnossa ilman, että muokkaukset vaikuttavat muihin prosesseihin tai koodiin, joka kutsuu toiminnon.  Tämä pätee, jos toiminnon allekirjoitus ei muutu. Jos tarvitset eri syöttöparametrit tai tulosteominaisuudet, sinun on luotava uusi, erilainen mukautettu toiminto, jotta nykyistä käyttävät prosessit tai koodit eivät vioitu.

Kun mukautettu toiminto määritetään ympäristössä, uusi OData v4 -toiminto on käytettävissä WWW-ohjelmointirajapinnan avulla ja mukautettu toiminto voidaan käynnistää organisaatiopalvelussa käyttämällä suoraan [OrganizationRequest-luokkaa](/dotnet/api/microsoft.xrm.sdk.organizationrequest) tai vahvasti kirjoitettua luokkaa, joka on luotu *koodin muodostus -työkalulla (CrmSvcUtil.exe)*.

Lisätietoja: 
- [Dynamics 365 -asiakkaalle suunnattu mukautusopas: toimintojen yleiskatsaus](/dynamics365/customer-engagement/customize/actions)
- [Dynamics 365 -asiakkaalle suunnattu kehittäjän opas: omien toimintojen luominen](/dynamics365/customer-engagement/developer/create-own-actions)
- [Dynamics 365 -asiakkaalle suunnattu kehittäjän opas: WWW-ohjelmointirajapinnan toimintojen käyttäminen > mukautetun toiminnon käyttäminen](/dynamics365/customer-engagement/developer/webapi/use-web-api-actions#use-a-custom-action)

## <a name="metadata-services"></a>Metatietopalvelut

WWW-ohjelmointirajapinta ja organisaatiopalvelu sisältävät ominaisuuksia, joiden avulla CRUD-toiminnot voidaan suorittaa entiteettirakenteessa. Vaikka nämä toiminnot voidaan suorittaa koodin avulla, yleensä mukautetut rakenne-elementit lisätään, päivitetään tai poistetaan suunnittelutyökalujen avulla. Käyttäjillä on oltava järjestelmänvalvojan oikeudet, jotta rakennemuutokset voidaan ottaa käyttöön, mutta kaikki käyttäjät voivat lukea metatietoja.

Metatietopalvelujen yleisempi käyttötapa on metatietojen noutaminen ympäristöstä, jossa laajennus on käynnissä. Koska jokainen ympäristö voi olla erilainen ja rakenteen metatiedot sisältävät paljon tietoa siitä, miten ympäristö on määritetty, voit joutua noutamaan tiedot, jotta laajennus voidaan sopeuttaa muihin ympäristössä käytössä oleviin mukautuksiin.

Esimerkkejä:
- Asetusjoukko-määritteen vaihtoehtojen määrä voi vaihdella. Sen sijaan, että arvot koodataan tiukasti ympäristössä, harkitse, onko olemassa muita vaihtoehtoja. Voit suorittaa kyselyn järjestelmässä sen määrittämiseksi, käytetäänkö nykyisessä ympäristössä eri vaihtoehtoja.
- Entiteetin näyttönimeä voidaan muuttaa. Tilientiteetin oletusarvoinen näyttönimi on *Tili*. Sen tilalle voidaan vaihtaa *Yritys*. Jos haluat näyttää käyttäjälle sanoman ja viitata entiteetin nimeen, sitä ei kannata koodata tiukasti. Käytä sen sijaan arvoa, joka vastaa tietoa, jonka käyttäjä on tottunut näkemään. Käytä siis entiteetin metatiedoista noudettua näyttönimeä.

Jos ymmärrät metatietojen merkityksen järjestelmässä, voit ymmärtää helpommin, miten Common Data Service for Apps -ympäristö toimii. Metatietojen muokkaamiseen käytettävissä olevat suunnittelutyökalut eivät voi näyttää kaikkia metatietoihin sisältyviä yksityiskohtaisia tietoja. Voit asentaa malliin perustuvan *Metadata Browser* -sovelluksen, jonka avulla voit tarkastella kaikkia järjestelmässä olevia piilotettuja entiteettejä ja metatieto-ominaisuuksia. 

Lisätietoja: [Dynamics 365 -asiakkaalle suunnattu kehittäjän opas: organisaation metatietojen selaaminen](/dynamics365/customer-engagement/developer/browse-your-metadata)

Lisätietoja metatietojen käsittelystä ohjelmallisesti:
- [Dynamics 365 -asiakkaalle suunnattu kehittäjän opas: WWW-ohjelmointirajapinnan käyttäminen metatiedoilla](/dynamics365/customer-engagement/developer/webapi/use-web-api-metadata)
- [Dynamics 365 -asiakkaalle suunnattu kehittäjän opas: Dynamics 365 -organisaatiopalvelun käyttö Dynamics 365 -metatiedoilla](/dynamics365/customer-engagement/developer/org-service/use-organization-service-metadata)
 
### <a name="see-also"></a>Katso myös

[Common Data Service for Apps -palvelun kehittäjien yleiskatsaus](overview.md)


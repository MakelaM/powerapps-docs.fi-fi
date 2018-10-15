---
title: Kehittäjien resurssien tarkasteleminen tai lataaminen | MicrosoftDocs
description: Etsi kehittäjien resursseja ja palvelun päätepisteen URL-osoitteita
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e200d242-ff3f-48e5-af32-aed050e02441
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.openlocfilehash: ae93b57d9ead3a62fb538ae986eb524367259545
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680008"
---
<!-- TODO: The Developer Resources page have to be updated to match this page -->

# <a name="view-or-download-developer-resources"></a>Kehittäjien resurssien tarkasteleminen tai lataaminen

Tällä sivulla on resursseja kehittäjille ja tietoja tietystä esiintymästä, jota käsittelet. 

## <a name="view-the-developer-resources-page-for-your-environment"></a>Näytä ympäristön Kehittäjien resurssit -sivu

1. Valitse PowerApps-portaalissa valitsemalla ![Asetukset-painike](../../administrator/media/settings-button-nav-bar.png) Asetukset-painike ja valitse **Kehittyneet mukautukset**.

    ![Kehittyneet mukautukset](media/advanced-customizations-menu.png)

1. **Kehittyneet mukautukset** -paneelissa valitse **Kehittäjien resurssit** -linkki:<br />![Kehittäjien resurssit -linkki](media/developer-resources-link.png)

## <a name="getting-started"></a>Aloittaminen 

Tässä osassa on linkkejä kehittäjille resurssien löytämiseksi. Seuraavat resurssit ovat käytettävissä:


|Linkki |Kuvaus|
|---------|---------|
|[Kehittäjäkeskus](https://go.microsoft.com/fwlink/?LinkId=551006)|Kehittäjien dokumentaation tärkein aloituskohta.|
|[Kehittäjien keskustelupalstat](https://go.microsoft.com/fwlink/?LinkId=550993)|Kysy kysymyksiä ja vastaa niihin muiden kehittäjien kanssa.|
|[NuGet-paketit](https://go.microsoft.com/fwlink/?LinkId=550994)|Tutustu NuGet-paketteihin lisätäksesi SDK-kokoonpanoja projektiisi.|
|[Lataa työkalut](https://go.microsoft.com/fwlink/?LinkID=512122)|Työkalut, joita tarvitset, ovat ladattavissa NuGetista. Saat uusimmat versiot tällä sivulla olevan PowerShell-komentosarjan avulla.|
|[Esimerkkikoodi](https://go.microsoft.com/fwlink/?LinkId=553007)|Luettelo saatavilla olevista esimerkeistä.|
|[Yleiskatsaus kehittäjille](https://go.microsoft.com/fwlink/?LinkId=550995)|Linkki aiheeseen, joissa on yleiskatsaus kehittäjille.|

<!-- TODO update 512122 to go to https://docs.microsoft.com/dynamics365/customer-engagement/developer/download-tools-nuget -->


## <a name="connect-your-apps-to-this-instance-of-common-data-service-for-apps"></a>Yhdistä sovelluksesi tähän Common Data Service for Apps -esiintymään

Tässä osassa on tietoja, joita tarvitset muodostaaksesi yhteyden tähän Common Data Service for Apps -esiintymään.

### <a name="instance-web-api"></a>Esiintymän WWW-ohjelmointirajapinta

Tämä on esiintymän WWW-ohjelmointirajapinnan URL-osoite. The WWW-ohjelmointirajapinta on OData v4 RESTful -ohjelmointirajapinta. Voit myös ladata palveluasiakirjan, joka kuvaa esiintymässä käytettävissä olevia metatietoja ja toimintoja. Lisätietoja: [Kehittäjien dokumentaatio: Dynamics 365 Customer Engagement -WWW-ohjelmointirajapinnan käyttäminen](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)

### <a name="organization-service"></a>Organisaatiopalvelut

Tämä on esiintymän organisaatiopalvelujen SOAP-päätepisteen URL-osoite.
Voit ladata tämän palvelun WSDL:n täällä, mutta yleensä entiteettiluokkien luomisessa .NET-projekteille käytetään CrmSvcUtil.exe-koodinmuodostustyökalua. Lisätietoja: 
- [Kehittäjien dokumentaatio: aikaisin sidottujen entiteettiluokkien luominen koodin muodostus -työkalun avulla (CrmSvcUtil.exe)](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)
- [Kehittäjien dokumentaatio: Organisaatiopalvelujen käyttö tietojen tai metatietojen lukemiseen ja kirjoittamiseen](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)

### <a name="instance-reference-information"></a>Esiintymän viitetiedot

Nämä tiedot kuvaavat esiintymää yksilöllisesti. Saatavana on GUID-**tunnus** ja **Yksilöllinen nimi**.
Näitä tietoja tarvitaan, kun käytät Azure-laajennuksia esiintymän kanssa.
Lisätietoja: [Kehittäjien dokumentaatio: Azure-laajennukset Dynamics 365 Customer Engagementille](/dynamics365/customer-engagement/developer/azure-extensions)

## <a name="connect-your-apps-to-the-common-data-service-for-apps-discovery-service"></a>Yhdistä sovelluksesi Common Data Service for Apps -etsintäpalveluun

Koska käyttäjillä voi olla oikeus useisiin CDS for Apps -ympäristöihin, etsintäpalveluiden avulla voidaan noutaa saatavilla olevia ympäristöjä, jotka ovat henkilön käytettävissä tunnistetietojen perusteella.

### <a name="discovery-web-api"></a>Verkkoetsintäpalvelun ohjelmointirajapinta

Tämä on päätepisteosoite etsintäpalvelun RESTful OData v4 -versiolle esiintymän kanssa käytettäväksi. Voit myös ladata palveluasiakirjan täältä.
Lisätietoja: [Kehittäjien dokumentaatio: organisaation URL-osoitteen etsiminen WWW-ohjelmointirajapinnan avulla](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)


### <a name="discovery-service"></a>Etsintäpalvelu

Tämä on päätepisteosoite esiintymässä käytettävälle etsintäpalvelun SOAP-versiolle. Voit myös ladata palveluasiakirjan täältä.
Lisätietoja: [Kehittäjien dokumentaatio: organisaation URL-osoitteen etsiminen etsintäpalvelun avulla](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  
### <a name="more-information"></a>Lisätietoja

[Kehittäjien dokumentaatio: Kehittäjien resurssit -sivu](/dynamics365/customer-engagement/developer/developer-resources-page)<br />
[Kehittäjien dokumentaatio: Dynamics 365 Customer Engagement -WWW-ohjelmointirajapinnan käyttäminen](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)<br />
[Kehittäjien dokumentaatio: Organisaatiopalvelujen käyttö tietojen tai metatietojen lukemiseen ja kirjoittamiseen](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)<br />
[Kehittäjien dokumentaatio: Azure-laajennukset Dynamics 365 Customer Engagementille](/dynamics365/customer-engagement/developer/azure-extensions)<br />
[Kehittäjien dokumentaatio: organisaation URL-osoitteen etsiminen WWW-ohjelmointirajapinnan avulla](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)<br />
[Kehittäjien dokumentaatio: organisaation URL-osoitteen etsiminen etsintäpalvelun avulla](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  


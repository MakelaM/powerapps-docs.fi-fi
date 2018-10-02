---
title: Kehittäjien resurssien tarkasteleminen tai lataaminen | MicrosoftDocs
description: Etsi Kehittäjien resurssit ja palvelun päätepiste-URL-osoitteet
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: e200d242-ff3f-48e5-af32-aed050e02441
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
<!-- TODO: The Developer Resources page have to be updated to match this page -->

# <a name="view-or-download-developer-resources"></a>Kehittäjien resurssien tarkasteleminen tai lataaminen

Tällä sivulla on tietoja sovelluskehittäjien resursseista ja käsiteltävänä olevasta tietystä ilmentymästä. 

## <a name="view-the-developer-resources-page-for-your-environment"></a>Sovelluskehittäjän resurssit -sivun tarkasteleminen ympäristössä

1. Valitse PowerApps-portaalissa ![Asetukset-painike](../../administrator/media/settings-button-nav-bar.png) Asetukset-painike ja valitse **Lisämukautukset**.

    ![Lisämukautukset](media/advanced-customizations-menu.png)

1. Valitse **Lisämukautukset**-paneelissa **Sovelluskehittäjän resurssit** -linkki:<br />![Sovelluskehittäjän resurssit -linkki](media/developer-resources-link.png)

## <a name="getting-started"></a>Alkutoimet 

Tässä osassa on linkkejä, joiden avulla sovelluskehittäjät voivat etsiä resursseja. Käytettävissä ovat seuraavat resurssit:


|Linkitä |Kuvaus|
|---------|---------|
|[Kehittäjäkeskus](https://go.microsoft.com/fwlink/?LinkId=551006)|Sovelluskehittäjän dokumentaation tärkein aloituskohta.|
|[Sovelluskehittäjien keskustelupalstat](https://go.microsoft.com/fwlink/?LinkId=550993)|Esitä kysymyksiä muille sovelluskehittäjille ja vastaa heidän kysymyksiinsä.|
|[NuGet-paketit](https://go.microsoft.com/fwlink/?LinkId=550994)|Tutustu NuGet-paketteihin, jotta voit lisätä SDK-kokoonpanoja projekteihin.|
|[Työkalujen lataaminen](https://go.microsoft.com/fwlink/?LinkID=512122)|Tarvittavat työkalut ovat ladattavissa NuGet-ohjelmasta. Hae uusimmat versiot tämän sivun PowerShell-komentosarjan avulla.|
|[Esimerkkikoodi](https://go.microsoft.com/fwlink/?LinkId=553007)|Käytettävissä olevien esimerkkien luettelo.|
|[Kehittäjäkatsaus](https://go.microsoft.com/fwlink/?LinkId=550995)|Linkki ohjeaiheeseen, joka sisältää sovelluskehittäjien yleiskatsauksen.|

<!-- TODO update 512122 to go to https://docs.microsoft.com/dynamics365/customer-engagement/developer/download-tools-nuget -->


## <a name="connect-your-apps-to-this-instance-of-common-data-service-for-apps"></a>Yhteyden muodostaminen sovelluksista Common Data Service sovelluksille -ratkaisun tähän ilmentymään

Tässä osassa on tietoja, joiden avulla voit muodostaa yhteyden Common Data Service sovelluksille -ilmentymään.

### <a name="instance-web-api"></a>Esiintymän Web-ohjelmointirajapinta

Tämä on ilmentymän Web-ohjelmointirajapinnan URL-osoite. Web-ohjelmointirajapinta on OData v4 RESTful -ohjelmointirajapinta. Voit ladata myös palveluasiakirjan, jossa kerrotaan ilmentymän käytettävissä olevista metatiedoista ja toiminnoista.. Lisätietoja: [Sovelluskehittäjän dokumentaatio: Dynamics 365 Customer Engagement -sovelluksen Web -ohjelmointirajapinnan käyttäminen](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)

### <a name="organization-service"></a>Organisaation palvelu

Tämä on ilmentymän organisaation palvelun SOAP-päätepisteen URL-osoite.
Voit ladata tämän palvelun WSDL:n täältä, mutta yleensä käytössä on CrmSvcUtil.exe-koodin luontityökalu. Sen avulla luodaan entiteetin luokat .NET-projekteissa. Lisätietoja: 
- [Sovelluskehittäjän dokumentaatio: Varhaisen sidotun entiteetin luokkien luominen koodin luontityökalun avulla (CrmSvcUtil.exe)](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)
- [Sovelluskehittäjän dokumentaatio: Organisaation palvelun käyttäminen tietojen tai metatietojen lukemisessa tai kirjoittamisessa](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)

### <a name="instance-reference-information"></a>Ilmentymän viitetiedot

Nämä tiedot yksilöivät ilmentymän. Tiedot sisältävät GUID-**tunnuksen** ja **yksilöllisen nimen**.
Näitä tietoja tarvitaan ilmentymän Azure-laajennusten käytössä.
Lisätietoja: [Sovelluskehittäjän dokumentaatio: Dynamics 365 Customer Engagement -sovelluksen Azure-laajennukset](/dynamics365/customer-engagement/developer/azure-extensions)

## <a name="connect-your-apps-to-the-common-data-service-for-apps-discovery-service"></a>Yhteyden muodostaminen sovelluksista Common Data Service sovelluksille -ratkaisun etsintäpalveluun

Käyttäjillä voi olla useita CDS sovelluksille -ympäristöjen käyttöoikeuksia. Tämän vuoksi etsintäpalvelu hakee käyttäjien käytettävissä olevat ympäristöt käyttäjien tunnistetietojen avulla.

### <a name="discovery-web-api"></a>Verkkoetsintäpalvelun ohjelmointirajapinta

Tämä on ilmentymän etsintäpalvelussa käytettävä RESTful OData v4 -version päätepisteen osoite. Voit ladata myös palveluasiakirjan täältä.
Lisätietoja: [Sovelluskehittäjän dokumentaatio: Organisaation URL-osoitteen haku Web-ohjelmointirajapinnan avulla](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)


### <a name="discovery-service"></a>Etsintäpalvelu

Tämä on ilmentymän etsintäpalvelussa käytettävä SOAP-version päätepisteen osoite. Voit ladata myös palveluasiakirjan täältä.
Lisätietoja: [Sovelluskehittäjän dokumentaatio: Organisaation URL-osoitteen haku etsintäpalvelun](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  
### <a name="more-information"></a>Lisätietoja

[Sovelluskehittäjän dokumentaatio: Sovelluskehittäjän resurssit -sivu](/dynamics365/customer-engagement/developer/developer-resources-page)<br />
[Sovelluskehittäjän dokumentaatio: Dynamics 365 Customer Engagement -sovelluksen Web -ohjelmointirajapinnan käyttäminen](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)<br />
[Sovelluskehittäjän dokumentaatio: Organisaation palvelun käyttäminen tietojen tai metatietojen lukemisessa tai kirjoittamisessa](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)<br />
[Sovelluskehittäjän dokumentaatio: Dynamics 365 Customer Engagement -sovelluksen Azure-laajennukset](/dynamics365/customer-engagement/developer/azure-extensions)<br />
[Sovelluskehittäjän dokumentaatio: Organisaation URL-osoitteen haku Web-ohjelmointirajapinnan avulla](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)<br />
[Sovelluskehittäjän dokumentaatio: Organisaation URL-osoitteen haku etsintäpalvelun](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  


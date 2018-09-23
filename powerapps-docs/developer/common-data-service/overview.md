---
title: Common Data Service for Apps Developer -palvelun yleiskatsaus | Microsoft Docs
description: Lue, miten kehittäjät voivat lisätä arvoja käyttämällä Common Data Service for Apps -palvelua.
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
ms.date: 03/19/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 3b0e2d70a9295bdf1a8a6d6a71cb6075677bb991
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42844050"
---
# <a name="common-data-service-for-apps-developer-overview"></a>Common Data Service for Apps Developer -palvelun yleiskatsaus

PowerApps tarjoaa käyttäjille, yrityksille, itsenäisille ohjelmistovalmistajille sekä laitekokoajille tehokkaan ympäristön liiketoiminta-aluesovellusten rakentamiseen. Common Data Service -palvelun laajennus, jota kutsutaan Common Data Service for Apps -palveluksi, on uusi lisäys PowerAppsiin ja se sisältää Dynamics 365 -ympäristön ydinfunktiot, joita käytetään Dynamics 356 for Sales, Marketing ja Customer Service -palvelujen kanssa.


## <a name="get-started"></a>Aloita

Jos olet jo käyttänyt Dynamics 365 for Sales, Marketing tai Customer Service -sovelluksia, pystyt hyödyntämään näitä kokemuksia mukauttaaksesi ja laajentaaksesi Common Data Service for Apps -palvelua.

Jos et ole käyttänyt Dynamics 365 for Sales, Marketing tai Customer Service -sovelluksia, seuraavat aiheet tarjoavat yleiskatsauksen tärkeimmistä käsitteistä ja auttavat alkuun Common Data Service for Apps -palvelun käytössä.

> [!NOTE]
> - Mallipohjaiset sovellukset ovat yhteydessä Common Data Service for Apps -palveluun. Saadaksesi lisätietoja siitä, miten kehittäjät voivat lisätä arvoja sovellustasolla, katso [Mallipohjaisten sovelluksien yleiskuvaus](../model-driven-apps/overview.md). Tämän osan sisältöä viittaa vain laajennuksiin, joita kehittäjät voivat tehdä palvelutasolla. 
> - Koska Common Data Service for Apps -palvelu käyttää samaa alustaa kuin Dynamics 365 Sales, Marketing tai Customer Service -sovellukset, löydät kehittäjille tarkoitettuja tarkempia tietoja [Dynamics 365 asiakkaalle suunnatusta kehittäjän -oppaasta](/dynamics365/customer-engagement/developer/developer-guide). Aiheet sisältävät yhteenvedon ja linkkejä kehittäjän oppaaseen sekä muihin oppaisiin, joista löytyy lisätietoja.


## <a name="tools-and-resources-for-developers"></a>Työkalut ja resurssit kehittäjille

Kehittäjät voivat käyttää seuraavat työkaluja ja resursseja käsitellessään ratkaisuja Common Data Service -palvelun avulla.

### <a name="tools-available-for-download-from-nuget"></a>NuGet:n kautta ladattavissa olevat työkalut

Seuraavat työkalut ovat saatavilla NuGet-paketteina. [Kehittäjän opas: lataa työkalut NuGet:sta](/dynamics365/customer-engagement/developer/download-tools-nuget) -aihe sisältää PowerShell-komentosarjan, jonka avulla voit ladata ja poimia uusimmat versiot näistä työkaluista.

|Työkalu  |Kuvaus  |
|---------|---------|
|Koodin muodostus -työkalu `CrmSvcUtil.exe`|Koodin muodostamisen komentorivityökalu, jonka avulla luodaan aikaisin sidotut .NET Framework -luokat, jotka edustavat organisaatiopalvelun käyttämää entiteettitietomallia. <br />Lisätietoja: <br />[Organisaatiopalvelut](use-web-services.md#organization-service)<br />[Dynamics 365 asiakkaalle suunnattu kehittäjän opas: aikaisin sidottujen entiteettiluokkien luominen koodin muodostus -työkalun avulla ](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)|
|Määritysten siirtotyökalu `DataMigrationUtility.exe`|Käytetään määritysten siirtoon ympäristöjen välillä. Määritystietoja käytetään määrittämään mukautettuja toimintoja ja ne tallennettaan yleensä mukautettuihin entiteetteihin. Työkalua ei ole tarkoitettu yritystietojen siirtoon. <br /> Lisätietoja: [Dynamics 365 asiakkaalle suunnattu järjestelmänvalvojan opas: määritystietojen siirto esiintymien ja organisaatioiden välillä kokoonpanon siirtotyökalun avulla](/dynamics365/customer-engagement/admin/manage-configuration-data)|
|Pakettien käyttöönottaja `PackageDeployer.exe`|Käytetään pakettien käyttöönottoon Common Data Service for Apps -palvelussa. Paketti on asennettavissa oleva yksikkö, joka sisältää ratkaisuja. <br /> Lisätietoja: <br />[Ratkaisupakettien käyttöönotto](introduction-solutions.md#deploy-solution-packages)<br />[Dynamics 365 asiakkaalle suunnattu kehittäjän opas: pakettien luominen Dynamics 365 paketin käyttöönotto -toimintoa varten](/dynamics365/customer-engagement/developer/create-packages-package-deployer)|
|Laajennuksen rekisteröintityökalu `PluginRegistration.exe`|Työkalu, jonka avulla tilataan .NET -kokoonpanolaajennuksien luokkia palvelimen tapahtumiin. <br />Lisätietoja: <br />[Laajennuksen luominen](apply-business-logic-with-code.md#create-a-plug-in)<br />[Dynamics 365 asiakkaan suunnattu kehittäjän opas: laajennuksen rekisteröinti laajennus rekisteröinti -työkalun avulla](/dynamics365/customer-engagement/developer/walkthrough-register-plugin-using-plugin-registration-tool)|
|Ratkaisun pakkaajatyökalu`SolutionPackager.exe`|Työkalu, jolla voi hajottaa palautuvasti Common Data Service for Apps -palvelun ratkaisutiedoston useiksi XML-tiedostoiksi ja muiksi tiedostoiksi, niin, että näitä tiedostoja voidaan helposti hallittava ohjausobjektin lähdejärjestelmässä.<br /> Lisätietoja: <br />[Ratkaisujen tiimikehitys](introduction-solutions.md#team-development-of-solutions)<br />[Dynamics 365 asiakkaalle suunnattu kehittäjän opas: ratkaisupakkaaja-työkalun käyttäminen ratkaisutiedoston pakkaamiseen ja purkamiseen](/dynamics365/customer-engagement/developer/compress-extract-solution-file-solutionpackager)|

### <a name="net-sdk-assemblies"></a>.NET SDK -kokoonpanot

Seuraavassa kokoonpanoja, joita .NET-kehittäjät voivat käyttää. Uusimmat versiot ovat ladattavissa vastaavina NuGet-paketteina.

#### <a name="work-with-data"></a>Tietojen käsittely

Näiden kokoonpanojen avulla voit käsitellä organisaatio- ja resurssienetsintäpalveluja.

Lisätietoja: [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Dynamics 365 organisaatiopalvelujen käyttö](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-organization-service)

**NuGet-paketti**: [Microsoft.CrmSdk.CoreAssemblies](https://www.nuget.org/packages/Microsoft.CrmSdk.CoreAssemblies/)

|Kokoonpano  |Nimitilat  |
|---------|---------|
|Microsoft.Crm.Sdk.Proxy.dll|[Microsoft.Crm.Sdk](/dotnet/api/microsoft.crm.sdk)<br />[Microsoft.Crm.Sdk.Messages](/dotnet/api/microsoft.crm.sdk.messages)|
|Microsoft.Xrm.Sdk.dll|[Microsoft.Xrm.Sdk](/dotnet/api/microsoft.xrm.sdk)<br />[Microsoft.Xrm.Sdk.Client](/dotnet/api/microsoft.xrm.sdk.client)<br />[Microsoft.Xrm.Sdk.Discovery](/dotnet/api/microsoft.xrm.sdk.discovery)<br />[Microsoft.Xrm.Sdk.Messages](/dotnet/api/microsoft.xrm.sdk.messages)<br />[Microsoft.Xrm.Sdk.Metadata](/dotnet/api/microsoft.xrm.sdk.metadata)<br />[Microsoft.Xrm.Sdk.Metadata.Query](/dotnet/api/microsoft.xrm.sdk.metadata.query)<br />[Microsoft.Xrm.Sdk.Organization](/dotnet/api/microsoft.xrm.sdk.organization)<br />[Microsoft.Xrm.Sdk.Query](/dotnet/api/microsoft.xrm.sdk.query)<br />[Microsoft.Xrm.Sdk.WebServiceClient](/dotnet/api/microsoft.xrm.sdk.webserviceclient)|

#### <a name="create-process-designer-workflow-extensions"></a>Prosessin suunnittelutyökalu (työnkulku) -laajennusten luominen

Kokoonpanon avulla voit lisätä prosessin suunnittelutyökaluun mukautettuja toimintoja. 

Lisätietoja [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: mukautetut työnkulkuaktiviteetit (työnkulun kokoonpanot)](/dynamics365/customer-engagement/developer/custom-workflow-activities-workflow-assemblies)

**NuGet-paketti**: [Microsoft.CrmSdk.Workflow](https://www.nuget.org/packages/Microsoft.CrmSdk.Workflow/) 

|Kokoonpano|Nimitilat|
|---------|---------|
|Microsoft.Xrm.Sdk.Workflow.dll|[Microsoft.Xrm.Sdk.Workflow](/dotnet/api/microsoft.xrm.sdk.workflow)<br />[Microsoft.Xrm.Sdk.Workflow.Activities](/dotnet/api/microsoft.xrm.sdk.workflow.activities)<br />[Microsoft.Xrm.Sdk.Workflow.Designers](/dotnet/api/microsoft.xrm.sdk.workflow.designers)|

#### <a name="build-windows-client-applications"></a>Windows-asiakassovellusten kehitys

Kokoonpanoja käytetään muodostettaessa yhteyttä organisaatiopalveluun ja rakennettaessa Windows-asiakassovelluksia. 

Lisätietoja [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Windows-asiakassovellusten rakentaminen XRM-työkaluilla](/dynamics365/customer-engagement/developer/build-windows-client-applications-xrm-tools)

**NuGet-paketit**:
- [Microsoft.CrmSdk.XrmTooling.CoreAssembly](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.CoreAssembly/) (Microsoft.Xrm.Tooling.Connector.dll)
- [Microsoft.CrmSdk.XrmTooling.WpfControls](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.WpfControls/) 

|Kokoonpano|Nimitilat  |
|---------|---------|
|Microsoft.Xrm.Tooling.Connector.dll|[Microsoft.Xrm.Tooling.Connector](/dotnet/api/microsoft.xrm.tooling.connector)<br />[Microsoft.Xrm.Tooling.Connector.Model](/dotnet/api/microsoft.xrm.tooling.connector.model)|
|Microsoft.Xrm.Tooling.CrmConnectControl.dll|[Microsoft.Xrm.Tooling.CrmConnectControl](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Model](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.model)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Properties](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.properties)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Utility](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.utility)|
|Microsoft.Xrm.Tooling.WebResourceUtility.dll|[Microsoft.Xrm.Tooling.WebResourceUtility](/dotnet/api/microsoft.xrm.tooling.webresourceutility)|

#### <a name="create-packages"></a>Pakettien luominen

Kokoonpanojen avulla voit luoda paketteja paketin käyttöönottotoiminnolle.

Lisätietoja: [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: pakettien luonti Dynamics 365 paketin käyttöönotto -toiminnolle](/dynamics365/customer-engagement/developer/create-packages-package-deployer)

**NuGet-paketti**: [Microsoft.CrmSdk.XrmTooling.PackageDeployment](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment/)

|Kokoonpano|Nimitila  |
|---------|---------|
|Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.dll|[Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase](/dotnet/api/microsoft.xrm.tooling.packagedeployment.crmpackageextentionbase)|

#### <a name="create-custom-virtual-entity-data-providers"></a>Mukautettujen näennäiskohdetietopalvelujen luonti

Kokoonpanon avulla voit luoda mukautettuja näennäiskohdetietopalveluja. 

Lisätietoja: [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: näennäisentiteettien käyttö](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)

**NuGet-paketti**: [Microsoft.CrmSdk.Data](https://www.nuget.org/packages/Microsoft.CrmSdk.Data/)

|Kokoonpano  |Nimitilat  |
|---------|---------|
|Microsoft.Xrm.Sdk.Data.dll|[Microsoft.Xrm.Sdk.Data](/dotnet/api/microsoft.xrm.sdk.data)<br />[Microsoft.Xrm.Sdk.Data.CodeGen](/api/microsoft.xrm.sdk.data.codegen)<br />[Microsoft.Xrm.Sdk.Data.Converters](/dotnet/api/microsoft.xrm.sdk.data.converters)<br />[Microsoft.Xrm.Sdk.Data.Exceptions](/dotnet/api/microsoft.xrm.sdk.data.exceptions)<br />[Microsoft.Xrm.Sdk.Data.Expressions](/dotnet/api/microsoft.xrm.sdk.data.expressions)<br />[Microsoft.Xrm.Sdk.Data.Infra](/dotnet/api/microsoft.xrm.sdk.data.infra)<br />[Microsoft.Xrm.Sdk.Data.Mappings](/dotnet/api/microsoft.xrm.sdk.data.mappings)|

#### <a name="extend-outlook-client"></a>Outlook-asiakasohjelman laajennus

Koonpanon avulla voit käyttää Microsoft Dynamics 365 Outlookia ja Microsoft Dynamics 365 for Microsoft Office Outlookia offline-tilassa. 

Lisätietoja: [Dynamics 365 asiakkaalle suunnattu kehittäjän opas: Dynamics 365 Customer Engagement for Outlook -laajennus](/dynamics365/customer-engagement/developer/extend-customer-engagement-outlook)

**NuGet-paketti**: [Microsoft.CrmSdk.Outlook](https://www.nuget.org/packages/Microsoft.CrmSdk.Outlook/)

|Kokoonpano|Nimitila|
|---------|---------|
|Microsoft.Crm.Outlook.Sdk.dll|[Microsoft.Crm.Outlook.Sdk](/dotnet/api/microsoft.crm.outlook.sdk)|



## <a name="community-tools-for-common-data-service-for-apps"></a>Common Data Service for Apps -palvelun yhteisötyökalut

Dynamics 365 -yhteisön luo työkaluja! Useat suosituimmista jaetaan [XrmToolBoxissa](https://www.xrmtoolbox.com/). XrmToolBox on Windows-sovellus, joka yhdistää Common Data Service for Apps -palveluun, tarjoten työkaluja, joilla mukauttaminen, kokoonpano ja toimintatehtävät helpottuvat. Se sisältä yli 30 laajennusta tehden hallinnasta, mukauttamisesta tai määritystehtävistä entistä helpompaa ja vähemmän aikaa vievää.

Seuraavassa luettelo valituista yhteisötyökaluista, jotka ovat saatavilla XrmToolBox,:n kautta, ja jota voidaan käyttää Common Data Service for Apps -palvelun kanssa.

|Työkalu  |Kuvaus  |
|---------|---------|
|[Määritteen hallinta](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.AttributeManager/)|Käytetään määritteen uudelleennimeämisessä/poistamisessa/tai muutettaessa määritteen tyyppiä.|
|[Aikaisen sidonnan -muodostin](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.EarlyBoundGenerator/)|Luo aikaisin sidottuja entiteettejä/asetusjoukkoja/toimintoja. Käyttää SDK:n CrmSvcUtil:a ja näyttää luokat avaimien luonnissa käytetyn komentorivin.|
|[Vienti Exceliin](https://www.xrmtoolbox.com/plugins/Ryr.XrmToolBox.ExportToExcel/)|Vie tietueita helposti valitusta näkymästä/fetchxml:stä Exceliin.|
|[FetchXML-muodostin](https://www.xrmtoolbox.com/plugins/Cinteros.Xrm.FetchXmlBuilder/)|Luo ja testaa FetchXml-kyselyjä|
|[Metatietoselain](https://www.xrmtoolbox.com/plugins/MsCrmTools.MetadataBrowser/)|Selaa Dynamics CRM -organisaatiosi metatietoja|
|[Laajennusten pinojäljityksen katseluohjelma](https://www.xrmtoolbox.com/plugins/Cinteros.XrmToolBox.PluginTraceViewer/)|Tutki laajennuksen jäljityslokia helposti, suodatin- ja näkymämahdollisuuksilla|
|[Käyttäjän asetukset -apuohjelma](https://www.xrmtoolbox.com/plugins/MsCrmTools.UserSettingsUtility/)|Hallitse käyttäjien henkilökohtaisia asetuksia joukkoina|

> [!NOTE]
> Microsoft ei tue yhteisön luomia työkaluja. Jos sinulla on kysymyksiä tai ongelmia yhteisötyökalujen kanssa, ota yhteyttä työkalun julkaisijaan.

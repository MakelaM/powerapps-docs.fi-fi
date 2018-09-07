---
title: Mallipohjaisten sovelluksien yleiskuvaus kehittäjille | Microsoft Docs
description: Lue miten kehittäjät voivat lisätä arvoja mallipohjaisiin sovelluksiin.
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
ms.date: 03/17/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 39fe83cdb059e0f1df634b9933f4a2f4251bca7b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42852410"
---
# <a name="model-driven-apps-developer-overview"></a>Mallipohjaisten sovelluksien yleiskuvaus

PowerApps tarjoaa käyttäjille, yrityksille, yhteistyökumppaneille, itsenäisille ohjelmistovalmistajille sekä laitekokoajille tehokkaan ympäristön liiketoiminta-aluesovellusten rakentamiseen. Tässä versiossa PowerAppsiin on lisätty mallipohjaisia sovelluksia, jotka on luotu käyttämällä uutta Common Data Service for Apps -palvelua. Common Data Service for Apps -palvelu sisältää nyt Dynamics 365 asiakkaalle suunnattujen sovellusten ydintoiminnot. Mallipohjaisten sovellusten avulla voit rakentaa sovelluksia, jotka käyttävät kyseisten sovellusten kanssa samoja laajennettavuusominaisuuksia.

Mallipohjaiset sovellukset ovat ensisijaisesti sovelluskehityksen komponenttikeskeisiä no-code tai low-code -lähestymistapoja. Kehittäjät voivat tarjota sovelluslaajennuksia. Ennen kuin aloitat koodin kirjoittamisen, opettele mallipohjaisen sovelluksen rakentaminen ja vaihtoehdot, jotka voidaan ottaa käyttöön ilman koodia. 

## <a name="get-started"></a>Aloita
Jos olet jo käyttänyt Dynamics 365 asiakkaalle suunnattuja sovelluksia, pystyt hyödyntämään tätä kokemuksesta mallipohjaisten sovellusten kehittämisessä. Saatavilla on joitakin uusia suunnittelutyökaluja, mutta yleiskäsitteet ovat samoja.

> [!NOTE]
> Mallipohjaiset sovellukset ovat yhteydessä Common Data Service for Apps -palveluun. Lisätietoja siitä, miten kehittäjät voivat lisätä arvoa palvelutasolla, katso [Common Data Service for Apps -palvelun yleiskuvaus](../common-data-service/overview.md).
> Tämän osan sisältöä viittaa vain laajennuksiin, joita kehittäjät voivat tehdä, jotka koskevat mallipohjaisten sovellusten käyttökokemusta. 

Jos et ole käyttänyt Dynamics 365 asiakkaalle suunnattuja sovelluksia, tämän osan aiheet tarjoavat korkeatasoisen yleiskatsauksen tärkeisiin käsitteisiin, jotka auttavat kehittäjiä alkuun mallipohjaisten sovelluksien käytössä. 

> [!NOTE]
> Koska Common Data Service for Apps -palvelu käyttää samaa alustaa kuin Dynamics 365 Customer Engagement, löydät kehittäjille tarkoitettuja tarkempia tietoja [Dynamics 365 asiakkaalle suunnatusta kehittäjän -oppaasta](/dynamics365/customer-engagement/developer/developer-guide). Aiheet sisältävät yhteenvedon ja linkkejä kehittäjän oppaaseen sekä muihin oppaisiin, joista löytyy lisätietoja.


## <a name="community-tools-for-model-driven-apps"></a>Yhteisötyökalut mallinpohjaisille sovelluksille

Dynamics 365 -yhteisön luo työkaluja! Useat suosituimmista jaetaan [XrmToolBoxin kautta](https://www.xrmtoolbox.com/). XrmToolBox on Windows-sovellus, joka yhdistää Common Data Service for Apps -palveluun, tarjoten työkaluja, joilla mukauttaminen, kokoonpano ja toimintatehtävät helpottuvat. Se sisältää yli 30 laajennusta tehden hallinnasta, mukauttamisesta tai määritystehtävistä entistä helpompaa ja vähemmän aikaa vievää.

Seuraavassa on joitakin XrmToolBoxin kautta saatavilla olevia yhteisötyökaluja, joita voi käyttää mallipohjaisia sovelluksia käsiteltäessä

|Työkalu  |Kuvaus  |
|---------|---------|
|[Helppo kääntäjä](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/)|Vie ja tuo käännökset tilannekohtaisilla tiedoilla|
|[Vienti Exceliin](https://www.xrmtoolbox.com/plugins/Ryr.XrmToolBox.ExportToExcel/)|Vie tietueita helposti valitusta näkymästä/fetchxml:stä Exceliin.|
|[Iconator](https://www.xrmtoolbox.com/plugins/MscrmTools.Iconator/)|Hallitse mukautettuja entiteettikuvakkeita samassa näytössä|
|[Valintanauha Workbench 2016](https://www.xrmtoolbox.com/plugins/RibbonWorkbench2016/)|Dynamics CRM-valintanauhan tai komentopalkin muokkaaminen XrmToolboxissa|
|[Näkymän suunnitteluohjelma](https://www.xrmtoolbox.com/plugins/Cinteros.XrmToolBox.ViewDesigner/)|Yksinkertaistettu käyttöliittymä näkymäasettelujen ja vaihtoehtoisten kyselyn luomiseksi FetchXML Builderia käyttämällä|
|[Asettelun monistusnäkymä](https://www.xrmtoolbox.com/plugins/MsCrmTools.ViewLayoutReplicator/)|Saman asettelun käyttöönotto useissa saman kohteen näkymissä yhtä aikaa|
|[Verkkoresurssien hallinta](https://www.xrmtoolbox.com/plugins/MsCrmTools.WebResourcesManager/)|Hallitse verkkoresursseja helposti|

Toinen työkalu, joka ei ole saatavilla XrmToolBoxin kautta on Jason Lattimerin [CRM REST -muodostin](https://github.com/jlattimer/CRMRESTBuilder). Työkalu luo JavaScript-koodi verkon ohjelmointirajapinnan kanssa käytettäväksi.

> [!NOTE]
> Microsoft ei tue yhteisön luomia työkaluja. Jos sinulla on kysymyksiä tai ongelmia yhteisötyökalujen kanssa, ota yhteyttä työkalun julkaisijaan.





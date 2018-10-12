---
title: Verkkoresurssien käyttö | Microsoft Docs
description: Lue lisätietoja siitä, miten kehittäjät käyttävät verkkoresursseja malliin perustuvissa sovelluksissa.
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
ms.openlocfilehash: 88e51e4547732bed2d3e7ef3290bc8d933afded3
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849907"
---
# <a name="use-web-resources"></a>Verkkoresurssien käyttö

Jokaisessa Common Data Service for Apps -esiintymässä on virtuaalikansio nimeltä `webresources`, jossa voit pyytää HTML-, JS-, CSS- ja kuvatiedostoja sekä muita tiedostoja nimeltä ja käyttää niitä selaimessasi. Voit ladata näitä tiedostoja sovelluksella tai lisätä ne ohjelmallisesti [WebResource Entity](../common-data-service/reference/entities/webresource.md) -tietueina. [XrmToolBox WebResources Manager](https://www.xrmtoolbox.com/plugins/MsCrmTools.WebResourcesManager/) on yhteisön työkalu, joka helpottaa näiden tietueiden käsittelyä.

Nämä tiedostot voivat viitata toisiinsa suhteellisilla polkunimillä sisällössään. Mahdollisuus ladata tiedostoja ja pyytää niitä nimeltä tarjoaa kaiken tarvittavan, jotta voit tehdä verkkosovelluksia tiedostoilla, jotka käsitellään selaimesi todennetussa istunnossa. Kun käytät vain asiakaspuolen koodia ja AJAX-tekniikoita, voit luoda monipuolisia sovelluksia, jotka suoritetaan selainikkunassa tai IFrame-kehyksessä lomakkeessa tai koontinäytössä. 

Yleensä käytät JavaScript-verkkoresursseja, joilla lisäät tapahtumakäsittelijän funktiot lomakkeisiin ja komentoihin.

Lisätietoja:
- [Asiakkaan komentosarjat ja malliin perustuvat sovellukset](client-scripting.md)
- [Dynamics 365 Customer Engagementin kehittäjän opas: verkkoresurssit](/dynamics365/customer-engagement/developer/web-resources)

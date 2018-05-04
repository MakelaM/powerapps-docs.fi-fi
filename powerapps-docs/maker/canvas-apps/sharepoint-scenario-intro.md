---
title: Integroi PowerApps, Microsoft Flow ja Power BI SharePoint Onlinen kanssa (johdanto) | Microsoft Docs
description: 'Tämän sarjan opetusohjelmissa tutkitaan, miten laaditaan yksinkertainen projektinhallintaohjelma, joka perustuu SharePoint-luetteloihin ja kolmeen tärkeään tekniikkaan, jotka voidaan integroida SharePoint Onlinen kanssa: PowerApps, Microsoft Flow ja Power BI.'
services: ''
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/19/2017
ms.author: mblythe
ms.openlocfilehash: 7b67e3e2346e734b648f51d1099ea2d2278c0b18
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="integrate-powerapps-microsoft-flow-and-power-bi-with-sharepoint-online"></a>Integroi PowerApps, Microsoft Flow ja Power BI SharePoint Onlinen kanssa
Onko käytössäsi SharePoint Online ja haluako automatisoida ja virtaviivaistaa liiketoimintaprosessejasi paremmin? Oletko työskennellyt PowerAppsin, Microsoft Flow'n tai Power BI:n kanssa, muttet ole varma, miten näitä käytetään SharePoint Onlinen kanssa? Olet tullut oikeaan paikkaan! Tämän sarjan opetusohjelmissa tutkitaan, miten laaditaan yksinkertainen projektinhallintaohjelma, joka perustuu SharePoint-luetteloihin ja kolmeen tärkeään tekniikkaan, jotka voidaan integroida SharePoint Onlinen kanssa: PowerApps, Microsoft Flow ja Power BI. Nämä tekniikat toimivat yhdessä, mikä helpottaa liiketoimintasi *mittaamista*, *toimimista* tulosten perusteella ja työnkulkujen *automatisoimista*. Kun olet käynyt läpi tämän sarjan, käytössäsi on hieno skenaario, kuten tämä:

![Valmiin skenaarion kaavio](./media/sharepoint-scenario-intro/composite-with-background.png)

## <a name="business-scenario"></a>Liiketoimintaskenaario
Tässä opetusohjelmasarjassa yrityksellä Contoso on SharePoint Online -sivusto, jolla he hallitsevat projektien elinkaarta pyynnöistä hyväksyntään, kehitykseen ja loppuarviointiin asti. *Projektin pyytäjä*, kuten osaston johtaja, pyytää IT-projektia lisäämällä kohteen SharePoint-luetteloon. *Projektin hyväksyjä*, kuten IT-päällikkö, arvioi projektin ja hyväksyy tai hylkää sen tämän jälkeen. Jos se hyväksytään, projektille määrätään *projektipäällikkö* ja toiseen luetteloon lisätään tietoja saman sovelluksen kautta. *Liiketoiminta-analyytikko* arvioi meneillään olevat ja valmiit projektit käyttämällä Power BI -raporttia, joka on upotettu SharePointiin.  Microsoft Flow'ta käytetään hyväksyntäsähköpostien lähettämiseen ja Power BI -hälytyksiin reagoimiseen.

## <a name="getting-started-quickly"></a>Nopeasti alkuun pääseminen
Tässä opetusohjelmasarjassa esittämämme skenaario on yksinkertainen verrattuna täysimittaiseen projektihallinta- ja analyysisovellukseen, mutta kestää silti jonkun aikaa. Jos haluat vain nopean esittelyn PowerAppsin, Microsoft Flow'n ja Power BI:n käytöstä SharePointin kanssa, tutustu seuraaviin artikkeleihin:

* **PowerApps**: [Sovelluksen luominen SharePointin sisältä PowerAppsilla ](generate-app-from-sharepoint-list-interface.md) ja [Luo sovellus SharePoint-luettelon tiedonhallintaa varten](app-from-sharepoint.md)
* **Microsoft Flow**: [Odota hyväksyntää Microsoft Flow'ssa](https://docs.microsoft.com/flow/wait-for-approvals)
* **Power BI**: [Upota raportin verkko-osa SharePoint Onlinessä](https://docs.microsoft.com/power-bi/service-embed-report-spo)

Kun olet valmis, toivomme, että palaat takaisin tutustumaan tähän kokonaiseen skenaarioon.

Tässäkin skenaariossa voit keskittyä itseäsi kiinnostaviin tehtäviin ja tehdä tehtävät loppuun ajan salliessa. Kun olet määrittänyt SharePoint-luettelot tehtävässä 1, voit sen jälkeen tehdä tehtävät 2–5 vapaavalintaisessa järjestyksessä. Tämän jälkeen tehtävät 6–8 ovat peräkkäisiä. Lopuksi olemme liittäneet mukaan kaksi valmista sovellusta ja Power BI Desktop -raportin osana tämän skenaarion [ladattavaa pakettia](https://aka.ms/o4ia0f). Voit tutustua näihin ja oppia esimerkkien avulla vaikka et kävisikään läpi jokaisen tehtävän kaikkia vaiheita.

## <a name="prerequisites"></a>Edellytykset
Skenaarion suorittamiseen tarvitset seuraavat tilaukset ja tietokoneen työkalut. Office 365 Business Premium -tilaus sisältää PowerAppsin ja Microsoft Flow'n.

| **Tilaus tai työkalu** | **Linkki** |
| --- | --- |
| Office 365 Business Premium -tilaus |[Kokeiluversion tilaus](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1) |
| Power BI Pro -tilaus |[Kokeiluversion tilaus](https://powerbi.microsoft.com/get-started/) (napsauta **KOKEILE ILMAISEKSI**) |
| Power BI Desktop |[Ladattavissa maksutta](https://powerbi.microsoft.com/get-started/) (napsauta **LATAA ILMAISEKSI**) |

Ihannetapauksessa sinulla on kaikkien tekniikoiden perustason tuntemusta, mutta voit silti tehdä skenaarion loppuun, vaikka jotkin näistä tekniikoista olisivatkin sinulle uusia. Käytä seuraavaa sisältöä apuna päästäksesi nopeasti liikkeelle:

* [Aloita SharePointin käyttäminen](https://support.office.com/article/Get-started-with-SharePoint-909ec2f0-05c8-4e92-8ad3-3f8b0b6cf261)
* [Opastettu perehdytys PowerAppsin käyttöön](../../guided-learning/index.md)
* [Opastettu perehdytys Microsoft Flow'n käyttöön](https://docs.microsoft.com/flow/guided-learning/)
* [Opastettu perehdytys Power BI:n käyttöön](https://docs.microsoft.com/power-bi/guided-learning/)

## <a name="next-steps"></a>Seuraavat vaiheet
Tämän opetusohjelman seuraava vaihe on [SharePoint Onlinen luetteloiden](sharepoint-scenario-setup.md) määrittäminen. Niitä käytetään koko sarjan ajan.


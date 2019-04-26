---
title: PowerAppsin, Microsoft Flow'n ja Power BI:n integroiminen SharePoint Onlinen kanssa (johdanto) | Microsoft Docs
description: 'Tämän sarjan Opetusohjelmissa käsitellään miten laaditaan perustason pohjaan perustuvan sovelluksen SharePoint-luetteloihin ja kolmeen tärkeään tekniikkaan, jotka voidaan integroida SharePoint Onlinen kanssa projektinhallintaa varten: Powerappsin, Microsoft Flow ja Power BI.'
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 12/19/2017
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 812a73163047914a8f0bcc651c831ee4022fcc28
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "63319412"
---
# <a name="integrate-powerapps-microsoft-flow-and-power-bi-with-sharepoint-online"></a>PowerAppsin, Microsoft Flow'n ja Power BI:n integroiminen SharePoint Onlinen kanssa
Onko käytössäsi SharePoint Online ja haluatko automatisoida ja virtaviivaistaa liiketoimintaprosessejasi paremmin? Oletko työskennellyt PowerAppsin, Microsoft Flow'n tai Power BI:n kanssa, muttet ole varma, miten näitä käytetään SharePoint Onlinen kanssa? Olet tullut oikeaan paikkaan! Tämän sarjan Opetusohjelmissa käsitellään miten laaditaan perustason pohjaan perustuvan sovelluksen SharePoint-luetteloihin ja kolmeen tärkeään tekniikkaan, jotka voidaan integroida SharePoint Onlinen kanssa projektinhallintaa varten: Powerappsin, Microsoft Flow ja Power BI. Nämä tekniikat toimivat yhdessä, mikä helpottaa liiketoimintasi *mittaamista*, *toimimista* tulosten perusteella ja työnkulkujen *automatisoimista*. Kun olet käynyt läpi tämän sarjan, käytössäsi on hieno skenaario, kuten tämä:

![Valmiin skenaarion kaavio](./media/sharepoint-scenario-intro/composite-with-background.png)

## <a name="business-scenario"></a>Liiketoimintaskenaario
Tässä opetusohjelmasarjassa yrityksellä Contoso on SharePoint Online -sivusto, jolla he hallitsevat projektien elinkaarta pyynnöistä hyväksyntään, kehitykseen ja loppuarviointiin asti. *Projektin pyytäjä*, kuten osaston johtaja, pyytää IT-projektia lisäämällä kohteen SharePoint-luetteloon. *Projektin hyväksyjä*, kuten IT-päällikkö, arvioi projektin ja hyväksyy tai hylkää sen tämän jälkeen. Jos se hyväksytään, projektille määrätään *projektipäällikkö* ja toiseen luetteloon lisätään tietoja saman sovelluksen kautta. *Liiketoiminta-analyytikko* arvioi meneillään olevat ja valmiit projektit käyttämällä Power BI -raporttia, joka on upotettu SharePointiin.  Microsoft Flow'ta käytetään hyväksyntäsähköpostien lähettämiseen ja Power BI -hälytyksiin reagoimiseen.

## <a name="getting-started-quickly"></a>Nopeasti alkuun pääseminen
Tässä opetusohjelmasarjassa esittämämme skenaario on yksinkertainen verrattuna täysimittaiseen projektihallinta- ja analyysisovellukseen, mutta kestää silti jonkun aikaa. Jos haluat vain nopean esittelyn PowerAppsin, Microsoft Flow'n ja Power BI:n käytöstä SharePointin kanssa, tutustu seuraaviin artikkeleihin:

* **Powerappsin**: [Sovelluksen luominen sisältä powerappsilla SharePoint](app-from-sharepoint.md#generate-an-app-from-within-sharepoint-online) ja [sovelluksen luominen SharePoint-luettelon tiedonhallintaa varten](app-from-sharepoint.md)
* **Microsoft Flow-**: [Odota hyväksyntää Microsoft Flow](https://docs.microsoft.com/flow/wait-for-approvals)
* **Power BI**: [Upota raportin verkko-osa SharePoint Onlinessa](https://docs.microsoft.com/power-bi/service-embed-report-spo)

Kun olet valmis, toivomme, että palaat takaisin tutustumaan tähän kokonaiseen skenaarioon.

Tässäkin skenaariossa voit keskittyä itseäsi kiinnostaviin tehtäviin ja tehdä tehtävät loppuun ajan salliessa. Kun olet määrittänyt SharePoint-luettelot tehtävässä 1, voit sen jälkeen tehdä tehtävät 2–5 vapaavalintaisessa järjestyksessä. Tämän jälkeen tehtävät 6–8 ovat peräkkäisiä. Lopuksi olemme liittäneet mukaan kaksi valmista sovellusta ja Power BI Desktop -raportin osana tämän skenaarion [ladattavaa pakettia](https://aka.ms/o4ia0f). Voit tutustua näihin ja oppia esimerkkien avulla vaikka et kävisikään läpi jokaisen tehtävän kaikkia vaiheita.

## <a name="prerequisites"></a>Edellytykset
Skenaarion suorittamiseen tarvitset seuraavat tilaukset ja tietokoneen työkalut. Office 365 Business Premium -tilaus sisältää PowerAppsin ja Microsoft Flow'n.

| **Tilaus tai työkalu** | **Linkki** |
| --- | --- |
| Office 365 Business Premium -tilaus |[Kokeiluversion tilaus](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1) |
| Power BI Pro -tilaus |[Kokeiluversion tilaus](https://powerbi.microsoft.com/get-started/) (napsauta **KOKEILE ILMAISEKSI**) |
| Power BI Desktop |[Ladattavissa maksutta](https://powerbi.microsoft.com/get-started/) (napsauta **LATAA ILMAISEKSI**) |

Ihannetapauksessa sinulla on kaikkien tekniikoiden perustason tuntemusta, mutta voit silti tehdä skenaarion loppuun, vaikka jotkin näistä tekniikoista olisivatkin sinulle uusia. Käytä seuraavaa sisältöä apuna, jotta pääset nopeasti liikkeelle:

* [Aloita SharePointin käyttäminen](https://support.office.com/article/Get-started-with-SharePoint-909ec2f0-05c8-4e92-8ad3-3f8b0b6cf261)
* [Opastettu perehdytys PowerAppsin käyttöön](../../guided-learning/index.md)
* [Opastettu perehdytys Microsoft Flow'n käyttöön](https://docs.microsoft.com/flow/guided-learning/)
* [Opastettu perehdytys Power BI:n käyttöön](https://docs.microsoft.com/power-bi/guided-learning/)

## <a name="next-steps"></a>Seuraavat vaiheet
Tämän opetusohjelman seuraava vaihe on [SharePoint Onlinen luetteloiden](sharepoint-scenario-setup.md) määrittäminen. Niitä käytetään koko sarjan ajan.


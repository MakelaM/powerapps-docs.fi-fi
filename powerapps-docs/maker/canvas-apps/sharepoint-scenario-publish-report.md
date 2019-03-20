---
title: Julkaise Power BI -projektiraportti ja luo koontinäyttö| Microsoft Docs
description: Tässä tehtävässä julkaisemme tietojoukon ja raportin Power BI -palveluun, minkä jälkeen luomme raportin pohjalta koontinäytön.
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/30/2018
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 43e95b88cdf305e7c4b768def83a6b41fa0fcae7
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799360"
---
# <a name="publish-the-power-bi-project-report-and-create-a-dashboard"></a>Power BI -projektiraportin julkaiseminen ja koontinäytön luominen
> [!NOTE]
> Tämä artikkeli on osa opetusohjelmasarjaa PowerAppsin, Microsoft Flow’n ja Power BI:n käyttämisestä SharePoint Onlinen kanssa. Varmista, että luet [sarjan esittelyn](sharepoint-scenario-intro.md), jotta saat paremman käsityksen kokonaiskuvasta, sekä aiheeseen liittyvät ladattavat tiedostot.

Tässä tehtävässä julkaisemme tietojoukon ja raportin Power BI -palveluun, minkä jälkeen luomme raportin pohjalta koontinäytön. Usein raportit sisältävät runsaasti visualisointeja ja koontinäytössä käytetään vain alijoukkoa. Tässä tapauksessa lisäämme kaikki neljä visualisointia koontinäyttöön.

## <a name="step-1-publish-the-dataset-and-report"></a>Vaihe 1: Tietojoukon ja raportin julkaiseminen
1. Napsauta tai napauta Power BI Desktopin **Aloitus**-välilehdessä **Julkaise**.
   
    ![Tietojoukon ja raportin julkaiseminen](./media/sharepoint-scenario-publish-report/06-01-01-publish.png)
2. Jos et ole vielä kirjautunut Power BI -palveluun, anna tili ja napsauta tai napauta **Kirjaudu sisään**.
   
    ![Tilille kirjautuminen](./media/sharepoint-scenario-publish-report/06-01-02-account.png)
3. Anna salasana ja napsauta tai napauta **Kirjaudu sisään**.
   
    ![Anna tilin salasana](./media/sharepoint-scenario-publish-report/06-01-03-password.png)
4. Valitse raportille kohde ja napsauta tai napauta **Valitse**. Suosittelemme julkaisemaan ryhmätyötilaan, koska se yksinkertaistaa raportin käyttöä SharePointissa. Tässä tapauksessa julkaisemme **Projektinhallinta**-ryhmätyötilaan. Jos haluat lisätietoja, katso [Yhteistyön tekeminen Power BI -sovelluksen työtilassa](https://docs.microsoft.com/power-bi/service-collaborate-power-bi-workspace).
   
    ![Kohdetyötila](./media/sharepoint-scenario-publish-report/06-01-04-workspace.png)
5. Kun julkaiseminen on valmis, napsauta tai napauta **Avaa ”project-analysis.pbx” Power BI:ssä**.
   
    ![Julkaiseminen onnistui](./media/sharepoint-scenario-publish-report/06-01-05-open-report.png)
6. Power BI -palvelu lataa raportin selaimeen. Jos vasen siirtymisruutu ei ole laajennettuna, laajenna se napsauttamalla tai napauttamalla ylävasemmalla olevaa valikkoa **(a)**.
   
    ![Raportti Power BI -palvelussa](./media/sharepoint-scenario-publish-report/06-01-06-service-report.png)
   
    Kuten kuvasta nähdään, Power BI Desktop latasi julkaisun yhteydessä palvelimeen tietojoukon **(d)** ja raportin **(c)**. Koontinäyttöjä luodaan palvelussa, ei Power BI Desktopissa. Tässä työtilassa ei ole vielä koontinäyttöjä **(b)**. Luomme sellaisen pian.

## <a name="step-2-configure-credentials-for-refresh"></a>Vaihe 2: Tunnistetietojen määrittäminen päivittämistä varten
1. Napsauta palvelun oikeassa yläkulmassa olevaa ![hammaspyöräkuvaketta](./media/sharepoint-scenario-publish-report/icon-gear.png) ja napsauta tai napauta **Asetukset**.
2. Napsauta tai napauta **Tietojoukot**, sitten **project-analysis**.
   
    ![project-analysis-tietojoukko](./media/sharepoint-scenario-publish-report/06-01-07-dataset.png)
3. Laajenna **Tietojoukon tunnistetiedot** ja napsauta tai napauta **Muokkaa tunnistetietoja**.
   
    ![Muokkaa tietolähteen tunnistetietoja](./media/sharepoint-scenario-publish-report/06-01-08-credentials.png)
4. Valitse todennusmenetelmäksi **OAuth2** ja napsauta tai napauta **Kirjaudu sisään**.
   
    ![Kirjaudu sisään SharePointiin](./media/sharepoint-scenario-publish-report/06-01-09-sign-in.png)
5. Valitse tili tai kirjaudu tilille, jolla on käyttöoikeus SharePoint-luetteloihin.
   
    ![Kirjautuneena sisään Office 365 -palveluun](./media/sharepoint-scenario-publish-report/06-01-10-account.png)
   
    Kun prosessi on valmis, saat palvelussa seuraavan viestin.
   
    ![Tietolähde päivitettiin](./media/sharepoint-scenario-publish-report/06-01-11-updated.png)

## <a name="step-3-create-a-dashboard"></a>Vaihe 3: Koontinäytön luominen

1. Voit palata raporttiisi napsauttamalla tai napauttamalla kohdetta **project-analysis** kohdassa **RAPORTIT**.

1. Napsauta tai napauta ylävasemmalla olevaa kaaviota ja valitse ![Kiinnitä-kuvake](./media/sharepoint-scenario-publish-report/icon-pin.png).
   
    ![Kiinnitä kaavio](./media/sharepoint-scenario-publish-report/06-01-12-pin-projected.png)
2. Anna nimi koontinäytölle, johon haluat kiinnittää kohteen, ja napsauta tai napauta **Kiinnitä**.
   
    ![Kiinnitä kaavio uuteen koontinäyttöön](./media/sharepoint-scenario-publish-report/06-01-13-pin-new.png)
3. Napsauta tai napauta yläoikealla olevaa kaaviota ja valitse ![Kiinnitä-kuvake](./media/sharepoint-scenario-publish-report/icon-pin.png).
   
    ![Kiinnitä kaavio](./media/sharepoint-scenario-publish-report/06-01-14-pin-variance.png)
4. Valitse olemassa oleva koontinäyttö ja napsauta tai napauta **Kiinnitä**.
   
    ![Kiinnitä kaavio olemassa olevaan koontinäyttöön](./media/sharepoint-scenario-publish-report/06-01-15-pin-existing.png)

5. Toista kiinnitysprosessi kahdelle muulle visualisoinnille.

6. Napsauta tai napauta koontinäytön nimeä vasemmassa siirtymisruudussa.
   
    ![Uusi koontinäyttö sivuston siirtymistoiminnossa](./media/sharepoint-scenario-publish-report/06-01-16-dashboard-menu.png)

7. Tarkastele koontinäyttöä. Jos napsautat ruutua, palaat takaisin raporttiin.
   
    ![Valmis koontinäyttö](./media/sharepoint-scenario-publish-report/06-01-17-dashboard-completed.png)

Tässä oli suurin osa Power BI:ssä tehtävästä työstä. Jos tämä oli ensimmäinen kokemuksesi raporttien ja koontinäyttöjen luomisesta, onnittelut! Jos olet kokeneempi käyttäjä, toivottavasti tehtävään ei kulunut liikaa aikaa. Seuraavaksi lisäämme ilmoitukset, jotta tiedämme, milloin koontinäyttö tarvitsee toimenpiteitä.

## <a name="next-steps"></a>Seuraavat vaiheet
Tämän opetusohjelmasarjan seuraava vaihe on [Tietoilmoitusten lisääminen Power BI -projektiraporttiin](sharepoint-scenario-alerts-flow.md).


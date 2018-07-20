---
title: Power BI -projektiraportin upottaminen SharePoint Onlineen | Microsoft Docs
description: Tässä tehtävässä upotamme Power BI -raportin samaan SharePoint Online -sivustoon, joka isännöi kahta luetteloamme.
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/30/2018
ms.author: mblythe
ms.openlocfilehash: 9e97020ae14ce6da9674e64559b42f98e45269f4
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023225"
---
# <a name="embed-the-power-bi-project-report-in-sharepoint-online"></a>Power BI -projektiraportin upottaminen SharePoint Onlineen
> [!NOTE]
> Tämä artikkeli on osa opetusohjelmasarjaa, joka käsittelee PowerAppsin, Microsoft Flow’n ja Power BI:n käyttämistä SharePoint Onlinen kanssa. Varmista, että luet [sarjan esittelyn](sharepoint-scenario-intro.md), jotta saat paremman käsityksen kokonaiskuvasta. Lue myös aiheeseen liittyvät ladattavat tiedostot.

Upotamme Power BI -raportin samaan SharePoint Online -sivustoon, joka isännöi kahta luetteloamme. Power BI tukee useita eri upottamistapoja, mukaan lukien integroinnin suoraan SharePoint-sivuihin verkko- ja mobiilinäkymiä varten.

Tämäntyyppisessä upottamisessa Power BI upottaa raportin WWW-osana, antaa asianmukaiset käyttöoikeudet käyttäjille ja sallii siirtymisen upotetusta raportista powerbi.com-raporttiin napsauttamalla. Luomme ensin liittymislinkin Power BI:ssä ja käytämme sitten tätä linkkiä sivulla, jonka luomme. Katso lisätietoja upottamisesta kohdasta [Upottaminen raportti-WWW-osan kanssa SharePoint Onlinessa](https://docs.microsoft.com/power-bi/service-embed-report-spo).

## <a name="step-1-generate-an-embed-link"></a>Vaihe 1: luo liittymislinkki
1. Kirjaudu Power BI:hin ja napsauta tai napauta sitten vasemmanpuoleisessa siirtymisruudussa raportin nimeä.
   
    ![Siirry raporttiin](./media/sharepoint-scenario-embed-report/08-01-01-reports.png)
2. Napsauta tai napauta **Tiedosto** ja sitten **Upota SharePoint Onlinessa**.
   
    ![Upota SharePoint Onlinessa](./media/sharepoint-scenario-embed-report/08-01-02-embed-spo.png)
3. Kopioi liittymislinkki valintaikkunasta tiedostoon ja napsauta tai napauta sitten **Sulje**. Käytämme linkkiä luotuamme SharePoint-sivun.
   
    ![Upota linkki SharePointiin](./media/sharepoint-scenario-embed-report/08-01-03-embed-url.png)

## <a name="step-2-embed-the-report"></a>Vaihe 2: upota raportti
1. Kirjaudu SharePointiin ja napsauta tai napauta sitten **Sivuston sisältö**.
   
    ![SharePoint-sivuston sisältö](./media/sharepoint-scenario-embed-report/08-01-04-site-contents.png)
2. Voit vain lisätä raportin työryhmän kotisivulle, mutta näytämme myös, miten sille luodaan erillinen sivu. Napsauta tai napauta **Uusi** ja sitten **Sivu**.
   
    ![Uusi SharePoint-sivu](./media/sharepoint-scenario-embed-report/08-01-05-new-page.png)
3. Anna sivulle nimi, kuten Projektianalyysi.
4. Napsauta tai napauta ![plus-kuvaketta](./media/sharepoint-scenario-embed-report/icon-plus.png) ja sitten **Power BI**.
   
    ![Lisää Power BI -sivuosa](./media/sharepoint-scenario-embed-report/08-01-06-add-page-part.png)
5. Napsauta tai napauta **Lisää raportti**.
   
    ![Lisää raportti](./media/sharepoint-scenario-embed-report/08-01-07-add-report.png)
6. Kopioi oikeanpuoleisessa ruudussa liitetty URL-osoite **Power BI -raporttilinkin** ruutuun. Määritä kohtien **Näytä suodatinruutu** ja **Näytä siirtymisruutu** asetukseksi **Käytössä**.
   
    ![Raportin asetukset](./media/sharepoint-scenario-embed-report/08-01-08-report-settings.png)
7. Raportti on nyt upotettu sivulle. Kun napsautat **Julkaise**, se tulee saataville kaikille, joilla on käyttöoikeus sen pohjana olevaan raporttiin.
   
    ![Raportin upottaminen on valmis](./media/sharepoint-scenario-embed-report/08-01-09-report-complete.png)

## <a name="step-3-grant-access-to-the-report"></a>Vaihe 3: myönnä käyttöoikeus raporttiin.
Jos käytössäsi on Office 365 -ryhmiä, kuten on suositeltavaa, varmista, että käyttäjät, jotka tarvitsevat käyttöoikeuden, kuuluvat ryhmätyötilaan Power BI -palvelussa. Näin voit varmistaa, että käyttäjät voivat tarkastella ryhmän sisältöä. Jos haluat lisätietoja, katso [Yhteistyön tekeminen Power BI -sovelluksen työtilassa](https://docs.microsoft.com/power-bi/service-collaborate-power-bi-workspace).

Tähän päättyy tehtävä Power BI:ssä tämän skenaarion osalta. Aloitimme hakemalla tietoja SharePoint-luetteloista Power BI:hin ja olemme päätyneet Power BI -raportin upottamiseen takaisin SharePointiin.

## <a name="next-steps"></a>Seuraavat vaiheet
Tämän opetusohjelmasarjan seuraava vaihe on [käydä alusta loppuun läpi työnkulku, jonka loimme](sharepoint-scenario-summary.md).


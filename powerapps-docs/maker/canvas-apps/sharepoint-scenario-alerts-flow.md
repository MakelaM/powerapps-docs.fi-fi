---
title: Määritä tietoilmoituksia Power BI -koontinäyttöön | Microsoft Docs
description: Tässä tehtävässä lisäämme Power BI:hin ilmoituksen, joka hälyttää, jos odottavien projektien hyväksyminen kestää liian kauan, ja työnkulun, joka reagoi ilmoituksen tapahtuessa.
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
ms.date: 06/12/2017
ms.author: mblythe
ms.openlocfilehash: 91d1fc6872992823aaa3c5c7baa9f36efd2fc99f
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="set-up-data-alerts-for-the-power-bi-dashboard"></a>Määritä tietoilmoituksia Power BI -koontinäyttöön
> [!NOTE]
> Tämä artikkeli on osa opetusohjelmasarjaa PowerAppsin, Microsoft Flow’n ja Power BI:n käyttämisestä SharePoint Onlinen kanssa. Varmista, että luet [sarjan esittelyn](sharepoint-scenario-intro.md), jotta saat paremman käsityksen kokonaiskuvasta, sekä aiheeseen liittyvät ladattavat tiedostot.

Tässä tehtävässä lisäämme Power BI:hin ilmoituksen, joka hälyttää, jos odottavien projektien hyväksyminen kestää liian kauan, ja työnkulun, joka reagoi ilmoituksen tapahtuessa. Katso lisätietoja ilmoituksista kohdasta [Tietoilmoitukset Power BI -palvelussa](https://docs.microsoft.com/power-bi/service-set-data-alerts).

## <a name="step-1-create-an-alert"></a>Vaihe 1: Luo ilmoitus
1. Avaa viime tehtävässä luomasi koontinäyttö Power BI -palvelussa.
2. Napsauta tai napauta yksinumeroisen kortin kolmea pistettä (**. . .**).
   
    ![Päivien enimmäismäärä hyväksynnän odottamiselle -kortti](./media/sharepoint-scenario-alerts-flow/07-01-01-tile-ellipsis.png)
3. Napsauta tai napauta ![Kellokuvake](./media/sharepoint-scenario-alerts-flow/icon-bell.png).
   
    ![Ruutuvalikko](./media/sharepoint-scenario-alerts-flow/07-01-02-tile-bell.png)
4. Napsauta tai napauta oikeassa ruudussa **Lisää ilmoitussääntö**.
   
    ![Lisää ilmoitussääntö](./media/sharepoint-scenario-alerts-flow/07-01-03-add-alert.png)
5. Katso ilmoituksille käytettävissä olevia vaihtoehtoja, kuten kuinka usein ilmoituksen on käynnistyttävä. Lisää arvo 25 kohtaan **Raja-arvo** ja napsauta tai napauta sitten **Tallenna ja sulje**.
   
    ![Määritä ilmoituksen raja-arvo ja tallenna](./media/sharepoint-scenario-alerts-flow/07-01-04-save-alert.png)

Ilmoitus ei käynnisty juuri nyt, vaikka 56 on suurempi kuin raja-arvo 25. Se käynnistyy, kun tiedot päivitetään, mikä tapahtuu, kun [suoritamme skenaarion alusta loppuun](sharepoint-scenario-summary.md).

Kun ilmoitukset käynnistyvät, Power BI lähettää sähköpostiviestin ilmoituksen tekijälle. Seuraavassa vaiheessa selvitämme, miten Microsoft Flow’lla voidaan lähettää muita viestejä.

## <a name="step-2-create-a-flow-that-responds-to-the-alert"></a>Vaihe 2: Luo työnkulku, joka reagoi ilmoitukseen
1. Kirjaudu osoitteeseen flow.microsoft.com ja napsauta tai napauta kohtaa **Palvelut** ja sitten **Power BI**.
   
    ![Power BI Microsoft Flow’ssa](./media/sharepoint-scenario-alerts-flow/07-01-05-power-bi.png)
2. Napsauta tai napauta **Lähetä sähköpostiviesti mille tahansa kohderyhmälle, kun Power BI -tietoilmoitus käynnistetään**.
   
    ![Lähetä sähköpostiviesti, kun Power BI -tietoilmoitus käynnistetään](./media/sharepoint-scenario-alerts-flow/07-01-06-alert-flow.png)
3. Napsauta tai napauta **Käytä tätä mallia**.
4. Jos et ole vielä kirjautunut, kirjaudu sisään Outlookiin ja Power BI:hin ja napsauta tai napauta sitten **Jatka**.
   
    ![Kirjaudu sisään ja jatka](./media/sharepoint-scenario-alerts-flow/07-01-08-continue.png)
5. Valitse avattavasta **Hälytyksen tunnus** -luettelosta **Päivien enimmäismäärä hyväksynnän odottamiselle -ilmoitus**.
   
    ![Määritä ilmoituksen käynnistin](./media/sharepoint-scenario-alerts-flow/07-01-09-choose-alert.png)
6. Anna kelvollinen sähköpostiosoite **Vastaanottaja**-kenttään.
   
    ![Määritä, kenelle sähköposti lähetetään](./media/sharepoint-scenario-alerts-flow/07-01-10-choose-email.png)
7. Napsauta tai napauta **Muokkaa**, niin näet muut kentät, joita voit päivittää.
   
    ![Muokkaa ilmoituksen sähköpostiviestiä](./media/sharepoint-scenario-alerts-flow/07-01-11-email-full.png)
8. Napsauta näytön oikeassa yläreunassa **Luo työnkulku** ja sitten **Valmis**.
   
    ![Valmis-painike](./media/sharepoint-scenario-alerts-flow/07-01-12-done.png)

Näet tämän työnkulun, kun [suoritamme skenaarion alusta loppuun](sharepoint-scenario-summary.md). Siirrymme nyt tämän skenaarion viimeiseen tehtävään, Power BI -raportin upottamiseen SharePointiin.

## <a name="next-steps"></a>Seuraavat vaiheet
Tämän opetusohjelmasarjan seuraava vaihe on [Power BI -projektiraportin upottaminen SharePoint Onlinessa](sharepoint-scenario-embed-report.md).


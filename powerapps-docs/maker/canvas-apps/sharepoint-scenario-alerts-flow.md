---
title: Tietoilmoitusten määrittäminen Power BI -koontinäyttöön | Microsoft Docs
description: Tässä tehtävässä lisäämme Power BI:hin ilmoituksen, joka hälyttää, jos odottavien projektien hyväksyminen kestää liian kauan, ja työnkulun, joka reagoi ilmoituksen tapahtuessa.
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/12/2017
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 89c22bec8972c0d58c559a09d4e9f0a8a8e3b7f5
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799084"
---
# <a name="set-up-data-alerts-for-the-power-bi-dashboard"></a>Tietoilmoitusten määrittäminen Power BI -koontinäyttöön
> [!NOTE]
> Tämä artikkeli on osa opetusohjelmasarjaa PowerAppsin, Microsoft Flow’n ja Power BI:n käyttämisestä SharePoint Onlinen kanssa. Varmista, että luet [sarjan esittelyn](sharepoint-scenario-intro.md), jotta saat paremman käsityksen kokonaiskuvasta, sekä aiheeseen liittyvät ladattavat tiedostot.

Tässä tehtävässä lisäämme Power BI:hin ilmoituksen, joka hälyttää, jos odottavien projektien hyväksyminen kestää liian kauan, ja työnkulun, joka reagoi ilmoituksen tapahtuessa. Katso lisätietoja ilmoituksista kohdasta [Tietoilmoitukset Power BI -palvelussa](https://docs.microsoft.com/power-bi/service-set-data-alerts).

## <a name="step-1-create-an-alert"></a>Vaihe 1: Luo hälytys
1. Avaa edellisessä tehtävässä luomasi koontinäyttö Power BI -palvelussa.
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


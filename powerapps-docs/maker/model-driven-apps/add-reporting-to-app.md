---
title: Raportoinnin lisääminen mallipohjaiseen sovellukseesi
ms.custom: ''
ms.date: 06/24/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: b4098c96-bce1-4f57-804f-8694e6254e81
caps.latest.revision: 15
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="add-reporting-to-your-model-driven-app"></a>Raportoinnin lisääminen mallipohjaiseen sovellukseesi

PowerApps-sovellukset voivat sisältää raportteja, joissa on hyödyllisiä liiketoimintatietoja käyttäjälle. Nämä raportit perustuvat SQL Server Reporting Servicesille ja sisältävät samat ominaisuudet, jotka ovat käytettävissä tyypillisissä SQL Server Reporting Services -raporteissa.

> [!div class="mx-imgBorder"] 
> ![](media/progress-against-goals-report.png "Edistyminen tavoitteisiin verrattuna -perusraportti")

Järjestelmäraportit ovat kaikkien käyttäjien käytettävissä. Käyttäjät voivat luoda tai muuten omistaa raportit tiettyjen työtoverien tai ryhmien kanssa tai tuoda ne kaikkien organisaatioon kuuluvien henkilöiden suoritettavaksi. Näissä raporteissa käytetään FetchXML-kyselyjä, jotka ovat Common Data Service- ja Dynamics 365 for Customer Engagement -sovellusten omistamia, ja noutavat tietoja raportin luomista varten. PowerApps-sovelluksessa luodut raportit ovat Fetch-pohjaisia raportteja.

> [!NOTE]
> Raporttiominaisuudet eivät toimi mobiililaitteissa, kuten tableteissa ja puhelimissa, piirto- tai mallipohjaisia sovelluksia käsittelevien sovellusten kanssa. 

Raportteja voidaan rakentaa jommallakummalla seuraavista tavoista.

- Mallista ohjatun sovelluksen avulla ohjatulla raportin luontitoiminnolla. Lisätietoja: [Raportin luominen tai muokkaaminen ohjatun raportin luontitoiminnon avulla](/dynamics365/customer-engagement/basics/create-edit-copy-report-wizard) 
<!-- From a model-driven app using an advanced find query. To do this, you build an advanced find query and then select **Download as FetchXML**. Next, from the reports area select **New**, for **Report Type** select **Existing File**, select **Choose File** open the xml file, fill in the required fields, and save the report. More information: [Add a report](/dynamics365/customer-engagement/basics/add-existing-report) -->
- Mukautetun raportin luominen SQL Server Data Tools -järjestelmän Report Authoring Extension -ohjelmalla. Lisätietoja: [Raportointi- ja analysointiopas](/dynamics365/customer-engagement/analytics/reporting-analytics-with-dynamics-365)


## <a name="add-reporting-to-a-unified-interface-app"></a>Raportoinnin lisääminen Unified Interface -sovellukseen
Voit lisätä Fetch-kielipohjaisia raportointitoimintoja sovellukseesi, jotta käyttäjät voivat suorittaa, jakaa, luoda ja muokata raportteja. Voit tehdä tämän lisäämällä raporttientiteetin sovelluksesi sivustokarttaan. 

1. Kirjaudu [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen ja avaa aiemmin luotu sovellus muokkausta varten. 
2. Valitse sovelluksen suunnittelu ohjelmassa ![Kynäkuvake sivustokartan muokkaamiseen](media/ccf-pencil-icon.png) **Sivukartta**-kohdan vieressä. 
3. Valitse sivustokartan suunnitteluohjelmassa **Lisää** ja valitse sitten **Alue**. 
4. Kirjoita **Otsikko**-ruutuun alueen otsikon nimi, esimerkiksi *Raportit*. 
5. Valitse edellisessä vaiheessa nimetty alue, valitse **Lisää**, valitse **Ryhmä** ja kirjoita sitten ryhmän **Nimi**-ruutuun ryhmän otsikon nimi, esimerkiksi *Raportit*. 
6. Valitse edellisessä vaiheessa nimetty ryhmä, valitse **Lisää**, valitse **Alialue** ja lisää sitten seuraavat ominaisuudet: 

   - **Tyyppi**. Valitse **Entiteetti**.
   - **Entiteetti**. Valitse entiteettiluettelosta **Raportti**-entiteetti.  
   - **Otsikko**. Kirjoita kuvaava otsikko, kuten *Raportit*.

      ![Lisää raporttientiteetti sivustokarttaan](media/report-entity-sitemap.png)

7. Valitse **Tallenna ja sulje**, kun haluat palata sovelluksen suunnitteluohjelman. 


8. Valitse sovelluksen suunnitteluohjelmassa ensin **Tallenna** ja sitten **Julkaise**.


Nyt sovellus näyttää **Raportit**-alueen, jossa käyttäjät voivat tarkastella, suorittaa, delegoida, jakaa ja muokata raportteja, joihin heillä on käyttöoikeus, sekä luoda uusia raportteja ohjatulla raportin luontitoiminnolla. 

> [!div class="mx-imgBorder"] 
> ![](media/report-feature-in-app.png "Raportoi näkymä")

### <a name="see-also"></a>Katso myös
[Raportin suorittaminen](/dynamics365/customer-engagement/basics/run-report)

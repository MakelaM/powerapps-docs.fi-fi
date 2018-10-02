---
title: Mallipohjaisen sovelluksen järjestelmäkaavion luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Lisätietoja kaavion luomisesta tai muokkaamisesta
ms.custom: ''
ms.date: 05/23/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: e02d58f7-6b1c-4a51-b801-a4d9f24729c5
caps.latest.revision: 29
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-model-driven-app-system-chart"></a>Mallipohjaisen sovelluksen järjestelmäkaavion luominen

Tässä ohjeaiheessa on tietoja järjestelmäkaavion luomisesta. Järjestelmäkaaviot ovat organisaation omistamia kaavioita. Tämän vuoksi niitä voivat käyttää kaikki, joilla on sovelluksen tietojen lukuoikeus. Järjestelmäkaavioita ei voi delegoida tai jakaa tietyille sovelluksen käyttäjille.  
  
1. Valitse [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Mallipohjainen** (siirtymisruudun alaosassa vasemmalla).  

     ![Mallipohjainen suunnittelutila](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2. Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Kaaviot**-välilehti.  
  
3.  Valitse työkaluriviltä **Lisää kaavio**.  
  
4.  Jos tämä raportti sisältää kaavion, määritä kaavion tyyppi ja tietojen näyttötapa.  
  
    -   Anna kaavion nimi, esimerkiksi *Henkilöstömäärä asiakkaiden mukaan*.  
  
    -   Avattavissa **Valitse kenttä** -luetteloissa: 
        - Valitse **Valitse kenttä** **Sarja** -kohdan akselin avattavasta luettelosta kenttä, esimerkiksi **Henkilöstömäärä**.  
        - Valitse **Valitse kenttä** **Luokka** -kohdan akselin avattavasta luettelosta kenttä, esimerkiksi **Asiakkaan nimi**.
  
    -   Lisää kuvaus ja määritä kaavion tarkoitus, esimerkiksi *Tässä sarakkeen kaaviossa näkyy henkilöstömäärä asiakkaisen nimien mukaan*. 

    > [!div class="mx-imgBorder"] 
    > ![Esimerkkikaavio](media/sample-chart.png)
  
5.  Valitse **Tallenna ja sulje**.  

## <a name="next-steps"></a>Seuraavat vaiheet  
[Koontinäyttöjen luominen tai muokkaaminen](create-edit-dashboards.md)

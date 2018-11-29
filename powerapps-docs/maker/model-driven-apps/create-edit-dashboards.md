---
title: Mallipohjaisen sovelluksen koontinäyttöjen luominen ja muokkaaminen | MicrosoftDocs
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
ms.assetid: 641885d2-4a08-41b8-b914-d9a244e4d5b1
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-model-driven-app-dashboards"></a>Mallipohjaisen sovelluksen koontinäyttöjen luominen ja muokkaaminen

CRM:ssä on kaksi koontinäyttötyyppiä: käyttäjän koontinäytöt ja järjestelmän koontinäytöt. Sovelluksen käyttäjä voi luoda koontinäytön niin, että se näkyy vain sovellusalueilla, joiden käyttöoikeudet käyttäjillä on. Järjestelmänvalvoja tai mukauttaja voi luoda tai mukauttaa järjestelmän koontinäyttöjä, jotka näkyvät kaikille sovelluksen käyttäjille. Käyttäjä voi määrittää oman koontinäyttönsä oletuskoontinäytöksi ja korvata järjestelmän koontinäytön. Tässä ohjeaiheessa keskitytään järjestelmän koontinäyttöihin.  
  
<a name="BKMK_createdashboard"></a>   
## <a name="create-a-new-dashboard"></a>Luo uusi koontinäyttö  
  
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.

    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment).   
  
2. Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten entiteetti, johon haluat koontinäytön perustuvan, esimerkiksi **Asiakas**-entiteetti. Valitse lopuksi **Koontinäytöt**-välilehti. 

3. Valitse työkaluriviltä **Lisää koontinäyttö** ja valitse sitten asettelu, jossa on 2, 3 tai 4 saraketta.  
  
4.  Syötä **Koontinäyttö: Uusi** -valintaikkunaan koontinäytön nimi.  
  
5.  Valitse jokin osan alue ja valitse sitten kaaviolle tai luettelolle kuvake.  
  
     Koontinäytössä voi olla enintään kuusi osaa.  
  
6.  Voit lisätä esimerkiksi kaavion valitsemalla **Lisää osa** -valintaikkunassa **tietuetyypin**, **näkymän** ja **kaavion** arvo. Lisää sitten kaavio koontinäyttöön valitsemalla **Lisää**.  
  
7.  Kun olet lisännyt osat koontinäyttöön, valitse **Tallenna** ja valitse sitten **Julkaise**.  
  
<a name="BKMK_editdashboard"></a>   
## <a name="edit-an-existing-dashboard"></a>Aiemmin luodun koontinäytön muokkaaminen  
  
1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.

    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment).    
  
2. Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten entiteetti, johon haluat koontinäytön perustuvan, esimerkiksi **Asiakas**-entiteetti. Valitse lopuksi **Koontinäytöt**-välilehti.  

3. Avaa koontinäyttö, valitse jokin osan alue ja valitse sitten työkaluriviltä **Muokkaa osaa**.  
  
4.  **Määritä ominaisuudet** -valintaikkunassa voit muuttaa kaaviota tai luetteloa. Voit esimerkiksi muuttaa entiteettiä tai oletusnäkymää, lisätä kaavion valitsimen tai määrittää koontinäytön käytettäväksi mobiilisovelluksissa. Kun olet valmis, valitse **Määritä**.  
  
     Lisätietoja koontinäytön osan ominaisuuksien määrittämisestä on kohdassa [Koontinäytön kaavion tai luettelon ominaisuuksien määrittäminen](set-properties-chart-list-included-dashboard.md).  
  
4.  Tallenna ja julkaise muutokset, kun ne ovat valmiit.  
  
 Voit suorittaa järjestelmän koontinäytöille myös seuraavia tehtäviä:  
  
    -   Luettelon tai kaavion poistaminen koontinäytöstä  
  
    -   Luettelon tai kaavion lisääminen koontinäyttöön  
  
    -   Oletuskoontinäytön määrittäminen  
  
    -   Koontinäyttöjen näyttäminen vain tietyille rooleille käyttöoikeusroolien avulla    
  
## <a name="next-steps"></a>Seuraavat vaiheet  
[Koontinäyttöön sisältyvän kaavion tai luettelon ominaisuuksien määrittäminen](set-properties-chart-list-included-dashboard.md)

---
title: Mallipohjaisen sovelluksen näkymän luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Lisätietoja näkymän luomisesta tai muokkaamisesta
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: bd1d393d-16ea-40ac-8136-26643c37dd2a
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-a-model-driven-app-view"></a>Mallipohjaisen sovelluksen näkymän luominen tai muokkaaminen

<a name="BKMK_CreatingAndEditingViews"></a>   

 Tässä ohjeaiheessa luodaan uusi mukautettu julkinen näkymä. Voit myös muokata aiemmin luotua näkymää.  
  
### <a name="create-a-new-view"></a>Luo uusi näkymä  
  
1.  Valitse [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Mallipohjainen** (siirtymisruudun alaosassa vasemmalla).  

    ![Mallipohjainen suunnittelutila](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten **Asiakas**-entiteetti. Valitse lopuksi **Näkymät**-välilehti. 

3.  Valitse työkaluriviltä **Lisää näkymä**.  

4.  Anna **Näkymän ominaisuudet** -valintaruutuun **nimi**, esimerkiksi **Asiakkaat, joilla on vähintään 25 työntekijää**. Halutessasi voit antaa näkymälle **kuvauksen**. Valitse lopuksi **OK**.

    > [!div class="mx-imgBorder"] 
    > ![Näytä ominaisuudet](media/view-properties.png)
  
5.  Valitse tavallisten tehtävien oikeanpuoleisessa ruudussa **Lisää sarakkeita**. Valitse **Lisää sarakkeita** -valintaikkunassa **Työntekijöiden määrä** ja valitse sitten **OK**.  

    > [!div class="mx-imgBorder"] 
    > ![Työntekijöiden määrä -sarake](media/column-no-employees.png)
  
6. Valitse yleisten tehtävien oikeanpuoleisessa ruudussa **Muokkaa suodatusehtoja**. Valitse Muokkaa suodatusehtoja -valintaikkunassa **Työntekijöiden määrä** ja valitse sitten **On suurempi tai yhtä suuri kuin**. Anna arvoksi **25**.  

    > [!div class="mx-imgBorder"] 
    > ![Muokkaa suodatusehtoja](media/edit-filter-criteria.png)

7.  Valitse **OK**, kun haluat sulkea **Muokkaa suodatusehtoja** -valintaikkunan. Valitse näkymäeditorin **Tallenna ja sulje** -kohta.  
  
8.  Huomaa, että näkymä on nyt käytettävissä PowerAppsin **Näkymät**-välilehdessä. Sen voi lisätä sovellukseen.
  
### <a name="edit-a-view"></a>Näkymän muokkaaminen  
  
1.  Valitse PowerApps-sivuston **Näkymät**-välilehdessä **Työntekijöiden määrä** -näkymä.
  
2.  Muuta näkymän **nimeksi** **Työntekijöiden määrä, yli 25 työntekijää Arizonassa** ja valitse **OK**.  

3.  Valitse tavallisten tehtävien oikeanpuoleisessa ruudussa **Lisää sarakkeita**. Valitse **Lisää sarakkeita** -valintaikkunassa **Osoite 1: kaupunki** ja valitse sitten **OK**.  

4. Valitse yleisten tehtävien oikeanpuoleisessa ruudussa **Muokkaa suodatusehtoja**. Lisää Muokkaa suodatusehtoja ‑valintaikkunaan toinen suodatinlauseke. Valitse **Osoite 2: osavaltio/provinssi**. Valitse **On sama kuin** ja kirjoita **Arizona**. 

    > [!div class="mx-imgBorder"] 
    > ![Osoite 2: Osavaltio/provinssi](media/column-address-2-state.png)

5. Valitse **OK**, kun haluat sulkea **Muokkaa suodatusehtoja** -valintaikkunan. Valitse näkymäeditorin **Tallenna ja sulje** -kohta.  
  

## <a name="create-a-new-view-from-an-existing-view"></a>Uuden näkymän luominen aiemmin luodun näkymän pohjalta  
 Noudata näkymän muokkausohjeita. Älä kuitenkaan valitse **Tallenna ja sulje** vaan valitse **Tallenna nimellä** ja anna näkymälle uusi **nimi** ja **kuvaus**.  
 
### <a name="next-steps"></a>Seuraavat vaiheet
[Valitse ja määritä sarakkeet](choose-and-configure-columns.md)  
  
[Muokkaa suodatusehtoja](edit-filter-criteria.md)  
  
[Lajittelun määrittäminen](configure-sorting.md)  

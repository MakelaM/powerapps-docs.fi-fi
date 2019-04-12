---
title: Korttilomakkeen luominen PowerAppsilla | MicrosoftDocs
description: Tietoja korttilomakkeiden luomisesta ja käyttämisestä PowerAppsissa
keywords: ''
ms.date: 03/05/2019
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: be93b9d7-f1c2-4ee7-8d7c-0f5c34dfa5f7
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-card-form"></a>Korttilomakkeen luominen
Korttilomakkeita käytetään Unified Interface -sovellusten näkymissä. Korttilomakkeet on suunniteltu esittämään tiedot mobiililaitteisiin sopivassa tiiviissä muodossa. Esimerkiksi Omat aktiiviset asiakkaat -näkymän oletuskorttilomake määrittää kussakin asiakastietueessa näytettävät tiedot. 

> [!div class="mx-imgBorder"] 
> ![](media/account-cardform-for-myactiveaccounts-view.png "Omat aktiiviset asiakkaat -näkymän asiakaskorttilomake")

Vaikka korttilomakkeita voi luoda ja muokata samalla tavoin kuin muita lomaketyyppejä, korttilomakkeet lisätään sovelluksiin eri tavalla. Sen sijaan että lomake lisättäisiin sovelluskomponenttina, mukautetun korttilomakkeet lisätään näkymiin **Vain luku -ruudukko** -ohjausobjektilla. 

## <a name="create-a-card-form"></a>Korttilomakkeen luominen
1. Luo korttilomake kirjautumalla [PowerAppsiin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). 
2. Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse lopuksi **Lomakkeet**-välilehti.
3. Valitse työkalurivillä **Lisää lomake** ja valitse sitten **Korttilomake**. Vaihtoehtoisesti voit avata aiemmin luodun **lomaketyypin**, joka on **Kortti**-lomake, ja muokata sitä.
4. Avaa haluamasi kentät. Kenttien määrä kannattaa rajoittaa, jotta lomake näkyy hyvin pienissä näytöissä. 
5. Valitse ensin **Tallenna** ja sitten **Julkaise**. 

## <a name="add-a-card-form-to-a-view"></a>Korttilomakkeen lisääminen lomakkeeseen 
1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.
2. Laajenna **Tiedot**, valitse haluamasi entiteetti ja valitse sitten **Näkymät**-välilehti.
3. Valitse haluamasi näkymä ja valitse sitten näkymän suunnitteluohjelman työkalurivillä **Siirry perinteiseen**.
4. Valitse **Mukautetut ohjausobjektit** **Tavalliset tehtävät** -ruudussa.
5. Valitse **Lisää ohjausobjekti**, valitse sitten ohjausobjektiluettelossa **Vain luku-ruudukko** ja valitse lopuksi **Lisää**.

   > [!NOTE]
   > Vain luku -ruudukko -ohjausobjekteja on kaksi. Oletusarvoinen vain luku -ruudukon ohjausobjekti on **Vain luku -ruudukko (oletus)**, joka ei tue mukautettuja korttilomakkeita. 

6. Määritä **Vain luku -ruudukko** -ominaisuussivulla seuraavat ominaisuudet ja valitse sitten **OK**. 
   - **Korttilomake**. Valitse ensin kynäkuvake ![Muokkaa ohjausobjektin ominaisuuksia](media/ccf-pencil-icon.png) ja sitten näkymässä näytettävä korttilomake. Näkymään liitetty ensisijainen entiteetti on oletusarvoisesti jo valittu, mutta voit muuttaa sitä. 
   - **Suorita käyttäytymisen työnkulku uudelleen**. Jos haluat muuttaa sitä, näkyykö korttilomake, kun sen kokoa muutetaan valitse kynäkuvake ![Muokkaa ohjausobjektin ominaisuuksia](media/ccf-pencil-icon.png). Lisätietoja: [Salli ruudukon ulkonäön muuttua luetteloon](specify-properties-for-unified-interface-apps.md#allow-grid-to-reflow-into-list)  
   - Valitse asiakasohjelmatyypit, **Verkko**, **Puhelin** tai **Tabletti**, jossa haluat näyttää **Vain luku -ruudukko** -ohjausobjektin.

     ![Korttilomakkeen Vain luku -ruudukko](media/read-only-grid-for-cardform.png)

7. Sulje **Mukautetut ohjausobjekti** -ominaisuussivu valitsemalla **OK**. 
8. Valitse perinteisen näkymän suunnitteluohjelman työkaluriviltä **Tallenna ja sulje**. 

## <a name="see-also"></a>Katso myös
[Mallipohjaisen sovelluksen tietojen visualisointien mukautettujen ohjausobjektien käyttäminen](use-custom-controls-data-visualizations.md)




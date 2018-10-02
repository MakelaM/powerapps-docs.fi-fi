---
title: Mallipohjaisten Unified Interface -sovellusten ominaisuuksien määrittäminen PowerAppsissa | MicrosoftDocs
description: Tietoja sovelluksen ruudukko-ohjausobjektin määrittämisestä
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 3ecea4a7-0d18-4ccd-9609-3a62179e9e1b
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 0
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="specify-properties-for-model-driven-unified-interface-apps"></a>Mallipohjaisten Unified Interface -sovellusten ominaisuuksien määrittäminen

Lisäksi Unified Interface -sovelluskehys käyttää responsiivisia suunnitteluperiaatteita voidakseen antaa optimaalisen katselu- ja vuorovaikutuskokemuksen näytön koosta tai suunnasta riippumatta. Mallin perustuva sovellukset, jotka käyttävät Unified Interface -sovelluskehystä ruudukon (näkymä) ohjausobjekti vastaa. Säilön koon pienentyessä – esimerkiksi puhelimilla ja pienemmissä näyttöikkunoissa, ruudukko muuttuu luetteloksi. 

Vain luku -ruudukon ohjausobjekti määrittää, miten ruudukon tulisi toimia näytön kokojen muuttuessa. Sovelluksen tekijänä jos käsittelet Unified Interface -sovelluksia, voit määrittää vain luku -ruudukon ohjausobjektin ja sen ominaisuuksia mukautettuja ruudukkoja ja luetteloita varten.
- **Korttilomake**-ominaisuus: Käytä luettelon oletusmallin sijaan luetteloiden korttilomaketta. Korttilomakkeet tarjoavat enemmän tietoja luettelonimikkeistä kuin oletusmalliluettelo.
- **Käyttäytymisen muuttuminen** -ominaisuus: Tämän parametrin avulla voit määrittää, muuttuuko ruudukon ulkonäkö luettelossa vai ei.

## <a name="allow-grid-to-reflow-into-list"></a>Salli ruudukon ulkonäön muuttua luetteloon

Vain luku -ruudukon ohjausobjektien lisäämisen avulla voit määrittää seuraavat ominaisuudet: 
- Salli ruudukon muuttua luetteloon pienillä näytöillä, kuten esimerkiksi mobiililaitteilla.
- Määritä värien tila vain ruudukoksi tai vain luetteloksi.  

1. Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).
2. Laajenna siirtymisruudussa **Entiteetit** -ruudussa haluamasi entiteetti (esimerkiksi **asiakas** tai **yhteyshenkilö**) ja valitse sitten **ohjausobjektit** -välilehdessä **Lisää ohjausobjekti**.

    ![Avaa Lisää ohjausobjekti](media/UnifiedInterface_ReadOnlyGrid_AddControl.png "Avaa Lisää ohjausobjekti")

3. Valitse **vain luku-ruudukko** ohjausobjektien luettelosta ja valitse sitten **Lisää**.

    Ohjausobjekti on lisätty käytettävissä olevien ohjausobjekti luetteloon.
   
    ![ohjausobjektin valitseminen](media/UnifiedInterface_ReadOnlyGrid_SelectControl.png "ohjausobjektin valitseminen")
    
4. Valitse laitteet (**Web**, **Puhelin**, tai **tabletti**), jota varten haluat määrittää vain luku-ruudukon.

    ![Valitse laitetyyppi](media/UnifiedInterface_ReadOnlyGrid_SelectDevice.png "Valitse laitteet")

5. Määritä **Korttilomake** -ominaisuus.

    Voit käyttää korttilomake-ominaisuutta luettelon oletusmallin sijaan luettelonimikkeitä varten. Korttilomakkeet tarjoavat enemmän tietoja luettelonimikkeistä kuin oletusmalliluettelo.    

    a. Valitse kynäkuvake **Korttilomakkeen** vieressä.

    ![Muokkaa korttilomake](media/UnifiedInterface_ReadOnlyGrid_CardForm.png "Muokkaa korttilomake")

    b.  Valitse **entiteetin** ja **Korttilomake**-tyypit.

    ![korttilomakkeen ominaisuudet](media/UnifiedInterface_ReadOnlyGrid_CardFormProperties.png "korttilomakkeen ominaisuudet")

    c. Valitse **OK**.
6. Määritä **Käyttäytymisen muuttuminen** -ominaisuus. 
    
    a. Valitse kynäkuvake **Käyttäytymisen muuttumisen** vieressä.

    ![Muokkaa käyttäytymisen muuttumista](media/UnifiedInterface_ReadOnlyGrid_EditReflow.png "Muokkaa käyttäytymisen muuttumista")

    b. Valitse ruudukon muutostyyppi **staattiseen asetukseen sitominen** avattavasta luettelosta.
    |Muutostyyppi|Kuvaus|
    |--------------|--------------------|
    |**Suorita työnkulku uudelleen**|Toiminnolla voi tehdä ruudukosta luettelotilan sen mukaan, kun ei ole riittävästi näyttötilaa.|
    |**Vain ruudukko**|Toiminnolla voi rajoittaa ruudukon muutosta luetteloksi silloinkin, kun ei ole riittävästi näyttötilaa.|
    |**Vain luettelo**|Näyttää vain luettelona silloinkin, kun tilaa on näyttämään sen ruudukossa.|
    
     ![Käyttäytymisen ominaisuuksien muuttuminen](media/UnifiedInterface_ReadOnlyGrid_ReflowProperties.png "Käyttäytymisen ominaisuuksien muuttuminen")

    c. Valitse **OK**.


7.  Tallenna ja julkaise muutokset. 


## <a name="conditional-image"></a>Ehdollinen kuva
Voit näyttää mukautetun kuvakkeen luettelossa arvon sijaan ja määrittää logiikan, jonka avulla voit valita ne JavaScriptin avulla sarakkeen arvojen perusteella. Saat lisätietoja ehdollisista kuvista aiheesta [Mukauta kuvakkeet sen sijaan, että arvot näkyvät luettelonäkyminä](../common-data-service/display-custom-icons-instead.md).

## <a name="next-steps"></a>Seuraavat vaiheet
[Näkymän luominen tai muokkaaminen](create-edit-views.md)

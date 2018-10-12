---
title: Mallipohjaisten Unified Interface -sovellusten ominaisuuksien määrittäminen PowerAppsissa | MicrosoftDocs
description: Opi määrittämään sovelluksen ruudukko-ohjausobjekti
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 3ecea4a7-0d18-4ccd-9609-3a62179e9e1b
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 0
topic-status: Drafting
ms.openlocfilehash: 007ac566e317ee99bd85ab0675e5a53839800bb4
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675419"
---
# <a name="specify-properties-for-model-driven-unified-interface-apps"></a>Mallipohjaisten Unified Interface -sovellusten ominaisuuksien määrittäminen

Unified Interface -kehys käyttää reagoivan suunnittelun periaatteita optimaalisen katselu- ja käyttökokemuksen tarjoamiseksi, olipa näytön koko tai suunta mikä tahansa. Mallipohjaisissa sovelluksissa, jotka käyttävät Unified Interface -kehystä, ruudukon (näkymän) ohjausobjekti on reagoiva. Säilön koon pienentyessä – esimerkiksi-puhelimissa ja pienemmissä näyttölaitteissa – ruudukko muutetaan luetteloksi. 

Vain luku -ruudukko -ohjausobjekti määrittää, miten ruudukko mukautuu eri näyttökokoihin. Jos olet tekemässä Unified Interface -sovellusta, voit määrittää Vain lukuruudukko -ohjausobjektin ja sen ominaisuudet mukautettuja ruudukoita ja luetteloita varten.
- **Kortin muoto** -ominaisuus: käytä kortin muotoa luetteloille oletusluettelomallin sijaan. Kortin muoto näyttää enemmän tietoja luettelokohteille kuin oletusluettelomalli.
- **Juoksutus**-ominaisuus: tämän parametrin avulla voit määrittää, juoksutetaanko ruudukko luetteloon.

## <a name="allow-grid-to-reflow-into-list"></a>Salli ruudukon juoksutus luetteloon

Lisäämällä Vain luku -ruudukko -ohjausobjektin ohjausobjektien luetteloon voit määrittää seuraavat ominaisuudet: 
- Salli ruudukon juoksutus luetteloon pienissä näytöissä, kuten matkapuhelimissa.
- Määritä hahmontamistilaksi vain ruudukko tai vain luettelo.  

1. Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).
2. Laajenna siirtymisruudussa **Entiteetit**, valitse asianmukainen entiteetti (kuten **Tili** tai **Yhteyshenkilö**), ja valitse sitten **Ohjausobjektit**-välilehdeltä **Lisää ohjausobjekti**.

    ![Avaa Lisää ohjausobjekti](media/UnifiedInterface_ReadOnlyGrid_AddControl.png "Avaa Lisää ohjausobjekti")

3. Valitse **Vain luku -ruudukko** ohjausobjektien luettelosta, ja valitse sitten **Lisää**.

    Ohjausobjekti lisätään käytettävissä olevien ohjausobjektien luetteloon.
   
    ![Valitse ohjausobjekti](media/UnifiedInterface_ReadOnlyGrid_SelectControl.png "valittu ohjausobjekti")
    
4. Valitse laitteet (**Verkko**, **Puhelin** tai **Tabletti**), joissa haluat ruudukon olevan Vain luku -tilassa.

    ![Valitse laitteen tyyppi](media/UnifiedInterface_ReadOnlyGrid_SelectDevice.png "Valitse laitteet")

5. Määritä **Kortin muoto** -ominaisuus.

    Kortin muoto -ominaisuuden avulla voit näyttää luettelokohteet oletusluettelomallin sijaan. Kortin muoto näyttää enemmän tietoja luettelokohteille kuin oletusluettelomalli.    

    a. Valitse kynäkuvake kohdan **Kortin muoto** vieressä.

    ![Muokkaa kortin muotoa](media/UnifiedInterface_ReadOnlyGrid_CardForm.png "Muokkaa kortin muotoa")

    b.  Valitse **Entiteetti** ja **Kortin muoto** -tyypit.

    ![Kortin muodon ominaisuudet](media/UnifiedInterface_ReadOnlyGrid_CardFormProperties.png "Kortin muodon ominaisuudet")

    c. Valitse **OK**.
6. Määritä **Juoksutus**-ominaisuus. 
    
    a. Valitse kynäkuvake kohdan **Juoksutus** vieressä.

    ![Muokkaa juoksutusta](media/UnifiedInterface_ReadOnlyGrid_EditReflow.png "Muokkaa juoksutusta")

    b. Valitse ruudukon juoksutustyyppi avattavasta **Sido staattisiin asetuksiin** -luettelosta.
    |Työnkulun tyyppi|Kuvaus|
    |--------------|--------------------|
    |**Juoksutus**|Sallii ruudukon hahmontamisen luetteloon, jos näytössä ei ole riittävästi tilaa.|
    |**Vain ruudukko**|Ei salli ruudukon hahmontamista luetteloon, vaikka näytössä ei ole riittävästi tilaa.|
    |**Vain luettelo**|Näyttää sisällön luettelona, vaikka näytössä olisi riittävästi tilaa ruudukon näyttämiseksi.|
    
     ![Juoksutuksen ominaisuudet](media/UnifiedInterface_ReadOnlyGrid_ReflowProperties.png "Juoksutuksen ominaisuudet")

    c. Valitse **OK**.


7.  Tallenna ja julkaise muutokset. 


## <a name="conditional-image"></a>Ehdollinen kuva
Voit näyttää luettelossa mukautetun kuvakkeen arvon sijaan ja määrittää niiden valintaan käytettävän logiikan käyttämällä sarakkeiden arvoja ja JavaScriptiä. Katso lisätietoja ehdollisista kuvista kohdasta [Mukautettujen kuvakkeiden näyttäminen arvojen sijaan luettelonäkymissä](../common-data-service/display-custom-icons-instead.md).

## <a name="next-steps"></a>Seuraavat vaiheet
[Näkymän luominen tai muokkaaminen](create-edit-views.md)
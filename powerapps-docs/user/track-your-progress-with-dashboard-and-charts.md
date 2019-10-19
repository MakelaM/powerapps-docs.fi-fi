---
title: Edistymisen seuranta koonti näyttöjen ja kaavioiden avulla mallipohjaisissa sovelluksissa | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/4/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
- D365CE
ms.openlocfilehash: e9d046c49a2a91aaf5c65094d446ae09f41572f9
ms.sourcegitcommit: 4c35aedde46380d5438687ae6f61a3b0cc7e7e2f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/05/2019
ms.locfileid: "71969100"
---
# <a name="track-your-progress-with-dashboards-and-charts"></a>Oman edistymisen seuraaminen kaavioilla ja koontinäytöillä

Koonti näytöt ottavat kokoelma sovellus tietoja ja tarjoavat merkityksellisiä tietoja suorituskyky ilmaisimien ja muiden tärkeiden tietojen näyttämiseen helposti luettavien vuorovaikutteisten kaavioiden ja kaavioiden avulla. Koonti näytöt ovat käytettävissä kaikille tietue tyypeille.

> [!div class="mx-imgBorder"]
> ![Koonti näytön](media/Dashboard.png "koonti näyttö") 

-  Jos haluat tarkastella eri koonti näytön ulkoasua, valitse alaspäin osoittava nuoli koonti näytön nimen vieressä ja valitse sitten haluamasi ulkoasu.
-  Jos haluat valita oletusarvoisen koonti näytön, Näytä haluamasi koonti näyttö ja valitse sitten **Aseta oletukseksi** näytön yläreunassa.

   > [!div class="mx-imgBorder"]
   > ![Koonti]näytön(media/add_dashboard.png "lisäämisen tai muuttamisen koonti") näytön lisääminen tai muuttaminen 

## <a name="create-a-new-dashboard"></a>Luo uusi koonti näyttö

1. Jos haluat luoda uuden koonti näytön, valitse **Luo Dynamics 365-koonti näyttö**. 

   > [!div class="mx-imgBorder"]
   > ![Lisää uusi koonti näyttö](media/new_dashboard.png "Lisää uusi koonti näyttö")
   
2. Valitse koonti näytön ulkoasu ja valitse **Luo**.  

   > [!div class="mx-imgBorder"]
   > ![Koonti näytön luominen](media/create_dashboard.png "koonti näytön luomi seksi")
 
3. Kirjoita koonti näytön nimi. 
4. Lisää, mitä haluat kullekin koonti näytön alueelle. Lisätään esimerkiksi kaavio. 

   > [!div class="mx-imgBorder"]
   > ![](media/add_chart.png "Kaavion") lisääminen kaavioon
 
 5. Valitse kaavion **tietue tyyppi** .
 6. Valitse **näkymä** , jossa kaavion tiedot näkyvät.
 7. Valitse kaavio ja valitse sitten **Lisää**.
 8. Jatka komponenttien lisäämistä koonti näyttöön ja kun olet tehnyt sen, valitse **Tallenna**. 
 
Luomasi koonti näyttö näkyy käytettävissä olevien koonti näyttöjen avattavassa valikossa.

## <a name="use-charts"></a>Kaavioiden käyttäminen 

Kaaviot tarjoavat sinulle nopean näkymän siitä, miten seuraat tavoitteitasi. Ne ovat myös vuorovaikutteisia, joten voit napsauttaa tai napauttaa kaavion aluetta saadaksesi lisä tietoja.

-   Viemällä hiiren osoittimen kaavion päälle saat näkyviin työkalu vihjeen, joka antaa nopeasti tietoja kaavion alueesta.
-   Napsauttamalla kaavion aluetta saat näkyviin ruudukko näkymän, jossa on lisä tietoja kaavion tiedoista.
-   Jos haluat laajentaa kaaviota, **Valitse Laajenna kaavion**![laajennus kaavio näkymä]Laajenna(media/expandviewbutton.png "kaavio näkymä") -painike.
-   Jos haluat tarkastella kaavion tietueita tai päivittää kaaviota, valitse ![Lisää komentoja](media/MoreButton.png "Lisää komentoja") ja valitse sitten toiminto: **Päivitä** tai **Näytä tietueet**.
     
     > [!div class="mx-imgBorder"]
     > ![Kaavioiden tarkastelu]Powerappsin kaavioiden powerapps-(media/ViewOfCharts.png "näkymässä")  
       

**Kaavio näkymän muuttaminen**
 
Kaavio näkymän muuttaminen näyttää tietojen erilaisen erittelyn, kuten tietyn ajan jakson aikana avatut mahdollisuudet. Voit muuttaa kaavio näkymää valitsemalla ruudukko sivun näkymä valitsimen.

Valitse esimerkiksi "kaikki mahdollisuudet" ja sitten eri näkymä. sekä kaavio että ruudukko päivitetään.

> [!div class="mx-imgBorder"]
> ![Kaavio näkymän muuttaminen powerappsissa](media/ChangeChartView.png "kaavio näkymän muuttaminen powerappsissa")

## <a name="known-issues"></a>Tunnetut ongelmat  
Kaavion suunnittelussa ei tueta order by-kohteen lisäämistä tiettyihin laskettuihin kenttiin, ja se aiheuttaa virheen.  Tämän aiheuttavat lasketut kentät käyttävät toista laskettua kenttää, liittyvää entiteettikenttä tai entiteetin paikallista kenttää.




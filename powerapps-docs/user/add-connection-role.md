---
title: Lisää yhteys rooli tietueiden linkittämistä varten | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 8/01/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: c606a7b809f1684cbe60b5e53e4b291f11b1d164
ms.sourcegitcommit: 4e4f7945c3f24faf9bb8a856a5f3892cbfd113be
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/05/2019
ms.locfileid: "68786897"
---
# <a name="add-a-connection-role-to-to-link-records-to-each-other"></a>Lisää yhteys rooli tietueiden linkittämistä varten |

[!INCLUDE [cc-beta-prerelease-disclaimer](../includes/cc-beta-prerelease-disclaimer.md)]

Yhteyksien avulla voit helposti yhdistää käyttäjiä, yhteyshenkilöitä, tarjouksia, myynti tilauksia ja monia muita entiteettitietueita toistensa kanssa. Liitoksen tietueille voidaan määrittää tietyt roolit, jotka auttavat suhteen tarkoituksen määrittämisessä.

Se on nopea tapa luoda useita yhteyksiä ja rooleja tietylle tietueelle. Kontaktilla voi olla esimerkiksi useita suhteita muihin yhteys tietoihin, asiakkaisiin tai sopimuksiin. Yhteys tieto voi olla eri roolissa jokaisessa suhteessa.

Yhteyden roolit liittyvät suoraan yhteyteen. Jos haluat käyttää yhteyden roolia, sinun on ensin lisättävä yhteyden tietueeseen.

Ennen kuin voit lisätä yhteyden rooleja, järjestelmänvalvojan on otettava se käyttöön. Lisä tietoja on Ohje aiheessa [yhteyksien roolien määrittäminen](https://docs.microsoft.com/en-us/powerapps/maker/common-data-service/configure-connection-roles).

1. Jos haluat lisätä tai hallita yhteyksiä, valitse tietue, jota haluat hallita, kuten mahdollisuus.  
2. Valitse **liittyvä** -väli lehti ja valitse sitten **yhteydet**. Tämä avaa yhteys ruudukon, joka sisältää tietueen yhteyksien luettelon.

    > [!div class="mx-imgBorder"]
    > ![Lisää uusi liittymä rooli](media/connection1.png "Lisää uusi liittymä rooli") 

3. Valitse **Yhdistä** ja valitse sitten **toinen** tai **minulle**.

    > [!div class="mx-imgBorder"]
    > ![Valitse yhteyksien tyyppi](media/connection2.png "Valitse yhteyksien tyyppi") 
  
4. Kirjoita **nimi** -kenttään tai Etsi yhteydelle tietueen nimi.

5. Valitse **koska tämä rooli** -kentässä valinta kuvake ja valitse sitten **uusi liittymä rooli**. Voit myös etsiä aiemmin luodun roolin, jonka haluat liittää yhteyteen, ja valitse sitten **Tallenna**.

    > [!div class="mx-imgBorder"]
    > ![Valitse uusi liittymä rooli](media/connection3.png "Valitse uusi liittymä rooli")  

    > [!NOTE]
    > Jos olet syöttänyt tiedot, ennen kuin luot uuden yhteyden roolin, näyttöön tulee varoitus valinta ikkuna, jossa pyydetään, Haluatko peruuttaa ja jatkaa työskentelyä yhteyden parissa, ja poistua nykyisestä tietueesta, jota käsittelet.

6. Jos haluat luoda uuden yhteyden roolin, kirjoita **Uusi yhteyden rooli** -näyttöön nimi ja valitse sitten **yhteyden rooli luokka**.

    > [!div class="mx-imgBorder"]
    >  ![Lisää yhteyksien rooli luokka](media/connection4.png "Lisää yhteyksien rooli luokka") 

7. Kun olet lopettanut, valitse **tallenna & Sulje**.

  
## <a name="manage-connection-roles"></a>Hallitse yhteyksien rooleja

Jos haluat hallita yhteyden roolia, valitse yhteyden rooli yhteyden entiteetistä. Tämä avaa Yhteysroolin entiteettitietueen.  Voit muokata nimeä, valita yhteydelle rooli luokan ja lisätä kuva uksen.


   > [!div class="mx-imgBorder"]
   > ![Muokkaa yhteyksien roolia](media/connection7.png "Muokkauksen yhteydessä-rooli") 
  
Voit myös hallita yhteyden rooli tyyppejä, jotka haluat liittää yhteyden rooliin.

1. Avaa yhteysrooli ja valitse sitten komennon **Hallitse tietue tyyppiä** . 

    > [!div class="mx-imgBorder"]
    > ![Muokkaa yhteyksien roolia](media/connection5.png "Muokkauksen yhteydessä-rooli") 
  

2. Tämä avaa luettelon niiden yhteyksien rooli tyypeistä, jotka voit lisätä tai poistaa tälle yhteydelle.

    > [!div class="mx-imgBorder"]
    > ![Hallitse tietue tyyppiä](media/connection6.png "Hallitse tietue tyyppiä") 



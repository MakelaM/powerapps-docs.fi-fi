---
title: Liiketoimintasäännön luominen Common Data Service for Appsissa | Microsoft Docs
description: Vaiheittaiset ohjeet liiketoimintasäännön luomiseen Common Data Service (CDS) for Appsissa.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: 13e00081ce01b44feeea6fc1d6fff9556c020298
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168270"
---
# <a name="create-a-business-rule"></a>Luo liiketoimintasääntö

Voit luoda liiketoimintasääntöjä ja suosituksia logiikan ja vahvistusten soveltamista varten kirjoittamatta koodia tai luomatta laajennuksia.  Liiketoimintasäännöt tarjoavat yksinkertaisen käyttöliittymän, jolla voit toteuttaa ja ylläpitää nopeasti muuttuvia ja yleisesti käytettyjä sääntöjä. 
  
Yhdistämällä ehtoja ja toimintoja voit tehdä seuraavia tehtäviä liiketoimintasääntöjen avulla:  
  
* Määritä kenttien arvoja  
* Tyhjennä kenttien arvoja  
* Määritä kenttien vaatimustasoja  
* Näytä tai piilota kenttiä  
* Ota kenttiä käyttöön tai poista niitä käytöstä  
* Vahvista tietoja ja näytä virhesanomia  
* Luo liiketoimintatietojen hallintaan perustuvia liiketoimintasuosituksia.  
  
## <a name="differences-between-canvas-and-model-driven-apps"></a>Pohjaan ja malliin perustuvien sovellusten erot

Malliin perustuvat sovellukset voivat käyttää kaikkia toimintoja, jotka ovat käytettävissä liiketoimintasääntöihin. Kaikki liiketoimintasääntötoiminnot eivät kuitenkaan ole pohjaan perustuvien sovellusten käytettävissä tällä hetkellä. Seuraavat toiminnot **eivät** ole käytettävissä pohjaan perustuvien sovellusten kanssa:

* Näytä tai piilota kenttiä  
* Ota kenttiä käyttöön tai poista niitä käytöstä  
* Luo liiketoimintatietojen hallintaan perustuvia liiketoimintasuosituksia.  

## <a name="prerequisites"></a>Edellytykset
Jotta voit noudattaa tämän aiheen ohjeita, siirry entiteettien luomisen ja muokkaamisen mahdollistavaan [ympäristöön](../canvas-apps/working-with-environments.md).

## <a name="create-a-business-rule"></a>Luo liiketoimintasääntö
  
1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com) ja napsauta tai napauta vasemmassa reunassa olevan **Tiedot**-kohdan alaspäin osoittavaa nuolta.

2. Napsauta tai napauta näyttöön tulevassa luettelossa **Entiteetti**.
  
3. Avaa entiteetti, jolle haluat luoda liiketoimintasäännön (esimerkiksi avata **Tili**-entiteetin), ja valitse sitten **Liiketoimintasäännöt**-välilehti.  

4. Valitse **Uusi**.  
  
    Liiketoimintasäännön suunnittelutyökalun ikkuna avautuu. Se sisältää yhden valmiiksi luodun ehdon. Jokainen sääntö alkaa ehdolla. Liiketoimintasääntö ottaa yhden tai useamman tähän ehtoon perustuvan toiminnon.  

    > [!TIP]
    > Jos haluat muokata aiemmin luotua liiketoimintasääntöä, se on poistettava käytöstä ennen sen muokkaamista.  
  
5. Lisää halutessasi kuvaus ikkunan vasemmassa yläkulmassa olevaan kuvausruutuun.
  
6. Määritä vaikutusalue seuraavien kohtien mukaisesti:  
  
    |||  
    |-|-|  
    |**Jos valitset tämän kohteen...**|**Vaikutusalueena on...**|  
    |**Entiteetti**|Malliin perustuvat lomakkeet ja palvelin|  
    |**Kaikki lomakkeet**|Malliin perustuvat lomakkeet|  
    |Erityislomake (esim. **Tili**-lomake)|Vain kyseinen malliin perustuva lomake|  

    > [!TIP]
    > Jos muodostat pohjaan perustuvaa sovellusta, joudut käyttämään entiteettiä vaikutusalueena.
  
7. **Lisää ehdot.** Voit lisätä lisää ehtoja liiketoimintasääntöösi:  
  
    1. Vedä **Ehto**-osa **Osat**-välilehdestä suunnittelutoiminnon plusmerkkiin.  
  
        ![Lisää ehto liiketoimintasääntöön](./media/data-platform-cds-create-business-rule/add-condition-business-rule.png "Lisää ehto liiketoimintasääntöön")  
  
    2. Voit määrittää ehdolle ominaisuuksia napsauttamalla **Ehto**-osaa suunnittelutyökalun ikkunassa. Määritä sitten ominaisuudet **Ominaisuudet**-välilehdessä näytön oikeassa reunassa. Kun määrität ominaisuuksia, Common Data Service luo lausekkeen **Ominaisuudet**-välilehden alareunaan.  
  
    3. Voit lisätä muita lauseita (ja AND tai OR) ehtoon. Luo uusi sääntö napsauttamalla **Ominaisuudet**-välilehdestä **Uusi** ja määritä sitten säännön ominaisuudet. **Sääntölogiikka**-kentässä voit määrittää, lisätäänkö uusi sääntö ANDina vai ORina.  
  
        ![Lisää uusi sääntö ehtoon](./media/data-platform-cds-create-business-rule/add-new-rule-condition.png "Lisää uusi sääntö ehtoon")  
  
    4. Kun olet asettanut ehdon ominaisuudet, valitse **Käytä**.  
  
8. **Lisää toimintoja.** Lisää toiminto:  
  
    1. Vedä jokin toiminto-osa **Osat**-välilehdestä **Ehto**-osan vieressä olevaan plusmerkkiin. Vedä toiminto valintamerkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön toteuttavan toiminnon, kun ehto täyttyy, tai x-merkin viereen olevaan plusmerkkiin, jos haluat liiketoimintasäännön toteuttavan toiminnon, jos ehto ei täyty.
  
        ![Vedä toiminto liiketoimintasääntöön](./media/data-platform-cds-create-business-rule/drag-an-action-business-rule.png "Vedä toiminto liiketoimintasääntöön")  
  
    2. Voit määrittää toiminnolle ominaisuuksia napsauttamalla **Toiminto**-osaa suunnittelutyökalun ikkunassa. Määritä sitten ominaisuudet **Ominaisuudet**-välilehdessä.  
  
    3. Kun olet asettanut ominaisuudet, valitse **Käytä**.  
  
9. **Lisää liiketoimintasuositus. (Vain malliin perustuva)** Lisää liiketoimintasuositus:  
  
    1. Vedä **Suositus**-osa **Osat**-välilehdestä **Ehto**-osan vieressä olevaan plusmerkkiin. Vedä **Suositus**-osa valintamerkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön toteuttavan kyseisen toiminnon, kun ehto täyttyy, tai x-merkin viereen olevaan plusmerkkiin, jos haluat liiketoimintasäännön toteuttavan toiminnon, jos ehto ei täyty.  
  
    2. Voit määrittää suositukselle ominaisuuksia napsauttamalla **Suositus**-osaa suunnittelutyökalun ikkunassa. Määritä sitten ominaisuudet **Ominaisuudet**-välilehdessä.  
  
    3. Voit lisätä Lisää toimintoja suositukseen vetämällä niitä **Osat**-välilehdestä. Määritä sitten kunkin toiminnon ominaisuudet **Ominaisuudet**-välilehdessä.  
  
        > [!NOTE]
        >  Kun luot suosituksen, Common Data Service lisää yhden toiminnon oletusarvoisesti. Näet kaikki suosituksen toiminnot napsauttamalla **Suositus**-osan kohtaa **Tiedot**.  
  
    4. Kun olet asettanut ominaisuudet, valitse **Käytä**.  
  
10. Vahvista liiketoimintasääntö napsauttamalla toimintorivillä **Vahvista**.  
  
11. Tallenna liiketoimintasääntö napsauttamalla toimintorivillä **Tallenna**.  
12. Aktivoi liiketoimintasääntö valitsemalla Ratkaisunhallinta-ikkuna ja napsauttamalla sitten **Aktivoi**. Et voi aktivoida liiketoimintasääntöä suunnittelutyökalun ikkunasta.  
  
    > [!TIP]
    >  Seuraavassa on muutamia vihjeitä, jotka kannattaa pitää mielessä, kun luot liiketoimintasääntöjä suunnittelutyökalun ikkunassa:  
    >   
    > - Voit ottaa tilannevedoksen liiketoimintasääntöikkunan sisällöstä napsauttamalla toimintorivillä **Tilannevedos**. Tästä on hyötyä, jos esimerkiksi haluat jakaa liiketoimintasääntöjä ja saada kommentteja niistä ryhmän jäseniltä.  
    > - Pienen kartan avulla voit siirtyä prosessin eri osien välillä. Tästä on hyötyä, kun työstät monimutkaista prosessia, joka jatkuu näytön yli.  
    > - Lisätessäsi ehtoja, toimintoja ja liiketoimintasuosituksia liiketoimintasääntöön Common Data Service luo koodin liiketoimintasäännölle suunnittelutyökalun ikkunan alareunaan. Koodi on vain luku -tilassa.  
  
## <a name="localize-error-messages-used-in-business-rules"></a>Lokalisoi liiketoimintasäännöissä käytettäviä virhesanomia  
 Jos organisaatiossa on käytössä useampi kuin yksi kieli, haluat lokalisoida määrittämäsi virhesanomat. Joka kerta, kun määrität viestin, järjestelmä luo otsikon. Jos viet käännökset organisaatioon, voit lisätä viestiesi lokalisoidut versiot ja tuoda sitten kyseiset otsikot takaisin Common Data Serviceen, jotta ihmiset, jotka käyttävät muita kieliä kuin peruskieli, voivat tarkastella käännettyjä sanomia.  
  
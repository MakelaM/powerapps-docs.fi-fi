---
title: Mallipohjaisen sovelluksen liiketoimintasääntöjen ja suositusten luominen | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 00e62904-2ce9-4730-a113-02b1fedbf22e
caps.latest.revision: 31
author: Mattp123
ms.author: matp
manager: kvivek
tags:
- PowerApps maker portal impact
ms.openlocfilehash: c1a132648a63845c42cde8a80636d0e87e10a328
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677139"
---
# <a name="tutorial-create-business-rules-and-recommendations-to-apply-logic-in-a-model-driven-app-form"></a>Opetusohjelma: Luo liiketoimintasääntöjä ja suosituksia logiikan käyttämiseksi mallipohjaisessa sovelluslomakkeessa

Tässä opetusohjelmassa kerrotaan, miten voit luoda liiketoimintasääntöjä ja suosituksia käyttääksesi lomakelogiikkaa kirjoittamatta JavaScript-koodia tai luomatta laajennuksia.  Liiketoimintasäännöt tarjoavat yksinkertaisen käyttöliittymän, jolla voit toteuttaa ja ylläpitää nopeasti muuttuvia ja yleisesti käytettyjä sääntöjä. Niitä voidaan käyttää päälomakkeissa ja nopean luonnin lomakkeissa, ja ne toimivat PowerApps-sovelluksissa, Dynamics 365 Customer Engagement -verkkosovelluksissa, Dynamics 365:n tablettisovelluksessa ja Dynamics 365 for Outlookissa (online- tai offline-tilassa).  
  
 Yhdistämällä ehtoja ja toimintoja voit tehdä seuraavia tehtäviä liiketoimintasääntöjen avulla:  
  
-   Määritä kenttien arvoja  
  
-   Tyhjennä kenttien arvoja  
  
-   Määritä kenttien vaatimustasoja  
  
-   Näytä tai piilota kenttiä  
  
-   Ota kenttiä käyttöön tai poista niitä käytöstä  
  
-   Vahvista tietoja ja näytä virhesanomia  
  
-   Luo liiketoimintatietojen hallintaan perustuvia liiketoimintasuosituksia.  
  
## <a name="create-a-business-rule-or-business-recommendation"></a>Luo liiketoimintasääntö tai liiketoimintasuositus
  
1. Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
  
2.  Avaa entiteetti, jolle haluat luoda liiketoimintasäännön (esimerkiksi avata **Tili**-entiteetin), ja kaksoisnapsauta sitten **Liiketoimintasäännöt**-kohtaa.  
  
 ![Liiketoimintasäännön luominen oletusratkaisussa](media/create-business-rule-the-default-solution.png "Liiketoimintasäännön luominen oletusratkaisussa")  
  
3.  Valitse **Uusi**.  
  
     Liiketoimintasäännön suunnittelutyökalun ikkuna avautuu. Se sisältää yhden valmiiksi luodun ehdon. Jokainen sääntö alkaa ehdolla. Liiketoimintasääntö ottaa yhden tai useamman tähän ehtoon perustuvan toiminnon.  
  
 ![Liiketoimintasääntöjen suunnitteluikkuna](media/business-rules-design-window.png "Liiketoimintasääntöjen suunnitteluikkuna")  
  
   > [!TIP]
> Jos haluat muokata aiemmin luotua liiketoimintasääntöä, se on poistettava käytöstä ennen sen muokkaamista.

4.  Lisää halutessasi kuvaus ikkunan vasemmassa yläkulmassa olevaan kuvausruutuun.  
  
5.  Määritä vaikutusalue seuraavien kohtien mukaisesti:  
  
    |||  
    |-|-|  
    |**Jos valitset tämän kohteen...**|**Vaikutusalueena on...**|  
    |**Entiteetti**|Kaikki lomakkeet ja palvelin|  
    |**Kaikki lomakkeet**|Kaikki lomakkeet|  
    |Erityislomake (esim. **Tili**-lomake)|Vain kyseinen lomake|  
  
6. **Lisää ehdot.** Voit lisätä lisää ehtoja liiketoimintasääntöösi:  
  
    1.  Vedä **Ehto**-osa **Osat**-välilehdestä suunnittelutoiminnon plusmerkkiin.  
  
        ![Lisää ehto liiketoimintasääntöön](media/add-condition-business-rule.png "Lisää ehto liiketoimintasääntöön")  
  
    2.  Voit määrittää ehdolle ominaisuuksia napsauttamalla **Ehto**-osaa suunnittelutyökalun ikkunassa. Määritä sitten ominaisuudet **Ominaisuudet**-välilehdessä näytön oikeassa reunassa. Kun määrität ominaisuuksia, lauseke luodaan **Ominaisuudet**-välilehden alareunaan.  
  
    3.  Voit lisätä muita lauseita (ja AND tai OR) ehtoon. Luo uusi sääntö napsauttamalla **Ominaisuudet**-välilehdestä **Uusi** ja määritä sitten säännön ominaisuudet. **Sääntölogiikka**-kentässä voit määrittää, lisätäänkö uusi sääntö ANDina vai ORina.  
  
        ![Lisää uusi sääntö ehtoon](media/add-new-rule-condition.png "Lisää uusi sääntö ehtoon")  
  
    4.  Kun olet asettanut ehdon ominaisuudet, valitse **Käytä**.  
  
7. **Lisää toimintoja.** Lisää toiminto:  
  
    1.  Vedä jokin toiminto-osa **Osat**-välilehdestä **Ehto**-osan vieressä olevaan plusmerkkiin. Vedä toiminto valintamerkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön toteuttavan toiminnon, kun ehto täyttyy, tai x-merkin viereen olevaan plusmerkkiin, jos haluat liiketoimintasäännön toteuttavan toiminnon, jos ehto ei täyty.  
  
        ![Vedä toiminto liiketoimintasääntöön](media/drag-an-action-business-rule.png "Vedä toiminto liiketoimintasääntöön")  
  
    2.  Voit määrittää toiminnolle ominaisuuksia napsauttamalla **Toiminto**-osaa suunnittelutyökalun ikkunassa. Määritä sitten ominaisuudet **Ominaisuudet**-välilehdessä.  
  
    3.  Kun olet asettanut ominaisuudet, valitse **Käytä**.  
  
8. **Lisää liiketoimintasuositus.** Lisää liiketoimintasuositus seuraavasti:  
  
    1.  Vedä **Suositus**-osa **Osat**-välilehdestä **Ehto**-osan vieressä olevaan plusmerkkiin. Vedä **Suositus**-osa valintamerkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön toteuttavan kyseisen toiminnon, kun ehto täyttyy, tai x-merkin viereen olevaan plusmerkkiin, jos haluat liiketoimintasäännön toteuttavan toiminnon, jos ehto ei täyty.  
  
    2.  Voit määrittää suositukselle ominaisuuksia napsauttamalla **Suositus**-osaa suunnittelutyökalun ikkunassa. Määritä sitten ominaisuudet **Ominaisuudet**-välilehdessä.  
  
    3.  Voit lisätä Lisää toimintoja suositukseen vetämällä niitä **Osat**-välilehdestä. Määritä sitten kunkin toiminnon ominaisuudet **Ominaisuudet**-välilehdessä.  
  
        > [!NOTE]
        >  Kun luot suosituksen, yksi toiminto lisätään oletusarvoisesti. Näet kaikki suosituksen toiminnot napsauttamalla **Suositus**-osan kohtaa **Tiedot**.  
  
    4.  Kun olet asettanut ominaisuudet, valitse **Käytä**.  
  
9. Vahvista liiketoimintasääntö napsauttamalla toimintorivillä **Vahvista**.  
  
10. Tallenna liiketoimintasääntö napsauttamalla toimintorivillä **Tallenna**.  
  
11. Aktivoi liiketoimintasääntö valitsemalla Ratkaisunhallinta-ikkuna ja napsauttamalla sitten **Aktivoi**. Et voi aktivoida liiketoimintasääntöä suunnittelutyökalun ikkunasta.  
  
> [!TIP]
>  Seuraavassa on muutamia vihjeitä, jotka kannattaa pitää mielessä, kun luot liiketoimintasääntöjä suunnittelutyökalun ikkunassa:  
>   
> - Voit ottaa tilannevedoksen liiketoimintasääntöikkunan sisällöstä napsauttamalla toimintorivillä **Tilannevedos**. Tästä on hyötyä, jos esimerkiksi haluat jakaa liiketoimintasääntöjä ja saada kommentteja niistä ryhmän jäseniltä.  
> - Pienen kartan avulla voit siirtyä prosessin eri osien välillä. Tästä on hyötyä, kun työstät monimutkaista prosessia, joka jatkuu näytön yli.  
> - Lisätessäsi ehtoja, toimintoja ja liiketoimintasuosituksia liiketoimintasääntöösi järjestelmä luo koodin liiketoimintasäännölle suunnittelutyökalun ikkunan alareunaan. Koodi on vain luku -tilassa.  
  
<a name="BKMK_LocalizingErrorMessages"></a>   
## <a name="localize-error-messages-used-in-business-rules"></a>Lokalisoi liiketoimintasäännöissä käytettäviä virhesanomia  
 Jos organisaatiossa on käytössä useampi kuin yksi kieli, haluat lokalisoida määrittämäsi virhesanomat. Joka kerta, kun määrität viestin, järjestelmä luo otsikon. Jos viet käännökset organisaatioon, voit lisätä viestiesi lokalisoidut versiot ja tuoda sitten kyseiset otsikot takaisin järjestelmään, jotta ihmiset, jotka käyttävät muita kieliä kuin peruskieli, voivat tarkastella käännettyjä sanomia.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Mukautetun liiketoimintalogiikan luominen prosesseja käyttämällä](guide-staff-through-common-tasks-processes.md)   
 [Liiketoimintaprosessin työnkulun luominen](/flow/create-business-process-flow)   


---
title: Mallipohjaisen sovelluksen liiketoimintasääntöjen ja suositusten luominen | MicrosoftDocs
ms.custom: ''
ms.date: 03/15/2019
ms.reviewer: ''
ms.service: powerapps
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-business-rules-and-recommendations-to-apply-logic-in-a-model-driven-app-form"></a>Liiketoimintasääntöjen ja suositusten luominen mallipohjaisen sovelluksen lomakkeen logiikan käyttämiseksi

Tässä ohjeaiheessa kerrotaan, miten liiketoimintasääntöjä ja -suosituksia luodaan käyttämällä lomakelogiikka mallipohjaisessa sovelluksessa ilman, että on kirjoitettava JavaScript-koodia tai luotava laajennuksia. Liiketoimintasäännöt on yksinkertainen käyttöliittymä, jossa voi ottaa käyttöön ja ylläpitää nopeasti muuttuvia ja yleisesti käytettyjä sääntöjä. Niitä voidaan käyttää pää- ja pikaluontilomakkeissa ja ne toimivat mallipohjaiset sovelluksissa, Dynamics 365 for Customer Engagement -verkkosovelluksissa, Dynamics 365 for tablets -ratkaisussa ja Dynamics 365 for Outlookissa (online- tai offline-tilassa).

> [!NOTE]
> Lisätietoja entiteetin liiketoimintasäännön määrittämisestä siten, että sittä käytetään kaikissa lomakkeissa ja palvelimessa on kohdassa [Entiteetin liiketoimintasäännön luominen](/powerapps/maker/common-data-service/data-platform-create-business-rule).
  
 Seuraavat ovat mahdollisia liiketoimintasääntöjen avulla, kun ehdot ja toiminnot yhdistetään:  
  
-   Määritä kentän arvot  
  
-   Kenttäarvojen tyhjentäminen  
  
-   Määritä kentän vaatimustasot  
  
-   Näytä tai piilota kentät  
  
-   Ota kenttiä käyttöön tai poista niitä käytöstä  
  
-   Tarkista tiedot ja näytä virhesanomat  
  
-   Suositusten luominen liiketoimintatietojen perusteella.  
  
## <a name="create-a-business-rule-or-business-recommendation"></a>Liiketoimintasäännön tai liiketoimintasuosituksen luominen
  
1. Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
  
2.  Avaa entiteetti, jolle liiketoimintasääntö luodaan (avaa esimerkiksi **Asiakas**-entiteetti), ja valitse sitten kaksoisnapsauttamalla **Liiketoimintasäännöt**.  
  
 ![Luo oletusratkaisun liiketoimintasääntö](media/create-business-rule-the-default-solution.png "Luo oletusratkaisun liiketoimintasääntö")  
  
3.  Valitse **Uusi**.  
  
     Avautuvassa liiketoimintasäännön suunnitteluikkunassa on luotu valmiiksi yksi ehto. Jokaisen säännön alussa on ehto. Liiketoimintasäännössä on vähintään yksi toiminto ehdon mukaan.  
  
 ![Liiketoimintasäännön suunnitteluikkuna](media/business-rules-design-window.png "Liiketoimintasäännön suunnitteluikkuna")  
  
   > [!TIP]
> Jos haluat muokata aiemmin luotua liiketoimintasääntöä, sen aktivointi on poistettava ennen muokkaamista.

4.  Voit lisätä kuvauksen ikkunan vasemmassa yläkulmassa olevaan kuvausruutuun.  
  
5.  Määritä vaikutusalue seuraavasti:  
  
    |||  
    |-|-|  
    |**Jos valitset tämän...**|**Vaikutusalueeksi määritetään...**|  
    |**Entiteetti**|Kaikki lomakkeet ja palvelin|  
    |**Kaikki lomakkeet**|Kaikki lomakkeet|  
    |Tietty lomake (esimerkiksi **Asiakas**-lomake)|Kyseinen lomake|  
  
6. **Lisää ehtoja**. Voit lisätä oman liiketoimintasääntöön lisää ehtoja seuraavasti:  
  
    1.  Vedä **Ehto**-osa **Osat**-välilehdestä suunnitteluohjelman plusmerkkiin.  
  
        ![Lisää liiketoimintasäännön ehto](media/add-condition-business-rule.png "Lisää liiketoimintasäännön ehto")  
  
    2.  Määritä tämän ehdon ominaisuudet valitsemalla suunnitteluikkunassa **Ehto**-osa ja määrittämällä sitten ominaisuudet näytön oikealla puolella **Ominaisuudet**-välilehdessä. Kun määrität ominaisuudet, lauseke luodaan **Ominaisuudet**-välilehden alareunassa.  
  
    3.  Voit lisätä lisälausekkeen (JA tai TAI) ehtoon valitsemalla **Uusi** **Ominaisuudet**-välilehdessä. Uusi sääntö luodaan, ja voit siiten määrittää säännön ominaisuudet. Voit määrittää **Sääntölogiikka**-kentässä lisätäänkö uusi sääntö JA- vai TAI-sääntönä.  
  
        ![Lisää ehdon uusi sääntö](media/add-new-rule-condition.png "Lisää ehdon uusi sääntö")  
  
    4.  Kun olet määrittänyt ehdon ominaisuudet, valitse **Käytä**.  
  
7. **Lisää toimintoja** Lisää toiminto näin:  
  
    1.  Vedä yksi toiminnon osista **Osat**-välilehdestä **Ehto**-osan vieressä olevaan plusmerkkiin. Vedä toiminto valintamerkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön tekevän kyseisen toiminnon, kun ehto toteutuu, tai x-merkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön tekevän kyseisen toiminnon, jos ehto ei toteudu.  
  
        ![Vedä toiminto liiketoimintasääntöön](media/drag-an-action-business-rule.png "Vedä toiminto liiketoimintasääntöön")  
  
    2.  Määritä toiminnon ominaisuudet valitsemalla suunnitteluikkunassa **Toiminto**-osa ja määrittämällä sitten ominaisuudet **Ominaisuudet**-välilehdessä.  
  
    3.  Kun olet määrittänyt ominaisuudet, valitse **Käytä**.  
  
8. **Lisää yrityssuositus** Lisää yrityssuositus näin:  
  
    1.  Vedä **Suositus**-osa **Osat**-välilehdestä **Ehto**-osan vieressä olevaan plusmerkkiin. Vedä **Suositus**-osa valintamerkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön tekevän kyseisen toiminnon, kun ehto toteutuu, tai x-merkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön tekevän kyseisen toiminnon, jos ehto ei toteudu.  
  
    2.  Määritä suosituksen ominaisuudet valitsemalla suunnitteluikkunassa **Suositus**-osa ja määrittämällä sitten ominaisuudet **Ominaisuudet**-välilehdessä.  
  
    3.  Voit lisätä uusia toimintoja suositukseen vetämällä ne **Osat**-välilehdestä ja määrittämällä sitten kunkin toiminnon ominaisuudet **Ominaisuudet**-välilehdessä.  
  
        > [!NOTE]
        >  Kun luot suosituksen, yksi toiminto lisätään oletusarvoisesti. Näet kaikki suosituksen toiminnot valitsemalla **Tiedot** **Suositus**-osassa.  
  
    4.  Kun olet määrittänyt ominaisuudet, valitse **Käytä**.  
  
9. Tarkista liiketoimintasääntö valitsemalla toimintorivillä **Tarkista**.  
  
10. Tallenna liiketoimintasääntö valitsemalla toimintorivillä **Tallenna**.  
  
11. Aktivoi liiketoimintasääntö valitsemalla se ratkaisunhallintaikkunassa ja valitsemalla sitten **Aktivoi**. Liiketoimintasääntöä ei voi aktivoida suunnitteluikkunasta.  
  
> [!TIP]
>  Seuraavassa on joitakin vinkkejä liiketoimintasääntöjen käsittelemiseen suunnitteluohjelman ikkunassa:  
>   
> - Voit ottaa liiketoimintasäännön ikkunan tapahtumista tilannevedoksen valitsemalla toimintorivillä **Tilannevedos**. Tämä on kätevää, jos esimerkiksi haluat jakaa liiketoimintasäännön ja saada siihen kommentteja ryhmän jäseneltä.  
> - Siirry nopeasti prosessin eri osiin pienoiskartan avulla. Tämä on kätevää, kun monimutkainen prosessi jatkuu näytön ulkopuolelle.  
> - Kun lisäät liiketoimintasääntöön ehtoja, toimintoja ja liiketoimintasuosituksia, liiketoimintasäännön koodi luodaan ja se tulee näkyviin suunnitteluohjelman alareunaan. Tätä koodia voi vain lukea.  
  
<a name="BKMK_LocalizingErrorMessages"></a>   
## <a name="localize-error-messages-used-in-business-rules"></a>Liiketoimintasäännöissä käytettävien virhesanomien lokalisoiminen  
 Jos organisaatiossa on käytössä useita kieliä, määritetyt virhesanomat kannattaa lokalisoida. Järjestelmä määrittää sanomalle otsikon sanoman luonnin yhteydessä. Jos viet käännökset organisaatioon, voit lisätä sanomien lokalisoidut versiot ja tuoda otsikot takaisin järjestelmään. Tällöin muuta kuin asennuskieltä käyttävät käyttäjät näkevät käännetyt sanomat.  

## <a name="common-issues"></a>Yleisiä ongelmia
Tässä osassa käsitellään yleisiä ongelmia, joita voi esiintyä liiketoimintasääntöjä käytettäessä. 

### <a name="full-name-field-not-supported-with-unified-interface-apps"></a>Koko nimi -kenttää ei tueta Unified Interface -sovelluksissa
**Koko nimi** (fullname) -kenttää käyttäviä toimintoja tai ehtoja ei tueta Unified Interfaceen perustuvissa sovelluksissa.  Vaihtoehtoisesti voit käyttää **Etunimi** (firstname)- ja **Sukunimi** (lastname) -kenttien toimintoja ja ehtoja. 

### <a name="is-your-business-rule-not-firing-for-a-form"></a>Jääkö lomakkeen liiketoimintasääntö käynnistymättä?
Liiketoimintasääntö saattaa jäädä suorittamatta, koska sääntö, johon kenttä viittaa, ei sisälly lomakkeeseen. 
1.  Avaa ratkaisunhallinta. Laajenna haluamasi entiteetti ja valitse **Lomakkeet**. 
2.  Avaa haluamasi lomake ja valitse lomakkeiden suunnitteluohjelman valintanauhasta **Liiketoimintasäännöt**. 
3.  Avaa liiketoimintasääntö lomakkeiden suunnitteluohjelmassa. 
4.  Valitse liiketoimintasäännön suunnitteluohjelmassa jokainen sääntö ja toiminto, joiden avulla niissä viitatut kentät vahvistetaan. 

     > [!div class="mx-imgBorder"] 
     > ![](media/business-rule-field.png "Liiketoimintasäännössä viitattu kenttä on entiteetissä")

 5. Vahvista, että jokainen liiketoimintasäännössä viitattu kenttä sisältyy myös lomakkeeseen. Jos näin ei ole, lisää puuttuva kenttä lomakkeeseen.

     > [!div class="mx-imgBorder"] 
     > ![](media/account-name-on-form.png "Asiakkaan nimi -kenttä lomakkeessa")

## <a name="frequently-asked-questions-faq"></a>Usein kysyttyjä kysymyksiä (FAQ)
*Voivatko liiketoimintasäännöt avata kenttiä vain luku -muodossa?*
- Kyllä, liiketoimintasääntö voi poistaa kenttien lukituksen ja muokata toimintoja vain luku -muodossa.

*Miten voin tehdä vianmäärityksen liiketoimintasäännölle, joka ei toimi?* 
- Katso [Jääkö lomakkeen liiketoimintasääntö käynnistymättä?](#is-your-business-rule-not-firing-for-a-form) tässä ohjeaiheessa.

## <a name="see-also"></a>Katso myös  
 [Mukautetun liiketoimintalogiikan luominen prosessien avulla](guide-staff-through-common-tasks-processes.md)   
 [Liiketoimintaprosessin luominen](/flow/create-business-process-flow)   


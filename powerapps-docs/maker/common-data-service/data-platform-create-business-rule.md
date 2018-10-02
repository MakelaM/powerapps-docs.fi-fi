---
title: Liiketoimintasäännön luominen Common Data Service sovelluksille -ratkaisussa | MicrosoftDocs
description: Liiketoimintasäännön luomisen vaiheittaiset vaiheet Common Data Service (CDS) sovelluksille -ratkaisussa.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-business-rule-for-an-entity"></a>Liiketoimintasäännön luominen entiteetille

Voit luoda liiketoimintasääntöjä ja -suosituksia käyttämällä logiikkaa ja tarkistuksia ilman koodin kirjoittamista ja laajennusten luomista. Liiketoimintasäännöt on yksinkertainen käyttöliittymä, jossa voi ottaa käyttöön ja ylläpitää nopeasti muuttuvia ja yleisesti käytettyjä sääntöjä. 
  
Seuraavat ovat mahdollisia liiketoimintasääntöjen avulla, kun ehdot ja toiminnot yhdistetään:  
  
* Määritä kentän arvot  
* Kenttäarvojen tyhjentäminen  
* Määritä kentän vaatimustasot  
* Näytä tai piilota kentät  
* Ota kenttiä käyttöön tai poista niitä käytöstä  
* Tarkista tiedot ja näytä virhesanomat  
* Suositusten luominen liiketoimintatietojen perusteella.  
  
## <a name="differences-between-canvas-and-model-driven-apps"></a>Kaaviosovellusten ja mallipohjaisten sovellusten väliset erot

Mallipohjaisia sovelluksia voi käyttää kaikissa liiketoiminnoissa käytettävissä olevissa toiminnoissa, mutta kaikki liiketoimintasäännön toiminnot eivät ole käytettävissä kaaviosovelluksissa tällä hetkellä. Seuraavat toiminnot **eivät** ole käytettävissä kaaviosovelluksissa:

* Näytä tai piilota kentät  
* Ota kenttiä käyttöön tai poista niitä käytöstä  
* Suositusten luominen liiketoimintatietojen perusteella.  

## <a name="prerequisites"></a>Edellytykset
Voit seurata tätä ohjeaihetta, jos vaihdat [ympäristöön](../canvas-apps/working-with-environments.md), jossa voit luoda ja muokata entiteettejä.

## <a name="create-a-business-rule"></a>Liiketoimintasäännön luominen
  
1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja napsauta tai napauta **Tiedot**-kohdan alanuolta lähellä vasemmanpuoleista reunaa.

2. Napsauta tai napauta **Entiteetit**-kohtaa näyttöön tulevassa luettelossa.
  
3. Avaa entiteetti, jolle liiketoimintasääntö luodaan (avaa esimerkiksi **Asiakas**-entiteetti), ja valitse sitten napsauttamalla **Liiketoimintasäännöt**-välilehti.  

4. Valitse **Uusi**.  
  
    Avautuvassa liiketoimintasäännön suunnitteluikkunassa on luotu valmiiksi yksi ehto. Jokaisen säännön alussa on ehto. Liiketoimintasäännössä on vähintään yksi toiminto ehdon mukaan.  

    > [!TIP]
    > Jos haluat muokata aiemmin luotua liiketoimintasääntöä, sen aktivointi on poistettava ennen muokkaamista.  
  
5. Voit lisätä kuvauksen ikkunan vasemmassa yläkulmassa olevaan kuvausruutuun.
  
6. Määritä vaikutusalue seuraavasti:  
  
    |||  
    |-|-|  
    |**Jos valitset tämän...**|**Vaikutusalueeksi määritetään...**|  
    |**Entiteetti**|Mallipohjaiset lomakkeet ja palvelin|  
    |**Kaikki lomakkeet**|Mallipohjaiset lomakkeet|  
    |Tietty lomake (esimerkiksi **Asiakas**-lomake)|Vain tietty mallipohjainen lomake|  

    > [!TIP]
    > Jos olet luomassa kaaviosovellusta, vaikutusalueena on käytettävä entiteettiä.
  
7. **Lisää ehtoja**. Voit lisätä oman liiketoimintasääntöön lisää ehtoja seuraavasti:  
  
    1. Vedä **Ehto**-osa **Osat**-välilehdestä suunnitteluohjelman plusmerkkiin.  
  
        ![Lisää liiketoimintasäännön ehto](./media/data-platform-cds-create-business-rule/add-condition-business-rule.png "Lisää liiketoimintasäännön ehto")  
  
    2. Määritä tämän ehdon ominaisuudet valitsemalla suunnitteluikkunassa **Ehto**-osa ja määrittämällä sitten ominaisuudet näytön oikealla puolella **Ominaisuudet**-välilehdessä. Kun määrität ominaisuudet, Common Data Service luo lausekkeen **Ominaisuudet**-välilehden alareunassa.  
  
    3. Voit lisätä lisälausekkeen (JA tai TAI) ehtoon valitsemalla **Uusi** **Ominaisuudet**-välilehdessä. Uusi sääntö luodaan, ja voit siiten määrittää säännön ominaisuudet. Voit määrittää **Sääntölogiikka**-kentässä lisätäänkö uusi sääntö JA- vai TAI-sääntönä.  
  
        ![Lisää ehdon uusi sääntö](./media/data-platform-cds-create-business-rule/add-new-rule-condition.png "Lisää ehdon uusi sääntö")  
  
    4. Kun olet määrittänyt ehdon ominaisuudet, valitse **Käytä**.  
  
8. **Lisää toimintoja** Lisää toiminto näin:  
  
    1. Vedä yksi toiminnon osista **Osat**-välilehdestä **Ehto**-osan vieressä olevaan plusmerkkiin. Vedä toiminto valintamerkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön tekevän kyseisen toiminnon, kun ehto toteutuu, tai x-merkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön tekevän kyseisen toiminnon, jos ehto ei toteudu.
  
        ![Vedä toiminto liiketoimintasääntöön](./media/data-platform-cds-create-business-rule/drag-an-action-business-rule.png "Vedä toiminto liiketoimintasääntöön")  
  
    2. Määritä toiminnon ominaisuudet valitsemalla suunnitteluikkunassa **Toiminto**-osa ja määrittämällä sitten ominaisuudet **Ominaisuudet**-välilehdessä.  
  
    3. Kun olet määrittänyt ominaisuudet, valitse **Käytä**.  
  
9. **Lisää liiketoimintasuositus (vain mallipohjainen)** Liiketoimintasuosituksen lisääminen:  
  
    1. Vedä **Suositus**-osa **Osat**-välilehdestä **Ehto**-osan vieressä olevaan plusmerkkiin. Vedä **Suositus**-osa valintamerkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön tekevän kyseisen toiminnon, kun ehto toteutuu, tai x-merkin vieressä olevaan plusmerkkiin, jos haluat liiketoimintasäännön tekevän kyseisen toiminnon, jos ehto ei toteudu.  
  
    2. Määritä suosituksen ominaisuudet valitsemalla suunnitteluikkunassa **Suositus**-osa ja määrittämällä sitten ominaisuudet **Ominaisuudet**-välilehdessä.  
  
    3. Voit lisätä uusia toimintoja suositukseen vetämällä ne **Osat**-välilehdestä ja määrittämällä sitten kunkin toiminnon ominaisuudet **Ominaisuudet**-välilehdessä.  
  
        > [!NOTE]
        >  Kun luot suosituksen, Common Data Service lisää oletusarvoisesti yhden toiminnon. Näet kaikki suosituksen toiminnot valitsemalla **Tiedot** **Suositus**-osassa.  
  
    4. Kun olet määrittänyt ominaisuudet, valitse **Käytä**.  
  
10. Tarkista liiketoimintasääntö valitsemalla toimintorivillä **Tarkista**.  
  
11. Tallenna liiketoimintasääntö valitsemalla toimintorivillä **Tallenna**.  
12. Aktivoi liiketoimintasääntö valitsemalla se ratkaisunhallintaikkunassa ja valitsemalla sitten **Aktivoi**. Liiketoimintasääntöä ei voi aktivoida suunnitteluikkunasta.  
  
    > [!TIP]
    >  Seuraavassa on joitakin vinkkejä liiketoimintasääntöjen käsittelemiseen suunnitteluohjelman ikkunassa:  
    >   
    > - Voit ottaa liiketoimintasäännön ikkunan tapahtumista tilannevedoksen valitsemalla toimintorivillä **Tilannevedos**. Tämä on kätevää, jos esimerkiksi haluat jakaa liiketoimintasäännön ja saada siihen kommentteja ryhmän jäseneltä.  
    > - Siirry nopeasti prosessin eri osiin pienoiskartan avulla. Tämä on kätevää, kun monimutkainen prosessi jatkuu näytön ulkopuolelle.  
    > - Kun lisäät liiketoimintasääntöön ehtoja, toimintoja ja liiketoimintasuosituksia, Common Data Service muodostaa suunnitteluohjelman ikkunan alareunaan liiketoimintasäännön koodin. Tämä koodi on vain luku -muodossa.  
  
## <a name="localize-error-messages-used-in-business-rules"></a>Liiketoimintasäännöissä käytettävien virhesanomien lokalisoiminen  
 Jos organisaatiossa on käytössä useita kieliä, määritetyt virhesanomat kannattaa lokalisoida. Järjestelmä määrittää sanomalle otsikon sanoman luonnin yhteydessä. Jos viet käännökset organisaatioon, voit lisätä sanomien lokalisoidut versiot ja tuoda otsikot takaisin Common Data Service -sovellukseen. Tällöin muuta kuin asennuskieltä käyttävät käyttäjät näkevät käännetyt sanomat.  
  

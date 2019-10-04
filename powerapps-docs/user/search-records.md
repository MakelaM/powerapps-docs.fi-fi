---
title: Tietueiden etsiminen mallipohjaisista sovelluksista | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 26903543232025f43f935a403800ed27170e3123
ms.sourcegitcommit: 7c46e7ce889e2f1c5352ed2e705b0bb8968f2a89
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940867"
---
# <a name="search-for-records-in-an-app"></a>Hae tietueita sovelluksesta

Voit hakea tietueita useista entiteeteistä käyttämällä osuvuus hakua tai luokiteltua hakua Common Data Service. 

- Osuvuus haku tarjoaa nopeat ja kattavat tulokset useille entiteeteille yhdessä listassa, lajiteltu soveltuvuuden mukaan. Se käyttää ulkoista haku palvelua, joka on Common Data Service (powered by [!INCLUDE[pn_Windows_Azure](../includes/pn-windows-azure.md)]), joka tehostaa haun suoritus kykyä. 
- Luokiteltu haku palauttaa haku tulokset ryhmiteltyinä entiteettityypin mukaan, kuten asiakkuudet, yhteys henkilöt tai liidit.

Yleensä luokiteltu haku on oletus haku vaihtoehto. Jos organisaatiosi on kuitenkin ottanut osuvuus haun käyttöön, siitä tulee oletusarvoinen haku kokemus.  

Jos haluat etsiä tietueita vain yhdestä tyypistä, voit käyttää pikahaku-näkymää entiteetin ruudukossa.
  
## <a name="normal-quick-find-categorized-search"></a>Normaali pikahaku (luokiteltu haku) 

Luokiteltu-toiminnolla voit hakea tietueita, jotka alkavat tietyllä sanalla tai käyttävät yleismerkkiä.
  
- **Alkaa**: Tulokset sisältävät tietueita, jotka alkavat tietyllä sanalla. Jos esimerkiksi haluat hakea kohdetta "Alpine Ski House", kirjoita haku ruutuun **Alp** . Jos kirjoitat **Ski**, tietuetta ei näytetä.  
  
- **Yleismerkki**: Esimerkiksi * Ski tai * Ski @ no__t-0. 
  
## <a name="relevance-search"></a>Osuvuus haku
  
  Osuvuus haku on käytettävissä muiden jo tuttujen Common Data Service hakujen lisäksi. Voit jatkaa yhden entiteetin pikahakua Entiteettiruudukon tai Multi-yksikön-pikahaulla (kutsutaan luokiteltu haku-toiminnolla, jos osuvuus haku on käytössä). Suosittelemme osuvuus haun käyttämistä kattavampia ja nopeampia tuloksia varten.  

 Osuvuus haku tuo mukanaan seuraavat parannukset ja edut:  
  
- Parantaa suoritus kykyä ulkoisella indeksoinnilla ja [!INCLUDE[pn_azure_shortest](../includes/pn-azure-shortest.md)]-haku tekniikalla.  
  
- Etsii vastineita mistä tahansa haku termin sanasta entiteetin missä tahansa kentässä. Vastaavu uksia voivat olla esimerkiksi **suoratoistetut**, **suoratoistetut**tai **suoratoistetut**sanat.  
  
- Palauttaa yhden luettelon kaikkien haettavien entiteettien tulokset osuvuuden mukaan lajiteltuina niiden tekijöiden mukaan, kuten sanojen määrä tai niiden läheisyys toisiinsa tekstissä.  
  
- Korostaa vastaavu uksia tulos listassa.  

- Löydät haku tulokset teksti tiedostosta, joka on tallennettu Common Data Service, mukaan lukien tekstin muistiinpanot, sähkö postin liitteet tai tapaamiset. Seuraavia tiedosto muotoja tuetaan haussa: PDF, Microsoft Office dokumentit, HTML, XML, ZIP, EML, pelkkä teksti ja JSON.  
  
- Voit etsiä tietueita, jotka on jaettu kanssasi ja omistamiesi tietueiden kanssa.  
  
  > [!NOTE]
  >  Hierarkkisia suojaus malleja ei tueta.  Vaikka näet rivin Common Data Service, koska voit käyttää sitä hierarkkisessa suoja uksessa, et näe tulosta osuvuus haussa.  
  
- Voit myös hakea asetus joukkoja ja hakuja. Oletetaan esimerkiksi, että haluat löytää jälleenmyyntikauppatilin, jonka nimessä on **lääkkeitä** . Kun haet **farmasian vähittäismyyntiä**, löydät tuloksen, koska toimiala kenttään on määritetty vastine, joka on haettavissa oleva asetus joukko.  
  
  Koska tulokset saattavat sisältää entiteettien yhdistelmän, voit rajata haku tuloksesi tiettyyn entiteettiin valitsemalla entiteetin avattavasta **Suodata** -valikosta. Kun suodatat tietylle tietue tyypille, voit sisällyttää valittuun tietueeseen liittyviä aktiviteetteja ja muistiinpanoja haku tuloksissa. Voit tehdä tämän valitsemalla **haku toiminnot ja valittujen tietueiden muistiinpanot** **-valinta ruudun avattavan luettelon** oikealla puolella. Valinta ruutu on valittuna sen jälkeen, kun valitset tietueen avattavasta **Suodata** -luettelosta. se tyhjennetään, jos et valinnut entiteettiä **suodatin-** luettelosta. Aktiviteetit ja muistiinpanot palautetaan ylimmän tason tuloina.
  
  > [!NOTE]
  > - Osuvuus haku on oletus arvon mukaan poistettu käytöstä. Järjestelmänvalvojasi on otettava se käyttöön organisaatiossa. Kun osuvuus haku on otettu käyttöön, sinun on ehkä odotettava jopa tunti tai enemmän organisaatiosi koon mukaan, ennen kuin alat nähdä osuvuus haku tuloksia sovelluksillesi. Pienemmillä indeksoitujen tietojen muutoksilla voi olla jopa 15 minuuttia aikaa näkyä järjestelmässäsi.
  > - Osuvuus haun avulla kaikki organisaation käyttäjät voivat käyttää sitä.  
  > - Osuvuus haku on tekstipohjainen, ja se voi hakea vain kentistä, joiden tyyppi on yksi teksti rivi, useita teksti rivejä, asetus joukkoja tai hakuja. Se ei tue etsimistä numeric-tai Date-tieto tyypin kentissä. 
  
 Vaikka osuvuus haku löytää vastineita mihin tahansa haku termin sanaan missä tahansa entiteetin kentässä, Pikahaku @ no__t-0even teksti haun ollessa käytössä @ no__t-1Kaikki haku termin sanat on löydettävä yhdestä kentästä.  
  
 Osuvuus haussa parempi vastaavuus, sitä suurempi se näkyy tuloksissa. Vastaavu uksien osuvuus on suurempi, jos haku termin enemmän sanoja löytyy toistensa läheisyydestä. Mitä pienempi on tekstin määrä, josta haku sanat löytyvät, sitä suurempi on osuvuus. Jos esimerkiksi löydät haku sanat yrityksen nimestä ja osoitteesta, se saattaa olla parempi vastaavuus kuin suuressa artikkelissa löytyneet sanat, kaukana toisistaan. Koska tulokset palautetaan yksittäisessä listassa, voit tarkastella tietueiden yhdistelmää, joka näytetään yksitellen, kuten asiakkuudet, mahdollisuudet, liidit ja niin edelleen. Listassa olevat vastaavat sanat korostetaan.  
  
 Hae haluamasi tulokset käyttämällä syntaksia haku termeillä. Kirjoita esimerkiksi **auto Silver 2-Door** , jos haluat sisällyttää haku tuloksiin haku termin minkä tahansa sanan haku tuloksissa. Kirjoita **auto + hopea +2-ovi** löytääksesi vain vastineita, jotka sisältävät kaikki kolme sanaa. Tyyppi **auto&#124;Silver&#124;2-Door** saada tuloksia, jotka sisältävät **auton** tai **hopean** tai **2-ovinen**, tai kaikki kolme sanaa. Lisä tietoja syntaksista, jota voit käyttää haku kyselyissä: [Yksinkertaisen kyselyn syntaksi Azure-haussa](https://docs.microsoft.com/rest/api/searchservice/simple-query-syntax-in-azure-search)


> [!NOTE]
> Näet osumien Koho kohdat, kun haku ehto vastaa sovelluksesi termiä. Osuma korostukset näkyvät lihavoiduksi ja kursivoiduksi tekstinä haku tuloksissa. Nämä palautetaan usein osana kentän täyttä arvoa, koska vain vastaavat termit korostetaan. 
  
  
<a name=" #BKMK_DefaultOption "></a>
## <a name="switch-between-relevance-and-categorized-search"></a>Vaihda osuvuuden ja luokitellun haun välillä

Jos organisaatiosi on ottanut käyttöön molemmat haku vaihtoehdot (osuvuus ja luokiteltu haku), voit vaihtaa näiden kahden välillä.

1. Jos haluat vaihtaa haku tyyppien välillä, valitse siirtymis palkissa **Hae** -painike.

2. Valitse vasemmalla oleva avattava valikko, jos haluat vaihtaa **osuvuus haun** tai **luokitellun haun**välillä.

   > [!div class="mx-imgBorder"]
   > ![Vaihda osuvuuden ja luokiteltujen hakujen]välillä(media/switch-search.png "osuvuuden ja luokitellun haun välillä") 
    
### <a name="set-a-default-experience"></a>Oletus käyttö kokemuksen asetukset

Jos organisaatiosi on ottanut molemmat haku vaihtoehdot käyttöön, voit valita oletus haku kokemuksen henkilökohtaisista asetuksistasi.

1. Valitse sivun oikeasta yläkulmasta **Asetukset** ja valitse sitten **mukautus asetukset**.  
  
   > [!div class="mx-imgBorder"]
   > ![Valitse oletus haku kokemus](media/relevance-search-personal-settings.png "Valitse oletus haku kokemus")  

2. Valitse **Yleiset** -väli lehden Valitse oletus **haku kokemus** -osiossa oletus **haku kokemustasi**varten oletus käyttö kokemuksesi. 

   > [!div class="mx-imgBorder"]
   > ![Valitse oletus haku kokemus](media/default.png "Valitse oletus haku kokemus")  
 


## <a name="start-a-search"></a>Aloita haku 
 
1.  Valitse yläreunan siirtymis palkista **haku** -painike.  
  
2.  Kirjoita haku sanat haku ruutuun ja valitse sitten **Hae** -painike.   

    > [!div class="mx-imgBorder"]
    > ![Haku vaihtoehdon](media/search-option.png "haku vaihtoehto")  
  
## <a name="filter-categorized-search-results"></a>Suodata luokitellut haku tulokset 
  
-   Jos haluat suodattaa tulokset yhden tietue tyypin mukaan, valitse Haku näytössä tietue tyyppi **suodatin:** -pudotus valikosta.  
  
-   Jos haluat tehdä hakuja kaikista tietue tyypeistä, valitse **suodatin:** -pudotus valikosta **ei mitään** .  

    > [!div class="mx-imgBorder"]
    > ![Suodata haku](media/filter-search.png "suodatin haku")  

## <a name="filter-records-with-facets-works-with-relevance-search"></a>Suodata tietueita käyttäen puolia (toimii osuvuus haulla)  
 Common Data Service avulla voit nyt tarkentaa haku tulojasi käyttämällä puolia ja suodattimia. Vasemmassa ruudussa on käytettävissä olevia puolia. Heti haun tekemisen jälkeen seuraavat yleiset puolet ovat käytettävissä neljälle yhteiselle kentälle:  
  
-   Tietue tyyppi  
  
-   Omistaja  
  
-   Luonti  
  
-   Muokattu  
  
### <a name="record-type-facets"></a>Tietue tyypin osa-alueet  
 Jos haluat rajata haku tulokset tiettyyn entiteettiin, valitse entiteetti **tietue tyyppi** -osiossa.  
 
  > [!div class="mx-imgBorder"]
  > ![Tietue tyyppi, joka kaventaa]haku tulosten(media/relevance-search-record-type-facet.png "kaventamiseksi käytettävää haku tulos tietue tyyppiä Facen")  
  
 Kun suodatat tietylle tietue tyypille, voit sisällyttää haku tuloksissa valittuun tietueeseen liittyviä tehtäviä ja muistiinpanoja. Voit tehdä tämän valitsemalla **Aiheeseen liittyvät muistiinpanot & aktiviteetit** -valinta ruudun. Aktiviteetit ja muistiinpanot näkyvät ylimmän tason tuloksissa.  
  
 
  > [!div class="mx-imgBorder"]
  > ![Sisällytä muistiinpanoihin ja toimintoihin, jotka liittyvät tietue tyyppiin haku tuloksissa],(media/relevance-search-record-type-facet-related-notes-activities.png "Sisällytä muistiinpanot ja toimet, jotka liittyvät tietue tyyppiin haku tuloksissa")  
  
 Sähkö postin liitteistä tai tapaamisen entiteeteistä löytyneet haku tulokset näkyvät niiden päätietueen, sähkö postin tai tapaamisen, haku tuloksissa.  
  
 Kun tarkennat tietue tyypin mukaan, vaihe-vaikutus alue vaihtuu valittuun entiteettiin ja neljä tiettyä entiteettiä olevaa puolta näytetään. Jos valitset esimerkiksi tili-entiteetin, näet **ensisijaisen yhteys tiedon** , joka on yleisten osa-kohteiden lisäksi.  
  
 **Määritä henkilökohtaiset asetukset** -valinta ikkunassa voit myös valita muita puolia niistä, jotka järjestelmänvalvoja tai asiakas on antanut käyttöösi. Käyttäjä asetus ohittaa oletus asetuksen. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [Määritä haun puolia ja suodattimia](#BKMK_ConfigureFacets)  
  
### <a name="text-based-facets"></a>Tekstipohjaiset alueet  
 Kaikki haut, asetus joukot ja tietue tyypit ovat tekstipohjaisia. Esimerkiksi tekstipohjainen vaiheen omistaja sisältää luettelon kenttien arvoista ja niiden vastaavista määristä.  
 
  > [!div class="mx-imgBorder"]
  > ![Tekstipohjainen vaihe osuvuus haussa](media/relevance-search-text-based-facets.png "tekstipohjaisen vaiheen osuvuus haussa")  
  
 Näiden osa-alue isiin sisältyvät suodattimet lajitellaan laskevassa järjestyksessä määrä-kohdan mukaan. Neljä ylintä puoli arvoa näytetään oletuksena. Kun osa-arvoja on yli neljä, näkyviin tulee **Näytä lisää** -linkki, jonka avulla voit laajentaa listaa ja nähdä enintään 15 ylintä puoli arvoa. Valitse jokainen arvo, jos haluat suodattaa haku tulokset näyttämään vain tietueet, joissa kentällä on valitsemasi arvo. Jos valitset esimerkiksi **Kim Abercrombie**, haku tuloksissa näkyvät kaikki tietueet, joissa omistaja on Kim Abercrombie. Kun valitset haku-tai asetus joukko-arvon, haku tulokset suodatetaan sisältämään vain tietueet, joiden arvo on määritetty.  
  
### <a name="date-and-time-facets"></a>Päivä määrän ja ajan osa-alueet  
 Kuten muutkin näkö kohdat, voit käyttää päivä määrä-ja aika-alueita suodattamaan ja katsomaan tietyn ajan haku tuloksia. Valitse arvo alue vetämällä liuku säädintä tai valitsemalla jokin pystysuuntaisista sarakkeista.  
 
  > [!div class="mx-imgBorder"]
  > ![Päivä määrä-ja aika-alueet osuvuus haun](media/relevance-search-date-time-facets.png "päivä määrä-ja aika-puoliin osuvuus haussa")  
  
<a name="BKMK_ConfigureFacets"></a>   
### <a name="configure-facets-and-filters-for-the-search"></a>Määritä haku alueet ja suodattimet  
 Puolia ja suodattimia avulla voit pora utua nykyiseen hakuasi ja tutkia sen tuloksia ilman, että sinun tarvitsee toistuvasti tarkentaa haku termiä. Määritä haluamasi alueet ja suodattimet **Määritä henkilökohtaiset asetukset** -valinta ikkunassa.  
  
> [!NOTE]
>  Järjestelmän mukauttaja voi määrittää kaikkien entiteettien oletus käyttö kokemuksen, mutta voit määrittää omia puolia ja suodattimia.  
  
#### <a name="to-configure-facets-for-yourself"></a>Voit määrittää pintoja itse  
  
1. Valitse sivun oikeasta yläkulmasta **Asetukset** ja valitse sitten **mukautus asetukset**.  
  
   > [!div class="mx-imgBorder"]
   > ![Valitse oletus haku kokemus](media/relevance-search-personal-settings.png "Valitse oletus haku kokemus")  
  
2. Valitse **Yleiset** -väli lehden **Valitse oletus haku kokemus** -osiossa **puolet ja suodattimet** -kentässä **Määritä**.  
  
3. Määritä **Määritä pinnat ja suodattimet** -valinta ikkunassa, mitä puolia haluat tarkastella entiteetille. Järjestelmänvalvoja tai mukauttaja voi valita kaikkien entiteettien oletus käyttö kokemuksen, mutta voit tehdä sen itse.  
  
   - Valitse avattavasta **Valitse entiteetti** -luettelosta entiteetti, jolle haluat määrittää puolia. Tämä avattava luettelo sisältää vain entiteetit, jotka on otettu käyttöön osuvuus hakua varten.  
  
   - Valitse valitulle entiteetille enintään neljä puoli kenttää. Oletus arvon mukaan valitun entiteetin **Pikahaku** -näkymän neljä ensimmäistä facetable-kenttää valitaan-listasta. Voit milloin tahansa valita vain neljä kenttää.  
  
     Voit päivittää useita entiteettejä yhdellä kertaa. Kun valitset **OK**, kaikkien määrittämiesi entiteettien muutokset tallennetaan. Jos haluat palauttaa aiemmin määritetyn entiteetin oletus toiminnan, valitse **oletus**.  
  
   > [!NOTE]
   > - Jos järjestelmän mukauttaja poistaa kentän tai tekee siitä enää haettavan, ja olet tallentanut tämän kentän puoli, se ei enää näy puoli pisteinä.  
   >   -   Näet vain oletus ratkaisussa olevat kentät, jotka on määritetty haettaviksi järjestelmämukauttajasi.  
  
 

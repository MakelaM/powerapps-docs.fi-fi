---
title: Koontikenttien määrittäminen PowerAppseilla | MicrosoftDocs
description: Opettele määrittämään koontikenttiä
ms.custom: ''
ms.date: 05/23/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: ff0504a1-01bd-4f9b-b884-7f84911d86c3
caps.latest.revision: 58
ms.author: matp
manager: kvivek
ms.openlocfilehash: c76162747ac2bda27c46895290e5943b7f46739f
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674432"
---
# <a name="define-rollup-fields-that-aggregate-values"></a>Arvoja koostavien koontikenttien määrittäminen

Koontikenttien avulla käyttäjät voivat saada merkityksellisiä tietoja valvomalla tärkeitä liiketoiminnan arvoja. Koontikenttä sisältää koostearvon, joka on laskettu tiettyyn tietueeseen liittyvistä tietueista. Tämä sisältää säännönmukaisia entiteettejä ja aktiviteettientiteettejä, kuten sähköpostiviestejä ja tapaamisia.

Monimutkaisemmissa tilanteissa voit koostaa tietoja tietueiden hierarkiasta. Järjestelmänvalvojana tai mukauttajana voit määrittää koontikenttiä mukauttamistyökalujen avulla PowerAppsissa kirjoittamatta koodia.  
  
<a name="BKMK_benefitsandcapabilities"></a> 
 
## <a name="rollup-fields-benefits-and-capabilities"></a>Koontikenttien edut ja ominaisuudet  

Koontikenttien etuja ja ominaisuuksia ovat seuraavat asiat:  
  
- Visualisoinnin muokkaaminen on helppoa. Voit luoda koontikenttiä kenttäeditorilla tavallisten kenttien tapaan.  
- Laaja valikoima koostefunktioita. Voit koostaa tietoja käyttämällä seuraavia funktioita: `SUM`, `COUNT`, `MIN`, `MAX` ja `AVG`.  
- Täysi suodatintuki koosteelle. Voit määrittää eri suodattimia lähde-entiteetille tai liittyvälle entiteetille määritettäessä useita ehtoja.  
- Käyttöliittymän saumaton integrointi. Voit sisällyttää koontikenttiä lomakkeisiin, näkymiin, kaavioihin ja raportteihin.  
- Koontikentät ovat ratkaisun osia. Voit siirtää koontikenttiä helposti osina ympäristöjen välillä ja jakaa ne ratkaisuihin.  
- Koontikentät ja lasketut kentät täydentävät toisiaan. Voit käyttää koontikenttää lasketun kentän osana ja päinvastoin.  
- Voit määrittää koontikenttiä käyttämään mukautettuja ohjausobjekteja.  
  
 Esimerkkejä koontikentistä:  
  
- Tilin avointen mahdollisuuksien arvioitu kokonaistuotto  
- Avointen mahdollisuuksien arvioitu kokonaistuotto kaikilla hierarkian tileillä  
- Mahdollisuuden arvioitu kokonaistuotto alimahdollisuudet mukaan lukien  
- Kampanjan luomien liidien arvioitu kokonaisarvo  
- Suuren prioriteetin avointen palvelupyyntöjen määrä kaikilla hierarkian tileillä  
- Kaikkien suuren prioriteetin avointen palvelupyyntöjen aikaisin luontiaika tilille  
  
Kukin koostekenttä luo kaksi lisävarustekenttää, joissa on  *&lt;fieldname&gt;*`_date`- ja *&lt;fieldname&gt;*`_state`-jälkiliitemalli. `_date`-kentässä on päivämäärä-/aikatietoja ja `_state`-kentässä on kokonaislukutietoja. `_state`-kentässä on seuraavat arvot:  
  
|Arvo|Tila|Kuvaus|  
|-|-|-|  
|0|NotCalculated|Kenttäarvo on vielä laskematta.|  
|1|Laskettu|Kenttäarvo on laskettu viimeisimmän päivitysajan mukaan _päivämäärä-kentässä.|  
|2|OverflowError|Kentän arvon laskutoimitus aiheutti ylivuotovirheen.|  
|3|OtherError|Kentän arvon laskutoimitus epäonnistui sisäisen virheen vuoksi. Laskutoimituksen seuraava suorittaminen todennäköisesti korjaa sen.|  
|4|RetryLimitExceeded|Kentän arvon laskutoimitus epäonnistui, koska arvon laskennan uudelleenyritysten enimmäismäärä ylitettiin samanaikaisuuden ja lukitusristiriitojen suuren määrän vuoksi.|  
|5|HierarchicalRecursionLimitReached|Kentän arvon laskutoimitus epäonnistui, koska laskutoimituksen enimmäishierarkiasyvyyden raja saavutettiin.|  
|6|LoopDetected|Kentän arvon laskutoimitus epäonnistui, koska tietueen hierarkiassa havaittiin rekursiivinen silmukka.|  
  
<a name="BKMK_calculations"></a>  
 
## <a name="rollup-calculations"></a>Koonnin laskutoimitukset  

Koonnit laskevat ajoitetut järjestelmätyöt, jotka suoritetaan asynkronisesti taustalla. Vain järjestelmänvalvojat voivat tarkastella ja hallita koontitöitä. 

### <a name="view-rollup-jobs"></a>Koontitöiden tarkasteleminen

Voit tarkastella koontitöitä seuraavasti:

1. Tarkastellessasi **Common Data Servicesin oletusratkaisua** muokkaa URL-osoitetta poistaen kaiken kohdan `dynamics.com` jälkeen ja päivitä sivu.
2. Valitse **Asetukset**-alueella **Järjestelmä** > **Järjestelmätyöt**.<br />![Siirry järjestelmätöihin](media/navigate-system-jobs.png)
1. Valitse näkymävalitsimessa **Toistuvat järjestelmätyöt**.
2. Löydät nopeasti asianmukaisen työn suodattamalla järjestelmätyön tyypin mukaan: **Koontikentän joukkolaskenta** tai **Laske koontikenttä**.
 
### <a name="mass-calculate-rollup-field"></a>Koontikentän joukkolaskenta

**Koontikentän joukkolaskenta** on toistuva työ, joka luodaan koontikenttää kohden. Se suoritetaan kerran koontikentän luomisen tai päivittämisen jälkeen. Työ laskee määritetyn koontikentän arvon kaikissa olemassa olevissa tietueissa, jotka sisältävät tämän kentän. Oletusarvon mukaan työ suoritetaan 12 tuntia kentän luomisen tai päivittämisen jälkeen. Kun työ on valmis, se ajoitetaan automaattisesti suoritettavaksi kaukaisessa tulevaisuudessa noin 10 vuoden kuluttua. Jos kenttää on muokattu, työ nollautuu suoritettavaksi uudelleen 12 tunnin kuluttua päivityksen jälkeen. 12 tunnin viive on tarpeen, jotta **Koontikentän joukkolaskenta** suoritetaan ympäristön ei-toiminnallisena aikana. On suositeltavaa, että järjestelmänvalvoja säätää **Koontikentän joukkolaskenta** -työn alkamisaikaa koontikentän luomisen tai muokkaamisen jälkeen siten, että se suoritetaan ei-toiminnallisena aikana. Esimerkiksi keskiyö olisi hyvä aika työn suorittamiselle koontikenttien tehokkaan käsittelyn varmistamiseksi.  

### <a name="calculate-rollup-field"></a>Laske koontikenttä 

**Laske koontikenttä** on toistuva työ, joka tekee lisääviä laskutoimituksia kaikille koontikentille määritetyn entiteetin olemassa olevissa tietueissa. Entiteettiä kohden on vain yksi **Laske koontikenttä** -työ. Lisäävät laskutoimitukset tarkoittavat sitä, että **Laske koontikenttä** -työ käsittelee tietueet, jotka on luotu, päivitetty tai poistettu viimeisen **Koontikentän joukkolaskenta** -työn suorittamisen jälkeen. Suurimman toistuvuuden oletusasetus on yksi tunti. Työ luodaan automaattisesti, kun entiteetin ensimmäinen koontikenttä luodaan, ja poistetaan, kun viimeinen koontikenttä poistetaan.  

## <a name="online-recalculation-option"></a>Online-uudelleenlaskenta-asetus
Jos viet kohdistimen lomakkeen koontikentän päälle, näet viimeisen koonnin ajan ja voit päivittää koontiarvon valitsemalla kentän vieressä olevan Päivitä-kuvakkeen alla kuvatulla:  

![Tililomakkeen koontikenttä](media/rollup-field-on-account-form.png)
  

Muutamia seikkoja kannattaa ottaa huomioon Online-uudelleenlaskenta-asetusta käytettäessä (lomakkeen manuaalinen päivitys):  
  
- Sinulla on oltava entiteetin kirjoitusoikeudet ja kirjoittamisen käyttöoikeudet sille lähdetietueelle, jolle pyydät päivitystä. Jos esimerkiksi lasket arvioitua tuottoa tilin avoimista mahdollisuuksista, sinulla ei tarvitse olla kirjoitusoikeuksia mahdollisuusentiteetille, ainoastaan tilientiteetille.  
- Tämä vaihtoehto on käytettävissä vain online-tilassa. Et voi käyttää sitä offline-tilassa.  
- Koontipäivityksen aikana tietueiden enimmäismäärä on rajoitettu 50 000 tietueeseen. Jos kyseessä on hierarkkinen koonti, tämä koskee koko hierarkian liittyviä tietueita. Jos raja ylitetään, näyttöön tulee virhesanoma: *Laskutoimituksia ei voida suorittaa online-tilassa, koska 50 000 liittyvän tietueen laskentaraja saavutettiin.* Tätä rajaa ei sovelleta, kun järjestelmätyöt laskevat koonnin uudelleen automaattisesti.  
- Lähdetietueen hierarkian enimmäissyvyytenä on 10. Jos raja ylitetään, näyttöön tulee virhesanoma: *Laskutoimituksia ei voida suorittaa online-tilassa, koska lähdetietueen hierarkian enimmäissyvyyden raja 10 saavutettiin.* Tätä rajaa ei sovelleta, kun järjestelmätyöt laskevat koonnin uudelleen automaattisesti.  

## <a name="modify-rollup-job-recurrence"></a>Koontityön toistumisen muokkaaminen

Järjestelmänvalvojana voit muokata koontityön toistumiskaavaa sekä lykätä, keskeyttää tai jatkaa koontityötä. Et kuitenkaan voi peruuttaa tai poistaa koontityötä. 

Jos haluat keskeyttää, lykätä, jatkaa tai muokata toistumiskaavaa, sinun on tarkasteltava järjestelmätöitä. Lisätietoja on kohdassa [Koontitöiden tarkasteleminen](#view-rollup-jobs) 

Valitse siirtymispalkissa **Toiminnot** ja valitse haluamasi toiminto. 

**Koontikentän joukkolaskenta** -työlle valittavissa olevat vaihtoehdot ovat **Jatka**, **Lykkää** ja **Keskeytä**. 

**Laske koontikenttä** -työlle valittavissa olevat vaihtoehdot ovat **Muokkaa toistoa**, **Jatka**, **Lykkää** ja **Keskeytä**.  
  
<a name="BKMK_businessscenarios"></a>  
 
## <a name="examples"></a>Esimerkkejä 

Katsotaanpa useita esimerkkejä koontikentistä. Koostamme tietoja tietueelle liittyvistä tietueista sekä hierarkian kanssa että ilman sitä. Koostamme tietoja tietueelle myös liittyvistä aktiviteeteistä sekä epäsuorasti tietueeseen liittyvistä aktiviteeteistä Aktiviteetin osapuoli -entiteetin kautta. Kussakin esimerkissä määritämme koontikentän kenttäeditoria käyttämällä. Avaa kenttäeditori avaamalla ratkaisunhallinta ja laajentamalla **Osat** > **Entiteetit**. Valitse haluamasi entiteetti ja valitse **Kentät**. Valitse **Uusi**. Anna editorissa tarvittavat tiedot kentälle, mukaan lukien **Kenttätyyppi** ja **Tietotyyppi**. **Kenttätyyppi**-kohdassa valitse **Koonti**, kun olet valinnut tietotyypin. Tietotyyppeihin sisältyvät desimaali- tai kokonaisluvut, valuutta sekä päivämäärä ja aika. Valitse **Muokkaa**-painike **Kenttätyyppi**-kohdan vieressä. Tämä vie sinut koontikentän määrityksen editoriin. Koontikentän määritys sisältää kolme osaa: **Lähde-entiteetti**, **Liittyvä entiteetti** ja **Kooste**.  
  
-   **Lähde-entiteetti**-osassa voit määrittää entiteetin, jolle koontikenttä määritetään, sekä sen, teetkö koostamisen hierarkian kautta. Voit lisätä useita ehtoja sisältäviä suodattimia määrittääksesi hierarkian tietueet, joita haluat käyttää koonnissa.  
  
-   **Liittyvät entiteetit** -osassa voit määrittää entiteetin, jonka kautta teet koostamisen. Tämä osa on valinnainen, kun valitset koonnin lähde-entiteetin hierarkian kautta. Voit lisätä useita ehtoja sisältäviä suodattimia määrittääksesi, mitä liittyviä tietueita käytät laskutoimituksessa. Esimerkiksi sisällytät tuoton avoimista mahdollisuuksista, joiden vuosittainen tuotto on suurempi kuin 1 000 $.  
  
-   **Kooste**-osassa voit määrittää arvon, jonka haluat laskea. Voit valita käytettävissä olevista koostefunktioista, kuten SUM, COUNT, MIN, MAX tai AVG.  
  
### <a name="aggregate-data-for-a-record-from-related-records"></a>Tietojen koostaminen tietueelle liittyvistä tietueista  

Tässä esimerkissä hierarkiaa ei käytetä. Arvioitu kokonaistuotto lasketaan tiliä kohden liittyvistä avoimista mahdollisuuksista.  

![Arvioidun tuoton koostaminen tilille](media/rollup-field-no-hierarchy.png)
  
### <a name="aggregate-data-for-a-record-from-the-child-records-over-the-hierarchy"></a>Tietojen koostaminen tietueelle alitietueista hierarkian kautta 
 
Tässä esimerkissä laskemme mahdollisuuden arvioidun kokonaistuoton, alimahdollisuudet mukaan lukien, hierarkian kautta.  
  
![Arvioidun tuoton koostaminen, mahdollisuuden hierarkia](media/rollup-field-hierarchy-self.png)
  
### <a name="aggregate-data-for-a-record-from-the-related-records-over-the-hierarchy"></a>Tietojen koostaminen tietueelle liittyvistä tietueista hierarkian kautta

Tässä esimerkissä laskemme avoimien mahdollisuuksien arvioidun kokonaistuoton kaikilla tileillä hierarkian kautta.  
  
![Arvioidun tuoton koostaminen tilin hierarkian kautta](media/rollup-field-hierarchy.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities"></a>Tietojen koostaminen tietueelle kaikista liittyvistä aktiviteeteistä
  
Tässä esimerkissä laskemme käytetyn ja laskutetun kokonaisajan kaikista tiliin liittyvistä aktiviteeteistä. Tähän voi kuulua puhelimessa, tapaamisissa tai mukautettujen aktiviteettien parissa käytetty aika.  
  
Aiemmissa versioissa oli mahdollista määrittää koontikenttä yksittäiselle aktiviteetille, kuten puhelulle, faksille tai tapaamiselle. Mutta alla olevan esimerkin tuloksen saamiseksi tiedot oli laskettava yhteen laskettuja kenttiä käyttämällä. Nyt voit tehdä kaiken yhdessä vaiheessa määrittämällä yhden koontikentän aktiviteettientiteetille.  
  
![Kaikkien tilin aktiviteettien koonti](media/rollup-enhancements-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities-and-activities-indirectly-related-via-the-activity-party-entity"></a>Tietojen koostaminen tietueelle kaikista liittyvistä aktiviteeteistä sekä epäsuorasti liittyvistä aktiviteeteistä Aktiviteetin osapuoli -entiteetin kautta  

Tässä esimerkissä laskemme niiden tilille lähetettyjen sähköpostiviestien kokonaismäärän, joissa tili on merkitty viestin Vastaanottaja- tai Kopion vastaanottaja -riville. Tämä tehdään määrittämällä **Osallistumistapa** **Suodattimet**-kohdassa Aktiviteetin osapuoli -entiteetille koontikentän määrityksessä. Jos et käytä suodatusta, aktiviteetin kaikkia saatavilla olevia osallistumistapoja käytetään laskutoimituksessa. 
 
Katso lisätietoja Aktiviteetin osapuoli -entiteetistä ja tietylle aktiviteetille saatavilla olevista osallistumistavoista kohdasta [Aktiviteetin osapuoli -entiteetti](/dynamics365/customer-engagement/developer/activityparty-entity).

  
![Liittyvien aktiviteettien ja aktiviteetin osapuolen koonti](media/rollup-enhancements-indirect-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-related-records-using-the-avg-operator"></a>Tietojen koostaminen tietueelle liittyvistä tietueista AVG-operaattoria käyttämällä

Tässä esimerkissä laskemme keskimääräisen arvioidun tuoton kaikista tiliin liittyvistä mahdollisuuksista.  
  
![Keskimääräinen arvioitu tuotto Dynamics 365:ssä](media/rollup-enhancements-average.PNG)  
  
Seuraavassa esimerkissä näytetään, miten voit laskea keskimääräisen arvioidun tuoton liittyvistä mahdollisuuksista tilihierarkian kautta. Keskimääräinen arvioitu tuotto on nähtävissä kullakin tasolla hierarkiassa.  
  
![Keskimääräinen arvioitu tuotto Dynamics 365:ssä](media/cust-rollup-enhancements-avg-over-hierarchy.png)  
  
<a name="BKMK_considerations"></a> 

## <a name="rollup-field-considerations"></a>Koontikentän huomioon otettavia seikkoja 

Ota huomioon tietyt ehdot ja rajoitukset, kun työskentelet koontikenttien kanssa:  
  
- Voit määrittää enintään 100 koontikenttää organisaatiolle ja enintään 10 koontikenttää entiteettiä kohden.  
- Koontikenttien päivitykset eivät voi käynnistää työnkulkua.  
- Työnkulun odotusehto ei voi käyttää koontikenttää.  
- Koontikentän koontia ei tueta.  
- Koonti ei voi viitata laskettuun kenttään, joka käyttää toista laskettua kenttää, vaikka toisen lasketun kentän kaikki muut kentät olisivat nykyisessä entiteetissä.  
- Koonti käyttää suodattimia vain lähde-entiteetissä tai liittyvissä entiteeteissä, yksinkertaisissa kentissä tai ei-monimutkaisissa lasketuissa kentissä.  
- Koonti voidaan tehdä vain sellaisten liittyvien entiteettien kautta, joissa on 1:N-suhde. Koontia ei voi tehdä N:N-suhteen kautta.  
- Koontia ei voi tehdä 1:N-suhteen kautta aktiviteettientiteetille tai Aktiviteetin osapuoli -entiteetille.  
- Liiketoimintasäännöissä, työnkuluissa ja lasketuissa kentissä käytetään aina koontikentän viimeistä laskettua arvoa.  
- Koontikenttä koostetaan järjestelmän käyttäjän kontekstissa. Kaikki käyttäjät voivat nähdä saman koontikentän arvon. Voit hallita koontikentän näkyvyyttä kenttätason suojauksella (FLS) rajoittamalla koontikentän käyttöoikeuksia. Lisätietoja  [Käyttöoikeuksien hallinta kenttätason suojausta käyttämällä](/dynamics365/customer-engagement/admin/field-level-security). 

### <a name="precision-rounding"></a>Tarkkuuden pyöristys
 
Jos koostamiskentän tarkkuus on suurempi kuin koontikentän tarkkuus, koostamiskentän tarkkuus pyöristetään alaspäin koontikentän tarkkuuteen, ennen kuin koostaminen suoritetaan. Seuraava esimerkki kuvaa tätä toimintaa. Oletetaan, että tilientiteetin koontikentällä, joka on liittyvien mahdollisuuksien arvioidun kokonaistuoton laskemista varten, on kahden desimaalin tarkkuus. Arvioitu tuotto -kenttä mahdollisuusentiteetissä on koostamiskenttä, jonka tarkkuus on neljä desimaalia. Tässä esimerkissä tilillä on kaksi liittyvää mahdollisuutta. Arvioidun tuoton koostettu summa lasketaan seuraavasti:  
  
1. Arvioitu tuotto ensimmäiselle mahdollisuudelle: 1000,0041 $  
1. Arvioitu tuotto toiselle mahdollisuudelle: 2000,0044 $  
1. Arvioidun tuoton koostettu summa: 1000,00 $ + 2000,00 $ = 3000,00 $

Kuten näet, tarkkuuden pyöristys kahteen desimaaliin koostamiskentässä tehdään ennen kuin koostaminen suoritetaan.  
  
### <a name="different-behavior-from-associated-grids"></a>Eri toiminta liittyvistä ruudukoista
 
Tietyt entiteettilomakkeet, kuten Tili tai Yhteyshenkilö, sisältävät valmiina liittyviä ruudukoita. Esimerkiksi Tili-lomake sisältää Yhteystiedot-, Palvelupyynnöt-, Mahdollisuudet- sekä muita ruudukoita. Jotkin Tili-lomakkeen ruudukoissa näkyvistä tietueista liittyvät suoraan tilitietueeseen ja toiset epäsuorasti suhteidensa kautta muihin tietueisiin. Koontikentän kooste taas käyttää ainoastaan suoria suhteita, jotka on nimenomaisesti määritetty koontikentän määrityksessä. Muita suhteita ei oteta huomioon. Toiminnan eroja havainnollistetaan seuraavassa esimerkissä.  
  
1. Tilillä A1 on ensisijainen yhteyshenkilö P1. Palvelupyyntö C1 liittyy tiliin A1 (C1.Asiakaskenttä = A1) ja palvelupyyntö C2 liittyy yhteyshenkilöön P1 (C2. Asiakaskenttä = P1).  
1. **Palvelupyynnöt**-ruudukko **Tili**-ruudukossa A1-tietueelle näyttää kaksi palvelupyyntöä: C1:n ja C2:n.  
1. Tilientiteetin Palvelupyyntöjen kokonaismäärä -koontikenttää käytetään tiliin liittyvien palvelupyyntöjen laskennassa.  
1. Tilin koontikentän määrityksessä määritämme palvelupyynnöt, joilla on asiakassuhde tiliin. Koostamisen jälkeen Palvelupyyntöjen kokonaismäärä on yhtä suuri kuin 1 (palvelupyyntö C1). Palvelupyyntö C2 ei sisälly kokonaismäärään, koska sillä on suora suhde yhteyshenkilöön, ei tiliin, eikä sitä voida erikseen määrittää tilin koontikentän määrityksessä. Näin ollen koontitoiminnon palauttamien palvelupyyntöjen kokonaismäärä ei vastaa **Palvelupyynnöt**-ruudukossa näkyvien palvelupyyntöjen määrää.  
  
### <a name="see-also"></a>Katso myös  

[Luo ja muokkaa kenttiä](create-edit-fields.md)<br />
[Laskettujen kenttien määrittäminen](define-calculated-fields.md)<br />
[Päivämäärä ja aika -kentän toiminta ja muoto](behavior-format-date-time-field.md)<br />
[Hierarkkisten tietojen määrittäminen ja kyselyjen tekeminen](define-query-hierarchical-data.md)<br />
[Video: Koontikentät ja lasketut kentät](http://www.youtube.com/watch?v=RoahCH1p3T8&list=PLC3591A8FE4ADBE07&index=8)<br />
[Video: Power BI:n käyttäminen](http://www.youtube.com/watch?v=PkQe4BFlBS8&list=PLC3591A8FE4ADBE07&index=3)

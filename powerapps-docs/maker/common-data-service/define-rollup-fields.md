---
title: Koontikenttien määrittäminen PowerAppsissa | MicrosoftDocs
description: Koontikenttien määrittäminen
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="define-rollup-fields-that-aggregate-values"></a>Määritä koontikenttiä, jotka kokoavat arvoja

Koontikentät auttavat käyttäjiä tärkeiden liiketoiminnan mittareiden seuraamisessa. Koontikenttä sisältää tiettyyn tietueeseen liittyvistä tietueista lasketun koontiarvon. Tämä sisältää tavallisia entiteettejä ja aktiviteettientiteettejä, kuten sähköposteja ja tapaamisia.

Monimutkaisissa tilanteissa voit koostaa tietoja tietuehierarkiasta. Järjestelmänvalvojana tai mukauttajana voit määrittää koontikenttiä käyttämällä mukautustyökaluja PowerAppsissa ilman koodin kirjoittamista.  
  
<a name="BKMK_benefitsandcapabilities"></a> 
 
## <a name="rollup-fields-benefits-and-capabilities"></a>Koontikenttien edut ja ominaisuudet  

Koontikentillä on seuraavia etuja ja ominaisuuksia:  
  
- Visuaalinen muokkaaminen on helppoa. Voit luoda koontikenttiä käyttämällä kenttäeditoria vastaavalla tavalla kuin tavallisten kenttien luonnissa.  
- Laaja valikoima koostefunktioita. Voit koostaa tiedot käyttämällä seuraavia toimintoja: `SUM`, `COUNT`, `MIN`, `MAX` ja `AVG`.  
- Täysi suodatinten tuki koostamiselle. Voit määrittää erilaisia suodattimia lähde-entiteetille tai liittyvälle entiteetille asettamalla useita ehtoja.  
- Saumaton integraatio käyttöliittymän kanssa. Voit sisällyttää koontikenttiä lomakkeille, näkymiin, kaavioihin ja raportteihin.  
- Koontikentät ovat ratkaisun osia. Voit siirtää helposti koontikenttiä osina ympäristöjen välillä ja jakaa niitä ratkaisuissa.  
- Koontikentät ja lasketut kentät ovat toisiaan täydentäviä. Voit käyttää koontikenttää osana laskettua kenttää ja päinvastoin.  
- Voit määrittää koontikentät niin, että ne käyttävät mukautettuja ohjausobjekteja.  
  
 Koontikenttäesimerkkejä:  
  
- Tilin avointen mahdollisuuksien arvioitu kokonaistuotto  
- Hierarkian kaikkien tilien avointen mahdollisuuksien arvioitu kokonaistuotto  
- Mahdollisuuden arvioitu kokonaistuotto alatason mahdollisuudet mukaan lukien  
- Kampanjan luomien hyväksyttyjen liidien arvioitu kokonaistuotto  
- Korkean prioriteetin avointen tapausten määrä hierarkian kaikissa tileissä  
- Tilin kaikkien tärkeiden avointen palvelupyyntöjen aikaisin luontiaika  
  
Jokainen koontikenttä luo kaksi apukenttää, joilla on jälkiliitteet *&lt;fieldname&gt;*`_date` ja *&lt;fieldname&gt;*`_state`. `_date`-kenttä sisältää päivämäärän ja ajan tiedot. `_state`-kenttä sisältää kokonaislukutiedot. `_state`-kentällä on seuraavat arvot ja niihin liittyvät kuvaukset:  
  
|Arvo|Osavaltio|Kuvaus|  
|-|-|-|  
|0|NotCalculated|Kentän arvoa ei ole vielä laskettu.|  
|1|Laskettu|Kentän arvo on laskettu viimeisen _päivämäärä-kentän päivitysajan mukaisesti.|  
|2|OverflowError|Kentän arvon laskenta aiheutti ylivuotovirheen.|  
|3|OtherError|Kentän arvon laskenta epäonnistui sisäisen virheen vuoksi. Seuraava laskentatyön suoritus voi korjata sen.|  
|4|RetryLimitExceeded|Kentän arvon laskenta epäonnistui, koska uudelleenyritysten enimmäismäärä arvon laskemiseksi ylittyi suuren yhdenaikaisuus- ja lukitusristiriitojen määrän vuoksi.|  
|5|HierarchicalRecursionLimitReached|Kentän arvon laskenta epäonnistui, koska laskentahierarkian enimmäissyvyys on saavutettu.|  
|6|LoopDetected|Kentän arvon laskenta epäonnistui, koska tietueen hierarkiassa havaittiin rekursiivinen silmukka.|  
  
<a name="BKMK_calculations"></a>  
 
## <a name="rollup-calculations"></a>Koostelaskennat  

Taustalla asynkronisesti suoritettavat ajastetut järjestelmätyöt laskevat koosteet. Vain järjestelmänvalvoja voi tarkastella ja hallita koostetöitä. 

### <a name="view-rollup-jobs"></a>Koostetöiden tarkasteleminen

Voit tarkastella koostetöitä seuraavasti:

1. Muokkaa **Common Data Services -oletusratkaisun** tarkastelemisen yhteydessä URL-osoitetta. Poista kaikki osoitteen `dynamics.com` jälkeiset merkit ja päivitä sivu.
2. Valitse **Asetukset**-alue ja valitse sitten **Järjestelmä** > **Järjestelmätyöt**.<br />![Järjestelmätöihin siirtyminen](media/navigate-system-jobs.png)
1. Valitse näkymävalitsimessa **Toistuvat järjestelmätyöt**.
2. Löydät nopeasti haluamasi projektin suodattamalla järjestelmätyön tyypin perusteella: **Koontikentän joukkolaskenta** tai **Koontikentän laskenta**.
 
### <a name="mass-calculate-rollup-field"></a>Koontikentän joukkolaskenta

**Koontikentän joukkolaskenta** on koontikenttäkohtaisesti luotu toistuva työ. Se suoritetaan kerran, kun olet luonut koontikentän tai päivittänyt sitä. Työ laskee tietyn koontikentän arvon kaikissa olemassa olevissa tietueissa, jotka sisältävät tämän kentän. Oletusarvoisesti työ suoritetaan 12 tuntia sen jälkeen, kun olet luonut tai päivittänyt kentän. Kun työ on valmis, se ajoitetaan automaattisesti suoritettavaksi tulevaisuudessa noin 10 vuoden kuluessa. Jos kenttää on muokattu, työ asettaa sen suoritettavaksi uudelleen 12 tuntia päivityksen jälkeen. 12 tunnin viive tarvitaan, jotta voidaan taata, että **koontikentän joukkolaskenta** suoritetaan ympäristön työajan ulkopuolella. On suositeltavaa järjestelmänvalvoja säätää **koontikentän joukkolaskennan** aloitusaika luonnin tai muutoksen jälkeen siten, että se suoritetaan työajan ulkopuolella. Hyvä työn suoritusaika on esimerkiksi keskiyö, jotta koontikentät käsitellään tehokkaasti.  

### <a name="calculate-rollup-field"></a>Koontikentän laskenta 

**Koontikentän laskenta** on toistuvan työ, joka suorittaa tietyn entiteetin olemassa olevien tietueiden kaikkien koontikenttien lisääviä laskelmia. Jokaisella entiteetillä on vain yksi **Koontikentän laskenta** -työ. Lisäävä laskeminen tarkoittaa, että **Koontikentän laskenta** -työ käsittelee tietueet, jotka luotiin, päivitettiin tai poistettiin viimeisen **Koontikentän joukkolaskenta** -työnsuorituksen jälkeen. Suurin toistumisen oletusasetus on yksi tunti. Työ luodaan automaattisesti, kun entiteetin ensimmäinen koontikenttä luodaan ja poistetaan, kun viimeinen koontikenttä poistetaan.  

## <a name="online-recalculation-option"></a>Uudelleenlaskenta verkossa -vaihtoehto
Jos viet osoittimen lomakkeen koontikentän päälle, näet viimeisen koosteen ajan ja voit päivittää koosteen arvoa napsauttamalla Päivitä-kuvaketta kentän vieressä alla olevan kuvan mukaisesti:  

![Asiakaslomakkeen koontikenttä](media/rollup-field-on-account-form.png)
  

Uudelleenlaskenta verkossa -vaihtoehtoa käytettäessä on pidettävä mielessä muutamia asioita (lomakkeen manuaalinen päivitys):  
  
- Sinulla on oltava sen entiteetin ja lähdetietueen kirjoitusoikeudet, jolle pyydät päivitystä. Jos lasket esimerkiksi tilin avointen mahdollisuuksien arvioitua myyntituottoa, sinulla ei tarvitse olla kirjoitusoikeuksia mahdollisuus-entiteettiin, vain tili-entiteettiin.  
- Tämä asetus on käytettävissä vain online-tilassa. Sitä ei voi käyttää offline-tilassa.  
- Tietueiden enimmäismäärä on rajoitettu koosteen päivityksen 50 000 tietueeseen. Hierarkkisen koosteen tapauksessa tämä koskee liittyviin tietueisiin hierarkiassa. Jos aikarajoitus ylittyy, näet virheilmoituksen: *Laskelmia ei voi tehdä online-tilassa, koska on saavutettu liittyvien tietueiden laskennan enimmäisraja 50 000 liittyvää tietuetta.* Tätä rajaa ei sovelleta, kun järjestelmätyöt laskee koosteen automaattisesti.  
- Hierarkian enimmäissyvyys on rajoitettu arvoon 10 lähdetietueelle. Jos raja ylittyy, näet virheilmoituksen: *Laskelmia ei voi tehdä online-tilassa, koska on saavutettu hierarkian syvyysrajoitus 10 lähdetietueelle.* Tätä rajaa ei sovelleta, kun järjestelmätyöt laskee koosteen automaattisesti.  

## <a name="modify-rollup-job-recurrence"></a>Koostetyön toiston muokkaaminen

Järjestelmänvalvojana voit muokata koostetyön toistuvuutta, lykätä, keskeyttää tai jatkaa koostetyön suorittamista. Et voi kuitenkaan peruuttaa tai poistaa koostetyötä. 

Voit keskeyttää toistuvuuden tai lykätä, jatkaa tai muokata sitä tarkastelemalla järjestelmätöitä. Lisätietoja on kohdassa [Koostetöiden tarkasteleminen](#view-rollup-jobs) 

Valitse siirtymispalkissa **Toiminnot** ja valitse haluamasi toiminto. 

**Koontikenttien joukkolaskenta** -työlle käytettävissä olevat valinnat ovat: **Jatka**, **Lykkää** ja **Keskeytä**. 

**Koontikentän laskenta** -työlle käytettävissä olevat valinnat ovat: **Muokkaa toistoa**, **Jatka**, **Lykkää** ja **Keskeytä**.  
  
<a name="BKMK_businessscenarios"></a>  
 
## <a name="examples"></a>Esimerkit 

Seuraavassa on joitakin koontikenttäesimerkkejä. Esimerkissä yhdistämme tietueen tietoja liittyvistä tietueista hierarkian avulla ja hierarkiaa käyttämättä. Koostamme tietueen tiedot liittyvistä aktiviteeteista ja epäsuorasti tietueeseen liittyvistä aktiviteeteista ActivityParty-entiteetin kautta. Määritämme jokaisessa esimerkissä koontikentän kenttäeditorin avulla. Avaa kenttäeditori avaamalla ratkaisunhallinta ja laajentamalla **Osat** > **Entiteetit**. Valitse ensin haluamasi entiteetti ja sitten **Kentät**. Valitse **Uusi**. Anna editorissa vaadittavat kentän tiedot, mukaan lukien **Kentän tyyppi** ja **Tietotyyppi**. Valitse **Kentän tyyppi** kohdassa **Kooste**, kun olet valinnut tietotyypin. Tietotyyppejä ovat desimaali- tai kokonaisluvut, valuutta ja päivämäärä/kellonaika. Napsauta **Muokkaa**-painiketta **Kentän tyyppi** -kentän vieressä. Tämä avaa koontikentän määritys -editorin. Koontikentän määritys muodostuu kolmesta osasta: **Lähde-entiteetti**, **Liittyvä entiteetti** ja **Kooste**.  
  
-   **Lähde-entiteetti** -osassa määrität entiteetin jolle koontikenttä on määritetty ja koostetaanko hierarkian kautta. Voit lisätä suodattimia useilla ehdoilla määrittääksesi hierarkian tietueet joita haluat käyttää koosteeseen.  
  
-   **Liittyvä entiteetti** -osassa voit määrittää entiteetin jonka kautta koostetaan. Tämä osa on valinnainen, kun valitset koostamisen lähde-entiteetin hierarkian kautta. Voit lisätä suodattimia useilla ehdoilla määrittääksesi mitä liittyviä tietueita laskennassa käytetään. Jos esimerkiksi sisällytät sellaisten avointen mahdollisuuksien tuoton joiden vuosituotto on suurempi kuin 1000 €.  
  
-   **Kooste** -osassa voit määrittää mittarin, jonka haluat laskea. Voit valita käytettävissä olevista koostefunktioista, kuten SUM, COUNT, MIN, MAX tai AVG.  
  
### <a name="aggregate-data-for-a-record-from-related-records"></a>koontitiedot tietueelle liittyvistä tietueista  

Tässä esimerkissä ei käytetä hierarkiaa. Tilille lasketaan arvioitu kokonaistuotto liittyvistä avoimista mahdollisuuksista.  

![Tilin arvioitujen tulojen kokoaminen](media/rollup-field-no-hierarchy.png)
  
### <a name="aggregate-data-for-a-record-from-the-child-records-over-the-hierarchy"></a>Koontitiedot tietueelle alitietueista hierarkian kautta. 
 
Tässä esimerkissä laskemme mahdollisuuden arvioidun kokonaistuoton mukaan lukien alatason mahdollisuudet hierarkiassa.  
  
![Kooste arvioidusta myyntituotosta, mahdollisuushierarkia](media/rollup-field-hierarchy-self.png)
  
### <a name="aggregate-data-for-a-record-from-the-related-records-over-the-hierarchy"></a>Koontitiedot tietueelle liittyvistä tietueista hierarkian kautta.

Tässä esimerkissä laskemme mahdollisuuden arvioidun kokonaistuoton kaikkien tilien osalta hierarkian kautta.  
  
![Kooste arvioidusta myyntituotosta tilihierarkian yllä](media/rollup-field-hierarchy.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities"></a>Koostetiedot tietueelle kaikista liittyvistä aktiviteeteista
  
Tässä esimerkissä laskemme käytetyn ja lasketun kokonaisajan kaikista asiakkaaseen liittyvistä aktiviteeteista. Tähän voi sisältää puhelimessa, tapaamisissa tai mukautetuissa toiminnoissa käytetyn ajan.  
  
Aiemmissa versioissa pystyit määrittämään koontikentän yksittäiselle aktiviteetille, kuten puhelulle, faksille tai tapaamiselle. Mutta alla olevan esimerkin saavuttamiseksi sinun oli luotava kokonaissumma laskennallisten kenttien avulla. Nyt voit tehdä kaiken yhdessä vaiheessa määrittämällä koontikentän aktiviteettientiteetille.  
  
![Kaikkien tilin aktiviteettien kooste](media/rollup-enhancements-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities-and-activities-indirectly-related-via-the-activity-party-entity"></a>Tietueen tietojen koostaminen kaikista liittyvistä aktiviteeteista ja epäsuorasti tietueeseen liittyvistä aktiviteeteista Activity Party -entiteetin kautta.  

Tässä esimerkissä laskemme asiakkaalle lähetettyjen sähköpostiviestien kokonaismäärän, jossa asiakas on "Vastaanottaja"- tai "Kopio"-rivillä. Tämä tehdään määrittämällä **Osallistumistapa** kohdassa **SUODATTIMET**-aktiviteettiosapuolelle koontikentän määrityksessä. Jos et käytä suodatusta, laskennassa käytetään kaikkia aktiviteetin käytettävissä olevia osallistumistyyppejä. 
 
Lisätietoja tietyn aktiviteetin aktiviteetin osapuolientiteetistä ja käytettävissä olevista osallistumistyypeistä on kohdassa [ActivityParty-entiteetti](/dynamics365/customer-engagement/developer/activityparty-entity).

  
![Koosta liittyvät aktiviteetit ja aktiviteetin osapuolet](media/rollup-enhancements-indirect-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-related-records-using-the-avg-operator"></a>Koostetiedot tietueelle liittyvistä tietueista käyttämällä AVG-operaattoria

Tässä esimerkissä laskemme keskimääräisen arvioidun tuoton kaikista asiakkaaseen liittyvistä mahdollisuuksista.  
  
![Keskimääräinen arvioitu tuotto Dynamics 365:ssä](media/rollup-enhancements-average.PNG)  
  
Seuraavasta esimerkistä näkyy, kuinka liittyvien mahdollisuuksien keskimääräinen arvioitu tuotto lasketaan asiakashierarkian kautta. Keskimäärin arvioitu tuotto voidaan nähdä hierarkian jokaisella tasolla.  
  
![Keskimääräinen arvioitu tuotto Dynamics 365:ssä](media/cust-rollup-enhancements-avg-over-hierarchy.png)  
  
<a name="BKMK_considerations"></a> 

## <a name="rollup-field-considerations"></a>Koontikenttään liittyviä huomioita 

Sinun tulisi huomioida tietyt ehdot ja rajoitukset, kun työskentelet koontikenttien kanssa:  
  
- Voit määrittää enintään 100 koontikenttää organisaatiossa ja enintään 10 koontikenttää yhdelle entiteetille.  
- Työnkulkua ei voi käynnistää koontikentän päivityksillä.  
- Työnkulun odotusehto ei voi käyttää koontikenttää.  
- Koontikentän koostetta ei tueta.  
- Koonti ei voi viitata laskennalliseen kenttään, joka käyttää toista laskennallista kenttää, vaikka kaikki toisen laskennallisen kentän kentät kuuluisivat nykyiseen entiteettiin.  
- Kooste voi käyttää suodattimia vain lähde-entiteettiin tai liittyviin entiteetteihin, yksinkertaisiin kenttiin tai ei monimutkaisiin laskennallisiin kenttiin.  
- Kooste voidaan suorittaa vain liittyville entiteeteille suhteella 1:N. Koostetta ei voida suorittaa N:N-suhteiden kautta.  
- Koostetta ei voida suorittaa 1:N-suhteessa aktiviteettientiteetille tai aktiviteetin osapuolen entiteetille.  
- Liiketoimintasäännöt, työnkulut tai laskennalliset kentät käyttävät aina koontikentän viimeistä laskettua arvoa.  
- Koontikenttä yhdistetään järjestelmän käyttäjän kontekstissa. Kaikki käyttäjät näkevät saman koontikentän arvon. Voit hallita koontikentän näkyvyyttä kenttätason suojauksella (FLS) rajoittamalla koontikentänkäyttöoikeuksia. Lisätietoja: [Käytön hallinta kenttätason suojauksen avulla](/dynamics365/customer-engagement/admin/field-level-security). 

### <a name="precision-rounding"></a>Tarkkuuden pyöristäminen
 
Jos koostamiskentän tarkkuus on korkeampi kuin koontikentän tarkkuus, koostamiskentän tarkkuus pyöristetään alaspäin koontikentän tarkkuuteen ennen koostamista. Toimintaa valaisee seuraava esimerkki. Oletetaan, että Asiakas-entiteetin koontikentän tarkkuus on liittyvien mahdollisuuksien kokonaistuloksen arvion laskennassa kahden desimaalin tarkkuudella. Arvioitu myyntituotto -kenttä mahdollisuusentiteetissä on koostamiskenttä, jonka tarkkuus on neljä desimaalia. Esimerkkitilillämme on kaksi liittyvää mahdollisuutta. Arvioidun myyntituoton koostettu summa lasketaan seuraavasti:  
  
1. Arvioitu Ensimmäisen mahdollisuuden myyntituotto: 1000,0041 €  
1. Arvioitu Toisen mahdollisuuden myyntituotto: 2000,0044 €  
1. Koostettu summa arvioidusta Myyntituotto: 1000,00 $ + 2000,00 $ = 3000,00 $

Kuten näet, pyöristys kahteen desimaaliin koostamiskenttään tehdään ennen koostamista.  
  
### <a name="different-behavior-from-associated-grids"></a>Liittyvien ruudukkojen erilainen toimintatapa
 
Tiettyjen entiteettien lomakkeet, kuten Tili tai Yhteyshenkilö, sisältävät valmiiksi liitetyt ruudut. Esimerkiksi Asiakkuus-lomake sisältää Yhteyshenkilö-, Tapaus-, Mahdollisuus- ja muita ruudukoita. Jotkin Tili-lomakkeen ruuduissa näytettävät tietueet ovat suoraan liitoksissa tilin tietueen kanssa; muiden tietueiden liitos muodostuu epäsuorasti suhteista muiden tietueiden kanssa. Vertailun vuoksi koontikentän kooste käyttää ainoastaan erikseen koontikentälle määritettyjä suoria yhteyksiä. Muita yhteyksiä ei oteta huomioon. Toiminnallisuuden eroa valaisee seuraava esimerkki.  
  
1. Tilillä A1 on liitetty pääkontakti P1. Tapaus C1 on liitetty tiliin A1 (C1.Asiakas -kenttä = A1) ja tapaus C2 on liitetty yhteyshenkilöön P1 (C2.Asiakas -kenttä = P1).  
1. A1-tietueen **Tili**-lomakkeen **Tapaukset**-ruudukko näyttää kaksi tapausta, C1 ja C2.  
1. Asiakas-entiteetin koontikentän nimi on Tapausten kokonaismäärä, ja sitä käytetään asiakkaaseen liitettyjen tapausten laskemiseen.  
1. Asiakkaan koontikentälle on määritelty tapaukset, joilla on asiakkaan kanssa asiakassuhde. Koostamisen jälkeen Tapausten kokonaismäärä on 1 (tapaus C1) Tapausta C2 ei lasketa mukaan, koska se liittyy suoraan yhteystietoon asiakkaan sijaan, eikä sitä voi määrittää suoraan asiakkaan koontikentän määrityksessä. Tämän vuoksi koontikentässä näkyvä tapausten kokonaismäärä ei vastaa **Tapaukset**-ruudulla näkyvää määrää.  
  
### <a name="see-also"></a>Katso myös  

[Kenttien luominen ja muokkaaminen](create-edit-fields.md)<br />
[Laskennallisten kenttien määrittäminen](define-calculated-fields.md)<br />
[Päivämäärän ja kellonajan kentän toimintatapa ja muoto](behavior-format-date-time-field.md)<br />
[Hierarkkisesti järjestettyjen tietojen määrittäminen ja kysely](define-query-hierarchical-data.md)<br />
[Video: Koontikentät ja laskennalliset kentät](http://www.youtube.com/watch?v=RoahCH1p3T8&list=PLC3591A8FE4ADBE07&index=8)<br />
[Video: Power BI:n käyttäminen CRM 2015:n kanssa](http://www.youtube.com/watch?v=PkQe4BFlBS8&list=PLC3591A8FE4ADBE07&index=3)

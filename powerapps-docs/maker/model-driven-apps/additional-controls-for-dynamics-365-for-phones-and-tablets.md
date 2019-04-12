---
title: Dynamics 365 puhelimille ja taulutietokoneille -sovelluksen lisäohjausobjektit | MicrosoftDocs
description: Dynamics 365 puhelimille ja taulutietokoneille -sovelluksen kanssa käytettävien ohjausobjektien luettelo
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 7920ef78-2540-48ad-ba25-9ce9cb995ed1
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="additional-controls-for-dynamics-365-for-phones-and-tablets"></a>Lisää ohjausobjekteja Dynamics 365 puhelimille ja taulutietokoneille -sovellukseen 

 Käytettävissäsi on laaja valikoima ohjausobjekteja, joilla voit luoda lisää käyttäjäystävällisiä toimintoja Dynamics 365 puhelimille ja taulutietokoneille -sovellukseen. Näitä ovat liukusäätimiä, kytkimet, multimedian toisto, syöttörajoitteita, kalenteri ja muita ohjausobjekteja.  

 
> [!NOTE]
>  Voit käyttää näitä vain mobiilisovelluksissa. Ne eivät tue web-sovellusta.  
  
 Ohjausobjektien käyttäminen lomake-editorissa:  
  
1.  Avaa ohjausobjektin kohteena oleva kenttä tai luettelo kaksoisnapsauttamalla.  
  
2.  Napsauta **Ohjausobjektit**-välilehteä.  
  
3.  Valitse **Lisää ohjausobjekti**.  
  
4.  Valitse haluamasi ohjausobjekti ja valitse sitten **Lisää**.  
  
    > [!NOTE]
    >  Eri ohjausobjekteja on käytettävissä kenttä- tai luettelotyypin mukaan. Esimerkiksi liukusäädin ohjaa vain numeerinen tai rahasumman sisältävät kentät ja kalenteriohjausobjektia voi käyttää vain luetteloissa.  
  
5.  Valitse laitteet, jonka haluat näyttävän ohjausobjektin (puhelin, taulutietokone tai molemmat). Ohjausobjektit eivät ole käytettävissä puhelimen otsikkokentät.  
  
6.  Määritä kunkin ominaisuuden arvot.  
  
7.  Valitse **OK** kun olet tehnyt ohjausobjektin määrittäminen.  
  
 Seuraavassa on kuvaukset kunkin ohjausobjektin, joita voit käyttää Dynamics 365 puhelimille ja taulutietokoneille -sovelluksen lomakkeissa.  
  
## <a name="calendar-control"></a>Kalenterin ohjausobjekti  
 Tällä toiminnolla voit määrittää lomakkeet niin, että ne näyttävät kalenterinäkymän Dynamics 365 puhelimille ja taulutietokoneille -sovelluksessa. Tämän ohjausobjektin avulla voit korvata koontinäytöt, luettelot tai entiteettiruudukot puhelimissa ja taulutietokoneissa.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Aloituspäivä|Määritä alkamispäivämäärä ja kellonaika kohteelle, joka visualisoidaan kalenterinäkymässä. Käytettävissä olevat arvot ovat päivämäärätyyppiä olevat sarakkeet.|  
|Päättymispäivä|Määritä päättymispäivämäärä ja kellonaika kohteelle, joka visualisoidaan kalenterinäkymässä. Käytettävissä olevat arvot ovat päivämäärätyyppiä olevat sarakkeet.|  
|Kesto|Kesto minuutteina. Jos määrität päättymispäivämäärän arvon, kesto ohitetaan.|  
|Kuvaus|Tämä on kuvateksti, jonka haluat nähdä kalenterikohteissa.|  
  
 Kalenterissa näkyvä vähimmäiskesto on 30 minuuttia. Jos kohteen kesto on alle 30 minuuttia, se näkyy 30 minuuttia pitkänä.  
  
 Kalenteriohjausobjekti tukee kaikkia päivämäärän ominaisuuksia (paikallinen käyttäjä, vain päivämäärä ja aikavyöhykkeestä riippumaton).  
  
## <a name="timeline-control"></a>Aikajanan ohjausobjekti  
 Tuottaa aikajanan tilin äskettäisistä olennaisista uutisartikkeleista ja Twitterin twiiteistä.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|CC_Timeline_Title|Ominaisuus, joka yhdistää aikajanan kunkin kohteen otsikon.|  
|CC_Timeline_Title_Desc|Otsikon kuvaus.|  
|CC_Timeline_Label1|Aikajanan osan otsikon alapuolella näytettävä kenttä.|  
|CC_Timeline_Label1_Desc|Otsikon 1 kuvaus.|  
|CC_Timeline_Label2|Kenttä otsikon 1 jälkeen.|  
|CC_Timeline_Label2_Desc|Otsikon 2 kuvaus.|  
|CC_Timeline_Label3|Kenttä otsikon 2 jälkeen.|  
|CC_Timeline_Label3_Desc|Otsikon 3 kuvaus.|  
|CC_Timeline_Label4|Kenttä otsikon 3 jälkeen.|  
|CC_Timeline_Label4_Desc|Otsikon 4 kuvaus.|  
|CC_Timeline_Label5|Kenttä otsikon 4 jälkeen.|  
|CC_Timeline_Label5_Desc|Otsikon 5 kuvaus.|  
|CC_Timeline_Timestamp|Kenttä, jota käytetään, kun aikajana määritetään käänteisessä aikajärjestyksessä.|  
|CC_Timeline_Timestamp_Desc|Aikajanan kuvaus.|  
|CC_Timeline_Group|Aikajanan ryhmittelyä varten yhdistettävä kenttä.|  
|CC_Timeline_Group_Desc|Ryhmä-kentän kuvaus.|  
|CC_Timeline_GroupOrder|Ryhmän järjestys, johon kohde kuuluu, suhteessa muihin ryhmiin (määritä arvot 1, 2, 3 ja niin edelleen näytettäville ryhmille). Ryhmä näkyy nousevassa järjestyksessä määritettyjen ryhmän arvojen mukaan.|  
|CC_Timeline_GroupOrder_Desc|Ryhmän järjestys -kentän kuvaus.|  
|CC_Timeline_URL|URL-kenttä, joka yhdistää aikajanan kunkin kohteen näytettävän URL-osoitteen.|  
|CC_Timeline_URL_Desc|URL-kentän kuvaus|  
|CC_Timeline_ThumbnailURL|Kenttä, joka yhdistää näytettävän pikkukuvan tai kuvakkeen kunkin nimikkeen osalta.|  
|CC_Timeline_ThumbnailURL_Desc|`ThumbnailURL`-kentän kuvaus.|  
|CC_Timeline_Filter|Aikajanan suodatusta varten yhdistettävä kenttä.|  
|CC_Timeline_Filter_Desc|Suodattimen kuvaus|  
|CC_Timeline_Footer|Verkkoresurssi, joka näytetään aikajanan alatunnisteena.|  
|CC_Timeline_Footer_Desc|Alatunniste-kentän kuvaus.|  
  
## <a name="linear-slider"></a>Lineaarinen liukusäädin  
 Lineaarinen liukusäädintä vetämällä käyttäjät voivat syöttää numeeriset arvot ja lisäksi voivat kirjoittaa määrän. Liukusäädin on kokonaisluku ja vain näytettävä tieto. Voit käyttää tätä ohjausobjektia mille tahansa numero- tai rahakentälle.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Enintään|Määrittää liukusäätimessä näytettävän enimmäisarvon.|  
|min|Määrittää liukusäätimessä näytettävän vähimmäisarvon.|  
|Arvo|Liukusäätimessä näytettävä arvo.|  
|Osavaihe|Määrittää nykyiseen arvoon lisättävän tai siitä vähennettävän summan syötettäessä tietoja tämän ohjausobjektin avulla.|  
  
## <a name="option-sets"></a>Asetusjoukot  
 Asetusjoukon ohjausobjekti esittää vaihtoehdot, joista käyttäjä voi valita syötettävän tiedon. Voit käyttää tätä ohjausobjektia asetusjoukolle, jossa vaihtoehtoja on kaksi tai kolme.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
  
## <a name="flip-switch"></a>Vaihtokytkin  
 Vaihtokytkin on kuin on/off-kytkin, tarjoaa vaihtoehdon kahden arvon välillä.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
  
## <a name="star-rating"></a>Tähtiluokitus  
 Käyttää tähtiluokitusta arvosanan visuaaliseen esittämiseen. Voit määrittää tähteä enimmäismäärä on viisi. Tätä ohjausobjektia voidaan käyttää vain kokonaislukuihin. Se ei hyväksy desimaaliarvoja.  
  
> [!NOTE]
>  Muista valita **Piilota verkossa** tälle ohjausobjektille.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Enintään|Valitse ohjausobjektissa käytettävä tähtien enimmäismäärä avattavasta luettelosta.|  
  
## <a name="radial-knob"></a>Säteittäinen säädin  
 Säteittäinen säädin mahdollistaa, että käyttäjät voivat syöttää tiedot liu'uttamalla säädintä ja näytössä näkyy ympyränä. Säteittäinen säädin antaa kokonaisluvun ja on vain näytettävä tieto. Voit käyttää tätä ohjausobjektia mille tahansa numero- tai rahakentälle. Kosketusnäytön avulla voit muuttaa arvoa tai numeronäppäimistön avulla voit keskittyä numeroon ja muokata sitä.  
  
> [!NOTE]
>  Tätä ohjausobjektia ei tueta Android 4.2- tai 4.3-laitteissa. Se vaikuttaa näiden versioiden ruudun vieritykseen.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Enintään|Määritä mittarissa näytettävä enimmäisarvo.|  
|min|Määritä mittarissa näytettävä vähimmäisarvo.|  
|Arvo|Noutaa tai määrittää mittarissa näytettävän arvon.|  
|Osavaihe|Määrittää nykyiseen arvoon lisättävän tai siitä vähennettävän summan syötettäessä tietoja tämän ohjausobjektin avulla.|  
  
## <a name="website-preview"></a>Verkkosivuston esikatselu  
 Käytä esikatselun ohjausobjektia yhdistämään URL-kenttä ja näyttämään verkkosivuston esikatselu.  
  
> [!IMPORTANT]
>  Kun tämä ohjausobjekti on otettu käyttöön, hyväksyt, että käyttäjät voivat jakaa tiettyjä tunnistettavissa olevia laitetietoja ulkoisen järjestelmän kanssa. Ulkoisista järjestelmistä PowerApps-sovellukseen tai Dynamics 365 Customer engagement -sovellukseen tuotuja tietoja koskevat tietosuojatiedot kohdassa [Microsoftin Tietosuoja ja evästeet](http://go.microsoft.com/fwlink/p/?LinkId=521839).  
>   
>  [Tietosuojatiedot](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
  
## <a name="bullet-graph"></a>Luettelomerkkikuvaaja  
 Luettelomerkkikuvaaja näyttää yhden avaimen tiedon ja vertailuarvon ja laadullisen alueen ilmaisten heti, onko tulos hyvä, huono tai jokin muu tila. Voit käyttää tätä ohjausobjektia koontinäytössä mille tahansa numero- tai rahakentälle. Voit esimerkiksi yhdistää arvon todelliseen tuottoon ja kohteen arvioituun tuottoon visualisoidaksesi todellisen tuoton verrattuna arvioituun tuottoon.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Enintään|Määrittää kaaviossa näytettävän enimmäisarvon.|  
|min|Määrittää kaaviossa näytettävän vähimmäisarvon.|  
|Good|Anna arvo, jota pidetään hyvänä mittayksikölle (valinnainen).|  
|Huono|Anna arvo, jota pidetään huonona mittayksikölle (valinnainen).|  
|Arvo|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
|Tavoite|Yhdistä tämä kenttään, johon arvoa verrataan. Esimerkiksi jos **Arvo** on yhdistetty **Todellinen tuotto** -kenttään, voit yhdistää **Hohde** ja **Arvioitu tuotto**, tai antaa staattinen arvo.|  
  
## <a name="pen-control"></a>Kynäohjausobjekti  
 Kynä-ohjausobjektin avulla voit siepata kirjoitetun toimen kuten allekirjoitukset.  
  
> [!NOTE]
>  Pienin suositeltu **enimmäispituus** määritetty tämän ohjausobjektin kenttään on 15000.  
>   
>  Muista valita **Piilota verkossa** tälle ohjausobjektille.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|PenMode|Määritä **PenMode!Draw**, **PenMode!Erase** tai **PenMode!Select** määrittääksesi, mitä tapahtuu, jos käyttäjä vetää osoitinlaitteella kynäohjausobjektissa.|  
  
## <a name="auto-complete"></a>Täydennä automaattisesti  
 Automaattisen täydennyksen ohjausobjektin suodattaa nimikeluettelon kirjoittaessasi ja voit valita arvon avattavasta luettelosta. Tämän ohjausobjektin avulla voit antaa käyttäjien valita avattavasta luettelosta maat/alueet ja valtiot. Tämä ohjausobjekti liittyy **Yksi tekstirivi** -tyypin kenttään.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
|Lähde|Määritä tietojen tietolähteen (ryhmitelty vaihtoehdot, asetusjoukko tai näkymä).|  
|Asetusjoukko|Valitse asetusjoukko tälle kentälle.|  
|Näkymä|Valitse entiteetti ja näkymä tälle kentälle.|  
|Kenttä|Valitse näkymän ensisijaisen entiteetin kenttä, jota käytetään tietolähteenä.|  
  
## <a name="multimedia"></a>Multimedia  
 Voit upottaa videoita tarjotaksesi monipuolisen asiakaskokemuksen myynnin ja kentän henkilöille. Tällä toiminnolla voit yhdistää ohjausobjektiin ääni- tai videolinkin sisältävän URL-osoitekentän.  
  
> [!NOTE]
>  Tätä ohjausobjektia tuetaan vain Androidin 4.4-versioissa tai sitä uudemmissa versioissa.  
>   
>  YouTube-videoita ei tällä hetkellä tueta Windows 8- ja Windows 8.1-taulutietokoneissa tai puhelimissa Windows 10:ssä tuetaan tällä hetkellä vain HTTPS-videoita, myös YouTube-videoita.  
  
 Tuetut tietovälinetyypit ovat seuraavat:  
  
-   MPEG4-tiedostojen suoratoisto  
  
-   YouTube-videot  
  
-   Azure-media  
  
-   Äänivirrat  
  
 [Tietosuojatiedot](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Tiedotusvälineet|Kirjoita sen mediakohteen URL-osoite, jonka tämä ohjausobjekti toistaa.|  
  
## <a name="number-input"></a>Numerosyöte  
 Number Input -ohjausobjektin avulla käyttäjät voivat syöttää tietoja nopeasti. Käyttäjien on vain napautettava plus ja miinus painikkeita muuttaakseen numeerinen arvo määrittämälläsi määrällä. Voit käyttää tätä ohjausobjektia mille tahansa numero- tai rahakentälle. Käyttäjät voivat myös kirjoittaa numeron suoraan. Tämä kenttä on tuettu vain muokkaustilassa.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Osavaihe|Määrittää nykyiseen arvoon lisättävän tai siitä vähennettävän summan syötettäessä tietoja tämän ohjausobjektin avulla.|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
  
## <a name="input-mask"></a>Syötepeite  
 Input Mask -ohjausobjektin avulla voit määrittää muotoilun kentän, kuten puhelinnumero tai luottokortti, virheellisten tietojen kirjoittamisen estäminen. Esimerkiksi jos haluat, että käyttäjät syöttämään Yhdysvaltojen puhelinnumeron muoto + 1-222-555-1011, käytä syöttörajoitetta + 1-000 000-0000.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Peite|Anna peite, jota käytetään tietojen tarkistamiseen käyttäjän syöttäessä. Voit käyttää peittessä yhdistelmä seuraavia merkkejä:<br /><br /> 0 – numeromerkki<br /><br /> 9 – numeromerkki tai välilyönti<br /><br /> # – numeromerkki, etumerkki tai välilyönti<br /><br /> L – kirjain<br /><br /> I – kirjain tai välilyönti<br /><br /> A – aakkosnumeerinen merkki<br /><br /> a – aakkosnumeerinen merkki tai välilyönti<br /><br /> < – muuntaa seuraavat merkit pieniksi kirjaimiksi<br /><br /> > – muuntaa seuraavat merkit isoiksi kirjaimiksi<br /><br /> &#124; – poistaa kirjainkokomuunnon käytöstä<br /><br /> \ – toimii mille tahansa merkille ohjausmerkkinä, joka muuttaa sen literaaliksi<br /><br /> Kaikki muut – literaaleja|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
  
## <a name="linear-gauge"></a>Lineaarinen mittari  
 Lineaarinen mittari antaa käyttäjien syöttää numeeriset arvot vetämällä liukusäädintä tarkan määrän kirjoittamisen sijaan. Liukusäädin on kokonaisluku ja vain näytettävä tieto. Voit käyttää tätä ohjausobjektia mille tahansa numero- tai rahakentälle.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Enintään|Määritä mittarissa näytettävä enimmäisarvo.|  
|min|Määritä mittarissa näytettävä vähimmäisarvo.|  
|Arvo|Noutaa tai määrittää mittarissa näytettävän arvon.|  
|Osavaihe|Määrittää nykyiseen arvoon lisättävän tai siitä vähennettävän summan syötettäessä tietoja tämän ohjausobjektin avulla.|  
  
## <a name="arc-knob"></a>Kaarisäädin  
 Kaarisäätimen avulla käyttäjät voivat antaa tiedot liu'uttamalla säädintä, mikä näkyy näytössä kaarena. Kaarisäädin antaa kokonaisluvun ja on vain näytettävä tieto. Voit käyttää tätä ohjausobjektia mille tahansa numero- tai rahakentälle. Kosketusnäytön avulla voit muuttaa arvoa tai numeronäppäimistön avulla voit keskittyä numeroon ja muokata sitä.  
  
> [!NOTE]
> Tätä ohjausobjektia ei tueta Android 4.2- tai 4.3-laitteissa. Se vaikuttaa näiden versioiden ruudun vieritykseen.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Enintään|Määritä mittarissa näytettävä enimmäisarvo.|  
|min|Määritä mittarissa näytettävä vähimmäisarvo.|  
|Arvo|Noutaa tai määrittää mittarissa näytettävän arvon.|  
|Osavaihe|Määrittää nykyiseen arvoon lisättävän tai siitä vähennettävän summan syötettäessä tietoja tämän ohjausobjektin avulla.|  
  
## <a name="next-steps"></a>Seuraavat vaiheet
[Opetusohjelma: Mukautettujen ohjausobjektien käyttäminen tietojen visualisointiin](use-custom-controls-data-visualizations.md)

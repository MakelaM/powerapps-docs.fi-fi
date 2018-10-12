---
title: Lisäohjausobjektit Dynamics 365:n puhelin- ja tablettisovellukselle | MicrosoftDocs
description: Luettelo Dynamics 365:n puhelin- ja tablettisovelluksessa käytettävissä olevista ohjausobjekteista
ms.custom: ''
ms.date: 06/18/2018
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
ms.assetid: 7920ef78-2540-48ad-ba25-9ce9cb995ed1
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: d6293f1fc0913a7e2f66e3830702458e3249f0f0
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675000"
---
# <a name="additional-controls-for-dynamics-365-for-phones-and-tablets"></a>Lisäohjausobjektit Dynamics 365:n puhelin- ja tablettisovellukselle 

 Käytettävissäsi on laaja valikoima ohjausobjekteja, joilla voit luoda Dynamics 365:n puhelin- ja tablettisovelluksesta entistä käyttäjäystävällisemmän. Tällaisia ohjausobjekteja ovat esimerkiksi liukusäätimet, valitsimet, multimediasoitin, syöttörajoitteet ja kalenteri.  

 
> [!NOTE]
>  Voit käyttää näitä lisäohjausobjekteja vain mobiilisovelluksissa. Niitä ei tueta verkkosovelluksessa.  
  
 Ohjausobjektien käyttäminen lomake-editorissa:  
  
1.  Kaksoisnapsauta kenttää tai luetteloa, johon haluat lisätä ohjausobjektin.  
  
2.  Valitse **Ohjausobjektit**-välilehti.  
  
3.  Valitse **Lisää ohjausobjekti**.  
  
4.  Valitse haluamasi ohjausobjekti ja sitten **Lisää**.  
  
    > [!NOTE]
    >  Eri ohjausobjekteja on käytettävissä kenttä- tai luettelotyypin mukaan. Esimerkiksi liukusäädinohjausobjektit voivat olla käytettävissä vain numero- tai rahakentissä ja kalenteriohjausobjekti vain luetteloissa.  
  
5.  Valitse laitteet, joissa haluat ohjausobjektin näkyvän (puhelin, tabletti tai molemmat). Ohjausobjektit eivät ole käytettävissä puhelimen otsikkokentissä.  
  
6.  Määritä kunkin ominaisuuden arvot.  
  
7.  Valitse **OK**, kun ohjausobjekti on määritetty.  
  
 Seuraavassa kuvataan jokainen ohjausobjekti, jota voit käyttää Dynamics 365:n puhelin- ja tablettisovelluksen lomakkeissa.  
  
## <a name="calendar-control"></a>Kalenterin ohjausobjekti  
 Tällä ohjausobjektilla voit määrittää lomakkeet niin, että ne näyttävät kalenterinäkymän Dynamics 365:n puhelin- ja tablettisovelluksessa. Tämän ohjausobjektin avulla voit korvata koontinäytöt, luettelot tai entiteettiruudukot puhelimissa ja tableteissa.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Alkamispäivä|Määritä alkamispäivä ja -aika kohteelle, joka visualisoidaan kalenterinäkymässä. Käytettävissä olevat arvot ovat päivämäärätyyppiä olevat sarakkeet.|  
|Päättymispäivä|Määritä päättymispäivämäärä ja -aika kohteelle, joka visualisoidaan kalenterinäkymässä. Käytettävissä olevat arvot ovat päivämäärätyyppiä olevat sarakkeet.|  
|Kesto|Kesto minuutteina. Jos määrität päättymispäivän arvon, kesto ohitetaan.|  
|Kuvaus|Tämä on kuvateksti, jonka haluat nähdä kalenterikohteissa.|  
  
 Kalenterissa näkyvä vähimmäiskesto on 30 minuuttia. Jos kohteen kesto on alle 30 minuuttia, se näkyy 30 minuuttia pitkänä.  
  
 Kalenterin ohjausobjekti tukee kaikkia päivämäärän ominaisuuksia (paikallinen käyttäjä, vain päivämäärä ja aikavyöhykkeestä riippumaton).  
  
## <a name="timeline-control"></a>Aikajanan ohjausobjekti  
 Tuottaa aikajanan tilin äskettäisistä olennaisista uutisartikkeleista ja Twitter-twiiteistä.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|CC_Timeline_Title|Ominaisuus, joka yhdistää aikajanan kunkin kohteen otsikon.|  
|CC_Timeline_Title_Desc|Otsikon kuvaus.|  
|CC_Timeline_Label1|Aikajanan kohteen otsikon alapuolella näytettävä kenttä.|  
|CC_Timeline_Label1_Desc|Otsikon 1 kuvaus.|  
|CC_Timeline_Label2|Otsikon 1 jälkeen näytettävä kenttä.|  
|CC_Timeline_Label2_Desc|Otsikon 2 kuvaus.|  
|CC_Timeline_Label3|Otsikon 2 jälkeen näytettävä kenttä.|  
|CC_Timeline_Label3_Desc|Otsikon 3 kuvaus.|  
|CC_Timeline_Label4|Otsikon 3 jälkeen näytettävä kenttä.|  
|CC_Timeline_Label4_Desc|Otsikon 4 kuvaus.|  
|CC_Timeline_Label5|Otsikon 4 jälkeen näytettävä kenttä.|  
|CC_Timeline_Label5_Desc|Otsikon 5 kuvaus.|  
|CC_Timeline_Timestamp|Kenttä, jota käytetään, kun aikajana määritetään käänteisessä aikajärjestyksessä.|  
|CC_Timeline_Timestamp_Desc|Aikaleiman kuvaus.|  
|CC_Timeline_Group|Aikajanan ryhmittelyä varten yhdistettävä kenttä.|  
|CC_Timeline_Group_Desc|Ryhmä-kentän kuvaus.|  
|CC_Timeline_GroupOrder|Kohteen ryhmän järjestys suhteessa muihin ryhmiin (määritä arvot 1, 2, 3 ja niin edelleen näytettäville ryhmille). Ryhmä näkyy nousevassa järjestyksessä määritettyjen ryhmän arvojen mukaan.|  
|CC_Timeline_GroupOrder_Desc|Ryhmän järjestys -kentän kuvaus.|  
|CC_Timeline_URL|URL-kenttä, joka yhdistää aikajanan kunkin kohteen näytettävän URL-osoitteen.|  
|CC_Timeline_URL_Desc|URL-kentän kuvaus.|  
|CC_Timeline_ThumbnailURL|Kenttä, joka yhdistää näytettävän pikkukuvan tai kuvakkeen kunkin kohteen osalta.|  
|CC_Timeline_ThumnailURL_Desc|`ThumbnailURL`-kentän kuvaus.|  
|CC_Timeline_Filter|Aikajanan suodatusta varten yhdistettävä kenttä.|  
|CC_Timeline_Filter_Desc|Suodattimen kuvaus.|  
|CC_Timeline_Footer|Verkkoresurssi, joka näytetään aikajanan alatunnisteena.|  
|CC_Timeline_Footer_Desc|Alatunniste-kentän kuvaus.|  
  
## <a name="linear-slider"></a>Lineaarinen liukusäädin  
 Lineaarisen liukusäätimen ohjausobjektin avulla käyttäjät voivat syöttää numeerisia arvoja vetämällä liukusäädintä. Lisäksi voidaan kirjoittaa määrä. Liukusäädin mahdollistaa vain kokonaislukujen syöttämisen ja näyttämisen. Tätä ohjausobjektia voidaan käyttää missä tahansa numero- tai rahakentässä.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Max|Määrittää liukusäätimessä näytettävän enimmäisarvon.|  
|Min|Määrittää liukusäätimessä näytettävän vähimmäisarvon.|  
|Arvo|Liukusäätimessä näytettävä arvo.|  
|Vaihe|Määrittää nykyiseen arvoon lisättävän tai siitä vähennettävän summan syötettäessä tietoja tämän ohjausobjektin avulla.|  
  
## <a name="option-sets"></a>Asetusjoukot  
 Asetusjoukon ohjausobjekti esittää vaihtoehdot, joista käyttäjä voi valita syötettävän tiedon. Voit käyttää tätä ohjausobjektia asetusjoukolle, jossa vaihtoehtoja on kaksi tai kolme.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
  
## <a name="flip-switch"></a>Vaihtokytkin  
 Vaihtokytkin on kuin on/off-kytkin, joka tarjoaa vaihtoehdon kahden arvon välillä.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
  
## <a name="star-rating"></a>Tähtiluokitus  
 Tähtiluokituksen avulla voit esittää luokituksen visuaalisesti. Määritettävien tähtien enimmäismäärä on viisi. Tätä ohjausobjektia voidaan käyttää vain kokonaislukuihin. Se ei hyväksy desimaaliarvoja.  
  
> [!NOTE]
>  Muista valita **Piilota verkossa** tälle ohjausobjektille.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Max|Valitse ohjausobjektissa käytettävä tähtien enimmäismäärä avattavasta luettelosta.|  
  
## <a name="radial-knob"></a>Säteittäinen säädin  
 Säteittäisen säätimen avulla käyttäjät voivat syöttää tietoja liu'uttamalla säädintä. Se näkyy näytössä ympyränä. Säteittäinen säädin mahdollistaa vain kokonaislukujen syöttämisen ja näyttämisen. Tätä ohjausobjektia voidaan käyttää missä tahansa numero- tai rahakentässä. Voit muuttaa arvoa kosketusnäytöllä tai siirtyä numeroon ja muokata sitä näppäimistön avulla.  
  
> [!NOTE]
>  Tätä ohjausobjektia ei tueta Android 4.2- ja 4.3-laitteissa. Se vaikuttaa vieritystoimintoon kyseisissä versioissa.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Max|Määrittää mittarissa näytettävän enimmäisarvon.|  
|Min|Määrittää mittarissa näytettävän vähimmäisarvon.|  
|Arvo|Noutaa tai määrittää mittarissa näytettävän arvon.|  
|Vaihe|Määrittää nykyiseen arvoon lisättävän tai siitä vähennettävän summan syötettäessä tietoja tämän ohjausobjektin avulla.|  
  
## <a name="website-preview"></a>Verkkosivuston esikatselu  
 Verkkosivuston esikatselun ohjausobjektin avulla voit yhdistää URL-kentän ja näyttää verkkosivuston esikatselun.  
  
> [!IMPORTANT]
>  Kun otat tämän ohjausobjektin käyttöön, hyväksyt, että käyttäjät voivat jakaa tiettyjä tunnistettavissa olevia laitetietoja ulkoisen järjestelmän kanssa. Ulkoisista järjestelmistä PowerApps-sovellukseen tai Dynamics 365 Customer Engagementiin tuotavia tietoja koskevat tietosuojatiedot sivustossa [Microsoftin tietosuojatiedot ja evästeet](http://go.microsoft.com/fwlink/p/?LinkId=521839).  
>   
>  [Tietosuojailmoitukset](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
  
## <a name="bullet-graph"></a>Nuolikuvaaja  
 Nuolikuvaajan ohjausobjekti näyttää yhden tärkeän mitan ja vertailuarvon ja laadullisen alueen ilmaisten heti, onko mitta hyvä, huono tai jokin muu. Tätä ohjausobjektia voidaan käyttää koontinäytöissä missä tahansa numero- tai rahakentässä. Voit esimerkiksi yhdistää arvon todelliseen tuottoon ja kohteen arvioituun tuottoon visualisoidaksesi todellisen tuoton verrattuna arvioituun tuottoon.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Max|Määrittää kaaviossa näytettävän enimmäisarvon.|  
|Min|Määrittää kaaviossa näytettävän vähimmäisarvon.|  
|Hyvä|Määrittää arvon, jota pidetään hyvänä mitalle (valinnainen).|  
|Huono|Määrittää arvon, jota pidetään huonona mitalle (valinnainen).|  
|Arvo|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
|Kohde|Yhdistä tämä kenttään, johon haluat verrata arvoa. Esimerkiksi jos **arvo** yhdistetään **todelliseen tuottoon**, voit yhdistää **kohteen** **arvioituun tuottoon** tai voit antaa staattisen arvon.|  
  
## <a name="pen-control"></a>Kynäohjausobjekti  
 Kynäohjausobjektin avulla voit siepata kirjallisen syötteen, kuten allekirjoituksia.  
  
> [!NOTE]
>  Pienin suositeltu **enimmäispituus** kentälle, johon tämä ohjausobjekti yhdistää, on 15 000.  
>   
>  Muista valita **Piilota verkossa** tälle ohjausobjektille.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|PenMode|Määritä **PenMode!Draw**, **PenMode!Erase** tai **PenMode!Select**, jotta voit määritellä, mitä tapahtuu, jos käyttäjä vetää osoitinlaitetta kynäohjausobjektissa.|  
  
## <a name="auto-complete"></a>Automaattinen täydennys  
 Automaattisen täydennyksen ohjausobjekti suodattaa kohdeluettelon kirjoittaessasi, ja voit valita arvon avattavasta luettelosta. Tämän ohjausobjektin avulla voit esimerkiksi antaa käyttäjien valita avattavasta luettelosta valtiot tai maat/alueet. Tämä ohjausobjekti yhdistää **Yksi tekstirivi** -tyypin kenttään.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
|Lähde|Määrittää tietojen tietolähteen (ryhmitellyt asetukset, asetusjoukko tai näkymä).|  
|Asetusjoukko|Valitse asetusjoukko tälle kentälle.|  
|Näkymä|Valitse entiteetti ja näkymä tälle kentälle.|  
|Kenttä|Valitse näkymän ensisijaisen entiteetin kenttä, jota käytetään tietolähteenä.|  
  
## <a name="multimedia"></a>Multimedia  
 Voit upottaa videoita tarjotaksesi monipuolisen asiakaskokemuksen myyjille ja kenttähenkilöstölle. Tällä ohjausobjektilla voit yhdistää URL-kenttään, joka sisältää ohjausobjektissa toistettavan ääni- tai videolinkin.  
  
> [!NOTE]
>  Tätä ohjausobjektia tuetaan vain Androidin 4.4-versioissa tai sitä uudemmissa versioissa.  
>   
>  YouTube-videoita ei tällä hetkellä tueta Windows 8- ja Windows 8.1-tableteissa ja -puhelimissa. Windows 10:ssä tuetaan vain HTTPS-videoita, myös YouTube-videoita.  
  
 Tuettuja mediatyyppejä ovat seuraavat:  
  
-   MP4-tiedostojen suoratoisto  
  
-   YouTube-videot  
  
-   Azure-media  
  
-   Äänivirrat  
  
 [Tietosuojailmoitus](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Media|Kirjoita sen mediakohteen URL-osoite, joka toistetaan tässä ohjausobjektissa.|  
  
## <a name="number-input"></a>Numerosyöte  
 Numerosyötteen ohjausobjektin avulla käyttäjät voivat syöttää tietoja nopeasti. Käyttäjät voivat muuttaa numeroarvoa määrittämälläsi määrällä plus- ja miinuspainikkeita napauttamalla. Tätä ohjausobjektia voidaan käyttää missä tahansa numero- tai rahakentässä. Käyttäjät voivat myös kirjoittaa numeron suoraan. Tätä kenttää tuetaan vain muokkaustilassa.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Vaihe|Määrittää nykyiseen arvoon lisättävän tai siitä vähennettävän summan syötettäessä tietoja tämän ohjausobjektin avulla.|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
  
## <a name="input-mask"></a>Syöttörajoite  
 Syöttörajoitteen ohjausobjektin avulla voit määrittää kentän muotoilun, kuten puhelinnumeron tai luottokortin, virheellisten tietojen kirjoittamisen estämiseksi. Esimerkiksi jos haluat, että käyttäjät syöttävät Yhdysvaltojen puhelinnumeron muodossa +1-222-555-1011, käytä syöttörajoitetta +1-000-000-0000.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Rajoite|Anna rajoite, jota käytetään tietojen tarkistamiseen käyttäjän syöttäessä niitä. Voit käyttää rajoitteessa seuraavien merkkien yhdistelmää:<br /><br /> 0 – numero<br /><br /> 9 – numero tai välilyönti<br /><br /> # – numero, merkki tai välilyönti<br /><br /> L – kirjain<br /><br /> I – kirjain tai välilyönti<br /><br /> A – aakkosnumeerinen merkki<br /><br /> A – aakkosnumeerinen merkki tai välilyönti<br /><br /> < – muuntaa seuraavat merkit pieniksi kirjaimiksi<br /><br /> > – muuntaa seuraavat merkit isoiksi kirjaimiksi<br /><br /> &#124;– poistaa käytöstä kirjainkoon muuntamisen<br /><br /> \ – ohittaa minkä tahansa merkin muuttamalla sen literaaliksi<br /><br /> Kaikki muut – literaalit|  
|Kenttä|Näyttää kentän, johon ohjausobjekti yhdistetään.|  
  
## <a name="linear-gauge"></a>Lineaarinen mittari  
 Lineaarisen mittarin avulla käyttäjät voivat syöttää numeerisia arvoja vetämällä liukusäädintä tarkan määrän kirjoittamisen sijaan. Liukusäädin mahdollistaa vain kokonaislukujen syöttämisen ja näyttämisen. Tätä ohjausobjektia voidaan käyttää missä tahansa numero- ja rahakentässä.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Max|Määrittää mittarissa näytettävän enimmäisarvon.|  
|Min|Määrittää mittarissa näytettävän vähimmäisarvon.|  
|Arvo|Noutaa tai määrittää mittarissa näytettävän arvon.|  
|Vaihe|Määrittää nykyiseen arvoon lisättävän tai siitä vähennettävän summan syötettäessä tietoja tämän ohjausobjektin avulla.|  
  
## <a name="arc-knob"></a>Kaarisäädin  
 Kaarisäätimen avulla käyttäjät voivat syöttää tietoja liu'uttamalla säädintä. Se näkyy näytössä kaarena. Kaarisäädin mahdollistaa vain kokonaislukujen syöttämisen ja näyttämisen. Tätä ohjausobjektia voidaan käyttää missä tahansa numero- ja rahakentässä. Voit muuttaa arvoa kosketusnäytöllä tai siirtyä numeroon ja muokata sitä näppäimistön avulla.  
  
> [!NOTE]
> Tätä ohjausobjektia ei tueta Android 4.2- ja 4.3-laitteissa. Se vaikuttaa vieritystoimintoon kyseisissä versioissa.  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Max|Määrittää mittarissa näytettävän enimmäisarvon.|  
|Min|Määrittää mittarissa näytettävän vähimmäisarvon.|  
|Arvo|Noutaa tai määrittää mittarissa näytettävän arvon.|  
|Vaihe|Määrittää nykyiseen arvoon lisättävän tai siitä vähennettävän summan syötettäessä tietoja tämän ohjausobjektin avulla.|  
  
## <a name="next-steps"></a>Seuraavat vaiheet
[Opetusohjelma: Mukautettujen ohjausobjektien käyttäminen tietojen visualisointiin](use-custom-controls-data-visualizations.md)
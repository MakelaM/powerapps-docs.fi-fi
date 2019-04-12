---
title: Mallipohjaisen sovelluksen päälomakkeiden osan ominaisuudet PowerAppsissa | MicrosoftDocs
description: Tietoja päälomakkeen osaresurssin ominaisuuksista
Keywords: Päälomake; osan ominaisuudet; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: powerapps
ms.topic: article
ms.assetid: 2d3af6e9-e8a4-4129-b708-383b2740c015
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-form-section-properties"></a>Mallipohjaisen sovelluksen lomakkeen osan ominaisuudet

 Lomakkeen osa käyttää välilehtisarakkeessa olevaa tilaa. Osilla on otsikko, joka voidaan näyttää, ja otsikon alapuolella voidaan näyttää viiva.  
  
 Osissa voi olla enintään neljä saraketta, ja ne sisältävät asetukset, joilla määritetään osan kenttien otsikoiden näyttäminen.  
  
 Ylä- ja alatunnisteet muistuttavat otsikoita, mutta niitä ei voi poistaa. Jos ne ovat tyhjiä, niitä ei näytetä. 

Voit käyttää **Osan ominaisuudet** -kohtaa PowerApps-sivustossa. 
1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti. 

3.  Avaa lomakeluettelosta lomake, joka tyyppi on **Pää**. Voit tarkastella osan ominaisuuksia kaksoisnapsauttamalla sitten jonkin osan sisällä. 

    ![section-properties](media/section-properties.png)
  
|Sarkain|Ominaisuus|Kuvaus|  
|---------|--------------|-----------------|  
|**Näytä**|**Nimi**|**Pakollinen**: Osan yksilöivä nimi, jolla siihen viitataan komentosarjoissa. Nimessä voi olla vain aakkosnumeerisia merkkejä ja alaviivoja.|  
||**Otsikko**|**Pakollinen**: osan lokalisoitava otsikko, jonka käyttäjät näkevät.|  
||**Näytä tämän osan otsikko lomakkeessa**|Osia käytetään usein ilman otsikoita, jotta niissä olevien kenttien muotoilua voi hallita.|  
||**Näytä viiva osan yläreunassa**|Osan yläreunassa oleva viiva auttaa hahmottamaan lomakkeen asettelua.|  
||**Kentän otsikkoalueen leveys**|**Pakollinen**: Määritä kentän otsikoiden välisen tilan arvoksi 50–250.<br /><br /> Myös ylä- ja alatunniste-elementeillä on tämä ominaisuus.|  
||**Näkyvyys**|Osan näyttäminen on valinnaista, ja sitä voidaan hallinta komentosarjoilla. Lisätietoja: [Näkyvyysasetukset](visibility-options-legacy.md)|  
||**Käytettävyys**|Valitse, haluatko, että puhelimessa voi käyttää välilehteä.|  
||**Lukitse osa lomakkeessa**|Tämä estää osan poistamisen vahingossa. Muut eivät voi myöskään poistaa sisältöä.<br /><br /> Osan poistaminen poistaa osan lisäksi myös kaikki siinä olevat kentät.<br /><br /> Jos joku haluaa poistaa tämän osan, hänen on muutettava asetusta ennen kuin se onnistuu.|  
|**Muotoilu**<br /><br /> Myös ylä- ja alatunnisteosilla on tämä ominaisuus.|**Asettelu**|Voit määrittää osaan enintään neljä saraketta.|  
||**Kentän otsikon tasaus**|Osan kenttien otsikot voidaan tasata vasemmalle, oikealle tai keskelle.|  
||**Kentän otsikon sijainti**|Osan kenttien otsikot voivat olla kentän vieressä tai sen yläpuolella.|  


Myös uudenlainen osa, **Viitepaneeli**, voidaan lisätä. Viitepaneeli on yksisarakkeinen osa. Voit lisätä aliruudukoita, pikanäkymän ohjausobjektin tai tietämyskannan hakuobjektin viitepaneeliosaan. Jokainen viitepaneeliin lisäämäsi ohjausobjekti näytetään pystysuuntaisena välilehtenä paneelissa suorituksen aikana. Ohjausobjekteja voi järjestää vetämällä ja pudottamalla viitepaneeliosassa. Suorituksenaikainen oletusvälilehti on ensimmäinen viitepaneeliin lisätty ohjausobjekti. Muut välilehdet näkyvät siinä järjestyksessä, jossa ne on lisätty lomake-editorilla. Välilehtiä voit poistaa näppäimistön Delete-näppäimellä.  
  
Kun lisäät viitepaneelin, se lisätään oletusarvoisesti välilehden viimeisenä osana. Voit lisätä lomakkeeseen vain yhden viitepaneelin.  
  
> [!IMPORTANT]
>  Oletusarvoisesti viitepaneeliosa on lukittu seuraavissa vakiolomakkeissa: palvelupyynnöt, asiakkaat ja yhteyshenkilöt. Jos haluat poistaa sen tai tehdä siihen muutoksia, avaa lukitus. 

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)

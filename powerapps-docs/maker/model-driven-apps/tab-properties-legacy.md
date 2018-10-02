---
title: Mallipohjaisen sovelluksen lomakkeiden välilehtien ominaisuudet PowerAppsissa | MicrosoftDocs
description: Tietoja päälomakkeiden välilehtiresurssin ominaisuuksista
Keywords: Tab properties; Dynamics 365; Main forms
author: matp
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: Mattp123
manager: kvivek
ms.date: 06/07/2018
ms.service: crm-online
ms.topic: article
ms.assetid: e0790865-c5a4-4e86-bce2-584af2b8ed93
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="tab-properties-for-model-driven-app-forms-overview"></a>Mallipohjaisten sovellusten lomakkeiden välilehtien ominaisuuksien yleiskatsaus

 Lomakkeen runko erotellaan vaakasuunnassa välilehtien avulla. Välilehdissä on otsikko, joka voidaan näyttää. Jos otsikko on näkyvissä, välilehdet voidaan laajentaa näyttämään sisältö tai tiivistää piilottamaan sisältö valitsemalla otsikko.  
  
 Välilehdissä on enintään kolme saraketta, ja kunkin sarakkeen leveys voidaan määrittää kokonaisleveyden prosenttiosuutena. Kun luot uuden välilehden, jokaiseen sarakkeeseen lisätään valmiiksi osa.  

Voit käyttää **Välilehden ominaisuudet** -kohtaa PowerApps-sivustossa. 
1.  Valitse [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Mallipohjainen** (siirtymisruudun alaosassa vasemmalla).  

     ![Mallipohjainen suunnittelutila](media/model-driven-switch.png)

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti.  

3.  Avaa lomakeluettelosta lomake, joka tyyppi on **Pää**. Voit tarkastella välilehden ominaisuuksia lomakekaaviossa kaksoisnapsauttamalla sitten jonkin välilehden sisällä.

    ![tab-properties](media/tab-properties.png)
  
 Seuraavassa taulukossa on ominaisuudet, jotka voidaan määrittää lomakkeen välilehtiin:
  
|Välilehti|Ominaisuus|Kuvaus|  
|---------|--------------|-----------------|  
|**Näytä**|**Nimi**|**Pakollinen**: Välilehden yksilöivä nimi, jolla siihen viitataan komentosarjoissa. Nimessä voi olla vain aakkosnumeerisia merkkejä ja alaviivoja.|  
||**Otsikko**|**Pakollinen**: välilehden lokalisoitava otsikko, jonka käyttäjä näkee.|  
||**Näytä tämän välilehden otsikko lomakkeessa**|Kun otsikko näkyy, käyttäjät voivat sitä napsauttamalla laajentaa tai tiivistää välilehden. Valitse, haluatko näyttää otsikon.|  
||**Laajenna tämä välilehti oletusarvoisesti**|Välilehden tilaa voi vaihdella laajennetun tai tiivistetyn välillä lomakkeen komentosarjoilla. Käyttäjät voivat vaihtaa sitä myös otsikon valitsemalla. Valitse välilehden oletustila.|  
||**Oletusarvoisesti näkyvissä**|Välilehden näyttäminen on valinnaista, ja sitä voidaan hallinta komentosarjoilla. Valitse, onko välilehti näkyvissä. Lisätietoja: [Näkyvyysasetukset](visibility-options-legacy.md)|  
||**Käytettävyys**|Valitse, haluatko, että puhelimessa voi käyttää välilehteä.|  
|**Muotoilu**|**Asettelu**|Välilehdissä voi olla enintään kolme saraketta. Näillä asetuksilla voit määrittää välilehtien lukumäärän ja niiden leveyden osuutena kokonaisleveydestä.|  
|**Tapahtumat**|**Lomakekirjastot**|Määritä mikä tahansa JavaScript-WWW-resurssi, joita käytetään välilehden `TabStateChange`-tapahtumakäsittelijässä.<br /><br />|  
||**Tapahtumakäsittelijät**|Määritä toiminnot kirjastoista, jotka on kutsuttava välilehden `TabStateChange`-tapahtumaa varten. Lisätietoja: [Tapahtumankäsittelijöiden määrittäminen](configure-event-handlers-legacy.md)|  
  
## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)

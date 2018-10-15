---
title: Tapahtumakäsittelijöiden määrittäminen mallipohjaisten sovellusten päälomakkeille PowerAppsissa | MicrosoftDocs
description: Tutustu tapahtumakäsittelijöiden määrittämiseen Dynamics 365 for Customer Engagementissa
Keywords: Main form; Configure event handlers; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
ms.assetid: dc0ebb3f-0c00-413a-968f-9cfd107055c0
ms.openlocfilehash: e05e9d840a2b3ad7d8d5c74e8e3b670504f739b0
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39678648"
---
# <a name="configure-model-driven-app-form-event-handlers"></a>Mallipohjaisten sovellusten lomakkeiden tapahtumakäsittelijöiden määrittäminen

 PowerApps-lomakkeiden tapahtumakäsittelijöitä voidaan määrittää seuraaville lomakealueille:  
  
|Elementti|Tapahtuma|Kuvaus|  
|-------------|-----------|-----------------|  
|Lomake|`OnLoad`|Toteutuu, kun lomake latautuu.|  
||`OnSave`|Toteutuu, kun tietoja tallennetaan.|  
|Välilehti|`TabStateChange`|Toteutuu, kun välilehti laajennetaan tai kutistetaan.|  
|Kenttä|`OnChange`|Tapahtuu, kun kentässä oleva tieto muuttuu ja ohjausobjekti menettää kohdistuksen.|  
|IFRAME-kehys|`OnReadyStateComplete`|Toteutuu, kun IFRAME-kehyksen sisältö latautuu.|  
  
 Tapahtumakäsittelijä sisältää viittauksen JavaScript-verkkoresurssiin ja funktioon, joka on määritetty kyseisessä verkkoresurssissa ja joka suoritetaan, kun tapahtuma tapahtuu. Jokaiselle elementille voidaan määrittää enintään 50 erillistä tapahtumakäsittelijää.  
  
> [!IMPORTANT]
>  Virheellisesti määritetty tapahtumakäsittelijä voi aiheuttaa komentosarjavirheitä, jotka voivat estää lomaketta latautumasta tai toimimasta oikein. Jos et ole komentosarjan kehittäjä, muista tarkistaa komentosarjan vaatimat määritysvaihtoehdot.  
>   
>  Kun määrität komentosarjan tapahtumakäsittelijää, käytä vain sellaista kirjastoa, joka on peräisin luotetusta lähteestä. Komentosarjojen avulla voit suorittaa kaikkia samoja toimintoja kuin käyttäjäsikin, ja huonosti kirjoitettu komentosarja voi alentaa lomakkeen suorituskykyä huomattavasti.  
>   
>  Kun olet määrittänyt tapahtumakäsittelijän, muista aina tarkistaa sen toimivuus.  
  
### <a name="to-configure-an-event-handler"></a>Tapahtumakäsittelijän määrittäminen 
  
1.  Valitse lomake-editorissa elementti, joka sisältää tapahtuman, jolle haluat määrittää käsittelijän.  
  
2.  Valitse [Aloitus-välilehden](form-editor-user-interface-legacy.md#home-tab) **Muokkaa**-ryhmästä **Muuta ominaisuuksia** tai kaksoisnapsauta elementtiä.  
  
3.  Valitse elementin ominaisuudet -valintaikkunassa **Tapahtumat**-välilehti.  
  
4.  Laajenna **Lomakekirjastot**-alue. Jos et löydä luettelosta sitä kirjastoa, joka sisältää tapahtumakäsittelijäksi asetettavan toiminnon, lisää kyseinen kirjasto.  
  
5.  Lomakekirjaston lisääminen tapahtumakäsittelijään:  
    1.  Valitse **Tapahtumaluettelon** **Lomakekirjastot**-osiossa **Lisää**.  
  
    2.  Etsi haluamasi JavaScript-verkkoresurssi käytettävissä olevien verkkoresurssien luettelosta. Valitse se ja valitse sitten **Lisää**.  
  
         Jos tarvitsemaasi JavaScript-verkkoresurssia ei ole olemassa, valitse **Uusi** avataksesi uuden verkkoresurssilomakkeen, jossa voit luoda sen.  
  
    3.  JavaScript-verkkoresurssin luominen:  
        1.  Määritä seuraavat ominaisuudet verkkoresurssilomakkeessa:  
  
            |Ominaisuus|Arvo|  
            |--------------|-----------|  
            |Nimi|**Pakollinen**. Kirjoita verkkoresurssin nimi.|  
            |Näyttönimi|**Pakollinen**. Kirjoita nimi, joka näytetään verkkoresurssiluettelossa.|  
            |Kuvaus|Valinnainen. Kirjoita verkkoresurssin kuvaus.|  
            |Tyyppi|**Pakollinen**. Valitse **Komentosarja (JScript)**.|  
            |Kieli|Valinnainen. Valitse jokin organisaatiollesi käytettävissä olevista kielistä.|  
  
        2.  Jos ole saanut komentosarjan, suosittelemme, että etsit saamasi tiedoston **Selaa**-painikkeen avulla ja lataat sen.  
  
             Vaihtoehtoisesti voit napsauttaa **Tekstieditori**-painiketta ja liittää tai kirjoittaa komentosarjan sisällön **Muokkaa sisältöä** -valintaikkunaan.  
  
            > [!NOTE]
            >  Koska tämä yksinkertainen tekstieditori ei sisällä mitään komentosarjan tarkistukseen liittyviä ominaisuuksia, suosittelemme aina käyttämään erillistä sovellusta kuten Visual Studiota komentosarjojen muokkaamiseen ennen kuin lataat ne.  
  
        3.  Valitse **Tallenna** ja sulje verkkoresurssin valintaikkuna.  
  
        4.  Luomasi verkkoresurssi on nyt valittuna **Hae tietue** -valintaikkunassa. Valitse **Lisää** sulkeaksesi valintaikkunan.  
6.  Valitse **Tapahtumakäsittelijät**-osassa tapahtuma, jolle haluat määrittää tapahtumakäsittelijän.  
  
7.  Valitse **Lisää** avataksesi **Käsittelijän ominaisuudet** -valintaikkunan.  
  
8. Valitse **Tiedot** välilehdessä haluamasi kirjasto ja kirjoita tapahtumalle suoritettavan funktion nimi.  
  
9. Tapahtumakäsittelijä on käytössä oletusarvoisesti. Jos et halua ottaa tätä tapahtumaa käyttöön, poista **Käytössä**-valintaruudun valinta.  
  
     Jotkin funktiot edellyttävät suorittamiskontekstin välittämistä funktiolle. Valitse **Välitä suorituskonteksti ensimmäisenä parametrina**, jos sitä vaaditaan.  
  
     Jotkin funktiot voivat hyväksyä joukon parametreja, joilla ohjataan funktion käyttäytymistä. Jos näitä vaaditaan, syötä ne **Pilkuin eroteltuun funktiolle välitettävien parametrien luetteloon**.  
  
10. **Riippuvuudet**-välilehdessä voit lisätä kaikki komentosarjan tarvitsemat kentät **Riippuvaiset kentät** -alueeseen.  
  
11. Valitse **OK** sulkeaksesi **Käsittelijän ominaisuudet** -valintaikkunan.  
  
12. Kun tapahtumakäsittelijä on syötetty, voit muuttaa funktion suoritusjärjestystä suhteessa muihin funktioihin siirtämällä sitä vihreiden nuolien avulla ylöspäin tai alaspäin.  
  
13. Valitse **OK** sulkeaksesi elementin ominaisuudet -valintaikkunan.  
  
14. Tallenna muutoksesi valitsemalla **Tallenna**. Valitse **Julkaise** julkaistaksesi lomakkeen.  
  
> [!NOTE]
>  Vaikka voit muuttaa komentosarjojen latausjärjestystä käyttöliittymässä vihreiden ylöspäin ja alaspäin osoittavien nuolien avulla, komentosarjoja ei kuitenkaan ladata järjestyksessä.   

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja sen osien käyttäminen](use-main-form-and-components.md)

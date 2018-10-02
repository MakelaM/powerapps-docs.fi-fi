---
title: Mallipohjaisen sovelluksen päälomakkeiden tapahtumakäsittelijöiden määrittäminen PowerAppsissa | MicrosoftDocs
description: Tapahtumakäsittelijöiden määrittäminen Dynamics 365 for Customer Engagementissa
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-model-driven-app-form-event-handlers"></a>Mallipohjaisen sovelluksen lomakkeen tapahtumakäsittelijöiden määrittäminen

 PowerApps-lomakkeiden tapahtumakäsittelijät voidaan määrittää seuraavilla lomakkeen alueilla:  
  
|Elementti|Tapahtuma|Kuvaus|  
|-------------|-----------|-----------------|  
|Lomake|`OnLoad`|Tapahtuu, kun lomake latautuu.|  
||`OnSave`|Tapahtuu, kun tiedot tallennetaan.|  
|Välilehti|`TabStateChange`|Tapahtuu, kun välilehti laajennetaan tai tiivistetään.|  
|Kenttä|`OnChange`|Tapahtuu, kun kentän tiedot muuttuvat eikä ohjausobjekti ole enää aktiivinen.|  
|IFRAME|`OnReadyStateComplete`|Tapahtuu, kun IFRAME-kehyksen sisältö latautuu.|  
  
 Tapahtumakäsittelijä sisältää viittauksen JavaScript-WWW-resurssiin ja toimintoon, joka on määritetty kyseisessä verkkoresurssissa ja joka suoritetaan tapahtuman tapahtuessa. Kussakin elementissä voi olla määritettynä enintään 50 tapahtumakäsittelijää.  
  
> [!IMPORTANT]
>  Tapahtumakäsittelijän virheellinen määritys voi johtaa komentosarjavirheisiin, jotka voivat aiheuttaa lomakkeen latausvirheen tai virheellisen toiminnan. Jos et ole komentosarjan kehittäjä, varmista, että tiedät täsmälleen, miten komentosarjan asetukset on määritettävä.  
>   
>  Älä määritä komentosarjan tapahtumakäsittelijää kirjastolla, joka ei ole peräisin luotettavasta lähteestä. Komentosarjoilla voidaan suorittaa mikä tahansa toiminto, jonka käyttäjä voi suorittaa. Niinpä huonosti laadittu komentosarja voi heikentää merkittävästi lomakkeen toimintaa.  
>   
>  Varmista aina tapahtumakäsittelijän asianmukainen toiminta testaamalla se määrittämisen jälkeen.  
  
### <a name="to-configure-an-event-handler"></a>Tapahtumakäsittelijän määrittäminen 
  
1.  Valitse lomake-editorissa elementti, jonka tapahtumalle haluat määrittää käsittelijän.  
  
2.  Valitse ensin [Koti-välilehti](form-editor-user-interface-legacy.md#home-tab), sitten **Muokkaa**-ryhmä ja lopuksi **Muuta ominaisuuksia** tai vain kaksoisnapsauta elementtiä.  
  
3.  Valitse elementin ominaisuuksien valintaikkunassa **Tapahtumat**-välilehti.  
  
4.  Laajenna **Lomakekirjastot**-alue. Jos kirjasto, jonka toiminnon haluat määrittää tapahtumakäsittelijäksi, ei ole vielä luettelossa, lisää se.  
  
5.  Lomakekirjaston lisääminen tapahtumakäsittelijään:  
    1.  Valitse **Tapahtumaluettelo**-kohdan **Lomakekirjastot**-osassa **Lisää**.  
  
    2.  Etsi JavaScript-WWW-resurssi käytettävissä olevien verkkoresurssien luettelosta. Valitse ensin se ja sitten **Lisää**.  
  
         Jos tarvitsemaasi JavaScript-WWW-resurssia ei ole olemassa, avaa uusi verkkoresurssilomake valitsemalla **Uusi** ja luo lomake.  
  
    3.  JavaScript-verkkoresurssin luominen:  
        1.  Määritä verkkoresurssilomakkeessa seuraavat ominaisuudet:  
  
            |Ominaisuus|Arvo|  
            |--------------|-----------|  
            |Nimi|**Pakollinen**. Kirjoita verkkoresurssin nimi.|  
            |Näyttönimi|**Pakollinen**. Kirjoita verkkoresurssiluettelossa näkyvä nimi.|  
            |Kuvaus|Valinnainen. Kirjoita verkkoresurssin kuvaus.|  
            |Tyyppi|**Pakollinen**. Valitse **Komentosarja (JScript)**.|  
            |Kieli|Valinnainen. Valitse jokin organisaatiossa käytettävissä olevista kielistä.|  
  
        2.  Jos sinulle on toimitettu komentosarja, on suositeltavaa etsiä se **Selaa**-painikkeella ja ladata se.  
  
             Voit vaihtoehtoisesti valita **Tekstieditori**-painikkeen ja liittää tai kirjoittaa **Muokkaa sisältöä** -valintaikkunan komentosarjan sisällön.  
  
            > [!NOTE]
            >  Koska yksinkertaisessa tekstieditorissa ei ole ominaisuuksia, joilla komentosarjan oikeellisuuden voi tarkistaa, komentosarjojen muokkaamiseen on yleensä syytä käyttää erillistä sovellusta, kuten Visual Studiota, jonka jälkeen voit ladata ne.  
  
        3.  Valitse **Tallenna** ja sulje verkkoresurssin valintaikkuna.  
  
        4.  Luomasi verkkoresurssi on nyt valittuna **Valitse tietue** -valintaikkunassa. Sulje valintaikkuna valitsemalla **Lisää**.  
6.  Valitse **Tapahtumakäsittelijät**-osassa tapahtuma, jolle haluat määrittää tapahtumakäsittelijän.  
  
7.  Avaa **Käsittelijän ominaisuudet** -valintaikkuna valitsemalla **Lisää**.  
  
8. Valitse **Tiedot**-välilehdessä sopiva kirjasto ja kirjoita sen funktio nimi, joka tapahtumalle on suoritettava.  
  
9. Tapahtumakäsittelijä on oletusarvoisesti otettu käyttöön. Poista **Käytössä**-valintaruudun valinta, jos et halua ottaa käyttöön tätä tapahtumaa.  
  
     Jotkin funktiot edellyttävät, että funktiolle välitetään suorituskonteksti. Valitse tarvittaessa **Välitä suorituskonteksti ensimmäisenä parametrina**.  
  
     Jotkin funktiot voivat hyväksyä parametrijoukon hallitsemaan funktion toimintaa. Jos niitä tarvitaan, kirjoita ne **Luetteloerottimella erotettujen parametrien luettelo, joka siirretään funktioon** -vaihtoehtoon.  
  
10. Lisää **Riippuvuudet**-välilehdessä komentosarjalle välttämättömät kentät **Alisteiset kentät** -alueella.  
  
11. Sulje **Käsittelijän ominaisuudet** -valintaikkuna valitsemalla **OK**.  
  
12. Kun tapahtumakäsittelijä on lisätty, voit muokata funktion suoritusjärjestystä suhteessa muihin funktioihin siirtämällä sitä ylös- tai alaspäin vihreillä nuolilla.  
  
13. Sulje elementin ominaisuusikkuna valitsemalla **OK**.  
  
14. Tallenna muutokset valitsemalla **Tallenna**. Julkaise lomake valitsemalla **Julkaise**.  
  
> [!NOTE]
>  Vaikka voit muokata käyttöliittymässä komentosarjojen latausjärjestystä vihreiden ylä- ja alanuolten avulla, komentosarjoja ei tosiasiassa ladata peräkkäisessä järjestyksessä.   

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)

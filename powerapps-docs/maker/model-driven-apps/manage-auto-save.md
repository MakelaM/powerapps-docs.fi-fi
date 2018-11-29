---
title: Automaattisen tallennuksen käytöstäpoisto mallipohjaisessa sovelluksessa PowerAppsin avulla | MicrosoftDocs
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
author: Mattp123
ms.assetid: 2e7f75dd-7a3f-4716-b995-b626929c0501
caps.latest.revision: 14
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="disable-auto-save-in-a-model-driven-app"></a>Automaattisen tallennuksen käytöstäpoisto mallipohjaisessa sovelluksessa

Automaattisen tallentamisen avulla sovelluksen käyttäjät voivat keskittyä työntekoon lomakkeen tietojen tallentamisen sijaan. Useimmat ihmiset ovat tyytyväisiä, jos tietoja ei tarvitse tallentaa aina tietueen päivittämisen jälkeen. Joillakin organisaatioilla voi olla mukautuksia, jotka vaativat erillisen tallentamisen. Näille organisaatioille on olemassa vaihtoehtoja, joiden avulla automaattinen tallentaminen voidaan ottaa käyttöön.  
  
<a name="BKMK_HowAutoSaveWorks"></a>   

## <a name="how-auto-save-works"></a>Automaattisen tallentamisen toiminta  
 Kaikissa [Päivitetyt entiteetti ja perinteiset entiteetit](create-design-forms.md#updated-versus-classic-entities) -kohdan päälomakkeissa on käytössä automaattinen tallentaminen oletusarvoisesti. Tietueen luomisen jälkeen (alkuperäisesti tallennettu) kaikki lomakkeeseen tehdyt muutokset tallennetaan 30 sekuntia muutoksen tekemisen jälkeen. Jos lomakkeeseen ei tehdä muutoksia, automaattista tallennusta ei tapahdu, kun lomake on auki. Kun muutos tehdään, 30 sekunnin jakso ennen automaattista tallennusta alkaa uudelleen. Kenttää, jota joku käyttäjä muokkaa parhaillaan, ei tallenneta automaattisesti. Jos joku toinen käyttäjä on päivittänyt saman tietueen sen aikana, kun muokkaat sitä itse, muutokset noudetaan ja näytetään lomakkeessa automaattisen tallentamisen yhteydessä.  
  
 Kun automaattinen tallentaminen on käytössä, tallennuspainike näkyy vain tietueen ensimmäisen tallentamisen yhteydessä. Komentopalkin tallennuspainike ei näy tietueen luonnin jälkeen. Oikeassa alakulmassa näkyy kuitenkin ![Automaattinen tallennus](media/auto-save-icon.png "Automaattinen tallennus") -painike , joka näyttää mahdolliset tallentamattomat muutokset. Tämä ohjausobjekti näkyy myös silloin, kun automaattinen tallentaminen ei ole käytössä.  
  
 Tallenna tietue ja päivitä lomakkeen tiedot heti valitsemalla tämä painike. Kun automaattinen tallentaminen on käytössä, tietue tallennetaan aina, kun siirryt pois tietueesta tai suljet erillisen tietueen näyttävän ikkunan. Et tarvitse niiden entiteettien lomakkeissa olevaa **Tallenna ja sulje** -painiketta, joita ei ole päivitetty.  
  
<a name="BKMK_AutoSave"></a>   
## <a name="should-you-disable-auto-save"></a>Kannattaako automaattinen tallentaminen ottaa pois käytöstä?  
 Laajennusten työnkulkujen tai lomakkeiden komentosarjat, jotka käynnistetään tietueen tallentamisen yhteydessä, suoritetaan aina automaattisen tallentamisen yhteydessä. Tämä voi aiheuttaa ei-toivottuja toimintoja, jos laajennuksia ei ole suunniteltu toimimaan yhdessä automaattisen tallentamisen kanssa. Laajennusten, työnkulkujen ja lomakkeiden komentosarjojen tulisi etsiä tiettyjä muutoksia, eikä niitä tule suorittaa jokaisen tallennuksen yhteydessä, vaikka automaattinen tallentaminen olisi käytössä.  
  
 Jos entiteetille on määritetty seuranta, jokaista tallennusta käsitellään erillisenä päivityksenä. Jos käyttäjä viipyy tallentamattomia muutoksia omaavalla lomakkeella yli 30 sekunnin ajan, lisämerkintä tehdään vain, jos käyttäjä lisää tietoja automaattisen tallentamisen suorituksen jälkeen. Jos järjestelmässä on raportteja, jotka ovat riippuvaisia seurannan tiedoista ja käsittelevät jokaista tallennusta tietueen yksittäisenä käsittelynä, käsittelytiheys saattaa nousta. Jos tämä tapa on käytössä, kannattaa ottaa huomioon, että yksittäisen käyttäjän toiminnot eivät ole luotettava mittari, olipa automaattinen tallentaminen käytössä tai ei.  
  
<a name="BKMK_DisableAutoSaveOrg"></a>   
## <a name="disable-auto-save-for-the-organization"></a>Automaattisen tallentamisen poistaminen käytöstä organisaatiossa  
 Jos automaattinen tallentaminen aiheuttaa mielestäsi ongelmia käytössä olevien laajennusten kanssa, voit poistaa sen käytöstä organisaatiossa. Automaattista tallentamista ei voi poistaa käytöstä yksittäissä entiteeteissä tai lomakkeissa.  
  
1. Siirry kohtaan **[Asetukset](advanced-navigation.md#settings)** > **Hallinta**.  
  
2.  Valitse **Järjestelmäasetukset**.  
  
3.  Valitse **Ota automaattinen tallentaminen käyttöön kaikissa lomakkeissa** -vaihtoehdolle arvoksi **Ei**.  
  
<a name="BKMK_DisalbleAutoSaveForm"></a>   
## <a name="disable-auto-save-for-a-form"></a>Automaattisen tallentamisen poistaminen käytöstä lomakkeessa  
 Jos haluat poistaa tietyn entiteettilomakkeen automaattisen tallentamisen käytöstä, voit lisätä koodin entiteetin `OnSave`-tapahtumaan.  
  
> [!NOTE]
>  Automaattinen tallentaminen poistetaan käytöstä lomakkeessa, mutta tiedot tallennetaan yhä, kun käyttäjä valitsee oikeassa alakulmassa olevan ![Automaattinen tallennus](media/auto-save-icon.png "Automaattinen tallennus") -painikkeen. Jos käyttäjä yrittää siirtyä pois lomakkeesta tai sulkea lomakkeen tietojen muuttamisen jälkeen, hän saa kehotuksen tallentaa muutokset ennen lomakkeesta poistumista tai sen sulkemista.  
  
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti.  
  
3.  Avaa muokattava lomake.  
  
4.  JavaScript-WWW-resurssin luominen ja lisääminen lomakkeeseen:  
  
    1.  Valitse lomake-editorin **Lomake**-ryhmän **Lomakkeen ominaisuudet** -kohta.  
  
    2.  Valitse **Tapahtumat**-välilehden **Lomakekirjastot**-kohdan alla oleva **Lisää**-kohta.  
  
    3.  Valitse **Valitse tietue** -valintaikkunassa **Uusi**.  
  
    4.  Syötä WWW-resurssilomakkeeseen seuraavat tiedot:  
  
        |||  
        |-|-|  
        |**Nimi**|preventAutoSave|  
        |**Näyttönimi**|Automaattisen tallentamisen estäminen|  
        |**Tyyppi**|Komentosarja (JScript)|  
  
    5.  Valitse **Tyyppi**-kentän vieressä oleva **Tekstieditori**-kohta.  
  
    6.  Lisää **Lähde**-kenttään seuraava koodi:  
  
        ```javascript  
        function preventAutoSave(econtext) {  
            var eventArgs = econtext.getEventArgs();  
            if (eventArgs.getSaveMode() == 70 || eventArgs.getSaveMode() == 2) {  
                eventArgs.preventDefault();  
            }  
        }  
  
        ```  
  
    7.  Valitse **OK**, kun haluat sulkea tekstieditorin.  
  
    8.  Tallenna WWW-resurssi valitsemalla **Tallenna** ja sulje sitten WWW-resurssin ikkuna.  
  
    9. Luomasi WWW-resurssi valitaan **Valitse tietue** -valintaikkunaan. Sulje valintaikkuna valitsemalla **Lisää**.  
  
5.  OnSave-tapahtuman määrittäminen:  
  
    1.  Määritä **Lomakkeen ominaisuudet** -ikkunan **Tapahtumakäsittelijät**-osan **Tapahtuma**-kohdan arvoksi **OnSave**.  
  
    2.  Valitse **Lisää**.  
  
    3.  Määritä **Käsittelijän ominaisuudet** -ikkunassa **kirjastoksi** edellisessä osavaiheessa lisäämäsi WWW-resurssi.  
  
    4.  Kirjoita **Toiminto**-kenttään `preventAutoSave`. Kirjainkoko otetaan huomioon. Älä lisää lainausmerkkejä.  
  
    5.  Varmista, että **Käytössä**-valintaruutu on valittuna.  
  
    6.  Valitse **Välitä suorituskonteksti ensimmäisenä parametrina** -kohta.  
  
        > [!IMPORTANT]
        >  Jos et tee niin, komentosarja ei toimi.  
  
         **Käsittelijän ominaisuudet** -valintaikkunan pitäisi näyttää seuraavalta. Mukautuksen etuliite new_ voi vaihdella sen mukaan, mikä organisaation oletusjulkaisijan määrittämä mukautuksen etuliite on.  
  
 ![OnSave- lomaketapahtumien käsittelijä estää automaattisen tallentamisen Dynamics 365:ssa](media/prevent-auto-save-script.png "OnSave- lomaketapahtumien käsittelijä estää automaattisen tallentamisen Dynamics 365:ssa")  
  
    7.  Sulje **Käsittelijän ominaisuudet** -valintaikkuna valitsemalla **OK**.  
  
    8.  Jos `OnSave`-tapahtumalla on muita tapahtuman käsittelijöitä, siirrä tämä ylimmäksi vihreiden nuolten avulla.  
  
6. Sulje **Lomakkeen ominaisuudet** -valintaikkuna valitsemalla **OK**.  
  
7. Valitse **Tallenna ja sulje**, kun haluat sulkea lomakkeen.  
  
8. Valitse ratkaisunhallinnassa **Julkaise kaikki mukautukset**.  
  
 Kun olet ottanut tämän komentosarjan käyttöön `OnSave`-tapahtumassa, **tallentamattomia muutoksia** -viesti tulee esille lomakkeen oikeaan alakulmaan, kun käyttäjät muokkaavat tietuetta tämän lomakkeen avulla. Viesti tulee esille samalla tavalla kuin silloin, kun automaattinen tallentaminen on käytössä. Sanoma kuitenkin häviää vasta sen jälkeen, kun käyttäjä valitsee sanoman vieressä olevan ![Automaattinen tallennus](media/auto-save-icon.png "Automaattinen tallennus") -painikkeen.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Luo ja suunnittele lomakkeita](create-design-forms.md)      

 

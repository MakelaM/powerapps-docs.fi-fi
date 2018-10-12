---
title: Malliin perustuvien sovellusten ruudukoiden (luetteloiden) muokattavaksi muuttaminen mukautetulla Muokattava ruudukko -ohjausobjektilla PowerAppsissa | MicrosoftDocs
description: Lue ohjeet Muokattava ruudukko -ohjausobjektin käyttöön
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: cefbc0c2-769b-4230-ab5a-b28a84630a42
caps.latest.revision: 8
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: 704280dbed2177ba9a5467e2897980f78c31b050
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680555"
---
# <a name="make-model-driven-app-grids-lists-editable-using-the-editable-grid-custom-control"></a>Malliin perustuvien sovellusten ruudukoiden (luetteloiden) muokattavaksi muuttaminen mukautetulla Muokattava ruudukko -ohjausobjektilla

Aiemmissa Dynamics CRM -versioissa käyttäjät eivät voineet antaa tietoja suoraan lomakkeiden ruudukoihin (joita kutsutaan joskus myös luetteloiksi) tai aliruudukoihin. Käyttäjien täytyi avata lomake valitsemalla ruudukon tietue, muokata tietoja ja tallentaa sitten tiedot. Tämä edellytti useita vaiheita. Muokattavien ruudukoiden avulla käyttäjät voivat tehdä monipuolisia muokkauksia suoraan ruudukoissa ja aliruudukoissa verkkosovelluksella, tabletilla ja puhelimella.  
  
 ![Muokattavan ruudukon esimerkkejä](media/editable-grid-examples.png "Muokattavan ruudukon esimerkkejä")  
  
 Kun muokattavat ruudukot on otettu käyttöön Muokattava ruudukko -ohjausobjektilla, käyttäjät voivat muokata useimpia kenttätyyppejä, esimerkiksi perushakukenttiä ja asetusjoukkoja.  

**Muokattavat ruudukot tukevat**
  
-   tietueiden muokkaamista kontekstissa entiteetti- ja aliruudukkotasolla (mukaan lukien mukautetut entiteetit)  
  
-   järjestelmänäkymiä ja henkilökohtaisia näkymiä  
  
-   verkko- ja mobiilisovelluksia  
  
-   siirtymistä hiirellä tai näppäimistöllä  
  
-   ryhmittelyä ja lajittelua (nykyisen näkymän minkä tahansa sarakkeen perusteella voi lajitella tai ryhmitellä)  
  
-   suodatusta  
  
-   sarakkeiden siirtämistä ja koon muuttamista  
  
-   sivutusta  
  
-   muutosten tallentamista istunnosta toiseen ryhmittelyä, lajittelua, suodatusta, sivutusta sekä sarakkeiden siirtämistä ja koon muuttamista varten  
  
-   hakumääritystä  
  
-   laskettuja kenttiä ja koostekenttiä  
  
-   liiketoimintasääntöjä (näytä virheilmoitus, määritä kentän arvo, määritä pakolliseksi, määritä oletusarvo, lukitse tai avaa kenttä)  
  
-   JavaScript-tapahtumia  
  
-   solujen käyttöön ottamista ja käytöstä poistamista käyttöoikeusroolin perusteella  
  
-   sitä, että käyttäjät voivat jatkaa haun ja kaavioiden käyttämistä ja että käyttäjät voivat käyttää toimintopalkkia kuten Vain luku -ruudukoissa.  
  
## <a name="make-main-grids-editable"></a>Pääruudukoiden muuttaminen muokattaviksi  
  
1.  Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
  
2.  Valitse **Entiteetit**-luettelosta haluamasi entiteetti, valitse **Ohjausobjektit**-välilehti ja valitse sitten **Lisää ohjausobjekti**.  
  
     ![Lisää mukautettu Muokattava ruudukko -ohjausobjekti](media/add-editable-grids-custom-control.png "Lisää mukautettu Muokattava ruudukko -ohjausobjekti")  
  
3.  Valitse **Lisää ohjausobjekti** -valintaikkunassa **Muokattava ruudukko** ja valitse sitten **Lisää**.  
  
4.  Valitse lisätyllä **Muokattava ruudukko** -rivillä, missä sovellusversioissa haluat käyttää ruudukkoa. Tämä tekee Muokattava ruudukko -ohjausobjektista valitun lomakkeen oletusohjausobjektin valituissa sovellusversioissa.  
  
     ![Muokattava ruudukko -rivi ja sovellusversion valinta](media/editable-grid-row-wit-factor-selection.png "Muokattava ruudukko -rivi ja sovellusversion valinta")    

   > [!NOTE]
   >  Sovellukset voivat sovellusta käyttäessään vaihtaa muokattavien ruudukoiden ja Vain luku -ruudukoiden välillä.  
      
5.  Jos haluat lisätä haun, valitse **Muokattava ruudukko** -asetusjoukossa **Lisää valinta**. Toimi sitten **Määritä ominaisuus Lisää valinta** -valintaikkunassa seuraavasti:  
  
    1.  Valitse **käytettävissä olevien näkymien** luettelossa näkymä, johon haku lisätään (esimerkiksi **Omat aktiiviset tilit**).  
  
    2.  Valitse **käytettävissä olevien sarakkeiden** luettelossa lisättävä hakusarake (esimerkiksi **Ensisijainen yhteyshenkilö**).  
  
    3.  Valitse **oletusnäkymän** luettelossa hakukentän tietolähde.  
  
    4.  Jos haluat rajoittaa näytettäviä tietueita, valitse **Näytä vain tietueet, joissa** -valintaruutu, valitse haluamasi ehdot luettelosta ja valitse sitten **OK**.  
  
         ![Haun lisääminen Muokattava ruudukko -ohjausobjektiin](media/add-lookup-in-editable-grid-control.png "Haun lisääminen Muokattava ruudukko -ohjausobjektiin")  
     
6.  Jos sinulla on sisäkkäinen ruudukko, valitse **sisäkkäisen ruudukkonäkymän** kynäkuvake ja valitse sitten sisäkkäisen ruudukon entiteetti ja näkymä. Valitse **sisäkkäisen ruudukon pääkohteen tunnukseksi** entiteettien suhde. Esimerkiksi ParentAccountID-kenttä yhdistetään **tilin** ja **yhteyshenkilön** entiteetteihin.  
  
    > [!NOTE]
    >  Sisäkkäiset ruudukot ovat käytettävissä vain puhelin- ja tablettisovelluksissa, ei verkkosovelluksessa.  
  
7.  Jos et halua sallia, että käyttäjät voivat ryhmitellä tietoja näkymän minkään sarakkeen perusteella (jos haluat esimerkiksi säästää tilaa), valitse **Ryhmittele sarakkeen mukaan** rivin kynäpainike ja valitse sitten **Määritä ominaisuus Ryhmittele sarakkeen mukaan** -valintaikkunassa **Ei käytössä**. Valitse tämän jälkeen **OK**.  
  
    > [!TIP]
    >  Tästä on eniten hyötyä lomakkeiden aliruudukoissa.  
  
8.  Jos haluat lisätä JavaScript-tapahtumia, valitse **Tapahtumat**-välilehti ja valitse sitten haluamasi entiteetit, kentät ja tapahtumat. Lisätiedot: [Kehittäjädokumentaatio: muokattavien ruudukoiden käyttö](/dynamics365/customer-engagement/developer/customize-dev/use-editable-grids-dynamics-365.md)  
  
     ![Tapahtumien lisääminen Muokattava ruudukko -ohjausobjektiin](media/add-events-in-editable-grid-control.png "Tapahtumien lisääminen Muokattava ruudukko -ohjausobjektiin")  
  
9. Tallenna tekemäsi muutokset valitsemalla toimintariviltä **Tallenna**.  
  
10. Kun olet valmis tarjoamaan muutokset tiimisi käyttöön, valitse toimintoriviltä **Julkaise**.  
  
11. Jos haluat testata muutoksesi, siirry vaiheessa 5 määrittämääsi näkymään ja tee joitain muutoksia kontekstissa.  
  
## <a name="make-a-sub-grid-on-a-form-editable"></a>Lomakkeen aliruudukon muuttaminen muokattavaksi

> [!NOTE] 
> - Jos käyttäjä haluaa tallentaa muokattavan ruudukon aliruudukon muutoksen, hänen täytyy tallentaa ennen lomakkeesta pois siirtymistä.
> - Jos käytät vanhoja lomakkeita (Dynamics CRM 2016:ta vanhemmat versiot) ja otat muokattavan ruudukon käyttöön aliruudukossa, aliruudukkoa ei näytetä. Järjestelmänvalvojat voivat tarvittaessa poistaa vanhat lomakkeet käytöstä järjestelmäasetuksissa.
  
1.  Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
  
2.  Avaa aliruudukon sisältävä lomake.  
  
3.  Valitse soveltuva ohjausobjekti ja valitse sitten valintanauhasta **Muuta ominaisuuksia**.  
  
4.  Valitse **Määritä ominaisuudet** -valintaikkunassa **Ohjausobjektit** > **Lisää ohjausobjekti** ja toimi sitten yllä annettujen ohjeiden mukaisesti.  
  
## <a name="supported-standard-entities"></a>Tuetut vakioentiteetit  
  
||||  
|-|-|-|  
|**Verkko, tabletti tai puhelin**|**Vain tabletti tai puhelin**|**Vain verkko**|  
|Tili<br /><br /> Tapaaminen<br /><br /> Varattava resurssi<br /><br /> Varattavan resurssin varaus<br /><br /> Varattavan resurssin varauksen otsikko<br /><br /> Varattavan resurssin luokka<br /><br /> Varattavan resurssin luokkamääritys<br /><br /> Varattavan resurssin ominaisuus<br /><br /> Varattavan resurssin ryhmä<br /><br /> Varauksen tila<br /><br /> Tapaus<br /><br /> Luokka<br /><br /> Ominaisuus<br /><br /> Kilpailija<br /><br /> Yhteystiedot<br /><br /> Sähköposti<br /><br /> Oikeus<br /><br /> Palaute<br /><br /> Lasku<br /><br /> Tietoartikkeli<br /><br /> Tietoartikkelien näyttökerrat<br /><br /> Tietokantatietue<br /><br /> Liidi<br /><br /> Mahdollisuus<br /><br /> Tilaus<br /><br /> Puhelu<br /><br /> Hinnasto<br /><br /> Tuote<br /><br /> Jono<br /><br /> Tarjous<br /><br /> Luokitusmalli<br /><br /> Luokitusarvo<br /><br /> SLA-suorituskykyilmaisimen ilmentymä<br /><br /> Yhteisöpalveluaktiviteetti<br /><br /> Yhteisöpalveluprofiili<br /><br /> Synkronointivirhe<br /><br /> Tehtävä<br /><br /> Ryhmä<br /><br /> Käyttäjä|Toiminta<br /><br /> Liite<br /><br /> Kanavaoikeusprofiilin sääntökohde<br /><br /> Kilpailijan osoite<br /><br /> Yhteys<br /><br /> Yhteysrooli<br /><br /> Sähköpostiallekirjoitus<br /><br /> Sähköpostimalli<br /><br /> Vanhentunut prosessi<br /><br /> Laskutustuote<br /><br /> Tietoartikkelin tapauksen tila<br /><br /> Liidistä mahdollisuuteen -myynti<br /><br /> Prosessi<br /><br /> Postilaatikko<br /><br /> Uusi prosessi<br /><br /> Huomautus<br /><br /> Mahdollisuuden tuote<br /><br /> Myyntimahdollisuusprosessi<br /><br /> Tilaustuote<br /><br /> Organisaatio<br /><br /> Puhelu palvelupyynnöksi -prosessi<br /><br /> Hinnaston nimike<br /><br /> Jonon kohde<br /><br /> Tarjoustuote<br /><br /> SharePoint-tiedosto<br /><br /> Käännösprosessi|Kampanja<br /><br /> Kampanja-aktiviteetti<br /><br /> Kampanjan vastaus<br /><br /> Kanavaoikeusprofiili<br /><br /> Kanavaoikeusprofiilin sääntö<br /><br /> Sopimus<br /><br /> Oikeuden malli<br /><br /> Ulkoinen osapuoli<br /><br /> Faksi<br /><br /> Kirje<br /><br /> Markkinointiluettelo<br /><br /> Sijainti<br /><br /> Pikakampanja<br /><br /> Toistuva tapaaminen<br /><br /> Myyntimateriaali<br /><br /> SLA|  
 
##  <a name="data-types-that-arent-editable-in-an-editable-grid"></a>Tietotyypit, jotka eivät ole muokattavissa muokattavassa ruudukossa
Seuraavia tietotyyppejä ei voi muokata muokattavissa ruudukoissa: asiakkaan ja osapuoliluettelon hakukentät, koosteosoitekentät, tilan kentät ja haun entiteetteihin liittyvät kentät (esimerkiksi tilin entiteetissä on yhteyshenkilön haku, jossa yhteyshenkilön kenttä on muokattavissa, mutta yhteyshenkilön sähköpostiosoitteen kenttä ei ole muokattavissa).  
 
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Pikanäppäinten käyttö muokattavissa ruudukoissa](https://docs.microsoft.com/dynamics365/customer-engagement/basics/keyboard-shortcuts#editable-grids-views)


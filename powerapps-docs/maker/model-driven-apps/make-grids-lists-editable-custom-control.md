---
title: Mallipohjaisen sovelluksen ruudukoiden (luetteloiden) muuttaminen muokattaviksi muokattavan ruudukon mukautetun ohjausobjektin avulla PowerAppsissa | MicrosoftDocs
description: Opettele käyttämään muokattavan ruudukon mukautettavaa ohjausobjektia
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="make-model-driven-app-grids-lists-editable-using-the-editable-grid-custom-control"></a>Mallipohjaisen sovelluksen ruudukoiden (luetteloiden) muuttaminen muokattavan ruudukon mukautetun ohjausobjektin avulla

Dynamics CRM:n aiemmissa versioissa käyttäjät eivät voineet antaa tietoja suoraan lomakkeiden ruudukoissa (joita joskus kutsutaan luetteloiksi) tai aliruudukoissa. Lomake oli sen sijaan avattava ruudukkoa napsauttamalla, jonka jälkeen tietoja voitiin muokata ja muokkaukset tallentaa. Tämä edellytti useita vaiheita. :n muokattavien ruudukoiden avulla käyttävät voivat muokata rivejä monella tavoin suoraan ruudukoissa ja aliruudukoissa riippumatta siitä, käyttävätkö he verkkosovellusta, tablettia vai puhelinta.  
  
 ![Muokattavan ruudukon esimerkkejä](media/editable-grid-examples.png "Muokattavan ruudukon esimerkkejä")  
  
 Kun muokattavat ruudukot otetaan käyttöön mukautetulla Muokattavat ruudukot -ohjausobjektilla, käyttäjät voivat muokata useimpia kenttätyyppejä, kuten perushakukenttiä ja asetusjoukkoja.  

**Muokattavien ruudukoiden tuki:**
  
-   Tietueiden rivimuokkaus entiteetti- tai aliruudukkotasolla (sisältää mukautetut entiteetit)  
  
-   Järjestelmänäkymät ja henkilökohtaiset näkymät  
  
-   Verkko- ja mobiiliasiakasohjelmat  
  
-   Siirtyminen näppäimistön ja hiiren avulla  
  
-   Ryhmittely ja lajittelu (ryhmittelyn ja lajittelun voi tehdä minkä tahansa nykyisen näkymän sarakkeen perusteella)  
  
-   Suodatus  
  
-   Sarakkeiden siirtäminen ja koon muuttaminen  
  
-   Sivutus  
  
-   Muutosten tallentaminen istunnosta toiseen sarakkeiden ryhmittelyä, lajittelua, suodatusta, sivutusta, siirtämistä ja koon muuttamista varten  
  
-   Haun määrittäminen  
  
-   Laskennalliset kentät ja koontikentät  
  
-   Liiketoimintasäännöt (Näytä virhesanoma, Määritä kentän arvo, Määritä pakolliseksi, Määritä oletusarvo, Lukitse kenttä tai poista kentän lukitus)  
  
-   JavaScript-tapahtumat  
  
-   Solujen ottaminen käyttöön tai poistaminen käytöstä käyttöoikeusroolin perusteella  
  
-   Käyttäjät voivat edelleen käyttää hakuja ja kaavioita sekä toimintoriviä, kuten vain luku -ruudukoissakin  
  
## <a name="make-main-grids-editable"></a>Pääruudukkojen muuttaminen muokattaviksi  
  
1.  Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
  
2.  Avaa **Entiteetit**-luettelossa sopiva entiteetti, valitse **Ohjausobjektit** -välilehti ja valitse **Lisää ohjausobjekti**.  
  
     ![Muokattavien ruudukoiden ohjausobjekti lisääminen](media/add-editable-grids-custom-control.png "Muokattavien ruudukoiden ohjausobjekti lisääminen")  
  
3.  Valitse **Lisää ohjausobjekti** -valintaikkunassa ensin **Muokattava ruudukko** ja sitten **Lisää**.  
  
4.  Valitse lisätyllä **Muokattava ruudukko** -rivillä muodot, jota haluat käyttää ruudukossa. Muokattava ruudukko -ohjausobjekti on nyt valittujen muotojen oletusohjausobjekti.  
  
     ![Muokattava ruudukkorivi, jossa on lomakkeen kerroinvalinta](media/editable-grid-row-wit-factor-selection.png "Muokattava ruudukkorivi, jossa on lomakkeen kerroinvalinta")    

   > [!NOTE]
   >  Käyttäjät voivat vaihdella muokattavia ruudukoista ja vain luku -ruudukoita käytön aikana.  
      
5.  Lisää haku valitsemalla **Muokattava ruudukko** -asetusryhmässä **Lisää haku**. Sitten **Määritä Lisää haku -ominaisuus** -valintaikkunassa  
  
    1.  valitaan **Käytettävissä olevat näkymät** -luettelossa hakuun lisättävä näkymä (valitse esimerkiksi **Omat aktiiviset asiakkaat**)  
  
    2.  valitaan **Käytettävissä olevat sarakkeet** -luettelossa lisättävä hakusarake (valitse esimerkiksi **Ensisijainen yhteyshenkilö**)  
  
    3.  valitaan **Oletusnäkymä**-luettelossa hakukentän tietolähde.  
  
    4.  Jos haluat rajoittaa näytettävien tietueiden määrää, valitse ensin **Näytä vain tietueet, joissa** -valintaruutu ja sitten ehdot luettelosta ja sitten **OK**.  
  
         ![Muokattavan ruudukon ohjausobjektin haun lisääminen](media/add-lookup-in-editable-grid-control.png "Muokattavan ruudukon ohjausobjektin haun lisääminen")  
     
6.  Jos käytössä on sisäkkäinen ruudukko, napsauta **Sisäkkäinen ruudukkonäkymä** -kynäpainiketta ja valitse sisäkkäisen ruudukon entiteetti ja näkymä. Valitse **Sisäkkäisen ruudukon pääkohteen tunnus** -kohtaan entiteettien suhde. Esimerkiksi ParentAccountID-kenttä yhdistää **Asiakas**- ja **Yhteyshenkilö**-entiteetit.  
  
    > [!NOTE]
    >  Sisäkkäisiä ruudukoita voi käyttää vain puhelimissa ja tableteissa, ei verkkoversiossa.  
  
7.  Et halua, että käyttäjä ryhmittää tietoja näkymissä sarakkeiden avulla (haluat esimerkiksi säästää tilaa), napsauta **Ryhmittele sarakkeen mukaan** -rivillä kynäpainiketta ja valitse sitten **Määritä Ryhmittele sarakkeen mukaan -ominaisuus** -valintaikkunassa **Ei käytössä** ja valitse lopuksi **OK**.  
  
    > [!TIP]
    >  Tämä on kätevää lähinnä lomakkeiden aliruudukoissa.  
  
8.  Jos haluat lisätä JavaScript-tapahtumia, valitse **Tapahtumat**-välilehti ja valitse sitten sopiva entiteetit, kentät ja tapahtumat. Lisätietoja: [Sovelluskehittäjän dokumentaatio: Muokattavien ruudukoiden käyttäminen](/dynamics365/customer-engagement/developer/customize-dev/use-editable-grids-dynamics-365.md)  
  
     ![Muokattavan ruudukon ohjausobjektin tapahtuman lisääminen](media/add-events-in-editable-grid-control.png "Muokattavan ruudukon ohjausobjektin tapahtuman lisääminen")  
  
9. Tallenna työsi valitsemalla toimintorivillä **Tallenna**.  
  
10. Kun muutokset ovat valmiit ryhmän käyttöön, valitse toimintorivillä **Julkaise**.  
  
11. Voit testata tekemäsi muutokset siirtymällä vaiheessa 5 määritettyyn näkymään ja muokkaamalla rivejä.  
  
## <a name="make-a-sub-grid-on-a-form-editable"></a>Lomakkeen aliruudukon muuttaminen muokattavaksi

> [!NOTE] 
> - Muokattavan ruudukon muutoksen tallentaminen aliruudukossa edellyttää, että käyttäjä tekee tallennuksen ennen lomakkeesta poistumista.
> - Jos käytössä ovat vanhat versiot (Dynamics CRM 2016 -versiota vanhemmat versiot) ja muokattavassa oleva ruudukko aliruudukossa, muokattavissa olevaa aliruudukkoa ei hahmonneta. Järjestelmänvalvojat voivat tarvittaessa ottaa vanhat lomakkeet pois käytöstä järjestelmäasetuksissa.
  
1.  Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
  
2.  Avaa aliruudukon sisältävä lomake.  
  
3.  Valitse ensin sopiva ohjausobjekti ja valitse sitten toimintorivillä **Muuta ominaisuuksia**.  
  
4.  Valitse **Määritä ominaisuudet** -valintaikkunassa ensin **Ohjausobjektit**, sitten **Lisää ohjausobjekti** ja toista lopuksi edellä kuvatut vaiheet.  
  
## <a name="supported-standard-entities"></a>Tuetut vakioentiteetit  
  
||||  
|-|-|-|  
|**Verkko, tabletti ja puhelin**|**Vain tabletti ja puhelin**|**Vain verkko**|  
|Asiakas<br /><br /> Tapaaminen<br /><br /> Varattava resurssi<br /><br /> Varattavissa olevan resurssin varaus<br /><br /> Varattavissa olevan resurssin otsikko<br /><br /> Varattavissa olevan resurssin luokka<br /><br /> Varattavissa olevan resurssin luokkaliitos<br /><br /> Varattavissa olevan resurssin ominaisuus<br /><br /> Varattavissa oleva resurssiryhmä<br /><br /> Varauksen tila<br /><br /> Palvelupyyntö<br /><br /> Luokka<br /><br /> Ominaisuus<br /><br /> Kilpailija<br /><br /> Yhteyshenkilö<br /><br /> Sähköposti<br /><br /> Oikeudet<br /><br /> Palaute<br /><br /> Lasku<br /><br /> Tietoartikkeli<br /><br /> Tietoartikkelien näyttökerrat<br /><br /> Tietokantatietue<br /><br /> Lead<br /><br /> Mahdollisuus<br /><br /> Tilaus<br /><br /> Puhelu<br /><br /> Hinnasto<br /><br /> Tuote<br /><br /> Jono<br /><br /> Tarjous<br /><br /> Luokitusmalli<br /><br /> Luokitusarvo<br /><br /> SLA-suorituskykyilmaisimen ilmentymä<br /><br /> Yhteisöpalveluaktiviteetti<br /><br /> Yhteisöpalveluprofiili<br /><br /> Synkronointivirhe<br /><br /> Tehtävä<br /><br /> Ryhmä<br /><br /> Käyttäjä|Aktiviteetti<br /><br /> Liite<br /><br /> Kanavaoikeusprofiilin sääntökohde<br /><br /> Kilpailijan osoite<br /><br /> Yhteys<br /><br /> Yhteysrooli<br /><br /> Sähköpostin allekirjoitus<br /><br /> Sähköpostimalli<br /><br /> Vanhentunut prosessi<br /><br /> Laskutustuote<br /><br /> Tietoartikkelin tapaus<br /><br /> Liidistä myyntimahdollisuudeksi<br /><br /> Prosessi<br /><br /> Postilaatikko<br /><br /> Uusi prosessi<br /><br /> Huomautus<br /><br /> Mahdollisuuden tuote<br /><br /> Myyntimahdollisuusprosessi<br /><br /> Tilaustuote<br /><br /> Organisaatio<br /><br /> Puhelu palvelupyynnöksi -prosessi<br /><br /> Hinnastonimike<br /><br /> Jonon kohde<br /><br /> Tarjoustuote<br /><br /> SharePoint-tiedosto<br /><br /> Käännösprosessi|Kampanja<br /><br /> Kampanja-aktiviteetti<br /><br /> Kampanjapalaute<br /><br /> Kanavaoikeusprofiili<br /><br /> Kanavaoikeusprofiilin sääntö<br /><br /> Palvelusopimus<br /><br /> Oikeuksien malli<br /><br /> Ulkoinen osapuoli<br /><br /> Faksi<br /><br /> Kirje<br /><br /> Markkinointiluettelo<br /><br /> Sijainti<br /><br /> Pikakampanja<br /><br /> Toistuva tapaaminen<br /><br /> Myyntimateriaali<br /><br /> Palvelutasosopimus (SLA)|  
 
##  <a name="data-types-that-arent-editable-in-an-editable-grid"></a>Tietotyypit, joita ei voi muokata muokattavassa ruudukossa
Seuraavia tietotyyppejä ei voi muokata muokattavissa ruudukoissa: Asiakas- ja Osapuoliluettelo-hakukentät; Yhdistelmä (osoite) -kentät; Tila-kentät; Entiteettiin liittyvät hakukentät (esimerkiksi Asiakas-entiteetti sisältää yhteyshenkilöhaun, jossa Yhteyshenkilö-kenttää voi muokata EmailAdress(Contact)-kenttää ei).  
 
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Pikanäppäinten käyttö muokattavissa ruudukoissa](https://docs.microsoft.com/dynamics365/customer-engagement/basics/keyboard-shortcuts#editable-grids-views)


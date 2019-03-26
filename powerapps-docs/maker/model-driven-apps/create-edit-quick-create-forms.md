---
title: Mallipohjaisen sovelluksen pikaluontilomakkeiden luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Tietoja pikaluontilomakkeen luomisesta tai muokkaamisesta
ms.custom: ''
ms.date: 01/25/2019
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
ms.assetid: 68ca9059-cc5a-45e7-88bd-cc57186bbb48
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-model-driven-app-quick-create-forms-for-a-streamlined-data-entry-experience"></a>Mallipohjaisen sovelluksen pikaluontilomakkeiden luominen tai muokkaaminen tietojen syötön helpottamiseksi

Tässä ohjeaiheessa luodaan pikaluontilomake ja muokataan sitä.

 Pikaluontilomakkeiden avulla sovelluksessa on virtaviivaistettu tietojen syöttökokemus, jota tukee lomakkeen komentosarjojen ja liiketoimintasääntöjen mukaan määritetty logiikka. Pikaluontilomakkeet tulevat näkyviin PowerAppsin mallipohjaisessa sovelluksessa, kun valitset **Luo**-painikkeen siirtymispalkissa tai kun valitset **+ Uusi** luodessasi uutta tietuetta hausta tai aliruudukosta.
  
 Dynamics 365 Customer Engagement -mobiilisovellukset luovat uusia tietueita pikaluontilomakkeilla. Jos entiteetillä on jo määritetty pikaluontilomake, mobiilisovellukset käyttävät tätä lomaketta. Jos entiteetille ei ole määritetty pikaluontilomaketta, PowerApps luo pikaluontilomakkeen tietueiden luomista varten mobiilisovelluksissa päälomakkeen määritelmän perusteella.  
  
<a name="BKMK_QuickCreateFormEntities"></a>   
## <a name="entities-with-quick-create-forms"></a>Entiteetit, joissa on pikaluontilomakkeet  
 Oletusarvon mukaan vain seuraavassa järjestelmäentiteeteissä on pikaluontilomakkeet.  
  
|||||  
|-|-|-|-|  
|Tili|Kampanjapalaute|Palvelupyyntö|Kilpailija|  
|Yhteyshenkilö|Liidi|Mahdollisuus||  
  
Vaikka voit luoda pikaluontilomakkeita järjestelmän aktiviteetti-entiteeteille, lukuunottamatta tapaamisentiteettejä, ne eivät tue pikaluontilomakkeita. Dynamics 365-version 9.0, versiossa tapaaminen-entiteetti sisältää pikaluontilomakkeen Unified Interfacen käytettäväksi. Tällä hetkellä vaihtoehtoa, jolla poistetaan tapaamisentiteetin pikakuvakehakemisto, ei ole tuettu. Jokin toinen ja mitkä tahansa [mukautetut entiteetit](create-design-forms.md) voidaan ottaa käyttöön tukemaan näitä lomakkeita valitsemalla **Salli nopea luominen** entiteettimäärityksessä ja luomalla pikaluontilomake niille. 

Voit ottaa käyttöön mukautettuja aktiviteettientiteettejä tukemaan pikaluontilomakkeita, ja voit luoda pikaluontilomakkeita kyseisille entiteeteille. Mukautettujen aktiviteettientiteettien pikaluontilomakkeita ei kuitenkaan käytetä, kun ihmiset valitsevat **Luo** -painikkeen siirtymispalkissa. Näitä pikaluontilomakkeita voidaan käyttää vain, kun käyttäjät lisäävät uuden tietueen aliruudukkoon, joka näyttää tämän tietyn mukautetun aktiviteettientiteetin.  
  
<a name="BKMK_CreateQuickCreate"></a>   
## <a name="create-a-quick-create-form"></a>Luo pikaluontilomake  
 Vaikka voit määrittää useita pikaluontilomakkeita, vain yhtä pikaluontilomaketta voidaan käyttää kaikkien käyttäjien toimesta. Kaikkien haluama lomake luodaan käyttämällä lomaketilausta. Pikaluontilomakkeita ei voi delegoida käyttöoikeusrooleille ja ne eivät tarjoa käyttäjälle mahdollisuutta vaihtaa lomakkeita.  
  
> [!NOTE]
>  - Entiteetissä on oltava **Salli nopea luominen** -asetus valittuna, jotta pikaluontilomake näytetään. 
>  - Joitakin kenttiä, kuten CREATEDON, ei voi lisätä pikaluontilomakkeeseen.  
  
### <a name="how-to-create-a-quick-create-form"></a>Pikaluontilomakkeen luominen  
  
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.


> [!IMPORTANT]
> Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti.  

3.  Valitse työkaluriviltä **Lisää lomake** > **Pikaluontilomake**.  
  
4.  Vedä mitkä tahansa kentät lomakkeen suunnitteluohjelmassa **kenttien hallinnasta** lomakkeen osiin.  
  
5.  Kun olet valmis, valitse **Tallenna**.  
  
6.  Valitse **Julkaise**, kun haluat nähdä sovelluksen uuden lomakkeen.  
  
<a name="BKMK_EditQuickCreate"></a>   
## <a name="edit-a-quick-create-form"></a>Muokkaa pikaluontilomake  
 Kun pikaluontilomakkeet tukevat lomakkeen komentosarjoja ja liiketoimintasääntöjä, niiden tarkoitus on eri kuin päälomakkeiden ja ne eivät tue kaikkia päälomakkeiden ominaisuuksia. Pikaluontilomakkeissa on aina yksi osa, jossa on kolme saraketta. Et voi lisätä uusia osia tai sarakkeita.  
  
 Seuraavia ohjausobjekteja ei voi lisätä pikaluontilomakkeisiin:  
  
-   Aliruudukot  
  
-   Pikanäkymälomakkeet  
  
-   WWW-resurssit  
  
-   iFrame-kehykset  
  
-   Muistiinpanot  
  
-   Bing-kartat  
  
Jos lisäät yhdistelmäkentän pikaluontilomakkeeseen, se näytetään erillisissä kentissä.  
  
### <a name="to-edit-a-quick-create-form"></a>Muokkaa pikaluontilomake  
  
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  

> [!IMPORTANT]
> Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment).    
  
2. Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti.    

3. Valitse lomakeluettelosta lomake, jossa **Lomaketyyppi** on **Pikaluonti**.  
  
3.  Vedä mitkä tahansa kentät kohteesta **Kenttien hallinta** lomakkeen osiin.  
  
     Katso [komentosarjojen tapahtumankäsittelijöiden muokkaaminen](configure-event-handlers-legacy.md) lisätietoja lomakkeen komentosarjojen tapahtumankäsittelijöiden muokkaamisesta.  
  
4.  Kun olet valmis, valitse **Tallenna**.  
  
5.  Valitse **Julkaise**, kun haluat nähdä sovelluksen muokatun lomakkeen.  
  
### <a name="next-steps"></a>Seuraavat vaiheet  
[Lomake-editorin käyttöliittymän yleiskatsaus](form-editor-user-interface-legacy.md)

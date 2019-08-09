---
title: Mallipohjaisen sovelluksen pikaluontilomakkeiden luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Tietoja pikaluontilomakkeen luomisesta tai muokkaamisesta
ms.custom: ''
ms.date: 05/14/2019
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

## <a name="allow-quick-create-property-form-behavior-for-activities"></a>Salli pikaluonti -ominaisuuden käyttö aktiviteettien lomakkeissa
Päivityksessä 9.1.0.2007 käyttöotettu **Salli pikaluonti** -ominaisuus voidaan ottaa tai poistaa käytöstä kaikissa muissa vakioaktiviteeteissa paitsi toistuvissa tapaamisissa. Voit muuttaa tällä ominaisuudella useimmissa aktiviteeteissa oletusarvoisesti näkyvää lomaketta. **Salli pikaluonti** -ominaisuus on oletusarvoisesti otettu käyttöön ja juuri pikaluontilomake näkyy sovellusalueilla ja sitä tukevissa aktiviteettientiteeteissä. 

> [!div class="mx-imgBorder"] 
> ![](media/allow-quick-create.png "Salli pikaluonti -ominaisuus tapaamisentiteetissä")


### <a name="unified-interface-client-form-display-behavior"></a>Unified Interface -asiakkaan lomakkeen näyttötapa
Seuraavassa taulukossa ilmoitetaan, mikä lomake näytetään oletusarvoisesti, kun **Salli pikaluonti** -ominaisuus on *käytössä* Unified Interface -asiakasohjelmassa.
 
|Sijainti, josta lomaketta käytetään  |Näytetty lomake  |
|---------|---------|
|Tiettyyn aktiviteettiin liitetty ruudukko  | Pikaluonti      |
|Tiettyyn aktiviteettiin liitetty aliruudukko   |  Pikaluonti     |
|Aktiviteettien (activitypointer) ruudukko     | Pikaluonti     |
|Aktiviteettien (activitypointer) liitetty ruudukko   | Pikaluonti    |
|Aktiviteettien (activitypointer) aliruudukko  | Pikaluonti    |
|Yleisen komentopalkin +-painike<sup>1</sup>    | Pikaluonti    |
|Aikajanaseinä   | Pikaluonti    |
|Aktiviteettien (activitypointer) ruudukko   | Ensisijainen   |
|Tiettyyn aktiviteettiin liitetty ruudukko    | Ensisijainen   |

<sup>1</sup>Aktiviteetit näkyvät yleisissä**Luo**- tai **+ Uusi** -painikkeissa, kun **Salli pikaluonti** -ominaisuus on käytössä. Tässä tapauksessa käytetään pikaluontilomaketta, jos sellainen on luotu, tai päälomaketta, jos pikaluontilomaketta ei ole. Jos **Salli pikaluonti** on poistettu käytöstä, entiteetin merkintä ei näy.

### <a name="classic-web-client-form-display-behavior"></a>Perinteisen verkkoasiakaslomakkeen toiminta

Seuraavassa taulukossa ilmoitetaan, mikä lomake näytetään oletusarvoisesti, kun **Salli pikaluonti** -ominaisuus on *käytössä* perinteisessä verkkoasiakasohjelmassa.

|Sijainti, josta lomaketta käytetään  |Näytetty lomake  |
|---------|---------|
|Tiettyyn aktiviteettiin liitetty ruudukko  | Pikaluonti      |
|Tiettyyn aktiviteettiin liitetty aliruudukko   |  Pikaluonti     |
|Aktiviteettien (activitypointer) ruudukko     | Ensisijainen     |
|Aktiviteettien (activitypointer) liitetty ruudukko   | Ensisijainen    |
|Aktiviteettien (activitypointer) aliruudukko  | Ensisijainen    |
|Yleisen komentopalkin +-painike    | Ensisijainen    |
|Tiettyyn aktiviteettiin liitetty ruudukko   | Ensisijainen    |

 #### <a name="classic-web-client-social-pane-behavior"></a>Perinteisen verkkoasiakasohjelman yhteisöruudun toiminta
 
Yhteisöruutu on erikoistapaus, sillä se ei käytä **Salli pikaluonti** -ominaisuutta vaan eri lomakkeita eri aktiviteettientiteeteissä osoitetulla tavalla.


|Aktiviteetti  |Näytetty lomake  |
|---------|---------|
|Tehtävä     | Pikaluonti    |
|Phone Call   | Pikaluonti     |
|Sähköposti   | Ensisijainen     |
|Tapaaminen  | Ensisijainen     |
|Mukautettu aktiviteetti     | Ensisijainen      |

### <a name="solution-import-allow-quick-create-value-behavior"></a>Ratkaisun tuoman Salli pikaluonti -arvon käyttö

Jos tuot arvon versiosta 8.2, seuraavat entiteetit palautetaan lomakkeen oletusnäyttöarvoon riippumatta siitä, mikä on **Salli pikaluonti** -ominaisuuden arvo ratkaisussa, ja päälomake näytetään: tehtävä, puhelu, sähköposti ja tapaaminen. Tässä tilanteessa näiden aktiviteettientiteettien **Salli pikaluonti** -asetuksen arvoksi on palautettava tuonnin jälkeen *käytössä*.
 
Jos version 9.0 ratkaisussa on mukautettu entiteettejä, joissa **Salli pikaluonti** on käytössä, arvo ei muutu tuonnin jälkeen.  Jos tehtävä-, puhelu-, sähköposti- ja tapaamisentiteetin **Salli pikaluonti** -asetukseksi on määritetty *poistettu käytöstä*, tämä arvo korvautuu käytössä-arvolla. Tässä tilanteessa näiden aktiviteettientiteettien **Salli pikaluonti** -asetuksen arvoksi on palautettava tuonnin jälkeen poistettu käytöstä. 
  
### <a name="see-also"></a>Katso myös  
[Lomake-editorin käyttöliittymän yleiskatsaus](form-editor-user-interface-legacy.md)

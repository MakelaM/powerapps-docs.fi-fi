---
title: Mallipohjaisen sovelluksen lomakkeen siirtymistoiminnon muuttaminen PowerAppsissa | MicrosoftDocs
description: 'Tietoja siitä, miten voit muuttaa siirtymistä lomakkeessa'
ms.custom: ''
ms.date: 06/06/2018
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
ms.assetid: 4c379202-9f0e-4003-a49c-efff53e7f79f
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="change-navigation-within-a-model-driven-app-form"></a>Mallipohjaisen sovelluksen lomakkeen siirtymistoiminnon muuttaminen

 Koska lomakkeessa voi siirtyä, sovelluksen käyttäjät voivat tarkastella liittyvien tietojen luetteloita. Kussakin entiteettisuhteessa on ominaisuuksia, joilla hallitaan sen näyttämistä. Lisätietoja: [Ensisijaisen entiteetin siirtymisruudun kohde](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)  
  
 Näytettäviksi määritetyt entiteettisuhteet voidaan ohittaa lomake-editorissa. Voit lisätä lomakkeen siirtymisosaan linkkejä, joilla näytetään verkkoresursseja tai muita sivustoja.  
  
 Vaiheittaiset ohjeet ovat kohdassa [Common Data Service sovelluksille -ratkaisun entiteettisuhteiden luominen ja muokkaaminen](../common-data-service/create-edit-entity-relationships.md)  
  
 Jos haluat ottaa siirtymisen muokkaamisen käyttöön, sinun on ensin valittava **Siirtyminen** lomakkeen suunnitteluohjelman **Koti**-välilehden **Valitse**-ryhmässä.  
 
> [!div class="mx-imgBorder"] 
> ![Siirtymiskomento](media/navigation-command.png)
 
 Voit käyttää oikeanpuoleisen ruudun **suhteiden hallinnassa** suodatukseen 1:N (yksi moneen)- tai N:N (monta moneen) -suhteita tai näyttää kaikki käytettävissä olevat suhteet. **Näytä vain käyttämättömät suhteet** -valintaruutu on poistettu käytöstä ja valittu. Niinpä voit lisätä kunkin suhteen vain kerran.  
 
 > [!div class="mx-imgBorder"] 
 > ![Suhteiden hallinta](media/relationship-explorer.png)

 Jos haluat lisätä suhteen **suhteiden hallinnassa**, kaksoisnapsauta suhdetta, jolloin se lisätään siirtymisalueella valittuna olevan suhteen alapuolelle. Kaksoisnapsauta suhdetta siirtymisalueella. Voit nyt muuttaa otsikon **Näytä**-välilehdessä. **Nimi**-välilehdessä on tietoja suhteesta. Voit avata entiteetin määritelmän **Muokkaa**-painikkeella.  
  
 Siirtymisalueella on viisi ryhmää. Voit muuttaa niiden sijaintia vetämällä ja vaihtaa niiden otsikon kaksoisnapsauttamalla. Et voi kuitenkaan poistaa niitä. Nämä ryhmät näkyvät vain, kun niissä on sisältöä. Jos et halua ryhmän näkyvän, älä lisää siihen mitään.  
  
 Voit lisätä linkin verkkoresurssiin tai ulkoiseen URL-osoitteeseen **Lisää**-välilehden **Ohjausobjekti**-ryhmän **Siirtymislinkki**-painikkeella.  
 
 ![Siirtymislinkki](media/navigation-link.png)
 
<a name="BKMK_NavigationLinkProperties"></a>   
### <a name="navigation-link-properties"></a>Siirtymislinkin ominaisuudet  
 Siirtymislinkeillä on seuraavat ominaisuudet:  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Nimi|**Pakollinen**: Otsikkona näytettävä teksti.|  
|Kuvake|Käytä 32 x 32 kuvapisteen verkkoresurssia. PNG-kuvan ja läpinäkyvän taustan käyttöä suositellaan.|  
|WWW-resurssi|Määritä lomakkeen pääruudussa näytettävä verkkoresurssi.|  
|Ulkoinen URL|Määritä lomakkeen pääruudussa näytettävän sivun URL-osoite.|  

<a name="BKMK_PrivacyNotices"></a>   

## <a name="privacy-notices"></a>Tietosuojatiedot  
 [!INCLUDE[cc_privacy_crm_website_preview_control](../../includes/cc-privacy-crm-website-preview-control.md)]    
  
 [!INCLUDE[cc_privacy_multimedia_control](../../includes/cc-privacy-multimedia-control.md)]  

## <a name="next-steps"></a>Seuraavat vaiheet

[Lomake-editorin käyttöliittymän yleiskatsaus](form-editor-user-interface-legacy.md)

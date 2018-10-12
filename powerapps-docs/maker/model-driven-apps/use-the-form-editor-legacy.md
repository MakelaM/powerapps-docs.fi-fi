---
title: Siirtymisen muuttaminen malliin perustuvan sovelluksen lomakkeessa PowerAppsissa | MicrosoftDocs
description: Opi muuttamaan siirtymistä lomakkeessa
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
ms.openlocfilehash: 5a8156875f669854a4ba4649e50a23e340f3ceff
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39673872"
---
# <a name="change-navigation-within-a-model-driven-app-form"></a>Siirtymisen muuttaminen malliin perustuvan sovelluksen lomakkeessa

 Siirtyminen lomakkeessa mahdollistaa sovelluksen käyttäjille lomakkeeseen liittyvien tietueiden luettelojen tarkastelemisen. Jokaisessa entiteettisuhteessa on ominaisuuksia sen hallintaan, näytetäänkö suhde. Lisätietoja: [Ensisijaisen entiteetin siirtymisruutukohde](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)  
  
 Näytettäviksi määritetyt entiteettisuhteet voidaan ohittaa lomake-editorissa. Voit myös sisällyttää siirtymislinkkejä, jotka näyttävät verkkoresursseja tai muita verkkosivustoja lomakkeen siirtymistoimintojen kautta.  
  
 Saat vaiheittaiset ohjeet artikkelista [Common Data Service for Appsin entiteettisuhteiden luominen ja muokkaaminen](../common-data-service/create-edit-entity-relationships.md)  
  
 Siirtymisen muokkaamisen ottamiseksi käyttöön sinun täytyy ensin valita **Siirtyminen**-vaihtoehto lomakkeiden suunnitteluohjelman **Aloitus**-välilehden **Valitse**-ryhmästä.  
 
 ![Siirtymiskomento](media/navigation-command.png)
 
 Oikeanpuoleisen ruudun **Suhteidenhallinta**-kohdassa voit suodattaa näkyviin 1:N (yksi-moneen)- tai N:N (monta moneen) -suhteet tai näyttää kaikki käytettävissä olevat suhteet. **Näytä vain käyttämättömät suhteet -valintaruutu** on poistettu käytöstä ja valittuna. Voit siis lisätä kunkin suhteen vain kerran.  
  
 ![Suhteidenhallinta](media/relationship-explorer.png)

 Voit lisätä suhteen **Suhteidenhallinta**-kohdasta kaksoisnapsauttamalla suhdetta, jolloin se lisätään valittuna olevan suhteen alapuolelle siirtymisalueella. Kaksoisnapsauta suhdetta siirtymisalueella. Voit muuttaa suhteen nimeä **Näytä**-välilehdellä. **Nimi**-välilehdellä näet suhdetta koskevia tietoja. Voit avata entiteetin määrityksen käyttämällä **Muokkaa**-painiketta.  
  
 Siirtymisalueella on viisi ryhmää. Voit siirtää ryhmiä vetämällä niitä tai muuttaa niiden otsikkoa kaksoisnapsauttamalla sitä, mutta et voi poistaa niitä. Nämä ryhmät näkyvät vain, jos ne sisältävät jotain. Jos siis et halua ryhmän näkyvän, älä lisää siihen mitään.  
  
 Voit lisätä linkin verkkoresurssiin tai ulkoiseen URL-osoitteeseen käyttämällä **Siirtymislinkki**-painiketta **Ohjausobjekti**-ryhmässä **Lisää**-välilehdellä.  
 
 ![Siirtymislinkki](media/navigation-link.png)
 
<a name="BKMK_NavigationLinkProperties"></a>   
### <a name="navigation-link-properties"></a>Siirtymislinkin ominaisuudet  
 Siirtymislinkeillä on seuraavat ominaisuudet:  
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|Nimi|**Pakollinen**: otsikkona näytettävä teksti.|  
|Kuvake|Käytä 32x32 kuvapisteen verkkoresurssia. On suositeltavaa käyttää PNG-kuvaa, jolla on läpinäkyvä tausta.|  
|Verkkoresurssi|Määritä lomakkeen pääruudussa näytettävä verkkoresurssi.|  
|Ulkoinen URL|Määritä lomakkeen pääruudussa näytettävän sivun URL-osoite.|  

<a name="BKMK_PrivacyNotices"></a>   

## <a name="privacy-notices"></a>Tietosuojailmoitukset  
 [!INCLUDE[cc_privacy_crm_website_preview_control](../../includes/cc-privacy-crm-website-preview-control.md)]    
  
 [!INCLUDE[cc_privacy_multimedia_control](../../includes/cc-privacy-multimedia-control.md)]  

## <a name="next-steps"></a>Seuraavat vaiheet

[Lomake-editorin käyttöliittymän yleiskatsaus](form-editor-user-interface-legacy.md)
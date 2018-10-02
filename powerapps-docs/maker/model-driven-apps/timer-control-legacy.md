---
title: Mallipohjaisen sovelluksen ajastimen ohjausobjekti PowerAppsissa | MicrosoftDocs
description: 'Tietoja siitä, miten käytät ajastinohjausobjektia'
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
ms.assetid: b2b64771-083b-42f9-a3d5-2218f9d8a713
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-timer-control-overview"></a>Mallipohjaisen sovelluksen ajastimen ohjausobjektin yleiskatsaus

 Käytä ajastimen ohjausobjektia lomakkeissa, joissa tietueiden on vastattava aikaperusteista välitavoitetta. Ajastimen ohjausobjekti osoittaa käyttäjille, kuinka paljon aikaa aktiivisen tietueen ratkaisutoiminnon suorittamiseen on tai kuinka kauan on kulunut siitä, kun toiminnon suorittamiseen varattu aika on ohitettu. Ajastimen ohjausobjektit on määritettävä ainakin näyttämään toiminnon suorittamisen onnistuminen tai epäonnistuminen. Lisäksi ne voidaan määrittää näyttämään varoituksia, kun ehdot ovat lähestymässä epäonnistumista.  
  
 Ajastimen ohjausobjekti voidaan lisätä minkä tahansa entiteetin lomakkeeseen, mutta niitä käytetään useimmin palvelupyyntöentiteetissä etenkin silloin, kun se on linkitetty palvelutasosopimuksia seuraaviin kenttiin. Voit lisätä useita ajastimen ohjausobjekteja lomakkeen runkoon. Et voi lisätä niitä ylä-tai alatunnisteeseen.  
  
 Ajastimen ohjausobjektin **Tietolähde**-ominaisuudet käyttävät entiteetin kenttiä.  
  
-   **Virheajan kenttä** määrittää ajan aika- ja päivämääräkentän.  
  
-   Kolme ehtokenttää käyttää jotakin entiteetin **Asetusjoukko**-, **Kaksi asetusta**-, **Tila**- tai **Tilan syy** -kentistä.  

Voit luoda ajastimen ohjausobjekti valitsemalla lomakkeen suunnitteluohjelmassa **Lisää**-välilehden ja valitsemalla sitten työkaluriviltä **Ajastin**. 

  > [!div class="mx-imgBorder"] 
  > ![Ajastinohjausobjektin lisääminen](media/insert-timer-control.png)

Anna Ajastimen ohjausobjektin ominaisuudet -sivulle haluamasi ominaisuudet tai valitse ne. Valitse sitten **OK**. 

  
<a name="BKMK_TimerControlProperties"></a>   

## <a name="timer-control-properties"></a>Ajastimen ohjausobjektin ominaisuudet  
 Seuraavassa taulukossa käsitellään ajastimen ohjausobjektin ominaisuuksia.  
  
|Ryhmä|Nimi|Kuvaus|  
|-----------|----------|-----------------|  
|Nimi|Nimi|**Pakollinen**. Ohjausobjektin yksilöivä nimi.|  
||Nimi|**Pakollinen**. Ajastimen ohjausobjektissa näytettävä otsikko.|  
|Tietolähde|Virheajan kenttä|**Pakollinen**. Valitse jokin entiteetin päivämäärä- tai aikakentistä ilmoittamaan, milloin välitavoite on saavutettava.|  
||Onnistumisen ehto|**Pakollinen**. Valitse entiteetin kenttä arvioimaan välitavoitteen onnistumista ja valitse sitten, mikä asetus osoittaa onnistumisen.|  
||Varoituksen ehto|Valitse entiteetin kenttä arvioimaan, onko välitavoitteen onnistuminen vaarassa, jolloin on näytettävä varoitus. Valitse sitten, mikä asetus osoittaa varoituksen näyttämisen.|  
||Peruutuksen ehto|Valitse entiteetin kenttä arvioimaan, milloin välitavoitteen saavuttaminen on peruutettava. Valitse sitten asetus osoittamaan välitavoitteen peruuttaminen.|  

## <a name="next-steps"></a>Seuraavat vaiheet

[Lomake-editorin käyttöliittymän yleiskatsaus](form-editor-user-interface-legacy.md)

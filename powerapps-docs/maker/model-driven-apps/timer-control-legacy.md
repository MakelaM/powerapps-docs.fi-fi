---
title: Mallipohjaisen sovelluksen ajastimen ohjausobjekti PowerAppsissa | MicrosoftDocs
description: Ajastimen ohjausobjektin käyttöön tutustuminen
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
ms.openlocfilehash: 7df13482e7773abc3e6762f80bd9f6b99c7ba9e6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674976"
---
# <a name="model-driven-app-timer-control-overview"></a>Mallipohjaisen sovelluksen ajastimen ohjausobjektin yleiskatsaus

 Käytä ajastimen ohjausobjektia lomakkeissa, joissa tietueiden on vastattava aikaperusteista välitavoitetta. Ajastimen ohjausobjekti osoittaa käyttäjille, kuinka paljon aikaa aktiivisen tietueen ratkaisutoiminnon suorittamiseen on tai kuinka kauan on kulunut siitä, kun toiminnon suorittamiseen varattu aika on ohitettu. Ajastimen ohjausobjektit on määritettävä näyttämään ainakin toiminnon suorittamisen onnistuminen tai epäonnistuminen. Lisäksi ne voidaan määrittää näyttämään varoituksia, kun ehdot ovat lähestymässä epäonnistumista.  
  
 Ajastimen ohjausobjekti voidaan lisätä minkä tahansa entiteetin lomakkeeseen, mutta niitä käytetään useimmin tapausentiteetissä etenkin silloin, kun se on linkitetty palvelutasosopimuksia seuraaviin kenttiin. Voit lisätä useita ajastimen ohjausobjekteja lomakkeen runkoon. Et voi lisätä niitä ylä- tai alatunnisteeseen.  
  
 Ajastimen ohjausobjektin **Tietolähde**-ominaisuudet käyttävät entiteetin kenttiä.  
  
-   **Virheajan kenttä** määrittää ajan aika- ja päivämääräkentän.  
  
-   Kolme ehtokenttää käyttää jotakin entiteetin **Asetusjoukko**-, **Kaksi asetusta**-, **Tila**- tai **Tilan syy** -kentistä.  

Voit luoda ajastimen ohjausobjektin valitsemalla lomakkeiden suunnitteluohjelman **Lisää**-välilehden ja sitten työkaluriviltä **Ajastin**. 

  ![Ajastimen ohjausobjektin lisääminen](media/insert-timer-control.png)

Kirjoita tai valitse haluamasi ominaisuudet Ajastimen ohjausobjektin ominaisuudet -sivulla ja valitse sitten **OK**. 

  
<a name="BKMK_TimerControlProperties"></a>   

## <a name="timer-control-properties"></a>Ajastimen ohjausobjektin ominaisuudet  
 Seuraavassa taulukossa kuvataan ajastimen ohjausobjektin ominaisuudet.  
  
|Ryhmä|Nimi|Kuvaus|  
|-----------|----------|-----------------|  
|Nimi|Nimi|**Pakollinen**. Ohjausobjektin yksilöivä nimi.|  
||Selite|**Pakollinen**. Näytettävä ajastimen ohjausobjektin nimi.|  
|Tietolähde|Virheajan kenttä|**Pakollinen**. Valitse jokin entiteetin päivämäärä- tai aikakentistä ilmoittamaan, milloin välitavoite on saavutettava.|  
||Onnistumisen ehto|**Pakollinen**. Valitse entiteetin kenttä arvioimaan välitavoitteen onnistumista ja valitse sitten, mikä asetus osoittaa onnistumisen.|  
||Varoituksen ehto|Valitse entiteetin kenttä arvioimaan, onko välitavoitteen onnistuminen vaarassa, jolloin on näytettävä varoitus. Valitse sitten, mikä asetus osoittaa varoituksen näyttämisen.|  
||Peruutuksen ehto|Valitse entiteetin kenttä arvioimaan, milloin välitavoitteen saavuttaminen on peruutettava. Valitse sitten asetus osoittamaan välitavoitteen peruuttaminen.|  

## <a name="next-steps"></a>Seuraavat vaiheet

[Lomake-editorin käyttöliittymän yleiskatsaus](form-editor-user-interface-legacy.md)
---
title: Mallipohjaisen sovelluksen lomakkeiden suorituskyvyn optimointi PowerAppsissa | MicrosoftDocs
description: Opi välttämään lomakemalleja, jotka hidastavat lomakkeen latautumista.
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 59cfa5e6-638a-437f-a462-fddfd26fb07d
caps.latest.revision: 8
ms.author: matp
manager: kvivek
ms.openlocfilehash: c9dd764fe565b59e68411dabf453207c4e01a320
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674491"
---
# <a name="optimize-model-driven-app-form-performance"></a>Mallipohjaisen sovelluksen lomakkeiden suorituskyvyn optimointi

Hitaasti latautuvat lomakkeet heikentävät tuottavuutta ja sovelluksen käytön omaksumista. Noudata näitä suosituksia, niin saat lomakkeesi latautumaan mahdollisimman nopeasti. Monet suosituksista koskevat sitä, miten kehittäjä voi ottaa lomakkeen komentosarjoja käyttöön organisaatiollesi. Kerro näistä suosituksista kehittäjille, jotka vastaavat lomakkeiden komentosarjojen luomisesta.  
  
<a name="BKMK_FormDesign"></a>   
## <a name="form-design"></a>Lomakkeen rakenne  
 Ota huomioon ne tavat, joilla käyttäjä käyttää lomaketta, sekä lomakkeessa näytettävien tietojen määrä.  
  
 **Pidä kenttien määrä minimissään**  
 Mitä enemmän kenttiä lomakkeessa on, sitä enemmän tietoa on siirrettävä Internetissä tai intranetissä jokaisen tietueen näyttämiseksi.  
  
<a name="BKMK_FormScripts"></a>   
## <a name="form-scripts"></a>Lomakkeen komentosarjat  
 Jos käytät lomakkeiden komentosarjoilla toteutettuja mukautuksia, varmista, että kehittäjä on sisäistänyt nämä strategiat suorituskyvyn parantamiseksi.  
  
 **Vältä tarpeettomia JavaScript-verkkoresurssien kirjastoja**  
 Mitä enemmän komentosarjoja lomakkeeseen lisätään, sitä kauemmin niiden lataaminen kestää. Yleensä komentosarjat tallennetaan selaimen välimuistiin, kun ne ladataan ensimmäisen kerran. Suurimman vaikutuksen käyttäjätyytyväisyyteen tekee kuitenkin lomakkeen ensimmäinen katselukerta ja sen tehokkuus.  
  
 **Vältä lataamasta kaikkia komentosarjoja Onload-tapahtumassa**  
 Jos koodisi tukee kentille vain `OnChange`-tapahtumia tai `OnSave`-tapahtumaa, aseta tapahtumakäsittelijän sisältävä komentosarjakirjasto vain näille tapahtumille `OnLoad`-tapahtuman sijaan. Tällä tavoin näiden kirjastojen lataamista lykätään ja lomakkeen latautumisen suorituskykyä parannetaan.  
  
 **Käytä kutistettuja välilehtiä verkkoresurssien lataamisen lykkäämiseen**  
 Kun verkkoresurssit tai iFrame-kehykset sisältyvät kutistetuilla välilehdillä oleviin osioihin, niitä ei ladata, jos välilehti on kutistettu. Ne ladataan, kun välilehti laajennetaan. Kun välilehden tila muuttuu, tapahtuu `TabStateChange`-tapahtuma. Jos koodin on tuettava kutistetuilla välilehdillä olevia verkkoresursseja tai iFrame-kehyksiä, voidaan käyttää tapahtumakäsittelijöitä **TabStateChange**-tapahtumalle ja vähentää koodia, jonka muuten olisi tapahduttava `OnLoad`-tapahtumassa.  
  
 **Määritä näkyvyyden oletusasetukset**  
 Vältä lomake-elementtejä piilottavia komentosarjoja `OnLoad`-tapahtumassa. Määritä sen sijaan piilotettavien elementtien oletusarvoiseksi näkyvyydeksi näkymättömissä oleminen, kun lomake latautuu. Voit sen jälkeen näyttää näytettävät elementit käyttämällä `OnLoad`-tapahtuman komentosarjoja.  
  
<a name="BKMK_CommandBar"></a>   
## <a name="command-bar-or-ribbon"></a>Komentopalkki tai valintanauha  
 Pidä nämä suositukset mielessä, kun muokkaat komentopalkkia tai valintanauhaa.  
  
 **Pidä ohjausobjektien määrä minimissään**  
 Mieti tarkkaan, mitä ohjausobjekteja lomakkeen komentopalkissa tai valintanauhassa välttämättä tarvitaan. Piilota tarpeettomat. Jokainen näytettävä ohjausobjekti kasvattaa selaimeen ladattavien resurssien määrää.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Luo ja suunnittele lomakkeita](create-design-forms.md)    
    
 

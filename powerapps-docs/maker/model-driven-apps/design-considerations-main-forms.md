---
title: Mallipohjaisen sovelluksen päälomakkeiden suunnittelunäkökohtia PowerAppsissa | MicrosoftDocs
description: Tietoja päälomakkeiden suunnittelusta
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
ms.assetid: a83872f4-9e36-413b-8561-41a1e5ffe5dd
caps.latest.revision: 17
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="design-considerations-for-model-driven-app-main-forms"></a>Mallipohjaisen sovelluksen päälomakkeiden suunnittelunäkökohtia

Lomakkeet ovat ensisijainen käyttöliittymä, jossa henkilöt tarkastelevat ja käsittelevät tietojaan. Päälomakkeet tarjoavat laajimmat vaihtoehdot ja ovat käytettävissä mallipohjaisissa sovelluksissa. Dynamics 365 for phones on kuitenkin poikkeus.  
  
 Yksi tärkeimmistä suunnittelun tavoitteista päälomakkeille on, että ne suunnitellaan kerran ja otetaan käyttöön kaikkialla. Samaa mallipohjaiselle sovellukselle tai Dynamics 365 customer engagement -WWW-sovelluksen suunniteltua päälomaketta käytetään myös Dynamics 365 for Outlook- ja Dynamics 365 for tablets -sovelluksissa. Tämän lähestymistavan etu on, että sinun ei tarvitse integroida muutoksia useisiin lomakkeisiin. On kuitenkin useita tärkeitä seikkoja, joita on syytä harkita näiden lomakkeiden suunnittelussa.  
  
<a name="BKMK_CustomFormsForGroups"></a>   

## <a name="custom-forms-for-different-groups"></a>Mukautetut lomakkeet eri käyttäjäryhmille  
 Koska voit luoda useita päälomakkeita ja antaa eri käyttöoikeusrooleja kullekin lomakkeelle, voit tarjota organisaation eri ryhmille lomakkeen, joka on optimoitu kullekin ryhmälle sovelluksen käyttötarkoituksen mukaan. Voit jopa tarjota erilaisia vaihtoehtoja kullekin ryhmälle siten, että niillä on valittavana erilaisia lomakkeita. Lisätietoja: [Lomakkeiden käytön hallinta](control-access-forms.md)  
  
 Voit olettaa, että päälliköt ja päätöksentekijät haluavat lomakkeita, jotka on optimoitu viittaamaan nopeasti päätöksenteon avaintietoihin. He haluavat nähdä kaavioita mieluummin kuin luetteloita, eivätkä he mahdollisesti suorita paljon tietojen syöttämistä.  
  
 Henkilöt, jotka ovat suoraan asiakkaiden kanssa tekemisissä, tarvitsevat ehkä lomakkeita, jotka on suunniteltu erityisesti heidän useimmin suorittamia tehtäviä varten. He haluavat ehkä lomakkeita, joiden avulla tietojen syöttäminen on kaikkein tehokkainta.  
  
 Sinun täytyy tietää, mitä ihmiset organisaatiossa haluavat ja tarvitsevat. Tämä on usein toistuva prosessi, jossa kerätään palautetta, kokeillaan eri asioita ja rakennetaan lomakkeita, joita käyttäjät voivat käyttää. Muista, että sinulla on erilaisia työkaluja käytettävissäsi, eikä kaikkea tarvitse tehdä lomakkeessa. Käytä liiketoimintasääntöjä, työnkulkuprosesseja, dialogeja ja liiketoimintaprosessivuota yhdessä lomakkeiden kanssa tarjotaksesi ratkaisun, joka toimii organisaatiossasi.  
  
 Sinun on tasapainoteltava tämä ajan kanssa, jonka haluat käyttää lomakkeiden hallintaan. Lomakkeiden luominen ja muokkaaminen on suhteellisen helppoa, mutta samalla, kun luot lisää lomakkeita, sinun on hallittava useampia lomakkeita.  
  
<a name="BKMK_PresentationDifferences"></a>   
## <a name="presentation-differences"></a>Esityksen erot  
 Vaikka sinun ei tarvitse hallita useita lomakkeita kutakin esitystä varten, sinun täytyy miettiä, miten esityksen erot voidaan ottaa huomioon päälomakkeessa. Aiheessa [Päälomakkeen esitystavat](main-form-presentations.md) kerrotaan eri tavoista, joilla päälomake voidaan esittää. Ensisijaisia asioita, jotka otetaan huomioon, ovat:  
  
- Dynamics 365 for tablets ei tue kuvan, HTML-koodin tai Silverlight-WWW-resurssien lisäämistä lomakkeisiin.  
  
-   Dynamics 365 for tablets -lomakkeiden asettelu on luotu automaattisesti päälomakkeen perusteella. Dynamics 365 for tablets -lomakkeille ei ole erityistä lomake-editoria. Sinun täytyy varmistaa, että lomake-esitys soveltuu hyvin molemmille asiakkaille.  
  
-   Jos sinulla on tukemattomia komentosarjoja, jotka käsittelevät verkkosovellukseen sisältyviä DOM-elementtejä, nämä komentosarjat eivät toimi Dynamics 365 for tablets -lomakkeissa, koska samat DOM-elementit eivät ole käytettävissä.  
  
- Dynamics 365 for Outlookin lukuruutu ei salli komentosarjoja. Lomake-elementtien näkyvyyden oletusasetukset määräytyvät oletusarvojen mukaan, eikä niitä voi muuttaa suorituksen komentosarjojen avulla.  
  
<a name="BKMK_FormPerformance"></a>   
## <a name="form-performance"></a>Lomakkeen suorituskyky  
 Lomakkeet, jotka latautuvat hitaasti tai eivät vastaa nopeasti vaikuttavat varmasti tuottavuuteen ja sovelluksen käyttöönottoon. [Lomakkeen suorituskyvyn optimointi](optimize-form-performance.md) sisältää joukon suosituksia, jotka on otettava huomioon lomakkeiden suunnittelussa, jotta mukautukset eivät vaikuta haitallisesti lomakkeen suorituskykyyn.  
  
### <a name="next-steps"></a>Seuraavat vaiheet 
 [Luo ja suunnittele lomakkeita](create-design-forms.md)    
 [Luo ja muokkaa pikaluontilomakkeita nopeasti](create-edit-quick-create-forms.md)   

 

---
title: Malliin perustuvien sovellusten päälomakkeiden suunnittelussa huomioitavat seikat PowerAppsissa | MicrosoftDocs
description: Lue ohjeet päälomakkeiden suunnitteluun
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
ms.openlocfilehash: 68915af214b86511f7fba4bbb05ee59f598340b0
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681681"
---
# <a name="design-considerations-for-model-driven-app-main-forms"></a>Malliin perustuvien sovellusten päälomakkeiden suunnittelussa huomioitavat seikat

Päälomakkeet muodostavat ensisijaisen käyttöliittymän, jossa ihmiset käyttävät tietojaan. Päälomakkeet tarjoavat laajimmat mahdolliset toiminnot. Ne ovat käytettävissä malliin perustuvissa sovelluksissa Dynamics 365 for Phones -sovellusta lukuun ottamatta.  
  
 Päälomakkeiden suunnittelun pääperiaate on se, että ne suunnitellaan kerran, minkä jälkeen niitä voi ottaa käyttöön kaikkialla. Samaa päälomaketta, jonka suunnittelet malliin perustuvalle sovellukselle tai Dynamics 365 Customer Engagement -verkkosovellukselle, käytetään myös Dynamics 365 for Outlookissa ja Dynamics 365 for Tablets -sovelluksessa. Tämän ansiosta sinun ei tarvitse integroida muutoksia useisiin lomakkeisiin. Näiden lomakkeiden suunnittelussa täytyy kuitenkin huomioida useita tärkeitä seikkoja.  
  
<a name="BKMK_CustomFormsForGroups"></a>   

## <a name="custom-forms-for-different-groups"></a>Eri ryhmien mukautetut lomakkeet  
 Koska voit luoda useita päälomakkeita ja määrittää kullekin lomakkeelle erilaisia käyttöoikeusrooleja, voit näyttää organisaatiosi eri ryhmille lomakkeen, joka on optimoitu juuri sille tavalle, jolla kukin ryhmä käyttää sovellusta. Voit jopa tarjota kullekin ryhmälle eri vaihtoehtoja, jotta heillä on valittavissaan erilaisia lomakkeita. Lisätiedot: [Lomakkeiden käyttöoikeuksien hallinta](control-access-forms.md)  
  
 Voit olettaa, että esimiehet ja päätöksentekijät haluavat lomakkeita, jotka on optimoitu tarjoamaan tärkeät tiedot nopeasti. He haluavat luultavasti nähdä mieluummin kaavioita kuin luetteloita. He eivät myöskään luultavasti lisää paljoakaan tietoja.  
  
 Käyttäjät, jotka ovat suoraan tekemisissä asiakkaiden kanssa, saattavat tarvita lomakkeita, jotka on räätälöity heidän eniten tekemilleen tehtäville. He haluavat luultavasti lomakkeita, joissa voi antaa tietoja tehokkaasti.  
  
 Sinun täytyy kartoittaa organisaatiosi käyttäjien tarpeet ja toiveet. Tämä on usein luonteeltaan toisteinen prosessi, jossa keräät palautetta, kokeilet eri asioita ja luot lomakkeita käyttäjien käyttöön. Muista, että käytettävissäsi on runsaasti työkaluja ja että kaikkea ei tarvitse tehdä lomakkeessa. Kun käytät yhdessä lomakkeiden kanssa liiketoimintasääntöjä, työnkulkuprosesseja, valintaikkunoita ja liiketoimintaprosesseja, voit tarjota organisaatiollesi toimivan ratkaisun.  
  
 Sinun täytyy tasapainottaa tämä sen kanssa, paljonko aikaa haluat käyttää lomakkeiden hallintaan. Lomakkeiden luominen ja muokkaaminen on suhteellisen helppoa, mutta mitä enemmän lomakkeita luot, sitä enemmän niitä täytyy myös hallita.  
  
<a name="BKMK_PresentationDifferences"></a>   
## <a name="presentation-differences"></a>Erilaiset esitystavat  
 Vaikka sinun ei tarvitsekaan hallita useita lomakkeita kullekin esitykselle, sinun täytyy huomioida erot siinä, miten esitystapa voidaan huomioida päälomakkeessa. [Päälomakkeen esitysten](main-form-presentations.md) ohjeartikkelista saat kuvauksen eri tavoista, joilla päälomake voidaan esittää. Tärkeimpiä huomioitavia seikkoja ovat seuraavat:  
  
- Dynamics 365 for Tablets ei tue lomakkeisiin lisättyjä kuvia, HTML-resursseja tai Silverlight-verkkoresursseja.  
  
-   Dynamics 365 for Tablets -lomakkeet luodaan automaattisesti päälomakkeen pohjalta. Dynamics 365 for Tablets -lomakkeille ei ole mitään erikoislomake-editoria. Sinun täytyy varmistaa, että lomakkeen esittäminen toimii hyvin kaikissa asiakasohjelmissa.  
  
-   Jos sinulla on tukemattomia komentosarjoja, jotka toimivat yhdessä verkkosovelluksen DOM-elementtien kanssa, nämä komentosarjat eivät toimi Dynamics 365 for Tablets -lomakkeissa, koska samoja DOM-elementtejä ei ole saatavilla.  
  
- Dynamics 365 for Outlookin lukuruutu ei salli komentosarjoja. Lomake-elementtien näkyvyys riippuu oletusasetuksista. Muuttaminen ei ole mahdollista suorituksen yhteydessä komentosarjoilla.  
  
<a name="BKMK_FormPerformance"></a>   
## <a name="form-performance"></a>Lomakkeiden suorituskyky  
 Hitaasti latautuvat tai reagoivat lomakkeet vaikuttavat varmasti tuottavuuteen ja siihen, kuinka halukkaasti käyttäjät niitä käyttävät. [Lomakkeiden suorituskyvyn optimoinnin](optimize-form-performance.md) artikkelista saat useita suosituksia lomakkeiden suunnitteluun siten, että mukautukset eivät heikennä lomakkeiden suorituskykyä.  
  
### <a name="next-steps"></a>Seuraavat vaiheet 
 [Lomakkeiden suunnitteleminen ja luominen](create-design-forms.md)    
 [Pikaluontilomakkeiden luominen ja muokkaaminen](create-edit-quick-create-forms.md)   

 

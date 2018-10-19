---
title: Mallipohjaisen sovelluksen mukauttamiseen tarvittavat oikeudet | MicrosoftDocs
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: 43cf7f3a-7e26-4990-8b5a-c817ac6d51bb
caps.latest.revision: 13
ms.author: matp
manager: kvivek
author: Mattp123
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="privileges-required-for-model-driven-app-customization"></a>Mallipohjaisen sovelluksen mukauttamiseen tarvittavat oikeudet

Sovelluksen käyttäjät voivat mukauttaa järjestelmää ja jopa jakaa joitakin mukautuksia muiden kanssa. Kuitenkin vain käyttäjät, joilla on tarvittavat oikeudet, voivat käyttää muutoksia kaikkiin.  
  
> [!NOTE]
>  Tässä jaksossa oletetaan, että tiedät miten käyttöoikeusrooleja käsitellään. Saat lisätietoja käyttöoikeusroolien käsittelemisestä [Käyttäjien luominen ja käyttöoikeusroolien delegointi](https://docs.microsoft.com/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles).  
  
<a name="BKMK_SysAdminAndSysCustomizer"></a>   
## <a name="system-administrator-and-system-customizer-security-roles"></a>Järjestelmänvalvojan ja Järjestelmän mukauttajan käyttöoikeusroolit  
 Jokaisella mukautuksia tekevällä on tiliin liittyvä järjestelmänvalvojan tai järjestelmän mukauttajan käyttöoikeusrooli. Nämä käyttöoikeusroolit antavat sinulle oikeuksia, jotka tarvitset sovelluksen mukauttamiseen.  
  
|Järjestelmänvalvoja|Järjestelmän mukauttaja|  
|--------------------------|-----------------------|  
|On täysi oikeus mukauttaa järjestelmä|On täysi oikeus mukauttaa järjestelmä|  
|Voi nähdä järjestelmän kaikki tiedot|Voi vain tarkastella niiden järjestelmäentiteettien tietueita, joita he luovat|  
  
 Järjestelmänvalvojan ja järjestelmän mukauttajan käyttöoikeusroolien välinen ero on se, että järjestelmänvalvojalla on lukuoikeudet useimpiin järjestelmän tietueisiin ja hän voi nähdä kaiken. Määritä järjestelmän mukauttajan rooli henkilölle, jonka pitää suorittaa mukautustehtäviä, mutta ei pidä nähdä mitään tietoja järjestelmäentiteeteissä. Testaus on kuitenkin tärkeä osa järjestelmän mukauttamista. Jos järjestelmän mukauttajat eivät näe mitään tietoja, niiden täytyy luoda tietueita mukautusten testaamiseksi. Järjestelmän mukauttajilla on oletusarvoisesti täydet käyttöoikeudet mukautettuihin entiteetteihin. Jos haluat samat rajoitukset, jotka ovat järjestelmänentiteeteillä, sinun pitää muuttaa järjestelmän mukauttajan käyttöoikeusroolia niin, että taso on **Käyttäjä** mieluummin kuin **Organisaatio** mukautetuille entiteeteille.  
  
<a name="BKMK_DelegatingCustomizationTasks"></a>   
## <a name="delegate-customization-tasks"></a>Delegoi mukautustehtävät  
 Voit haluta delegoida joitakin tehtäviä luotetuille henkilöille siten, että he voivat käyttää tarvitsemiaan muutoksia. Muista, että kellä tahansa voi olla useita käyttöoikeusrooleja, jotka liittyvät heidän käyttäjätileihinsä ja että oikeudet ja käyttöoikeudet, jotka on myönnetty käyttöoikeusroolien perusteella, perustuvat *vähiten rajoittavan* tason käyttöoikeuksiin.  
  
 Se tarkoittaa sitä, että voit antaa järjestelmän mukauttajan käyttöoikeusroolia käyttäjälle, jolla on jo muu käyttöoikeusrooli, esimerkiksi myyntipäällikkö. Näin he voivat mukauttaa järjestelmää sen lisäksi että heillä on muut oikeudet. Sinun ei tarvitse muokata käyttöoikeusroolia, joka heillä jo on, ja voit poistaa järjestelmän mukauttajan käyttöoikeusroolin henkilön käyttäjätililtä milloin haluat.  
  
<a name="BKMK_UsingTwoUserAccounts"></a>   
## <a name="test-customizations-without-customization-privileges"></a>Ilman mukautusoikeutta mukautusten testaaminen  
 Kannattaa testata tekemiäsi mukautuksia käyttäjätilille, jolla ei ole mukautusoikeuksia. Tällä tavalla voit varmistaa, että ihmiset ilman järjestelmänvalvojan tai järjestelmän mukauttajan käyttöoikeusroolia voivat käyttää mukautuksia. Tehdäksesi tämän tehokkaasti sinun täytyy käyttää kahta käyttäjätiliä: järjestelmänvalvojan käyttöoikeusroolille yksi tili, ja toinen, jolla on käyttöoikeusrooleja, jotka edustavat henkilöitä, jotka käyttävät mukautuksia.  
  
> [!IMPORTANT]
>  Älä yritä poistaa järjestelmänvalvojan käyttöoikeusroolia, jos sinulla on vain yksi käyttäjätili. Järjestelmä antaa varoituksen, jos yrität, mutta jos etenet, voi olla, että et voi saada takaisin. Useimmat suojausroolit ei salli käyttäjien käyttöoikeusroolien muokkaamista.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
[Tietoja mallipohjaisen sovelluksen osista](model-driven-app-components.md)


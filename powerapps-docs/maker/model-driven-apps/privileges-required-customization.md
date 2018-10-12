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
ms.openlocfilehash: dd0c7e05d756145a701bb6bfb137dc07cb8c45fb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675963"
---
# <a name="privileges-required-for-model-driven-app-customization"></a>Mallipohjaisen sovelluksen mukauttamiseen tarvittavat oikeudet

Sovelluksen käyttäjät voivat mukauttaa järjestelmää ja jopa jakaa joitakin mukautuksia muiden kanssa, mutta vain käyttäjät, joilla on tarvittavat oikeudet, voivat ottaa muutokset käyttöön kaikille.  
  
> [!NOTE]
>  Tässä osassa oletetaan, että osaat käsitellä käyttöoikeusrooleja. Katso lisätietoja käyttöoikeusrooleista kohdasta [Käyttäjien luominen ja käyttöoikeusroolien määrittäminen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles).  
  
<a name="BKMK_SysAdminAndSysCustomizer"></a>   
## <a name="system-administrator-and-system-customizer-security-roles"></a>Järjestelmänvalvojan ja järjestelmämukauttajan käyttöoikeusroolit  
 Kaikilla mukauttajilla on järjestelmänvalvojan tai järjestelmämukauttajan käyttöoikeusrooli liitettynä tiliinsä. Nämä käyttöoikeusroolit antavat sinulle oikeuden sovelluksen mukauttamiseen.  
  
|Järjestelmänvalvoja|Järjestelmämukauttaja|  
|--------------------------|-----------------------|  
|Täydet oikeudet järjestelmän mukauttamiseen|Täydet oikeudet järjestelmän mukauttamiseen|  
|Pystyy tarkastelemaan kaikkia järjestelmässä olevia tietoja|Voi tarkastella vain itse luotujen järjestelmäentiteettien tietueita|  
  
 Järjestelmänvalvojan ja järjestelmämukauttajan käyttöoikeusroolien ero on, että järjestelmänvalvojalla on lukuoikeus useimmille tietueille järjestelmässä ja hän voi tarkastella kaikkia tietoja. Määritä järjestelmämukauttajan rooli henkilölle, jonka on suoritettava mukauttamistehtäviä mutta ei pitäisi nähdä mitään tietoja järjestelmän entiteeteissä. Testaus on kuitenkin tärkeä osa järjestelmän mukauttamista. Jos järjestelmämukauttajat eivät näe mitään tietoja, heidän on luotava tietueet mukautustensa testaamiseksi. Oletusarvon mukaan järjestelmämukauttajilla on täydet käyttöoikeudet mukautettuihin entiteetteihin. Jos haluat käyttää samoja rajoituksia kuin järjestelmäentiteettejä varten, sinun tulee säätää järjestelmämukauttajan käyttöoikeusroolia siten, että käyttöoikeustaso on **Käyttäjä** eikä **Organisaatio** mukautetuille entiteeteille.  
  
<a name="BKMK_DelegatingCustomizationTasks"></a>   
## <a name="delegate-customization-tasks"></a>Mukautettujen tehtävien delegointi  
 Haluat ehkä delegoida joitakin tehtäviä luotetuille henkilöille, jotta he voivat ottaa muutoksia käyttöön tarvittaessa. Muista, että kaikilla voi olla useita käyttöoikeusrooleja tiliinsä liitettynä, ja että käyttöoikeusrooleihin perustuvat oikeudet ja käyttöoikeudet perustuvat oikeuksien *vähiten rajoittavaan* tasoon.  
  
 Tämä tarkoittaa sitä, että voit antaa järjestelmämukauttajan käyttöoikeusroolin henkilölle, jolla on jo jokin muu käyttöoikeusrooli, kuten myyntipäällikkö. Näin he voivat mukauttaa järjestelmää muiden oikeuksiensa lisäksi. Sinun ei tarvitse muokata heillä jo olevia käyttöoikeusrooleja, ja voit poistaa järjestelmämukauttajan käyttöoikeusroolin henkilön käyttäjätilistä milloin tahansa.  
  
<a name="BKMK_UsingTwoUserAccounts"></a>   
## <a name="test-customizations-without-customization-privileges"></a>Mukautusten testaaminen ilman mukautusoikeuksia  
 Testaa tekemäsi mukautukset aina käyttäjätilillä, jolla ei ole mukautusoikeuksia. Näin voit varmistaa, että käyttäjät ilman järjestelmänvalvojan tai järjestelmämukauttajan käyttöoikeusroolia pystyvät käyttämään mukautuksiasi. Tarvitset tätä varten kaksi käyttäjätiliä: yhden tilin, jolla on järjestelmänvalvojan käyttöoikeusrooli ja toisen tilin, jonka käyttöoikeusroolit vastaavat mukautusten käyttäjiä.  
  
> [!IMPORTANT]
>  Älä yritä poistaa järjestelmänvalvojan käyttöoikeusroolia, jos sinulla on vain yksi käyttäjätili. Järjestelmä antaa tällöin varoituksen, mutta jos silti jatkat poistamista, et ehkä saa käyttöoikeusroolia takaisin. Useimmat käyttöoikeusroolit eivät salli käyttäjän käyttöoikeusroolien muokkaamista.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Mukauttamisen aloittaminen](getting-started-customization.md)


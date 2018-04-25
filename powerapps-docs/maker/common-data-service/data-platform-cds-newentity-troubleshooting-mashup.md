---
title: Power Queryn vianmääritys | Microsoft Docs
description: Ratkaise ongelmia Power Queryn avulla luodaksesi mukautetun kohteen Common Data Service -sovelluksille
services: ''
suite: powerapps
documentationcenter: na
author: mllopis
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/18/2017
ms.author: millopis
ms.openlocfilehash: dafed76565a4bd3fb3e2822319d344f49376b4fc
ms.sourcegitcommit: aa2d0166dccb38100183c093f293233b46f3669d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2018
---
# <a name="troubleshooting-power-query"></a>Power Queryn vianmääritys
Kun käytät Power Queryä laatiaksesi mukautetun kohteen, joka sisältää tietoja ulkoisista lähteistä, esiin saattaa tulla tämä virhe:

`Your Azure Active Directory administrator has set a policy that prevents you from using this feature. Please contact your administrator, who can grant permissions for this feature on your behalf.`

Virhe tulee näkyviin, jos Power Query ei voi käyttää organisaation tietoja PowerAppsissa tai Common Data Servicessä. Tämä tilanne tulee esiin kahdessa seuraavassa tilanteessa:

* Azure Active Directory (AAD) -vuokraajan järjestelmänvalvoja ei ole sallinut käyttäjien mahdollisuutta antaa suostumusta sovelluksille, jotka käyttävät yrityksen tietoja heidän puolestaan.
* Hallitsemattoman Active Directory -vuokraajan käyttäminen. Hallitsematon vuokraaja on hakemisto, jolla ei ole yleistä järjestelmänvalvojaa ja joka on luotu täydentämään omatoimisen rekisteröitymisen tarjousta. Tämän skenaarion korjaamiseksi käyttäjien täytyy ensin muuntaa vuokraaja hallituksi vuokraajaksi ja seurata sitten jompaakumpaa seuraavassa osassa kuvatusta kahdesta ratkaisusta ongelmaan.

Tämän ongelman ratkaisemiseksi AAD-järjestelmänvalvojan täytyy noudattaa jommankumman tässä artikkelissa myöhemmin esitetyn toimenpiteen vaiheita.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>Salli käyttäjän antaa suostumus sovelluksille, jotka käyttävät yrityksen tietoja
Tämä lähestymistapa on ehkä helpompi kuin seuraava, mutta se sallii laajemmat käyttöoikeudet.

1. Avaa osoitteessa [https://portal.azure.com](https://portal.azure.com) **Azure Active Directory** -lapa, ja valitse sitten **Käyttäjäasetukset**.
1. Valitse vaihtoehto **Kyllä** kohdan **Käyttäjät voivat antaa sovellukselle luvan käyttää yrityksen tietoja puolestaan** vierestä ja valitse sitten **Tallenna**.

## <a name="allow-power-query-to-access-company-data"></a>Salli Power Queryn käyttää yrityksen tietoja
Vaihtoehtoisesti vuokraajan järjestelmänvalvoja voit antaa Power Querylle suostumuksen muokkaamatta vuokraajan laajuisia käyttöoikeuksia.

1. Asenna [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps).
2. Suorita seuraavat PowerShell-komennot:
   * Login-AzureRmAccount (ja kirjaudu sisään vuokraajan järjestelmänvalvojana)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

Tämän lähestymistavan etuna vuokraajan laajuiseen ratkaisuun verrattuna on se, että tämä ratkaisu on hyvin kohdennettu. Se täydentää vain **Power Query** palveluobjektia mutta ei tee muita käyttöoikeusmuutoksia vuokraajaan.


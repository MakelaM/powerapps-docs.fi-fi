---
title: Power Queryn vianmääritys | Microsoft Docs
description: Ratkaise ongelmia Power Queryn avulla, jotta voit luoda mukautetun entiteetin Common Data Service (CDS) for Apps -palvelussa.
author: mllopis
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/16/2018
ms.author: millopis
ms.openlocfilehash: b89d7a59406d19759b84c34dbda84b98b10d5e58
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34445725"
---
# <a name="troubleshooting-power-query"></a>Power Queryn vianmääritys
Kun käytät Power Queryä laatiaksesi mukautetun kohteen, joka sisältää tietoja ulkoisista lähteistä, esiin saattaa tulla tämä virhe:

`Your Azure Active Directory administrator has set a policy that prevents you from using this feature. Please contact your administrator, who can grant permissions for this feature on your behalf.`

Virhe tulee näkyviin, jos Power Query ei voi käyttää organisaation tietoja PowerAppsissa tai Common Data Service (CDS) for Apps -palvelussa. Tämä tilanne tulee esiin kahdessa seuraavassa tilanteessa:

* Azure Active Directory (AAD) -vuokraajan järjestelmänvalvoja ei ole sallinut käyttäjien mahdollisuutta antaa suostumusta sovelluksille, jotka käyttävät yrityksen tietoja heidän puolestaan.
* Hallitsemattoman Active Directory -vuokraajan käyttäminen. Hallitsematon vuokraaja on hakemisto, jolla ei ole yleistä järjestelmänvalvojaa ja joka on luotu täydentämään omatoimisen rekisteröitymisen tarjousta. Tämän skenaarion korjaamiseksi käyttäjien täytyy ensin muuntaa vuokraaja hallituksi vuokraajaksi ja seurata sitten jompaakumpaa seuraavassa osassa kuvatusta kahdesta ratkaisusta ongelmaan.

Tämän ongelman ratkaisemiseksi Azure Active Directory -järjestelmänvalvojan täytyy noudattaa jommankumman tässä artikkelissa myöhemmin esitetyn toimenpiteen vaiheita.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>Salli käyttäjän antaa suostumus sovelluksille, jotka käyttävät yrityksen tietoja
Tämä lähestymistapa on ehkä helpompi kuin seuraava, mutta se sallii laajemmat käyttöoikeudet.

1. Avaa osoitteessa [https://portal.azure.com](https://portal.azure.com) **Azure Active Directory** -lapa, ja valitse sitten **Käyttäjäasetukset**.
2. Valitse vaihtoehto **Kyllä** kohdan **Käyttäjät voivat antaa sovellukselle luvan käyttää yrityksen tietoja puolestaan** vierestä ja valitse sitten **Tallenna**.

## <a name="allow-power-query-to-access-company-data"></a>Salli Power Queryn käyttää yrityksen tietoja
Vaihtoehtoisesti vuokraajan järjestelmänvalvoja voit antaa Power Querylle suostumuksen muokkaamatta vuokraajan laajuisia käyttöoikeuksia.

1. Asenna [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps).
2. Suorita seuraavat PowerShell-komennot:
   * Login-AzureRmAccount (ja kirjaudu sisään vuokraajan järjestelmänvalvojana)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

Tämän tavan etuna vuokraajan laajuiseen ratkaisuun verrattuna on se, että ratkaisu on hyvin kohdennettu. Se täydentää vain **Power Query** -palveluobjektia mutta ei tee muita käyttöoikeusmuutoksia vuokraajaan.

## <a name="updating-personal-data"></a>Henkilökohtaisten tietojen päivittäminen

Käyttäjät voivat päivittää koosteita ja muita tietoja (kuten kyselyiden nimiä ja koosteen metatietoja) kyselyeditorin ja kyselyeditorin `Options`-valintaikkunan kautta.

PowerAppsissa kyselyeditoria voidaan käyttää siirtymällä tietoruutuun, laajentamalla se ja napsauttamalla sitten Entiteetit-ruudun valikkokohdetta. Napsauta kolmea pistettä ja valitse Muokkaa kyselyitä. Napsauta sitten `Options`-painiketta valintanauhassa ja sitten `Export Diagnostics` -painiketta.


## <a name="deleting-personal-data"></a>Henkilökohtaisten tietojen poistaminen

Useimmat tiedot poistetaan automaattisesti 30 päivän kuluessa. Koosteiden tietojen ja metatietojen osalta käyttäjän on poistettava kaikki koosteensa PowerAppsin kautta. Kaikki liittyvät tiedot ja metatiedot poistetaan 30 päivän kuluessa.

Koosteita voidaan poistaa PowerAppsista poistamalla tietojen integrointiprojektit, jotka voidaan poistaa saman nimisestä välilehdestä napsauttamalla ”...”-painiketta ja valitsemalla `Delete`-vaihtoehto.

Jos olet luonut koosteen Uudet entiteetit tiedoista (Technical Preview) -ominaisuuden avulla, voit poistaa sen napsauttamalla ”...”-painiketta, valitsemalla Muokkaa kyselyitä ja valitsemalla sitten Asetukset valintanauhasta ja napsauttamalla lopuksi Poista kaikki kyselyt -painiketta. Kun vahvistat, että haluat poistaa kyselysi, ne poistetaan.


## <a name="exporting-personal-data"></a>Henkilökohtaisten tietojen vieminen

Käyttäjä voi avata kyselyeditorin napsauttamalla `Options`-painiketta valintanauhassa ja sitten `Export Diagnostics` -painiketta.

PowerAppsissa kyselyeditoria voidaan käyttää siirtymällä tietoruutuun, laajentamalla se ja napsauttamalla sitten Entiteetit-ruudun valikkokohdetta. Napsauta kolmea pistettä ja valitse Muokkaa kyselyitä. Napsauta sitten `Options`-painiketta valintanauhassa ja sitten `Export Diagnostics` -painiketta.

Järjestelmän luomiin lokeihin, jotka koskevat käyttäjän toimintoja käyttöliittymässä, voidaan käyttää Azure-portaalissa.



---
title: PowerAppsin palvelupaketin 2 käyttöoikeuksia vaativat monimutkaiset entiteetit | Microsoft Docs
description: Luettelo Common Data Service (CDS) for Appsin sisältämistä monimutkaisista entiteeteistä, jotka edellyttävät PowerAppsin palvelupaketin 2 käyttöoikeutta.
author: clwesene
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: reference
ms.date: 07/17/2018
ms.author: clwesene
ms.openlocfilehash: 76c101f35e236ac6bf037d2b5b748ca1b943d61d
ms.sourcegitcommit: efea7ed5ad8e80c87ba423fb094fa94b4e864d75
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/26/2018
ms.locfileid: "39266253"
---
# <a name="complex-entities-and-licensing"></a>Monimutkaiset entiteetit ja käyttöoikeudet
Seuraavia monimutkaisia, palvelimen logiikkaa sisältävät entiteetit vaativat näitä entiteettejä käyttävien sovellusten tai työnkulkujen käyttäjillä PowerApps Plan 2- tai Microsoft Flow Plan 2 -sopimuksen:

* Koodin laajennukset. Lisätietoja: [Laajennuksen kehitys](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development))
* Reaaliaikaiset työnkulut. Lisätietoja: [Työnkulun prosessit](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes))

    > [!IMPORTANT]
    >  Vain työnkulkuja, jotka on muunnettu reaaliaikaisiksi työnkuluiksi, pidetään reaaliaikaisina ja synkronoituina. Työnkulkuja, jotka suoritetaan taustalla, voidaan silti käyttää asianmukaisen PowerApps-palvelupaketin osana, eivätkä ne vaadi muita käyttöoikeuksia.

Jos haluat tietää, onko entiteeteissäsi monitasoista liiketoimintalogiikkaa, tarkista laajennuksen kokoonpanojen ja ympäristössäsi määriteltyjen työnkulkujen luettelo.

## <a name="complex-entities-installed-with-dynamics-365"></a>Dynamics 365:n mukana asennetut monimutkaiset entiteetit
Seuraavassa taulukossa on lueteltu entiteettejä, jotka sisältävät monimutkaista palvelinpuolen logiikkaa valmiina Dynamics 365 -sovelluksen asennuksen osana. Tämä luettelo on tarkoitettu ohjeeksi. Monimutkaisten entiteettien luettelo voi vaihdella sen mukaan, mitkä Dynamics 365 -sovellukset ja -versiot on asennettu ympäristöösi.

> [!NOTE]
>  Jos käytössäsi on Common Data Service etkä ole asentanut Dynamics 365 -sovellusta tai kolmannen osapuolen ratkaisua, ympäristössäsi ei ole monimutkaista palvelinpuolen logiikkaa sisältäviä entiteettejä.

* Tili
* Sopimus
* Sopimuksen varauksen päivämäärä
* Sopimuksen varauksen tapaus
* Sopimuksen varauksen tuote
* Sopimuksen varauksen palvelu
* Sopimuksen varauksen palvelutehtävä
* Sopimuksen varauksen määritys
* Sopimuksen laskun päivämäärä
* Sopimuksen laskun tuote
* Sopimuksen laskun määritys
* Sopimuksen alitila
* Varattava resurssi
* Varattavan resurssin varaus
* Varattavan resurssin varauksen otsikko
* Varattavan resurssin luokka
* Varattavan resurssin luokkamääritys
* Varattavan resurssin ominaisuus
* Varattavan resurssin ryhmä
* Varauksen hälytys
* Varauksen hälytyksen tila
* Varauksen tila
* Tapaus
* Ominaisuus
* Osaamisen vaatimus (vanhentunut)
* Kilpailija
* Yhteystiedot
* Asiakkaan resurssi
* Delegointi
* Kulut
* Kenttälaskenta
* Kenttäpalvelun hinnastonimike
* Filter
* Seuraa
* Tapaustyyppi
* Tapaustyypin tuote
* Tapaustyypin palvelu
* Tapaustyypin palvelutehtävä
* Integrointityö
* Integrointityön tiedot
* Varastonmuutos
* Varastonmuutoksen tuote
* Varastosiirto
* Lasku
* Laskutustiheys
* Laskurivi
* Laskurivin tiedot
* Kirjausraportti
* Kirjausraportin rivi
* Liidi
* Huomautus
* OData v4 -tietolähde
* Mahdollisuus
* Mahdollisuusrivi
* Mahdollisuusrivin tiedot
* Tilaus
* Tilauksen laskutuksen tuote
* Tilauksen laskutuksen määritys
* Tilausrivi
* Maksu
* Maksun tiedot
* Julkaise määritys
* Julkaise sääntömääritys
* Postinumero
* Hinnasto
* Hinnaston nimike
* Tuote
* Projekti
* Projektin hyväksyntä
* Projektin sopimusrivin tiedot
* Projektin sopimusrivin välitavoite
* Projektin sopimusrivin resurssiluokka
* Projektin sopimusrivin tapahtumaluokka
* Project Parameter
* Project Stages
* Projektitehtävän tilan käyttäjä
* Projektiryhmän jäsenen rekisteröityminen
* Ostotilaus
* Ostotilauksen lasku
* Ostotilauksen tuote
* Ostotilauksen vastaanotto
* Ostotilauksen vastaanoton tuote
* Ostotilauksen alitila
* Jonon kohde
* Tarjous
* Tarjouksen varauksen tapaus
* Tarjouksen varauksen tuote
* Tarjouksen varauksen palvelu
* Tarjouksen varauksen palvelutehtävä
* Tarjouksen varauksen määritys
* Tarjouksen laskutuksen tuote
* Tarjouksen laskutuksen määritys
* Tarjousrivi
* Tarjousrivin tiedot
* Tarjousrivin välitavoite
* Tarjousrivin resurssiluokka
* Tarjousrivin tapahtumaluokka
* Tarjouksen projektihinnasto
* Luokitusmalli
* Luokitusarvo
* Vaatimuksen ominaisuus
* Vaatimuksen resurssiluokka
* Vaatimuksen resurssin ensisijaisuus
* Vaatimuksen tila
* Resurssipyyntö
* Resurssitarve
* Resurssitarpeen tiedot
* RMA
* RMA-tuote
* RMA-vastaanotto
* RMA-vastaanoton tuote
* RMA-alitila
* Roolin osaamistarve
* Roolin hinta
* RTV
* RTV-tuote
* RTV-alitila
* Verokoodi
* Verokoodin tiedot
* Aikamerkintä
* Aikaryhmä
* Aikaryhmän tiedot
* Vapaapyyntö
* Tapahtumaluokan hinta
* Käyttäjä
* Näkymä
* Seinän näkymä
* Varasto
* Työtilaus
* Työtilauksen tapaus
* Työtilauksen tuote
* Työtilauksen palvelu
* Työtilauksen palvelutehtävä
* Työtilauksen alitila
* Työmalli


## <a name="licensing"></a>Käyttöoikeudet
Katso lisätietoja PowerAppsin ja Dynamics 365 -käyttöoikeuksista [Käyttöoikeuksien yleiskuvaus](../../administrator/pricing-billing-skus.md) -sivulta.


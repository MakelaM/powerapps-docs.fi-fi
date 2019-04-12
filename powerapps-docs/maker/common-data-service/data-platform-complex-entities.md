---
title: 'Monimutkaiset entiteetit, jotka vaativat PowerApps-palvelupaketin 2 käyttöoikeudet | Microsoft Docs'
description: 'Niiden Common Data Servicen monimutkaisten entiteettien luettelo, jotka vaativat PowerApps-palvelupaketin 2 käyttöoikeudet.'
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: reference
ms.date: 07/17/2018
ms.author: lanced
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="complex-entities-and-licensing"></a>Monimutkaiset entiteetit ja käyttöoikeudet
Entiteetit, jotka sisältävät seuraavaa monimutkaista palvelinpään logiikkaa, vaativat näitä entiteettejä käyttäviltä sovelluksen tai työnkulun käyttäjiltä PowerApps-palvelupaketin 2 tai Microsoft Flow -palvelupaketin 2 käyttöoikeudet:

* Koodilaajennukset. Lisätietoja: [Laajennuskehitys](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development)
* Reaaliaikaiset työnkulut. Lisätietoja: [Työnkulkuprosessit](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes)

    > [!IMPORTANT]
    >  Vain työnkulkuja, jotka on muunnettu reaaliaikaisiksi työnkuluiksi, käsitellään reaaliaikaisina ja synkronisina. Taustalla suoritettavia työnkulkuja voi yhä käyttää soveltuvan PowerApps-palvelupaketin kanssa. Ne eivät vaadi lisäkäyttöoikeuksia.

Ympäristöön määritettyjen laajennuskokoonpanojen ja työnkulkujen luettelossa on lisätietoja entiteetteihin lisätystä monimutkaisesta liiketoimintalogiikasta.

## <a name="complex-entities-installed-with-dynamics-365"></a>Dynamics 365:n kanssa asennetut monimutkaiset entiteetit
Seuraava taulukko sisältää entiteetit, jotka sisältävät valmista monimutkaista palvelinpään logiikkaa, joka on osa Dynamics 365 -sovelluksen asennusta. Tämä luettelo toimii oppaana. Monimutkaisten entiteettien luettelo on erilainen sen mukaan, mitä Dynamics 365 -sovelluksia ja -versioita ympäristöön on asennettu.

> [!NOTE]
>  Jos käytössä on Common Data Service, etkä ole asentanut Dynamics 365 -sovellusta tai kolmannen osapuolen ratkaisua, ympäristössä ei ole monimutkaista palvelinpään logiikkaa sisältäviä entiteettejä.

* Asiakas
* Sopimus
* Sopimuksen varauspäivä
* Sopimuksen varauksen tapaus
* Sopimuksen varauksen tuote
* Sopimuksen varauspalvelu
* Sopimuksen varauksen palvelutehtävä
* Sopimuksen varauksen asetukset
* Sopimuksen laskun päivämäärä
* Sopimuksen laskutustuote
* Sopimuksen laskun asetus
* Sopimuksen alitila
* Varattava resurssi
* Varattavissa olevan resurssin varaus
* Varattavissa olevan resurssin otsikko
* Varattavissa olevan resurssin luokka
* Varattavissa olevan resurssin luokkaliitos
* Varattavissa olevan resurssin ominaisuus
* Varattavissa oleva resurssiryhmä
* Varauksen hälytys
* Varauksen hälytyksen tila
* Varauksen tila
* Ominaisuus
* Osaamisaluetarve (Vanhentunut)
* Kilpailija
* Yhteyshenkilö
* Asiakasresurssi
* Delegointi
* Kulut
* Kenttälaskenta
* Field Service sovelluksen hinnaston nimike
* Suodatus
* Seuraa
* Tapauksen tyyppi
* Tapauksen tyypin tuote
* Tapauksen tyypin palvelu
* Tapauksen tyypin palvelutehtävä
* Integrointityö
* Integrointityön tiedot
* Varastonmuutos
* Varastonmuutoksen tuote
* Varaston siirto
* Lasku
* Laskutustiheys
* Laskurivi
* Laskurivin tiedot
* Päivyri
* Kirjauskansion rivi
* Lead
* Huomautus
* OData v4 -tietolähde
* Mahdollisuus
* Mahdollisuusrivi
* Mahdollisuusrivin tiedot
* Tilaus
* Tilauksen laskutustuote
* Tilauksen laskutusasetus
* Tilausrivi
* Maksu
* Maksutiedot
* Viestimääritys
* Viestisäännön määritys
* Postinumero
* Hinnasto
* Hinnastonimike
* Tuote
* Projekti
* Projektin hyväksyntä
* Projektin sopimusrivin tiedot
* Projektisopimusrivin välitavoite
* Projektin sopimusrivin resurssiluokka
* Projektin sopimusrivin tapahtumaluokka
* Projektin parametri
* Projektin vaiheet
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
* Tarjouksen varaustuote
* Tarjouksen varauspalvelu
* Tarjouksen varauksen palvelutehtävä
* Tarjouksen varausasetus
* Tarjouksen laskutustuote
* Tarjouksen laskutusasetus
* Tarjousrivi
* Tarjousrivin tiedot
* Tarjousrivin välitavoite
* Tarjousrivin resurssiluokka
* Tarjousrivin tapahtumaluokka
* Tarjouksen projektihinnasto
* Luokitusmalli
* Luokitusarvo
* Tarpeen ominaisuus
* Tarpeen resurssiluokka
* Tarpeen resurssin ensisijaisuus
* Tarpeen tila
* Resurssipyyntö
* Resurssitarve
* Resurssitarpeen tiedot
* Palautus
* Tavaran valtuutettu palautustuote
* Tavaran valtuutettu palautuksen vastaanotto
* Tavaran valtuutetun palautuksen vastaanoton tuote
* Palautuksen alitila
* Roolin osaamistarve
* Roolin hinta
* Palautus toimittajalle
* Toimittajalle palautettava tuote
* Toimittajalle tehtävän palautuksen alitila
* Verokoodi
* Verokoodin tiedot
* Aikamerkintä
* Aikaryhmä
* Aikaryhmän tiedot
* Poissaolopyyntö
* Tapahtumaluokan hinta
* Käyttäjä
* Näkymä
* Seinänäkymä
* Varasto
* Työtilaus
* Työtilauksen tapaus
* Työtilauksen tuote
* Työtilauksen palvelu
* Työtilauksen palvelutehtävä
* Työtilauksen alitila
* Työmalli


## <a name="licensing"></a>Käyttöoikeuden hankkiminen
Lisätietoja PowerApps- ja Dynamics 365 -käyttöoikeuksista on [Käyttöoikeuksien yleiskatsaus](../../administrator/pricing-billing-skus.md) -sivulla.


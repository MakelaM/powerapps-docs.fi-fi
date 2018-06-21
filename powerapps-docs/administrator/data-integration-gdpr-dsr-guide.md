---
title: Tietojen integrointi järjestelmänvalvojien asiakastiedoille
description: Henkilökohtaisten tietojen tunnistaminen, vienti ja poistaminen tietojen integroinnissa CDS for Apps -järjestelmänvalvojille
author: sabinn-msft
ms.service: powerapps
ms.topic: how-to
ms.component: cds
ms.date: 05/20/2018
ms.author: sabinn
ms.openlocfilehash: 01dafceacff89cb9b3a400caad5dde07a0995f1c
ms.sourcegitcommit: e59c849a88c6fc0ed333ef4ce2d982a5b8623c97
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34754163"
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-data-integration-for-common-data-service-for-apps-customer-data"></a>Common Data Service for Appsin asiakastietoihin tietojen integroinnissa kohdistuviin DSR-pyyntöihin vastaaminen

## <a name="introduction-to-dsr-requests"></a>Johdanto DSR-pyyntöihin

Euroopan unionin (EU) yleinen tietosuoja-asetus (GDPR) antaa ihmisille (joita kutsutaan asetuksessa rekisteröidyiksi) oikeudet hallita henkilötietoja, joita työnantaja tai muu organisaatio tai virasto (jota kutsutaan henkilötietorekisterinpitäjäksi tai vain rekisterinpitäjäksi) on heistä kerännyt. GDPR määrittää henkilötiedoiksi hyvin yleisesti mitkä tahansa tiedot, jotka liittyvät tunnistettuun tai tunnistettavissa olevaan luonnolliseen henkilöön. GPDR antaa rekisteröidyille oikeuden seuraaviin toimiin heidän henkilökohtaisiin tietoihinsa liittyen:

- Kopion saaminen
- Korjausten pyytäminen
- Käsittelyn rajoittaminen
- Poistaminen
- Tietojen saaminen sähköisessä muodossa niin, että ne voidaan siirtää toiselle rekisterinpitäjälle

Rekisteröidyn rekisterinpitäjälle tekemää virallista pyyntöä ryhtyä toimiin henkilötietoihin liittyen kutsutaan rekisteröidyn tietopyynnöksi (Data Subject Rights, DSR).

Tässä asiakirjassa kerrotaan, miten Microsoft valmistautuu yleiseen tietosuoja-asetukseen. Annamme myös esimerkkejä toimenpiteistä, joihin voit ryhtyä täyttääksesi yleisen tietosuoja-asetuksen vaatimukset, kun käytät tietojen integrointia järjestelmänvalvojille CDS for Appsin järjestelmänvalvojaportaalin kautta. Opit, miten Microsoftin tuotteet, palvelut ja hallintatyökalut auttavat rekisterinpitäjiä etsimään Microsoftin pilvipalveluissa olevia henkilötietoja ja suorittamaan niille toimintoja rekisteröityjen tietopyyntöihin vastaamiseksi.

### <a name="searching-for-and-identifying-personal-data"></a>Henkilökohtaisten tietojen hakeminen ja tunnistaminen

Tietojen integrointi järjestelmänvalvojille CDS for Appsissa sallii kenen tahansa integrointisovelluksen käyttäjän tarkastella tietojaan Tietojen integrointi -välilehden avulla osoitteessa:

[https://admin.powerapps.com/dataintegration](https://admin.powerapps.com/dataintegration)

Käyttäjää koskevat tallennetut tiedot näkyvät portaalissa. Kaikki projektit näkyvät Projektit-välilehdessä:

![Näytä projektit Projektit-välilehdessä](./media/data-integration-gdpr-dsr/projects-tab.png)

Kaikki yhteysjoukot näkyvät Yhteysjoukot-välilehdessä:

![Näytä yhteysjoukot näkyvät Yhteysjoukot-välilehdessä](./media/data-integration-gdpr-dsr/connections-tab.png)

Kaikki mallit näkyvät Mallit-välilehdessä:

![Näytä mallit Mallit-välilehdessä](./media/data-integration-gdpr-dsr/templates-tab.png)

## <a name="securing-and-controlling-access-to-personal-information"></a>Henkilökohtaisten tietojen suojaaminen ja käytön hallinta

CDS for Appsin tietojen integroinnissa järjestelmänvalvojille tietojen integrointisovelluksen tallentamia tietoja voi käyttää vain järjestelmänvalvojaportaalin kautta.

## <a name="deleting-personal-data"></a>Henkilökohtaisten tietojen poistaminen

CDS for Appsin tietojen integroinnissa järjestelmänvalvojille käyttäjien luomat tiedot, projektit ja yhteysjoukot voi poistaa käyttäjä, johon tiedot liittyvät. Jos käyttäjät haluavat poistaa henkilökohtaisia tietojaan, he voivat kirjautua järjestelmänvalvojaportaalin: [https://admin.powerapps.com](https://admin.powerapps.com)

Käyttäjät voivat poistaa projekteja siirtymällä Projektit-välilehteen, napsauttamalla kolmea pistettä projektin vieressä ja valitsemalla sitten Poista-vaihtoehdon:

![Poista projekteja napsauttamalla kolmea pistettä](./media/data-integration-gdpr-dsr/projects-del.png)

Käyttäjät voivat poistaa malleja siirtymällä Mallit-välilehteen, napsauttamalla kolmea pistettä mallin vieressä ja valitsemalla sitten Poista-vaihtoehdon:

![Poista malleja napsauttamalla kolmea pistettä](./media/data-integration-gdpr-dsr/templates-del.png)

Käyttäjät voivat poistaa yhteysjoukkoja siirtymällä Yhteysjoukot-välilehteen, napsauttamalla kolmea pistettä yhteysjoukon vieressä ja valitsemalla sitten Poista-vaihtoehdon:

![Poista yhteysjoukkoja napsauttamalla kolmea pistettä](./media/data-integration-gdpr-dsr/connsets-del.png)

## <a name="exporting-personal-data"></a>Henkilökohtaisten tietojen vieminen

CDS for Appsin tietojen integroinnissa järjestelmänvalvojille käyttäjien luomat tiedot voi viedä käyttäjä, johon tiedot liittyvät. Jos käyttäjät haluavat viedä henkilökohtaisia tietojaan, he voivat kirjautua järjestelmänvalvojaportaalin:

[https://admin.powerapps.com](https://admin.powerapps.com)

Jos käyttäjät haluavat viedä projekteja tai projekteja ja suoritushistorian, he voivat siirtyä Projektit-välilehteen, napsauttaa kolmea pistettä projektin vieressä ja valita sitten haluamansa vientivaihtoehdon:

![Vie projekteja napsauttamalla kolmea pistettä](./media/data-integration-gdpr-dsr/projects-exp.png)

Jos käyttäjät haluavat viedä malleja, he voivat siirtyä Mallit-välilehteen, napsauttaa kolmea pistettä mallin vieressä ja valita sitten vientivaihtoehdon:

![Vie malleja napsauttamalla kolmea pistettä](./media/data-integration-gdpr-dsr/templates-exp.png)

Jos käyttäjät haluavat viedä yhteysjoukkoja, he voivat siirtyä Yhteysjoukot-välilehteen, napsauttaa kolmea pistettä yhteysjoukon vieressä ja valita sitten vientivaihtoehdon:

![Vie yhteysjoukkoja napsauttamalla kolmea pistettä](./media/data-integration-gdpr-dsr/connsets-exp.png)

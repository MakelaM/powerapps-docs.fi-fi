---
title: Kokeiluympäristöt | Microsoft Docs
description: Ota toimintoja käyttöön ennen virallista julkaisua osallistumalla PowerAppsin esiversio-ohjelmaan
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 01/09/2019
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: bd05c4c1251058d464034de71d9b1c287e714190
ms.sourcegitcommit: 170deba334c922157bbb826c795bed3fa858b85e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/10/2019
ms.locfileid: "54196100"
---
# <a name="about-trial-environments"></a>Tietoja kokeiluympäristöistä

Tällä hetkellä voit luoda kahdenlaisia Common Data Service (CDS) for Apps -ympäristöjä: kokeilu- ja tuotantoympäristöjä. Kokeiluympäristön avulla voit kokeilla Dynamics 365 for Customer Engagement -sovelluksia maksutta. Kokeiluympäristöt vanhenevat 30 päivän kuluttua.

**Ympäristöt**-sivulta näet ympäristötyypit, joita sinulla on, sekä kokeiluympäristöjen tulevat vanhenemispäivät:

> [!div class="mx-imgBorder"] 
> ![PowerApps-ympäristöt](media/powerapps-environments75b.png "PowerApps-ympäristöt")

## <a name="convert-a-trial-environment-to-production"></a>Kokeiluympäristön muuntaminen tuotantoympäristöksi

Jos loit kokeiluympäristön käytön aikana resursseja, jotka haluat säilyttää yli 30 päivää, muunna kokeiluympäristö tuotantoympäristöksi.

Tuotantoympäristöksi muuttaminen onnistuu, jos seuraavat ehdot täyttyvät:

**Soveltuva PowerApps-palvelupaketti**. Palvelupaketti, joka mahdollistaa tuotantoympäristöjen luomisen, esimerkiksi PowerAppsin palvelupaketti 2. Artikkelista [Tiimillesi sopivien palvelupakettien valitseminen](https://powerapps.microsoft.com/pricing/) saat tietoa PowerApps-palvelupaketeista, jotka sisältävät mahdollisuuden luoda tuotantoympäristöjä. Artikkelista [Palvelupakettien tunnistaminen](#how-do-i-identify-my-plans) saat ohjeita oman PowerApps-palvelupakettisi tarkistamiseen.
**Käytettävissä oleva tuotantoympäristökiintiö**. Voit luoda kunkin palvelupaketin puitteissa tietyn määrän tuotantoympäristöjä. Esimerkiksi PowerAppsin palvelupaketti 2 mahdollistaa kahden tuotantoympäristön luomisen. Jos olet jo luonut kaksi tuotantoympäristöä, sinun on poistettava niistä jompikumpi ennen uuden ympäristön luomista. Lisätietoja saat kohdasta [Ympäristön luominen](environments-overview.md#creating-an-environment).

Muunna kokeiluympäristö tuotantoympäristöksi seuraamalla näitä ohjeita:

1. Avaa [https://admin.powerapps.com/environments](https://admin.powerapps.com/environments) ja kirjaudu sisään järjestelmänvalvojana.
 
2. Avaa **Ympäristöt**-sivu ja valitse tuotantoympäristöksi muunnettava kokeiluympäristö:

    > [!div class="mx-imgBorder"] 
    > ![Valitse kokeiluympäristö](media/powerapps-environments75b-select-trial.png "Valitse kokeiluympäristö")

3. Valitse **Tiedot**-välilehdessä **Muunna**:

    > [!div class="mx-imgBorder"] 
    > ![Valitse Muunna](media/powerapps-trial-select-convert.png "Valitse Muunna")

4. Valitse **Vahvista**:

    > [!div class="mx-imgBorder"] 
    > ![Valitse Vahvista](media/powerapps-trial-select-confirm.png "Valitse Vahvista")

Jos ympäristöön kuuluu tietokanta, tuotantoympäristöksi muuntamiseen voi kulua useita tunteja. Voit seurata edistymistä **Tiedot**-välilehden ilmoituksen kautta:

  > [!div class="mx-imgBorder"] 
  > ![Muuntaminen aloitettu](media/powerapps-trial-conversion-started.png "Muuntaminen aloitettu")

## <a name="frequently-asked-questions"></a>Usein kysytyt kysymykset

### <a name="who-can-convert-a-trial-environment-to-a-production-environment"></a>Kuka voi muuntaa kokeiluympäristön tuotantoympäristöksi?

Seuraavien ehtojen on täytyttävä, jotta voit muuntaa kokeiluympäristön tuotantoympäristöksi:

**Sinulla on oltava soveltuva PowerApps-palvelupaketti**. Tarvitset palvelupaketin, joka mahdollistaa tuotantoympäristöjen luomisen, esimerkiksi PowerAppsin palvelupaketin 2. Artikkelista [Tiimillesi sopivien palvelupakettien valitseminen](https://powerapps.microsoft.com/pricing/) saat tietoa PowerApps-palvelupaketeista, jotka sisältävät mahdollisuuden luoda tuotantoympäristöjä. Artikkelista [Palvelupakettien tunnistaminen](#how-do-i-identify-my-plans) saat ohjeita oman PowerApps-palvelupakettisi tarkistamiseen.
**Sinulla on oltava tuotantoympäristökiintiötä jäljellä**. Voit luoda kunkin palvelupaketin puitteissa tietyn määrän tuotantoympäristöjä. Esimerkiksi PowerAppsin palvelupaketti 2 mahdollistaa kahden tuotantoympäristön luomisen. Jos olet jo luonut kaksi tuotantoympäristöä, sinun on poistettava niistä jompikumpi ennen uuden ympäristön luomista.

### <a name="what-if-i-dont-have-available-quota-for-production-environments"></a>Entä jos tuotantoympäristökiintiö on täynnä?

Ota yhteyttä Office 365:n yleiseen järjestelmänvalvojaan tai Azure Active Directory (Azure AD) -vuokraajan järjestelmänvalvojaan ja pyydä häntä
- määrittämään sinulle PowerAppsin palvelupaketti 2 
- etsimään toinen käyttäjä, jolla on tuotantoympäristökiintiötä jäljellä.

Voit myös ostaa PowerApps-palvelupaketin.

### <a name="can-every-office-365-global-admin-or-azure-ad-tenant-admin-convert-a-trial-environment-to-a-production-environment"></a>Voivatko kaikki Office 365:n yleiset järjestelmänvalvojat tai Azure AD -vuokraajan järjestelmänvalvojat muuntaa kokeiluympäristöjä tuotantoympäristöiksi?

Ei. Yleisillä järjestelmänvalvojilla ja Azure AD -vuokraajan järjestelmänvalvojilla on oltava riittävästä tuotantoympäristökiintiötä jäljellä muuntaakseen kokeiluympäristöjä tuotantoympäristöiksi.

### <a name="is-there-a-way-to-recover-a-deleted-trial-environment"></a>Voiko poistetun kokeiluympäristön palauttaa?

Poistetun kokeiluympäristön palauttamista ei voida taata, mutta sitä voidaan yrittää 7 päivän sisällä poistamisesta. Ympäristön tietokantaa ei voi palauttaa, mutta (PowerAppsilla luodut) sovellukset ja työnkulut voi.

### <a name="how-can-i-retain-my-data-and-resources-if-i-dont-have-a-way-to-convert-the-trial-environment-to-a-production-environment"></a>Miten voin säilyttää tietoni ja resurssini, jos en pysty muuntamaan kokeiluympäristöä tuotantoympäristöksi?

Voit viedä tiedot ja resurssit toiseen ympäristöön. Jos haluat säilyttää niitä pidempään, suosittelemme luomaan tuotantoympäristön tai yksittäisen ympäristön (PowerAppsin yhteisöpalvelupaketilla) ja viemään resurssit kyseiseen ympäristöön. 

Tässä ohjeita resurssien viemiseen.

|Ympäristön resurssin tyyppi  |Miten se viedään?  |
|---------|---------|
|Sovellukset (kaavio- ja mallipohjaiset) ja työnkulut     |Voit käyttää sovellusten ja työnkulkujen ympäristöstä viemiseen [paketointia](environment-and-tenant-migration.md).         |
|Tietokannan tiedot (Common Data Service (CDS) for Apps -ympäristö)     |Vaihtoehtoja on useita:<br/><ul><li>[Vie Exceliin](../user/export-data-excel.md) ja tallenna tiedot. Voit [tuoda tiedot](../user/import-data.md) toiseen ympäristöön.</li><br/><li>Voit käyttää [tietojen integrointipalveluita](data-integrator.md) ja ohjelmointirajapintoja tietojen viemiseksi toiseen ympäristöön.</li></ul> |

Kokeiluympäristöt, joiden tietokannoissa ei ole havaittu toimintaa 30 päivän sisällä, poistetaan.

### <a name="how-can-i-create-a-production-or-an-individual-environment"></a>Miten tuotantoympäristö tai yksittäinen ympäristö luodaan?

Tarvitset PowerApps-palvelupaketin, joka mahdollistaa tuotantoympäristön luomisen. Lisätietoja saat kohdasta [Ympäristön luominen](environments-overview.md#creating-an-environment).

Voit luoda yksittäisen ympäristön rekisteröitymällä [PowerAppsin yhteisöpalvelupaketin käyttäjäksi](https://powerapps.microsoft.com/communityplan/). Huomaa, että sovellusten jakamisessa yksittäisissä ympäristöissä on tiettyjä rajoituksia: ympäristöt on tarkoitettu ainoastaan henkilökohtaiseen käyttöön.

### <a name="how-do-i-identify-my-plans"></a>Mistä tunnistan palvelupakettini?

Voit selvittää käyttämäsi palvelupaketin valitsemalla PowerApps-sivuston oikeassa yläkulmassa olevan **rataskuvakkeen** ja valitsemalla sitten **Palvelupaketit**.

> [!div class="mx-imgBorder"] 
> ![Valitse Palvelupaketit](media/powerapps-plans.png "Valitse Palvelupaketit")

### <a name="see-also"></a>Katso myös
[Ympäristöjen hallinta PowerAppsissa](environments-administration.md)<br/>
[Ympäristöjen yleiskatsaus](environments-overview.md)<br/>
[Tiimillesi sopivan palvelupaketin valitseminen](https://powerapps.microsoft.com/pricing/)<br/>
[Käyttöoikeuksien yleiskatsaus](pricing-billing-skus.md)<br/>

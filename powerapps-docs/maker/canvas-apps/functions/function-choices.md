---
title: Choices-funktio | Microsoft Docs
description: PowerAppsin Choices-funktion viitetiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/15/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c9d3e9c6c408d70e22d566855e5899a0f5b0fae7
ms.sourcegitcommit: 39b32abb19ad9fae98ca986ded6974bcbbb3cea7
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/24/2019
ms.locfileid: "68473955"
---
# <a name="choices-function-in-powerapps"></a>PowerAppsin Choices-funktio
Palauttaa hakusarakkeen mahdollisten arvojen taulukon.

## <a name="description"></a>Kuvaus
**Choices**-funktio palauttaa hakusarakkeen mahdollisten arvojen taulukon.  

**Choices**-funktion avulla voit tuottaa vaihtoehtojen luettelon, josta käyttäjä voi valita. Tätä funktiota käytetään yleisesti [**Yhdistelmäruutu**](../controls/control-combo-box.md)-ohjausobjektin kanssa muokkauslomakkeissa.

**Choices**-funktion hakutoiminnosta palauttama taulukko vastaa hakuun liittyvää viitetaulukkoa. Kun käytät **Choices**-funktiota, sinun ei tarvitse lisätä viitetaulukkoa lisätietolähteenä. **Choices** palauttaa viitetaulukon kaikki sarakkeet.

Koska **Choices** palauttaa taulukon, voit käyttää funktioita [**Filter**](function-filter-lookup.md), [**Sort**](function-sort.md) ja [**AddColumns**](function-table-shaping.md) sekä kaikkia muita taulukonkäsittelyfunktioita taulukon suodattamiseen, lajittelemiseen ja muotoilemiseen. 

Tällä hetkellä et voi [delegoida](../delegation-overview.md) **Choices**-funktiota. Jos tämä rajoitus muodostaa ongelman sovelluksessa, lisää viite-entiteetti tietolähteeksi ja käytä sitä suoraan. 

**Choices**-funktio ei vaadi, että sarakkeiden nimet olisivat merkkijonoja ja lainausmerkkeihin kirjoitettuja, toisin kuin [**ShowColumns**](function-table-shaping.md), [**Search**](function-filter-lookup.md) ja muut taulukkofunktiot. Anna kaava samoin kuin jos viittaisit sarakkeeseen suoraan.

Sarakeviittausten on viitattava suoraan tietolähteeseen. Jos tietolähde on esimerkiksi **Accounts** ja haku on **SLA**, sarakeviittaus on **Accounts.SLA**. Viittausta ei voi välittää funktion, muuttujan tai ohjausobjektin kautta. Jos tätä esimerkkiä laajentaen **Accounts** syötetään **Valikoima**-ohjausobjektiin, viittaa valittuun tiliin käyttämällä kaavaa **Gallery.Selected.SLA**. Tämä viittaus on kuitenkin välitetty ohjausobjektin kautta, joten sitä ei voida välittää **Columns**-funktioon. Sinun on silti käytettävä kaavaa **Accounts.SLA**.

Tällä hetkellä voit käyttää haku sarakkeita vain SharePointin ja Common Data Service kanssa.

## <a name="syntax"></a>Syntaksi
**Choices**( *column-reference* )

* *column-reference* – Pakollinen.  Tietolähteen hakusarake. Älä kirjoita sarakkeen nimeä lainausmerkkeihin. Viittauksen on viitattava suoraan tietolähteen sarakkeeseen; se ei voi kulkea funktion tai ohjausobjektin kautta.

## <a name="examples"></a>Esimerkkejä

#### <a name="choices-for-a-lookup"></a>Hakuvaihtoehdot

1. [Luo tieto kanta](../../../administrator/create-database.md) Common Data Service ja valitse **Sisällytä malli sovellukset ja tiedot** -ruutu.

    Useita entiteettejä luodaan, kuten **Accounts**.

    **Huomautus**: Entiteettien nimet ovat yksikössä Web.powerapps.com ja monikko PowerApps Studio.

    ![Common Data Service for Appsin tili-entiteetin kenttien osittainen luettelo, jossa korostetaan, että ensisijainen yhteys henkilö on haku kenttä](media/function-choices/entity-account.png)

    **Accounts**-entiteetissä on **Ensisijainen yhteyshenkilö** -sarake, joka on haku **Contacts**-entiteettiin.  

    ![Common Data Service yhteys henkilö-entiteetin kenttien osittainen luettelo](media/function-choices/entity-contact.png)

    Jokaisessa tilissä jokin yhteystieto on nimetty ensisijaiseksi yhteyshenkilöksi, tai ensisijainen yhteyshenkilö on *tyhjä*.

1. [Luo sovellus](../data-platform-create-app.md) **Accounts**-entiteetistä.

1. Vieritä alaspäin näyttöjen ja ohjausobjektien luettelossa lähellä vasenta reunaa, kunnes **EditScreen1** tulee näkyviin, ja valitse sitten **EditForm1** välittömästi sen alapuolella.

    ![Valitse vasemmassa siirtymispalkissa EditForm1 kohdassa EditScreen1](media/function-choices/select-editform.png)

1. Valitse oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdeltä **Muokkaa kenttiä**.

    ![Avaa tiedot-ruutu](media/function-choices/open-data-pane.png)

1. Valitse **kentät** -ruudussa **Lisää kenttä**.

1. Hae **ensisijaista yhteys tieto** kenttää, valitse sen valinta ruutu ja valitse sitten **Lisää**.

    ![Tiedot-ruudun avaaminen valitsemalla Accounts](media/function-choices/field-list.png)

    **Ensisijainen yhteys henkilö** -kenttä näkyy lomakkeen alaosassa. Jos kentässä lukee virhe, valitse **tieto lähteet** **näkymä** -väli lehdeltä, valitse **tili** tieto lähteelle kolme pistettä (...) ja valitse sitten **Päivitä**.

1. (valinnainen) Vedä **Ensisijainen yhteyshenkilö** -kenttä kenttäluettelon alkuun.

1. Valitse **Ensisijainen yhteyshenkilö** -kortissa **Yhdistelmäruutu**-ohjausobjekti.

    Tämän ohjaus objektin **Items** -ominaisuudeksi on määritetty kaava, joka yksilöi sarakkeen joko sen näyttö nimen mukaan, kuten ensimmäisessä esimerkissä tai sen loogisessa nimessä, kuten toisessa esimerkissä:

   - **Choices( Accounts.'Primary Contact' )**
   - **Choices( Accounts.primarycontactid )**

     ![Kaavionäyttö ja lomakeohjausobjekti. Ensisijaisen yhteys tieto kortin yhdistelmä ruutu-ohjaus objekti on valittuna ja Items-ominaisuus, jossa on kaava vaihtoehdot (accounts. ' Primary Contact '), näkyy](media/function-choices/accounts-primary-contact.png)

1. Valitse **Aloitus**-välilehdessä **Uusi näyttö** ja valitse sitten **Blank**.

1. Valitse **Lisää**-välilehdestä **Arvotaulukko**.

1. Valitse **tieto taulukko** -ohjaus objektin **Items** -ominaisuudeksi Tämä kaava:

     **Choices( Accounts.'Primary Contact' )**

1. Valitse **tieto taulukko** -ohjaus objektin keskeltä linkki, joka alkaa **valita kentät...** ja valitse sitten niiden kenttien tai kenttien valinta ruudut, jotka haluat näyttää (esimerkiksi **Etunimi** ja **suku nimi**).

     ![Kaavionäyttö ja arvotaulukko-ohjausobjekti. Items-ominaisuudeksi on määritetty kaava Choices( Accounts.'Primary Contact' ), ja taulukossa näkyvät Contacts-entiteetin ensimmäisen tietuejoukon firstname- ja lastname-sarakkeet](media/function-choices/full-accounts-pc.png)
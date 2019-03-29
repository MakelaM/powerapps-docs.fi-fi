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
ms.openlocfilehash: 5c6876ac22f50be293781a7a6be58657f856baec
ms.sourcegitcommit: 9444e6404770788b99cfcdb13b41ca6187d25149
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/29/2019
ms.locfileid: "58623391"
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

Tällä hetkellä voit hakusarakkeita vain SharePoint- ja Common Data Service-kanssa.

## <a name="syntax"></a>Syntaksi
**Choices**( *column-reference* )

* *column-reference* – Pakollinen.  Tietolähteen hakusarake. Älä kirjoita sarakkeen nimeä lainausmerkkeihin. Viittauksen on viitattava suoraan tietolähteen sarakkeeseen; se ei voi kulkea funktion tai ohjausobjektin kautta.

## <a name="examples"></a>Esimerkkejä

#### <a name="choices-for-a-lookup"></a>Hakuvaihtoehdot

1. [Luo tietokanta](../../../administrator/create-database.md) Common Data Service-ja valitse **Sisällytä Mallisovellukset ja tiedot** ruutuun.

    Useita entiteettejä luodaan, kuten **Accounts**.

    **Huomautus**: Entiteettien nimien on yksittäinen osoitteessa web.powerapps.com ja plural PowerApps Studio.

    ![Common Data Service for Apps -palvelun Account-entiteetin kenttien osittainen luettelo, josta näkyy, että Ensisijainen yhteyshenkilö on hakukenttä](media/function-choices/entity-account.png)

    **Accounts**-entiteetissä on **Ensisijainen yhteyshenkilö** -sarake, joka on haku **Contacts**-entiteettiin.  

    ![Common Data Service -palvelun Contact-entiteetin kenttien osittainen luettelo](media/function-choices/entity-contact.png)

    Jokaisessa tilissä jokin yhteystieto on nimetty ensisijaiseksi yhteyshenkilöksi, tai ensisijainen yhteyshenkilö on *tyhjä*.

2. [Luo sovellus](../data-platform-create-app.md) **Accounts**-entiteetistä.

3. Vieritä alaspäin näyttöjen ja ohjausobjektien luettelossa lähellä vasenta reunaa, kunnes **EditScreen1** tulee näkyviin, ja valitse sitten **EditForm1** välittömästi sen alapuolella.

    ![Valitse vasemmassa siirtymispalkissa EditForm1 kohdassa EditScreen1](media/function-choices/select-editform.png)

4. Valitse **Ominaisuudet**-välilehti oikeanpuoleisessa ruudussa ja valitse **Accounts**.

    ![Tiedot-ruudun avaaminen valitsemalla Accounts](media/function-choices/open-data-pane.png)

5. Vieritä **Tiedot**-ruudussa alaspäin kenttäluetteloon.

    ![Tiedot-ruudun avaaminen valitsemalla Accounts](media/function-choices/field-list.png)

6. Etsi **Ensisijainen yhteyshenkilö** -valintaruutu ja valitse se, jos se on tyhjä.

7. (valinnainen) Vedä **Ensisijainen yhteyshenkilö** -kenttä kenttäluettelon alkuun.

8. Valitse **Ensisijainen yhteyshenkilö** -kortissa **Yhdistelmäruutu**-ohjausobjekti.

    **Kohteet** kyseisen ohjausobjektin asetuksena on kaava, joka tunnistaa sarakkeen sen näyttönimi, kuten ensimmäisessä esimerkissä tai sen looginen nimi, kuten toisessa esimerkissä:

   - **Choices( Accounts.'Primary Contact' )**
   - **Choices( Accounts.primarycontactid )**

     ![Kaavionäyttö ja lomakeohjausobjekti. **Yhdistelmäruutu**-ohjausobjekti **Ensisijainen yhteyshenkilö** -kortissa on valittuna, ja Items-ominaisuus kaavassa Choices( Accounts.'Primary Contact' ) on näkyvissä](media/function-choices/accounts-primary-contact.png)

9. Valitse **Aloitus**-välilehdessä **Uusi näyttö** ja valitse sitten **Blank**.

10. Valitse **Lisää**-välilehdestä **Arvotaulukko**.

11. Määritä **kohteet** -ominaisuuden **tietotaulukko** ominaisuudeksi tämä kaava:

     **Choices( Accounts.'Primary Contact' )**

12. Avaa **Tiedot**-ruutu ja valitse sitten **firstname**- tai **lastname**-valintaruutu tai mikä tahansa muu kenttä, jonka haluat näyttää.

     ![Kaavionäyttö ja arvotaulukko-ohjausobjekti. Items-ominaisuudeksi on määritetty kaava Choices( Accounts.'Primary Contact' ), ja taulukossa näkyvät Contacts-entiteetin ensimmäisen tietuejoukon firstname- ja lastname-sarakkeet](media/function-choices/full-accounts-pc.png)

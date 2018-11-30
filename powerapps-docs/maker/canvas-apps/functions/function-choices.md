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
ms.openlocfilehash: 531a614493ef739acd7be71f396dfc2f7e1ada1c
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42832792"
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

Tällä hetkellä hakusarakkeita voi käyttää vain SharePointin ja Common Data Service for Apps -palvelun kanssa.

## <a name="syntax"></a>Syntaksi
**Choices**( *column-reference* )

* *column-reference* – Pakollinen.  Tietolähteen hakusarake. Älä kirjoita sarakkeen nimeä lainausmerkkeihin. Viittauksen on viitattava suoraan tietolähteen sarakkeeseen; se ei voi kulkea funktion tai ohjausobjektin kautta.

## <a name="examples"></a>Esimerkkejä

#### <a name="choices-for-a-lookup"></a>Hakuvaihtoehdot

1. [Luo tietokanta](../../../administrator/create-database.md) Common Data Service for Apps -palvelussa ja valitse **Sisällytä mallisovellukset ja tiedot** -ruutu.

    Useita entiteettejä luodaan, kuten **Accounts**.

    **Huomautus**: entiteettien nimet ovat yksikössä web.powerapps.com-sivustossa ja monikossa PowerApps Studiossa.

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

    Kyseisen ohjausobjektin **Items**-ominaisuus on määritetty toiseen kahdesta kaavasta sen mukaan, mikä lisäasetusten **Käytä sarakkeiden näyttönimiä** -valintaruudun tila on.

   - Jos valintaruutu on valittuna, ominaisuus on määritetty tähän kaavaan:<br>**Choices( Accounts.'Primary Contact' )**
   - Jos valintaruutu on tyhjä, ominaisuus on määritetty tähän kaavaan:<br>**Choices( Accounts.primarycontactid )**

     ![Kaavionäyttö ja lomakeohjausobjekti. **Yhdistelmäruutu**-ohjausobjekti **Ensisijainen yhteyshenkilö** -kortissa on valittuna, ja Items-ominaisuus kaavassa Choices( Accounts.'Primary Contact' ) on näkyvissä](media/function-choices/accounts-primary-contact.png)

9. Valitse **Aloitus**-välilehdessä **Uusi näyttö** ja valitse sitten **Blank**.

10. Valitse **Lisää**-välilehdestä **Arvotaulukko**.

11. Määritä kunkin **Arvotaulukko**-ohjausobjektin **Items**-ominaisuudeksi jokin näistä kaavoista:

     - Jos **Käytä sarakkeiden näyttönimiä** -valintaruutu on valittuna lisäasetuksissa, käytä seuraavaa kaavaa:<br>**Choices( Accounts.'Primary Contact' )**
     - Muutoin käytä tätä kaavaa:<br>**Choices( Accounts.primarycontactid )**

12. Avaa **Tiedot**-ruutu ja valitse sitten **firstname**- tai **lastname**-valintaruutu tai mikä tahansa muu kenttä, jonka haluat näyttää.

     ![Kaavionäyttö ja arvotaulukko-ohjausobjekti. Items-ominaisuudeksi on määritetty kaava Choices( Accounts.'Primary Contact' ), ja taulukossa näkyvät Contacts-entiteetin ensimmäisen tietuejoukon firstname- ja lastname-sarakkeet](media/function-choices/full-accounts-pc.png)

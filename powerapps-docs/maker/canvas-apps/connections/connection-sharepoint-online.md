---
title: SharePoint-yhteyden yleiskatsaus | Microsoft Docs
description: Katso SharePointin käytettävissä olevat Funktiot, vastaukset ja esimerkit.
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/03/2019
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 65ce3b7736b55f3734d6da7d945965ed791a3ce4
ms.sourcegitcommit: f84095d964fe1fe5cc5290e5edbee284bd768e1e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/18/2019
ms.locfileid: "59007885"
---
# <a name="connect-to-sharepoint-from-a-canvas-app"></a>Yhdistäminen SharePoint-pohjaan perustuva sovellus

![SharePoint](./media/connection-sharepoint-online/sharepointicon.png)

Muodosta yhteys SharePoint-sivustoon voit luoda sovelluksen automaattisesti mukautetun luettelon tai muodosta yhteys, ennen kuin tietojen lisääminen olemassa olevan sovelluksen tai sovelluksen luominen alusta alkaen.

Voi kestää jompikumpi tai molemmat sopiva tapa sen mukaan, jossa tiedot sijaitsee:

- Näytä tietoja mukautetun luettelon SharePoint Online-sivustossa tai paikallisen sivustossa.
- Kuvien näyttäminen ja toistaa video- tai (vain SharePoint Online) kirjaston tiedostoja.

## <a name="generate-an-app"></a>Luo sovellus

Jos haluat mukautetun luettelon tietojen hallintaan, PowerApps voi [Luo kolmen näytön sovellus automaattisesti](../app-from-sharepoint.md). Käyttäjät voivat selata ensimmäisessä näytössä, Näytä kohteen tiedot toinen näyttö ja luoda tai päivittää kolmas näyttö-kohteita.

> [!NOTE]
> Jos SharePoint-luettelo sisältää **valinta**, **Lookup**, tai **henkilö tai ryhmä** sarakkeen, katso [tietojen näyttäminen valikoimassa](connection-sharepoint-online.md#show-list-columns-in-a-gallery) jäljempänä tässä aiheessa.

## <a name="create-a-connection"></a>Luo yhteys

1. [Kirjaudu sisään Powerappsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), valitse **tietojen** > **yhteydet** vasemmassa siirtymisruudussa ja sitten Valitse **uusi yhteys** lähellä vasemmassa yläkulmassa.

    > [!div class="mx-imgBorder"]
    > ![Valitse tiedot > yhteyksien vasemmassa siirtymispalkissa ja vasemmassa yläkulmassa ja valitse sitten uusi yhteys.](./media/connection-sharepoint-online/new-connection.png)

1. Haku-ruutua oikeassa yläkulmassa, kirjoita tai liitä **SharePoint**, ja valitse sitten **SharePoint**.

    > [!div class="mx-imgBorder"]
    > ![Haku-ruutua oikeassa yläkulmassa Kirjoita tai liitä SharePoint ja valitse sitten SharePoint.](./media/connection-sharepoint-online/select-sharepoint.png)

1. Suorita jompikumpi joukon näistä vaiheista:

    - Jos haluat yhdistää SharePoint Onlineen, valitse **Yhdistä suoraan (pilvipalvelut)**, valitse **Luo**, ja anna sitten tunnistetiedot (pyydettäessä).

        > [!div class="mx-imgBorder"]
        > ![Jos haluat yhdistää SharePoint Onlineen, valitse Yhdistä suoraan (pilvipalvelut)](./media/connection-sharepoint-online/select-online.png)

        Yhteys on luotu, ja voit lisätä tietojen olemassa olevaan sovellukseen tai luo sovellus alusta alkaen.

    - Yhteyden muodostaminen paikalliseen-sivustoon, valitse **Yhdistä paikallisen tietoyhdyskäytävän käyttäen**.

        > [!div class="mx-imgBorder"]
        > ![Muodosta yhteys paikalliseen sivustoon valitsemalla ** Yhdistä paikallisen tietoyhdyskäytävän käyttäen)](./media/connection-sharepoint-online/select-onprem.png)

        Määritä **Windows** todennustyypiksi ja määritä sitten tunnistetietosi. (Jos tunnistetietoihisi kuuluu toimialuenimi, anna käyttäjänimi muodossa *toimialue\alias*.)

        > [!div class="mx-imgBorder"]
        > ![Määritä tunnistetiedot](./media/connection-sharepoint-online/specify-creds.png)

        Valitse **Valitse yhdyskäytävä**, valitse yhdyskäytävä, jota haluat käyttää ja valitse sitten **Luo**.

        > [!NOTE]
        > Jos sinulla ei ole asennettuna, paikallisen-tietoyhdyskäytävää [asenna sellainen](../gateway-reference.md), ja valitse sitten Päivitä päivityskuvaketta.

        > [!div class="mx-imgBorder"]
        > ![Valitse yhdyskäytävä](./media/connection-sharepoint-online/choose-gateway.png)

        Yhteys on luotu, ja voit lisätä tietojen olemassa olevaan sovellukseen tai luo sovellus alusta alkaen.

## <a name="add-data-to-an-existing-app"></a>Tietojen lisääminen olemassa oleva sovellus

1. Avaa PowerApps Studio-sovellus, jonka haluat päivittää, valitse **Näytä** välilehti ja valitse sitten **tietolähteet**.

    > [!div class="mx-imgBorder"]
    > ![Näytä-välilehti ja sitten tietolähteet](./media/connection-sharepoint-online/view-data-sources.png)

1. Tässä **tietojen** ruudussa **Lisää tietolähde** > **SharePoint**.

1. Valitse **Yhdistä SharePoint-sivustoon**, valitse merkintää **Viimeisimmät sivustot** luettelo (tai kirjoita tai liitä, jota haluat käyttää sivuston URL-osoite), ja valitse sitten **Yhdistä**.

    > [!div class="mx-imgBorder"]
    > ![Valitse sivusto](./media/connection-sharepoint-online/select-sp-site.png)

1. Valitse **Valitse luettelo**, valitse valintaruutu **asiakirjojen** tai vähintään yksi luetteloita, jota haluat käyttää ja valitse sitten **Yhdistä**:

    > [!div class="mx-imgBorder"]
    > ![Valitse luettelo Valitse tiedostot-valintaruutu tai yksi tai useampi luettelo, jota haluat käyttää ja valitse sitten Yhdistä](./media/connection-sharepoint-online/select-sp-tables.png)

    Kaikkia luettelotyyppejä ei näytetä oletuksena. PowerApps tukee mukautettuja luetteloita mutta ei mallipohjaisia luetteloita. Jos haluat käyttää luettelon nimeä ei näy, vieritä alas ja kirjoita sitten ruutuun, joka sisältää luettelon nimi **Anna mukautetun taulukkonimi**.

    > [!div class="mx-imgBorder"]
    > ![Kirjoita luettelon nimi ruutu, joka sisältää Anna mukautettu Luettelonimi.](./media/connection-sharepoint-online/custom-list.png)

    Tietolähde tai tietolähteitä lisätään sovellukseesi.

## <a name="build-your-own-app-from-scratch"></a>Luo oma sovelluksesi alusta alkaen

Ota käyttöön-käsitteitä [sovelluksen luominen alusta alkaen](../get-started-create-from-blank.md) SharePointissa Excelin sijaan.

## <a name="show-list-columns-in-a-gallery"></a>Näytä luettelon sarakkeista valikoimassa

Jos mukautettu luettelo sisältää kaikki tällaiset sarakkeet, Näytä, että tiedot **valikoiman** ohjausobjektiin kaavarivin avulla voit määrittää **tekstin** ominaisuuden yhden tai useamman **nimen** asettamiseen kyseisessä valikoimassa:

- Varten **valinta** tai **Lookup** saraketta, Määritä **ThisItem.** _ColumnName_**. Arvo** näyttämään tiedot kyseisessä sarakkeessa.

    Määritä esimerkiksi **ThisItem.Location.Value**, jos sinulla on **Valinta**-sarake, jonka nimi on **Location**, ja määritä **ThisItem.PostalCode.Value**, jos sinulla on **Haku**-sarake, jonka nimi on **PostalCode**.

- Varten **henkilö tai ryhmä** saraketta, Määritä **ThisItem.** _ColumnName_**. DisplayName** näyttämään käyttäjän tai ryhmän näyttönimi.

    Määritä esimerkiksi **ThisItem.Manager.DisplayName** näyttämään näyttönimet **Henkilö tai ryhmä** -sarakkeesta, jonka nimi on **Manager**.

    Voit myös näyttää erilaista tietoa käyttäjistä, kuten sähköpostiosoitteet tai työnimikkeet. Voit näyttää luettelon kaikista valinnoista määrittämällä **ThisItem.** _ColumnName_**.** (mukaan lukien lopussa ajan).

    > [!NOTE]
    > Varten **CreatedBy** saraketta, Määritä **ThisItem.Author.DisplayName** näyttämään luettelossa kohteita luoneiden käyttäjien näyttönimet. Jos käytät **ModifiedBy**-saraketta, määritä **ThisItem.Editor.DisplayName** näyttämään luettelon kohteita muuttaneiden käyttäjien näyttönimet.

- Varten **Managed Metadata** saraketta, Määritä **ThisItem.** _ColumnName_**. Nimen** näyttämään tiedot kyseisessä sarakkeessa.

    Määritä esimerkiksi **ThisItem.Languages.Label**, jos sinulla on **Managed Metadata** -sarake, jonka nimi on **Languages**.

## <a name="show-data-from-a-library"></a>Näytä tiedot-kirjastosta

Jos sinulla on useita kuvia SharePoint-kirjastoon, voit lisätä **avattava** ohjausobjektin sovelluksesi, jotta käyttäjät voivat määrittää kuvaa, niin näet. Voit myös tehdä samoja periaatteita myös muita ohjausobjekteja, kuten **valikoiman** ohjausobjekteja ja muita tietoja, kuten videoita.

1. Jos et ole jo, [Muodosta yhteys](#create-a-connection), ja sitten [tietojen lisääminen olemassa olevan sovelluksen](#add-data-to-an-existing-app).

1. Lisää **avattava** ohjausobjekti ja anna sille **ImageList**.

1. Määritä **kohteet** ominaisuuden **ImageList** - **asiakirjojen**.

1. Valitse **ominaisuudet** välilehti oikeanpuoleisessa ruudussa, Avaa **arvo** luettelo ja valitse sitten **nimi**.

    Kuvat kirjaston nimet näkyvät **ImageList**.

    > [!div class="mx-imgBorder"]
    > ![Luettelo](./media/connection-sharepoint-online/dropdown-items.png)

1. Lisää **kuvan** ohjausobjekti ja määritä sen **kuva** ominaisuudeksi seuraava lauseke:

    `ImageList.Selected.'Link to item'`

1. Paina F5-näppäintä ja valitse toinen arvo **ImageList**.

    Kuva, jonka määritit näkyy.

    > [!div class="mx-imgBorder"]
    > ![Mallikuva](./media/connection-sharepoint-online/golden-honey.png)

Voit myös [ladata mallisovelluksen](https://pwrappssamples.blob.core.windows.net/samples/spdoclib_blogapp.msapp) , joka esittelee, jossa tiedot SharePoint-kirjaston monimutkaisempia lähestymistapaa.

1. Kun olet ladannut sovelluksen, Avaa [PowerApps Studio](https://us.create.powerapps.com/studio/#), valitse **Avaa** vasemmassa siirtymisruudussa ja sitten Valitse **Selaa**.
1. - **Avaa** valintaikkunassa Etsi ja avaa lataamaasi tiedostoa ja lisää sitten SharePoint-kirjaston tietolähteenä noudattamalla tässä aiheessa kaksi ensimmäistä toimintosarjoja.

> [!NOTE]
> Tämä sovellus näytetään oletuksena [delegointia varoitukset](../delegation-overview.md), mutta ne voivat ohittaa, jos kirjaston sisältää alle 500 kohdetta.

Tässä sovelluksessa yhden näytön vasemmassa yläkulmassa luettelossa kirjaston kaikki tiedostot.

- Voit hakea tiedoston kirjoittamalla tai liittämällä yksi tai useamman merkin hakukenttään oikean lähellä ylös.
- Jos kirjaston sisältää kansioita, voit suodattaa tiedostojen luettelo valitsemalla suodatinkuvake otsikkorivin alapuolella kansioiden luettelo.

Kun löydät haluamaasi tiedostoa, valitse se näyttää sen **videon**, **kuvan**, tai **ääni** ohjausobjektin oikeassa reunassa.

> [!div class="mx-imgBorder"]
> ![Mallikuva](./media/connection-sharepoint-online/library-app.png)

## <a name="known-issues"></a>Tunnetut ongelmat

### <a name="lists"></a>Luettelo

PowerApps voi lukea sarakkeiden nimet, jotka sisältävät välilyöntejä, mutta välilyönnit korvataan heksadesimaalikoodilla **”\_x0020\_”**. Esimerkiksi **Sarakkeen nimi** SharePointissa näkyy muodossa **Sarakkeen_x0020_Nimi** PowerAppsissa, kun se näytetään tietoasettelussa tai sitä käytetään kaavassa.

Kaikentyyppiset sarakkeet eivät ole tuettuja, ja kaikentyyppiset sarakkeet tue kaikentyyppisiä kortteja.

| Saraketyyppi | Tuki | Oletuskortit |
| --- | --- | --- |
| Yksi tekstirivi |Kyllä |Näytä teksti |
| Useita tekstirivejä |Kyllä |Näytä teksti |
| Valinta |Kyllä |Näytä haku<br>Muokkaa hakua<br>Näytä monivalinta<br>Muokkaa monivalintaa |
| Luku |Kyllä |Näytä prosenttiosuus<br>Näytä luokitus<br>Näytä teksti |
| Valuutta |Kyllä |Näytä prosenttiosuus<br>Näytä luokitus<br>Näytä teksti |
| Päivämäärä ja aika |Kyllä |Näytä teksti |
| Haku |Kyllä |Näytä haku<br>Muokkaa hakua<br>Näytä monivalinta<br>Muokkaa monivalintaa |
| Totuusarvo (kyllä/ei) |Kyllä |Näytä teksti<br>Näkymän vaihto |
| Henkilö tai ryhmä |Kyllä |Näytä haku<br>Muokkaa hakua<br>Näytä monivalinta<br>Muokkaa monivalintaa |
| Hyperlinkki |Kyllä |Näytä URL-osoite<br>Näytä teksti |
| Kuva |Kyllä (vain luku) |Näytä kuva<br>Näytä teksti |
| Liite |Kyllä (vain luku) |Näytä liitteet|
| Laskettu |Kyllä (vain luku) | |
| Tehtävän tulos |Ei | |
| Ulkoiset tiedot |Ei | |
| Hallitut metatiedot |Kyllä (vain luku) | |
| Luokitus |Ei | |

### <a name="libraries"></a>Kirjastot

- Powerappsista tiedostoja kirjastoon ei voi ladata.
- Kirjastosta PDF-tiedostoja ei voi näyttää PDF-katseluohjelman ohjausobjektissa.
- PowerApps Mobilessa ei tue **Lataa** funktio.
- Jos käyttäjäsi sovellusta PowerApps Mobilessa tai Windows 10-sovellukseen, käytä **Käynnistä** funktio, joka näyttää kirjaston sisältöä valikoimassa.

## <a name="next-steps"></a>Seuraavat vaiheet

- Opi [näyttämään tietolähteen tietoja](../add-gallery.md).
- Opi [tarkastelemaan tietoja ja luomaan tai päivittämään tietueita](../add-form.md).
- Tutustu muuntyyppisiin [tietolähteisiin](../connections-list.md), joihin voit muodostaa yhteyden.

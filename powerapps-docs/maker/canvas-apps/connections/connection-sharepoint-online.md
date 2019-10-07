---
title: SharePoint-yhteyden yleiskatsaus | Microsoft Docs
description: Näytä SharePointin käytettävissä olevat Funktiot, vasta ukset ja esimerkit.
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/03/2019
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ae82166b9cc21de1e25f99f7606ce7b95b2152b9
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993954"
---
# <a name="connect-to-sharepoint-from-a-canvas-app"></a>Muodosta yhteys SharePointiin pohjaan sovelluksena

![SharePoint](./media/connection-sharepoint-online/sharepointicon.png)

Muodosta yhteys SharePoint-sivustoon, jotta voit luoda sovelluksen automaattisesti mukautetusta listasta tai luoda yhteyden, ennen kuin lisäät tietoja olemassa olevaan sovellukseen tai rakennat sovelluksen alusta alkaen.

Sen mukaan, missä tiedot ovat, voit käyttää jompaakumpaa seuraavista menetelmistä:

- Näytä tiedot SharePoint Online-sivuston tai paikallisen sivuston mukautetusta listasta.
- Näytä kuvia ja toista video-tai ääni tiedostoja kirjastossa (vain SharePoint Online).

## <a name="generate-an-app"></a>Luo sovellus

Jos haluat hallita mukautetun listan tietoja, PowerApps voi [luoda automaattisesti kolmen näytön sovelluksen](../app-from-sharepoint.md). Käyttäjät voivat selata luettelon ensimmäisessä näytössä, näyttää kohteen tiedot toisessa näytössä ja luoda tai päivittää kohteita kolmannessa näytössä.

> [!NOTE]
> Jos SharePoint-luettelosi sisältää **valinta**-, **haku**-tai **henkilö-tai ryhmä** -sarakkeen, Katso kohta [Näytä tiedot valikoimassa](connection-sharepoint-online.md#show-list-columns-in-a-gallery) myöhemmin tässä ohje aiheessa.

## <a name="create-a-connection"></a>Luo yhteys

1. [Kirjaudu sisään Powerappsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), valitse vasemmasta siirtymis palkista **tiedot** > -**yhteydet** ja valitse sitten **Uusi yhteys** lähellä vasenta yläkulmaa.

    > [!div class="mx-imgBorder"]
    > ![Valitse tiedot > yhteydet vasemmasta siirtymis palkista ja valitse sitten uusi yhteys vasemman yläkulman lähellä. ](./media/connection-sharepoint-online/new-connection.png)

1. Kirjoita tai liitä **SharePoint**-ruutuun lähellä oikeaa yläkulmaa olevaa haku ruutua ja valitse sitten **SharePoint**.

    > [!div class="mx-imgBorder"]
    > ![Kirjoita haku ruutuun lähellä oikeaa yläkulmaa, kirjoita tai liitä SharePoint ja valitse sitten SharePoint. ](./media/connection-sharepoint-online/select-sharepoint.png)

1. Suorita jompikumpi seuraavista vaihe joukoista:

    - Jos haluat muodostaa yhteyden SharePoint Onlineen, valitse **Yhdistä suoraan (pilvi palvelut)** , valitse **Luo**ja Anna tunniste tiedot (pyydettäessä).

        > [!div class="mx-imgBorder"]
        > ![Jos haluat muodostaa yhteyden SharePoint Onlineen, valitse Yhdistä suoraan (pilvi palvelut) ](./media/connection-sharepoint-online/select-online.png)

        Yhteyden luominen on mahdollista, ja voit lisätä tietoja olemassa olevaan sovellukseen tai luoda sovelluksen alusta alkaen.

    - Jos haluat muodostaa yhteyden paikalliseen sivustoon, valitse **Yhdistä käyttäen paikallista tietoyhdyskäytävää**.

        > [!div class="mx-imgBorder"]
        > ![Jos haluat muodostaa yhteyden paikalliseen sivustoon, valitse * * Yhdistä käyttäen paikallista tietoyhdyskäytävää) ](./media/connection-sharepoint-online/select-onprem.png)

        Määritä **Windows** todennustyypiksi ja määritä sitten tunnistetietosi. (Jos tunnistetietoihisi kuuluu toimialuenimi, anna käyttäjänimi muodossa *toimialue\alias*.)

        > [!div class="mx-imgBorder"]
        > ![Määritä tunniste tiedot @ no__t-1

        Valitse **Valitse yhdyskäytävä**-kohdassa yhdyskäytävä, jota haluat käyttää, ja valitse sitten **Luo**.

        > [!NOTE]
        > Jos sinulla ei ole asennettuna paikallista tietoyhdyskäytävää, [Asenna sellainen](../gateway-reference.md)ja päivitä sitten yhdyskäytävien luettelo valitsemalla kuvake.

        > [!div class="mx-imgBorder"]
        > ![Valitse yhdyskäytävä @ no__t-1

        Yhteyden luominen on mahdollista, ja voit lisätä tietoja olemassa olevaan sovellukseen tai luoda sovelluksen alusta alkaen.

## <a name="add-data-to-an-existing-app"></a>Tietojen lisääminen olemassa olevaan sovellukseen

1. Avaa PowerApps Studio sovellus, jonka haluat päivittää, valitse **näkymä** -väli lehti ja valitse sitten **tieto lähteet**.

    > [!div class="mx-imgBorder"]
    > ![Näytä-väli lehdestä ja valitse sitten tieto lähteet @ no__t-1

1. Valitse **tiedot** -ruudussa **lisää tieto lähde** > **SharePoint**.

1. Valitse **Yhdistä SharePoint-sivustoon**-kohdassa **viimeisimmät sivustot** -luettelosta (tai kirjoita tai liitä sen sivuston URL-osoite, jota haluat käyttää) ja valitse sitten **Yhdistä**.

    > [!div class="mx-imgBorder"]
    > ![Valitse sivusto @ no__t-1

1. Valitse **Valitse luettelo**-kohdassa **asia kirjojen** valinta ruutu tai vähintään yksi luettelo, jota haluat käyttää, ja valitse sitten **Yhdistä**:

    > [!div class="mx-imgBorder"]
    > ![Valitse Valitse luettelo, valitse niiden asia kirjojen valinta ruutu tai vähintään yksi luettelo, jota haluat käyttää, ja valitse sitten Yhdistä @ no__t-1

    Kaikkia luettelotyyppejä ei näytetä oletuksena. PowerApps tukee mukautettuja luetteloita mutta ei mallipohjaisia luetteloita. Jos haluamaasi luettelon nimeä ei näy, vieritä alas ja kirjoita luettelon nimi ruutuun, joka sisältää **Anna mukautetun taulukon nimi**.

    > [!div class="mx-imgBorder"]
    > ![Kirjoita luettelon nimi ruutuun, joka sisältää Anna mukautettu luettelon nimi. ](./media/connection-sharepoint-online/custom-list.png)

    Tieto lähde tai lähteet lisätään sovellukseesi.

## <a name="build-your-own-app-from-scratch"></a>Luo oma sovelluksesi alusta alkaen

Käytä käsitteitä [Luo sovellus tyhjästä](../get-started-create-from-blank.md) SharePointiin Excelin sijaan.

## <a name="show-list-columns-in-a-gallery"></a>Näytä luetteloiden sarakkeet valikoimassa

Jos mukautettu luettelosi sisältää minkä tahansa näistä sarakkeista, Näytä tiedot **valikoima** -ohjaus objektissa käyttämällä kaava riviä, jos haluat määrittää yhden tai useamman **Selite** ohjaus objektin **Text** -ominaisuuden kyseisessä valikoimassa:

- Jos kyseessä on **valinta** -tai **haku** sarake, Määritä **thisitem.** _ColumnName_ **. Arvo** , joka näyttää kyseisen sarakkeen tiedot.

    Määritä esimerkiksi **ThisItem.Location.Value**, jos sinulla on **Valinta**-sarake, jonka nimi on **Location**, ja määritä **ThisItem.PostalCode.Value**, jos sinulla on **Haku**-sarake, jonka nimi on **PostalCode**.

- Määritä **henkilön tai ryhmän** sarakkeelle **thisitem.** _ColumnName_ **. DisplayName** , joka näyttää käyttäjän tai ryhmän näyttö nimen.

    Määritä esimerkiksi **ThisItem.Manager.DisplayName** näyttämään näyttönimet **Henkilö tai ryhmä** -sarakkeesta, jonka nimi on **Manager**.

    Voit myös näyttää erilaista tietoa käyttäjistä, kuten sähköpostiosoitteet tai työnimikkeet. Jos haluat nähdä täydellisen luettelon vaihto ehdoista, Määritä **thisitem.** _ColumnName_ **.** (mukaan lukien lopussa oleva piste).

    > [!NOTE]
    > Jos kyseessä on **createdby** -sarake, Määritä **Thisitem. Author. DisplayName** näyttämään luettelon kohteiden luomien käyttäjien näyttö nimet. Jos käytät **ModifiedBy**-saraketta, määritä **ThisItem.Editor.DisplayName** näyttämään luettelon kohteita muuttaneiden käyttäjien näyttönimet.

- Määritä **Hallittujen metatietojen** sarakkeelle **thisitem.** _ColumnName_ **. Otsikko** , joka näyttää kyseisen sarakkeen tiedot.

    Määritä esimerkiksi **ThisItem.Languages.Label**, jos sinulla on **Managed Metadata** -sarake, jonka nimi on **Languages**.

## <a name="show-data-from-a-library"></a>Näytä tiedot kirjastosta

Jos sinulla on useita kuvia SharePoint-kirjastossa, voit lisätä sovellukseen **avattavan** luettelo-ohjaus objektin, jotta käyttäjät voivat määrittää, mikä kuva näytetään. Voit myös käyttää samoja periaatteita muihin ohjaus objekteihin, kuten **valikoima** -ohjaus objekteihin, ja muuntyyppisiin tietoihin, kuten videoihin.

1. Jos et ole vielä [luonut yhteyksiä, luo se](#create-a-connection)ja [Lisää sitten tietoja olemassa olevaan sovellukseen](#add-data-to-an-existing-app).

1. Lisää **avattava luettelo** -ohjaus objekti ja nimeä se **ImageList**-luettelo.

1. Valitse **ImageList** -luettelon **Items** -ominaisuudeksi **asia kirjat**.

1. Avaa oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdellä **arvo** -luettelo ja valitse sitten **nimi**.

    Kirjastossasi olevien kuvien tiedosto nimet näkyvät **ImageList**-luettelossa.

    > [!div class="mx-imgBorder"]
    > ![Luettelon kuvista @ no__t-1

1. Lisää **kuva** -ohjaus objekti ja määrittää sen **kuva** -ominaisuudeksi tämä lauseke:

    `ImageList.Selected.'Link to item'`

1. Paina F5-näppäintä ja valitse sitten eri arvo **ImageList**-luettelosta.

    Määrittämäsi kuva tulee näkyviin.

    > [!div class="mx-imgBorder"]
    > ![Esimerkki kuva @ no__t-1

Voit [ladata malli sovelluksen](https://pwrappssamples.blob.core.windows.net/samples/spdoclib_blogapp.msapp) , joka näyttää monitasoisemman tavan näyttää tietoja SharePoint-kirjastosta.

1. Kun olet ladannut sovelluksen, avaa [PowerApps Studio](https://us.create.powerapps.com/studio/#), valitse **Avaa** vasemmassa siirtymis palkissa ja valitse sitten **Selaa**.
1. Etsi ja avaa lataamasi tiedosto **Avaa** -valinta ikkunassa ja lisää sitten SharePoint-Kirjasto tieto lähteeksi noudattamalla tämän ohje aiheen kahta ensimmäistä toiminto sarjan kohtaa.

> [!NOTE]
> Oletus arvon mukaan tämä sovellus sisältää [delegointi varoitukset](../delegation-overview.md), mutta voit ohittaa ne, jos kirjastossasi on alle 500 kohdetta.

Tässä yksisuuntaisessa sovelluksessa vasemmassa alakulmassa olevassa luettelossa näytetään kaikki kirjastossasi olevat tiedostot.

- Voit hakea tiedostoa kirjoittamalla tai liittämällä yhden tai useamman merkin yläosassa olevaan haku ruutuun.
- Jos kirjastossasi on kansioita, voit suodattaa tiedosto luettelon valitsemalla suodatin kuvakkeen vain otsikko rivin alla olevasta kansio luettelossa.

Kun löydät haluamasi tiedoston, valitse se, niin näet sen **video**-, **kuva**-tai **ääni** -ohjaus objektissa oikealla puolella.

> [!div class="mx-imgBorder"]
> ![Esimerkki kuva @ no__t-1

## <a name="known-issues"></a>Tunnetut ongelmat

### <a name="lists"></a>Luettelot

PowerApps voi lukea välejä sisältäviä sarakkeiden nimiä, mutta väli lyönnit korvataan heksa desimaali koodilla **"\_x0020 @ no__t-2"** . Esimerkiksi **Sarakkeen nimi** SharePointissa näkyy muodossa **Sarakkeen_x0020_Nimi** PowerAppsissa, kun se näytetään tietoasettelussa tai sitä käytetään kaavassa.

Kaikkia sarake tyyppejä ei tueta, eivätkä kaikki sarakkeet tue kaikentyyppisiä kortteja.

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

- Et voi ladata tiedostoja Powerappsin kirjastosta kirjastoon.
- PDF-tiedostoja ei voi näyttää kirjastosta PDF-katselu ohjelman ohjaus objektissa.
- PowerApps Mobile ei tue **lataamis** tehtävää.
- Jos käyttäjät suorittavat sovelluksen PowerApps Mobilessa tai Windows 10-sovelluksessa, Näytä Kirjasto sisältö valikoimassa **Launch** -funktiolla.

## <a name="next-steps"></a>Seuraavat vaiheet

- Opi [näyttämään tietolähteen tietoja](../add-gallery.md).
- Opi [tarkastelemaan tietoja ja luomaan tai päivittämään tietueita](../add-form.md).
- Tutustu muuntyyppisiin [tietolähteisiin](../connections-list.md), joihin voit muodostaa yhteyden.

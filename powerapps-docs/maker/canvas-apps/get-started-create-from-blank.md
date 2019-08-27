---
title: Pohjaan perustuvan sovelluksen luominen alusta alkaen Excel-tietojen perusteella | Microsoft Docs
description: Tässä opetusohjelmassa luot kahden näytön pohjaan perustuvan sovelluksen, jotta käyttäjät voivat luoda, muokata ja poistaa tietueita Excel-tiedostossa.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/26/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c66277cbd0d0ded3bfe0bee942e9160a650d2a98
ms.sourcegitcommit: 6dea3559e012e56fde09b95ea8a2af2a81b89a91
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/23/2019
ms.locfileid: "70000091"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-a-canvas-app-from-scratch-based-on-excel-data"></a>Pohjaan perustuvan sovelluksen luominen alusta alkaen Excel-tietojen perusteella

Voit luoda oman, taulukoksi muotoillun pohjaan perustuvan sovelluksesi alusta alkaen Excel-tietojen perusteella ja lisätä sitten halutessasi tietoja muista lähteistä. Tässä opetusohjelmassa luodaan sovellus, joka sisältää kaksi näyttöä. Yhdessä näytössä käyttäjät voivat selata tietuejoukkoa. Toisessa näytössä käyttäjät voivat luoda tietueen, päivittää vähintään tietueen yhden kentän tai poistaa koko tietueen. Tämä menetelmä vie enemmän aikaa kuin [sovelluksen muodostaminen automaattisesti](get-started-create-from-data.md), mutta kokeneet käyttäjät voivat näin tehdä parhaiten tarpeitaan vastaavan sovelluksen.

## <a name="prerequisites"></a>Edellytykset

Noudata tämän opetusohjelman ohjeita tarkasti luomalla ensin Excel-tiedosto, jossa on nämä mallitiedot.

1. Kopioi nämä tiedot ja liitä ne Excel-tiedostoon.

    | StartDay | StartTime | Vapaaehtoinen | Varmuus kopiointi |
    | --- | --- | --- | --- |
    | Lauantai |Klo 10–12 |Vasquez |Kumashiro |
    | Lauantai |Klo 12–14 |Ice |Singhal |
    | Lauantai |Klo 14–16 |Myk |Mueller |
    | Sunnuntai |Klo 10–12 |Li |Adams |
    | Sunnuntai | Klo 12–14 |Singh |Morgan |
    | Sunnuntai | Klo 14–16 |Batye |Nguyen |

2. Muotoile tiedot taulukoksi nimeltä **Schedule**, jotta PowerApps voi jäsentää tiedot.

    Lisätietoja on artikkelissa [Excel-taulukon muotoileminen](how-to-excel-tips.md).

3. Tallenna tiedosto nimellä **eventsignup. xlsx**, sulje se ja lataa se sitten [pilvi tallennus tilille](connections/cloud-storage-blob-connections.md), kuten OneDriveen.

> [!IMPORTANT]
> Voit käyttää omaa Excel-tiedostoasi ja katsoa opetusohjelmasta vain yleiset käsitteet. Excel-tiedoston tietojen täytyy kuitenkin olla taulukkomuodossa. Lisätietoja on artikkelissa [Excel-taulukon muotoileminen](how-to-excel-tips.md).

## <a name="open-a-blank-app"></a>Avaa tyhjä sovellus

1. Kirjaudu sisään [PowerAppsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Valitse **Tee oma sovelluksesi** -kohdasta vaihtoehto **Pohjan sovellus tyhjästä**.

    > [!div class="mx-imgBorder"]
    >![Luo tyhjä pohjaan perustuva sovellus](./media/get-started-create-from-blank/blank-app.png)

1. Määritä sovelluksesi nimi, valitse **Puhelin** ja valitse sitten **Luo**.

    Voit suunnitella sovelluksen alusta alkaen puhelimia tai muita laitteita (kuten tabletteja) varten. Tässä artikkelissa keskitytään sovelluksen suunnittelemiseen puhelinta varten.

    > [!div class="mx-imgBorder"]
    >![Määritä sovelluksen nimi ja muoto](./media/get-started-create-from-blank/excel-demo.png)

    PowerApps Studio luo tyhjän sovelluksen puhelimia varten.

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

## <a name="connect-to-data"></a>Yhdistä tietoihin

1. Valitse näytön keskellä **Yhdistä tietoihin**.

1. Valitse **Tiedot**-ruudussa pilvitallennustilisi yhteys, jos se on näkyvissä. Muutoin lisää yhteys seuraavasti:

    1. Valitse **Uusi yhteys**, valitse tilisi pilvitallennustilaruutu ja valitse sitten **Luo**.
    2. Anna tilin tunnistetietosi, jos niitä pyydetään.

1. Valitse **Valitse Excel-tiedosto**, kirjoita tai liitä ensimmäiset kirjaimet sanasta **eventsignup** luettelon suodattamista varten ja valitse sitten lataamasi tiedosto.

1. Valitse **Valitse taulukko**, valitse **Aikataulu**-valintaruutu ja valitse sitten **Yhdistä**.

1. Sulje **Tiedot**-ruutu valitsemalla oikean yläkulman sulkemiskuvake (X).

## <a name="create-the-view-screen"></a>Tarkastelunäytön luominen

1. Valitse **Aloitus**-välilehdessä kohdan **Uusi näyttö** vieressä oleva alanuoli, jolloin näyttötyyppien luettelo avautuu, ja valitse sitten **Luettelo**.

    Kun näyttö lisätään, siinä on useita oletusohjausobjekteja, kuten hakukenttä ja **[Valikoima](controls/control-gallery.md)** -ohjausobjekti. Valikoima kattaa koko näytön hakukentän alapuolella.

1. Valitse uuden näytön yläreunassa **[Selite](controls/control-text-box.md)** -ohjausobjekti ja korvaa sitten **[Otsikko]** asetuksella **Näytä tietueet**.

     ![Muuta otsikkoriviä](./media/get-started-create-from-blank/change-title-bar.png)

1. Valitse vasemmassa siirtymispalkissa **BrowseGallery1**.

    Valikoiman ympärillä näkyy valintakehys kahvoineen.

    ![Luettelonäytön lisääminen](./media/get-started-create-from-blank/select-gallery.png)

1. Valitse oikeanpuoleisen ruudun **Ominaisuudet**-välilehdessä **Asettelu**-valikon alanuoli.

    ![Avaa asetteluvalikko](./media/get-started-create-from-blank/select-layout.png)

1. Valitse **Otsikko, alaotsikko ja leipäteksti**.

1. Korvaa kaavarivillä **CustomGallerySample**-kohta tekstillä **Schedule** ja korvaa molemmat **SampleText**-kohdat tekstillä **Volunteer**.

1. Valitse kaavarivin oikeassa reunassa oleva alaspäin osoittava nuoli ja valitse sitten **Muotoile teksti**.

    Kaava vastaa tätä esimerkkiä:

    ```powerapps-comma
    SortByColumns(
        Search(
            Schedule;
            TextSearchBox1.Text;
            "Volunteer"
        );
        "Volunteer";
        If(
            SortDescending1;
            SortOrder.Descending;
            SortOrder.Ascending
        )
    )
    ```

1. Valitse oikeanpuoleisen ruudun **Ominaisuudet**-välilehdessä **Kentät**-otsikon vierestä **Muokkaa**.

1. Valitse **Title2** -ruudussa **vapaaehtoinen**, valitse **Subtitle2** -ruudussa Startday jaValitse **Body1** -ruudusta **StartTime**.

1. Sulje **Tiedot**-ruutu valitsemalla oikean yläkulman sulkemiskuvake (X).

Käyttäjät voivat lajitella ja suodattaa valikoiman vapaaehtoisen nimen mukaan kyseisen kaavan **SortByColumns**- ja **Search**-funktioiden perusteella.

- Jos käyttäjä kirjoittaa ainakin yhden kirjaimen hakukenttään, valikoimassa näytetään vain tietueet, joissa **Vapaaehtoinen**-kenttä sisältää käyttäjän antaman tekstin.
- Jos käyttäjä valitsee lajittelupainikkeen (otsikkorivillä päivityspainikkeen ja plus-painikkeen välissä), tietueet näkyvät valikoimassa nousevassa tai laskevassa järjestyksessä (sen mukaan, kuinka monta kertaa käyttäjä valitsee painikkeen) **Vapaaehtoinen**-kentän perusteella.

Lisätietoja näistä ja muista funktioista on artikkelissa [Lisätietoja kaavasta](formula-reference.md).

## <a name="create-the-change-screen"></a>Muutosnäytön luominen

1. Valitse **Aloitus**-välilehdessä **Uusi näyttö** -kohdan vieressä oleva alanuoli ja valitse sitten **Lomake**.

1. Valitse vasemmassa siirtymispalkissa **EditForm1**.

1. Valitse oikeanpuoleisen ruudun **Ominaisuudet**-välilehdessä **Tietolähde**-kohdan vieressä oleva alanuoli ja valitse sitten esiin tulevassa luettelossa **Aikataulu**.

1. Valitse juuri määrittämäsi tietolähteen kohdalla **Muokkaa kenttiä**.

1. Valitse **Kentät**-ruudussa **Lisää kenttä**, valitse kunkin kentän valintaruutu ja valitse sitten **Lisää**.

1. Tiivistä kentät valitsemalla kunkin kentän nimen vieressä oleva nuoli ja vedä sitten **Vapaaehtoinen**-kenttää ylöspäin niin, että se näkyy ylimpänä kenttäluettelossa.

     ![Kenttien järjestäminen uudelleen](./media/get-started-create-from-blank/reorder-fields.png)

1. Sulje **Kentät**-ruutu valitsemalla oikean yläkulman sulkemiskuvake (X).

1. Määritä lomakkeen **Item**-ominaisuudeksi tämä lauseke kirjoittamalla tai liittämällä se kaavariville:

    `BrowseGallery1.Selected`

1. Valitse näytön yläreunassa **[Selite](controls/control-text-box.md)** -ohjausobjekti ja korvaa sitten **[Otsikko]** asetuksella **Vaihda tietueet**.

    ![Muuta otsikkoriviä](./media/get-started-create-from-blank/change-title-bar2.png)

## <a name="delete-and-rename-screens"></a>Näyttöjen poistaminen ja uudelleennimeäminen

1. Valitse vasemmassa siirtymispalkissa kolme pistettä (...) kohdassa **Näyttö1** ja valitse sitten **Poista**.

    ![Näytön poistaminen](./media/get-started-create-from-blank/delete-screen.png)

1. Valitse kolme pistettä (...) kohdassa **Näyttö2**, valitse **Nimeä uudelleen** ja kirjoita tai liitä sitten **ViewScreen**.

1. Valitse kolme pistettä (...) kohdassa **Näyttö3**, valitse **Nimeä uudelleen** ja kirjoita tai liitä sitten **ChangeScreen**.

## <a name="configure-icons-on-the-view-screen"></a>Tarkastelunäytön kuvakkeiden määrittäminen

1. Valitse **ViewScreen**-näytön yläreunassa pyöreä nuoli -kuvake.

    ![Tietueen lisääminen](./media/get-started-create-from-blank/refresh-icon.png)

1. Määritä kyseisen kuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:

    `Refresh(Schedule)`

    Kun käyttäjä valitsee tämän kuvakkeen, tietoja **Schedule**-arvo päivitetään Excel-tiedostosta.

    Lisätietoja näistä ja muista funktioista on artikkelissa [Lisätietoja kaavasta](formula-reference.md).

1. Valitse plus-kuvake **ViewScreen**-näytön oikeassa yläkulmassa.

    ![Tietueen lisääminen](./media/get-started-create-from-blank/add-record.png)

1. Määritä kyseisen kuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:

    `NewForm(EditForm1);;Navigate(ChangeScreen;ScreenTransition.None)`

    Kun käyttäjä valitsee tämän kuvakkeen, **ChangeScreen** näytetään kaikki kentät tyhjänä, jotta käyttäjä voi luoda tietueen helpommin.

1. Valitse oikealle osoittava nuoli valikoiman ensimmäisessä tietueessa.

    ![Nuolen valitseminen](./media/get-started-create-from-blank/select-arrow.png)

1. Määritä nuolen **OnSelect**-ominaisuudeksi tämä kaava:

    `EditForm(EditForm1);; Navigate(ChangeScreen; ScreenTransition.None)`

    Kun käyttäjä valitsee tämän kuvakkeen, **ChangeScreen** näytetään niin, että jokaisessa kentässä näkyvät valitun tietueen tiedot, jotta käyttäjä voi luoda tietueen tai muokata sitä helpommin.

## <a name="configure-icons-on-the-change-screen"></a>Muutosnäytön kuvakkeiden määrittäminen

1. Valitse **ChangeScreen**-näytössä vasemman yläkulman X-kuvake.

    ![Peruutuskuvake](./media/get-started-create-from-blank/cancel-icon.png)

1. Määritä kyseisen kuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:

    `ResetForm(EditForm1);;Navigate(ViewScreen; ScreenTransition.None)`

    Kun käyttäjä valitsee tämän kuvakkeen, kaikki käyttäjän tässä näytössä tekemät muutokset hylätään, ja tarkastelunäyttö avautuu.

1. Valitse valintamerkkikuvake oikeassa yläkulmassa.

    ![Valintamerkkikuvake](./media/get-started-create-from-blank/checkmark-icon.png)

1. Määritä valintamerkin **OnSelect**-ominaisuudeksi tämä kaava:

    `SubmitForm(EditForm1);; Navigate(ViewScreen; ScreenTransition.None)`

    Kun käyttäjä valitsee tämän kuvakkeen, kaikki käyttäjän tässä näytössä tekemät muutokset tallennetaan, ja tarkastelunäyttö avautuu.

1. Valitse **Lisää**-välilehdessä **Kuvakkeet** ja valitse sitten **Roskakori**-kuvake.

1. Määritä uuden kuvakkeen **Väri**-ominaisuuden arvoksi **Valkoinen** ja siirrä uusi kuvake valintamerkkikuvakkeen viereen.

    ![Roskakorikuvake](./media/get-started-create-from-blank/trash-icon.png)

1. Määritä roskakorikuvakkeen **Visible**-ominaisuudeksi tämä kaava:

    `EditForm1.Mode = FormMode.Edit`

    Tämä kuvake näkyy vain, kun lomake on **Muokkaa**-tilassa, ei **Uusi**-tilassa.

1. Määritä roskakorikuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:

    `Remove(Schedule; BrowseGallery1.Selected);; Navigate(ViewScreen; ScreenTransition.None)`

    Kun käyttäjä valitsee tämän kuvakkeen, valittu tietue poistetaan tietolähteestä ja tarkastelunäyttö avautuu.

## <a name="test-the-app"></a>Sovelluksen testaus

1. Valitse **ViewScreen**-näyttö ja avaa sitten esikatselu painamalla F5-näppäintä (tai valitsemalla oikean yläkulman **Esikatselu**-kuvake).

    ![Esikatselutilan avaaminen](./media/get-started-create-from-blank/open-preview.png)

1. Kirjoita tai liitä hakukenttään yksi tai useampi kirjain, niin voit suodattaa luetteloa vapaaehtoisen nimen perusteella.

1. Valitse lajittelukuvake kerran tai useammin, niin saat tiedot näkyviin nousevassa tai laskevassa järjestyksessä vapaaehtoisen nimen mukaan.

1. Lisää tietue.

1. Päivitä lisäämäsi tietue ja tallenna sitten muutokset.

1. Päivitä lisäämäsi tietue ja peruuta sitten muutokset.

1. Poista lisäämäsi tietue.

1. Sulje esikatselutila painamalla Esc-näppäintä (tai valitsemalla sulkemiskuvake oikeassa yläkulmassa).

## <a name="next-steps"></a>Seuraavat vaiheet

- Tallenna sovelluksesi pilveen painamalla Ctrl+S, jotta voit suorittaa sen muissa laitteissa.
- [Jaa sovellus](share-app.md), jotta muut voivat suorittaa sen.
- Lue lisätietoja [funktioista](working-with-formulas.md), kuten **Patch**, joiden avulla voit hallita tietoja luomatta vakiolomaketta.
- [Linkitä tämä sovellus ratkaisuun](add-app-solution.md), jotta voit esimerkiksi ottaa sen käyttöön toisessa ympäristössä tai julkaista sen AppSourceen.

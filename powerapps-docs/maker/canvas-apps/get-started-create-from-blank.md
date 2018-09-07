---
title: Pohjaan perustuvan sovelluksen luominen alusta alkaen Excel-tietojen perusteella | Microsoft Docs
description: Tässä opetusohjelmassa luot kahden näytön pohjaan perustuvan sovelluksen, jotta käyttäjät voivat luoda, muokata ja poistaa tietueita Excel-tiedostossa.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 04/23/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a1ee0b02465853306881ca4379182aef42bffd84
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833535"
---
# <a name="create-an-canvas-app-from-scratch-based-on-excel-data"></a>Pohjaan perustuvan sovelluksen luominen alusta alkaen Excel-tietojen perusteella

Voit luoda oman, taulukoksi muotoillun pohjaan perustuvan sovelluksesi alusta alkaen Excel-tietojen perusteella ja lisätä sitten halutessasi tietoja muista lähteistä. Tässä opetusohjelmassa luodaan sovellus, joka sisältää kaksi näyttöä. Yhdessä näytössä käyttäjät voivat selata tietuejoukkoa. Toisessa näytössä käyttäjät voivat luoda tietueen, päivittää vähintään tietueen yhden kentän tai poistaa koko tietueen. Tämä menetelmä vie enemmän aikaa kuin [sovelluksen muodostaminen automaattisesti](get-started-create-from-data.md), mutta kokeneet käyttäjät voivat näin tehdä parhaiten tarpeitaan vastaavan sovelluksen.

## <a name="prerequisites"></a>Edellytykset

Noudata tämän opetusohjelman ohjeita tarkasti luomalla ensin Excel-tiedosto, jossa on nämä mallitiedot.

1. Kopioi nämä tiedot ja liitä ne Excel-tiedostoon.

    | StartDay | StartTime | Vapaaehtoinen | Varmuuskopiointi |
    | --- | --- | --- | --- |
    | Lauantai |Klo 10–12 |Vasquez |Kumashiro |
    | Lauantai |Klo 12–14 |Ice |Singhal |
    | Lauantai |Klo 14–16 |Myk |Mueller |
    | Sunnuntai |Klo 10–12 |Li |Adams |
    | Sunnuntai |Klo 10–12 |Singh |Morgan |
    | Sunnuntai |Klo 10–12 |Batye |Nguyen |

2. Muotoile tiedot taulukoksi nimeltä **Schedule**, jotta PowerApps voi jäsentää tiedot.

    Lisätietoja on artikkelissa [Excel-taulukon muotoileminen](how-to-excel-tips.md).

3. Tallenna tiedosto nimellä **eventsignup.xls**, sulje se ja lataa se sitten [pilvitallennustilille](connections/cloud-storage-blob-connections.md), kuten OneDriveen.

> [!IMPORTANT]
> Voit käyttää omaa Excel-tiedostoasi ja katsoa opetusohjelmasta vain yleiset käsitteet. Excel-tiedoston tietojen täytyy kuitenkin olla taulukkomuodossa. Lisätietoja on artikkelissa [Excel-taulukon muotoileminen](how-to-excel-tips.md).

## <a name="open-a-blank-app"></a>Avaa tyhjä sovellus
1. Kirjaudu sisään [PowerAppsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    ![PowerAppsin aloitussivu](./media/get-started-create-from-blank/sign-in.png)

    Voit suunnitella sovelluksen alusta alkaen puhelimia tai muita laitteita (kuten tabletteja) varten. Tässä artikkelissa keskitytään sovelluksen suunnittelemiseen puhelinta varten.

1. Vie **Tee tämän kaltaisia sovelluksia** -kohdassa hiiren osoitin **Aloita tyhjästä** -ruudun kohdalle, valitse puhelinkuvake ja sitten valitse sitten **Tee tämä sovellus**.

    ![Tyhjän sovelluksen ruutu](./media/get-started-create-from-blank/blank-app.png)

    PowerApps Studio luo tyhjän sovelluksen puhelimia varten.

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

## <a name="connect-to-data"></a>Yhdistä tietoihin
1. Valitse näytön keskellä **Yhdistä tietoihin**.

1. Valitse **Tiedot**-ruudussa pilvitallennustilisi yhteys, jos se on näkyvissä. Muutoin lisää yhteys seuraavasti:

    1. Valitse **Uusi yhteys**, valitse tilisi pilvitallennustilaruutu ja valitse sitten **Luo**.
    2. Anna tilin tunnistetietosi, jos niitä pyydetään.

1. Valitse **Valitse Excel-tiedosto**, kirjoita tai liitä ensimmäiset kirjaimet sanasta **eventsignup** luettelon suodattamista varten ja valitse sitten lataamasi tiedosto.

1. Valitse **Valitse taulukko**, valitse **Aikataulu**-valintaruutu ja valitse sitten **Yhdistä**.

## <a name="create-the-view-screen"></a>Tarkastelunäytön luominen

1. Valitse **Aloitus**-välilehdessä kohdan **Uusi näyttö** vieressä oleva alanuoli, jolloin näyttötyyppien luettelo avautuu, ja valitse sitten **Luettelonäyttö**.

    ![Luettelonäytön lisääminen](./media/get-started-create-from-blank/add-list-screen.png)

    Kun näyttö lisätään, siinä on useita oletusohjausobjekteja, kuten hakukenttä ja **[Valikoima](controls/control-gallery.md)**-ohjausobjekti. Valikoima kattaa koko näytön hakukentän alapuolella.

2. Valitse valikoima napsauttamalla tai napauttamalla lähellä sen keskiosaa.

    Valikoiman ympärillä näkyy valintakehys kahvoineen.

    ![Luettelonäytön lisääminen](./media/get-started-create-from-blank/select-gallery.png)

3. Valitse oikeanpuoleisessa ruudussa **CustomGallerySample**, jolloin **Tiedot**-ruutu avautuu.

    ![Tietoruudun avaaminen](./media/get-started-create-from-blank/custom-gallery-sample.png)

4. Valitse **Tietolähde**-kohdassa oleva alanuoli, jolloin sovelluksen tietolähteiden luettelo avautuu, ja valitse sitten **Aikataulu**.

    ![Tietolähteen valitseminen](./media/get-started-create-from-blank/select-schedule.png)

5. Valitse **Asettelu**, avaa asettelujen luettelo valitsemalla alanuoli ja valitse sitten **Otsikko, alaotsikko ja leipäteksti**.

    ![Asettelun valitseminen](./media/get-started-create-from-blank/select-layout.png)

6. Vaihda näytettävä sarake **Otsikko2**-kohdassa **Varmuuskopiointi**-sarakkeesta **Vapaaehtoinen**-sarakkeeksi.

     ![Selitteen sarakkeen vaihtaminen](./media/get-started-create-from-blank/change-title2.png)

7. Sulje **Tiedot**-ruutu valitsemalla oikean yläkulman sulkemiskuvake.

    Valikoimassa näkyy kunkin vapaaehtoisen nimi ja kyseisen vapaaehtoisen vuoron päivä ja aika.

    ![Valikoiman aikataulutiedot lajittelemattomina](./media/get-started-create-from-blank/show-data-unsorted.png)

8. Valitse valikoima ja varmista, että ominaisuusluettelossa näkyy ominaisuus **[Items](controls/properties-core.md)**.

    Kuten kaavariviltä näkyy, kyseisen ominaisuuden arvo on **Schedule**.

    ![Valikoiman aikataulutiedot lajittelemattomina](./media/get-started-create-from-blank/set-property.png)

9. Vaihda **Items**-ominaisuuden arvo kopioimalla tämä kaava ja liittämällä se kaavariville:

    **SortByColumns(Search(Schedule, TextSearchBox1.Text, "Vapaaehtoinen"), "Vapaaehtoinen", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

    Valikoiman tiedot näkyvät aakkosjärjestyksessä vapaaehtoisten nimien mukaan.

    ![Valikoiman aikataulutiedot lajiteltuina](./media/get-started-create-from-blank/show-data-sorted.png)

    Käyttäjät voivat lajitella ja suodattaa valikoiman vapaaehtoisen nimen mukaan kyseisen kaavan **SortByColumns**- ja **Search**-funktioiden perusteella.

   - Jos käyttäjä kirjoittaa ainakin yhden kirjaimen hakukenttään, valikoimassa näytetään vain tietueet, joissa **Vapaaehtoinen**-kenttä sisältää käyttäjän antaman tekstin.
   - Jos käyttäjä valitsee lajittelupainikkeen, tietueet näkyvät valikoimassa nousevassa tai laskevassa järjestyksessä (sen mukaan, miten monta kertaa käyttäjä valitsee painikkeen) **Vapaaehtoinen**-kentän perusteella.

     Lisätietoja näistä ja muista funktioista on artikkelissa [Lisätietoja kaavasta](formula-reference.md).

10. Kirjoita **i** hakuruutuun, valitse lajittelupainike napsauttamalla tai napauttamalla sitä ja valitse se sitten vielä kerran (tai pariton määrä lisäkertoja).

     Valikoima näyttää nämä tulokset.

     ![Lajittele ja suodata valikoimaa](./media/get-started-create-from-blank/sort-filter.png)

11. Tyhjennä kaikki teksti hakuruudusta.

12. Valitse näytön yläreunassa **[Selite](controls/control-text-box.md)**-ohjausobjekti ja korvaa sitten **[Otsikko]** asetuksella **Näytä tietueet**.

     ![Muuta otsikkoriviä](./media/get-started-create-from-blank/change-title-bar.png)

## <a name="create-the-change-screen"></a>Muutosnäytön luominen
1. Valitse **Aloitus**-välilehdessä alanuoli **Uusi näyttö** -kohdan vieressä ja valitse sitten **Lomakenäyttö**.

     ![Lomakenäytön lisääminen](./media/get-started-create-from-blank/add-form-screen.png)

1. Valitse juuri lisäämässäsi näytössä **Yhdistä tietoihin**, jolloin **Tiedot**-ruutu avautuu, ja yhdistä sitten tietolähde **Schedule**-arvoon.

1. Valitse **Kentät**-kohdassa kaikki valintaruudut, jolloin kaikki kentät näkyvät lomakkeessa.

     ![Kenttien näyttäminen](./media/get-started-create-from-blank/show-fields.png)

1. Vedä **Vapaaehtoinen**-kenttää ylöspäin niin, että se näkyy kenttäluettelossa ensimmäisenä.

     ![Kenttien järjestäminen uudelleen](./media/get-started-create-from-blank/reorder-fields.png)

1. Valitse lomake ja määritä sen **Item**-ominaisuudeksi tämä lauseke kirjoittamalla tai liittämällä se kaavariville:<br>**BrowseGallery1.Selected**

1. Valitse näytön yläreunassa **[Selite](controls/control-text-box.md)**-ohjausobjekti ja korvaa sitten **[Otsikko]** asetuksella **Vaihda tietueet**.

    ![Muuta otsikkoriviä](./media/get-started-create-from-blank/change-title-bar2.png)

## <a name="delete-and-rename-screens"></a>Näyttöjen poistaminen ja uudelleennimeäminen
1. Valitse vasemmassa siirtymispalkissa kolme pistettä (...) kohdassa **Näyttö1** ja valitse sitten **Poista**.

    ![Näytön poistaminen](./media/get-started-create-from-blank/delete-screen.png)

1. Valitse kolme pistettä (...) kohdassa **Näyttö2**, valitse **Nimeä uudelleen** ja kirjoita tai liitä sitten **ViewScreen**.

1. Valitse kolme pistettä (...) kohdassa **Näyttö3**, valitse **Nimeä uudelleen** ja kirjoita tai liitä sitten **ChangeScreen**.

## <a name="configure-icons-on-the-view-screen"></a>Tarkastelunäytön kuvakkeiden määrittäminen
1. Valitse **ViewScreen**-näytön yläreunassa pyöreä nuoli -kuvake.

    ![Tietueen lisääminen](./media/get-started-create-from-blank/refresh-icon.png)

1. Määritä kyseisen kuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:<br>**Refresh(Schedule)**

    Kun käyttäjä valitsee tämän kuvakkeen, tietoja **Schedule**-arvo päivitetään Excel-tiedostosta.

    Lisätietoja näistä ja muista funktioista on artikkelissa [Lisätietoja kaavasta](formula-reference.md).

1. Valitse plus-kuvake **ViewScreen**-näytön oikeassa yläkulmassa.

    ![Tietueen lisääminen](./media/get-started-create-from-blank/add-record.png)

1. Määritä kyseisen kuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:<br>**NewForm(EditForm1);Navigate(ChangeScreen,ScreenTransition.None)**

    Kun käyttäjä valitsee tämän kuvakkeen, **ChangeScreen** näytetään kaikki kentät tyhjänä, jotta käyttäjä voi luoda tietueen helpommin.

1. Valitse oikealle osoittava nuoli valikoiman ensimmäisessä tietueessa.

    ![Nuolen valitseminen](./media/get-started-create-from-blank/select-arrow.png)

1. Määritä nuolen **OnSelect**-ominaisuudeksi tämä kaava:<br>**EditForm(EditForm1); Navigate(ChangeScreen, ScreenTransition.None)**

    Kun käyttäjä valitsee tämän kuvakkeen, **ChangeScreen** näytetään niin, että jokaisessa kentässä näkyvät valitun tietueen tiedot, jotta käyttäjä voi luoda tietueen tai muokata sitä helpommin.

## <a name="configure-icons-on-the-change-screen"></a>Muutosnäytön kuvakkeiden määrittäminen
1. Valitse **ChangeScreen**-näytössä x-kuvake vasemmassa yläkulmassa.

    ![Peruutuskuvake](./media/get-started-create-from-blank/cancel-icon.png)

1. Määritä kyseisen kuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:<br>**ResetForm(EditForm1);Navigate(ViewScreen, ScreenTransition.None)**

    Kun käyttäjä valitsee tämän kuvakkeen, kaikki käyttäjän tässä näytössä tekemät muutokset hylätään, ja tarkastelunäyttö avautuu.

1. Valitse valintamerkkikuvake oikeassa yläkulmassa.

    ![Valintamerkkikuvake](./media/get-started-create-from-blank/checkmark-icon.png)

1. Määritä valintamerkin **OnSelect**-ominaisuudeksi tämä kaava:<br>**SubmitForm(EditForm1); Navigate(ViewScreen, ScreenTransition.None)**

    Kun käyttäjä valitsee tämän kuvakkeen, kaikki käyttäjän tässä näytössä tekemät muutokset tallennetaan, ja tarkastelunäyttö avautuu.

1. Valitse **Lisää**-välilehdessä **Kuvakkeet** ja valitse sitten **Roskakori**-kuvake.

1. Määritä uuden kuvakkeen **Väri**-ominaisuuden arvoksi **Valkoinen** ja siirrä uusi kuvake valintamerkkikuvakkeen viereen.

    ![Roskakorikuvake](./media/get-started-create-from-blank/trash-icon.png)

1. Määritä roskakorikuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:<br>**Remove(Schedule, BrowseGallery1.Selected); Navigate(ViewScreen, ScreenTransition.None)**

    Kun käyttäjä valitsee tämän kuvakkeen, valittu tietue poistetaan tietolähteestä ja tarkastelunäyttö avautuu.

## <a name="test-the-app"></a>Sovelluksen testaus
1. Valitse **ViewScreen**-näyttö ja avaa sitten esikatselu painamalla F5-näppäintä (tai valitsemalla **Esikatselu**-kuvake lähellä oikeaa yläkulmaa).

    ![Esikatselutilan avaaminen](./media/get-started-create-from-blank/open-preview.png)

1. Lisää tietue.

1. Päivitä lisäämäsi tietue ja tallenna sitten muutokset.

1. Päivitä lisäämäsi tietue ja peruuta sitten muutokset.

1. Poista lisäämäsi tietue.

1. Sulje esikatselutila painamalla Esc-näppäintä (tai valitsemalla sulkemiskuvake oikeassa yläkulmassa).

## <a name="next-steps"></a>Seuraavat vaiheet
* Tallenna sovelluksesi pilveen painamalla Ctrl+S, jotta voit suorittaa sen muissa laitteissa.
* [Jaa sovellus](share-app.md), jotta muut voivat suorittaa sen.
* Lue lisätietoja [funktioista](working-with-formulas.md), kuten **Patch**, joiden avulla voit hallita tietoja luomatta vakiolomaketta.

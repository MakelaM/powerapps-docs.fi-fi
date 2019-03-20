---
title: Luo ja Päivitä kokoelma pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Luo kokoelma pohjaan perustuvan sovelluksen, Lisää kohteita kokoelmaan ja vähintään yksi kohteiden poistaminen
author: aftowen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/28/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 04ef7924ce3f6945a666fe06bdc6091159bc44c4
ms.sourcegitcommit: c6ad6ba7814c5e7b12c3b7b76bf2e7718bf41b8c
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/19/2019
ms.locfileid: "58198540"
---
# <a name="create-and-update-a-collection-in-a-canvas-app"></a>Luo ja Päivitä kokoelma pohjaan perustuva sovellus

Kokoelman avulla voit tallentaa tietoja, joita käyttäjät voivat hallita sovelluksessa. Kokoelma on joukko kohteita, jotka muistuttavat, kuten tuotteen luettelon tuotteita. Saat lisätietoja eri muuttujatyyppiä kuten kokoelmat: [Tutustu pohjaan perustuvien sovellusten muuttujiin](working-with-variables.md).

## <a name="prerequisites"></a>Edellytykset

- [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.
- Luo sovellus tai avaa olemassa oleva sovellus PowerAppsissa.
- Lue, miten [ohjausobjekti määritetään](add-configure-controls.md) PowerAppsissa.

## <a name="create-a-multicolumn-collection"></a>Luo monisarakkeisen kokoelma

1. PowerApps Studio, Lisää **Tekstisyöte** ohjausobjektin.

    ![Lisää Tekstisyöte](./media/create-update-collection/add-textbox.png)

1. Ohjausobjektin nimeäminen uudelleen valitsemalla vasemmassa siirtymisruudussa sen pistettä valitsemalla **nimeä**, ja kirjoittamalla sitten **ProductName**.

    ![Ohjausobjektin nimeäminen uudelleen](./media/create-update-collection/rename-textbox.png)

1. Lisää **avattava** ohjausobjektin.

    ![Avattavan luettelon lisääminen](./media/create-update-collection/add-dropdown.png)

1. Nimeä uudelleen **avattava** ohjausobjektin **värit**, ja varmista, että **kohteet** ominaisuus valitaan ominaisuusluettelossa.

    ![Kohteiden ominaisuus](./media/create-update-collection/items-property.png)

1. Korvaa kaavarivillä **DropDownSample** Tämä lauseke:

    `["Red","Green","Blue"]`

1. Lisää **painike** ohjausobjekti, määritä sen **tekstin** ominaisuudeksi **”Lisää”**, ja määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    Collect(
        ProductList,
        {
            Product: ProductName.Text,
            Color: Colors.Selected.Value
        }
    )
    ```

1. Paina F5-näppäintä, kirjoita tekstiä **ProductName**, valitse vaihtoehto **värit**, ja valitse sitten **Lisää**.

    ![Sovelluksen esikatselu](./media/create-update-collection/preview-add.png)

1. Toista edellinen vaihe vähintään kaksi kertaa ja paina sitten ESC-näppäintä.

1. Valitse **tiedoston** -valikosta **kokoelmat** näyttämään kokoelman, jonka loit.

    ![Näytä kokoelma](./media/create-update-collection/show-collection.png)

## <a name="show-a-collection"></a>Näytä kokoelma

1. Lisää pystysuora **valikoiman** ohjausobjektin.

    ![Lisää pystysuuntainen valikoima](./media/create-update-collection/add-gallery.png)

1. Määritä valikoiman **kohteet** ominaisuudeksi **ProductList**.

1. - **Tietojen** ruudussa alaotsikko kentän arvoksi **väri**, ja otsikkokentän arvoksi **tuotteen**.

    ![Valikoiman Items-ominaisuuden asettaminen ja muuta se näyttää kentät](./media/create-update-collection/configure-gallery.png)

1. Sulje **tietojen** ruutu avautuu, ja **asettelu** kentän **otsikko ja alaotsikko**.

    ![Valikoiman Items-ominaisuuden asettaminen ja muuta se näyttää kentät](./media/create-update-collection/change-layout.png)

    Näytön pitäisi näyttää samalta kuin tässä esimerkissä:

    ![Ensimmäinen näyttö-Esimerkki](./media/create-update-collection/screen-example1.png)

## <a name="remove-one-or-all-items"></a>Poista yksi tai kaikki kohteet

1. Valitse haluamasi valikoiman mallipohja napsauttamalla tai napauttamalla valikoiman ja napsauttamalla tai napauttamalla vasemmassa yläkulmassa olevaa kynäkuvaketta.

    ![Valitse valikoiman mallipohja](./media/create-update-collection/select-template.png)

1. Lisää **roskakori** kuvake valikoiman mallipohja.

    ![Lisää roskakorikuvake](./media/create-update-collection/trash-icon.png)

1. Määritä kuvakkeen **OnSelect** -ominaisuuden arvoksi tämä kaava:

    `Remove(ProductList, ThisItem)`

1. Valikoiman ulkopuolella Lisää painike, määritä sen **tekstin** ominaisuudeksi **”Tyhjennä”**, ja määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava:

    `Clear(ProductList)`

1. Pidät Alt-näppäintä ja valitse **roskakori** kohde kokoelmasta poistettavat sen tai valitsemalla kuvakkeen **Tyhjennä** poistaaksesi kaikki kohteet kokoelmasta.

## <a name="put-a-sharepoint-list-into-a-collection"></a>SharePoint-luettelon asettaminen kokoelmaan

1. [Yhdistä SharePoint-luetteloon](connections/connection-sharepoint-online.md#create-a-connection).

1. Lisää painike ja määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä funktio. Korvaa *ListName* SharePoint-luettelon nimellä:<br>

    `Collect(MySPCollection, ListName)`

    Tämä funktio luo kokoelman, jonka nimi on **MySPCollection** ja joka sisältää samat tiedot kuin SharePoint-luettelokin.

1. Pidä Alt-näppäintä painettuna ja valitse painike.

1. (valinnainen) Jos haluat esikatsella luomasi kokoelman, valitse **kokoelmat** - **tiedoston** valikosta.

Lisätietoja SharePoint-luettelosta (esimerkiksi päivämäärät, vaihtoehtoja ja henkilöt) tietojen näyttäminen valikoimassa: [Näytä luettelon sarakkeet valikoimassa](connections/connection-sharepoint-online.md#show-list-columns-in-a-gallery). Lisätietoja siitä, miten voit näyttää lomakkeen (avattavia luetteloita, päivämäärävalitsimia ja ihmisten keräilijät): [Muokattu lomake- ja näytetty lomake-ohjausobjektit](controls/control-form-detail.md).

## <a name="next-steps"></a>Seuraavat vaiheet

- Tarkista [tiedot](functions/function-clear-collect-clearcollect.md) varten **kerätä** funktio.
- Lue, miten voit muotoilla kokoelman tietoja käyttämällä [AddColumns-, DropColumns-, RenameColumns- ja ShowColumns](functions/function-table-shaping.md) funktioita.

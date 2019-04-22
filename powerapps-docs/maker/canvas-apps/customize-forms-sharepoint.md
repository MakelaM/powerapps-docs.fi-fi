---
title: Lomakkeen mukauttaminen pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Määritä PowerAppsissa, mitä tietoja näytetään pohjaan perustuvan sovelluksen lomakkeessa, missä järjestyksessä ne näytetään ja missä ohjausobjekteissa ne näytetään.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/17/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1a6465a00f135489d594bad75b8a25942e05dd25
ms.sourcegitcommit: f84095d964fe1fe5cc5290e5edbee284bd768e1e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/18/2019
ms.locfileid: "58870927"
---
# <a name="customize-a-canvas-app-form-in-powerapps"></a>Pohjaan perustuvan sovelluksen lomakkeen mukauttaminen PowerAppsissa

Mukauta pohjaan perustuvassa sovelluksessa **Näytä lomake**- ja **Muokkaa lomaketta** -ohjausobjekteja siten, että ne näyttävät merkittävimmät tiedot intuitiivisimmassa järjestyksessä, jotta käyttäjät voivat helposti ymmärtää ja päivittää tietoja.

Jokainen lomake käsittää yhden tai useampia kortteja, joista jokainen näyttää tiedot tietolähteen tietystä sarakkeesta. Noudattamalla tämän artikkelin ohjeita voit määrittää, mitkä kortit näkyvät lomakkeessa, ja voit siirtää kortteja ylös ja alas lomakkeessa.

Jos et tunne pohjaan pps, katso [mitä ovat pohjaan perustuvat sovellukset?](getting-started.md).

## <a name="prerequisites"></a>Edellytykset

[Luo sovellus](data-platform-create-app.md) Common Data Service -palvelussa ja [mukauta sitten valikoimaa](customize-layout-sharepoint.md) kyseisessä sovelluksessa.

## <a name="show-and-hide-cards"></a>Korttien näyttäminen ja piilottaminen

1. Kirjaudu sisään [Powerappsin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), ja Avaa luomasi ja mukauttamasi sovellus.

1. Vasemmassa siirtymispalkissa, kirjoita tai liitä **D** hakukenttään elementtien luettelo ja valitse sitten **DetailForm1**.

    > [!div class="mx-imgBorder"]
    > ![Valitse tiedot-näyttö](./media/customize-forms-sharepoint/select-detailform.png)

1. Valitse oikeanpuoleisen ruudun **Ominaisuudet**-välilehdessä **Muokkaa kenttiä**, jotta voit valita **Kentät**-ruudun.

    > [!div class="mx-imgBorder"]
    > ![Avaa kentät-ruudussa](./media/customize-forms-sharepoint/edit-fields.png)

1. Piilota kenttä, kuten **kuvaus**, hiiren osoitin sen päälle, valitsemalla kolme pistettä (...), joka näkyy ja valitsemalla sitten **poistaa**.

    > [!div class="mx-imgBorder"]
    > ![Kenttien luettelo](./media/customize-forms-sharepoint/hide-fields.png)

1. Näytä kentän valitsemalla **Lisää kenttä**, kirjoittamalla tai liittämällä kentän nimi muutama ensimmäinen hakuruutuun, valitsemalla kentän ja valitsemalla sitten **Lisää**.

    > [!div class="mx-imgBorder"]
    > ![Kenttien luettelo](./media/customize-forms-sharepoint/show-field.png)

## <a name="reorder-the-cards"></a>Järjestä kortit uudelleen

1. - **Kentät** ruudussa tietokenttä **tilin nimi** kentän kenttäluettelossa yläreunaan.

    Korttien **DetailForm1** muutoksen.

    > [!div class="mx-imgBorder"]
    > ![Uudelleen järjestetyt kortit](./media/customize-forms-sharepoint/reordered-card.png)

1. (valinnainen) Järjestä muut kortit uudelleen tähän järjestykseen:

    - Tilin nimi
    - Työntekijöiden määrä
    - Vuosittainen tuotto
    - Ensisijainen puhelin
    - Osoite 1: Katuosoite 1
    - Osoite 1: Katuosoite 2
    - Osoite 1: Postitoimipaikka
    - Osoite 1: Postinumero

1. Vasemmassa siirtymispalkissa, kirjoita tai liitä **Ed** Etsi ja valitse sitten **EditForm1** sitä.

1. Toista edellisen ja nykyisen toimintosarjan vaiheet, jotta **EditForm1**:n kentät vastaavat **DetailForm1**:n kenttiä.

## <a name="run-the-app"></a>Sovelluksen suorittaminen

1. Vasemmassa siirtymispalkissa, kirjoita tai liitä **Br** Etsi ja valitse sitten **BrowseScreen1** sitä.

1. Avaa esikatselutila painamalla F5-näppäintä (tai valitsemalla **Esikatselu**-kuvake oikean yläkulman läheltä).

    > [!div class="mx-imgBorder"]
    > ![Esikatselu-kuvake](./media/customize-forms-sharepoint/open-preview.png)

1. Valitse oikeassa yläkulmassa plus-kuvaketta voit lisätä tietueen **EditScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Tietueen lisääminen](./media/customize-forms-sharepoint/add-record.png)

1. Lisää haluamasi tiedot ja valitse sitten valintamerkkikuvaketta oikeassa yläkulmassa tallentaaksesi muutokset ja palaa **BrowseScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Tallenna tietue](./media/customize-forms-sharepoint/save-record.png)

1. Valitse nuoli-kohteen, jonka loit äsken näyttää tietoja kyseisestä kohteesta **DetailScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Oikea nuoli](./media/customize-forms-sharepoint/right-arrow.png)

1. Valitse oikeassa yläkulmassa sijaitsevaa muokkauskuvaketta päivittääksesi tietueen **EditScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Tietueen muokkaaminen](./media/customize-forms-sharepoint/edit-record.png)

1. Muuta yhden tai useamman kentän tietoja ja valitse sitten valintamerkkiä oikeassa yläkulmassa tallentaaksesi muutokset ja palaa **DetailScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Tallenna muutokset](./media/customize-forms-sharepoint/save-record.png)

1. Valitse oikeassa yläkulmassa roskakorikuvaketta voit poistaa juuri päivittämäsi tietueen ja palata **BrowseScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Poista tietue](./media/customize-forms-sharepoint/delete-record.png)

1. Sulje esikatselutila painamalla ESC-näppäintä (tai valitsemalla vasemmassa yläkulmassa sijaitsevaa Sulje-kuvaketta).

## <a name="next-steps"></a>Seuraavat vaiheet

- [Tallenna ja julkaise](save-publish-app.md) sovelluksesi.
- [Mukauta korttia](customize-card.md) sovelluksessasi.
---
title: Lomakkeen mukauttaminen pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Määritä PowerAppsissa, mitä tietoja näytetään pohjaan perustuvan sovelluksen lomakkeessa, missä järjestyksessä ne näytetään ja missä ohjausobjekteissa ne näytetään.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/17/2018
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 67e7e0074259731bb1d3c50474e8020e3f4fcf1b
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993176"
---
# <a name="customize-a-canvas-app-form-in-powerapps"></a>Pohjaan perustuvan sovelluksen lomakkeen mukauttaminen PowerAppsissa

Mukauta pohjaan perustuvassa sovelluksessa **Näytä lomake**- ja **Muokkaa lomaketta** -ohjausobjekteja siten, että ne näyttävät merkittävimmät tiedot intuitiivisimmassa järjestyksessä, jotta käyttäjät voivat helposti ymmärtää ja päivittää tietoja.

Jokainen lomake käsittää yhden tai useampia kortteja, joista jokainen näyttää tiedot tietolähteen tietystä sarakkeesta. Noudattamalla tämän artikkelin ohjeita voit määrittää, mitkä kortit näkyvät lomakkeessa, ja voit siirtää kortteja ylös ja alas lomakkeessa.

Jos et tunne pohjaan liittyviä PPS-sovelluksia, tutustu Ohje artikkeliin [Mitä ovat kangas sovellukset?](getting-started.md).

## <a name="prerequisites"></a>Edellytykset

[Luo sovellus](data-platform-create-app.md) Common Data Service -palvelussa ja [mukauta sitten valikoimaa](customize-layout-sharepoint.md) kyseisessä sovelluksessa.

## <a name="show-and-hide-cards"></a>Korttien näyttäminen ja piilottaminen

1. Kirjaudu sisään [Powerappsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)ja avaa sitten luomasi ja mukauttamasi sovellus.

1. Suodata luettelon elementit kirjoittamalla tai liittämällä **D** vasemmassa siirtymis palkissa ja valitsemalla sitten **DetailForm1**.

    > [!div class="mx-imgBorder"]
    > ![Valitse tiedot-näyttö @ no__t-1

1. Valitse oikeanpuoleisen ruudun **Ominaisuudet**-välilehdessä **Muokkaa kenttiä**, jotta voit valita **Kentät**-ruudun.

    > [!div class="mx-imgBorder"]
    > ![Avaa kentät-ruutu @ no__t-1

1. Piilota kenttä, kuten **Kuvaus**, viemällä hiiren osoitin sen päälle, valitsemalla esiin tulevan kolme pistettä (...) ja valitsemalla sitten **Poista**.

    > [!div class="mx-imgBorder"]
    > ![Luettelon kentistä @ no__t-1

1. Näytä kenttä valitsemalla **Lisää kenttä**, kirjoittamalla tai liittämällä kentän nimen ensimmäiset kirjaimet haku kenttään, valitsemalla kentän valinta ruutu ja valitsemalla sitten **Lisää**.

    > [!div class="mx-imgBorder"]
    > ![Luettelon kentistä @ no__t-1

## <a name="reorder-the-cards"></a>Järjestä kortit uudelleen

1. Vedä **kentät** -ruudussa **tilin nimi** -kenttä kenttä luettelon yläreunaan.

    **DetailForm1** -kortit vastaavat muutosta.

    > [!div class="mx-imgBorder"]
    > ![Järjestettyjä kortteja @ no__t-1

1. valinnainen Järjestä muut kortit tähän järjestykseen:

    - Tilin nimi
    - Työntekijöiden määrä
    - Vuosittainen tuotto
    - Pääpuhelin
    - Osoite 1: Katuosoite 1
    - Osoite 1: Katu 2
    - Osoite 1: Postitoimipaikka
    - Osoite 1: Posti numero

1. Kirjoita **tai liitä vasemmassa** siirtymis palkissa haku palkkiin ja valitse sitten **EditForm1** .

1. Toista edellisen ja nykyisen toimintosarjan vaiheet, jotta **EditForm1**:n kentät vastaavat **DetailForm1**:n kenttiä.

## <a name="run-the-app"></a>Sovelluksen suorittaminen

1. Kirjoita **tai liitä vasemman** siirtymis palkin haku palkkiin ja valitse sitten **BrowseScreen1** .

1. Avaa esikatselutila painamalla F5-näppäintä (tai valitsemalla **Esikatselu**-kuvake oikean yläkulman läheltä).

    > [!div class="mx-imgBorder"]
    > ![Preview-kuvake @ no__t-1

1. Valitse oikeassa yläkulmassa pluskuvake, jos haluat lisätä tietueen **EditScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Lisää tietue @ no__t-1

1. Lisää haluamasi tiedot ja valitse sitten oikeasta yläkulmasta valinta merkki kuvake, jos haluat tallentaa tekemäsi muutokset ja palata osoitteeseen **BrowseScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Tallenna tietue @ no__t-1

1. Valitse juuri luomasi kohteen nuoli, jos haluat näyttää kohteen tiedot kohteessa **DetailScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Oikea nuoli @ no__t-1

1. Valitse oikeassa yläkulmassa Muokkaa-kuvake, jos haluat päivittää tietueen **EditScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Muokkaa tietuetta @ no__t-1

1. Muuta yhden tai useamman kentän tietoja ja tallenna muutoksesi ja palaa osoitteeseen **DetailScreen1**napsauttamalla oikeassa yläkulmassa olevaa valinta merkkiä.

    > [!div class="mx-imgBorder"]
    > ![Tallenna muutokset @ no__t-1

1. Valitse oikeasta yläkulmasta roska kori-kuvake, niin voit poistaa juuri päivittämäsi tietueen ja palata osoitteeseen **BrowseScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Poista tietue @ no__t-1

1. Sulje esikatselutila painamalla ESC-näppäintä (tai valitsemalla Sulje-kuvake vasemman yläkulman läheltä).

## <a name="next-steps"></a>Seuraavat vaiheet

- [Tallenna ja julkaise](save-publish-app.md) sovelluksesi.
- [Mukauta korttia](customize-card.md) sovelluksessasi.
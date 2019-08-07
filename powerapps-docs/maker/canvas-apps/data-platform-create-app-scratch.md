---
title: Pohjaan perustuvan sovelluksen luominen alusta alkaen Common Data Servicen avulla | Microsoft Docs
description: Luo PowerAppsissa pohjaan perustuva sovellus, jotta voit lisätä, päivittää ja poistaa tietueita Common Data Servicessa.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/21/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 482a5a91c241aa9fd8c85dfb970cf692cd2ab1a3
ms.sourcegitcommit: 38270060d2d0b784fe065164e6112c011b26e17c
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/06/2019
ms.locfileid: "68830465"
---
# <a name="create-a-canvas-app-from-scratch-using-common-data-service"></a>Pohjaan perustuvan sovelluksen luominen alusta alkaen Common Data Servicen avulla

Voit rakentaa pohjaan perustuvan sovelluksen, jolla hallitaan Common Data Servicessa säilytettäviä tietoja käyttämällä (sisäänrakennettuja) standardientiteettejä, (organisaatiosi luomia) mukautettuja entiteettejä tai kumpiakin.

Kun luot sovelluksen Common Data Servicestä, sinun ei tarvitse luoda yhteyttä PowerAppsista, kuten SharePointin, Dynamics 365:n tai Salesforcen kaltaisten tietolähteiden kanssa. Sinun on vain määritettävä entiteetit, jotka haluat näyttää tai joita haluat hallita sovelluksessa.

## <a name="prerequisites"></a>Edellytykset

- Ennen sovelluksen luomista alusta alkaen tutustu PowerAppsin perusteisiin [luomalla sovellus](data-platform-create-app.md) ja mukauttamalla sovelluksen [valikoimaa](customize-layout-sharepoint.md), [lomakkeita](customize-forms-sharepoint.md) ja [kortteja](customize-card.md).
- [Vaihda ympäristöön](working-with-environments.md), jossa on luotu tietokanta näytetiedoilla. Jos sinulla on asianmukainen käyttöoikeus, voit [luoda ympäristön](../../administrator/create-environment.md), joka täyttää tämän tarpeen.
- Sovelluksen luominen edellyttää, että käyttöoikeusroolisi on [Ympäristön tekijä](https://docs.microsoft.com/power-platform/admin/database-security#predefined-security-roles).

## <a name="open-a-blank-app"></a>Avaa tyhjä sovellus

1. Kirjaudu sisään [PowerAppsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Valitse **Tee oma sovelluksesi** -kohdasta vaihtoehto **Pohjan sovellus tyhjästä**.

    ![Tyhjän sovelluksen ruutu](./media/data-platform-create-app-scratch/blank-app.png)

1. Määritä sovelluksesi nimi, valitse **Puhelin** ja valitse sitten **Luo**.

    Voit luoda sovelluksen alusta alkaen tableteille, mutta tässä aiheessa näytetään sovelluksen luominen puhelimille.

## <a name="specify-an-entity"></a>Entiteetin määritys

1. Valitse näytön keskellä **Yhdistä tietoihin**.

1. Valitse **Tiedot**-ruudussa **Common Data Service**, valitse **Tilit**-valintaruutu ja valitse sitten **Yhdistä**.

1. Sulje **Tiedot**-ruutu valitsemalla oikean yläkulman sulkemiskuvake.

## <a name="add-a-list-screen"></a>Luettelonäytön lisääminen

1. Valitse **Aloitus**-välilehdessä **Uusi näyttö** -kohdan vieressä oleva alanuoli ja valitse sitten **Luettelo**.

    ![Luettelonäytön lisääminen](./media/data-platform-create-app-scratch/list-screen.png)

1. Valitse vasemmassa siirtymäpalkissa **BrowseGallery1**-kohta ja aseta sen **Items**-ominaisuuden arvoksi tämä kaava:

    `SortByColumns(Search(Accounts, TextSearchBox1.Text, "name"), "name", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))`

    Tämä kaava määrittää seuraavat:

   - Valikoiman tulee näyttää **Accounts**-entiteetin tietoja.
   - Tiedot tulee lajitella nousevassa järjestyksessä, kunnes käyttäjä valitsee lajittelupainikkeen lajittelujärjestyksen vaihtamiseksi.
   - Jos käyttäjä kirjoittaa tai liittää yhden tai useamman merkin hakuriville (**TextSearchBox1**), luettelo näyttää vain ne tilit, joiden **nimikenttä** sisältää käyttäjän määrittämät merkit.

     Voit käyttää [näitä ja monia muita funktioita](formula-reference.md) määrittämään sovelluksen ulkoasua ja toimintaa.

     ![Valikoiman Items-ominaisuuden asettaminen](./media/data-platform-create-app-scratch/gallery-items.png)

1. Aseta valikoiman asettelu näyttämään vain tilien nimet ja määritä otsikkopalkki näyttämään sana **Selaa** kuten [valikoiman mukauttamista käsittelevässä](customize-layout-sharepoint.md) aiheessa kuvaillaan.

    ![Selaa-näyttö](./media/data-platform-create-app-scratch/final-browse.png)

1. Liikuta hiirtä vasemmassa siirtymispalkissa **Screen1**-kohdan yläpuolella, valitse kolmen pisteen kuvake (...) ja valitse sitten **Poista**.

1. Liikuta hiirtä vasemmassa siirtymispalkissa **Screen2**-kohdan yläpuolella, valitse kolmen pisteen kuvake (...) ja valitse sitten **Nimeä uudelleen**.

1. Kirjoita tai liitä nimi **BrowseScreen** ja sitten anna näytön valikoiman nimeksi **BrowseGallery**.

    ![Selausruudun, valikoiman nimeäminen uudelleen](./media/data-platform-create-app-scratch/rename-browse.png)

## <a name="add-a-form-screen"></a>Lomakenäytön lisääminen

1. Toista edellisen toimintosarjan ensimmäinen vaihe, mutta lisää **Luettelonäytön** sijasta **Lomakenäyttö**.

1. Aseta lomakkeen **DataSource**-ominaisuudeksi **Accounts** ja sen **Item**-ominaisuudeksi **BrowseGallery.Selected** kuten oikeanpuoleisen ruudun **Lisäasetukset**-välilehdessä on näytetty.

    ![Lomakkeen Datasource- ja Item-ominaisuuden asettaminen](./media/data-platform-create-app-scratch/form-datasource.png)

1. Avaa **kentät** -ruutu valitsemalla oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdestä **Muokkaa kenttiä** .

1. Valitse **Lisää kenttä**, ja valitse sitten seuraavien kenttien valintaruudut:

    - **Tilin nimi**
    - **Osoite 1: Katuosoite 1**
    - **Osoite 1: Kaupunki**
    - **Osoite 1: Postinumero**
    - **Työntekijöiden määrä**
    - **Vuosittainen tuotto**

    > [!NOTE]
    > Tämän skenaarion ulkopuolella voit luoda mukautetun kentän valitsemalla **uusi kenttä**, antamalla tarvittavat tiedot ja valitsemalla sitten **Done**. Lisätietoja: [Luo kenttä](../common-data-service/create-edit-field-portal.md#create-a-field).<br><br>![](media/data-platform-create-app-scratch/choose-or-add-fields.png "Kentän valitseminen ja lisääminen")

1. Valitse **Lisää**.

1. Aseta otsikkopalkin **Text**-ominaisuudeksi **Luo/Muokkaa**.

    Näyttö päivittyy muutosten mukaisesti.

    ![Lomakkeen Datasource- ja Item-ominaisuuden asettaminen](./media/data-platform-create-app-scratch/field-list.png)

1. Anna näytölle nimi **FormScreen**.

## <a name="configure-icons"></a>Kuvakkeiden määritys

1. Aseta **BrowseScreen**-kohdassa näytön yläosan pyöreän kuvakkeen lähellä olevan **OnSelect**-ominaisuudeksi tämä kaava:

    `Refresh(Accounts)`

    ![Päivitä-kuvake](./media/data-platform-create-app-scratch/refresh-icon.png)

1. Aseta plus-kuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:

    `NewForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![Lisäämiskuvake](./media/data-platform-create-app-scratch/plus-icon.png)

1. Aseta ensimmäisen oikealle osoittavan nuolen **OnSelect**-ominaisuudeksi tämä kaava:

    `EditForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![Seuraava-kuvake](./media/data-platform-create-app-scratch/next-icon.png)

1. Aseta **FormScreen**-kohdassa peruutuskuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:

    `ResetForm(EditForm1);Navigate(BrowseScreen, ScreenTransition.None)`

    ![Peruutuskuvake](./media/data-platform-create-app-scratch/cancel-icon.png)

1. Aseta valintamerkkikuvakkeen **OnSelect**-ominaisuudeksi tämä kaava:

    `SubmitForm(EditForm1); Navigate(BrowseScreen, ScreenTransition.None)`

    ![Valintamerkkikuvake](./media/data-platform-create-app-scratch/checkmark-icon.png)

1. Valitse **Lisää**-välilehdessä **Kuvakkeet** ja valitse sitten **Roskakori**-kuvake.

1. Aseta **Roskakori**-kuvakkeen **Color**-ominaisuudeksi **White** ja sen **OnSelect**-ominaisuudeksi tämä kaava:

    `Remove(Accounts, BrowseGallery.Selected); Navigate(BrowseScreen, ScreenTransition.None)`

    ![Roskakorikuvake](./media/data-platform-create-app-scratch/trash-icon.png)

## <a name="test-the-app"></a>Sovelluksen testaus

1. Valitse vasemmanpuoleisessa siirtymispalkissa **BrowseScreen**-kohta ja avaa sitten Esikatselu painamalla F5-näppäintä (tai valitsemalla Toista-kuvake lähellä oikeaa yläkulmaa).

    ![Esikatselun avaaminen](./media/data-platform-create-app-scratch/open-preview.png)

1. Vaihda luettelon lajittelujärjestystä nousevan ja laskevan välillä, ja suodata luetteloa syöttämällä tilin nimen sisältävä yksi tai useampi merkki.

1. Lisää tili, muokkaa lisäämääsi tiliä ja aloita tilin päivittäminen, mutta sitten peruuta muutokset ja poista tili.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Linkitä tämä sovellus ratkaisuun](add-app-solution.md), jotta voit esimerkiksi ottaa sen käyttöön toisessa ympäristössä tai julkaista sen AppSourceen.
- [Avaa yksi tai useampi esimerkkisovellus](open-and-run-a-sample-app.md) ja tutustu erilaisiin sovellustyyppeihin, joita voit luoda.

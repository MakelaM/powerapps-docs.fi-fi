---
title: Pohjaan perustuvan sovelluksen luominen alusta alkaen Common Data Service for Apps -palvelun avulla | Microsoft Docs
description: Luo PowerAppsissa pohjaan perustuva sovellus, jotta voit lisätä, päivittää ja poistaa tietueita Common Data Service for Apps -palvelussa.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 45b5d85998825cdafc2bbea7badaa5d7cde2f092
ms.sourcegitcommit: 02d0234bd84352bf1c43d0fc9225ab60947a0add
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/15/2018
ms.locfileid: "49317041"
---
# <a name="create-a-canvas-app-from-scratch-using-common-data-service-for-apps"></a>Pohjaan perustuvan sovelluksen luominen alusta alkaen Common Data Service for Apps -palvelun avulla

Voit rakentaa pohjaan perustuvan sovelluksen, jolla hallitaan Common Data Service for Apps -tietokannassa säilytettäviä tietoja käyttämällä (sisäänrakennettuja) standardientiteettejä, (organisaatiosi luomia) mukautettuja entiteettejä tai kumpiakin.

Kun rakennat sovelluksen Common Data Servicen avulla, sinun ei tarvitse luoda yhteyttä PowerAppsista, kuten on tarpeen tietolähteille SharePoint, Dynamics 365 ja Salesforce. Sinun tarvitsee vain määrittää sovellukselle entiteetit, joita haluat näyttää, hallita tai käyttää kummallekin toiminnalle.

## <a name="prerequisites"></a>Edellytykset

- Ennen sovelluksen luomista alusta alkaen tutustu PowerAppsin perusteisiin [luomalla sovellus](data-platform-create-app.md) ja mukauttamalla sovelluksen [valikoimaa](customize-layout-sharepoint.md), [lomakkeita](customize-forms-sharepoint.md) ja [kortteja](customize-card.md).
- [Vaihda ympäristöön](working-with-environments.md), jossa on luotu tietokanta näytetiedoilla. Jos sinulla on asianmukainen käyttöoikeus, voit [luoda ympäristön](../../administrator/create-environment.md), joka täyttää tämän tarpeen.

## <a name="open-a-blank-app"></a>Tyhjän sovelluksen avaaminen

1. Kirjaudu sisään [PowerAppsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Vie hiiren osoitin **Tee oma sovelluksesi** -osiossa pohjaan perustuvien sovellusten **Aloita tyhjästä** -ruudun päälle. Napsauta tai napauta puhelinkuvaketta ja napsauta tai napauta sitten kohtaa **Tee tämä sovellus**.

    ![Tyhjän sovelluksen ruutu](./media/data-platform-create-app-scratch/start-from-blank.png)

    Voit suunnitella sovelluksen alusta alkaen puhelimille tai muille laitteille (kuten tableteille). Tässä aiheessa keskitytään puhelinsovelluksen luomiseen.

## <a name="specify-an-entity"></a>Entiteetin määritys

1. Napsauta tai napauta näytön keskialueella olevaa kohtaa **yhdistä tietoihin** ja sitten napsauta tai napauta **Tiedot**-ruudun **Common Data Service** -yhteyttä.

1. Suodata entiteettiluetteloa kirjoittamalla tai liittämällä hakukenttään pari ensimmäistä kirjainta sanasta **Accounts**, valitse **Accounts**-valintaruutu ja napsauta tai napauta **Yhdistä**.

    ![Accounts-entiteetin määrittäminen](./media/data-platform-create-app-scratch/cds-connect.png)

1. Sulje **Tiedot**-ruutu napsauttamalla tai napauttamalla oikean yläkulman sulkemiskuvaketta.

## <a name="add-a-list-screen"></a>Luettelonäytön lisääminen

1. Napsauta tai napauta **Aloitus**-välilehdessä **Uusi näyttö** -kohdan alaspäin osoittavaa nuolta ja napsauta tai napauta **Luettelonäyttö**.

    ![Luettelonäytön lisääminen](./media/data-platform-create-app-scratch/list-screen.png)

1. Napsauta tai napauta vasemman siirtymäpalkin kohtaa **TemplateGalleryList1** ja aseta sen **Items**-ominaisuudeksi tämä kaava:

    `SortByColumns(Search(Accounts, TextSearchBox1.Text, "name"), "name", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))`

    Tämä kaava määrittää seuraavat:

   - Valikoiman tulee näyttää **Accounts**-entiteetin tietoja.
   - Tiedot tulee järjestää nousevassa järjestyksessä, kunnes käyttäjä napsauttaa tai napauttaa lajittelupainiketta järjestyksen muuttamiseksi.
   - Jos käyttäjä kirjoittaa tai liittää yhden tai useamman merkin hakukenttään, luettelo näyttää vain ne tilit, joiden nimikenttä sisältää käyttäjän määrittämät merkit.

     Voit käyttää [näitä ja monia muita funktioita](formula-reference.md) määrittämään sovelluksen ulkoasua ja toimintaa.

     ![Valikoiman Items-ominaisuuden asettaminen](./media/data-platform-create-app-scratch/gallery-items.png)

1. Aseta valikoiman asettelu näyttämään vain tilien nimet ja määritä otsikkopalkki näyttämään sana **Selaa** kuten [valikoiman mukauttamista käsittelevässä](customize-layout-sharepoint.md) aiheessa kuvaillaan.

    ![Selaa-näyttö](./media/data-platform-create-app-scratch/final-browse.png)

1. Siirrä hiiren osoitin kohdan **Screen1** päälle, napsauta tai napauta kolmea pistettä (...) ja napsauta tai napauta **Poista**.

1. Siirrä hiiren osoitin kohdan **Screen2** päälle, napsauta tai napauta kolmea pistettä (...) ja napsauta tai napauta **Nimeä uudelleen**.

1. Kirjoita tai liitä nimi **BrowseScreen** ja sitten anna näytön valikoiman nimeksi **BrowseGallery**.

    ![Selausruudun, valikoiman nimeäminen uudelleen](./media/data-platform-create-app-scratch/rename-browse.png)

## <a name="add-a-form-screen"></a>Lomakenäytön lisääminen

1. Toista edellisen toimintosarjan ensimmäinen kohta, mutta lisää **Luettelonäytön** sijasta **Lomakenäyttö**.

1. Aseta lomakkeen **DataSource**-ominaisuudeksi **Accounts** ja sen **Item**-ominaisuudeksi **BrowseGallery.Selected** kuten oikeanpuoleisen **Lisäasetukset-välilehdessä** näytetään.

    ![Lomakkeen Datasource- ja Item-ominaisuuden asettaminen](./media/data-platform-create-app-scratch/form-datasource.png)

1. Napsauta tai napauta oikeanpuoleisen ruudun **Ominaisuudet**-välilehteä, napsauta tai napauta **Accounts**, niin **Tiedot**-ruutu avautuu, ja valitse seuraavien kenttien valintaruudut:

    - Tilin nimi
    - Osoite 1: Katu 1
    - Osoite 1: Kaupunki
    - Osoite 1: Postinumero
    - Työntekijöiden määrä
    - Vuosittainen tuotto

1. Aseta otsikkopalkin **Text**-ominaisuudeksi **Luo/Muokkaa**.

    Näyttö päivittyy muutosten mukaisesti.

    ![Lomakkeen Datasource- ja Item-ominaisuuden asettaminen](./media/data-platform-create-app-scratch/field-list.png)

1. Anna näytölle nimi **FormScreen**.

## <a name="configure-icons"></a>Kuvakkeiden määritys

1. Napsauta tai napauta **BrowseScreen**-näytöllä ympyränmuotoista kuvaketta näytön yläosassa ja aseta sen **OnSelect**-ominaisuudeksi tämä kaava:

    `Refresh(Accounts)`

    ![Päivitä-kuvake](./media/data-platform-create-app-scratch/refresh-icon.png)

1. Napsauta tai napauta plus-kuvaketta ja aseta sen **OnSelect**-ominaisuudeksi tämä kaava:

    `NewForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![Lisäämiskuvake](./media/data-platform-create-app-scratch/plus-icon.png)

1. Napsauta tai napauta ensimmäistä oikealle osoittavaa nuolta ja aseta sen **OnSelect**-ominaisuudeksi tämä kaava:

    `EditForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![Seuraava-kuvake](./media/data-platform-create-app-scratch/next-icon.png)

1. Napsauta tai napauta **FormScreen**-näytöllä peruutuskuvaketta ja aseta sen **OnSelect**-ominaisuudeksi tämä kaava:

    `ResetForm(EditForm1);Navigate(BrowseScreen, ScreenTransition.None)`

    ![Peruutuskuvake](./media/data-platform-create-app-scratch/cancel-icon.png)

1. Napsauta tai napauta valintamerkkikuvaketta ja aseta sen **OnSelect**-ominaisuudeksi tämä kaava:

    `SubmitForm(EditForm1); Navigate(BrowseScreen, ScreenTransition.None)`

    ![Valintamerkkikuvake](./media/data-platform-create-app-scratch/checkmark-icon.png)

1. Napsauta tai napauta **Lisää**-välilehdessä **Kuvakkeet** ja napsauta tai napauta **Roskakori**-kuvaketta.

1. Aseta **Roskakori**-kuvakkeen **Color**-ominaisuudeksi **White** ja sen **OnSelect**-ominaisuudeksi tämä kaava:

    `Remove(Accounts, BrowseGallery.Selected); Navigate(BrowseScreen, ScreenTransition.None)`

    ![Roskakorikuvake](./media/data-platform-create-app-scratch/trash-icon.png)

## <a name="test-the-app"></a>Sovelluksen testaus

1. Valitse vasemmanpuoleiselta siirtymäpalkilta **BrowseScreen** ja avaa Esikatselu painamalla F5-näppäintä (tai napsauttamalla tai napauttamalla Toista-kuvaketta lähellä oikeaa yläkulmaa).

    ![Esikatselun avaaminen](./media/data-platform-create-app-scratch/open-preview.png)

1. Vaihda luettelon lajittelujärjestystä nousevan ja laskevan välillä ja suodata luetteloa syöttämällä tilien nimien sisältämiä merkkejä.

1. Lisää tili, muokkaa lisäämääsi tiliä ja aloita tilin päivittäminen, mutta sitten peruuta muutokset ja poista tili.

## <a name="next-steps"></a>Seuraavat vaiheet

[Avaa yksi tai useampi esimerkkisovellus](open-and-run-a-sample-app.md) ja tutustu erilaisiin sovellustyyppeihin, joita voit luoda.

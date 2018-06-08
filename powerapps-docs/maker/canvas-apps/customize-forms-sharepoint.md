---
title: Lomakkeiden muokkaaminen | Microsoft Docs
description: Määritä, mitä tietoja näytetään, missä järjestyksessä ne näytetään ja missä ohjausobjekteissa ne näytetään.
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/17/2018
ms.author: anneta
ms.openlocfilehash: 98162ce4d291b976c816326efc5d4c6d4d18c870
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31829592"
---
# <a name="customize-forms-in-powerapps"></a>Lomakkeiden mukauttaminen PowerAppsissa
Mukauta **Näytä lomake**- ja **Muokkaa lomaketta** -ohjausobjekteja siten, että ne näyttävät merkittävimmät tiedot intuitiivisimmassa järjestyksessä, jotta käyttäjät voivat helposti ymmärtää ja päivittää tietoja.

Jokainen lomake käsittää yhden tai useampia kortteja, joista jokainen näyttää tiedot tietolähteen tietystä sarakkeesta. Noudattamalla tämän artikkelin ohjeita voit määrittää, mitkä kortit näkyvät lomakkeessa, ja voit siirtää kortteja ylös ja alas lomakkeessa.

Jos et tunne PowerAppsia, katso [PowerAppsin johdanto](getting-started.md).

## <a name="prerequisites"></a>Edellytykset
[Luo sovellus](data-platform-create-app.md) Common Data Service -palvelussa ja [mukauta sitten valikoimaa](customize-layout-sharepoint.md) kyseisessä sovelluksessa.

## <a name="show-and-hide-cards"></a>Korttien näyttäminen ja piilottaminen
1. Kirjaudu sisään [PowerAppsiin](http://web.powerapps.com).

    ![PowerApps-sivuston aloitussivu](./media/customize-forms-sharepoint/sign-in.png)


1. Avaa luomasi ja mukauttamasi sovellus.

1. Suodata elementtilistaa kirjoittamalla tai liittämällä **D** vasemman siirtymispalkin etsintäpalkkiin ja valitse sitten **DetailForm1** napsauttamalla tai napauttamalla sitä.

    ![Valitse tiedot-näyttö](./media/customize-forms-sharepoint/select-detailform.png)

1. Napsauta tai napauta oikeanpuoleisessa ruudussa **Tilit**-näppäintä näyttääksesi **tietoruudun**.

    ![Näytä tietoruutu](./media/customize-forms-sharepoint/show-data-pane.png)

1. Tyhjennä **tietoruudun** **Ensisijainen yhteyshenkilö**-, **Kuvaus**- ja **Osoite 1: Katu 2** -valintaruudut piilottaaksesi kyseiset kentät.

    ![Kenttäluettelo](./media/customize-forms-sharepoint/hide-fields.png)

1.  Näytä **tietoruudun** **Osoite 1: Postinumero** -valintaruutu valitsemalla se.

    ![Kenttäluettelo](./media/customize-forms-sharepoint/show-field.png)

## <a name="reorder-the-cards"></a>Järjestä kortit uudelleen
1. Vedä **tietoruudun** **Tilin nimi** -kenttä kenttäluettelon ylimmäiseksi.

    ![Siirrä kortti](./media/customize-forms-sharepoint/move-card.png)

    Samat muutokset näkyvät **DetailForm1**:n korteissa.

    ![Uudelleen järjestetyt kortit](./media/customize-forms-sharepoint/reordered-card.png)

1. Järjestä muut kortit uudelleen tähän järjestykseen:

    - Tilin nimi
    - Osoite 1: Katu 1
    - Osoite 1: Kaupunki
    - Osoite 1: Postinumero
    - Työntekijöiden määrä
    - Vuosittainen tuotto

1. Kirjoita tai liitä **Ed** vasemmanpuoleiseen siirtymispalkkiin ja valitse sitten **EditForm1** napsauttamalla tai napauttamalla sitä.

1. Toista edellisen ja nykyisen toimintosarjan vaiheet, jotta **EditForm1**:n kentät vastaavat **DetailForm1**:n kenttiä.

## <a name="run-the-app"></a>Sovelluksen suorittaminen
1. Kirjoita tai liitä **Br** vasemmanpuoleiseen siirtymispalkkiin ja valitse sitten **BrowseScreen1** napsauttamalla tai napauttamalla sitä.

2. Avaa esikatselutila painamalla F5-näppäintä (tai valitsemalla **Esikatselu**-kuvake oikean yläkulman läheltä).

    ![Esikatselun kuvake](./media/customize-forms-sharepoint/open-preview.png)

3. Napsauttamalla tai napauttamalla oikeassa yläkulmassa sijaitsevaa plus-kuvaketta voit lisätä tietueen **EditScreen1**:een.

    ![Tietueen lisääminen](./media/customize-forms-sharepoint/add-record.png)

4. Lisää haluamasi tiedot ja napsauta tai napauta valintamerkkikuvaketta oikeassa yläkulmassa tallentaaksesi muutokset ja palataksesi **BrowseScreen1**:een.

    ![Tietueen tallentaminen](./media/customize-forms-sharepoint/save-record.png)

5. Napsauta tai napauta juuri laatimasi kohteen nuolta tuodaksesi näkyviin tietoja kyseisestä kohteesta **DetailScreen1**:ssä.  

    ![Oikea nuoli](./media/customize-forms-sharepoint/right-arrow.png)

6. Napsauta tai napauta oikeassa yläkulmassa sijaitsevaa muokkauskuvaketta päivittääksesi tietueen **EditScreen1**:ssä.

    ![Tietueen muokkaaminen](./media/customize-forms-sharepoint/edit-record.png)

7. Muuta yhden tai useamman kentän tietoja ja napsauta tai napauta oikeassa yläkulmassa sijaitsevaa valintamerkkiä tallentaaksesi muutokset SharePoint-luetteloon ja palataksesi **DetailScreen1**:een.  

    ![Tallenna muutokset](./media/customize-forms-sharepoint/save-record.png)

8. Napsauttamalla tai napauttamalla oikean yläkulman lähellä sijaitsevaa roskakorikuvaketta voit poistaa juuri päivittämäsi tietueen ja palata **BrowseScreen1**:een.

    ![Tietueen poistaminen](./media/customize-forms-sharepoint/delete-record.png)

9. Sulje esikatselutila painamalla ESC-näppäintä (tai napsauttamalla tai napauttamalla vasemmassa yläkulmassa sijaitsevaa sulje-kuvaketta).

## <a name="next-steps"></a>Seuraavat vaiheet
- [Tallenna ja julkaise](save-publish-app.md) sovelluksesi.
- [Mukauta korttia](customize-card.md) sovelluksessasi.

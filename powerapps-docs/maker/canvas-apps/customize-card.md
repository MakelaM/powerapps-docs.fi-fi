---
title: Kortin mukauttaminen | Microsoft Docs
description: Muuta kortilla oletuksena näytettävää ohjausobjektia Tiedot- tai Muokkaa-lomakkeessa PowerAppsissa
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
ms.openlocfilehash: 31c0810b9da5a52bcd5cc3b28b6def858541e15b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42841782"
---
# <a name="customize-a-card-in-powerapps"></a>Kortin mukauttaminen PowerAppsissa
Voit suorittaa kortille perustason mukautuksia (poistamatta kortin lukitusta) esimerkiksi vaihtamalla sen ohjausobjektia. Edistyneitä mukautuksia varten kortin lukitus täytyy poistaa. Näihin kuuluu esimerkiksi sellaisen ohjausobjektin lisääminen, joka ei ole oletuksena käytettävissä kyseiselle kortille.

Katso yleiskatsaus aiheesta [Tutustu tietokortteihin](working-with-cards.md).

## <a name="prerequisites"></a>Edellytykset

* Lue, kuinka [voit lisätä ja määrittää ohjausobjekteja](add-configure-controls.md).
* Voit tarkastella vain tämän aiheen yleisiä käsitteitä, tai voit seurata sitä täsmällisesti suorittamalla näiden aiheiden vaiheet:

  1. [Sovelluksen luominen](data-platform-create-app.md).
  2. [Valikoiman mukauttaminen](customize-layout-sharepoint.md).
  3. [Lomakkeiden mukauttaminen](customize-forms-sharepoint.md).

## <a name="customize-a-locked-card"></a>Lukitun kortin mukauttaminen
Tässä prosessissa korvaat **[Tekstisyöte](controls/control-text-input.md)**-ohjausobjektin **[Liukusäädin](controls/control-slider.md)**-ohjausobjektilla poistamatta kortin lukitusta.

1. Kirjaudu sisään [PowerAppsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    ![PowerAppsin aloitussivu](./media/customize-card/sign-in.png)

1. Avaa luomasi ja mukauttamasi sovellus, valitse **EditForm1** ja sitten avaa **Tiedot**-ruutu valitsemalla oikeasta ruudusta **Accounts**.

1. Avaa vaihtoehtoluettelo valitsemalla luettelokentistä kohdan **Number of Employees** alaspäin osoittava nuoli ja valitse **Muokkaa liukusäädintä**.

    ![Avattava asetusluettelo numerokortille](./media/customize-card/card-selector.png)

    Näyttö päivittyy muutoksen mukaisesti.

    ![EditForm1 liukusäätimellä](./media/customize-card/add-slider.png)

## <a name="unlock-and-customize-a-card"></a>Kortin lukituksen poistaminen ja mukauttaminen
Tässä prosessissa poistetaan kortin lukitus ja **[Kytkin](controls/control-toggle.md)**-ohjausobjekti korvataan **[Valintaruutu](controls/control-check-box.md)**-ohjausobjektilla.

1. Näytä **EditForm1:ssä** **Send Marketing Materials** -kenttä.

    ![Send Marketing Materials -kentän näyttäminen](./media/customize-card/show-field.png)

2. Kun kortti on valittuna, avaa kortin lukitus napsauttamalla tai napauttamalla oikean ruudun yläosan kohtaa **Lisäasetukset** ja napsauta tai napauta lukkokuvaketta.

    ![Send Marketing Materials -kentän näyttäminen](./media/customize-card/unlock-card.png)

1. Poista kortista **Kytkin**-ohjausobjekti, lisää **Valintaruutu**-ohjausobjekti ja anna sille nimeksi **chkMktg**.

    ![Kytkimen korvaaminen valintaruudulla](./media/customize-card/add-checkbox.png)

1. Valitse kortti, jonka juuri päivitit.

    ![Kortin valinta](./media/customize-card/select-card.png)

1. Varmista, että oikeassa ruudussa on edelleen valittuna **Lisäasetukset**-välilehti ja napsauta tai napauta kohtaa **Enemmän vaihtoehtoja**.

    ![Enemmän vaihtoehtoja -painike](./media/customize-card/more-options.png)

1. Vaihda kortin **Update**-ominaisuudeksi tämä kaava:
<br>`chkMktg.Value`

1. Vaihda kortin virheviestin **Y**-ominaisuuden arvoksi tämä kaava:<br>
`chkMktg.Y + chkMktg.Height`

    ![Virheviestin valinta uudelle kortille](./media/customize-card/select-error.png)

1. Vaihda **chkMktg:n** **Text**-ominaisuudeksi **Kyllä**.

    Näyttö päivittyy muutosten mukaisesti ja virheet ratkaistaan.

    ![Lopullinen ruutu virheet ratkaistuina](./media/customize-card/final-screen.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Nyt kun ymmärrät sovelluksen luomisen sekä valikoiman, lomakkeen ja kortin mukauttamisen, voit [luoda oman sovelluksen alusta alkaen](data-platform-create-app-scratch.md).

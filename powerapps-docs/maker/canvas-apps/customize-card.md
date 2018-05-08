---
title: Kortin mukauttaminen | Microsoft Docs
description: Muuta kortilla oletuksena näytettävää ohjausobjektia Tiedot- tai Muokkaa-lomakkeessa PowerAppsissa
services: ''
suite: powerapps
documentationcenter: ''
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 0a46aeaf5e37a4c461daae65a01a00c38ed53414
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="customize-a-card-in-powerapps"></a>Kortin mukauttaminen PowerAppsissa
Voit suorittaa kortille perustason mukautuksia (poistamatta kortin lukitusta) esimerkiksi vaihtamalla sen ohjausobjektia. Edistyneitä mukautuksia varten kortin lukitus täytyy poistaa. Näihin kuuluu esimerkiksi sellaisen ohjausobjektin lisääminen, joka ei ole oletuksena käytettävissä kyseiselle kortille.

Katso yleiskatsaus aiheesta [Tutustu yhteyskortteihin](working-with-cards.md).

## <a name="prerequisites"></a>Edellytykset

* Lue, kuinka [voit lisätä ja määrittää ohjausobjekteja](add-configure-controls.md).
* Voit tarkastella vain tämän aiheen yleisiä käsitteitä, tai voit seurata sitä täsmällisesti suorittamalla näiden aiheiden vaiheet:

  1. [Sovelluksen luominen](data-platform-create-app.md).
  2. [Valikoiman mukauttaminen](customize-layout-sharepoint.md).
  3. [Lomakkeiden mukauttaminen](customize-forms-sharepoint.md).

## <a name="customize-a-locked-card"></a>Lukitun kortin mukauttaminen
Tässä prosessissa korvaat **[Tekstisyöte](controls/control-text-input.md)**-ohjausobjektin **[Liukusäädin](controls/control-slider.md)**-ohjausobjektilla poistamatta kortin lukitusta.

1. Kirjaudu sisään [PowerAppsiin](http://web.powerapps.com).

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

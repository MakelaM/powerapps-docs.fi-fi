---
title: Pikaopas sovelluksen luomiseen PowerAppsissa SharePointista | Microsoft Docs
description: Luo sovellus automaattisesti PowerAppsissa SharePoint-luettelon tiedonhallintaa varten
services: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/12/2018
ms.author: anneta
ms.openlocfilehash: 86e255f6c3fbb77b60820108c4a21dd8c0cba532
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-for-generating-an-app-in-powerapps-from-sharepoint"></a>Pikaopas sovelluksen luomiseen PowerAppsissa SharePointista

Tässä pikaoppaassa käytetään PowerAppsia ensimmäisen sovelluksen luomiseen automaattisesti SharePointissa luomasi luettelon pohjalta. Tässä sovelluksessa voit selata luettelon kaikkia kohteita, tarkastella yksittäisen kohteen tietoja sekä luoda, päivittää tai poistaa kohteen.

Tässä pikaoppaassa voit tutustua käsitteisiin ja tekniikoihin, jos sinulla on luettelo SharePointissa. Noudata tätä pikaopasta tarkasti ja luo SharePoint Online -sivustossa luettelo nimeltä **SimpleApp**, joka sisältää sarakkeen nimeltä **Otsikko**. Luo luetteloon **Vanilla**-, **Chocolate**- ja **Strawberry**-merkinnät.

Voit luoda paljon monimutkaisemman luettelon, jossa on useita erityyppisiä sarakkeita, esimerkiksi tekstille, päivämäärille, numeroille ja valuutalle. Sovelluksen luonnin periaatteet eivät muutu. Voit myös luoda sovelluksen paikallisen SharePoint-sivuston luettelosta, jos [muodostat yhteyden sivustoon](connect-to-sharepoint.md) tietoyhdyskäytävän kautta.

Jos sinulla ei ole PowerApps-käyttöoikeutta, voit [rekisteröityä ilmaiseksi](../signup-for-powerapps.md).

## <a name="generate-an-app"></a>Sovelluksen luominen
1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com).

    ![PowerAppsin aloitussivu](./media/app-from-sharepoint/sign-in.png)

1. Vie osoitin kohdan **Tee tämän kaltaisia sovelluksia** kohtaan **Aloita tiedoista** ja valitse **Tee tämä sovellus**.

    ![Asetus sovelluksen luomiseksi](./media/app-from-sharepoint/make-this-app.png)

1. Valitse SharePoint-ruudusta **Puhelinasettelu**.

    ![Asetus sovelluksen luomiseksi](./media/app-from-sharepoint/sharepoint-tile.png)

1. Valitse **Yhdistä suoraan** -vaihtoehdon ollessa valittuna **Luo**.

    ![Yhteyden luominen](./media/app-from-sharepoint/create-connection.png)

1. Kirjoita tai liitä **Yhdistä SharePoint-sivustoon** -kohtaan SharePoint Online -sivuston URL-osoite ja valitse sitten **Siirry**.

    Sisällytä vain sivuston URL-osoite (ei luettelon nimeä), kuten seuraavassa esimerkissä:<br>`https://microsoft.sharepoint.com/teams/Contoso`

1. Valitse **Valitse luettelo**, **SimpleApp** ja sitten **Connect**.

Muutaman minuutin päästä sovelluksesi avautuu selausnäyttöön, jossa näytetään luettelo luomistasi kohteista. Jos luettelossa on tietoa useammassa sarakkeessa kuin vain **Otsikko**-sarakkeessa, sovellus näyttää nämä tiedot. Lähellä näytön yläosaa on otsikkorivi, jolla näytetään kuvakkeet luettelon päivittämiseen ja lajitteluun sekä kohteen luontiin luettelossa. Otsikkopalkin alla oleva hakukenttä mahdollistaa luettelon suodattamisen kirjoittamasi tai liittämäsi tekstin perusteella. 

![Selaa-näyttö](./media/app-from-sharepoint/browse-screen.png)

Haluat luultavasti tehdä sovellukseen lisää muutoksia, ennen kuin käytät sitä tai jaat sen muille. Suosittelemme tallentamaan tähän asti tehdyt työt painamalla Ctrl-S ennen jatkamista. Anna sovellukselle nimi ja valitse sitten **Tallenna**.

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä pikaoppaassa loimme sovelluksen, jolla hallitaan SharePoint-luettelon tietoja. Seuraava vaihe on sovelluksen luominen monimutkaisemmasta luettelosta ja sen mukauttaminen (alkaen selausnäytöstä), jotta se vastaa paremmin tarpeitasi.

> [!div class="nextstepaction"]
> [Oletusselausnäytön mukauttaminen](customize-layout-sharepoint.md)
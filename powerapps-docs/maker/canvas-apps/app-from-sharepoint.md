---
title: Pohjaan perustuvan sovelluksen luominen SharePoint-luettelosta | Microsoft Docs
description: Luo pohjaan perustuva sovellus automaattisesti PowerAppsissa SharePoint-luettelon tiedonhallintaa varten
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 08/09/2018
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: af06a3707073498df65f782fc634c1e93b1760c5
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994088"
---
# <a name="generate-a-canvas-app-in-powerapps-from-a-sharepoint-list"></a>Pohjaan perustuvan sovelluksen luominen PowerAppsissa SharePoint-luettelosta

Tässä aiheessa käytetään PowerAppsia pohjaan perustuvan sovelluksen luomiseen automaattisesti SharePoint-luettelon kohteiden pohjalta. Voit luoda sovelluksen joko PowerAppsissa tai SharePoint Onlinessa. PowerAppsissa voit luoda sovelluksen paikallisen SharePoint-sivuston luettelosta, jos [muodostat yhteyden sivustoon](connections/connection-sharepoint-online.md#create-a-connection) tietoyhdyskäytävän kautta.

Luotava sovellus sisältää kolme näyttöä:

- Selausnäytössä voit selata luettelon kaikkia kohteita.
- Tietonäytössä voit näyttää kaikki tiedot yhdestä luettelon kohteesta.
- Muokkausnäytössä voit luoda kohteen tai päivittää aiemmin luodun kohteen tietoja.

Voit käyttää tämän ohjeaiheen käsitteitä ja tekniikoita mihin tahansa SharePoint-luetteloon. Noudata ohjeita tarkasti:

1. Luo SharePoint Online -sivustossa luettelo nimeltä **SimpleApp**.
2. Luo **Title**-sarakkeeseen **Vanilla**-, **Chocolate**- ja **Strawberry**-merkinnät.

Sovelluksen luomisen periaatteet pysyvät samana, vaikka tekisit paljon monimutkaisemman luettelon, jossa on useita erityyppisiä sarakkeita, esimerkiksi tekstille, päivämäärille, numeroille ja valuutalle.

> [!IMPORTANT]
> PowerApps ei tue kaikkia SharePoint-tietotyyppejä. Katso lisätietoja kohdasta [Tunnetut ongelmat](connections/connection-sharepoint-online.md#known-issues).

## <a name="generate-an-app-from-within-powerapps"></a>Sovelluksen luominen PowerAppsissa

1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Vie hiiren osoitin **Tee oma sovelluksesi** -osiossa **Aloita tiedoista** -kohdan päälle ja valitse **Tee tämä sovellus**.

    ![Sovelluksen luontiasetus](./media/app-from-sharepoint/start-from-data.png)

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

## <a name="generate-an-app-from-within-sharepoint-online"></a>Sovelluksen luominen SharePoint Onlinessa

Jos luot mukautetun luettelon sovelluksen SharePoint Online -komentopalkin kautta, sovellus näytetään kyseisen luettelon näkymänä. Voit verkkoselaimen ohella suorittaa sovelluksen myös iOS- tai Android-laitteella.

1. Avaa SharePoint Onlinessa mukautettu luettelo, valitse komentopalkista **PowerApps** ja valitse sitten **Luo sovellus**.

    ![Sovelluksen luominen](./media/app-from-sharepoint/generate-new-app.png)

2. Kirjoita avautuvaan paneeliin sovelluksesi nimi ja valitse **Luo**.

    ![Nimeä sovellus](./media/app-from-sharepoint/app-name.png)

    Verkkoselaimeesi avautuu uusi välilehti, jolla näytetään SharePoint-luetteloosi pohjautuva automaattisesti luotu sovellus. Sovellus näkyy PowerApps Studiossa, jossa voit mukauttaa sitä.

    ![Oletussovellus](./media/app-from-sharepoint/default-app.png)

3. (valinnainen) Päivitä SharePoint-luettelon selainvälilehti valitsemalla se ja painamalla F5-näppäintä. Suorita sovelluksesi tai hallitse sitä näiden ohjeiden avulla:

    - Jos haluat suorittaa sovelluksen erillisellä selaimen välilehdellä, valitse **Avaa**.
    - Jos haluat antaa organisaatiosi muiden jäsenten suorittaa sovelluksen, valitse **Tee tästä näkymästä julkinen**.

        Jos haluat antaa muiden muokata sovellusta, [jakaa se](share-app.md) **Voi muokata** -oikeuksilla.

    - Poista näkymä SharePointista valitsemalla **Poista tämä näkymä**.

        Poista sovellus PowerAppsista [poistamalla sovellus](delete-app.md).

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä ohjeaiheessa loimme sovelluksen, jolla hallitaan SharePoint-luettelon tietoja. Seuraava vaihe on sovelluksen luominen monimutkaisemmasta luettelosta ja sen mukauttaminen (alkaen selausnäytöstä), jotta se vastaa paremmin tarpeitasi.

> [!div class="nextstepaction"]
> [Oletusselausnäytön mukauttaminen](customize-layout-sharepoint.md)

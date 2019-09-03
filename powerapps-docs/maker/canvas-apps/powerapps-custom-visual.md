---
title: PowerAppsin mukautettu visualisointi Power BI:lle | Microsoft Docs
description: Toimintosarja ja rajoitukset sellaisen pohjaan perustuvan sovelluksen upottamiseen, joka käyttää samaa tietolähdettä ja joka voidaan suodattaa muiden Power BI -raporttikohteiden mukaisesti
author: chmoncay
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 08/30/2019
ms.author: chmoncay
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 562811ebce59660d6033585868afd42da46442d5
ms.sourcegitcommit: 25a85b462515cb64f3f2b114864a682abf803f4a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/03/2019
ms.locfileid: "70213931"
ms.PowerAppsDecimalTransform: true
---
# <a name="powerapps-custom-visual-for-power-bi"></a>PowerAppsin mukautettu visualisointi Power BI:lle

Power BI mahdollistaa merkityksellisten tietojen saamisen ja paremman päätöksenteon. PowerApps antaa puolestaan kaikkien luoda ja käyttää sovelluksia, jotka muodostavat yhteyden yritystietoihin. Käyttämällä PowerAppsin mukautettua visualisointia voit välittää kontekstin huomioon ottavaa tietoa pohjaan perustuvaan sovellukseen, joka päivittyy reaaliajassa, kun teet muutoksia raporttiin. Sovelluksesi käyttäjät saavat merkityksellistä liiketoimintatietoa, ja he voivat suorittaa toimintoja suoraan Power BI -raporteista ja koontinäytöltä.

## <a name="using-the-powerapps-custom-visual"></a>PowerAppsin mukautetun visualisoinnin käyttäminen

Katsotaan nyt vaadittavia vaiheita PowerAppsin mukautetun visualisoinnin käyttämiseksi Power BI -raportissasi.

1. Hanki mukautettu visualisointi [AppSource](https://appsource.microsoft.com/product/power-bi-visuals/WA104381378?tab=Overview)-palvelusta tai tuo se suoraan Power BI -palvelussa.

    ![Mukautettu visualisointi Marketplacessa](./media/powerapps-custom-visual/powerapps-store.png) 

2. Lisää PowerApps-visualisointi raporttiisi ja määritä siihen liittyvät tietokentät.

    ![Raporttitietojen valitseminen](./media/powerapps-custom-visual/add-visual-set-data.png)

    Voit valita olemassa olevan sovelluksen tai luo uuden, mutta raportti on julkaistava Power BI -palvelussa ja avattava Microsoft Edgessä tai Google Chromessa.

3.  Jos päätät luoda sovelluksen, voit valita missä ympäristössä se luodaan.

    ![Uusi tai olemassa oleva sovellus](./media/powerapps-custom-visual/create-new-or-choose-app.png)

    Jos päätät käyttää olemassa olevaa sovellusta, visualisointi kehottaa sinua avaamaan sovelluksen PowerAppsissa. Visualisointi määrittää sitten vaadittavat komponentit sovelluksessasi, jotta Power BI voi lähettää tietoa PowerAppsiin.

    Jos luot uuden sovelluksen, PowerApps luo yksinkertaisen sovelluksen, jossa vaadittavat komponentit on määritetty valmiiksi.

    ![Uusi sovellus](./media/powerapps-custom-visual/new-app.png)

4. Nyt voit käyttää vaiheessa 2 määrittämiäsi tietokenttiä PowerApps Studiossa. `PowerBIIntegration`-objekti toimii samalla tavalla kuin muutkin PowerAppsin vain luku -tietolähteet ja -kokoelmat. Voit käyttää objektia minkä tahansa ohjausobjektin täyttämiseen tai liittämiseen ja suodattamiseen muiden tietolähteiden kanssa.

    ![Mukautettu kaava](./media/powerapps-custom-visual/custom-formula.png)

    Tämä kaava liittää Power BI -tiedon asiakkaan tietolähteeseen: `LookUp(Customer;Customer_x0020_Name=First(PowerBIIntegration.Data).Customer_Name)`

   Power BI -raportti ja käynnistetty PowerApps Studio -esiintymä jakavat reaaliaikaisen tietoyhteyden. Kun molemmat ovat avoinna, voit suodattaa tai muuttaa raportin tietoa ja nähdä, että päivitetty tieto vaikuttavaa välittömästi sovellukseesi PowerApps Studiossa.

5. Kun olet suorittanut loppuun sovelluksen luomisen tai muutosten tekemisen sovellukseen, tallenna ja julkaise sovellus PowerAppsissa, jotta näet sovelluksen Power BI -raportissa.

6. Kun olet tyytyväinen tekemiisi muutoksiin, muista jakaa PowerApps-sovellus raporttisi käyttäjien kanssa ja tallentaa sitten raportti.

7. Näin olet luonut raportin, jossa käyttäjäsi voivat suorittaa toimintoja, kun he saavat merkityksellistä tietoa tiedoistasi.

    ![Raportin käsittely](./media/powerapps-custom-visual/working-report.gif)

    Jos haluat tehdä muutoksia sovellukseen, avaa raportti muokkaustilassa, napsauta tai napauta PowerApps-visualisoinnissa **Enemmän vaihtoehtoja** ( **. . .** ) ja valitse **Muokkaa**.

    ![Sovelluksen muokkaaminen](./media/powerapps-custom-visual/edit-app.png)

## <a name="limitations-of-the-powerapps-custom-visual"></a>PowerAppsin mukautetun visualisoinnin rajoitukset

Seuraavat rajoitukset koskevat Powerappsin mukautettua visualisointia:

- Jos muutat visualisointiin liittyviä tietokenttiä, sinun on muokattava sovellusta Power BI -palvelussa valitsemalla kolme pistettä (...) ja **Muokkaa**. Muussa tapauksessa muutoksia ei lisätä PowerAppsiin, ja sovellus käyttäytyy odottamattomasti.
- Powerappsin mukautettu visualisointi ei voi käynnistää Power BI raporttien ja Power BI tieto lähteiden päivittämistä Power BI Desktop sisältä. Jos kirjoitat tietoja sovelluksesta takaisin samaan tieto lähteeseen kuin raportti, muutoksesi eivät näy heti Power BI Desktop. Muutokset otetaan käyttöön seuraavassa ajoitetussa päivityksessä.
- PowerAppsin mukautettu visualisointi ei voi suodattaa tietoa tai lähettää tietoa takaisin raporttiin.
- Sinun on jaettava PowerApps-sovellus raportistasi erillisenä. Lue lisätietoja [sovellusten jakamisesta PowerAppsissa](share-app.md).
- Power BI-raporttipalvelin ja mobiilisovellus Power BI eivät tue Powerappsin mukautettua visualisointia.
- Jos käytät PowerBIIntegration. Refresh ()-funktioita, sinun on käytettävä lähdettä, joka tukee [Directqueryä](https://docs.microsoft.com/en-us/power-bi/desktop-directquery-data-sources) , ja tieto yhteydet on luotava käyttämällä directquery-menetelmää.

> [!NOTE]
> Suosittelemme, että julkaiset raporttisi ensin Power BI-palvelu ja sitten luot tai muokkaat sovelluksia.

## <a name="browser-support"></a>Selain tuki

Seuraavassa taulukossa on luettelo selain Supportability for View-, Create-ja muokata-toiminnoista powerappsin mukautetusta visualisoinnista. Tuetut selaimet ja toiminnot tunnistetaan valinta merkillä ( &check; ).

|Selain|Näkymä|Luoda|Muokata
|-|-|-|-
|Microsoft Edge|&check;|&check;|&check;
|Internet Explorer 11|&check;
|Google Chrome|&check;|&check;|&check;
|Safari|&check;
|Mozilla Firefox
|Kaikki muut selaimet

## <a name="next-steps"></a>Seuraavat vaiheet

* Käy läpi yksinkertainen [vaiheittainen opetusohjelma](embed-powerapps-powerbi.md).
* Tutustu videoomme [](https://aka.ms/powerappscustomvisualvideo).

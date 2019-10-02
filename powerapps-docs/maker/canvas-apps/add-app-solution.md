---
title: Kangas sovelluksen luominen ratkaisussa | Microsoft Docs
description: Luo Powerappsissa kangas sovellus ratkaisuun, jotta voit ottaa sovelluksen käyttöön toisessa ympäristössä
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: ''
ms.date: 10/23/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3703fc5e36b38c7894300bc2074453716ddd9946
ms.sourcegitcommit: 60fd1792430b9f3da08ec161cb2277506d795e3a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/01/2019
ms.locfileid: "71705077"
---
# <a name="create-a-canvas-app-from-within-a-solution"></a>Kangas sovelluksen luominen ratkaisun sisältä

Luo sovellus ratkaisun sisältä, jos haluat esimerkiksi ottaa sovelluksen käyttöön eri ympäristössä. Ratkaisut voivat sisältää paitsi sovelluksia myös mukautettuja entiteettejä, asetus joukkoja ja muita komponentteja. Voit nopeasti mukauttaa ympäristöä monin eri tavoin luomalla sovelluksia ja muita komponentteja ratkaisun sisältä, viemällä ratkaisun ja tuomalla sen sitten toiseen ympäristöön.

Lisä tietoja ratkaisuista on kohdassa [ratkaisujen yleiskatsaus](../common-data-service/solutions-overview.md).

## <a name="prerequisite"></a>Edellytys

Jos haluat noudattaa tämän ohje aiheen vaiheita, sinun on siirryttävä ympäristöön, joka sisältää Common Data Service-tieto kannan.

## <a name="create-a-solution"></a>Ratkaisun luominen

Voit ohittaa tämän toiminnon, jos sinulla on jo sovellus, johon haluat luoda sovelluksen tai johon haluat linkittää sovelluksen.

1. [Kirjaudu sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin ja sitten (tarvittaessa) Vaihda sopivaan ympäristöön:

    - Jos haluat luoda sovelluksen ratkaisun sisältä, Vaihda mihin tahansa ympäristöön, joka sisältää Common Data Service-tieto kannan.
    - Jos haluat linkittää olemassa olevan sovelluksen ratkaisuun, Vaihda ympäristöön, joka sisältää kyseisen sovelluksen.

1. Valitse vasemmassa siirtymis palkissa **ratkaisut**.

    > [!div class="mx-imgBorder"]
    > ![Ratkaisu vaihtoehto]vasemmassa siirtymis palkin ratkaisut-vaihto ehdon vasemmassa siirtymis(./media/add-app-solution/left-nav.png "palkissa")

1. Valitse otsikko rivin alla olevasta palkista **Uusi liuos**.

    > [!div class="mx-imgBorder"]
    > ![New-Solution-vaihto ehto](./media/add-app-solution/banner-new-solution.png "Banner New-Solution-asetuksessa bannerissa")

1. Määritä näyttöön tulevassa ikkunassa ratkaisun näyttö nimi, julkaisija ja versio.

    > [!div class="mx-imgBorder"]
    > Uuden(./media/add-app-solution/configure-new-solution.png "ratkaisun") ![uusien ratkaisujen asetusten asetukset]

    Nimi (ilman väli lyöntejä) muodostetaan automaattisesti määrittämäsi näyttö nimen perusteella, mutta voit halutessasi mukauttaa luotua nimeä. Voit määrittää ympäristön oletus julkaisijan ja **1,0** -version, jos sinulla ei ole erityistarvetta kyse isillä alueilla.

1. Valitse vasemman yläkulman lähellä **Tallenna ja sulje**.

    > [!div class="mx-imgBorder"]
    > ![Tallenna uusi liuos](./media/add-app-solution/save-new-solution.png "Tallenna uusi liuos")

## <a name="create-a-canvas-app-in-a-solution"></a>Kangas sovelluksen luominen ratkaisussa

Voit luoda tyhjän kangas sovelluksen ratkaisun sisältä. Et voi luoda automaattisesti kolmen näytön sovellusta tai mukauttaa mallia tai malli sovellusta ratkaisun sisältä.

1. [Kirjaudu sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin.

1. Vaihda tarvittaessa ympäristöön, joka sisältää ratkaisun, johon haluat luoda pohjaan kuuluvan sovelluksen.

1. Valitse vasemmassa siirtymis palkissa **ratkaisut**.

    > [!div class="mx-imgBorder"]
    > ![Ratkaisu vaihtoehto]vasemmassa siirtymis palkin ratkaisut-vaihto ehdon vasemmassa siirtymis(./media/add-app-solution/left-nav.png "palkissa")

1. Valitse ratkaisu luettelosta ratkaisu, jonka pohjalle haluat luoda pohjaan kuuluvan sovelluksen.

1. Valitse otsikko rivin alla olevasta palkista **uusi** > **sovellus** > **kangas sovellus**ja valitse sitten luotavan sovelluksen lomake kerroin (Puhelin tai tabletti).

    > [!div class="mx-imgBorder"]
    > ![Vaihto ehdot sovelluksen luomi seksi ratkaisun](./media/add-app-solution/new-option.png "asetuksissa sovelluksen luomi seksi ratkaisulle")

    PowerApps Studio avautuu tyhjällä pohjalla toisessa selain väli lehdessä.

1. Luo sovelluksesi (tai tee vähintään yksi muutos) ja tallenna sitten tekemäsi muutokset.

1. Päivitä ratkaisusi komponenttien **luettelo valitsemalla selain** väli lehdeltä, jossa valitsit ratkaisusi.

    > [!div class="mx-imgBorder"]
    > ![Done-painikkeen](./media/add-app-solution/done-button.png "tehtävä painike")

    Uusi sovelluksesi näkyy tämän ratkaisun osien luettelossa. Jos tallennat muutokset sovellukseesi, ne näkyvät ratkaisussa olevassa versiossa.

## <a name="link-an-existing-canvas-app-to-a-solution"></a>Olemassa olevan kangas sovelluksen linkittäminen ratkaisuun

Jos haluat linkittää sovelluksen ratkaisuun, molempien on oltava samassa ympäristössä, ja sovelluksen on oltava luotu ratkaisun sisältä.

1. [Kirjaudu sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin.

1. Vaihda tarvittaessa ympäristöön, joka sisältää ratkaisun, johon haluat linkittää sovelluksen.

1. Valitse vasemmassa siirtymis palkissa **ratkaisut**.

    > [!div class="mx-imgBorder"]
    > ![Ratkaisu vaihtoehto]vasemmassa siirtymis palkin ratkaisut-vaihto ehdon vasemmassa siirtymis(./media/add-app-solution/left-nav.png "palkissa")

1. Valitse ratkaisujen luettelosta ratkaisu, johon haluat linkittää sovelluksen.

1. Valitse otsikko rivin alla olevassa palkissa **Lisää olemassa oleva** > **sovellus** > -**kangas sovellus**.

    > [!div class="mx-imgBorder"]
    > ![Banner-asetukset linkittäen]aiemmin luodun sovelluksen(./media/add-app-solution/add-existing.png "Banner-asetukset olemassa olevan sovelluksen linkittämistä varten")

    Näyttöön tulee luettelo tämän ympäristön ratkaisussa luoduista kangas sovelluksista.

1. Valitse sovellus luettelosta sovellus, jonka haluat linkittää ratkaisuun, ja valitse sitten **Lisää**.

    > [!div class="mx-imgBorder"]
    > ![Lisää painikkeen](./media/add-app-solution/add-button.png "lisääminen-painike")

## <a name="known-limitations"></a>Tunnetut rajoitukset

Lisä tietoja tunne tuista rajoituksista on kohdassa [ratkaisujen käyttäminen Powerappsissa](../common-data-service/use-solution-explorer.md#known-limitations). 

## <a name="next-steps"></a>Seuraavat vaiheet

- Luo tai linkitä sovelluksia ja [muita komponentteja](../common-data-service/use-solution-explorer.md), kuten entiteettejä, työn kulkuja ja koonti näyttöjä, ratkaisuusi.
- [Vie ratkaisusi](../common-data-service/import-update-export-solutions.md) , jotta voit ottaa sen käyttöön toiseen ympäristöön, appsourceen ja niin edelleen.

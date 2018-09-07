---
title: Näytön lisääminen pohjaan perustuvaan sovellukseen ja näyttöjen välillä siirtyminen | Microsoft Docs
description: Lisää pohjaan perustuvaan sovellukseen näyttö ja siirry näytöstä toiseen eteen- ja taaksepäin osoittavilla nuolilla PowerAppsissa
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 07/10/2017
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f7e03402690cb448a10c64882fdb6d79713cffcb
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42858903"
---
# <a name="add-a-screen-to-a-canvas-app-and-navigate-between-screens"></a>Näytön lisääminen pohjaan perustuvaan sovellukseen ja näyttöjen välillä siirtyminen

Luo usean näytön pohjaan perustuva sovellus ja lisää tapoja, joilla käyttäjät voivat siirtyä niiden välillä.

## <a name="prerequisites"></a>Edellytykset

* Lue, miten [ohjausobjekti määritetään](add-configure-controls.md).
* Luo tai avaa sovellus.

## <a name="add-and-rename-a-screen"></a>Lisää ja nimeä näyttö uudelleen

1. Napsauta tai napauta **Aloitus**-välilehdestä **Uusi näyttö**.

    ![Lisää Aloitus-välilehteen Näyttö-vaihtoehto](./media/add-screen-context-variables/add-screen.png)

2. Napsauta tai napauta oikeanpuoleisessa ruudussa näytön nimeä (suoraan **Ominaisuudet**-välilehden yläpuolella), ja kirjoita sitten uusi nimi **Lähde**.

    ![Nimeä oletusnäyttö uudelleen](./media/add-screen-context-variables/name-source-screen.png)

3. Lisää toinen näyttö ja anna sille nimeksi **Kohde**.

    ![Vasemman siirtymispalkin kaksi näyttöä](./media/add-screen-context-variables/two-screens-in-nav.png)

## <a name="add-navigation"></a>Lisää siirtyminen
1. Avaa **Lisää**-välilehti **Lähde**-näytön ollessa valittuna, napsauta tai napauta **Kuvakkeet** ja napsauta tai napauta sitten **Seuraava nuoli**.  

    ![Lisää-välilehden Muodot-vaihtoehto](./media/add-screen-context-variables/add-next-arrow.png)

2. (valinnainen) Siirrä nuolta niin, että se näkyy näytön oikeassa alakulmassa.

3. Napsauta tai napauta **Toiminto**-välilehteä nuolen ollessa edelleen valittuna ja napsauta tai napauta sitten **Siirry**.

    Nuolen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi määritetään automaattisesti **Siirry**-toiminto.  

    ![OnSelect-ominaisuudeksi on määritetty Siirry-toiminto](./media/add-screen-context-variables/onselect-default.png)

    Kun käyttäjä napsauttaa tai napauttaa nuolta, **Kohde**-näyttö voimistuu esiin.

4. Lisää **Kohde**-näyttöön **takaisin-nuoli** ja määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**Navigate(Lähde, ScreenTransition.Fade)**

5. Avaa esikatselutila (![](./media/add-screen-context-variables/preview.png) tai paina F5-näppäintä) ja siirry sitten näyttöjen välillä napsauttamalla tai napauttamalla lisäämiäsi nuolia.

6. Palaa oletustyötilaan painamalla **Esc**.

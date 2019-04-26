---
title: Näytön lisääminen pohjaan perustuvaan sovellukseen ja näyttöjen välillä siirtyminen | Microsoft Docs
description: Lisää pohjaan perustuvaan sovellukseen näyttö ja siirry näytöstä toiseen eteen- ja taaksepäin osoittavilla nuolilla PowerAppsissa
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 02/03/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b6f83d21b2964dac7c4925d45efdf11a3a1e6b02
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "63321376"
---
# <a name="add-a-screen-to-a-canvas-app-and-navigate-between-screens"></a>Näytön lisääminen pohjaan perustuvaan sovellukseen ja näyttöjen välillä siirtyminen

Luo usean näytön pohjaan perustuva sovellus ja lisää tapoja, joilla käyttäjät voivat siirtyä niiden välillä.

## <a name="add-and-rename-a-screen"></a>Lisää ja nimeä näyttö uudelleen

1. Valitse **aloitus** -välilehden **uuden näytön**, ja valitse sitten näytön, jonka haluat lisätä tyyppi.

    ![Lisää Aloitus-välilehteen Näyttö-vaihtoehto](./media/add-screen-context-variables/add-screen.png)

2. Valitse oikeanpuoleisessa ruudussa näytön nimeä (vain yläpuolella **ominaisuudet** välilehdessä), ja kirjoita sitten **tietolähteen**.

    ![Nimeä oletusnäyttö uudelleen](./media/add-screen-context-variables/name-source-screen.png)

3. Lisää toinen näyttö ja anna sille nimeksi **Kohde**.

    ![Vasemman siirtymispalkin kaksi näyttöä](./media/add-screen-context-variables/two-screens-in-nav.png)

## <a name="reorder-screens"></a>Näyttöjen järjestäminen uudelleen

Osoita näyttö, jossa haluat siirtää tai alas, valitse kolme pistettä, joka näkyy vasemmassa siirtymispalkissa ja valitse sitten **ylöspäin** tai **alaspäin**.

![Näytön järjestäminen uudelleen](./media/add-screen-context-variables/reorder-screen.png)

> [!NOTE]
> Kun sovellus avataan, yläosassa oleva ohjausobjektien hierarkkisessa luettelossa näytön yleensä näkyy ensimmäisenä. Mutta voit määrittää eri näyttöön määrittämällä **[OnStart](controls/control-screen.md)** ominaisuuden näyttämään kaavan, joka sisältää **[Navigate](functions/function-navigate.md)** funktio.

## <a name="add-navigation"></a>Lisää siirtyminen

1. Kanssa **tietolähteen** näytön ollessa valittuna, Avaa **Lisää** -välilehden **kuvakkeet**, ja valitse sitten **seuraava-nuolta**.  

    ![Lisää-välilehden Muodot-vaihtoehto](./media/add-screen-context-variables/add-next-arrow.png)

2. (valinnainen) Siirrä nuolta niin, että se näkyy näytön oikeassa alakulmassa.

3. Nuolen ollessa edelleen valittuna ja valitse **toiminto** välilehti ja valitse sitten **Navigate**.

    Nuolen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi määritetään automaattisesti **Siirry**-toiminto.

    ![OnSelect-ominaisuudeksi on määritetty Siirry-toiminto](./media/add-screen-context-variables/onselect-default.png)

    Kun käyttäjä valitsee olevaa nuolta **kohde** näyttö voimistuu esiin.

4. Lisää **Kohde**-näyttöön **takaisin-nuoli** ja määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    `Navigate(Source, ScreenTransition.Fade)`

5. Kun pidät alhaalla Alt-näppäintä, Näytä tai piilota valitsemalla nuoli kunkin näytön näyttöjen välillä.

## <a name="more-information"></a>Lisätietoja

[Näytön ohjausobjektin viittauksesta](controls/control-screen.md)
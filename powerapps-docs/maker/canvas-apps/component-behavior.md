---
title: Osien toiminta kaavat | Microsoft Docs
description: Käynnistä sovellus suorittamaan vähintään yksi tehtävä, kun komponenttipohjainen toiminto suoritetaan.
author: yifwang
ms.service: powerapps
ms.topic: article
ms.date: 05/24/2019
ms.author: yifwang
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c8ec4edd835f12fb6fccf04ba0fb27f1e755cac0
ms.sourcegitcommit: ea3ab5926541c60a9e7c17f52f937c9812d48c71
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/05/2019
ms.locfileid: "70310074"
---
# <a name="behavior-formulas-for-components"></a>Komponenttien toiminta kaavat

> [!IMPORTANT]
> Ominaisuus on edelleen kokeellinen, ja se on oletus arvon mukaan poistettu käytöstä. Lisä tietoja on kohdassa [Experimental-ja Preview-ominaisuudet](working-with-experimental.md).

Määritä vähintään yksi [toiminta kaava](working-with-formulas-in-depth.md) , joka suoritetaan, kun tapahtuma käynnistää osan esiintymien muutoksen. Voit esimerkiksi määrittää komponentin **Onreset** -ominaisuudeksi yhden tai useamman kaavan, joka suorittaa alustuksen, tyhjentää syötteen ja nollata arvot, kun **reset** -funktiolla suoritetaan komponentti esiintymiä.

## <a name="onreset"></a>OnReset

Kun osa on valittuna, valitse **Onreset** avattavasta ominaisuuksien luettelosta (kaava rivin oikealla puolella) ja kirjoita vähintään yksi kaava.

> [!div class="mx-imgBorder"]
> ![OnReset-esimerkki](./media/component-behavior/example-onreset.png)

Voit testata **Onreset**-määritystä määrittämällä ohjaus objektin nollaamaan komponentin. Voit esimerkiksi määrittää painikkeen **onselect** -ominaisuudeksi tämän kaavan: **Nollaa** (*Componentname*)

> [!div class="mx-imgBorder"]
> ![Palauta-painike](./media/component-behavior/reset-button.png)

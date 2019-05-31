---
title: Osien toimintakaavoissa | Microsoft Docs
description: Käynnistä sovellus ja yhden tai useamman tehtävän osaa perustuvan toiminnon ilmetessä.
author: yifwang
ms.service: powerapps
ms.topic: article
ms.date: 05/24/2019
ms.author: yifwang
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7275395a4c21afaebc60e9635461afc08f5e84a0
ms.sourcegitcommit: afe958805d8e1cfa4fdf02c7bceea947185f71f2
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/30/2019
ms.locfileid: "66420310"
---
# <a name="behavior-formulas-for-components"></a>Toimintakaavoissa osia

> [!IMPORTANT]
> Tämä ominaisuus on edelleen kokeellinen ja käytöstä oletusarvon mukaan. Jos haluat lisätietoja, katso [kokeelliseen ja esikatselu](working-with-experimental.md).

Määritä vähintään yksi [toimintakaavoissa](working-with-formulas-in-depth.md) , joka suoritetaan, kun tapahtuma käynnistää osa esiintymät muutos. Voit esimerkiksi määrittää komponentin **OnReset** kaavat, jotka suorittavat alustus, poista syöte ja nollaa ominaisuuden arvot, kun **vaihtaa** funktion suorittaminen osa-esiintymille.

## <a name="onreset"></a>OnReset ##

Valitun osan, valitse **OnReset** avattavan luettelon ominaisuudet (oikeassa laidassa kaavarivin), ja kirjoita sitten yhden tai useamman kaavan.

> [!div class="mx-imgBorder"]
> ![OnReset Esimerkki](./media/component-behavior/example-onreset.png)

Testattava **OnReset**, vaihtaa osa ohjausobjektin määrittäminen. Voit esimerkiksi määrittää **OnSelect** ominaisuuden painikkeen tämä kaava: **Palauta**(*ladattavissa*)

> [!div class="mx-imgBorder"]
> ![Palauta-painike](./media/component-behavior/reset-button.png)

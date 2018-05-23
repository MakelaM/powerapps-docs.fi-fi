---
title: 'Muoto- ja kuvakeohjausobjektit: viittaus | Microsoft Docs'
description: Muoto- ja kuvakeohjausobjekteja koskevaa tietoa, kuten ominaisuuksia ja esimerkkejä
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 7a71695460453816dd5c63dad8477cb7ccc703d7
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>Muoto- ja kuvakeohjausobjektit PowerAppsissa
Grafiikkoja, joille voi määrittää ulkoasu- ja toimintaominaisuuksia.

## <a name="description"></a>Kuvaus
Tällaisia ohjausobjekteja ovat muun muassa nuolet, geometriset muodot, toimintokuvakkeet ja symbolit, joille voi määrittää täytön, koon ja sijainnin kaltaisia ominaisuuksia. Lisäksi voit määrittää niiden **[OnSelect](properties-core.md)**-ominaisuuden. Tällöin sovellus reagoi tietyllä tavalla, kun käyttäjä napsauttaa tai napauttaa ohjausobjektia.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[OnSelect](properties-core.md)** – Sovelluksen reagointitapa, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

## <a name="additional-properties"></a>Lisäominaisuudet
**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä pitää hiiren osoitinta sen päällä.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin näppäimistösyötteisen reunan paksuus.

**[Näkyvissä](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**Navigate**( *ScreenName*, *ScreenTransition* )](../functions/function-navigate.md)

## <a name="example"></a>Esimerkki
1. Anna oletusarvoiselle **[Näyttö](control-screen.md)**-ohjausobjektille nimi **Kohde**, lisää **[Otsikko](control-text-box.md)**-ohjausobjekti ja määritä sen **[Teksti](properties-core.md)**-ominaisuus näyttämään **Kohde**.
   
    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?
2. Lisää **[Näyttö](control-screen.md)**-ohjausobjekti ja anna sille nimi **Lähde**.
3. Lisää **Lähde**-ohjausobjektiin **Muoto**-ohjausobjekti ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**Navigate(Target, ScreenTransition.Fade)**
4. Paina F5-näppäintä ja napsauta tai napauta sitten **Muoto**-ohjausobjektia.
   
    **Kohde**-näyttö tulee näkyviin.
5. (valinnainen) Palaa oletustyötilaan painamalla Esc-näppäintä. Lisää **Muoto**-ohjausobjekti **Kohde**-näyttöön ja määritä **Muoto**-ohjausobjektin **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**Navigate(Source, ScreenTransition.Fade)**


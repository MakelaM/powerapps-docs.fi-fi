---
title: 'Ympyräkaavio-ohjausobjekti: viittaus | Microsoft Docs'
description: Ympyräkaavio-ohjausobjektin ominaisuudet ja joitakin esimerkkejä
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
ms.openlocfilehash: 1388eac45e5086f677cb83c8db9593fe01a9819f
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="pie-chart-control-in-powerapps"></a>PowerAppsin Ympyräkaavio-ohjausobjekti
Ohjausobjekti, joka näyttää suhteellisia arvoja verrattuna toisiinsa.

## <a name="description"></a>Kuvaus
Lisää **Ympyräkaavio**-ohjausobjekti, jos haluat näyttää suhteellisia tietoja taulukosta, joka sisältää selitteet kauimpana vasemmalla olevassa sarakkeessa ja arvot siitä seuraavassa sarakkeessa.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Items](properties-core.md)** – Ohjausobjektiin, kuten valikoimaan, luetteloon tai kaavioon, näkyviin tulevan tiedon lähde.

**ShowLabels** – Näytetäänkö ympyräkaaviossa arvot, jotka liittyvät lohkoihin.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva**vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Color](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus pois käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**Explode** – Lohkojen etäisyys toisistaan ympyräkaaviossa.

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**ItemBorderColor** – Ympyräkaavion lohkoja ympäröivien reunojen väri.

**ItemBorderThickness** – Ympyräkaavion lohkoja ympäröivien reunojen paksuus.

**ItemColorSet** – Kunkin kaavion arvopisteen väri.

**LabelPosition** – Selitteiden sijainti ympyräkaaviossa suhteessa sen lohkoihin.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Size](properties-text.md)** – Ohjausobjektiin ilmaantuvan tekstin fonttikoko.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="related-functions"></a>Liittyvät funktiot
[**Max**( *TietoLähde*, *SarakkeenNimi* )](../functions/function-aggregates.md)

## <a name="example"></a>Esimerkki
1. Lisää **[Painike](control-button.md)**-ohjausobjekti ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **Collect(Revenue2015, {Product:"Europa", Revenue:27000}, {Product:"Ganymede", Revenue:26300}, {Product:"Callisto", Revenue:29200})**
   
    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?
   
    Haluatko lisätietoja **[Collect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
2. Palaa oletustyötilaan painamalla F5, napsauta tai napauta **[Painike](control-button.md)**-ohjausobjektia ja paina sitten Esc.
3. Lisää **Ympyräkaavio**-ohjausobjekti ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi **Revenue2015**.
   
    **Ympyräkaavio**-ohjausobjekti näyttää tuotteiden liikevaihtotiedot verrattuna muihin tuotteisiin.


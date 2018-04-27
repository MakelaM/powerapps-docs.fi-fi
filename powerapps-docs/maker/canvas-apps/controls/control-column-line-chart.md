---
title: 'Pylväskaavio- ja viivakaavio-ohjausobjektit: viittaus | Microsoft Docs'
description: Pylväskaavio- ja viivakaavio-ohjausobjekteja koskevaa tietoa, kuten ominaisuuksia ja esimerkkejä
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
ms.openlocfilehash: 039b267394ef6be5e3038fa0b07149f69fee6a51
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/12/2018
---
# <a name="column-chart-and-line-chart-controls-in-powerapps"></a>Pylväskaavio- ja viivakaavio-ohjausobjektit PowerAppsissa
Ohjausobjektit, jotka esittävät tiedon x- ja y-akselisina kaavioina.

## <a name="description"></a>Kuvaus
**Pylväskaavio**-ohjausobjekti tai **viivakaavio**-ohjausobjekti käsittävät oletusarvoisesti useita ohjausobjekteja, jotka on ryhmitelty yhteen. Nämä ohjausobjektit sisältävät otsikon, tiedon ja tietojen selitteen.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Items](properties-core.md)** – Ohjausobjektiin, kuten valikoimaan, luetteloon tai kaavioon, näkyviin tulevan tiedon lähde.

**NumberOfSeries** – Pylväs- tai viivakaavion edustamien tietosarakkeiden määrä.

## <a name="all-properties"></a>Kaikki ominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva**vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Color](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) tai vain tarkastella tietoja (**Näytä**) vai onko ominaisuus kokonaan poissa käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-ominaisuuden asetuksena on **Ei käytössä**.

**[Font](properties-text.md)**  – Näytössä näkyvän fonttiperheen nimi.

**GridStyle** – Näytetäänkö pysty- tai viivakaaviossa sen x-akseli, y-akseli, molemmat tai ei kumpaakaan.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**ItemColorSet** – Kunkin kaavion arvopisteen väri.

**ItemsGap** – Pylväskaavion pylväiden välinen etäisyys.

* **ItemsGap**-ominaisuus on käytettävissä **pylväskaavio**-ohjausobjektin kanssa, mutta ei **viivakaavio**-ohjausobjektin kanssa.

**Markers** – Näytetäänkö pylväs- tai viivakaaviossa kunkin arvopisteen arvo.

**MarkerSuffix** – Teksti, joka näytetään jokaisen pylväskaavion arvon jälkeen, jos pylväskaavion **Markers**-ominaisuudeksi on määritetty **tosi**.

* **MarkerSuffix**-ominaisuus on käytettävissä **pylväskaavio**-ohjausobjektin kanssa, mutta ei **viivakaavio**-ohjausobjektin kanssa.

**MinimumBarWidth** – Pylväskaavion pylväiden kapein mahdollinen leveys.

* **MinimumBarWidth**-ominaisuus on käytettävissä **pylväskaavio**-ohjausobjektin kanssa, mutta ei **viivakaavio**-ohjausobjektin kanssa.

**[OnSelect](properties-core.md)** – Sovelluksen reagointitapa, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**SeriesAxisMax** – Pylväs- tai viivakaavion y-akselin enimmäisarvo.

* **SeriesAxisMax**-ominaisuus on käytettävissä **pylväskaavio**-ohjausobjektin kanssa, mutta ei **viivakaavio**-ohjausobjektin kanssa.

**SeriesAxisMin** – Luku, joka määrittää pylväskaavion y-akselin vähimmäisarvon.

* **SeriesAxisMin**-ominaisuus on käytettävissä **pylväskaavio**-ohjausobjektin kanssa, mutta ei **viivakaavio**-ohjausobjektin kanssa.

**[Size](properties-text.md)** – Ohjausobjektiin ilmaantuvan tekstin fonttikoko.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Leveys eli ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (näytön, jos pääsäilöä ei ole).

**XLabelAngle** – Pylväs- tai viivakaavion x-akselin alapuolella olevien otsikoiden kulma.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (näytön, jos pääsäilöä ei ole).

**YAxisMax** – Viivakaavion y-akselin enimmäisarvo.

* **YAxisMax**-ominaisuus on käytettävissä **pylväskaavio**-ohjausobjektin kanssa, mutta ei **viivakaavio**-ohjausobjektin kanssa.

**YAxisMin** – Viivakaavion y-akselin vähimmäisarvo.

* **YAxisMin**-ominaisuus on käytettävissä **pylväskaavio**-ohjausobjektin kanssa, mutta ei **viivakaavio**-ohjausobjektin kanssa.

**YLabelAngle** – Pylväs- tai viivakaavion y-akselin vieressä olevien otsikoiden kulma.

## <a name="related-functions"></a>Liitetyt toiminnot
[**Max**( *DataSource*, *ColumnName* )](../functions/function-aggregates.md)

## <a name="example"></a>Esimerkki
1. Lisää **[painike](control-button.md)** ohjausobjekti ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **Collect(Tuotto, {Vuosi:"2013", Europa:24000, Ganymede:22300, Callisto:21200}, {Vuosi:"2014", Europa:26500, Ganymede:25700, Callisto:24700},{Vuosi:"2014", Europa:27900, Ganymede:28300, Callisto:25600})**
   
    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?
   
    Haluatko lisätietoja **[Collect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
2. Palaa oletustyötilaan painamalla F5, napsauta tai napauta **[painike](control-button.md)** ohjausobjektia ja paina sitten Esc.
3. Lisää **pylväskaavio**- tai **viivakaavio**-ohjausobjekti, määritä sen **[Items](properties-core.md)**-ominaisuuden arvoksi **Tuotto** ja määritä sen **NumberOfSeries** -ominaisuuden arvoksi **3**.
   
    Ohjausobjekti näyttää kunkin tuotteen tuottotiedot kolmen vuoden ajalta.


---
title: 'Pylväskaavio- ja viivakaavio-ohjausobjektit: viittaus | Microsoft Docs'
description: Pylväskaavio- ja viivakaavio-ohjausobjekteja koskevaa tietoa, mukaan lukien ominaisuuksia ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9c290d28db7ae35d33f4ceb2cd56c3a3ad79b01c
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61559376"
---
# <a name="column-chart-and-line-chart-controls-in-powerapps"></a>Pylväskaavio- ja viivakaavio-ohjausobjektit PowerAppsissa
Ohjausobjektit, jotka esittävät tiedon x- ja y-akselisina kaavioina.

## <a name="description"></a>Kuvaus
**Pylväskaavio** ja **Viivakaavio** ovat ryhmiteltyjä ohjausobjekteja. Kukin ryhmä sisältää kolme ohjausobjektia: otsikon **[selitteen](control-text-box.md)**, kuvan kaaviosta ja kaavion **selitteen**.

## <a name="chart-key-properties"></a>Kaavion tärkeimmät ominaisuudet
**[Kohteet](properties-core.md)** – Tietolähde, joka näkyy ohjausobjektissa, kuten valikoimassa, luettelossa tai kaaviossa.

**NumberOfSeries** – Pylväs- tai viivakaavion edustamien tietosarakkeiden määrä.

## <a name="additional-chart-properties"></a>Muut kaavion ominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Color](properties-color-border.md)** – Ohjausobjektin tekstin väri.

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**), vai onko ominaisuus poistettu käytöstä (**Disabled**).

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**GridStyle** – Näytetäänkö pysty- tai viivakaaviossa sen x-akseli, y-akseli, molemmat tai ei kumpaakaan.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**ItemColorSet** – Kunkin kaavion arvopisteen väri.

**ItemsGap** – Pylväskaavion pylväiden välinen etäisyys.

* **ItemsGap**-ominaisuus on käytettävissä **pylväskaavio**-ohjausobjektin kanssa, mutta ei **viivakaavio**-ohjausobjektin kanssa.

**Merkit** – Näytetäänkö pylväs- tai viivakaaviossa kunkin arvopisteen arvo.

**MarkerSuffix** – Teksti, joka näytetään jokaisen pylväskaavion arvon jälkeen, jos pylväskaavion **Merkit**-ominaisuudeksi on määritetty **true**.

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

**[Size](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**XLabelAngle** – Pylväs- tai viivakaavion x-akselin alapuolella olevien otsikoiden kulma.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

**YAxisMax** – Viivakaavion y-akselin enimmäisarvo.

* **YAxisMax**-ominaisuus on käytettävissä **viivakaavio**-ohjausobjektin kanssa, mutta ei **pylväskaavio**-ohjausobjektin kanssa.

**YAxisMin** – Viivakaavion y-akselin vähimmäisarvo.

* **YAxisMin**-ominaisuus on käytettävissä **viivakaavio**-ohjausobjektin kanssa, mutta ei **pylväskaavio**-ohjausobjektin kanssa.

**YLabelAngle** – Pylväs- tai viivakaavion y-akselin vieressä olevien otsikoiden kulma.

## <a name="related-functions"></a>Liitetyt toiminnot
[**Max**( *DataSource*, *ColumnName* )](../functions/function-aggregates.md)

## <a name="example"></a>Esimerkki
1. Lisää **[painike](control-button.md)** ohjausobjekti ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **Collect(Tuotto, {Vuosi:"2013", Europa:24000, Ganymede:22300, Callisto:21200}, {Vuosi:"2014", Europa:26500, Ganymede:25700, Callisto:24700},{Vuosi:"2014", Europa:27900, Ganymede:28300, Callisto:25600})**
   
    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?
   
    Haluatko lisätietoja **[Kerää](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
2. Palaa oletustyötilaan painamalla F5, napsauta tai napauta **[painike](control-button.md)** ohjausobjektia ja paina sitten Esc.
3. Lisää **pylväskaavio**- tai **viivakaavio**-ohjausobjekti, määritä sen **[Kohteet](properties-core.md)**-ominaisuuden arvoksi **Tuotto** ja määritä sen **NumberOfSeries** -ominaisuuden arvoksi **3**.
   
    Ohjausobjekti näyttää kunkin tuotteen tuottotiedot kolmen vuoden ajalta.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* kaikki kohteet **ItemColorSet**-ominaisuudessa
* kaikki kohteet **ItemColorSet**-ominaisuudessa ja taustaväri
* **[Väri](properties-color-border.md)** ja taustaväri

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[Selite](control-text-box.md)** on pakollinen ennen kuvaa kaaviosta. Selite toimii kuvan otsikkona.
* Harkitse yhteenvedon lisäämistä kaaviokuvasta. Esimerkiksi ”Viivakaaviossa näkyy myynnin tasainen kasvu tämän vuoden maaliskuun ja elokuun välillä”.

    > [!NOTE]
  > Kaaviokuvat ja **kaavioselitteet** on piilotettu näytönlukuohjelmien käyttäjiltä. Tiedot esitetään heille taulukkomuodossa. He voivat myös selata painikkeita, joilla valitaan kaavion tietoja.

### <a name="low-vision-support"></a>Tuki heikkonäköisille
* **Kaavioselite** on oltava, jos useampi kuin yksi sarja näkyy.
* Jos valitset **GridStyle**-asetukseksi GridStyle.All, molemmat akselit näkyvät. Näin kaikki käyttäjät voivat määrittää tarkasti tietojen asteikon.
* **Pylväskaavion** **Merkit**-ominaisuudeksi kannattaa määrittää **true**. Tämä auttaa heikkonäköisiä käyttäjiä määrittämään sarakkeen arvon.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.

    > [!NOTE]
  > Kun näppäimistön käyttäjät siirtyvät kaaviossa, he voivat käydä läpi painikkeita, joilla valitaan kaavion tietoja.

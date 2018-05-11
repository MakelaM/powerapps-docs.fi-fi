---
title: 'Ympyräkaavio-ohjausobjekti: viittaus | Microsoft Docs'
description: Ympyräkaavio-ohjausobjektin ominaisuudet ja joitakin esimerkkejä
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: bda839765d797bf87590f037221b116bad781657
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="pie-chart-control-in-powerapps"></a>PowerAppsin Ympyräkaavio-ohjausobjekti
Ohjausobjekti, joka näyttää suhteellisia arvoja verrattuna toisiinsa.

## <a name="description"></a>Kuvaus
Lisää **Ympyräkaavio**-ohjausobjekti, jos haluat näyttää suhteellisia tietoja taulukosta, joka sisältää selitteet kauimpana vasemmalla olevassa sarakkeessa ja arvot siitä seuraavassa sarakkeessa.

Tämä ohjausobjekti on ryhmitelty ohjausobjekti, joka sisältää kolme ohjausobjektia: otsikon **[selitteen](control-text-box.md)**, kuvan kaaviosta ja kaavion **selitteen**.

## <a name="chart-key-properties"></a>Kaavion tärkeimmät ominaisuudet
**[Items](properties-core.md)** – Ohjausobjektiin, kuten valikoimaan, luetteloon tai kaavioon, näkyviin tulevan tiedon lähde.

**ShowLabels** – Näytetäänkö ympyräkaaviossa arvot, jotka liittyvät lohkoihin.

## <a name="additional-chart-properties"></a>Muut kaavion ominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Color](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

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

**[Size](properties-text.md)** – Ohjausobjektissa näytettävän tekstin fonttikoko.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

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


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* kaikki kohteet **ItemColorSet**-ominaisuudessa
* kaikki kohteet **ItemColorSet**-ominaisuudessa ja taustaväri
* **[Väri](properties-color-border.md)** ja taustaväri

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[Selite](control-text-box.md)** on pakollinen ennen kuvaa kaaviosta. Selite toimii kuvan otsikkona.

    > [!NOTE]
> Kaaviokuvat ja **kaavioselitteet** on piilotettu näytönlukuohjelmien käyttäjiltä. Tiedot esitetään heille taulukkomuodossa. He voivat myös selata painikkeita, joilla valitaan kaavion tietoja.

### <a name="low-vision-support"></a>Tuki heikkonäköisille
* **Selite** on pakollinen.
* Suosittelemme asettamaan **ShowLabels**-ominaisuuden arvoksi **tosi**. Tämä auttaa heikkonäköisiä käyttäjiä selvittämään nopeasti mitä kukin ympyräkaavion sektori edustaa.
* Suosittelemme asettamaan **LabelPosition**-ominaisuuden arvoksi **LabelPosition.Outside**. Tämä parantaa selitteiden luettavuutta yhtenäistämällä värikontrastia.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.

    > [!NOTE]
> Kun näppäimistön käyttäjät siirtyvät kaaviossa, he voivat käydä läpi painikkeita, joilla valitaan kaavion tietoja.

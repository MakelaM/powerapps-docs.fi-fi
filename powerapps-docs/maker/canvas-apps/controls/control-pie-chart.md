---
title: 'Ympyräkaavio-ohjausobjekti: viittaus | Microsoft Docs'
description: Ympyräkaavio-ohjausobjektin ominaisuudet ja joitakin esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7a7c69be8fea874a6d911fa26909a7b3ece0bce5
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986392"
ms.PowerAppsDecimalTransform: true
---
# <a name="pie-chart-control-in-powerapps"></a>PowerAppsin Ympyräkaavio-ohjausobjekti
Ohjausobjekti, joka näyttää suhteellisia arvoja verrattuna toisiinsa.

## <a name="description"></a>Kuvaus
Lisää **Ympyräkaavio**-ohjausobjekti, jos haluat näyttää suhteellisia tietoja taulukosta, joka sisältää selitteet kauimpana vasemmalla olevassa sarakkeessa ja arvot siitä seuraavassa sarakkeessa.

Tämä ohjausobjekti on ryhmitelty ohjausobjekti, joka sisältää kolme ohjausobjektia: otsikon **[selitteen](control-text-box.md)** , kuvan kaaviosta ja kaavion **selitteen**.

## <a name="chart-key-properties"></a>Kaavion tärkeimmät ominaisuudet
**[Kohteet](properties-core.md)** – Tietolähde, joka näkyy ohjausobjektissa, kuten valikoimassa, luettelossa tai kaaviossa.

**ShowLabels** – Näytetäänkö ympyräkaaviossa arvot, jotka liittyvät lohkoihin.

## <a name="additional-chart-properties"></a>Muut kaavion ominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Väri](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)** -asetuksena on **Ei käytössä**.

**Explode** – Lohkojen etäisyys toisistaan ympyräkaaviossa.

**[Font](properties-text.md)**  – Näytössä näkyvän fonttiperheen nimi.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**ItemBorderColor** – Ympyräkaavion lohkoja ympäröivien reunojen väri.

**ItemBorderThickness** – Ympyräkaavion lohkoja ympäröivien reunojen paksuus.

**ItemColorSet** – Kunkin kaavion arvopisteen väri.

**LabelPosition** – Selitteiden sijainti ympyräkaaviossa suhteessa sen lohkoihin.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Size](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**Max**( *DataSource*; *ColumnName* )](../functions/function-aggregates.md)

## <a name="example"></a>Esimerkki
1. Lisää **[Painike](control-button.md)** -ohjausobjekti ja määritä sen **[OnSelect](properties-core.md)** -ominaisuudeksi seuraava kaava:<br>
   **Collect(Revenue2015; {Product:"Europa"; Revenue:27000}; {Product:"Ganymede"; Revenue:26300}; {Product:"Callisto"; Revenue:29200})**
   
    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?
   
    Haluatko lisätietoja **[Kerää](../functions/function-clear-collect-clearcollect.md)** -funktiosta tai [muista funktioista](../formula-reference.md)?
2. Palaa oletustyötilaan painamalla F5, napsauta tai napauta **[painike](control-button.md)** ohjausobjektia ja paina sitten Esc.
3. Lisää **Ympyräkaavio**-ohjausobjekti ja aseta sen **[Items](properties-core.md)** -ominaisuudeksi **Revenue2015**.
   
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
* **[TabIndex](properties-accessibility.md)** -kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.

    > [!NOTE]
  > Kun näppäimistön käyttäjät siirtyvät kaaviossa, he voivat käydä läpi painikkeita, joilla valitaan kaavion tietoja.

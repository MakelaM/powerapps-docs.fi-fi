---
title: 'HTML-tekstin ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja, kuten ominaisuudet ja esimerkkejä, HTML-tekstin ohjausobjektista
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
ms.openlocfilehash: bb652f3ba6decad7cb6f93007eaec6340f230ca1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="html-text-control-in-powerapps"></a>HTML-tekstin ohjausobjekti PowerAppsissa
Ruutu, joka näyttää tekstiä ja muuntaa HTML-tunnisteet muotoiluksi.

## <a name="description"></a>Kuvaus
**HTML-tekstin** ohjausobjekti näyttää tekstin ja numerot, mutta se voi lisäksi muuntaa HTML-tunnisteet, kuten sitovat välilyönnit.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**[Color](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[Font](properties-text.md)**  – Näytössä näkyvän fonttiperheen nimi.

**HTMLText** – HTML-tekstin ohjausobjektissa näkyvä teksti, joka voi sisältää HTML-tunnisteita.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva**vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus pois käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Ei käytössä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[Size](properties-text.md)** – Ohjausobjektiin ilmaantuvan tekstin fonttikoko.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka näytetään, kun kohdistin on ohjausobjektin päällä.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="related-functions"></a>Liittyvät toiminnot
[**Find**( *FindString*, *WithinString* )](../functions/function-find.md)

## <a name="example"></a>Esimerkki
1. Lisää **[Selite](control-text-box.md)**-ohjausobjekti, anna sille nimi **Source** ja määritä sen **[Text](properties-core.md)**-ominaisuudeksi tämä merkkijono:

\<p> Olemme suorittaneet erittäin \&nbsp; \&quot; perusteellisen \&quot; globalisoinnin ja lokalisoinnin. \<p>

Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?

1. Lisää **HTML-tekstin** ohjausobjekti ja määritä sen **HTMLText**-ominaisuudeksi tämä arvo:<br>
   **Source.Text**
   
     **HTML-tekstin** ohjausobjekti näyttää saman tekstin kuin **[Selite](control-text-box.md)**-ohjausobjekti, mutta se muuntaa tunnisteet sopiviksi merkeiksi.


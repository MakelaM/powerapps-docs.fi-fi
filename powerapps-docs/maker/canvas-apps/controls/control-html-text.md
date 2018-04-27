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
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/12/2018
---
# <a name="html-text-control-in-powerapps"></a>HTML-tekstin ohjausobjekti PowerAppsissa
Ruutu, joka näyttää tekstiä ja muuntaa HTML-tunnisteet muotoiluksi.

## <a name="description"></a>Kuvaus
**HTML-tekstin** ohjausobjekti näyttää tekstin ja numerot, mutta se voi lisäksi muuntaa HTML-tunnisteet, kuten sitovat välilyönnit.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**[Väri](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[Fontti](properties-text.md)**  – Näytössä näkyvän fonttiperheen nimi.

**HTML-teksti** – HTML-tekstin ohjausobjektissa näkyvä teksti, joka voi sisältää HTML-tunnisteita.

## <a name="additional-properties"></a>Lisäominaisuudet
**[Reunan väri](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[Reunan tyyli](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[Reunan paksuus](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Näyttötila](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus pois käytöstä (**Ei käytössä**).

**[Käytöstä poistetun reunan väri](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[Näyttötila](properties-core.md)**-asetuksena on **Ei käytössä**.

**[Käytöstä poistetun täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[Näyttötila](properties-core.md)**-asetuksena on **Ei käytössä**.

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[Valintareunaväri](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**[Valittaessa](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[Täyttö alhaalla](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[Täyttö vasemmalla](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[Täyttö oikealla](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[Täyttö ylhäällä](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[Koko](properties-text.md)** – Ohjausobjektiin ilmaantuvan tekstin fonttikoko.

**[Työkaluvihje](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="related-functions"></a>Liittyvät toiminnot
[**Find**( *FindString*, *WithinString* )](../functions/function-find.md)

## <a name="example"></a>Esimerkki
1. Lisää **[Selite](control-text-box.md)**-ohjausobjekti, anna sille nimi **Source** ja määritä sen **[Text](properties-core.md)**-ominaisuudeksi tämä merkkijono:

\<p> Olemme suorittaneet erittäin \&nbsp; \&quot; perusteellisen \&quot; globalisoinnin ja lokalisoinnin. \<p>

Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?

1. Lisää **HTML-tekstin** ohjausobjekti ja määritä sen **HTMLText**-ominaisuudeksi tämä arvo:<br>
   **Source.Text**
   
     **HTML-tekstin** ohjausobjekti näyttää saman tekstin kuin **[Selite](control-text-box.md)**-ohjausobjekti, mutta se muuntaa tunnisteet sopiviksi merkeiksi.


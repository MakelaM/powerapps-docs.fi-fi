---
title: 'Muoto- ja kuvakeohjausobjektit: viittaus | Microsoft Docs'
description: Muoto- ja kuvakeohjausobjekteja koskevaa tietoa, kuten ominaisuuksia ja esimerkkejä
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
ms.openlocfilehash: e2c5d384c29766d6c30db8aa85ad4d7d45b48e04
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31838144"
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>Muoto- ja kuvakeohjausobjektit PowerAppsissa
Grafiikkoja, joille voi määrittää ulkoasu- ja toimintaominaisuuksia.

## <a name="description"></a>Kuvaus
Tällaisia ohjausobjekteja ovat muun muassa nuolet, geometriset muodot, toimintokuvakkeet ja symbolit, joille voi määrittää täytön, koon ja sijainnin kaltaisia ominaisuuksia. Lisäksi voit määrittää niiden **[OnSelect](properties-core.md)**-ominaisuuden. Tällöin sovellus reagoi tietyllä tavalla, kun käyttäjä napsauttaa tai napauttaa ohjausobjektia.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[OnSelect](properties-core.md)** – Sovelluksen reagointitapa, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**), vai onko ominaisuus poistettu käytöstä (**Disabled**).

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä pitää hiiren osoitinta sen päällä.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

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


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraava koskee vain grafiikkoja, joita käytetään painikkeina tai jotka eivät muutoin ole pelkkiä koristeita.

Kuvakkeet:
* **[Color](properties-color-border.md)** ja **[Fill](properties-color-border.md)**
* Muut [tavalliset värikontrastivaatimukset](../accessible-apps-color.md) pätevät (käytettäessä painikkeena)

Reunoja sisältävät muodot:
* **[BorderColor](properties-color-border.md)** ja ohjausobjektin ulkopuolinen väri
* **[FocusedBorderColor](properties-color-border.md)** ja väri ohjausobjektin ulkopuolella (käytettäessä painikkeena)

Muodot, jotka eivät sisällä reunoja:
* **[Fill](properties-color-border.md)** ja ohjausobjektin ulkopuolinen väri
* **[PressedFill](properties-color-border.md)** ja väri ohjausobjektin ulkopuolella (käytettäessä painikkeena)
* **[HoverFill](properties-color-border.md)** ja väri ohjausobjektin ulkopuolella (käytettäessä painikkeena)

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava olemassa, jos kuvaa käytetään painikkeena tai muussa kuin koristeellisessa tarkoituksessa.
* **[AccessibleLabel](properties-accessibility.md)** on oltava tyhjä tai tyhjä merkkijono **""**, jos kuva on pelkästään koristeena. Näin näytönlukuohjelmat voivat ohittaa kuvan.
* **[AccessibleLabel](properties-accessibility.md)** voi olla tyhjä tai tyhjä merkkijono **""**, jos kuvassa esitetään tarpeetonta tietoa.
    * Esimerkiksi **Asetukset**-kuvake ja **[AccessibleLabel](properties-accessibility.md)**-objekti, jonka arvo on **Asetukset**. Kuvaketta ei käytetä painikkeena. Se on **[selitteen](control-text-box.md)** vieressä, jossa lukee myös **Asetukset**. Näytönlukuohjelmat lukevat kuvakkeen tekstinä **Asetukset**, ja sitten myös selitteen tekstinä **Asetukset**. Tämä on tarpeetonta. Tässä tapauksessa kuvake ei tarvitse **[AccessibleLabel](properties-accessibility.md)**-objektia.

    > [!IMPORTANT]
> Näytönlukuohjelmat lukevat aina kuvakkeet ja muodot, joilla **[TabIndex](properties-accessibility.md)** on suurempi tai yhtä suuri kuin 0, riippumatta siitä, onko **[AccessibleLabel](properties-accessibility.md)** tyhjä vai ei. Tämä johtuu siitä, että ne hahmonnetaan painikkeina. Jos **[AccessibleLabel](properties-accessibility.md)**-objektia ei ole, näytönlukuohjelmat lukevat kuvan **painikkeena**.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-objektin arvo on oltava suurempi tai yhtä suuri kuin 0, jos kuvaa käytetään painikkeena. Näin näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistusilmaisimien on oltava selvästi näkyvissä, jos kuvaa käytetään painikkeena. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.

    > [!NOTE]
> Jos **[TabIndex](properties-accessibility.md)** on suurempi tai yhtä suuri kuin 0, kuvake tai muoto hahmonnetaan painikkeena. Kuvan visuaalinen ulkoasu ei muutu, mutta näytönlukuohjelmat tunnistavat kuvan oikein painikkeeksi. Jos **[TabIndex](properties-accessibility.md)** on pienempi kuin 0, kuvake tai muoto tunnistetaan kuvana.

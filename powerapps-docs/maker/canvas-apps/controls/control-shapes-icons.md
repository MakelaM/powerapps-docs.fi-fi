---
title: 'Muoto- ja kuvakeohjausobjektit: viittaus | Microsoft Docs'
description: Muoto- ja kuvakeohjausobjekteja koskevaa tietoa, kuten ominaisuuksia ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 88e0a74d2c25d1d2f5f571f4d1850417d1aab9ca
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "63318425"
ms.PowerAppsDecimalTransform: true
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>Muoto- ja kuvakeohjausobjektit PowerAppsissa
Grafiikkoja, joille voi määrittää ulkoasu- ja toimintaominaisuuksia.

## <a name="description"></a>Kuvaus
Tällaisia ohjausobjekteja ovat muun muassa nuolet, geometriset muodot, toimintokuvakkeet ja symbolit, joille voi määrittää täytön, koon ja sijainnin kaltaisia ominaisuuksia. Voit myös määrittää niiden **[OnSelect](properties-core.md)** ominaisuus niin, että sovellus reagoi, jos käyttäjä valitsee ohjausobjektin.

## <a name="key-properties-icons-and-shapes"></a>Tärkeimmät ominaisuudet (kuvakkeet ja muodot)
**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[OnSelect](properties-core.md)**  – miten sovellus reagoi, kun käyttäjä valitsee ohjausobjektin.

## <a name="key-properties-icons-only"></a>Tärkeimmät ominaisuudet (vain kuvakkeet)

**Kuvake** -kuvaketta näyttääksesi tyyppi (esimerkiksi **ArrowDown** tai **ShoppingCart**). 

**Kierto** -arvo Kierrä kuvaketta. 

**Väri** -kuvake nimen tai RGBA arvojen väri.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**), vai onko ominaisuus poistettu käytöstä (**Disabled**).

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[PressedBorderColor](properties-color-border.md)**  – kun käyttäjä valitsee tämän ohjausobjektin ohjausobjektin reunan väri.

**[PressedFill](properties-color-border.md)**  – ohjausobjektiin, kun käyttäjä valitsee tämän ohjausobjektin taustaväri.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot

[**Navigate**( *ScreenName*; *ScreenTransition* )](../functions/function-navigate.md)

## <a name="example"></a>Esimerkki

1. Anna oletusarvoiselle **[Näyttö](control-screen.md)** -ohjausobjektille nimi **Kohde**, lisää **[Otsikko](control-text-box.md)** -ohjausobjekti ja määritä sen **[Teksti](properties-core.md)** -ominaisuus näyttämään **Kohde**.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

1. Lisää **[Näyttö](control-screen.md)** -ohjausobjekti ja anna sille nimi **Lähde**.

1. Lisää **Lähde**-ohjausobjektiin **Muoto**-ohjausobjekti ja määritä sen **[OnSelect](properties-core.md)** -ominaisuudeksi seuraava kaava:

  `Navigate(Target; ScreenTransition.Fade)`
  
1. Paina F5-näppäintä ja valitse sitten **muodon** ohjausobjektin.

    **Kohde**-näyttö tulee näkyviin.

1. (valinnainen) Palaa oletustyötilaan painamalla Esc-näppäintä. Lisää **Muoto**-ohjausobjekti **Kohde**-näyttöön ja määritä **Muoto**-ohjausobjektin **[OnSelect](properties-core.md)** -ominaisuudeksi seuraava kaava:

  `Navigate(Source; ScreenTransition.Fade)`

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet

### <a name="color-contrast"></a>Värikontrasti

Seuraava koskee vain grafiikkakuvia, joita käytetään painikkeina tai jotka eivät muutoin ole pelkkiä koristeita.

Kuvakkeet:
- **[Color](properties-color-border.md)** ja **[Fill](properties-color-border.md)**
- Muut [tavalliset värikontrastivaatimukset](../accessible-apps-color.md) pätevät (käytettäessä painikkeena)

Reunoja sisältävät muodot:
- **[BorderColor](properties-color-border.md)** ja ohjausobjektin ulkopuolinen väri
- **[FocusedBorderColor](properties-color-border.md)** ja väri ohjausobjektin ulkopuolella (käytettäessä painikkeena)

Muodot, jotka eivät sisällä reunoja:
- **[Fill](properties-color-border.md)** ja ohjausobjektin ulkopuolinen väri
- **[PressedFill](properties-color-border.md)** ja väri ohjausobjektin ulkopuolella (käytettäessä painikkeena)
- **[HoverFill](properties-color-border.md)** ja väri ohjausobjektin ulkopuolella (käytettäessä painikkeena)

### <a name="screen-reader-support"></a>Näytönlukuohjelmien tuki
- **[AccessibleLabel](properties-accessibility.md)**  on määritettävä muu kuin tyhjä merkkijono, jos kuvaa käytetään painikkeena tai muussa kuin koristeellisessa tarkoituksessa.

- **[AccessibleLabel](properties-accessibility.md)**  on oltava tyhjä tai tyhjä merkkijono **””** Jos kuvaa esitetään tarpeetonta tietoa tai pelkästään koristeena. Tämä arvo aiheuttaa näytönlukuohjelmat voivat ohittaa kuvan.

Voit esimerkiksi määrittää **[AccessibleLabel](properties-accessibility.md)** ominaisuus **asetukset** kuvakkeen **asetukset**. Kuvaketta ei käytetä painikkeena. Se on vieressä **[nimen](control-text-box.md)** , joka lukee myös **asetukset**. Näytönlukuohjelmat lukevat kuvakkeen ja sitten myös selitteen tekstinä **asetukset**, joka on tarpeetonta. Tässä tapauksessa kuvake ei tarvitse  **[AccessibleLabel](properties-accessibility.md)** .

> [!IMPORTANT]
> Näytönlukuohjelmat lukevat kuvakkeen tai muodon kuin lukea **painike** Jos sen **[AccessibleLabel](properties-accessibility.md)** on asetettu tyhjä merkkijono, ja sen **[Sarkainindeksi ](properties-accessibility.md)** asetetaan nolla tai suurempi. Tällaiset kuvakkeet ja muodot hahmonnetaan painikkeina. 

### <a name="keyboard-support"></a>Näppäimistön tuki
- **[TabIndex](properties-accessibility.md)**  on oltava nolla tai suurempi, jos kuvaa käytetään painikkeena. Jos määrität tämän arvon kuvakkeen tai muodon, näppäimistön käyttäjät voivat siirtyä siihen.

- Kohdistusilmaisimien on oltava selvästi näkyvissä, jos kuvaa käytetään painikkeena. Käytä **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** saavutat tämän tuloksen.

    > [!NOTE]
    > Jos **[TabIndex](properties-accessibility.md)** on suurempi tai yhtä suuri kuin 0, kuvake tai muoto hahmonnetaan painikkeena. Sen ulkoasu ei muutu, mutta näytönlukuohjelmat tunnistavat kuvan painikkeena oikein. Jos **[TabIndex](properties-accessibility.md)** on pienempi kuin 0, kuvake tai muoto tunnistetaan kuvana.

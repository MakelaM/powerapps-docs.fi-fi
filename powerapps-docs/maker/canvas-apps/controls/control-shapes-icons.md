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
ms.openlocfilehash: 54ab2ba2186f68fcb68b9aa59729933af5d04652
ms.sourcegitcommit: 39b32abb19ad9fae98ca986ded6974bcbbb3cea7
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/24/2019
ms.locfileid: "68473900"
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>Muoto- ja kuvakeohjausobjektit PowerAppsissa
Grafiikkoja, joille voi määrittää ulkoasu- ja toimintaominaisuuksia.

## <a name="description"></a>Kuvaus
Tällaisia ohjausobjekteja ovat muun muassa nuolet, geometriset muodot, toimintokuvakkeet ja symbolit, joille voi määrittää täytön, koon ja sijainnin kaltaisia ominaisuuksia. Voit myös määrittää niiden **[onselect](properties-core.md)** -ominaisuuden niin, että sovellus reagoi, jos käyttäjä valitsee ohjaus objektin.

## <a name="key-properties-icons-and-shapes"></a>Avain ominaisuudet (kuvakkeet ja muodot)
**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Onselect](properties-core.md)** – miten sovellus reagoi, kun käyttäjä valitsee ohjaus objektin.

## <a name="key-properties-icons-only"></a>Avain ominaisuudet (vain kuvakkeet)

**Kuvake** – näytettävän kuvakkeen tyyppi (esimerkiksi **nuoli alas** tai **shopptingcart**). 

**Kierto** – kuvakkeen kiertämisen asteiden määrä. 

**Color** – kuvakkeen värin nimen tai RGBA-arvon mukaan.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**), vai onko ominaisuus poistettu käytöstä (**Disabled**).

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Pressedbordercolor](properties-color-border.md)** – ohjaus objektin reunan väri, kun käyttäjä valitsee kyseisen ohjaus objektin.

**[Pressedfill](properties-color-border.md)** – ohjaus objektin tausta väri, kun käyttäjä valitsee kyseisen ohjaus objektin.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot

[**Navigate**( *ScreenName*, *ScreenTransition* )](../functions/function-navigate.md)

## <a name="example"></a>Esimerkki

1. Anna oletusarvoiselle **[Näyttö](control-screen.md)** -ohjausobjektille nimi **Kohde**, lisää **[Otsikko](control-text-box.md)** -ohjausobjekti ja määritä sen **[Teksti](properties-core.md)** -ominaisuus näyttämään **Kohde**.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

1. Lisää **[Näyttö](control-screen.md)** -ohjausobjekti ja anna sille nimi **Lähde**.

1. Lisää **Lähde**-ohjausobjektiin **Muoto**-ohjausobjekti ja määritä sen **[OnSelect](properties-core.md)** -ominaisuudeksi seuraava kaava:

  `Navigate(Target, ScreenTransition.Fade)`
  
1. Paina F5-näppäintä ja valitse sitten **muoto** -ohjaus objekti.

    **Kohde**-näyttö tulee näkyviin.

1. (valinnainen) Palaa oletustyötilaan painamalla Esc-näppäintä. Lisää **Muoto**-ohjausobjekti **Kohde**-näyttöön ja määritä **Muoto**-ohjausobjektin **[OnSelect](properties-core.md)** -ominaisuudeksi seuraava kaava:

  `Navigate(Source, ScreenTransition.Fade)`

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
- **[AccessibleLabel](properties-accessibility.md)** -asetuksena on oltava muu kuin tyhjä merkki jono, jos kuvaa käytetään painikkeena tai muuten ei pelkästään koriste luun.

- **[AccessibleLabel](properties-accessibility.md)** -arvon on oltava tyhjä tai tyhjä **merkki jono** , jos grafiikka antaa tarpeettomia tietoja tai on puhtaasti koriste. Tämä arvo saa näytön luku ohjelmat ohittamaan grafiikan.

Voit esimerkiksi valita **Asetukset** -kuvakkeen **[AccessibleLabel](properties-accessibility.md)** -ominaisuudeksi **Asetukset**. Tätä kuvaketta ei käytetä painikkeena. Se on **[otsikon](control-text-box.md)** vieressä, jossa lukee myös **Asetukset**. Näytön luku ohjelmat lukevat sekä kuvakkeen että otsikon asetuksina,mikä on tarpeettoman monisanainen. Tässä tapa uksessa kuvake ei tarvitse **[AccessibleLabel](properties-accessibility.md)** .

> [!IMPORTANT]
> Näytön luku ohjelmat lukevat kuvakkeen tai muodon painikkeena , jos sen **[AccessibleLabel](properties-accessibility.md)** -asetus on tyhjä merkki jono ja sen **[tabdex](properties-accessibility.md)** -arvo on nolla tai suurempi. Tällaiset kuvakkeet tai muodot hahmonnetaan painikkeina. 

### <a name="keyboard-support"></a>Näppäimistön tuki
- **[Tabdex](properties-accessibility.md)** -arvon on oltava nolla tai suurempi, jos kuvaa käytetään painikkeena. Jos määrität tämän arvon kuvakkeelle tai muodolle, näppäimistön käyttäjät voivat siirtyä siihen.

- Kohdistus ilmaisimien on oltava selvästi näkyvissä, jos kuvaa käytetään painikkeena. Käytä **[Focusedbordercolor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** tämän tuloksen saavuttamiseksi.

    > [!NOTE]
    > Jos **[TabIndex](properties-accessibility.md)** on suurempi tai yhtä suuri kuin 0, kuvake tai muoto hahmonnetaan painikkeena. Sen ulkoasu ei muutu, mutta näytön luku ohjelmat tunnistavat kuvan oikein painikkeena. Jos **[TabIndex](properties-accessibility.md)** on pienempi kuin 0, kuvake tai muoto tunnistetaan kuvana.

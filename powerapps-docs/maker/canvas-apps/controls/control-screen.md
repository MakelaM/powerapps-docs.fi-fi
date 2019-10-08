---
title: 'Screen-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja Screen-ohjausobjektista (näytön ohjausobjektista), kuten ominaisuudet ja esimerkkejä
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 09/14/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1b9f819ab7e047b68e60b9c78e6f7f000502abb8
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993329"
ms.PowerAppsDecimalTransform: true
---
# <a name="screen-control-in-powerapps"></a>Screen-ohjausobjekti PowerAppsissa

Käyttöliittymän elementti, joka sisältää yhden tai useamman muun ohjausobjektin sovelluksessa.

## <a name="description"></a>Kuvaus

Useimmissa sovelluksissa on useita **näytön** ohjausobjekteja, jotka sisältävät **[Otsikko](control-text-box.md)** -, **[Painike](control-button.md)** -ohjausobjektit ja muut ohjausobjektit, jotka näyttävät tietoja ja tukevat siirtymistä. Lisä tietoja näytön lisäämisestä, näyttöjen uudelleenjärjesteleminen ja siirtymisen määrittämisestä on kohdassa [Lisää näyttö](../add-screen-context-variables.md).

## <a name="key-properties"></a>Tärkeimmät ominaisuudet

**[BackgroundImage](properties-visual.md)** – näytön taustalla näkyvän kuvatiedoston nimi.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

## <a name="additional-properties"></a>Lisäominaisuudet

**Korkeus** – näytön korkeus. Jos sovellus reagoi herkästi ([**Sovita**](../set-aspect-ratio-portrait-landscape.md#change-screen-size-and-orientation) on **poistettu käytöstä**) ja laite, jossa sovellus on käynnissä, on lyhyempi kuin tämä ominaisuus, näyttö voi vierittämään näkymää pystysuunnassa.

**[ImagePosition](properties-visual.md)** – Näytössä olevan kuvan tai ohjausobjektin asettelu (**Täyttö**, **Sovita**, **Stretch**, **Vierekkäin** tai **Keskitä**), jos se ei ole saman kokoinen kuin kuva.

**Nimi** – näytön nimi.

**OnHidden** – miten sovellus reagoi, kun käyttäjä siirtyy pois näytöstä.

**OnVisible** – miten sovellus reagoi, kun käyttäjä siirtyy näyttöön.  Tämän ominaisuuden avulla voit määrittää näytön käyttämät muuttujat ja esilatauksen tiedot.  Käytä [**sovellusta. OnStart**](../functions/object-app.md#onstart-property) -ominaisuutta, joka määritetään kerran, kun sovellus käynnistetään.

**Suunta** – näytön suunta. Jos sen **Leveys** on suurempi kuin **Korkeus**, suunta on **asettelu. vaaka suunnassa**; muussa tapa uksessa se on **ulkoasu. pysty**.

**Koko** – positiivinen kokonaisluku, joka luokittelee näytön koon. Luokitus määritetään vertaamalla näytön **Width** -ominaisuutta [**sovelluksen arvoihin. siderbreakpoints**](../functions/signals.md) -ominaisuus. **Screensize** -tyyppi sisältää neljä arvoa (**pieni**, **keskikokoinen**, **suuri**ja **extraalarge**), jotka vastaavat kokonaislukuja 1 – 4.

**Leveys** – näytön leveys. Jos sovellus reagoi herkästi ([**Sovita**](../set-aspect-ratio-portrait-landscape.md#change-screen-size-and-orientation) on **poissa käytöstä**) ja laite, jossa sovellus on käynnissä, on kapeampi kuin tämä ominaisuus, näyttö voi vierittää vaaka suunnassa.

## <a name="related-functions"></a>Aiheeseen liittyvät funktiot

[**Distinct**( *Tietolähde*; *SarakkeenNimi* )](../functions/function-distinct.md)

## <a name="example"></a>Esimerkki

1. Lisää **[Valintanappi](control-radio.md)** -ohjausobjekti, anna sille nimeksi **ScreenFills** ja aseta sen **[Items](properties-core.md)** -ominaisuudeksi tämä arvo:

    `["Red"; "Green"]`

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?

1. Anna oletusarvoisen **Näyttö**-ohjausobjektin nimeksi **Source**, lisää toinen **Näyttö**-ohjausobjekti ja anna sille nimeksi **Target**.

1. Lisää **lähteessä** **[muoto](control-shapes-icons.md)** -ohjaus objekti (kuten nuoli) ja määritä sen **[onselect](properties-core.md)** -ominaisuudeksi Tämä kaava:

    `Navigate(Target; ScreenTransition.Fade)`

    Haluatko lisätietoja **[Navigate](../functions/function-navigate.md)** -funktiosta tai [muista funktioista](../formula-reference.md)?

1. Lisää **Target**-ohjausobjektiin **[Muoto](control-shapes-icons.md)** -ohjausobjekti (kuten nuoli), ja määritä sen **[OnSelect](properties-core.md)** -ominaisuudeksi tämä kaava:

    `Navigate(Source; ScreenTransition.Fade)`

1. Määritä **Target**-ohjausobjektin **[Fill](properties-color-border.md)** -ominaisuudeksi tämä kaava:

    `If("Red" in ScreenFills.Selected.Value; RGBA(255; 0; 0; 1); RGBA(54; 176; 75; 1))`

1. Valitse **lähde** näyttö ja pidä sitten ALT-näppäintä painettuna, valitse joko vaihto ehto **[Radio](control-radio.md)** -ohjaus objektissa ja valitse sitten **[muoto](control-shapes-icons.md)** -ohjaus objekti.

    **Kohde** näkyy valitsemassasi värissä.

1. Valitse **kohde**-kohdassa **[muoto](control-shapes-icons.md)** -ohjaus objekti palataksesi **lähteeseen**.

1. valinnainen Valitse toinen vaihto ehto **[Radio](control-radio.md)** -ohjaus objektissa ja valitse sitten **[muoto](control-shapes-icons.md)** -ohjaus objekti vahvistaaksesi, että **kohde** näkyy toisessa värissä.

1. valinnainen Järjestä näytöt uudelleen viemällä osoitin vasemmassa siirtymis palkissa olevan **kohteen** kohdalle, valitsemalla näkyviin tulee kolme pistettä ja valitsemalla sitten **Siirrä ylös**.

    **Kohde** näkyy ensimmäisenä, kun käyttäjä avaa sovelluksen.

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet

### <a name="color-contrast"></a>Värikontrasti

Kun **näyttöä** käytetään tekstin taustana, seuraavien osien värikontrastin on oltava riittävä:

- **[Täyttö](properties-color-border.md)** ja teksti
- **[BackgroundImage](properties-visual.md)** -kuva ja teksti (jos sovellettavissa)

Jos **näyttö** sisältää esimerkiksi sisältää **[otsikon](control-text-box.md)** , jonka täyttö on läpinäkyvä, näytön **[täyttö](properties-color-border.md)** toimii käytännössä otsikon taustana.

Tarkista tekstin lisäksi olennaisten graafisten objektien (esim. **[Arvio](control-rating.md)** -ohjausobjektin tähtikuvien) värikontrasti.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki

- **Näytöillä** on oltava kuvaava nimi. Näytön nimeä voi tarkastella ja muokata samalla tavalla kuin muita ohjausobjekteja: ohjausobjektit-ruudun puunäkymästä tai ominaisuudet-ruudun otsikosta.

    > [!NOTE]
  > Kun uusi **näytön** on ladattu, näytönlukuohjelmat ilmoittavat sen nimen.

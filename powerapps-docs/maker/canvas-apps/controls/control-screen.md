---
title: 'Screen-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja Screen-ohjausobjektista (näytön ohjausobjektista), kuten ominaisuudet ja esimerkkejä
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6fedff6d6ffc34fe390ec6978672d699480a7cb9
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61548727"
---
# <a name="screen-control-in-powerapps"></a>Screen-ohjausobjekti PowerAppsissa

Käyttöliittymän elementti, joka sisältää yhden tai useamman muun ohjausobjektin sovelluksessa.

## <a name="description"></a>Kuvaus

Useimmissa sovelluksissa on useita **näytön** ohjausobjekteja, jotka sisältävät **[Otsikko](control-text-box.md)**-, **[Painike](control-button.md)**-ohjausobjektit ja muut ohjausobjektit, jotka näyttävät tietoja ja tukevat siirtymistä. Lisätietoja siitä, miten voit lisätä näytön, Järjestä näyttöjä ja määrittää siirtyminen, tarkista [Lisää näyttö](../add-screen-context-variables.md).

## <a name="key-properties"></a>Tärkeimmät ominaisuudet

**[BackgroundImage](properties-visual.md)** – näytön taustalla näkyvän kuvatiedoston nimi.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

## <a name="additional-properties"></a>Lisäominaisuudet

**Korkeus** -näytön korkeus. Jos sovellus on reagoiva ([**Sovita** ](../set-aspect-ratio-portrait-landscape.md#change-screen-size-and-orientation) on **käytöstä**) ja laite, johon sovellus on käynnissä on lyhyempi kuin tätä ominaisuutta, näyttöön voi vierittää pystysuunnassa.

**[ImagePosition](properties-visual.md)** – Näytössä olevan kuvan tai ohjausobjektin asettelu (**Täyttö**, **Sovita**, **Stretch**, **Vierekkäin** tai **Keskitä**), jos se ei ole saman kokoinen kuin kuva.

**Nimi** -näytön nimi.

**OnHidden** – miten sovellus reagoi, kun käyttäjä siirtyy pois näytöstä.

**OnStart** – miten sovellus reagoi, kun käyttäjä avaa sovelluksen.

- Kaava, johon tämä ominaisuus määritetään, suoritetaan, ennen kuin sovelluksen ensimmäinen näyttö näytetään. Kutsu [**Navigate**](../functions/function-navigate.md)-funktiota muuttaaksesi sovelluksen käynnistämisen yhteydessä näytettävää näyttöä.
- Et voi määrittää [kontekstimuuttujia](../working-with-variables.md) [**UpdateContext**](../functions/function-updatecontext.md)-funktiolla, koska yhtään näyttöä ei ole näytetty vielä. Voit kuitenkin välittää kontekstimuuttujia **Navigate**-funktiossa ja luoda ja täyttää [kokoelman](../working-with-variables.md) käyttämällä [**Collect**](../functions/function-clear-collect-clearcollect.md)-funktiota.
- Kun päivität sovelluksen, kaava, johon tämä ominaisuus määritetään, suoritetaan kun sovellus ladataan PowerApps Studioon. Jotta näet tämän ominaisuuden muuttamisen vaikutuksen, tallenna, sulje ja lataa sovellus uudelleen.
- **OnStart**-ominaisuus on varsinaisesti sovelluksen ominaisuus, ei näytön ominaisuus. Muokkaamisen helpottamiseksi sitä tarkastellaan ja muokataan ominaisuutena sovelluksen ensimmäisessä näytössä. Jos poistat ensimmäisen näytön tai muutat näyttöjen järjestystä, tätä ominaisuutta voi olla vaikea löytää. Tässä tapauksessa tallenna, sulje ja lataa sovellus uudelleen, niin ominaisuus näkyy uudelleen ominaisuutena ensimmäisellä ruudulla.

**OnVisible** – miten sovellus reagoi, kun käyttäjä siirtyy näyttöön.

**Suunta** -näytön suunnan. Jos sen **leveys** on suurempi kuin sen **korkeus**, suuntaa on **Layout.Horizontal**; muussa tapauksessa se on **Layout.Vertical** .

**Koon** -positiivinen kokonaisluku, joka luokittelee näytön koko. Luokituksen määritetään vertaamalla näytön **leveys** ominaisuuden arvot [ **App.SizeBreakpoints** ](../functions/signals.md) ominaisuus. **ScreenSize** tyyppi koostuu neljästä arvosta (**pieni**, **Normaali**, **suuri**, ja **ExtraLarge** ), jotka vastaavat kokonaislukujen 1 – 4.

**Leveys** -näytön leveys. Jos sovellus on reagoiva ([**Sovita** ](../set-aspect-ratio-portrait-landscape.md#change-screen-size-and-orientation) on **käytöstä**) ja laite, johon sovellus on käynnissä on kuin tätä ominaisuutta, näytön vierittää vaakasuunnassa.

## <a name="related-functions"></a>Aiheeseen liittyvät funktiot

[**Distinct**( *Tietolähde*, *SarakkeenNimi* )](../functions/function-distinct.md)

## <a name="example"></a>Esimerkki

1. Lisää **[Valintanappi](control-radio.md)**-ohjausobjekti, anna sille nimeksi **ScreenFills** ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi tämä arvo:

    `["Red", "Green"]`

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?

1. Anna oletusarvoisen **Näyttö**-ohjausobjektin nimeksi **Source**, lisää toinen **Näyttö**-ohjausobjekti ja anna sille nimeksi **Target**.

1. - **Tietolähteen**, Lisää **[muodon](control-shapes-icons.md)** ohjausobjekti (kuten nuoli) ja määritä sen **[OnSelect](properties-core.md)** -ominaisuuden arvoksi Tämä kaava:

    `Navigate(Target, ScreenTransition.Fade)`

    Haluatko lisätietoja **[Navigate](../functions/function-navigate.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?

1. Lisää **Target**-ohjausobjektiin **[Muoto](control-shapes-icons.md)**-ohjausobjekti (kuten nuoli), ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:

    `Navigate(Source, ScreenTransition.Fade)`

1. Määritä **Target**-ohjausobjektin **[Fill](properties-color-border.md)**-ominaisuudeksi tämä kaava:

    `If("Red" in ScreenFills.Selected.Value, RGBA(255, 0, 0, 1), RGBA(54, 176, 75, 1))`

1. Valitse **tietolähteen** näytössä ja valitse sitten, kun pidät alhaalla Alt-näppäintä, jompaakumpaa vaihtoehtoa **[Radio](control-radio.md)** ohjausobjekti ja valitse sitten **[Muodon](control-shapes-icons.md)** ohjausobjektin.

    **Kohde** tulee näkyviin, jonka valitsit väri.

1. - **Kohde**, valitse **[muodon](control-shapes-icons.md)** ohjausobjektia palataksesi **tietolähteen**.

1. (valinnainen) Valitse muut asetus **[Radio](control-radio.md)** ohjausobjekti ja valitse sitten **[muodon](control-shapes-icons.md)** ohjausobjektia vahvistaaksesi, että **kohde**  näkyy erivärisenä.

1. (valinnainen) Järjestää näyttöjen hiiri **kohde** vasemmassa siirtymispalkissa, valitsemalla kolme pistettä, joka näkyy ja valitsemalla sitten **ylöspäin**.

    **Kohde** tulee ensin, kun käyttäjä avaa sovelluksen.

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet

### <a name="color-contrast"></a>Värikontrasti

Kun **näyttöä** käytetään tekstin taustana, seuraavien osien värikontrastin on oltava riittävä:

- **[Täyttö](properties-color-border.md)** ja teksti
- **[BackgroundImage](properties-visual.md)**-kuva ja teksti (jos sovellettavissa)

Jos **näyttö** sisältää esimerkiksi sisältää **[otsikon](control-text-box.md)**, jonka täyttö on läpinäkyvä, näytön **[täyttö](properties-color-border.md)** toimii käytännössä otsikon taustana.

Tarkista tekstin lisäksi olennaisten graafisten objektien (esim. **[Arvio](control-rating.md)**-ohjausobjektin tähtikuvien) värikontrasti.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki

- **Näytöillä** on oltava kuvaava nimi. Näytön nimeä voi tarkastella ja muokata samalla tavalla kuin muita ohjausobjekteja: ohjausobjektit-ruudun puunäkymästä tai ominaisuudet-ruudun otsikosta.

    > [!NOTE]
  > Kun uusi **näytön** on ladattu, näytönlukuohjelmat ilmoittavat sen nimen.

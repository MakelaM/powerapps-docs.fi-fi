---
title: 'Screen-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja Screen-ohjausobjektista (näytön ohjausobjektista), kuten ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: 165b6544808da234773c2b7a2cdd0014d6fe5c2d
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/07/2018
ms.locfileid: "37898699"
---
# <a name="screen-control-in-powerapps"></a>Screen-ohjausobjekti PowerAppsissa
Käyttöliittymän elementti, joka sisältää yhden tai useamman muun ohjausobjektin sovelluksessa.

## <a name="description"></a>Kuvaus
Useimmissa sovelluksissa on useita **näytön** ohjausobjekteja, jotka sisältävät **[Otsikko](control-text-box.md)**-, **[Painike](control-button.md)**-ohjausobjektit ja muut ohjausobjektit, jotka näyttävät tietoja ja tukevat siirtymistä.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**[BackgroundImage](properties-visual.md)** – näytön taustalla näkyvän kuvatiedoston nimi.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

## <a name="additional-properties"></a>Lisäominaisuudet
**[ImagePosition](properties-visual.md)** – Kuvan tai ohjausobjektin asettelu (**Fill** [täytä], **Fit** [sovita], **Stretch** [venytä], **Tile** [vierekkäin] tai **Center** [keskitä]), jos kuva tai ohjausobjekti ei ole saman kokoinen kuin näyttö.

**OnHidden** – miten sovellus reagoi, kun käyttäjä siirtyy pois näytöstä.

**OnVisible** – miten sovellus reagoi, kun käyttäjä siirtyy näyttöön.

**OnStart** – miten sovellus reagoi, kun käyttäjä avaa sovelluksen.

* Kaava, johon tämä ominaisuus määritetään, suoritetaan, ennen kuin sovelluksen ensimmäinen näyttö näytetään. Kutsu [**Navigate**](../functions/function-navigate.md)-funktiota muuttaaksesi sovelluksen käynnistämisen yhteydessä näytettävää näyttöä.
* Et voi määrittää [kontekstimuuttujia](../working-with-variables.md) [**UpdateContext**](../functions/function-updatecontext.md)-funktiolla, koska yhtään näyttöä ei ole näytetty vielä. Voit kuitenkin välittää kontekstimuuttujia **Navigate**-funktiossa ja luoda ja täyttää [kokoelman](../working-with-variables.md) käyttämällä [**Collect**](../functions/function-clear-collect-clearcollect.md)-funktiota.
* Kun päivität sovelluksen, kaava, johon tämä ominaisuus määritetään, suoritetaan kun sovellus ladataan PowerApps Studioon. Jotta näet tämän ominaisuuden muuttamisen vaikutuksen, tallenna, sulje ja lataa sovellus uudelleen.
* **OnStart**-ominaisuus on varsinaisesti sovelluksen ominaisuus, ei näytön ominaisuus. Muokkaamisen helpottamiseksi sitä tarkastellaan ja muokataan ominaisuutena sovelluksen ensimmäisessä näytössä. Jos poistat ensimmäisen näytön tai muutat näyttöjen järjestystä, tätä ominaisuutta voi olla vaikea löytää. Tässä tapauksessa tallenna, sulje ja lataa sovellus uudelleen, niin ominaisuus näkyy uudelleen ominaisuutena ensimmäisellä ruudulla.

## <a name="related-functions"></a>Liittyvät funktiot
[**Distinct**( *Tietolähde*, *SarakkeenNimi* )](../functions/function-distinct.md)

## <a name="example"></a>Esimerkki
1. Lisää **[Valintanappi](control-radio.md)**-ohjausobjekti, anna sille nimeksi **ScreenFills** ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi tämä arvo:<br>
   **["Red", "Green"]**
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Anna oletusarvoisen **Näyttö**-ohjausobjektin nimeksi **Source**, lisää toinen **Näyttö**-ohjausobjekti ja anna sille nimeksi **Target**.
3. Lisää **Source**-ohjausobjektiin **[Muoto](control-shapes-icons.md)**-ohjausobjekti (kuten nuoli), ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Navigate(Kohde, ScreenTransition.Fade)**
   
    Haluatko lisätietoja **[Navigate](../functions/function-navigate.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
4. Lisää **Target**-ohjausobjektiin **[Muoto](control-shapes-icons.md)**-ohjausobjekti (kuten nuoli), ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Navigate(Lähde, ScreenTransition.Fade)**
5. Määritä **Target**-ohjausobjektin **[Fill](properties-color-border.md)**-ominaisuudeksi tämä kaava:<br>
   **If("Red" in NäytönTäyttö.Selected.Value, RGBA(255, 0, 0, 1), RGBA(54, 176, 75, 1))**
6. Paina **Lähde**-ohjausobjektissa F5, napsauta tai napauta jompaakumpaa vaihtoehtoa **[Radio](control-radio.md)**-ohjausobjektissa (valintanappi) ja napsauta tai napauta sen jälkeen **[Shape](control-shapes-icons.md)**-ohjausobjektia.
   
    **Target** näkyy valitsemasi värisenä.
7. Napsauta tai napauta **Target**-ohjausobjektissa **[Muoto](control-shapes-icons.md)**-ohjausobjektia palataksesi **Source**-ohjausobjektiin.
8. (valinnainen) Napsauta tai napauta toista valintaa **[Valintanappi](control-radio.md)**-ohjausobjektissa ja napsauta tai napauta **[Muoto](control-shapes-icons.md)**-ohjausobjektia vahvistaaksesi, että **Target** näkyy erivärisenä.
9. Palaa oletustyötilaan painamalla ESC-näppäintä.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Kun **näyttöä** käytetään tekstin taustana, seuraavien osien värikontrastin on oltava riittävä:
* **[Täyttö](properties-color-border.md)** ja teksti
* **[BackgroundImage](properties-visual.md)**-kuva ja teksti (jos sovellettavissa)

Jos **näyttö** sisältää esimerkiksi sisältää **[otsikon](control-text-box.md)**, jonka täyttö on läpinäkyvä, näytön **[täyttö](properties-color-border.md)** toimii käytännössä otsikon taustana.

Tarkista tekstin lisäksi olennaisten graafisten objektien (esim. **[Arvio](control-rating.md)**-ohjausobjektin tähtikuvien) värikontrasti.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **Näytöillä** on oltava kuvaava nimi. Näytön nimeä voi tarkastella ja muokata samalla tavalla kuin muita ohjausobjekteja: ohjausobjektit-ruudun puunäkymästä tai ominaisuudet-ruudun otsikosta.

    > [!NOTE]
  > Kun uusi **näytön** on ladattu, näytönlukuohjelmat ilmoittavat sen nimen. 

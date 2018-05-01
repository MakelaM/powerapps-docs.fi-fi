---
title: 'Screen-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja Screen-ohjausobjektista (näytön ohjausobjektista), kuten ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: cd2e2a8c28fb894b1935b29bf80bf65eb631a266
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="screen-control-in-powerapps"></a>Screen-ohjausobjekti PowerAppsissa
Käyttöliittymän elementti, joka sisältää yhden tai useamman muun ohjausobjektin sovelluksessa.

## <a name="description"></a>Kuvaus
Useimmissa sovelluksissa on useita **Screen**-ohjausobjekteja, jotka sisältävät **[Label](control-text-box.md)**- ja **[Button](control-button.md)**-ohjausobjekteja sekä muita ohjausobjekteja jotka näyttävät tietoja ja tukevat siirtymistä.

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
* Kun päivität sovelluksen, kaava johon tämä ominaisuus määritetään, suoritetaan kun sovellus ladataan PowerApps Studioon. Jotta näet tämän ominaisuuden muuttamisen vaikutuksen, tallenna, sulje ja lataa sovellus uudelleen.
* **OnStart**-ominaisuus on varsinaisesti sovelluksen ominaisuus, ei näytön ominaisuus. Muokkaamisen helpottamiseksi sitä tarkastellaan ja muokataan ominaisuutena sovelluksen ensimmäisessä näytössä. Jos poistat ensimmäisen näytön tai muutat näyttöjen järjestystä, tätä ominaisuutta voi olla vaikea löytää. Siinä tapauksessa tallenna, sulje ja lataa sovellus uudelleen, niin ominaisuus näkyy uudelleen ominaisuutena ensimmäisessä näytössä.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Distinct**( *Tietolähde*, *SarakkeenNimi* )](../functions/function-distinct.md)

## <a name="example"></a>Esimerkki
1. Lisää **[Radio](control-radio.md)**-ohjausobjekti (valintanappi), anna sille nimeksi **NäytönTäyttö**, ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi tämä arvo:<br>
   **["Red", "Green"]**
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Anna oletusarvoisen **Screen**-ohjausobjektin nimeksi **Lähde**, lisää toinen **Screen**-ohjausobjekti ja anna sille nimeksi **Kohde**.
3. Lisää **Lähde**-ohjausobjektiin **[Shape](control-shapes-icons.md)**-ohjausobjekti (kuten nuoli), ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Navigate(Kohde, ScreenTransition.Fade)**
   
    Haluatko lisätietoja **[Navigate](../functions/function-navigate.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
4. Lisää **Kohde**-ohjausobjektiin **[Shape](control-shapes-icons.md)**-ohjausobjekti (kuten nuoli), ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Navigate(Lähde, ScreenTransition.Fade)**
5. Määritä **Kohde**-ohjausobjektin **[Fill](properties-color-border.md)**-ominaisuudeksi tämä kaava:<br>
   **If("Red" in NäytönTäyttö.Selected.Value, RGBA(255, 0, 0, 1), RGBA(54, 176, 75, 1))**
6. Paina **Lähde**-ohjausobjektissa F5, napsauta tai napauta jompaakumpaa vaihtoehtoa **[Radio](control-radio.md)**-ohjausobjektissa (valintanappi) ja napsauta tai napauta sen jälkeen **[Shape](control-shapes-icons.md)**-ohjausobjektia.
   
    **Kohde** näkyy valitsemasi värisenä.
7. Napsauta tai napauta **Kohde**-ohjausobjektissa **[Shape](control-shapes-icons.md)**-ohjausobjektia palataksesi **Lähde**-ohjausobjektiin.
8. (valinnainen) Napsauta tai napauta toista vaihtoehtoa **[Radio](control-radio.md)**-ohjausobjektissa (valintanappi) ja napsauta tai napauta sitten **[Shape](control-shapes-icons.md)**-ohjausobjektia varmistaaksesi, että **Kohde** näkyy eri värisenä.
9. Palaa oletustyötilaan painamalla Esc.


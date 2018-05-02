---
title: 'Näytön ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja näytön ohjausobjektista, kuten ominaisuudet ja esimerkkejä
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
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/23/2018
---
# <a name="screen-control-in-powerapps"></a>Näytön ohjausobjekti PowerAppsissa
Käyttöliittymän elementti, joka sisältää yhden tai useamman muun ohjausobjektin sovelluksessa.

## <a name="description"></a>Kuvaus
Useimmissa sovelluksissa on useita **näytön** ohjausobjekteja, jotka sisältävät **[Otsikko](control-text-box.md)**-, **[Painike](control-button.md)**-ohjausobjektit ja muut ohjausobjektit, jotka näyttävät tietoja ja tukevat siirtymistä.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**[BackgroundImage](properties-visual.md)** – näytön taustalla näkyvän kuvatiedoston nimi.

**[Fill](properties-color-border.md)** – ohjausobjektin taustaväri.

## <a name="additional-properties"></a>Lisäominaisuudet
**[ImagePosition](properties-visual.md)** – kuvan tai ohjausobjektin asettelu (**Täytä**, **Sovita**, **Venytä**, **Vierekkäin** tai **Keskitä**), jos se ei ole saman kokoinen kuin näyttö.

**OnHidden** – miten sovellus reagoi, kun käyttäjä siirtyy pois ruudulta.

**OnVisible** – miten sovellus reagoi, kun käyttäjä siirtyy ruudulle.

**OnStart** – miten sovellus reagoi, kun käyttäjä avaa sovelluksen.

* Kaava, johon tämä ominaisuus määritetään, suoritetaan ennen kuin sovelluksen ensimmäinen ruutu näytetään. Kutsu [**Navigate**](../functions/function-navigate.md)-funktiota muuttaaksesi sovelluksen käynnistämisen yhteydessä näytettävää ruutua.
* Et voi määrittää [kontekstimuuttujia](../working-with-variables.md) [**UpdateContext**](../functions/function-updatecontext.md)-funktiolla, koska yhtään ruutua ei ole näytetty vielä. Voit kuitenkin välittää kontekstimuuttujia **Navigate**-funktiossa ja luoda ja täyttää [kokoelman](../working-with-variables.md) käyttämällä [**Collect**](../functions/function-clear-collect-clearcollect.md)-funktiota.
* Kun päivität sovelluksen, kaava, johon tämä ominaisuus määritetään, suoritetaan kun sovellus ladataan PowerApps Studioon. Jotta näet tämän ominaisuuden muuttamisen vaikutuksen, tallenna, sulje ja lataa sovellus uudelleen.
* **OnStart**-ominaisuus on varsinaisesti sovelluksen ominaisuus, ei ruudun ominaisuus. Muokkaamisen helpottamiseksi sitä tarkastellaan ja muokataan ominaisuutena sovelluksen ensimmäisellä ruudulla. Jos poistat ensimmäisen ruudun tai muutat ruutujen järjestystä, tätä ominaisuutta voi olla vaikea löytää. Tässä tapauksessa tallenna, sulje ja lataa sovellus uudelleen, niin ominaisuus näkyy uudelleen ominaisuutena ensimmäisellä ruudulla.

## <a name="related-functions"></a>Liittyvät funktiot
[**Distinct**( *DataSource*, *ColumnName* )](../functions/function-distinct.md)

## <a name="example"></a>Esimerkki
1. Lisää **[Valintanappi](control-radio.md)**-ohjausobjekti, anna sille nimeksi **ScreenFills** ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi tämä arvo:<br>
   **["Red", "Green"]**
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Anna oletusarvoisen **Näyttö**-ohjausobjektin nimeksi **Source**, lisää toinen **Näyttö**-ohjausobjekti ja anna sille nimeksi **Target**.
3. Lisää **Source**-ohjausobjektiin **[Muoto](control-shapes-icons.md)**-ohjausobjekti (kuten nuoli), ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Navigate(Target, ScreenTransition.Fade)**
   
    Haluatko lisätietoja **[Navigate](../functions/function-navigate.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
4. Lisää **Target**-ohjausobjektiin **[Muoto](control-shapes-icons.md)**-ohjausobjekti (kuten nuoli), ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Navigate(Source, ScreenTransition.Fade)**
5. Määritä **Target**-ohjausobjektin **[Fill](properties-color-border.md)**-ominaisuudeksi tämä kaava:<br>
   **If("Red" in ScreenFills.Selected.Value, RGBA(255, 0, 0, 1), RGBA(54, 176, 75, 1))**
6. Paina **Source**-ohjausobjektissa F5, napsauta tai napauta toista valintaa **[Valintanappi](control-radio.md)**-ohjausobjektissa ja napsauta tai napauta **[Muoto](control-shapes-icons.md)**-ohjausobjektia.
   
    **Target** näkyy valitsemasi värisenä.
7. Napsauta tai napauta **Target**-ohjausobjektissa **[Muoto](control-shapes-icons.md)**-ohjausobjektia palataksesi **Source**-ohjausobjektiin.
8. (valinnainen) Napsauta tai napauta toista valintaa **[Valintanappi](control-radio.md)**-ohjausobjektissa ja napsauta tai napauta **[Muoto](control-shapes-icons.md)**-ohjausobjektia vahvistaaksesi, että **Target** näkyy erivärisenä.
9. Palaa oletustyötilaan painamalla Esc.


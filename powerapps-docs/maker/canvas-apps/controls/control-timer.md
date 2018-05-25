---
title: 'Ajastin-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja Ajastin-ohjausobjektista, kuten ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: 008c992ad3452c1844064335a51593c222fb1ac1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="timer-control-in-powerapps"></a>Ajastin-ohjausobjekti PowerAppsissa
Ohjausobjekti, joka voi määrittää, miten sovelluksesi vastaa tietyn ajan kuluttua.

## <a name="description"></a>Kuvaus
Ajastimet voivat esimerkiksi määrittää, miten kauan ohjausobjekti näkyy, tai muuttaa ohjausobjektin muita ominaisuuksia tietyn ajan kuluttua.

Huomaa, että sinun on esikatseltava sovellus, jotta ajastin voidaan suorittaa suunnittelutoiminnossa.  Tämän ansiosta käyttäjä voi määrittää ajastimen suunnittelutoiminnossa ilman aikarajoituksia.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**Kesto** – Miten kauan ajastin on käynnissä millisekunneissa.  Suurinta arvoa ei ole.

**OnTimerEnd** – Miten sovellus reagoi, kun ajastin lopettaa työnkulun suorittamisen.

**Toista** – Käynnistyykö ajastin automaattisesti uudelleen, kun sen toiminta pysähtyy.

## <a name="additional-properties"></a>Lisäominaisuudet
**[Align](properties-text.md)**  – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**AutoPause** – Keskeytetäänkö ääni- tai videoleike automaattisesti, jos käyttäjä siirtyy eri näyttöön.

**AutoStart** – Alkaako ääni- tai video-ohjausobjekti toistaa leikettä automaattisesti, kun käyttäjä siirtyy tämän ohjausobjektin sisältävään näyttöön.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviivat**, **pisteet** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Väri](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Fontti](properties-text.md)**  – Tekstissä käytetyn fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin leveys: **lihavoitu**, **puolilihavoitu**, **normaali** tai **ohuempi**.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin kohdalla.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen kohdalla.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Kursivoitu](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**[OnSelect](properties-core.md)** – Sovelluksen reagointitapa, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnTimerStart** – Sovelluksen reagointitapa, kun ajastin käynnistyy.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[Palauta](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**[Koko](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**Start** – Toistetaanko ääni- tai videoleike.

**[Strikethrough](properties-text.md)**  – Yliviivataanko ohjausobjektissa näkyvä teksti.

**[Teksti](properties-core.md)**  – Teksti, joka näytetään ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

**[Työkaluvihje](properties-core.md)** – Työkaluvihjeen ohjeteksti, joka ilmestyy näkyviin, kun hiiren osoitin on ohjausobjektin päällä.

**[Alleviivattu](properties-text.md)** – Ilmaisee, onko ohjausobjektissa näytettävä teksti alleviivattu.

**[Näkyvissä](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**Refresh**( *DataSource* )](../functions/function-refresh.md)

## <a name="examples"></a>Esimerkkejä
### <a name="show-a-countdown"></a>Näytä aikalaskuri
1. Lisää ajastin ja anna sille nimi **Countdown**.

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Määritä ajastimen **Kesto**-ominaisuudeksi **10000** sekä **Toista**- ja **Autostart**-ominaisuudet tilaan **true**.
3. (valinnainen) Tee ajastimen lukemisesta helpompaa asettamalla sen **[Korkeus](properties-size-location.md)**-ominaisuudeksi **160**, **[Leveys](properties-size-location.md)**-ominaisuudeksi **600** ja **[Koko](properties-text.md)**-ominaisuudeksi **60**.
4. Lisää selite ja aseta sen **[Teksti](properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**"Number of seconds remaining: " & RoundUp(10-Countdown.Value/1000, 0)**

    Haluatko lisätietoja **[RoundUp](../functions/function-round.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?

    Selite näyttää, kuinka monen sekunnin kuluttua ajastin käynnistyy uudelleen.
5. (valinnainen) Aseta ajastimen **[Näkyvissä](properties-core.md)**-ominaisuus tilaan **false**.

### <a name="animate-a-control"></a>Ohjausobjektin animointi
1. Lisää ajastin ja anna sille nimi **FadeIn**.

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Määritä ajastimen **Kesto**-ominaisuudeksi **5000** sekä **Toista**- ja **Autostart**-ominaisuudet tilaan **true**.
3. (valinnainen) Tee ajastimen lukemisesta helpompaa asettamalla sen **[Korkeus](properties-size-location.md)**-ominaisuudeksi **160**, **[Leveys](properties-size-location.md)**-ominaisuudeksi **600** ja **[Koko](properties-text.md)**-ominaisuudeksi **60**.
4. Lisää selite ja aseta sen **[Teksti](properties-core.md)**-ominaisuus näyttämään **Welcome!** ja määritä sen **[Väri](properties-color-border.md)**-ominaisuudeksi tämä kaava:
   <br>**ColorFade(Color.BlueViolet, FadeIn.Value/5000)**

    Haluatko lisätietoja **[ColorFade](../functions/function-colors.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?

    Selitteen teksti häivytetään valkoiseksi, minkä jälkeen se palaa täyteen voimakkuuteen. Tämän jälkeen prosessi toistuu.
5. (valinnainen) Aseta ajastimen **[Näkyvissä](properties-core.md)**-ominaisuus tilaan **false**.

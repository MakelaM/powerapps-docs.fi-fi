---
title: 'Mikrofoni-ohjausobjekti: viittaus | Microsoft Docs'
description: Mikrofoni-ohjausobjektin tietoja, ominaisuuksia ja esimerkkejä
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
ms.openlocfilehash: 3ffede0018a371b3c3a4cf4a3a1f9fc8115140de
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="microphone-control-in-powerapps"></a>Mikrofoni-ohjausobjekti PowerAppsissa
Ohjausobjekti, jolla käyttäjä voi taltioida ääniä.

## <a name="description"></a>Kuvaus
Jos lisäät tämän ohjausobjektin, käyttäjä voi päivittää tietolähteen yhdellä tai usealla äänellä mistä tahansa sovelluksen käyttöpaikasta.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**Mikrofoni** – Sovelluksen käyttämän mikrofonin numerotunnus, jos laitteessa on useampi kuin yksi mikrofoni.

**OnStop** – Miten sovellus reagoi, kun käyttäjä lopettaa taltioimisen mikrofoni-ohjausobjektilla.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviivat**, **pisteet** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Väri](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin kohdalla.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun käyttäjä pitää hiiren osoitinta sen kohdalla.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun käyttäjä pitää hiiren osoitinta sen kohdalla.

**[Kuva](properties-visual.md)** – Sen kuvan nimi, joka näkyy kuvan, äänen tai mikrofonin ohjausobjektissa.

**[ImagePosition](properties-visual.md)** – Näytössä olevan kuvan tai ohjausobjektin asettelu (**Täyttö**, **Sovita**, **Stretch**, **Vierekkäin** tai **Keskitä**), jos se ei ole saman kokoinen kuin kuva.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnStart** – Miten sovellus reagoi, kun käyttäjä aloittaa tallentamisen mikrofoni-ohjausobjektilla.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Nollaa](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**[Työkaluvihje](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun kohdistin on ohjausobjektin kohdalla.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Esimerkki
### <a name="add-sounds-to-a-custom-gallery-control"></a>Lisää ääniä mukautettuun valikoima-ohjausobjektiin
1. Lisää **Mikrofoni**, anna sen nimeksi **MyMic** ja määritä sen **OnStop**-ominaisuudeksi tämä kaava:<br>
   **Collect(MySounds, MyMic.Audio)**
   
    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
   
    Haluatko lisätietoja **[Kerää](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
2. Lisää **Mukautettu valikoima** -ohjausobjekti, siirrä se kohdan **MyMic** alle ja määritä **[Kohteet](properties-core.md)**-ominaisuudeksi **Mukautettu valikoima** -ohjausobjektissa **MySounds**.
3. Lisää **Mukautettu valikoima** - ohjausobjektin mallissa **[Ääni](control-audio-video.md)**-ohjausobjekti ja määritä sen **Media**-ominaisuudeksi  **ThisItem.Url**.
4. Paina F5-näppäintä, aloita taltiointi napsauttamalla tai napauttamalla **MyMic** ja lopeta taltiointi napsauttamalla tai napauttamalla sitä uudelleen.
5. Toista taltiointi napsauttamalla tai napauttamalla **Mukautettu valikoima** -ohjausobjektin toistopainiketta **[Ääni](control-audio-video.md)**-ohjausobjektissa.
6. Lisää niin monta taltiointia kuin haluat ja palaa sitten oletustyötilaan painamalla Esc.
7. (valinnainen) Lisää **Mukautettu valikoima** -ohjausobjektin mallissa **[Painike](control-button.md)**-ohjausobjekti, määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi **Remove(MySounds, ThisItem)**, paina F5-näppäintä ja poista sitten taltiointi napsauttamalla tai napauttamalla vastaavaa **Painike**-ohjausobjektia.

Voit tallentaa taltioinnit paikallisesti **[SaveData](../functions/function-savedata-loaddata.md)**-funktiolla tai päivittää tietolähteen **[Ohjelmakorjaus](../functions/function-patch.md)**-funktiolla.


---
title: 'Lisää kuva -ohjausobjekti: viitetiedot | Microsoft Docs'
description: Tietoja Lisää kuva -ohjausobjektista, mukaan lukien ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: 6a7c60755f5623803d20bec4ec9881108b1116c6
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="add-picture-control-in-powerapps"></a>Lisää kuva -ohjausobjekti PowerAppsissa
Ottaa valokuvan tai lataa kuvat paikallisesta laitteesta.

## <a name="description"></a>Kuvaus
Tämän ohjausobjektin avulla käyttäjät voivat ottaa kuvia tai ladata kuvatiedostoja laitteestaan ja päivittää tietolähteen tällä sisällöllä. Mobiililaitteessa käyttäjälle esitetään laitteen vaihtoehtojen valintaikkuna, jossa voidaan valita, otetaanko valokuva vai käytetäänkö jo käytettävissä olevaa valokuvaa.

Tämä ohjausobjekti on yhdistelmäohjausobjekti, joka koostuu kahdesta ohjausobjektista.  Valitse kerran painamalla tai napauttamalla ulkoinen ohjausobjekti, joka näyttää, että kuva on ladattu.  Valitse sisäinen selitteen ohjausobjekti painamalla tai napauttamalla uudelleen.

## <a name="outer-control-properties"></a>Ulomman ohjausobjektin ominaisuudet
Nämä ominaisuudet koskevat ulkoista ohjausobjektia.

**[BorderColor](properties-color-border.md)** – ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos ohjausobjektin **[DisplayMode](properties-core.md)**-ominaisuudeksi on asetettu **Ei käytössä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-ominaisuudeksi on määritetty **Ei käytössä**.

**Error** – Jos kuvaa ladatessa esiintyy ongelma, tämä ominaisuus sisältää tarvittavan virhesanoman.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun käyttäjä pitää hiiren osoitinta sen päällä.

**Media** – Ääni- tai video-ohjausobjektin toistaman leikkeen tunniste.

**[OnSelect](properties-core.md)** – Sovelluksen reagointitapa, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Visible](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="inner-text-properties"></a>Sisemmän tekstin ominaisuudet
Nämä ominaisuudet koskevat selitteen ohjausobjektia, jossa lukee oletusarvoisesti ”Tap or click to add a picture” (Lisää kuva napauttamalla tai napsauttamalla).  Valitse tämä sisempi ohjausobjekti, painamalla tai napauttamalla **Lisää kuva** -ohjausobjektia kerran ja sitten uudelleen.

**[Align](properties-text.md)**  – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**[Color](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)** -asetuksen arvoksi on asetettu **Disabled** (ei käytössä).

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)** – Ohjausobjektin tekstin paino: **lihavoitu**, **puolilihavoitu**, **normaali** tai **ohuempi**.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**[OnChange](properties-core.md)** – Sovelluksen reagointitapa, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

**[Padding](properties-size-location.md)** – Tuonti- tai vientipainikkeen tekstin ja painikkeen reunojen välinen etäisyys.

**[PressedColor](properties-color-border.md)** –Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[Size](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[Text](properties-core.md)**  – Teksti, joka näytetään ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

**[Underline](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti alleviivattua.

**[VerticalAlign](properties-text.md)** – Ohjausobjektin tekstin sijainti suhteessa ohjausobjektin pystysuoraan keskikohtaan.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Patch**( *Tietolähde*, *Perustietue*, *Muutostietue* )](../functions/function-patch.md)

## <a name="example"></a>Esimerkki
### <a name="add-images-to-an-image-gallery-control"></a>Lisää kuvia Kuvavalikoima-ohjausobjektiin
1. Lisää **Lisää kuva** -ohjausobjekti ja napsauta sitä sen jälkeen kolmesti.
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Napsauta tai napauta **Avaa**-valintaikkunassa kuvatiedostoa ja valitse sitten **Avaa**.
3. Lisää **[Painike](control-button.md)**-ohjausobjekti, siirrä se **Lisää kuva** -ohjausobjektin alle ja määritä **[Painike](control-button.md)**-ohjausobjektin **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Collect(MyPix, AddMediaButton1.Media)**
   
    Haluatko lisätietoja **[Collect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
4. Lisää **Kuvavalikoima**-ohjausobjekti ja aseta sen **[Items](properties-core.md)**-ominaisuudeksi **MyPix**.
5. Paina F5-näppäintä ja napsauta tai napauta sitten **[Painike](control-button.md)**-ohjausobjektia.
   
    **Lisää kuva** -ohjausobjektilta tuleva kuva näkyy **Kuvavalikoima**-ohjausobjektissa. Jos kuvallasi ei ole sama kuvasuhde kuin **Kuvavalikoima**-ohjausobjektissa olevalla **[Kuva](control-image.md)**-ohjausobjektilla, määritä **[Kuva](control-image.md)**-ohjausobjektin **[ImagePosition](properties-visual.md)**-ominaisuudeksi **Sovita**.
6. Napsauta tai napauta **Lisää kuva** -ohjausobjektia, napsauta tai napauta toista kuvatiedostoa, napsauta tai napauta kohtaa **Avaa** ja napsauta tai napauta sitten lisäämääsi **[Painike](control-button.md)**-ohjausobjektia.
   
    Toinen kuva tulee näkyviin **Kuvavalikoima**-ohjausobjektiin.
7. (valinnainen) Toista edellinen vaihe yhden tai useamman kerran ja palaa sitten oletustyötilaan painamalla ESC-näppäintä.

Tallenna kuvat paikallisesti **[SaveData](../functions/function-savedata-loaddata.md)**-funktiolla tai päivitä tietolähde **[Patch](../functions/function-patch.md)**-funktiolla.


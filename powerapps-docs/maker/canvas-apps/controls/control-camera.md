---
title: 'Kameran ohjausobjekti: viittaus | Microsoft Docs'
description: Kameran ohjausobjektin tiedot, mukaan lukien ominaisuudet ja esimerkit
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
ms.openlocfilehash: a3a724ad42082962ec8aea4e616f1d75aa7299ec
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="camera-control-in-powerapps"></a>Kameran ohjausobjekti PowerAppsissa
Ohjausobjekti, jolla käyttäjä voi ottaa valokuvia laitteen kameralla.

## <a name="description"></a>Kuvaus
Jos lisäät tämän ohjausobjektin, käyttäjä voi päivittää tietolähteeseen yhden tai useita valokuvia mistä tahansa sovelluksen käyttöpaikasta.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**Camera** – Sovelluksen käyttämän kameran numerotunnus, jos laitteella on useampi kuin yksi kamera.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva**vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**Brightness** – Miten paljon valoa käyttäjä näkee kuvassa.

**Contrast** – Miten helposti käyttäjä voi erottaa samankaltaiset värit kuvasta.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnStream** – Miten sovellus reagoi, kun **Stream**-ominaisuus päivitetään.

**Photo** – Kuva, joka siepataan, kun käyttäjä ottaa kuvan.

**Stream** – **StreamRate**-ominaisuuden perusteella automaattisesti päivitetty kuva.

**StreamRate** – Miten usein kuva päivitetään **Stream**-ominaisuudessa millisekunteina.  Tämä arvo voi olla välillä 100 (1/10 sekuntia) – 3 600 000 (1 tunti).

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun kohdistin on ohjausobjektin päällä.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

**Zoom** – Prosenttiosuus, jonka verran kameran kuvaa tai PDF-katseluohjelman tiedoston näkymää suurennetaan.

## <a name="related-functions"></a>Liittyvät funktiot
[**Patch**( *Tietolähde*, *Perustietue*, *Muutostietue* )](../functions/function-patch.md)

## <a name="example"></a>Esimerkki
### <a name="add-photos-to-an-image-gallery-control"></a>Lisää valokuvia Kuvavalikoima-ohjausobjektiin
1. Lisää **Kamera**-ohjausobjekti, anna sen nimeksi **MyCamera** ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **Collect(MyPix, MyCamera.Photo)**
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
   
    Haluatko lisätietoja **[Collect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
2. Paina F5 ja ota valokuva napsauttamalla tai napauttamalla **MyCamera**.
3. Lisää **[Kuvavalikoima](control-gallery.md)**-ohjausobjekti ja muuta **[Kuva](control-image.md)**-ohjausobjektin, sen mallin sekä itse **Kuvavalikoima**-ohjausobjektin koko näyttöön sopivaksi.
4. Määritä **Kuvavalikoima**-ohjausobjektin **[Items](properties-core.md)**-ominaisuudeksi seuraava lauseke:<br>**MyPix.Url**.
5. Määritä **Kuva**-ohjausobjektin **[Image](properties-visual.md)**-ominaisuudeksi seuraava lauseke:<br>
   **ThisItem.Url**
   
    Ottamasi kuva näkyy **Kuvavalikoima**-ohjausobjektissa.
6. Ota niin monta kuvaa kuin haluat ja palaa oletustyötilaan painamalla Esc.
7. (valinnainen) Määritä **Kuva**-ohjausobjektin **OnSelect**-ominaisuudeksi **Kuvavalikoima**-ohjausobjektissa **Remove(MyPix, ThisItem)**, paina F5 ja poista valokuva napsauttamalla tai napauttamalla sitä.

Voit käyttää **[SaveData](../functions/function-savedata-loaddata.md)**-funktiota tallentaaksesi valokuvat paikallisesti tai **[Patch](../functions/function-patch.md)**-funktiota tietolähteen päivittämiseksi.


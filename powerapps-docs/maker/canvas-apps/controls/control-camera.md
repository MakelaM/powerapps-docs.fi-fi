---
title: 'Kameran ohjausobjekti: viittaus | Microsoft Docs'
description: Kameran ohjausobjektin tiedot, mukaan lukien ominaisuudet ja esimerkit
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: bffbc86dda86c0b179634d2f59e0fb4f5d063ecd
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42842620"
---
# <a name="camera-control-in-powerapps"></a>Kameran ohjausobjekti PowerAppsissa
Ohjausobjekti, jolla käyttäjä voi ottaa valokuvia laitteen kameralla.

## <a name="description"></a>Kuvaus
Jos lisäät tämän ohjausobjektin, käyttäjä voi päivittää tietolähteeseen yhden tai useita valokuvia mistä tahansa sovelluksen käyttöpaikasta.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**Camera** – Sovelluksen käyttämän kameran numerotunnus, jos laitteella on useampi kuin yksi kamera.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi. Tulee kuvata kuvan käyttötarkoituksen.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**Brightness** – Miten paljon valoa käyttäjä näkee kuvassa.

**Contrast** – Miten helposti käyttäjä voi erottaa samankaltaiset värit kuvasta.

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**), vai onko ominaisuus poistettu käytöstä (**Disabled**).

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnStream** – Miten sovellus reagoi, kun **Stream**-ominaisuus päivitetään.

**Photo** – Kuva, joka siepataan, kun käyttäjä ottaa kuvan.

**Stream** – **StreamRate**-ominaisuuden perusteella automaattisesti päivitetty kuva.

**StreamRate** – Miten usein kuva päivitetään **Stream**-ominaisuudessa millisekunteina.  Tämä arvo voi olla alueella 100 (1/10 sekuntia) – 3 600 000 (1 tunti).

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Esimerkki
### <a name="add-photos-to-an-image-gallery-control"></a>Lisää valokuvia Kuvavalikoima-ohjausobjektiin
1. Lisää **Kamera**-ohjausobjekti, anna sen nimeksi **MyCamera** ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **Collect(MyPix, MyCamera.Photo)**

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?

    Haluatko lisätietoja **[Collect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
2. Paina F5 ja ota valokuva napsauttamalla tai napauttamalla **MyCamera**.
3. Lisää **[Pystysuuntainen valikoima](control-gallery.md)** -ohjausobjekti ja muuta sen **[Kuva](control-image.md)**-ohjausobjektin sekä itse **Kuvavalikoima**-ohjausobjektin koko näyttöön sopivaksi.
4. Aseta **Kuvavalikoima**-ohjausobjektin **[Kohteet](properties-core.md)**-ominaisuuden arvoksi:<br>**MyPix**.
5. Määritä **Kuva**-ohjausobjektin **[Image](properties-visual.md)**-ominaisuudeksi seuraava lauseke:<br>
   **ThisItem.Url**

    Ottamasi kuva näkyy **Kuvavalikoima**-ohjausobjektissa.
6. Ota niin monta kuvaa kuin haluat ja palaa oletustyötilaan painamalla Esc.
7. (valinnainen) Määritä **Kuva**-ohjausobjektin **OnSelect**-ominaisuudeksi **Kuvavalikoima**-ohjausobjektissa **Remove(MyPix, ThisItem)**, paina F5 ja poista valokuva napsauttamalla tai napauttamalla sitä.

Voit käyttää **[SaveData](../functions/function-savedata-loaddata.md)**-funktiota tallentaaksesi valokuvat paikallisesti tai **[Patch](../functions/function-patch.md)**-funktiota tietolähteen päivittämiseksi.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
Kamerasyötteen näyttämisen lisäksi kameran ohjausobjekti toimii myös painikkeena, joka ottaa kuvan. Siinä on siis samanlaisia helppokäyttötoimintojen kannalta huomioon otettavia seikkoja kuin painikkeilla.

### <a name="video-alternatives"></a>Vaihtoehdot videoille
* Harkitse vaihtoehtoisen syöttötavan lisäämistä näkövammaisille käyttäjille. Esimerkiksi **[Lisää kuva](control-add-picture.md)**, jonka avulla käyttäjät voivat ladata kuvan laitteestaan.

### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **[FocusedBorderColor](properties-color-border.md)**  ja ulkopuolinen väri

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.

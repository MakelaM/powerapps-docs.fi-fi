---
title: 'Verkko viiva koodi – skannerin ohjaus objekti: viittaus | Microsoft Docs'
description: Viiva koodi skannerin ohjaus objektin tiedot, mukaan lukien ominaisuudet ja esimerkit
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d1162c0c9954e67196eb4d3e42b2c91bdc3bf804
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986986"
ms.PowerAppsDecimalTransform: true
---
# <a name="web-barcode-scanner-control-experimental-in-powerapps"></a>Verkko viiva koodi – skannerin ohjaus objekti (kokeellinen) Powerappsissa

Vanha viiva koodin tarkistuksen ohjaus objekti, joka on vanhentunut, mutta saattaa olla hyödyllinen koodien skannaamisen kannalta selaimessa.

## <a name="description"></a>Kuvaus

Ohjaus objekti esittää kameran syötteen sovelluksessa, jotta käyttäjät voivat skannata viiva koodeja kaikissa laitteissa. Ohjaus objekti on vanhentunut huonon suoritus tehon vuoksi, ja mobiili **[viiva koodi skannerin](control-new-barcode-scanner.md)** ohjaus objekti korvaa tämän ohjaus objektin.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet

**barcode scanner** – Sovelluksen käyttämän viivakoodiskannerin numeerinen tunnus laitteessa, jossa on useampi kuin yksi viivakoodiskanneri.

## <a name="additional-properties"></a>Lisäominaisuudet

**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**ShowLiveBarcodeDetection** – Ilmaisee, näytetäänkö visuaalisia tietoja viivakoodien tunnistuksen tilasta. Tutkittavat alueet osoitetaan keltaisilla suorakulmioilla. Vihreä viiva suorakulmion halki osoittaa onnistuneen viivakoodin tunnistuksen.

**Stream** – **StreamRate**-ominaisuuden perusteella automaattisesti päivitetty kuva.

**StreamRate** – Miten usein kuva päivitetään **Stream**-ominaisuudessa millisekunteina.  Tämä arvo voi olla alueella 100 (1/10 sekuntia) – 3 600 000 (1 tunti).

**Teksti** – Skannerin viimeksi tunnistaman viivakoodin arvo.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät toiminnot

[**Patch**( *DataSource*; *BaseRecord*; *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Esimerkki

### <a name="add-photos-to-an-image-gallery-control"></a>Lisää valokuvia Kuvavalikoima-ohjausobjektiin

1. Lisää **viivakoodiskannerin** ohjausobjekti ja anna sen nimeksi **Oma viivakoodiskanneri**

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?

1. Lisää **Selite** -ohjaus objekti ja valitse sen tuloste viiva koodi skannerin **teksti** -ominaisuuteen.

1. Tarkista **Barcodetype** -ominaisuudessa määritetyn tyypin viiva koodi.

    Nimi näyttää skannatun viiva koodin.

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet

### <a name="video-alternatives"></a>Vaihtoehdot videoille

* Harkitse **[selitteen](control-text-box.md)** lisäämistä, jonka **[Teksti](properties-core.md)** -objektin arvoksi on asetettu viivakoodiskannerin **Teksti**. Koska viivakoodiskanneri ei näytä tunnistettua viivakoodiarvoa, tämä tekee skannerista helppokäyttöisen kaikille käyttäjille, ei vain näkövammaisille.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki

* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

    > [!NOTE]
  > Näytön luku ohjelmat ilmoittavat, kun uusi viiva koodi on löytynyt. Arvoa ei julkisteta. Niin kauan kuin viiva koodi on näkymässä, näytönlukijat muistuttavat käyttäjää viiden sekunnin välein, että samaa viiva koodia tunnistetaan yhä.

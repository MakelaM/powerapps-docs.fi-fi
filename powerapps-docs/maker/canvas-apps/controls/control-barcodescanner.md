---
title: 'WWW-viivakoodiskannerin ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja, kuten ominaisuudet ja esimerkkejä, Viivakoodiskanneri ohjausobjektista
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
ms.openlocfilehash: 787fa34bdfcabf6103fefd82f66e976b680544e2
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61544587"
ms.PowerAppsDecimalTransform: true
---
# <a name="web-barcode-scanner-control-experimental-in-powerapps"></a>WWW-viivakoodiskannerin ohjausobjekti (kokeellinen) powerappsissa

Vanhat viivakoodien skannaus ohjausobjektin, joka on vanhentunut, mutta voi olla hyötyä tarkistus koodit selaimessa.

## <a name="description"></a>Kuvaus

Ohjausobjekti näyttää kameran syötteen sovelluksessa, niin, että käyttäjät voivat skannata viivakoodeja kaikissa laitteissa. Ohjausobjekti on vanhentunut vuoksi heikentää suorituskykyä ja mobile **[Viivakoodiskanneri](control-new-barcode-scanner.md)** ohjausobjektin korvaa tämän ohjausobjektin.

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

1. Lisää **nimen** ohjausobjekti ja määritä sen tulosteeksi Viivakoodiskanneri **tekstin** ominaisuus.

1. Skannaa tyypin viivakoodi **BarcodeType** ominaisuus.

    Selite näyttää skannatun viivakoodin.

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet

### <a name="video-alternatives"></a>Vaihtoehdot videoille

* Harkitse **[selitteen](control-text-box.md)** lisäämistä, jonka **[Teksti](properties-core.md)** -objektin arvoksi on asetettu viivakoodiskannerin **Teksti**. Koska viivakoodiskanneri ei näytä tunnistettua viivakoodiarvoa, tämä tekee skannerista helppokäyttöisen kaikille käyttäjille, ei vain näkövammaisille.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki

* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

    > [!NOTE]
  > Näytönlukuohjelmat ilmoittavat, kun uusi viivakoodi on havaittu. Arvo ei voi ilmoitti. Niin kauan kuin viivakoodi on näkyvissä, näytönlukuohjelmat muistuttavat käyttäjän viiden sekunnin välein, joka sama tunnistettu viivakoodi on edelleen.

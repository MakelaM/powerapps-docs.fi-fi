---
title: 'Viivakoodiskannerin ohjausobjekti: viittaus | Microsoft Docs'
description: Viivakoodiskannerin ohjausobjektia koskevia tietoja, kuten ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: 8cd0c84f508c13e8064b0e5bc93b01024cf22120
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="barcode-scanner-control-experimental-in-powerapps"></a>Viivakoodiskannerin ohjausobjekti (kokeellinen) PowerAppsissa
Kokeellinen ohjausobjekti, jolla käyttäjä voi ottaa valokuvia käyttämällä laitteen viivakoodiskanneria.

## <a name="description"></a>Kuvaus
Jos lisäät tämän ohjausobjektin, käyttäjä voi päivittää tietolähteeseen yhden tai useita valokuvia mistä tahansa sovelluksen käyttöpaikasta.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**barcode scanner** – Sovelluksen käyttämän viivakoodiskannerin numeerinen tunnus laitteessa, jossa on useampi kuin yksi viivakoodiskanneri.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**Brightness** – Miten paljon valoa käyttäjä näkee kuvassa.

**Contrast** – Miten helposti käyttäjä voi erottaa samankaltaiset värit kuvasta.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnStream** – Miten sovellus reagoi, kun **Stream**-ominaisuus päivitetään.

**Photo** – Kuva, joka siepataan, kun käyttäjä ottaa kuvan.

**ShowLiveBarcodeDetection** – Ilmaisee, näytetäänkö visuaalisia tietoja viivakoodien tunnistuksen tilasta. Tutkittavat alueet osoitetaan keltaisilla suorakulmioilla. Vihreä viiva suorakulmion halki osoittaa onnistuneen viivakoodin tunnistuksen.

**Stream** – **StreamRate**-ominaisuuden perusteella automaattisesti päivitetty kuva.

**StreamRate** – Miten usein kuva päivitetään **Stream**-ominaisuudessa millisekunteina.  Tämä arvo voi olla välillä 100 (1/10 sekuntia) – 3 600 000 (1 tunti).

**Teksti** – Skannerin viimeksi tunnistaman viivakoodin arvo.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun kohdistin on ohjausobjektin päällä.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan (tai näytön, jos pääsäilöä ei ole) välinen etäisyys.

**Zoom** – Prosenttiosuus, jonka verran viivakoodiskannerin kuvaa tai PDF-katseluohjelman tiedoston näkymää suurennetaan.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Patch**( *Tietolähde*, *Perustietue*, *Muutostietue* )](../functions/function-patch.md)

## <a name="example"></a>Esimerkki
### <a name="add-photos-to-an-image-gallery-control"></a>Lisää valokuvia Kuvavalikoima-ohjausobjektiin
1. Lisää **viivakoodiskannerin** ohjausobjekti ja anna sen nimeksi **Oma viivakoodiskanneri**

    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **Selite**-ohjausobjekti ja määritä sen tulosteeksi viivakoodin **Teksti**.  
3. Skannaa tyypin viivakoodi BarcodeType-ominaisuudella.
4. Selite näyttää skannatun viivakoodin.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="video-alternatives"></a>Vaihtoehdot videoille
* Harkitse **[selitteen](control-text-box.md)** lisäämistä, jonka **[Teksti](properties-core.md)**-objektin arvoksi on asetettu viivakoodiskannerin **Teksti**. Koska viivakoodiskanneri ei näytä tunnistettua viivakoodiarvoa, tämä tekee skannerista helppokäyttöisen kaikille käyttäjille, ei vain näkövammaisille.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

    > [!NOTE]
> Näytönlukuohjelmat ilmoittavat uusista viivakoodeista. Arvoa ei ilmoiteta. Niin kauan kuin viivakoodi on näkyvissä, näytönlukuohjelmat muistuttavat viiden sekunnin välein, että tunnistettu viivakoodi on edelleen sama.

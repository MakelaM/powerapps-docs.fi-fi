---
title: 'Viivakoodiskannerin ohjausobjekti: viittaus | Microsoft Docs'
description: Viivakoodiskannerin ohjausobjektia koskevia tietoja, kuten ominaisuudet ja esimerkkejä
author: fikaradz
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 22b5cf081755f25b3aff33c36137547882fe3812
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34803464"
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

**[OnSelect](properties-core.md)** – Sovelluksen reagointitapa, kun käyttäjä napsauttaa tai napauttaa ohjausobjektia.

**OnStream** – Miten sovellus reagoi, kun **Stream**-ominaisuus päivitetään.

**Photo** – Kuva, joka siepataan, kun käyttäjä ottaa kuvan.

**ShowLiveBarcodeDetection** – Ilmaisee, näytetäänkö visuaalisia tietoja viivakoodien tunnistuksen tilasta. Tutkittavat alueet osoitetaan keltaisilla suorakulmioilla. Vihreä viiva suorakulmion halki osoittaa onnistuneen viivakoodin tunnistuksen.

**Stream** – **StreamRate**-ominaisuuden perusteella automaattisesti päivitetty kuva.

**StreamRate** – Miten usein kuva päivitetään **Stream**-ominaisuudessa millisekunteina.  Tämä arvo voi olla alueella 100 (1/10 sekuntia) – 3 600 000 (1 tunti).

**Teksti** – Skannerin viimeksi tunnistaman viivakoodin arvo.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan (tai näytön, jos pääsäilöä ei ole) välinen etäisyys.

**Zoom** – Prosenttiosuus, jonka verran viivakoodiskannerin kuvaa tai PDF-katseluohjelman tiedoston näkymää suurennetaan.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Esimerkki
### <a name="add-photos-to-an-image-gallery-control"></a>Lisää valokuvia Kuvavalikoima-ohjausobjektiin
1. Lisää **viivakoodiskannerin** ohjausobjekti ja anna sen nimeksi **Oma viivakoodiskanneri**

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
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

---
title: 'Kynän syöte -ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja Kynän syöte -ohjausobjektista, kuten ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: 7e5be9b68b501279329c23f9afe5d451487fa8d1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="pen-input-control-in-powerapps"></a>PowerAppsin Kynän syöte -ohjausobjekti
Ohjausobjekti, jolla käyttäjä voi piirtää, pyyhkiä ja korostaa kuvan alueita.

## <a name="description"></a>Kuvaus
Käyttäjä voi käyttää tätä ohjausobjektia valkotaulun tavoin ja piirtää kaavioita ja kirjoittaa sanoja, jotka voidaan muuntaa kirjoitetuksi tekstiksi.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Color](properties-color-border.md)** – Syötettyjen vetojen väri.

**Mode** – Ohjausobjekti on joko **Piirrä** tai **Poista**-tilassa.  Tilan valinta on vanhentunut.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva**vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**Input** – Syöte.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[SelectionColor](properties-color-border.md)** – Luettelon valitun kohteen tai kohteiden tekstin väri tai kynä-ohjausobjektin valintatyökalun väri.

**SelectionThickness** – Kynän syöte -ohjausobjektin valintatyökalun paksuus.

**ShowControls** – Näytetäänkö ääni- tai videosoittimessa esimerkiksi toistopainike ja äänenvoimakkuuden liukusäädin sekä näytetäänkö kynän ohjausobjektissa esimerkiksi piirustuksen, poistamisen ja tyhjentämisen kuvakkeet.

**[Size](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun kohdistin on ohjausobjektin päällä.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="related-functions"></a>Liittyvät funktiot
[**Collect**( *KokoelmanNimi*, *KerättävätTiedot* )](../functions/function-clear-collect-clearcollect.md)

## <a name="example"></a>Esimerkki
### <a name="create-a-set-of-images"></a>Kuvajoukon luominen
1. Lisää **Kynän syöte** -ohjausobjekti, anna sille nimi **MyDoodles** ja aseta sen **ShowControls**-ominaisuudeksi **tosi**.
   
    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **[Painike](control-button.md)**-ohjausobjekti, siirrä se **MyDoodles**-kohdan alle ja aseta **[Painike](control-button.md)**-ohjausobjektin **[Text](properties-core.md)**-ominaisuudeksi **Lisää**.
3. Määritä **[Painikkeen](control-button.md)** **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Collect(Doodles, {Sketch:MyDoodles.Image})**
4. Lisää **Kuvavalikoima**-ohjausobjekti, siirrä se **[Painike](control-button.md)**-ohjausobjektin alle ja pienenä **Kuvavalikoima**-ohjausobjektin kokoa, kunnes se näyttää vain kolme kohdetta.
5. Määritä **Kuvavalikoima**-ohjausobjektin **[Items](properties-core.md)**-ominaisuudeksi **Doodles** ja paina F5-näppäintä.
6. Piirrä **MyDoodles**-kohtaan kuva ja napsauta tai napauta **[Painike](control-button.md)**-ohjausobjektia.
   
    Piirtämäsi kuva näkyy **Kuvavalikoima**-ohjausobjektissa.
7. (valinnainen) Napsauta tai napauta **Kynän syöte** -ohjausobjektissa kuvaketta, niin piirtämäsi kuva poistetaan. Piirrä toinen kuva ja sitten napsauta tai napauta **[Painike](control-button.md)**-ohjausobjektia.
8. Aseta **Kuvavalikoima**-ohjausobjektissa **[Kuva](control-image.md)**-ohjausobjektin **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **Remove(Doodles, ThisItem)**
9. Poista piirustus napsauttamalla tai napauttamalla sitä **Kuvavalikoima**-ohjausobjektissa.

Voit käyttää **[SaveData](../functions/function-savedata-loaddata.md)**-funktiota piirustusten paikalliseen tallentamiseen tai **[Patch](../functions/function-patch.md)**-funktiota niiden tallentamiseksi tietolähteeseen.


---
title: 'Kynän syöte -ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja Kynän syöte -ohjausobjektista, kuten ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: 84981a00a516f553d3f1b318f12a6f68064c66b2
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31832167"
---
# <a name="pen-input-control-in-powerapps"></a>PowerAppsin Kynän syöte -ohjausobjekti
Ohjausobjekti, jolla käyttäjä voi piirtää, pyyhkiä ja korostaa kuvan alueita.

## <a name="description"></a>Kuvaus
Käyttäjä voi käyttää tätä ohjausobjektia valkotaulun tavoin ja piirtää kaavioita ja kirjoittaa sanoja, jotka voidaan muuntaa kirjoitetuksi tekstiksi.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Väri](properties-color-border.md)** – Syötettyjen vetojen väri.

**Tila** – Ohjausobjekti on joko **Piirrä**- tai **Poista**-tilassa.  Tilan valinta on vanhentunut.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi. Voidaan käyttää kuvaamaan ohjausobjektin tarkoitusta sekä vaihtoehtoisia syöttötapoja.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**Syöte** – Syöte.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[SelectionColor](properties-color-border.md)** – Luettelon valitun kohteen tai kohteiden tekstin väri tai kynä-ohjausobjektin valintatyökalun väri.

**SelectionThickness** – Kynän syöte -ohjausobjektin valintatyökalun paksuus.

**ShowControls** – Näytetäänkö ääni- tai videosoittimessa esimerkiksi toistopainike ja äänenvoimakkuuden liukusäädin sekä näytetäänkö kynän ohjausobjektissa esimerkiksi piirustuksen, poistamisen ja tyhjentämisen kuvakkeet.

**[Koko](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**[Työkaluvihje](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun kohdistin on ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**Collect**( *CollectionName*, *DatatoCollect* )](../functions/function-clear-collect-clearcollect.md)

## <a name="example"></a>Esimerkki
### <a name="create-a-set-of-images"></a>Kuvajoukon luominen
1. Lisää **Kynän syöte** -ohjausobjekti, anna sille nimi **MyDoodles** ja aseta sen **ShowControls**-ominaisuudeksi **true**.
   
    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **[Painike](control-button.md)**-ohjausobjekti, siirrä se **MyDoodles**-kohdan alle ja aseta **[Painike](control-button.md)**-ohjausobjektin **[Teksti](properties-core.md)**-ominaisuudeksi **Lisää**.
3. Määritä **[Painikkeen](control-button.md)** **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Collect(Doodles, {Sketch:MyDoodles.Image})**
4. Lisää **Kuvavalikoima**-ohjausobjekti, siirrä se **[Painike](control-button.md)**-ohjausobjektin alle ja pienennä **Kuvavalikoima**-ohjausobjektin kokoa, kunnes se näyttää vain kolme kohdetta.
5. Määritä **Kuvavalikoima**-ohjausobjektin **[Kohteet](properties-core.md)**-ominaisuudeksi **Doodles** ja paina F5-näppäintä.
6. Piirrä **MyDoodles**-kohtaan kuva ja napsauta tai napauta **[Painike](control-button.md)**-ohjausobjektia.
   
    Piirtämäsi kuva näkyy **Kuvavalikoima**-ohjausobjektissa.
7. (valinnainen) Napsauta tai napauta **Kynän syöte** -ohjausobjektissa kuvaketta, niin piirtämäsi kuva poistetaan. Piirrä toinen kuva ja sitten napsauta tai napauta **[Painike](control-button.md)**-ohjausobjektia.
8. Aseta **Kuvavalikoima**-ohjausobjektissa **[Kuva](control-image.md)**-ohjausobjektin **[OnSelect](properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **Remove(Doodles, ThisItem)**
9. Poista piirustus napsauttamalla tai napauttamalla sitä **Kuvavalikoima**-ohjausobjektissa.

Voit käyttää **[SaveData](../functions/function-savedata-loaddata.md)**-funktiota piirustusten paikalliseen tallentamiseen tai **[Ohjelmakorjaus](../functions/function-patch.md)**-funktiota niiden tallentamiseksi tietolähteeseen.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **[BorderColor](properties-color-border.md)** ja väri ohjausobjektin ulkopuolella (jos reuna on käytössä)
* **[Täyttö](properties-color-border.md)** ja väri ohjausobjektin ulkopuolella (jos reuna ei ole käytössä)

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

    > [!IMPORTANT]
> Näytönlukuohjelmien käyttäjät eivät voi käyttää **kynäsyötettä**. Anna aina vaihtoehtoinen syöttötapa. Esimerkiksi jos luonnos on pakollinen, suosittelemme lisäämään **[Lisää kuva](control-add-picture.md)** -ohjausobjektin, jolla käyttäjät voivat ladata kuvan. Molemmat tavat voidaan tarjota samanaikaisesti, ja käyttäjä voi valita haluamansa.

### <a name="keyboard-support"></a>Näppäimistön tuki

> [!IMPORTANT]
> Näppäimistöä käyttävät eivät voi käyttää **kynäsyötettä**. Anna aina vaihtoehtoinen syöttötapa. Esimerkiksi jos allekirjoitus on pakollinen, suosittelemme lisäämään **[Tekstisyöte](control-text-input.md)**-ohjausobjektin, jolla käyttäjät voivat kirjoittaa nimensä. Molemmat tavat voidaan tarjota samanaikaisesti, ja käyttäjä voi valita haluamansa.

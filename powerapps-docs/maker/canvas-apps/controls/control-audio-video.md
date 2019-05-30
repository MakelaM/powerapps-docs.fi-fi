---
title: 'Äänen ja videon ohjausobjektit: viittaus | Microsoft Docs'
description: Äänen ja videon ohjausobjekteja koskevaa tietoa, mukaan lukien ominaisuuksia ja esimerkkejä
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
ms.openlocfilehash: 7ac87e794341fe79a6e4f949893b64462c384f83
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61544633"
---
# <a name="audio-and-video-controls-in-powerapps"></a>Äänen ja videon ohjausobjektit PowerAppsissa
Ohjausobjekti, joka toistaa äänitiedoston, videotiedoston tai videon YouTubessa.

## <a name="description"></a>Kuvaus
**Ääni**-ohjausobjekti toistaa äänileikkeen tiedostosta, tallenteen **[Mikrofoni](control-microphone.md)**-ohjausobjektista tai ääniraidan videotiedoston.

**Video**-ohjausobjekti toistaa videoleikkeen tiedostosta, YouTubesta tai Microsoft Azure -mediapalveluista.  Tekstitys voidaan näyttää, jos se on määritetty.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**Loop** – Alkaako ääni- tai videoleike automaattisesti alusta, kun sen toistaminen lopetetaan.

**Media** – Ääni- tai video-ohjausobjektin toistaman leikkeen tunniste.

**ShowControls** – Näytetäänkö ääni- tai videosoittimessa esimerkiksi toistopainike ja äänenvoimakkuuden liukusäädin sekä näytetäänkö kynän ohjausobjektissa esimerkiksi piirustuksen, poistamisen ja tyhjentämisen kuvakkeet.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi. Tämän pitäisi olla video- tai äänileikkeen otsikko.

**AutoPause** – Keskeytetäänkö ääni- tai videoleike automaattisesti, jos käyttäjä siirtyy eri näyttöön.

**AutoStart** – Alkaako ääni- tai video-ohjausobjekti toistaa leikettä automaattisesti, kun käyttäjä siirtyy tämän ohjausobjektin sisältävään näyttöön.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**ClosedCaptionsUrl** – Vain video-ohjausobjekti.  Tekstityksen URL-osoite WebVTT-muodossa.  Sekä videon että tekstityksen URL-osoitteiden on oltava HTTPS-muodossa. Jos palvelin isännöi sekä video- että tekstitystiedostoa, palvelimen tulee tukea CORS:ää.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md) ** – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[Kuva](properties-visual.md)** – Kuvan, äänen tai mikrofonin ohjausobjektissa näkyvän kuvan nimi.

**[ImagePosition](properties-visual.md)** – Kuvan tai ohjausobjektin asettelu (**Täyttö**, **Sovita**, **Venytä**, **Vierekkäin** tai **Center**), jos kuva tai ohjausobjekti ei ole saman kokoinen kuin näyttö.

**OnEnd** – Miten sovellus reagoi, kun ääni- tai videoleikkeen toistaminen loppuu.

**OnPause** – Miten sovellus reagoi, kun käyttäjä keskeyttää leikkeen, jota ääni- tai video-ohjausobjekti on toistamassa.

**OnStart** – Miten sovellus reagoi, kun käyttäjä aloittaa tallentamisen mikrofoniohjausobjektilla.

**Keskeytetty** – *True*, jos median toisto -ohjausobjekti on sillä hetkellä keskeytetty, muuten *false*.

**[Nollaa](properties-core.md) ** – Palautuuko ohjausobjekti oletusarvoonsa.

**Start** – Toistetaanko ääni- tai videoleike.

**StartTime** – Aika siitä, kun ääni- tai videoleikkeen toistaminen on aloitettu.

**Aika** – Mediaohjausobjektin nykyinen sijainti.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**First**( *TableName* )](../functions/function-first-last.md)

## <a name="examples"></a>Esimerkkejä
### <a name="play-an-audio-or-video-file"></a>Ääni- tai videotiedoston toistaminen
1. Napsauta tai napauta **Tiedosto**-valikossa **Media**, napsauta tai napauta **Videot** tai **Ääni** ja sitten **Selaa**.
2. Selaa käytettävään tiedostoon, napsauta tai napauta sitä ja sitten **Avaa**.
3. Palaa oletustyötilaan painamalla Esc-näppäintä, lisää **Ääni**- tai **Video**-ohjausobjekti ja aseta sen **Media**-ominaisuus lisäämääsi tiedostoon.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?
4. Paina F5-näppäintä ja toista leike napsauttamalla tai napauttamalla lisäämäsi ohjausobjektin toistopainiketta.

    > [!TIP]
   > **Video**-ohjausobjektin toistopainike tulee näkyviin, kun pidät osoitinta ohjausobjektin päällä.
5. Palaa oletustyötilaan painamalla Esc-näppäintä.

### <a name="play-a-youtube-video"></a>Toista YouTube-video
1. Lisää **Video**-ohjausobjekti ja aseta sen **Media**-ominaisuus YouTube-videon URL-osoitteeseen lainausmerkeissä.
2. Paina F5 ja toista sitten leike napsauttamalla tai napauttamalla **Video**-ohjausobjektin toistopainiketta.
3. Palaa oletustyötilaan painamalla ESC-näppäintä.

### <a name="play-a-video-from-azure-media-services"></a>Videon toistaminen Microsoft Azure -mediapalveluista
1. Kun videot on julkaistu Microsoft Azure -mediapalveluissa, kopioi kokoonpanotietojen URL-osoite. Käynnistä palvelusi virtauttamisen päätepiste, jos sitä ei ole vielä käynnistetty.
1. Lisää **Video**-ohjausobjekti ja aseta sen **Media**-ominaisuus Microsoft Azure -mediapalveluiden videon URL-osoitteeseen lainausmerkeissä.
2. Paina F5 ja toista sitten leike napsauttamalla tai napauttamalla **Video**-ohjausobjektin toistopainiketta.
3. Palaa oletustyötilaan painamalla ESC-näppäintä.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="audio-and-video-alternatives"></a>Vaihtoehdot ääni- ja videoleikkeille
* **ShowControls**-ominaisuutena on oltava true, jotta käyttäjät voivat kuunnella tai katsella multimediaa omassa tahdissaan. Tämän ansiosta käyttäjät voivat myös näyttää tai piilottaa tekstityksen tai valita koko näytön tilan videosoittimessa.
* Videoissa on oltava tekstitys.
  *  YouTube-videoihin voit lisätä tekstityksen YouTuben tarjoamien luontityökalujen avulla.
  *  Muihin videoihin voit luoda tekstityksen WebVTT-muodossa, ladata sen ja määrittää **ClosedCaptionsUrl**-ominaisuuden url-sijaintiin. Rajoituksia on useita. Videota ja tekstitystä isännöivän palvelimen on tuettava CORS:ää ja käytettävä HTTPS-protokollaa. Tekstitys ei toimi Internet Explorerissa.
* Harkitse ääni- tai videotallenteen antamista käyttämällä jotakin seuraavista menetelmistä:
  1. Lisää teksti **[selitteeseen](control-text-box.md)** ja sijoita se multimediasoittimen viereen. Halutessasi voit luoda **[painikkeen](control-button.md)**, jolla tekstin voi näyttää tai piilottaa.
  2. Lisää teksti eri näyttöön. Luo **[painike](control-button.md)**, joka siirtyy näytölle, ja sijoita painike multimediasoittimen viereen.
  3. Jos kuvaus on lyhyt, se voidaan lisätä **[AccessibleLabel](properties-accessibility.md)**-objektiin.

### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **[FocusedBorderColor](properties-color-border.md) ** ja ulkopuolinen väri
* **[Kuva](properties-visual.md)** ja multimediasoittimen ohjausobjektit (jos sovellettavissa)
* **[Täyttö](properties-color-border.md)** ja multimediasoittimen ohjausobjektit (jos täyttö on näkyvissä)

Anna tekstitys ja/tai tallenne, jos videosisällössä on värikontrastiongelmia.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.
* **AutoStart**-ominaisuuden arvona on oltava false, koska näppäimistön käyttäjien voi olla vaikea lopettaa toistoa nopeasti.

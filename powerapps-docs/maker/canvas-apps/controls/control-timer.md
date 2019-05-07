---
title: 'Ajastin-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja Ajastin-ohjausobjektista, kuten ominaisuudet ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5d20e2324f2efb4f866ed4fc183f289733c10a41
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61560463"
ms.PowerAppsDecimalTransform: true
---
# <a name="timer-control-in-powerapps"></a>Ajastin-ohjausobjekti PowerAppsissa
Ohjausobjekti, joka voi määrittää, miten sovelluksesi vastaa tietyn ajan kuluttua.

## <a name="description"></a>Kuvaus
Ajastimet voivat esimerkiksi määrittää, miten kauan ohjausobjekti näkyy, tai muuttaa ohjausobjektin muita ominaisuuksia tietyn ajan kuluttua.

> [!NOTE]
> PowerApps Studio ajastimet suorittaa vain esikatselutilassa.


## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**Kesto** – Miten kauan ajastin on käynnissä millisekunneissa.  Suurinta arvoa ei ole.

**OnTimerEnd** – Miten sovellus reagoi, kun ajastin lopettaa työnkulun suorittamisen.

**Toista** – Käynnistyykö ajastin automaattisesti uudelleen, kun sen toiminta pysähtyy.

## <a name="additional-properties"></a>Lisäominaisuudet
**[Align](properties-text.md)** – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**AutoPause** – Keskeytetäänkö ajastimen ohjausobjekti automaattisesti, jos käyttäjä siirtyy eri näyttöön.

**AutoStart** – Alkaako ajastimen ohjausobjekti toistaa automaattisesti, kun käyttäjä siirtyy tämän ohjausobjektin sisältävään näyttöön.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Väri](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)**  – ohjausobjektin tekstin paino: **Lihavoitu**, **Semibold**, **Normaali**, tai **ohuempi**.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun hiiren kohdistin on kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Kursivoitu](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**[OnSelect](properties-core.md)** – Sovelluksen reagointitapa, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnTimerStart** – Sovelluksen reagointitapa, kun ajastin käynnistyy.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[Reset](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**[Size](properties-text.md)** – Ohjausobjektissa näkyvän tekstin fonttikoko.

**Start** – Käynnistyykö ajastin.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Text](properties-core.md)**  – Teksti, joka näytetään ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

**[Työkaluvihje](properties-core.md)** – Työkaluvihjeen ohjeteksti, joka ilmestyy näkyviin, kun hiiren osoitin on ohjausobjektin päällä.

**[Underline](properties-text.md)** – Onko ohjausobjektissa näytettävä teksti alleviivattu.

**[Visible](properties-core.md)** – Onko ohjausobjekti näytössä vai piilotettuna.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät funktiot
[**Refresh**( *DataSource* )](../functions/function-refresh.md)

## <a name="examples"></a>Esimerkkejä
### <a name="show-a-countdown"></a>Näytä aikalaskuri
1. Lisää ajastin ja anna sille nimi **Countdown**.

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Määritä ajastimen **Kesto**-ominaisuudeksi **10000** sekä **Toista**- ja **Autostart**-ominaisuudet tilaan **true**.
3. (valinnainen) Tee ajastimen lukemisesta helpompaa asettamalla sen **[Korkeus](properties-size-location.md)**-ominaisuudeksi **160**, **[Leveys](properties-size-location.md)**-ominaisuudeksi **600** ja **[Koko](properties-text.md)**-ominaisuudeksi **60**.
4. Lisää selite ja aseta sen **[Teksti](properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**"Number of seconds remaining: " & RoundUp(10-Countdown.Value/1000; 0)**

    Haluatko lisätietoja **[RoundUp](../functions/function-round.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?

    Selite näyttää, kuinka monen sekunnin kuluttua ajastin käynnistyy uudelleen.

### <a name="animate-a-control"></a>Ohjausobjektin animointi
1. Lisää ajastin ja anna sille nimi **FadeIn**.

    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Määritä ajastimen **Kesto**-ominaisuuden arvoksi **5 000**, **Toista**-ominaisuuden arvoksi **tosi** ja **[Teksti](properties-core.md)**-ominaisuuden arvoksi **Toggle animation** (Vaihda animaatio).
3. (valinnainen) Tee ajastimen lukemisesta helpompaa asettamalla sen **[Korkeus](properties-size-location.md)**-ominaisuudeksi **160**, **[Leveys](properties-size-location.md)**-ominaisuudeksi **600** ja **[Koko](properties-text.md)**-ominaisuudeksi **60**.
4. Lisää selite ja aseta sen **[Teksti](properties-core.md)**-ominaisuus näyttämään **Welcome!** ja määritä sen **[Väri](properties-color-border.md)**-ominaisuudeksi tämä kaava:
   <br>**ColorFade(Color.BlueViolet; FadeIn.Value/5000)**

    Haluatko lisätietoja **[ColorFade](../functions/function-colors.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?

5. Käynnistä tai pysäytä animaatio valitsemalla ajastinpainike. Selitteen teksti häivytetään valkoiseksi, minkä jälkeen se palaa täyteen voimakkuuteen. Tämän jälkeen prosessi toistuu.

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
Ohjeet ovat samat kuin **[painike](control-button.md)** ohjausobjektin koskevat **ajastin** ohjausobjektissa, jos käyttäjät voivat käyttää sitä.

### <a name="background-timers"></a>Taustan ajastimet
Taustan ajastimet suorittaa automaattisesti, ja se on piilotettu. Käyttää niitä tukevia roolissa jossa kuluneen ajan on pieni kiinnostuksen käyttäjälle. Voit esimerkiksi päivittää tiedot joka minuutti tai ilmoitussanoma näyttää vain tietyn ajanjakson.

Taustan ajastimet tulee olla niiden **[näkyvissä](properties-core.md)** ominaisuuden arvoksi epätosi, niin, että ne on piilotettu kaikilta käyttäjiltä.

### <a name="timing-considerations"></a>Ajoitus huomioon otettavia seikkoja
Jos **ajastin** suoritetaan automaattisesti, mieti onko käyttäjillä riittävästi aikaa lukea ja käyttää sisältöä. Näppäimistön ja Näytönlukuohjelman käyttäjät voivat on enemmän aikaa ajastettuun tapahtumaan.

Jokin seuraavista strategioista riittää:
* Salli käyttäjien peruuttaa ajastettu tapahtuma.
* Salli käyttäjien säätää aikarajaa ennen sen alkamista.
* Varoita 20 sekuntia ennen aikarajan ja tarjoavat helpon tavan umpeutumista.

Nämä vaatimukset eivät koske kaikkia tilanteita. Lue lisää [aikarajoja koskevasta WCAG 2.0 -ohjeesta](https://www.w3.org/TR/WCAG20/#time-limits).

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* Jos ajastin käynnistyy muutokset nykyisessä näytössä, käytä [reaaliaikaisen alueen](../accessible-apps-live-regions.md) – Näytönlukuohjelman käyttäjät kertoa, mitä muuttaa.

    > [!NOTE]
    > Ajastin on näkyvissä ja käynnissä, näytönlukuohjelmat ilmoittavat kuluneen ajan viiden sekunnin välein.

* Älä käytä **[tekstin](properties-core.md)** aikasidonnaisiin ja tärkeisiin tietoihin ohjausobjektin ominaisuus. Näytönlukuohjelmat ei ilmoita muutokset  **[tekstin](properties-core.md)**.
* -Vuorovaikutteinen ajastimet:
    * **[Teksti](properties-core.md)** on oltava käytössä.
    * Harkitse **[nimen](control-text-box.md)** ohjausobjektin kuluneen ajan näyttämiseksi. Ajastin ajastimen **[tekstin](properties-core.md)** ominaisuudeksi kehota käyttäjää Käynnistä tai Pysäytä ajastin.

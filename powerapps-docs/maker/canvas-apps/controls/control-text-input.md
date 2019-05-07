---
title: 'Tekstisyötteen ohjausobjekti: viitetiedot | Microsoft Docs'
description: Tekstisyötteen ohjausobjektin ominaisuudet ja joitakin esimerkkejä
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
ms.openlocfilehash: a46635276f6598cf0591dc21ae5aeb855b6667c1
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61560475"
ms.PowerAppsDecimalTransform: true
---
# <a name="text-input-control-in-powerapps"></a>PowerAppsin Tekstisyöte-ohjausobjekti
Ruutu, johon käyttäjä voi kirjoittaa tekstiä, numeroita ja muuta tietoa.

## <a name="description"></a>Kuvaus
Käyttäjä voi määrittää tietoa kirjoittamalla tekstisyötteen ohjausobjektiin. Riippuen siitä, miten määrität sovelluksen, tietoja voidaan lisätä tietolähteeseen, niitä voidaan käyttää väliaikaisen arvon laskemiseen tai jollakin muulla tavalla.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Default](properties-core.md)** – Ohjausobjektin alkuarvo ennen kuin käyttäjä muuttaa sitä.

**[Text](properties-core.md)**  – Teksti, joka näytetään ohjausobjektissa tai jonka käyttäjä kirjoittaa ohjausobjektiin.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[Align](properties-text.md)** – Tekstin asettelu suhteessa ohjausobjektin vaakasuoraan keskikohtaan.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**Clear** – Näyttääkö tekstisyötteen ohjausobjekti merkin X, jota käyttäjä voi napauttaa tai napsauttaa tyhjentääkseen kyseisen ohjausobjektin sisällön.

**[Color](properties-color-border.md)**  – Ohjausobjektin tekstin väri.

**DelayOutput** – Kun tämän arvo on tosi, käyttäjän syöte rekisteröidään puolen sekunnin viiveellä.  Toiminnosta on hyötyä, jos halutaan viivyttää kalliita toimintoja, kunnes käyttäjä on syöttänyt tekstin (esimerkiksi suodatus kun syötettä käytetään muissa kaavoissa).

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[DisabledFill](properties-color-border.md)** – Ohjausobjektin taustaväri, jos sen **[DisplayMode](properties-core.md)**-asetuksena on **Poistettu käytöstä**.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Font](properties-text.md)** – Näytössä näkyvän fonttiperheen nimi.

**[FontWeight](properties-text.md)**  – ohjausobjektin tekstin paino: **Lihavoitu**, **Semibold**, **Normaali**, tai **ohuempi**.

**Format** – Onko käyttäjän syöte rajoitettu vain numeroihin vai voiko se olla mitä tahansa tekstiä.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**HintText** – Vaaleanharmaa teksti, joka näkyy tekstisyötteen ohjausobjektissa, jos se on tyhjä.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin päällä.

**[HoverColor](properties-color-border.md)**  – Ohjausobjektin tekstin väri, kun hiiren kohdistin on sen päällä.

**[HoverFill](properties-color-border.md)**  – Ohjausobjektin taustaväri, kun hiiren kohdistin on sen päällä.

**[Italic](properties-text.md)**  – Onko ohjausobjektin teksti kursivoitu.

**[LineHeight](properties-text.md)** – Rivin korkeus eli esimerkiksi tekstin tai luettelon rivien välinen etäisyys.

**MaxLength** – Ilmaisee, montako merkkiä käyttäjä voi kirjoittaa tekstisyötteen ohjausobjektiin.

**Mode** – Ohjausobjekti on **SingleLine**-, **MultiLine**- tai **Password**-tilassa.

**[OnChange](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[PaddingBottom](properties-size-location.md)** – Ohjausobjektin tekstin ja alareunan välinen etäisyys.

**[PaddingLeft](properties-size-location.md)** – Ohjausobjektin tekstin ja vasemman reunan välinen etäisyys.

**[PaddingRight](properties-size-location.md)** – Ohjausobjektin tekstin ja oikean reunan välinen etäisyys.

**[PaddingTop](properties-size-location.md)** – Ohjausobjektin tekstin ja yläreunan välinen etäisyys.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedColor](properties-color-border.md)** – Ohjausobjektin tekstin väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**[PressedFill](properties-color-border.md)** – Ohjausobjektin taustaväri, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[RadiusBottomLeft](properties-size-location.md)** – Ohjausobjektin vasemman alakulman pyöristysaste.

**[RadiusBottomRight](properties-size-location.md)** – Ohjausobjektin oikean alakulman pyöristysaste.

**[RadiusTopLeft](properties-size-location.md)** – Ohjausobjektin vasemman yläkulman pyöristysaste.

**[RadiusTopRight](properties-size-location.md)** – Ohjausobjektin oikean yläkulman pyöristysaste.

**[Reset](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**[Size](properties-text.md)** – Ohjausobjektissa näytettävän tekstin fonttikoko.

**[Strikethrough](properties-text.md)**  – Onko ohjausobjektissa näkyvä teksti yliviivattua.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Underline](properties-text.md)** – Onko ohjausobjektissa näytettävä teksti alleviivattu.

**[Visible](properties-core.md)** – Onko ohjausobjekti näytössä vai piilotettuna.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Aiheeseen liittyvät funktiot
[**DateTimeValue**( *String* )](../functions/function-datevalue-timevalue.md)

## <a name="examples"></a>Esimerkkejä
### <a name="collect-data"></a>Tietojen kerääminen
1. Lisää kaksi tekstisyötteen ohjausobjektia ja anna niiden nimiksi **inputFirst** ja **inputLast**.
   
    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää painike, määritä sen **[Text](properties-core.md)**-ominaisuus näyttämään **Lisää** ja määritä sen **[OnSelect](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **Collect(Names; {FirstName:inputFirst.Text; LastName:inputLast.Text})**
   
    Haluatko lisätietoja **[Collect](../functions/function-clear-collect-clearcollect.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
3. Lisää tekstivalikoima pysty- tai vaakasuunnassa, aseta sen **[Items](properties-core.md)**-ominaisuus näyttämään **Nimet** ja aseta **Subtitle1**-kohdan **[Text](properties-core.md)**-ominaisuudeksi **ThisItem.FirstName**.
4. (valinnainen) Poista mallivalikoiman alimmainen selite, jonka nimi on **Body1**, ja aseta valikoiman **[TemplateSize](control-gallery.md)**-ominaisuudeksi **80**.
5. Paina F5-näppäintä, kirjoita tekstimerkkijono kenttiin **inputFirst** ja **inputLast**, ja napsauta tai napauta **Lisää**-painiketta.
6. (valinnainen) Lisää enemmän nimiä kokoelmaan ja palaa oletustyötilaan painamalla ESC-näppäintä.

### <a name="prompt-for-a-password"></a>Kysy salasana

1. Lisää tekstisyötteen ohjausobjekti, anna sen nimeksi **inputPassword** ja aseta sen **Tila**-ominaisuudeksi **Salasana**.

1. Lisää selite ja aseta sen **[Text](properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **If(inputPassword.Text = "P@ssw0rd"; "Access granted"; "Access denied")**

    Haluatko lisätietoja **[If](../functions/function-if.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?

1. Paina F5-näppäintä ja kirjoita sitten **P@ssw0rd** kohtaan **inputPassword**.

    Kun olet kirjoittanut salasanan, selite ei enää näytä tekstiä **Access denied**, vaan siinä näkyy teksti **Access granted**.

1. Palaa oletustyötilaan painamalla Esc-näppäintä.

1. (valinnainen) Lisää ohjausobjekti, kuten nuoli, määritä se siirtymään toiseen näyttöön ja näytä se vasta, kun käyttäjä kirjoittaa salasanan.

1. (valinnainen) Lisää painike, määritä sen **[Text](properties-core.md)**-ominaisuus näyttämään **Kirjaudu sisään**, lisää ajastin ja poista käytöstä tekstisyötteen ohjausobjekti tietyksi ajaksi, jos käyttäjä kirjoittaa väärän salasanan ja napsauttaa tai napauttaa sitten **Kirjaudu sisään** -painiketta.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
* [Tavalliset värikontrastivaatimukset](../accessible-apps-color.md) pätevät.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.
 

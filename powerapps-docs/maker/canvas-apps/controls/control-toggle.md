---
title: 'Ohjausobjektin vaihtopainike: viitetiedot | Microsoft Docs'
description: Tietoja ohjausobjektin vaihtopainikkeesta, kuten ominaisuudet ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4ec115eecc676a7ec5bea3b04b135eeb63268449
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993257"
---
# <a name="toggle-control-in-powerapps"></a>Ohjausobjektin vaihtopainike PowerAppsissa
Ohjausobjekti, jonka käyttäjä voi ottaa käyttöön tai poistaa käytöstä siirtämällä sen kahvaa.

## <a name="description"></a>Kuvaus
Vaihtopainike on suunniteltu uusimpia käyttöliittymiä varten, mutta se toimii samalla tavalla kuin valintaruutu.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**[Oletus](properties-core.md)** – Ohjausobjektin alkuarvo ennen kuin käyttäjä muuttaa sitä.

**[Arvo](properties-core.md)** – Syöteohjausobjektin arvo.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[DisabledBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, jos sen **[DisplayMode](properties-core.md)** -asetuksena on **Poistettu käytöstä**.

**FalseFill** – Värintäytön vaihtopainike, kun Poistettu käytöstä on valittuna.

**FalseHoverFill** – Värintäytön vaihtopainike hiiren osoittimen ollessa päällä, kun Poistettu käytöstä on valittuna.

**FalseText** – Teksti, joka näytetään, kun Poistettu käytöstä on valittuna.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**HandleFill** – Vaihtokahvan täyttöväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[HoverBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä pitää hiiren osoitinta kyseisen ohjausobjektin kohdalla.

**[OnChange](properties-core.md)**  – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

**OnCheck** – Miten sovellus reagoi, kun valintaruudun tai vaihtopainikkeen arvo muuttuu arvoon **true**.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**OnUnheck** – Miten sovellus reagoi, kun valintaruudun tai vaihtopainikkeen arvo muuttuu arvoon **false**.

**[PressedBorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri, kun käyttäjä napauttaa tai napsauttaa kyseistä ohjausobjektia.

**RailFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **false**, tai liukusäätimen kahvan oikealla puolella olevan viivan väri.

**RailHoverFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **false**, tai liukusäätimen kahvan oikealla puolella olevan viivan väri silloin, kun osoitinta pidetään valitsinkytkimen tai liukusäätimen kohdalla.

**[Nollaa](properties-core.md)**  – Palautuuko ohjausobjekti oletusarvoonsa.

**ShowLabel** – Näytetäänkö tekstiotsikko ohjausobjektin vaihtopainikkeen vieressä.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**TextPosition** – Onko selite ohjausobjektin vaihtopainikkeen vasemmalla vai oikealla puolella.

**[Työkaluvihje](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun kohdistin on ohjausobjektin kohdalla.

**TrueFill** – Värintäytön vaihtopainike, kun Käytössä on valittuna.

**TrueHoverFill** – Värintäytön vaihtopainike hiiren osoittimen ollessa päällä, kun Käytössä on valittuna.

**TrueText** – Teksti, joka näytetään, kun Käytössä on valittuna.

**ValueFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **true**, tai liukusäätimen kahvan vasemmalla puolella olevan viivan väri.

**ValueHoverFill** – Ohjausobjektin suorakulmion taustaväri, kun valintakytkimen arvo on **true**, tai liukusäätimen kahvan vasemmalla puolella olevan viivan väri, kun osoitinta pidetään ohjausobjektin tai liukusäätimen päällä.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Aiheeseen liittyvät funktiot
[**If**( *Ehto*, *Tulos* )](../functions/function-if.md)

## <a name="example"></a>Esimerkki
1. Lisää vaihtopainike ja anna sille nimeksi **MemberDiscount**.

    Miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää selite ja aseta sen **[Text](properties-core.md)** -ominaisuudeksi tämä kaava:
   <br>**If(MemberDiscount.Value = true, "Price: $75", "Price: $100")**

    Haluatko lisätietoja **[If](../functions/function-if.md)** -funktiosta tai [muista funktioista](../formula-reference.md)?
3. Paina F5-näppäintä ja muuta **MemberDiscount**-arvoa.

    Selitteessä on eri hinta sen mukaan, onko **MemberDiscount** käytössä vai poissa käytöstä.
4. Palaa oletustyötilaan painamalla ESC-näppäintä.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **HandleFill** ja **FalseFill**
* **HandleFill** ja **FalseHoverFill**
* **HandleFill** ja **TrueFill**
* **HandleFill** ja **TrueHoverFill**
* **FalseFill** ja ohjausobjektin ulkopuolinen väri
* **FalseHoverFill** ja ohjausobjektin ulkopuolinen väri
* **TrueFill** ja ohjausobjektin ulkopuolinen väri
* **TrueHoverFill** ja ohjausobjektin ulkopuolinen väri

Tämä tulee [värikontrastin vakiovaatimusten lisäksi](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.
* **FalseText** on oltava käytössä.
* **TrueText** on oltava käytössä.

### <a name="low-vision-support"></a>Tuki heikkonäköisille
* Harkitse **ShowLabel**-ominaisuuden asettamista arvoon **true**, jotta käyttäjät voivat nopeasti määrittää vaihtoarvon.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)** -kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.

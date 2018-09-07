---
title: Luokitus-ohjausobjektin viitetiedot| Microsoft Docs
description: Tietoja Luokitus-ohjausobjektista, mukaan lukien ominaisuudet ja esimerkkejä
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
ms.openlocfilehash: 1979ad63ce9cd5fbe3f3a9a3fa5a56df5e80966e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42830867"
---
# <a name="rating-control-in-powerapps"></a>Luokitus-ohjausobjekti PowerAppsissa
Ohjausobjekti, jolla käyttäjät voivat ilmaista arvon numeron 1 ja määrittämäsi suurimman numeron väliltä.

## <a name="description"></a>Kuvaus
Tämän ohjausobjektin avulla käyttäjä voi esimerkiksi tietyn määrän tähtiä valitsemalla ilmaista, kuinka paljon hän piti jostakin asiasta.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Default](properties-core.md)** – Ohjausobjektin alkuarvo, ennen kuin käyttäjä on muuttanut sitä.

**Max** – Suurin arvo, jonka käyttäjä voi antaa liukusäätimelle tai luokitukselle.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Poistettu käytöstä**).

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[OnChange](properties-core.md)**  – Miten sovellus reagoi, kun käyttäjä muuttaa ohjausobjektin arvoa (esimerkiksi säätämällä liukusäädintä).

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**RatingFill** – Luokitus-ohjausobjektin tähtien väri.

**ReadOnly** – Voiko käyttäjä muuttaa liukusäätimen tai luokituksen ohjausobjektin arvoa.

**[Reset](properties-core.md)** – Palautuuko ohjausobjekti oletusarvoonsa.

**ShowValue** – Näytetäänkö liukusäätimen tai luokituksen arvo, kun käyttäjä tekee muutoksia kyseiseen arvoon tai kun tämä pitää osoitinta ohjausobjektin kohdalla.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Tooltip](properties-core.md)** – Ohjeteksti, joka ilmestyy näkyviin, kun hiiren kohdistin on ohjausobjektin päällä.

**[Näkyvissä](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys.

## <a name="related-functions"></a>Liittyvät toiminnot
[**Average**( *Arvo1*, *Arvo2,* ... )](../functions/function-aggregates.md)

## <a name="example"></a>Esimerkki
1. Lisää **Luokitus**-ohjausobjekti ja anna sille nimeksi **Kvantitatiivinen**.
   
    Etkö tiedä, miten [ohjausobjekti lisätään, nimetään ja määritetään](../add-configure-controls.md)?
2. Lisää **[Tekstisyöte](control-text-input.md)**-ohjausobjekti, anna sen nimeksi **Kvalitatiivinen** ja siirrä se **Luokitus**-ohjausobjektin alapuolelle.
3. Määritä **[Tekstisyöte](control-text-input.md)**-ohjausobjektin **[Default](properties-core.md)**-ominaisuudeksi **""** ja määritä sen **HintText**-ominaisuudeksi tämä kaava:
   <br>**If(Kvantitatiivinen.Value > 3, "Mistä erityisesti pidit", "Missä meillä olisi parantamisen varaa?")**
   
    Haluatko lisätietoja **[If](../functions/function-if.md)**-funktiosta tai [muista funktioista](../formula-reference.md)?
4. Paina F5-näppäintä ja napsauta tai napauta sen jälkeen neljä tai viisi tähteä **Luokitus**-ohjausobjektissa.
   
    **[Tekstisyöte](control-text-input.md)**-ohjausobjektin vihjeteksti muuttuu korkeaa luokitusta vastaavaksi.
5. Napsauta tai napauta vähemmän kuin neljä tähteä kohdassa **Kvantitatiivinen**.
   
    **[Tekstisyöte](control-text-input.md)**-ohjausobjektin vihjeteksti muuttuu alhaista luokitusta vastaavaksi.
6. Palaa oletustyötilaan painamalla ESC-näppäintä.


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **RatingFill** ja **[Fill](properties-color-border.md)**

Tämä tulee [värikontrastin vakiovaatimusten lisäksi](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

    > [!NOTE]
  > Näytönlukuohjelmat käsittelevät **Rating** -ohjausobjektin valintanappeina.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.
* Jos tähtiä on liikaa, harkitse eri ohjausobjektin käyttämistä. Muuten käyttö näppäimistöllä voi olla vaikeaa ja valinnan tekeminen tarkasti kosketusnäytöllä vaikeaa.

    > [!NOTE]
  > **Rating**-kohteessa voidaan käyttää samoja valintanappien näppäimistövuorovaikutuksia.

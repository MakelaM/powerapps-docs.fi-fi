---
title: 'Yhdistelmäruutu-ohjausobjekti: viittaus | Microsoft Docs'
description: Yhdistelmäruutu-ohjausobjektia koskevaa tietoa, kuten ominaisuuksia ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/13/2017
ms.author: fikaradz
ms.openlocfilehash: 30e2b07a95c326b897e5b3386d888f3537db85fd
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015658"
---
# <a name="combo-box-control-in-powerapps"></a>Yhdistelmäruutu-ohjausobjekti PowerAppsissa
Ohjausobjekti, jonka avulla käyttäjät voivat tehdä valintoja annetuista vaihtoehdoista.  Tukee hakua ja useita valintoja.

## <a name="description"></a>Kuvaus
**Yhdistelmäruutu**-ohjausobjektin avulla voit etsiä kohteita, jotka aiot valita.  Haku suoritetaan palvelinpuolella käyttämällä SearchField-ominaisuutta, joten erittäin suuret tietolähteet eivät vaikuta suorituskykyyn.  

Yksittäinen tai monivalintatila määritetään SelectMultiple-ominaisuudella.

Valittavia kohteita etsittäessä voit näyttää kullekin kohteelle yksittäisen tietoarvon, kaksi arvoa tai kuvan ja kaksi arvoa (henkilö) muokkaamalla tietoruudun asettelun asetuksia.

## <a name="people-picker"></a>Henkilöiden valinta
Voit käyttää **yhdistelmäruutua** henkilöiden valintaan valitsemalla **henkilö**-mallin tietoruudun asettelun asetuksista ja määrittämällä toisiinsa liittyvät tieto-ominaisuudet näytettäväksi alla olevan henkilön osalta.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**[Items](properties-core.md)**  – Valintojen tekemisessä käytetyn tiedon lähde.

**DefaultItems** – Alkuperäiset valitut kohteet, ennen kuin käyttäjä on vuorovaikutuksessa ohjausobjektin kanssa.

**SelectedItems** – Luettelo kohteista, jotka on valittu käyttäjän toiminnan perusteella.

**SelectMultiple** – Voiko käyttäjä valita yhden vai useita kohteita.

**IsSearchable** – Voiko käyttäjä etsiä kohteita ennen valitsemista.

**SearchFields** - Sen tietolähteen tietokentät, josta haetaan, kun käyttäjä syöttää tekstiä.  Etsiäksesi useampia kenttiä, määritä ComboBox1.SearchFields = ["MyFirstColumn", "MySecondColumn"]

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Default](properties-core.md)** – Alkuperäinen valinta, ennen kuin käyttäjä on muuttanut sitä yksittäisen valinnan tilassa.

**DisplayFields** – Luettelo kentistä, jotka näytetään jokaisesta haun palauttamasta kohteesta.  Helpoin määrittää Ominaisuudet-välilehden tietoruudun kautta.

**[DisplayMode](properties-core.md)** – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**), vai onko ominaisuus poistettu käytöstä (**Disabled**).

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**InputTextPlaceholder** – Loppukäyttäjälle näytettävä ohjeteksti, jos kohteita ei ole valittu.

**OnChange** – Sovelluksen reagointitapa, kun käyttäjä muuttaa valintaa.

**OnNavigate** – Sovelluksen reagointitapa, kun käyttäjä valitsee kohteen.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="example"></a>Esimerkki
1. Lisää **Yhdistelmäruutu**-ohjausobjekti Ohjausobjektit-valikon Lisää-välilehdeltä.  
2. Valitse Ominaisuusasetukset-välilehdeltä Tiedot.  
3. Valitse tietolähde, asettelu ja siihen liittyvät ominaisuudet alta.
4. Määritä **SelectMultiple**-ominaisuus Lisäasetukset-välilehdeltä.

    Sovellukseesi tulee näkyviin toiminnallinen **Yhdistelmäruutu**.

    Miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **ChevronFill** ja **ChevronBackground**
* **ChevronHoverFill** ja **ChevronHoverBackground**
* **SelectionColor** ja **SelectionFill**
* **SelectionFill** ja **[Fill](properties-color-border.md)**
* **SelectionTagColor** ja **SelectionTagFill**

Tämä tulee [värikontrastin vakiovaatimusten lisäksi](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

    > [!NOTE]
  > Kosketusnäytöissä näytönlukuohjelman käyttäjät voivat siirtyä yhdistelmäruudun sisällössä peräkkäisessä järjestyksessä. Yhdistelmäruutu toimii painikkeena, joka näyttää tai piilottaa sen sisällön, kun se on valittuna.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.

    > [!NOTE]
  > Voit sarkainnäppäimellä siirtyä yhdistelmäruutuun tai siitä pois. Voit nuolinäppäimillä siirtyä yhdistelmäruudun sisällössä. Voit Escape-näppäimellä sulkea avattavan valikon, kun se on avattuna.

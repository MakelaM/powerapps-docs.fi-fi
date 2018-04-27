---
title: 'Yhdistelmäruutuohjausobjekti: viittaus | Microsoft Docs'
description: Yhdistelmäruutuohjausobjekteja koskevaa tietoa, kuten ominaisuuksia ja esimerkkejä
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
ms.date: 09/13/2017
ms.author: fikaradz
ms.openlocfilehash: 4d298e24ea967cbf5cb47638d4296f6efbd758c7
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="combo-box-control-in-powerapps"></a>Yhdistelmäruutuohjausobjekti PowerAppsissa
Ohjausobjekti, jonka avulla käyttäjät voivat tehdä valintoja annetuista vaihtoehdoista.  Tukee hakua ja useita valintoja.

## <a name="description"></a>Kuvaus
**Yhdistelmäruutu**ohjausobjektin avulla voit etsiä kohteita, jotka aiot valita.  Haku suoritetaan palvelinpuolella käyttämällä SearchField-ominaisuutta, joten erittäin suuret tietolähteet eivät vaikuta suorituskykyyn.  

Yksittäinen tai monivalintatila määritetään SelectMultiple-ominaisuudella.

Valittavia kohteita etsittäessä voit näyttää kullekin kohteelle yksittäisen tietoarvon, kaksi arvoa tai kuvan ja kaksi arvoa (henkilö) muokkaamalla tietoruudun asettelun asetuksia.

## <a name="people-picker"></a>Henkilöiden valinta
Voit käyttää **yhdistelmäruutua** henkilöiden valintaan valitsemalla **henkilö**mallin tietoruudun asettelun asetuksista ja määrittämällä toisiinsa liittyvät tieto-ominaisuudet näytettäväksi alla olevan henkilön osalta.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**[Items](properties-core.md)**  – Valintojen tekemisessä käytetyn tiedon lähde.

**DefaultItems** – Alkuperäiset valitut kohteet, ennen kuin käyttäjä on vuorovaikutuksessa ohjausobjektin kanssa.

**SelectedItems** – Luettelo kohteista, jotka on valittu käyttäjän toiminnan perusteella.

**SelectMultiple** – Voiko käyttäjä valita yhden vai useita kohteita.

**IsSearchable** – Voiko käyttäjä etsiä kohteita ennen valitsemista.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva**vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Default](properties-core.md)** – Alkuperäinen valinta, ennen kuin käyttäjä on muuttanut sitä yksittäisen valinnan tilassa.

**DisplayFields** – Luettelo kentistä, jotka näytetään jokaisesta haun palauttamasta kohteesta.  Helpoin määrittää Ominaisuudet-välilehden tietoruudun kautta.

**[DisplayMode](properties-core.md)**  – Määrittää ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Muokkaa**) tai vain tarkastella tietoja (**Näytä**) vai onko ominaisuus kokonaan poissa käytöstä (**Ei käytössä**).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**InputTextPlaceholder** – Loppukäyttäjälle näytettävä ohjeteksti, jos kohteita ei ole valittu.

**OnChange** – Sovelluksen reagointitapa, kun käyttäjä muuttaa valintaa.

**OnNavigate** – Sovelluksen reagointitapa, kun käyttäjä valitsee kohteen.

**[OnSelect](properties-core.md)** – Sovelluksen reagointitapa, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[Width](properties-size-location.md)** – Leveys eli ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (näytön, jos pääsäilöä ei ole).

## <a name="example"></a>Esimerkki
1. Lisää **yhdistelmäruutuohjausobjekti** Ohjausobjektit-valikon Lisää-välilehdeltä.  
2. Valitse Ominaisuusasetukset-välilehdeltä Tiedot.  
3. Valitse tietolähde, asettelu ja siihen liittyvät ominaisuudet alta.
4. Määritä **SelectMultiple**-ominaisuus Lisäasetukset-välilehdeltä.

    Sovellukseesi tulee näkyviin toiminnallinen **yhdistelmäruutu**.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

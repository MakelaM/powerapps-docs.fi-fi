---
title: 'Power BI -ruudun ohjausobjekti: viitetietoja | Microsoft Docs'
description: Tietoja Power BI -ruudun ohjausobjektista, kuten ominaisuudet ja esimerkkejä
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 07/07/2016
ms.author: fikaradz
ms.openlocfilehash: e7bc2e7e0aafa4d933c47bcf47300dc243c38523
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31827139"
---
# <a name="power-bi-tile-control-in-powerapps"></a>Power BI -ruudun ohjausobjekti PowerAppsissa
Ohjausobjekti, joka näyttää [Power BI](https://powerbi.microsoft.com) -ruudun sovelluksessa.

## <a name="description"></a>Kuvaus
Hyödynnä olemassa olevaa tietojen analysointia ja raportointia näyttämällä **[Power BI -ruutuja](https://docs.microsoft.com/power-bi/service-dashboard-tiles)** sovelluksissasi.  Valitse näytettävä ruutu asettamalla sen **Työtila**-, **Koontinäyttö**- ja **Ruutu**-ominaisuudet asetuspaneelin **Tiedot**-välilehdellä.

## <a name="sharing-and-security"></a>Jakaminen ja suojaus
Kun PowerApp jaetaan, sitä voivat käyttää kaikki käyttäjät, joilla on sovelluksen käyttöoikeus.  Jotta Power BI -sisältö näkyy näille käyttäjille, koontinäyttö, josta ruutu on peräisin, tulee [jakaa](https://docs.microsoft.com/power-bi/service-how-to-collaborate-distribute-dashboards-reports) käyttäjän kanssa Power BI:ssä.  Näin varmistetaan, että Power BI -jakamisoikeuksia kunnioitetaan, kun Power BI -sisältöä käytetään sovelluksessa.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**Työtila** – Power BI -työtila, josta ruutu on peräisin.

**Koontinäyttö** – Power BI -koontinäyttö, josta ruutu on peräisin.

**Ruutu** – Näytettävän Power BI -ruudun nimi.

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia. Sovellus vie käyttäjän oletuksena ruutuun liittyvään Power BI -raporttiin.

**[Visible](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="example"></a>Esimerkki
1. Lisää **Power BI -ruudun** ohjausobjekti **Ohjausobjektit**-valikon **Lisää**-välilehdeltä.  
2. Valitse **Tiedot**-välilehden asetuspaneelissa **Työtila**-asetukseksi "Oma työtila".  Valitse koontinäyttö koontinäyttöluettelosta ja ruutu ruutuluettelosta.
   
    Ohjausobjekti muodostaa Power BI -ruudun.
   
    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?
   
   Eikö sinulla ole Power BI:tä? [Rekisteröidy](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi).


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
**Power BI-ruutu** on vain säilö Power BI -sisällölle. Opi luomaan helppokäyttöistä sisältöä näiden [Power BI -helppokäyttötoimintojen vinkkien](https://docs.microsoft.com/power-bi/desktop-accessibility) avulla.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* Harkitse otsikon lisäämistä **[selitteen](control-text-box.md)** avulla, jos Power BI -sisällössä ei ole otsikkoa. Otsikko voidaan sijoittaa välittömästi ennen **Power BI -ruutua**.

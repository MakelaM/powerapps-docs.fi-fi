---
title: 'Container-ohjaus objekti: viittaus | Microsoft Docs'
description: Tietoja, mukaan lukien ominaisuudet ja esimerkkejä, säiliön ohjaus objektista
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 9/20/2019
ms.author: emcoope
ms.reviewer: tapanm-msft
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 758d986660137d4e513919911589cbbc0dc304a2
ms.sourcegitcommit: 7016ff837eff2cb0985fc71edab95cbf99335677
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/20/2019
ms.locfileid: "71160162"
---
# <a name="container-control-in-powerapps-experimental"></a>Container-ohjaus objekti Powerappsissa (kokeellinen)
Antaa mahdollisuuden luoda hierarkiaa.

> [!IMPORTANT]
> Tämä on kokeellinen ominaisuus. Kokeellisia ominaisuuksia voidaan muuttaa tai ne voivat kadota kokonaan milloin tahansa.
> Lue lisä tietoja [powerappsin kokeellinen-ja Preview-ominaisuuksista](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/working-with-experimental-preview).

## <a name="description"></a>Kuvaus
 Säilöllä voi olla ohjaus objekti joukko, ja sillä on omat ominaisuutensa. 

Voit aloittaa lisäämällä tyhjän säiliön ja mukauttamalla sen sitten lisäämällä siihen ohjaus objektin, muuttamalla sen kokoa, siirtämällä sitä, piilottamalla sen ja tekemällä muita muutoksia. Voit myös aloittaa useilla ohjaus objekteilla, valita ne ja lisätä ne säilöön puunäkymän pikavalikon kautta tai napsauttamalla hiiren kakkos painikkeella piirto alustaa. 

## <a name="properties"></a>Ominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys. 

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys. 


## <a name="known-limitations"></a>Tunnetut rajoitukset

Säiliöt eivät toimi pohjaan tai lomakkeisiin. 

## <a name="frequently-asked-questions"></a>Usein kysytyt kysymykset

**Mitä eroa on Säilöllä ja ryhmällä?**
Sisällöntuottamisryhmä on kevyt käsite, jota käytetään ohjaus objektien ympärille siirtymiseen ja samankaltaisten ohjaus objektien samankaltaisten ominaisuuksien muokkaamiseen ryhmässä. Sisällöntuottamisryhmä ei vaikuta sovelluksen rakenteeseen. 

Koelaitteessa aiemmin lähetetty Container-ohjaus objekti, joka on korvattu luonti ryhmälle uudeksi nimeksi laajennetuksi ryhmäksi. Se nimettiin uudelleen Container-ohjaus objektiin, koska sekä kevyessä luonti ryhmässä että Structured Container-ohjaus objektissa on lisä ominaisuuksia. 


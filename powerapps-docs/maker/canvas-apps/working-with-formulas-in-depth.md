---
title: Toimintakaavojen ymmärtäminen pohjaan perustuvissa sovelluksissa | Microsoft Docs
description: Viitetietoja toimintakaavoista, jotka muuttavat pohjaan perustuvan sovelluksen tilan PowerAppsissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/10/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d48559ee3a54cbb723621a0e36f09cb4a1d0fe3b
ms.sourcegitcommit: 825daacc9a812637815afc1ce6fad28f0cebd479
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/04/2019
ms.locfileid: "57803431"
---
# <a name="understand-behavior-formulas-for-canvas-apps-in-powerapps"></a>Toimintakaavojen ymmärtäminen PowerAppsin pohjaan perustuvissa sovelluksissa

Useimmat kaavat laskevat arvon.  Kuten Excel-laskentataulukossakin, uudelleenlaskenta tapahtuu automaattisesti, kun arvot muuttuvat.  Voit esimerkiksi haluta näyttää arvon **[selite](controls/control-text-box.md)**-ohjausobjektissa punaisena, jos arvo on pienempi kuin nolla ja muussa tapauksessa mustana. Voit siis määrittää tämän ohjausobjektin **[Color](controls/properties-color-border.md)**-ominaisuudeksi seuraavan kaavan:

**If( Value(TextBox1.Text) >= 0, Color.Black, Color.Red )**

Mitä tässä yhteydessä tarkoittaa se, kun käyttäjä valitsee **[painike](controls/control-button.md)**-ohjausobjektin?  Arvo ei ole muuttunut, joten mitään uutta laskettavaa ei ole. Excelissä ei ole mitään **[painike](controls/control-button.md)**-ohjausobjektia vastaavaa.  

Valitsemalla **[painike](controls/control-button.md)**-ohjausobjektin käyttäjä käynnistää toimintojen tai tapahtumien sarjan, joka muuttaa sovelluksen tilaa:

* Vaihda esiin tulevaa näyttöä: **[Takaisin](functions/function-navigate.md)**  ja **[Navigate](functions/function-navigate.md)** funktioita.
* Ohjausobjekti [signaalin](functions/signals.md): **[Ota käyttöön](functions/function-enable-disable.md)**  ja **[käytöstä](functions/function-enable-disable.md)** funktioita.
* Päivitä, Päivitä tai poista kohteita [tietolähteen](working-with-data-sources.md): **[Päivitä](functions/function-refresh.md)**,  **[päivitys](functions/function-update-updateif.md)**,  **[UpdateIf](functions/function-update-updateif.md)**, **[korjaustiedosto](functions/function-patch.md)**,  **[Poistaa](functions/function-remove-removeif.md)**, **[RemoveIf](functions/function-remove-removeif.md)** funktioita.
* Päivitys [kontekstimuuttujan](working-with-variables.md#use-a-context-variable):  **[UpdateContext](functions/function-updatecontext.md)**  funktio.
* Luo, Päivitä tai poista kohteita [kokoelma](working-with-data-sources.md#collections):  **[Kerää](functions/function-clear-collect-clearcollect.md)**,  **[Tyhjennä](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)** funktioita.

Koska nämä funktiot muuttavat sovelluksen tilaa, niitä ei voi automaattisesti laskea uudelleen. Voit käyttää niitä kaavoissa **[OnSelect](controls/properties-core.md)**-, **[OnVisible](controls/control-screen.md)**- ja **[OnHidden](controls/control-screen.md)**-ominaisuuksille sekä muille **On...**-ominaisuuksille, joita kutsutaan toimintakaavoiksi.

### <a name="more-than-one-action"></a>Useampi kuin yksi toiminto
Luo suoritettavien toimintojen luettelo käyttämällä puolipisteitä. Esimerkiksi, haluat ehkä päivittää kontekstimuuttujan ja palata sitten edelliseen näyttöön:

* **UpdateContext ({x: 1 } ); Back()**

Toiminnot suoritetaan siinä järjestyksessä, jossa ne näkyvät kaavassa.  Seuraava funktio ei käynnisty, ennen kuin nykyinen toiminto on suoritettu. Jos ilmenee virhe, seuraavat funktiot eivät ehkä käynnisty.


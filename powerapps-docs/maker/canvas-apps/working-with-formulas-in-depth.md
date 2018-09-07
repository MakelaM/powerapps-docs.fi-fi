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
ms.openlocfilehash: f7aed7812890482bb781e2d5ff7eac8c996b8837
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42850413"
---
# <a name="understand-behavior-formulas-for-canvas-apps-in-powerapps"></a>Toimintakaavojen ymmärtäminen PowerAppsin pohjaan perustuvissa sovelluksissa

Useimmat kaavat laskevat arvon.  Kuten Excel-laskentataulukossakin, uudelleenlaskenta tapahtuu automaattisesti, kun arvot muuttuvat.  Voit esimerkiksi haluta näyttää arvon **[selite](controls/control-text-box.md)**-ohjausobjektissa punaisena, jos arvo on pienempi kuin nolla ja muussa tapauksessa mustana. Voit siis määrittää tämän ohjausobjektin **[Color](controls/properties-color-border.md)**-ominaisuudeksi seuraavan kaavan:

**If( Value(TextBox1.Text) >= 0, Color.Black, Color.Red )**

Mitä tässä yhteydessä tarkoittaa se, kun käyttäjä valitsee **[painike](controls/control-button.md)**-ohjausobjektin?  Arvo ei ole muuttunut, joten mitään uutta laskettavaa ei ole. Excelissä ei ole mitään **[painike](controls/control-button.md)**-ohjausobjektia vastaavaa.  

Valitsemalla **[painike](controls/control-button.md)**-ohjausobjektin käyttäjä käynnistää toimintojen tai tapahtumien sarjan, joka muuttaa sovelluksen tilaa:

* Vaihda esiin tulevaa näyttöä: **[Back](functions/function-navigate.md)**- ja **[Navigate](functions/function-navigate.md)**-funktiot.
* Hallitse [signaalia](functions/signals.md): **[Enable](functions/function-enable-disable.md)**- ja **[Disable](functions/function-enable-disable.md)** funktiot.
* Päivitä, korvaa tai poista [tietolähteen](working-with-data-sources.md) kohteita: **[Refresh](functions/function-refresh.md)**-, **[Update](functions/function-update-updateif.md)**-, **[UpdateIf](functions/function-update-updateif.md)**-, **[Patch](functions/function-patch.md)**-, **[Remove](functions/function-remove-removeif.md)**- ja **[RemoveIf](functions/function-remove-removeif.md)**-funktiot.
* Päivitä [kontekstimuuttuja](working-with-variables.md#create-a-context-variable): **[UpdateContext](functions/function-updatecontext.md)**-funktio.
* Luo, päivitä tai poista [kokoelman](working-with-data-sources.md#collections) kohteita: **[Collect](functions/function-clear-collect-clearcollect.md)**-, **[Clear](functions/function-clear-collect-clearcollect.md)**- ja **[ClearCollect](functions/function-clear-collect-clearcollect.md)**-funktiot.

Koska nämä funktiot muuttavat sovelluksen tilaa, niitä ei voi automaattisesti laskea uudelleen. Voit käyttää niitä kaavoissa **[OnSelect](controls/properties-core.md)**-, **[OnVisible](controls/control-screen.md)**- ja **[OnHidden](controls/control-screen.md)**-ominaisuuksille sekä muille **On...**-ominaisuuksille, joita kutsutaan toimintakaavoiksi.

### <a name="more-than-one-action"></a>Useampi kuin yksi toiminto
Luo suoritettavien toimintojen luettelo käyttämällä puolipisteitä. Esimerkiksi, haluat ehkä päivittää kontekstimuuttujan ja palata sitten edelliseen näyttöön:

* **UpdateContext( { x: 1 } ); Back()**

Toiminnot suoritetaan siinä järjestyksessä, jossa ne näkyvät kaavassa.  Seuraava funktio ei käynnisty, ennen kuin nykyinen toiminto on suoritettu. Jos ilmenee virhe, seuraavat funktiot eivät ehkä käynnisty.


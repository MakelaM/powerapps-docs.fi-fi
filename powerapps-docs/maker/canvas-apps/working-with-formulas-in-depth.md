---
title: Toimintakaavojen ymmärtäminen pohjaan perustuvissa sovelluksissa | Microsoft Docs
description: Viitetietoja toimintakaavoista, jotka muuttavat pohjaan perustuvan sovelluksen tilan PowerAppsissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/10/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 546c19dd0bc767758fcf854e383be0f075717525
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71988016"
---
# <a name="understand-behavior-formulas-for-canvas-apps-in-powerapps"></a>Toimintakaavojen ymmärtäminen PowerAppsin pohjaan perustuvissa sovelluksissa

Useimmat kaavat laskevat arvon.  Kuten Excel-laskentataulukossakin, uudelleenlaskenta tapahtuu automaattisesti, kun arvot muuttuvat.  Voit esimerkiksi haluta näyttää arvon **[selite](controls/control-text-box.md)** -ohjausobjektissa punaisena, jos arvo on pienempi kuin nolla ja muussa tapauksessa mustana. Voit siis määrittää tämän ohjausobjektin **[Color](controls/properties-color-border.md)** -ominaisuudeksi seuraavan kaavan:

**If( Value(TextBox1.Text) >= 0, Color.Black, Color.Red )**

Mitä tässä yhteydessä tarkoittaa se, kun käyttäjä valitsee **[painike](controls/control-button.md)** -ohjausobjektin?  Arvo ei ole muuttunut, joten mitään uutta laskettavaa ei ole. Excelissä ei ole mitään **[painike](controls/control-button.md)** -ohjausobjektia vastaavaa.  

Valitsemalla **[painike](controls/control-button.md)** -ohjausobjektin käyttäjä käynnistää toimintojen tai tapahtumien sarjan, joka muuttaa sovelluksen tilaa:

* Muuta näytössä näkyvää näyttöä: **[Back](functions/function-navigate.md)** -ja **[Navigate](functions/function-navigate.md)** -funktiot.
* Hallitse [signaalia](functions/signals.md): **[Ota Funktiot käyttöön](functions/function-enable-disable.md)** ja **[Poista ne käytöstä](functions/function-enable-disable.md)** .
* [Tieto lähteen](working-with-data-sources.md)kohteiden päivittäminen, päivittäminen tai poistaminen: **[Päivitä](functions/function-refresh.md)** , **[Päivitä](functions/function-update-updateif.md)** , **[updateif](functions/function-update-updateif.md)** , **[patch](functions/function-patch.md)** , **[Remove](functions/function-remove-removeif.md)** , **[removeif](functions/function-remove-removeif.md)** funktiot.
* Päivitä [kontekstin muuttuja](working-with-variables.md#use-a-context-variable):  **[Updatecontext](functions/function-updatecontext.md)** -funktiolla.
* Luo, Päivitä tai poista [kokoelman](working-with-data-sources.md#collections)kohteita:  **[Collect](functions/function-clear-collect-clearcollect.md)** -, **[Clear](functions/function-clear-collect-clearcollect.md)** -ja **[clearcollect](functions/function-clear-collect-clearcollect.md)** -funktiot.

Koska nämä funktiot muuttavat sovelluksen tilaa, niitä ei voi automaattisesti laskea uudelleen. Voit käyttää niitä kaavoissa **[OnSelect](controls/properties-core.md)** -, **[OnVisible](controls/control-screen.md)** - ja **[OnHidden](controls/control-screen.md)** -ominaisuuksille sekä muille **On...** -ominaisuuksille, joita kutsutaan toimintakaavoiksi.

### <a name="more-than-one-action"></a>Useampi kuin yksi toiminto
Luo suoritettavien toimintojen luettelo käyttämällä puolipisteitä. Esimerkiksi, haluat ehkä päivittää kontekstimuuttujan ja palata sitten edelliseen näyttöön:

* **UpdateContext ({x: 1}); Edellinen ()**

Toiminnot suoritetaan siinä järjestyksessä, jossa ne näkyvät kaavassa.  Seuraava funktio ei käynnisty, ennen kuin nykyinen toiminto on suoritettu. Jos ilmenee virhe, seuraavat funktiot eivät ehkä käynnisty.


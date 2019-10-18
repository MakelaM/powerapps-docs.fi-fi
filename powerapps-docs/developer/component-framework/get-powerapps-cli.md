---
title: Hanki työkaluja PowerApps Component Frameworkin käyttöön | Microsoft Docs
description: Hanki Microsoft PowerApps CLI, jotta voit luoda, korjata ja ottaa käyttöön koodi komponentteja PowerApps Component Frameworkin avulla.
keywords: PowerApps Component Framework, koodi komponentit, komponentti kehys
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f393f227-7a88-4f25-9036-780b3bf14070
ms.openlocfilehash: 496b7d443775da075dd8da52ac4b0a754121bf28
ms.sourcegitcommit: 4c35aedde46380d5438687ae6f61a3b0cc7e7e2f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/05/2019
ms.locfileid: "72340019"
---
# <a name="get-tooling-for-powerapps-component-framework"></a>Hanki työkaluja PowerApps Component Frameworkin käyttöön

**Microsoft POWERAPPS CLI** (komento rivi liittymä) avulla voit luoda, tehdä virheen korjauksen ja ottaa käyttöön koodi komponentteja powerapps Component Frameworkin avulla. Powerappsin avulla kehittäjät voivat luoda koodi komponentteja nopeasti. Jatkossa se laajennetaan sisältämään tukea lisä kehitykselle ja sovelluksen elin kaaren hallinnan (ALM) kokemuksille. 

## <a name="what-is-microsoft-powerapps-cli"></a>Mikä on Microsoft PowerApps CLI 

Microsoft PowerApps CLI on yksinkertainen, yhden luukun kehittäjien komento rivi liittymä, jolla kehittäjät ja sovelluksen tekijät voivat luoda koodi komponentteja. PowerApps CLI-työkalut on ensimmäinen askel kohti kattavaa ALM-tarinaa, jossa yritys kehittäjät ja riippumattomat yritykset voivat luoda, rakentaa, korjata ja julkaista laajennuksia ja mukautuksia nopeasti ja tehokkaasti.  

## <a name="install-microsoft-powerapps-cli"></a>Asenna Microsoft PowerApps CLI

Jos haluat saada Microsoft PowerApps CLI, toimi seuraavasti:

1. Asenna [NPM](https://www.npmjs.com/get-npm) (Node. js) tai [Node. js](https://nodejs.org/en/) (mukana NPM). Suosittelemme LTS (pitkän aika välin tukea) versio 10.15.3 LTS, koska se näyttää olevan vakain.

1. Asenna [.NET Framework 4.6.2 Developer Pack](https://dotnet.microsoft.com/download/dotnet-framework/net462). 

1. Jos sinulla ei vielä ole Visual Studio 2017 tai uudempaa versiota, noudata jotakin seuraavista vaihto ehdoista:
   - Vaihto ehto 1: Asenna [Visual Studio 2017](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2017) tai uudempi versio.
   - Vaihto ehto 2: Asenna [.net ydintä 2,2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) ja asenna [Visual Studio Code](https://code.visualstudio.com/Download).

1. Asenna [Microsoft POWERAPPS CLI](https://aka.ms/PowerAppsCLI).
1. Jos haluat hyödyntää kaikkia uusimpia ominaisuuksia, Päivitä PowerApps CLI-työkalut uusimpaan versioon käyttämällä tätä komentoa:

    ```CLI
    pac install latest
    ```

> [!NOTE]
> - Jotta voit ottaa koodi osan käyttöön Powerappsin avulla, sinulla on oltava Common Data Service-ympäristö järjestelmänvalvojan tai järjestelmän mukauttajan oikeuksilla.
> - Tällä hetkellä PowerApps CLI on tuettu vain Windows 10: ssä.

## <a name="microsoft-powerapps-cli-telemetry"></a>Microsoft PowerApps CLI-telemetria

Ominaisuus ryhmä koostaa telemetria ja ymmärtää, mitä ominaisuuksia tai ominaisuuksia kehittäjät käyttävät useimmiten Powerappsin CLI-työkalussa. Kooste tietojen avulla voimme tarjota asiakkaille parhaan käyttö kokemuksen keskittymällä olennaiseen.

> [!NOTE]
> Jos haluat poistaa telemetria-kokoelman käytöstä, suorita komento `pac telemetry disable`. Jos haluat ottaa telemetria takaisin käyttöön, käytä komentoa `pac telemetry enable`.


## <a name="uninstall-microsoft-powerapps-cli"></a>Poista Microsoft PowerApps CLI

Jos haluat poistaa PowerApps CLI-työkalujen asennuksen, suorita MSI [tästä](https://aka.ms/PowerAppsCLI). 

Jos olet yksityinen Esikatseluosallistuja ja sinulla on aiempi versio CLI-versiosta, toimi seuraavasti:

1. Jos haluat selvittää, mihin PowerApps CLI on asennettu, Avaa komento rivi ja kirjoita `where pac`.
1. Poista PowerAppsCLI-kansio.
1. Avaa ympäristö muuttujat-työkalu suorittamalla komento `rundll32 sysdm.cpl,EditEnvironmentVariables` komento riviltä.
1. Kaksoisnapsauta `Path` `User variable for...`-osassa.
1. Valitse rivi, joka sisältää PowerAppsCLI-polun, ja valitse oikealla puolella oleva **Poista** -painike.
1. Valitse **OK** kahdesti.

### <a name="see-also"></a>Katso myös

[Toteuta komponentit käyttäen TypeScript-kohdetta](implementing-controls-using-typescript.md)<br/>

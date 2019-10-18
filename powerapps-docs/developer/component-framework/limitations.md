---
title: PowerApps Component Frameworkin rajoitukset | MicrosoftDocs
description: Rajoitukset PowerApps Component Frameworkin avulla
author: nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: index-page
ms.assetid: 18e88d702-3349-4022-a7d8-a9adf52cd34f
ms.author: nabuthuk
ms.openlocfilehash: aabcf4518e71648797c795a006c2d842f3e5ff01
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346735"
---
# <a name="limitations"></a>Rajoitukset 

PowerApps Component Frameworkin julkaisemisen myötä voit nyt luoda omia koodi komponentteja, jotka paran tavat mallipohjaisten sovellusten ja pohjaan perustuvien sovellusten käyttö kokemusta. Vaikka voit luoda omia komponenteille, jotkin rajoitukset estävät kehittäjiä toteuttamasta joitakin koodi komponenttien ominaisuuksia. Alla on joitakin rajoituksia:

1. Vain komponenttien *kenttä* tyyppiä tuetaan kokeellinen esikatselu pohjaan perustuvia sovelluksia varten, ei tieto *joukon* tyyppi komponentteja. 
2. Common Data Service riippuvaiset ohjelmointi raja pinnat, mukaan lukien WebAPI yhdessä muutamien muiden ohjelmointi raja pintojen kanssa, eivät ole käytettävissä tälle kokeelliselle esikatseluun. Jos kyseessä on kokeellinen ohjelmointi raja pinnan käytettävyysversio, tutustu [Powerapps Component Framework-ohjelmointi raja pinnan viite kehykseen](reference/index.md).
3. Koodi komponenttien tulee niputtaa kaikki koodi, mukaan lukien ulkoinen Kirjasto sisältö ensisijaiseen koodi nipuksi. Esimerkki siitä, miten PowerApps-komento rivi liittymä voi auttaa ulkoisen kirjaston sisällön niputtamiseen komponenttikohtaiseksi nipuksi, on kohdassa [kulmikas läppä komponentti](sample-controls/angular-flip-control.md) esimerkki.

   > [!NOTE]
   > Komponentti luettelon Kirjasto solmuja käyttävien Jaettujen kirjastojen tukea ei tueta vielä. Tarkastelemme tätä ja lisäämme tämän ominaisuuden tulevaan julkaisuun.
4. Useiden osien määrittämistä yksittäisessä luettelo tiedostossa ei tueta vielä.
5. Prosessien ja toimintojen kutsumista ei tueta vielä. Voit kutsua valinta ikkunoita vain käyttämällä [Navigation](reference/navigation.md) -menetelmää.
6. Yhden komponentin kutsumista toisesta koodi osasta ei tueta vielä.
7. Tällä hetkellä fontti resurssia (. TFF) ei tueta vielä.

## <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](overview.md)

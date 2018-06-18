---
title: Rand-funktio | Microsoft Docs
description: PowerAppsin Rand-funktion viitetiedot, mukaan lukien syntaksi
author: gregli-msft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 06/09/2018
ms.author: gregli
ms.openlocfilehash: 3bf29a3df235d669de2f2862f11b19f428378123
ms.sourcegitcommit: 6bfb002180148a3f22a4d1d8d750fc442489ebe4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/11/2018
ms.locfileid: "35291762"
---
# <a name="rand-function-in-powerapps"></a>PowerAppsin Rand-funktio
Palauttaa pseudosatunnaisluvun.

## <a name="description"></a>Kuvaus
**Rand**-funktio palauttaa pseudosatunnaisluvun, joka on suurempi tai yhtä suuri kuin 0 mutta pienempi kuin 1.

## <a name="volatile-functions"></a>Muuttuvat funktiot
**Rand** on muuttuva funktio.  Aina, kun funktiota arvioidaan, se palauttaa eri arvon.  

Kun muuttuvaa funktiota käytetään tietotyönkulun kaavassa, muuttuva funktio palauttaa eri arvon vain arvioitaessa uudelleen kaavaa, jossa se esiintyy.  Jos mitään muuta ei muuteta kaavassa, sillä on sama arvo koko sovelluksesi suorittamisen ajan.

Esimerkiksi selitteen ohjausobjekti, jossa **Label1.Text = Now()**, ei muutu, kun sovelluksesi on aktiivinen.  Uusi arvo luodaan vain sulkemalla sovellus ja avaamalla se uudelleen.

Funktio arvioidaan uudelleen, jos se on osa kaavaa, jossa jotakin muuta kohtaa on muutettu.  Jos lisäämme esimerkkiimme liukusäätimen ohjausobjektin, jossa **Label1.Text = Slider1.Value + Rand()** uusi satunnaisluku luodaan aina, kun liukusäätimen ohjausobjektin arvo muuttuu ja selitteen tekstin ominaisuutta arvioidaan uudelleen.  Katso esimerkki alta.

Kun sitä käytetään [käytöskaavassa](../working-with-formulas-in-depth.md), **Rand**-funktiota arvioidaan uudelleen aina arvioitaessa käytöskaavaa.  Katso esimerkki alta.

## <a name="syntax"></a>Syntaksi
**Rand**()

## <a name="examples"></a>Esimerkkejä

#### <a name="display-a-different-random-number-as-user-input-changes"></a>Eri satunnaisluvun näyttäminen käyttäjäsyötteen muuttuessa
1. Lisää **[Liukusäädin](../controls/control-slider.md)**-ohjausobjekti ja nimeä se uudelleen **Slider1**, jos sillä on eri nimi.

1. Lisää **[Selite](../controls/control-text-box.md)**-ohjausobjekti ja määritä sen **Text**-ominaisuus tähän kaavaan:

    **Slider1.Value + Rand()**

    Selite näyttää **50** (liukusäätimen oletusarvo) ja satunnaisdesimaalin:

    ![Näyttö, joka näyttää selitteen ohjausobjektin ja 50.741](media/function-rand/rand-slider-1.png)

1. Liukusäätimen arvo muuttuu, kun pidät alhaalla Alt-näppäintä.

    Aina kun muutat liukusäätimen arvoa, selitteen desimaaliosa näyttää eri satunnaisluvun:

    ![Neljä näyttöä, jotka näyttävät selitteen ohjausobjektin ja neljä eri satunnaista desimaaliarvoa kullekin neljälle erilaiselle liukusäätimen asetukselle 70.899, 84.667, 90.134, 99.690](media/function-rand/rand-slider-results.png)

#### <a name="create-a-table-of-random-numbers"></a>Satunnaislukujen taulukon luominen
1. Lisää **[painike](../controls/control-button.md)** ohjausobjekti ja määritä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:

    **ClearCollect( RandomNumbers, ForAll( [ 1, 2, 3, 4, 5 ], Rand() ))**

    Tämä kaava luo yksisarakkeisen taulukon, joka toistetaan viisi kertaa, ja tuloksesi saadaan viisi satunnaislukua.

1. Lisää **[tietotaulukko](../controls/control-data-table.md)**, määritä sen **Items**-ominaisuudeksi **RandomNumbers** ja näytä **Arvo**-kenttä.

    ![Näyttö, jossa näytetään tietotaulukko, jossa on viisi erilaista desimaaliarvoa 0.857, 0.105, 0.979, 0.167, 0.814](media/function-rand/set-show-data.png)

1. Kun pidät alhaalla Alt-näppäintä, valitse painike napsauttamalla tai napauttamalla sitä.

    Tietotaulukossa on viisi satunnaista desimaalilukua:

    ![Näyttö, jossa näytetään tietotaulukko, jossa on viisi erilaista desimaaliarvoa 0.857, 0.105, 0.979, 0.167, 0.814](media/function-rand/rand-collection-1.png)

1. Valitse painike uudelleen, jos haluat näyttää eri satunnaislukujen luettelon:

    ![Näyttö, jossa näytetään tietotaulukko, jossa on viisi erilaista desimaaliarvojoukkoa 0.414, 0.128, 0.860, 0.303, 0.568](media/function-rand/rand-collection-2.png)

Voit luoda yksittäisen satunnaisluvun taulukon sijasta käyttämällä kaavaa **Set( RandomNumber, Rand() )**.

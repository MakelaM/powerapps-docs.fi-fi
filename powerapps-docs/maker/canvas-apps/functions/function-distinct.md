---
title: Distinct-funktio | Microsoft Docs
description: PowerAppsin Distinct-funktion viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 09/14/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7d9ae4df7a4ad11a49b2a25ae78330d0cd807c9b
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985239"
ms.PowerAppsDecimalTransform: true
---
# <a name="distinct-function-in-powerapps"></a>PowerAppsin Distinct-funktio
Tekee [taulukon](../working-with-tables.md#records) [tietueista](../working-with-tables.md) yhteenvedon ja poistaa kaksoiskappaleet.

## <a name="description"></a>Kuvaus
**DISTINCT** -funktio laskee taulukon kunkin tietueen kaavan ja palauttaa yksisarakkeisen taulukon tuloksista, joiden arvojen kaksoiskappaleet on poistettu.  Sarakkeen nimi on **tulos**.  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

[!INCLUDE [delegation-no-one](../../../includes/delegation-no-one.md)]

## <a name="syntax"></a>Syntaksi
**Distinct**( *Table*; *Formula* )

* *Table* – Pakollinen.  Taulukko, jolle kaava lasketaan.
* *Formula* – Pakollinen.  Kaava, jolla lasketaan arvot kullekin tietueelle.

## <a name="example"></a>Esimerkki

1. Lisää [**painike**](../controls/control-button.md) -ohjaus objekti ja määritä sen **onselect** -ominaisuudeksi Tämä kaava.

    ```powerapps-comma
    ClearCollect( CityPopulations;
        { City: "London";    Country: "United Kingdom"; Population: 8615000 };
        { City: "Berlin";    Country: "Germany";        Population: 3562000 };
        { City: "Madrid";    Country: "Spain";          Population: 3165000 };
        { City: "Hamburg";   Country: "Germany";        Population: 1760000 };
        { City: "Barcelona"; Country: "Spain";          Population: 1602000 };
        { City: "Munich";    Country: "Germany";        Population: 1494000 }
    );;
    ```

1. Valitse painike pitäen Alt-näppäintä painettuna.

    Kaava on evaluatd ja **Citypopulaatio** -kokoelma luodaan, jonka voit näyttää valitsemalla kaava riviltä **kaupunki populaatiot** :

    > [!div class="mx-imgBorder"]
    > ![Citypopulaatio-kokoelma näytetään tulos näkymässä @ no__t-1

1. Lisää [**tieto taulukko**](../controls/control-data-table.md) -ohjaus objekti ja aseta sen **Items** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Distinct( CityPopulations; Country )
    ```

    Voit tarkastella tämän kaavan tulosta kaava rivillä valitsemalla koko kaavan:

    > [!div class="mx-imgBorder"]
    > ![Tuloste DISTINCT-toiminnosta näytetään tulos näkymässä @ no__t-1

1. Lisää **tulos** sarake käyttämällä tieto taulukon ominaisuudet-ruudun **Muokkaa kenttiä** -linkkiä:

    > [!div class="mx-imgBorder"]
    > ![Tuloste DISTINCT-toiminnosta, joka näkyy tieto taulukossa @ no__t-1

1. Lisää [**Selite**](../controls/control-text-box.md) -ohjaus objekti ja aseta sen **Text** -ominaisuudeksi kaava:

    ```powerapps-comma
    First( Sort( Distinct( CityPopulations; Country ); Result ) ).Result
    ```

    Tämä kaava lajittelee tulokset **DISTINCT** -funktiolla [**Sort**](function-sort.md) -funktiolla, ottaa ensimmäisen tietueen tuloksena olevasta taulukosta, jossa on [**ensimmäinen**](function-first-last.md) -funktiolla, ja poimii **tulos** -kentän vain maan nimen saamiseksi.

    > [!div class="mx-imgBorder"]
    > ![Output DISTINCT-toiminnosta, joka näyttää ensimmäisen maan nimen @ no__t-1

     

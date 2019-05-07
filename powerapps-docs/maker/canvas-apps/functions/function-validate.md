---
title: Validate-funktio | Microsoft Docs
description: Validate-funktion viitetietoja, kuten syntaksi ja esimerkit, PowerAppsissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/01/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d92236d630005b4608719efaadef4537984bc3d6
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "63317666"
ms.PowerAppsDecimalTransform: true
---
# <a name="validate-function-in-powerapps"></a>Validate-funktio PowerAppsissa
**Validate**-funktio tarkistaa, onko yksittäisen [sarakkeen](../working-with-tables.md#columns) tai täydellisen [tietueen](../working-with-tables.md#records) arvo kelvollinen [tietolähteelle](../working-with-data-sources.md).  

## <a name="description"></a>Kuvaus
Ennen kuin käyttäjä lähettää tietojen muutoksen, voit antaa välitöntä palautetta kyseisen lähetyksen kelpoisuudesta, mikä parantaa käyttökokemusta.

Tietolähteet voivat antaa tietoa siitä, mitä kelvolliset arvot tietueessa ovat. Nämä tiedot voivat sisältää monia rajoituksia, kuten esimerkiksi:

* täytyykö sarakkeella olla arvo
* kuinka pitkä tekstimerkkijono voi olla
* miten suuri ja pieni numero voi olla
* miten aikainen ja myöhäinen päivämäärä voi olla.

**Validate**-funktio käyttää näitä tietoja määrittämään, onko arvo kelvollinen, ja palauttamaan asianmukaisen virhesanoman, jos se ei ole. **[DataSourceInfo](function-datasourceinfo.md)**-funktiolla voit tarkastella samoja tietoja, joita **Validate** käyttää.

Tietolähteet vaihtelevat sen mukaan, kuinka paljon vahvistustietoja ne antavat tai eivät ehkä anna lainkaan. **Validate** voi vahvistaa vain näihin tietoihin perustuvia arvoja. Vaikka **Validate** ei löytäisi ongelmia, tietojen muutoksen soveltaminen saattaa silti epäonnistua. Voit hankkia tietoja virheestä **[Errors](function-errors.md)**-funktiolla.

Jos **Validate** löytää ongelman, funktio palauttaa virhesanoman, jonka voit näyttää sovelluksen käyttäjälle. Jos kaikki arvot ovat kelvollisia, **Validate** palauttaa [tyhjän](function-isblank-isempty.md) arvon. Kun käsittelet [kokoelmaa](../working-with-data-sources.md#collections), jossa ei ole vahvistustietoja, arvot ovat aina kelvollisia.

## <a name="syntax"></a>Syntaksi
**Validate**( *DataSource*; *Column*; *Value* )

* *DataSource* – Pakollinen. Tietolähde, jonka kanssa vahvistetaan.
* *Column* – Pakollinen. Vahvistettava sarake.
* *Value* – pakollinen. Valitun sarakkeen vahvistettava arvo.

**Validate**( *DataSource*; *OriginalRecord*; *Updates* )

* *DataSource* – Pakollinen. Tietolähde, jonka kanssa vahvistetaan.
* *OriginalRecord* – Pakollinen.  Tietue, jonka mukaan päivityksiä vahvistetaan.
* *Updates* – Pakollinen.  Alkuperäiseen tietueeseen sovellettavat muutokset.

## <a name="examples"></a>Esimerkkejä
Näissä esimerkeissä arvojen **Pisteet**-tietolähteen **Prosenttiosuus**-sarakkeessa on oltava alueella 0–100 (nämä luvut mukaan lukien). Jos tiedot läpäisevät vahvistuksen, funktio palauttaa *tyhjä*n arvon. Muussa tapauksessa funktio palauttaa virhesanoman.

### <a name="validate-with-a-single-column"></a>Vahvista yksittäisen sarakkeen kanssa

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Validate( Scores; Percentage; 10 )** |Tarkistaa, onko **10** kelvollinen arvo **Percentage**-sarakkeelle **Scores**-tietolähteessä. |*tyhjä* |
| **Validate( Scores; Percentage; 120 )** |Tarkistaa, onko **120** kelvollinen arvo **Percentage**-sarakkeelle **Scores**-tietolähteessä. |”Arvojen on oltava alueella 0–100.” |

### <a name="validate-with-a-complete-record"></a>Vahvista täydellisen tietueen kanssa

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Validate( Scores; EditRecord; Gallery.Updates )** |Tarkistaa, ovatko kaikkien sarakkeiden arvot kelvollisia **Scores**-tietolähteen kannalta. Tässä esimerkissä **Percentage**-sarakkeen arvo on **10**. |*tyhjä* |
| **Validate( Scores; EditRecord; Gallery.Updates )** | Tarkistaa, ovatko kaikkien sarakkeiden arvot kelvollisia **Scores**-tietolähteen kannalta. Tässä esimerkissä **Percentage**-sarakkeen arvo on **120**. |”Arvojen on oltava alueella 0–100.” |


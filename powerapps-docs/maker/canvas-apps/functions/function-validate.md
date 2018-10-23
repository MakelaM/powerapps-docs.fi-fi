---
title: Vahvista-funktio | Microsoft Docs
description: Vahvista-funktion viitetietoja, kuten syntaksi ja esimerkit, PowerAppsissa
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
ms.sourcegitcommit: 5a1864d1531b55b332749437674fd1378e1f55ca
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2018
ms.locfileid: "49307834"
---
# <a name="validate-function-in-powerapps"></a>Vahvista-funktio PowerAppsissa
**Vahvista**-funktio tarkistaa, onko yksittäisen [sarakkeen](../working-with-tables.md#columns) tai täydellisen [tietueen](../working-with-tables.md#records) arvo kelvollinen [tietolähteelle](../working-with-data-sources.md).  

## <a name="description"></a>Kuvaus
Ennen kuin käyttäjä lähettää tietojen muutoksen, voit antaa välitöntä palautetta kyseisen lähetyksen kelpoisuudesta, mikä parantaa käyttökokemusta.

Tietolähteet voivat antaa tietoa siitä, mitä kelvolliset arvot tietueessa ovat. Nämä tiedot voivat sisältää monia rajoituksia, kuten esimerkiksi:

* täytyykö sarakkeella olla arvo
* kuinka pitkä tekstimerkkijono voi olla
* miten suuri ja pieni numero voi olla
* miten aikainen ja myöhäinen päivämäärä voi olla.

**Vahvista**-funktio käyttää näitä tietoja määrittämään, onko arvo kelvollinen, ja palauttamaan asianmukaisen virhesanoman, jos se ei ole. **[DataSourceInfo](function-datasourceinfo.md)**-funktiolla voit tarkastella samoja tietoja, joita **Vahvista** käyttää.

Tietolähteet vaihtelevat sen mukaan, kuinka paljon vahvistustietoja ne antavat tai eivät ehkä anna lainkaan. **Vahvista** voi vahvistaa vain näihin tietoihin perustuvia arvoja. Vaikka **Vahvista** ei löytäisi ongelmia, tietojen muutoksen soveltaminen saattaa silti epäonnistua. Voit hankkia tietoja virheestä **[Virheet](function-errors.md)**-funktiolla.

Jos **Vahvista** löytää ongelman, funktio palauttaa virhesanoman, jonka voit näyttää sovelluksen käyttäjälle. Jos kaikki arvot ovat kelvollisia, **Vahvista** palauttaa [tyhjän](function-isblank-isempty.md) arvon. Kun käsittelet [kokoelmaa](../working-with-data-sources.md#collections), jossa ei ole vahvistustietoja, arvot ovat aina kelvollisia.

## <a name="syntax"></a>Syntaksi
**Validate**( *DataSource*, *Column*, *Value* )

* *Tietolähde* – Pakollinen. Tietolähde, jonka kanssa vahvistetaan.
* *Sarake* – Pakollinen. Vahvistettava sarake.
* *Arvo* – Pakollinen. Valitun sarakkeen vahvistettava arvo.

**Validate**( *DataSource*, *OriginalRecord*, *Updates* )

* *Tietolähde* – Pakollinen. Tietolähde, jonka kanssa vahvistetaan.
* *OriginalRecord* – Pakollinen.  Tietue, jonka mukaan päivityksiä vahvistetaan.
* *Päivitykset* – Pakollinen.  Alkuperäiseen tietueeseen sovellettavat muutokset.

## <a name="examples"></a>Esimerkkejä
Näissä esimerkeissä arvojen **Pisteet**-tietolähteen **Prosenttiosuus**-sarakkeessa on oltava alueella 0–100 (nämä luvut mukaan lukien). Jos tiedot läpäisevät vahvistuksen, funktio palauttaa *tyhjä*n arvon. Muussa tapauksessa funktio palauttaa virhesanoman.

### <a name="validate-with-a-single-column"></a>Vahvista yksittäisen sarakkeen kanssa

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Validate( Scores, Percentage, 10 )** |Tarkistaa, onko **10** kelvollinen arvo **Prosenttiosuus**-sarakkeelle **Pisteet**-tietolähteessä. |*tyhjä* |
| **Validate( Scores, Percentage, 120 )** |Tarkistaa, onko **120** kelvollinen arvo **Prosenttiosuus**-sarakkeelle **Pisteet**-tietolähteessä. |”Arvojen on oltava alueella 0–100.” |

### <a name="validate-with-a-complete-record"></a>Vahvista täydellisen tietueen kanssa

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Validate( Scores, EditRecord, Gallery.Updates )** |Tarkistaa, ovatko kaikkien sarakkeiden arvot kelvollisia **Pisteet**-tietolähteen kannalta. Tässä esimerkissä **Prosenttiosuus**-sarakkeen arvo on **10**. |*tyhjä* |
| **Validate( Scores, EditRecord, Gallery.Updates )** | Tarkistaa, ovatko kaikkien sarakkeiden arvot kelvollisia **Pisteet**-tietolähteen kannalta. Tässä esimerkissä **Prosenttiosuus**-sarakkeen arvo on **120**. |”Arvojen on oltava alueella 0–100.” |


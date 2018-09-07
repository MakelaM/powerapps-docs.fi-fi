---
title: Lower-, Upper- ja Proper -funktiot functions | Microsoft Docs
description: PowerAppsin Lower-, Upper- ja Proper-funktioiden viitetiedot mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 72e1bd234a9cbccc24cf35723ee10bacd175b278
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865827"
---
# <a name="lower-upper-and-proper-functions-in-powerapps"></a>PowerAppsin Lower-, Upper- ja Proper -funktiot
Muuntavat tekstimerkkijonot kokonaan pieniksi kirjaimiksi, kokonaan isoiksi kirjaimiksi tai alkamaan isolla kirjaimella.

## <a name="description"></a>Kuvaus
**Lower**-, **Upper**- ja **Proper**-funktiot määrittävät merkkijonojen kirjainkoon.

* **Lower**-funktio määrittää kaikki kirjaimet pieniksi kirjaimiksi.
* **Upper**-funktio määrittää kaikki kirjaimet isoiksi kirjaimiksi.
* **Proper**-funktio määrittää kunkin sanan ensimmäisen kirjaimen isoksi kirjaimeksi ja kaikki muut kirjaimet pieniksi kirjaimiksi.

Kaikki kolme funktiota ohittavat merkit, jotka eivät ole kirjaimia.

Jos välität yksittäisen merkkijonon, palautusarvo on tämän merkkijonon muunnettu versio.  Jos välität yksisarakkeisen, merkkijonoja sisältävän [taulukon](../working-with-tables.md), palautusarvo on yksisarakkeinen taulukko, joka sisältää muunnettuja merkkijonoja. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [Taulukoiden käyttö](../working-with-tables.md) mukaan.

## <a name="syntax"></a>Syntaksi
**Lower**( *String* )<br>**Upper**( *String* )<br>**Proper**( *String* )

* *String* – Pakollinen. Muunnettava merkkijono.

**Lower**( *SingleColumnTable* )<br>**Upper**( *SingleColumnTable* )<br>**Proper**( *SingleColumnTable* )

* *SingleColumnTable* - Pakollinen. Muunnettava yksisarakkeinen merkkijonotaulukko.

## <a name="examples"></a>Esimerkkejä
### <a name="single-string"></a>Yksittäinen merkkijono
Näissä esimerkeissä käytetään [tietolähteenä](../working-with-data-sources.md) tekstisyöte-ohjausobjektia, jonka nimi on **Author**. Ohjausobjektissa on merkkijono "E. E. CummINGS".

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Lower(&nbsp;Author.Text&nbsp;)** |Määrittää kaikki merkkijonon kirjaimet pieniksi kirjaimiksi. |"e. e. cummings" |
| **Upper(&nbsp;Author.Text&nbsp;)** |Määrittää kaikki merkkijonon kirjaimet isoiksi kirjaimiksi. |"E. E. CUMMINGS" |
| **Proper(&nbsp;Author.Text&nbsp;)** |Määrittää kaikkien merkkijonossa olevien sanojen ensimmäisen kirjaimen isoksi ja loput pieniksi. |"E. E. Cummings" |

### <a name="single-column-table"></a>Yksisarakkeinen taulukko
Seuraavissa esimerkeissä muunnetaan merkkijonoja **People**-tietolähteen **Address**[-sarakkeeseen](../working-with-tables.md#columns), joka sisältää seuraavat tiedot:

![](media/function-lower-upper-proper/people-table.png)

Kukin kaava palauttaa yksisarakkeisen taulukon, joka sisältää muunnetut merkkijonot.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Lower( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;) )** |Määrittää kaikki kirjaimet pieniksi kirjaimiksi. |<style> img { max-width:none; } </style> ![](media/function-lower-upper-proper/people-table-lower.png) |
| **Upper( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;) )** |Määrittää kaikki kirjaimet isoiksi kirjaimiksi. |![](media/function-lower-upper-proper/people-table-upper.png) |
| **Proper( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;) )** |Määrittää kunkin sanan ensimmäisen kirjaimen isoksi kirjaimeksi, ja kaikki muut isot kirjaimet pieniksi kirjaimiksi. |![](media/function-lower-upper-proper/people-table-proper.png) |

### <a name="step-by-step-example"></a>Vaiheittainen esimerkki
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti ja anna sille nimi **Source**.
2. Lisää selite ja aseta sen **[Text](../controls/properties-core.md)**-ominaisuudeksi tämä funktio:<br>**Proper(Source.Text)**
3. Paina F5-näppäintä ja kirjoita **ME OLEMME PARHAITA!** **Source**-kenttään.<br>Selitteessä näkyy teksti **Me Olemme Parhaita!**


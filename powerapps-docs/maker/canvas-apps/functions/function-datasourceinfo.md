---
title: DataSourceInfo-funktio | Microsoft Docs
description: PowerAppsin DataSourceInfo-funktion viitetiedot, mukaan lukien syntaksi ja esimerkkejä
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/11/2015
ms.author: gregli
ms.openlocfilehash: 9747bef986587da7e7a66fe6fc165b4d15e80aed
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="datasourceinfo-function-in-powerapps"></a>PowerAppsin DataSourceInfo-funktio
Palauttaa tietoja [tietolähteestä](../working-with-data-sources.md).

## <a name="overview"></a>Yleiskatsaus
Tietolähteet voivat tarjota paljon tietoja käyttökokemuksen optimointiin.

Voit käyttää [saraketason](../working-with-tables.md#columns) tietoja vahvistamaan käyttäjän syötteen ja antamaan käyttäjälle välitöntä palautetta ennen **[Patch](function-patch.md)**-funktion käyttöä. **[Validate](function-validate.md)**-funktio käyttää näitä samoja tietoja.

Voit käyttää tietoja tietolähdetasolla esimerkiksi **Muokkaa**- ja **Uusi**-painikkeiden piilottamiseen, jos käyttäjillä ei ole oikeuksia muokata tai luoda uusia [tietueita](../working-with-tables.md#records).

Tietolähteiden antamien tietomäärät vaihtelevat ja joissain tapauksissa tietoja ei saada yhtään.  [Kokoelmat](../working-with-data-sources.md#collections) eivät anna tietoja. Jos tietoja ei anneta, käytetään oletusta tai palautetaan *tyhjä* arvo.

## <a name="description"></a>Kuvaus
### <a name="column-information"></a>Saraketiedot
Voit käyttää **DataSourceInfo**-funktiota hakemaan tietoja tietolähteen tietystä sarakkeesta:  

| Tietoargumentti | Tuloksen tyyppi | Kuvaus |
| --- | --- | --- |
| **DataSourceInfo.DisplayName** |Merkkijono |Näyttää sarakkeen nimen. Jos näyttönimeä ei ole määritetty, tämä palauttaa sarakkeen nimen. |
| **DataSourceInfo.MaxLength** |Numero |Sarakkeen sisältävien merkkien enimmäismäärä. Koskee vain sarakkeita, jotka sisältävät merkkijonoja. Jos enimmäismäärää ei ole asetettu, palauttaa *tyhjän* arvon. |
| **DataSourceInfo.MaxValue** |Numero |Suurin numeroarvo, jonka sarake voi sisältää. Koskee vain sarakkeita, jotka sisältävät numeroita. Jos enimmäismäärää ei ole asetettu, palauttaa *tyhjän* arvon. |
| **DataSourceInfo.MinValue** |Numero |Pienin numeroarvo, jonka sarake voi sisältää. Koskee vain sarakkeita, jotka sisältävät numeroita. Jos vähimmäismäärää ei ole asetettu, palauttaa *tyhjän* arvon. |
| **DataSourceInfo.Required** |Totuusarvo |Vaaditaanko tälle sarakkeelle arvo? Jos tietolähde ei aseta tätä, palauttaa **epätoden**. |

Kolmas argumentti on sarakkeen nimi merkkijonona.  Esimerkiksi sarake **Puhelin** kokoelmassa **Ihmiset** välitettäisiin muodossa **"Puhelin"**, mukaan lukien lainausmerkit.

### <a name="data-source-information"></a>Tietolähteen tiedot
Voit käyttää **DataSourceInfo**-funktiota hakemaan tietolähteestä kokonaisuutena:  

| Tietoargumentti | Tuloksen tyyppi | Kuvaus |
| --- | --- | --- |
| **DataSourceInfo.AllowedValues** |Totuusarvo |Mitä käyttöoikeuksia käyttäjille voidaan antaa tälle tietolähteelle? Jos tietolähde ei aseta tätä, palauttaa *tyhjän* arvon. |
| **DataSourceInfo.CreatePermission** |Totuusarvo |Onko nykyisellä käyttäjällä oikeus luoda tietueita tässä tietolähteessä? Jos tietolähde ei aseta tätä, palauttaa **toden**. |
| **DataSourceInfo.DeletePermission** |Totuusarvo |Onko nykyisellä käyttäjällä oikeus poistaa tietueita tässä tietolähteessä? Jos tietolähde ei aseta tätä, palauttaa **toden**. |
| **DataSourceInfo.EditPermission** |Totuusarvo |Onko nykyisellä käyttäjällä oikeus muokata tietueita tässä tietolähteessä? Jos tietolähde ei aseta tätä, palauttaa **toden**. |
| **DataSourceInfo.ReadPermission** |Totuusarvo |Onko nykyisellä käyttäjällä oikeus lukea tietueita tässä tietolähteessä? Jos tietolähde ei aseta tätä, palauttaa **toden**. |

## <a name="syntax"></a>Syntaksi
**DataSourceInfo**( *DataSource*, *Tieto*, *SarakkeenNimi* )

* *Tietolähde* – Pakollinen. Käytettävä tietolähde.
* *Tieto* – Pakollinen. Haettavan tiedon tyyppi.
* *SarakkeenNimi* – Valinnainen. Saraketason tiedoille sarakkeen nimi merkkijonona. Sarake **Puhelin** välitettäisiin muodossa **"Puhelin"**, mukaan lukien lainausmerkit. *ColumnName*-argumenttia ei voi käyttää tietolähdetason tietoja varten.
  
    > [!NOTE]
> Jos SharePoint- ja Excel-tietolähteiden sarakenimissä käytetään välilyöntejä, merkitse jokaisen välilyönnin tilalle **\_x0020\_**. Voit esimerkiksi määrittää **Sarakkeen nimeksi** **”Sarakkeen_x0020_Nimi”**.

## <a name="examples"></a>Esimerkkejä
Tämän osion esimerkeissä käytetään tietolähdettä nimeltä **IceCream**:

![](media/function-datasourceinfo/icecream.png)

Tietolähde tarjoaa myös nämä tiedot:

* Kohdan **Quantity** näyttönimi on "Quantity on Hand".
* Kohdan **Flavor** enimmäispituus on 30 merkkiä.
* **Flavor**-sarakkeen täytyy sisältää arvo. **Quantity**-sarake ei ole pakollinen.
* **Quantity**-kohdan vähimmäisarvo on 0.
* **Quantity**-kohdan enimmäisarvo on 100.
* Nykyinen käyttäjä voi lukea ja muokata **IceCream**-tietolähteen tietueita, mutta ei luoda tai poistaa tietueita.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.DisplayName,&nbsp;"Quantity"&nbsp;)** |Palauttaa **IceCream**-tietolähteen **Quantity**-sarakkeen näyttönimen. |"Quantity on Hand" |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.MaxLength,&nbsp;"Flavor"&nbsp;)** |Palauttaa **IceCream**-tietolähteen **Flavor**-sarakkeen merkkijonon enimmäispituuden. |30 |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.Required,&nbsp;"Flavor"&nbsp;)** |Onko **IceCream**-tietolähteen **Flavor**-sarake pakollinen? |**tosi** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.Required,&nbsp;"Quantity"&nbsp;)** |Onko **IceCream**-tietolähteen **Quantity**-sarake pakollinen? |**epätosi** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.MaxValue,&nbsp;"Quantity"&nbsp;)** |Palauttaa **IceCream**-tietolähteen **Quantity**-sarakkeen enimmäisnumeroarvon. |100 |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.MinValue,&nbsp;"Quantity"&nbsp;)** |Palauttaa **IceCream**-tietolähteen **Quantity**-sarakkeen vähimmäisnumeroarvon. |0 |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.ReadPermission)** |Voiko käyttäjä lukea **IceCream**-tietolähteen tietueita? |**tosi** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.EditPermission)** |Voiko käyttäjä muokata **IceCream**-tietolähteen tietueita? |**tosi** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.CreatePermission)** |Voiko käyttäjä luoda **IceCream**-tietolähteen tietueita? |**epätosi** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.DeletePermission)** |Voiko käyttäjä poistaa **IceCream**-tietolähteen tietueita? |**epätosi** |


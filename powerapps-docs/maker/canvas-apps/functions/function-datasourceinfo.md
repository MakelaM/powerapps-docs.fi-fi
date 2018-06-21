---
title: DataSourceInfo-funktio | Microsoft Docs
description: PowerAppsin DataSourceInfo-funktion viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 11/11/2015
ms.author: gregli
ms.openlocfilehash: 5f156e5f7d0acb48090ac921aa92f31f3a6d20ea
ms.sourcegitcommit: 222df368f1f35e9357b0b1adf0e69d7206d8126e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/21/2018
ms.locfileid: "36298465"
---
# <a name="datasourceinfo-function-in-powerapps"></a>PowerAppsin DataSourceInfo-funktio
Antaa [tietolähteen](../working-with-data-sources.md) tietoja.

## <a name="overview"></a>Yleiskatsaus
Tietolähteet voivat tarjota paljon tietoja käyttökokemuksen optimointiin.

Voit käyttää [saraketason](../working-with-tables.md#columns) tietoja vahvistamaan käyttäjän syötteen ja antamaan käyttäjälle välitöntä palautetta ennen **[Patch](function-patch.md)**-funktion käyttöä. **[Validate](function-validate.md)**-funktio käyttää näitä samoja tietoja.

Voit käyttää tietoja tietolähdetasolla esimerkiksi **Muokkaa**- ja **Uusi**-painikkeiden poistamiseen käytöstä tai piilottamiseen, jos käyttäjillä ei ole oikeuksia muokata tai luoda uusia [tietueita](../working-with-tables.md#records).

Tietolähteiden antamat tietomäärät vaihtelevat ja joissain tapauksissa tietoja ei saada yhtään.  [Kokoelmat](../working-with-data-sources.md#collections) eivät anna tietoja. Jos jotakin tietoa ei anneta, käytetään oletusta tai palautetaan *tyhjä* arvo.

## <a name="description"></a>Kuvaus
### <a name="column-information"></a>Saraketiedot
Voit käyttää **DataSourceInfo**-funktiota hakemaan tietoja tietolähteen tietystä sarakkeesta:  

| Tietoargumentti | Tuloksen tyyppi | Kuvaus |
| --- | --- | --- |
| **DataSourceInfo.DisplayName** |Merkkijono |Näyttää sarakkeen nimen. Jos näyttönimeä ei ole määritetty, tämä palauttaa sarakkeen nimen. |
| **DataSourceInfo.MaxLength** |Numero |Sarakkeen sisältävien merkkien enimmäismäärä. Koskee vain sarakkeita, jotka sisältävät merkkijonoja. Jos enimmäismäärää ei ole asetettu, palauttaa *tyhjän* arvon. |
| **DataSourceInfo.MaxValue** |Numero |Suurin numeroarvo, jonka sarake voi sisältää. Koskee vain sarakkeita, jotka sisältävät numeroita. Jos enimmäismäärää ei ole asetettu, palauttaa *tyhjän* arvon. |
| **DataSourceInfo.MinValue** |Numero |Pienin numeroarvo, jonka sarake voi sisältää. Koskee vain sarakkeita, jotka sisältävät numeroita. Jos vähimmäismäärää ei ole asetettu, palauttaa *tyhjän* arvon. |
| **DataSourceInfo.Required** |Totuusarvo |Vaaditaanko tälle sarakkeelle arvo? Jos tietolähde ei aseta tätä, palauttaa arvon **false**. |

Kolmas argumentti on sarakkeen nimi merkkijonona.  Esimerkiksi sarake **Puhelin** kokoelmassa **Ihmiset** välitettäisiin muodossa **"Puhelin"**, mukaan lukien lainausmerkit.

### <a name="data-source-information"></a>Tietolähteen tiedot
Voit käyttää **DataSourceInfo**-funktiota hakemaan tietoja tietolähteestä kokonaisuutena:  

| Tietoargumentti | Tuloksen tyyppi | Kuvaus |
| --- | --- | --- |
| **DataSourceInfo.AllowedValues** |Totuusarvo |Mitä käyttöoikeuksia käyttäjille voidaan antaa tähän tietolähteeseen? Jos tietolähde ei aseta tätä, palauttaa *tyhjän* arvon. |
| **DataSourceInfo.CreatePermission** |Totuusarvo |Onko nykyisellä käyttäjällä oikeus luoda tietueita tässä tietolähteessä? Jos tietolähde ei aseta tätä, palauttaa arvon **true**. |
| **DataSourceInfo.DeletePermission** |Totuusarvo |Onko nykyisellä käyttäjällä oikeus poistaa tietueita tässä tietolähteessä? Jos tietolähde ei aseta tätä, palauttaa arvon **true**. |
| **DataSourceInfo.EditPermission** |Totuusarvo |Onko nykyisellä käyttäjällä oikeus muokata tietueita tässä tietolähteessä? Jos tietolähde ei aseta tätä, palauttaa arvon **true**. |
| **DataSourceInfo.ReadPermission** |Totuusarvo |Onko nykyisellä käyttäjällä oikeus lukea tietueita tässä tietolähteessä? Jos tietolähde ei aseta tätä, palauttaa arvon **true**. |

## <a name="syntax"></a>Syntaksi
**DataSourceInfo**( *DataSource*, *Information*, *ColumnName* )

* *DataSource* – Pakollinen. Käytettävä tietolähde.
* *Tiedot* – Pakollinen. Haettavan tiedon tyyppi.
* *ColumnName* – Valinnainen. Saraketason tiedoille sarakkeen nimi merkkijonona. Sarake **Puhelin** välitettäisiin muodossa **"Puhelin"**, mukaan lukien lainausmerkit. *ColumnName*-argumenttia ei voi käyttää tietolähdetason tietoja varten.
  
    > [!NOTE]
> Jos SharePoint- ja Excel-tietolähteiden sarakenimissä käytetään välilyöntejä, merkitse jokaisen välilyönnin tilalle **\_x0020\_**. Voit esimerkiksi määrittää **Sarakkeen nimeksi** **”Sarakkeen_x0020_Nimi”**.

## <a name="examples"></a>Esimerkkejä
Tämän osion esimerkeissä käytetään tietolähdettä nimeltä **IceCream**:

![](media/function-datasourceinfo/icecream.png)

Tietolähde on antanut myös nämä tiedot:

* Kohdan **Määrä** näyttönimi on "Quantity on Hand".
* Kohdan **Flavor** enimmäispituus on 30 merkkiä.
* **Flavor**-sarakkeen täytyy sisältää arvo. **Määrä**-sarake ei ole pakollinen.
* **Määrä**-kohdan vähimmäisarvo on 0.
* **Määrä**-kohdan enimmäisarvo on 100.
* Nykyinen käyttäjä voi lukea ja muokata **IceCream**-tietolähteen tietueita, mutta ei luoda tai poistaa tietueita.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.DisplayName,&nbsp;"Quantity"&nbsp;)** |Palauttaa **IceCream**-tietolähteen **Määrä**-sarakkeen näyttönimen. |"Quantity on Hand" |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.MaxLength,&nbsp;"Flavor"&nbsp;)** |Palauttaa **IceCream**-tietolähteen **Flavor**-sarakkeen merkkijonon enimmäispituuden. |30 |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.Required,&nbsp;"Flavor"&nbsp;)** |Onko **IceCream**-tietolähteen **Flavor**-sarake pakollinen? |**true** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.Required,&nbsp;"Quantity"&nbsp;)** |Onko **IceCream**-tietolähteen **Määrä**-sarake pakollinen? |**false** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.MaxValue,&nbsp;"Quantity"&nbsp;)** |Palauttaa **IceCream**-tietolähteen **Määrä**-sarakkeen enimmäisnumeroarvon. |100 |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.MinValue,&nbsp;"Quantity"&nbsp;)** |Palauttaa **IceCream**-tietolähteen **Määrä**-sarakkeen vähimmäisnumeroarvon. |0 |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.ReadPermission)** |Voiko nykyinen käyttäjä lukea **IceCream**-tietolähteen tietueita? |**true** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.EditPermission)** |Voiko nykyinen käyttäjä muokata **IceCream**-tietolähteen tietueita? |**true** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.CreatePermission)** |Voiko nykyinen käyttäjä luoda **IceCream**-tietolähteen tietueita? |**false** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.DeletePermission)** |Voiko nykyinen käyttäjä poistaa **IceCream**-tietolähteen tietueita? |**false** |


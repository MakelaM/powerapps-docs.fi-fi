---
title: Collect-, Clear- ja ClearCollect-funktiot | Microsoft Docs
description: Collect-, Clear- ja ClearCollect-funktioiden viitetiedot PowerAppsissa, mukaan lukien syntaksi ja esimerkkejä
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
ms.openlocfilehash: 351fede5be1e0f3db74bde065dd9663672afd08a
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992913"
---
# <a name="collect-clear-and-clearcollect-functions-in-powerapps"></a>Collect-, Clear- ja ClearCollect-funktiot PowerAppsissa

Luo ja tyhjentää [kokoelmat](../working-with-data-sources.md#collections) ja lisää [tietueita](../working-with-tables.md#records) mihin tahansa [tietolähteeseen](../working-with-data-sources.md).

## <a name="description"></a>Kuvaus

### <a name="collect"></a>Collect

**Collect**-funktio lisää tietueita tietolähteeseen. Lisättäviä kohteita voivat olla

- Yksittäinen arvo: Arvo asetetaan uuden tietueen **[arvo](function-value.md)** -kenttään.  Kaikki muut ominaisuudet jäävät [tyhjäksi](function-isblank-isempty.md).
- Tietue: Jokainen nimetty ominaisuus asetetaan uuden tietueen vastaavaan ominaisuuteen.  Kaikki muut ominaisuudet jäävät tyhjäksi.
- [Taulukko](../working-with-tables.md): Taulukon jokainen tietue lisätään tieto lähteen erillisenä tietueena edellä kuvatulla tavalla. Taulukkoa ei lisätä sisäkkäisenä taulukkona tietueeseen. Rivitä tietueessa oleva taulukko ensin, jotta tämä onnistuu.

Kokoelmassa käytettäessä muita [sarakkeita](../working-with-tables.md#columns) luodaan tarpeen mukaan. Muiden tietolähteiden sarakkeet ovat tietolähteen mukaisesti kiinteitä, eikä uusia sarakkeita voi lisätä.  

Jos tietolähdettä ei vielä ole olemassa, luodaan kokoelma.

Kokoelmia käytetään joskus yleisten muuttujien säilyttämiseen tai tietolähteen väliaikaisen kopion tekemiseen. PowerApps perustuu kaavoihin, jotka lasketaan automaattisesti uudelleen, kun käyttäjä on vuorovaikutuksessa sovelluksen kanssa. Kokoelmat eivät tarjoa tätä etua, ja ne voivat vaikeuttaa sovelluksesi laatimista ja ymmärtämistä. Ennen kuin käytät kokoelmaa tällä tavalla, tutustu [muuttujien käyttämiseen](../working-with-variables.md).

Voit käyttää myös **[Patch](function-patch.md)** -funktiota tietolähteen tietueiden luomiseen.

**Collect** palauttaa muokatun tietolähteen taulukkona.  **Collect**-funktiota voidaan käyttää vain [toimintokaavoissa](../working-with-formulas-in-depth.md).

### <a name="clear"></a>Clear

**Clear**-funktio poistaa kaikki tietueet kokoelmasta.  Kokoelman sarakkeet säilyvät.

Huomaa, että **Clear** toimii vain kokoelmissa, ei muissa tietolähteissä.  Voit käyttää lauseketta **[RemoveIf](function-remove-removeif.md)( *DataSource*, true)** tähän tarkoitukseen.  Ole varovainen, sillä tämä poistaa kaikki tietueet tietolähteen tallennustilasta ja voi vaikuttaa muihin käyttäjiin.

Voit käyttää **[Remove](function-remove-removeif.md)** -funktiota tietueiden poistamiseen valikoivasti.

**Clear**-funktiolla ei ole paluuarvoa.  Sitä voidaan käyttää vain toimintokaavoissa.

### <a name="clearcollect"></a>ClearCollect

**ClearCollect**-funktio poistaa kaikki tietueet kokoelmasta ja lisää sitten eri tietuejoukon samaan kokoelmaan.  Yksittäinen **ClearCollect**-funktio suorittaa ensin funktion **Clear** ja sitten funktion **Collect** yhdistelmänä.

**ClearCollect** palauttaa muokatun kokoelman taulukkona.  **ClearCollect**-funktiota voidaan käyttää vain toimintokaavoissa.

## <a name="syntax"></a>Syntaksi

**Collect**( *DataSource*, *Item*, ... )

* *DataSource* – Pakollinen. Tietolähde, johon haluat lisätä tiedot.  Jos sitä ei vielä ole olemassa, luodaan uusi kokoelma.
* *Item* – pakollinen.  Yksi tai useampia tietueita tai taulukoita tietolähteeseen lisättäväksi.  

**Clear**( *Collection* )

* *Collection* – pakollinen. Kokoelma, jonka haluat tyhjentää.

**ClearCollect**( *Collection*, *Item*, ... )

* *Collection* – pakollinen. Kokoelma, jonka tahdot tyhjentää ja johon haluat lisätä sen jälkeen tietoa.
* *Item* – pakollinen.  Yksi tai useampia tietueita tai taulukoita tietolähteeseen lisättäväksi.  

## <a name="examples"></a>Esimerkkejä

### <a name="clearing-and-adding-records-to-a-data-source"></a>Tietolähteen tietueiden poistaminen ja lisääminen

Näissä esimerkeissä poistetaan ja lisätään kohteita kokoelmaan, jonka nimi on **IceCream**. Tietolähde alkaa tällä sisällöllä:

![Malli tieto lähde](media/function-clear-collect-clearcollect/icecream.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **ClearCollect( IceCream, {&nbsp;Flavor:&nbsp;"Strawberry",&nbsp;Quantity:&nbsp;300&nbsp;} )** |Tyhjentää kaikki tiedot **IceCream**-kokoelmasta ja lisää sitten tietueen, joka sisältää mansikkajäätelön määrän. |<style>IMG {Max-width: none}</style> ![Table yhdellä tietueella @ no__t-2<br><br>**Icecream** -kokoelmaa on myös muokattu. |
| **Collect( IceCream, {&nbsp;Flavor:&nbsp;"Pistachio",&nbsp;Quantity:&nbsp;40&nbsp;}, {&nbsp;Flavor:&nbsp;"Orange",&nbsp;Quantity:&nbsp;200&nbsp;}  )** |Lisää kaksi tietuetta **icecream** -kokoelmaan, joka sisältää määrän pistaasi-ja appelsiini-jäätelöä. |![Taulukko, jossa on kaksi tietuetta @ no__t-1<br><br>**Icecream** -kokoelmaa on myös muokattu. |
| **Clear( IceCream )** |Poistaa kaikki tietueet **IceCream**-kokoelmasta. |![Tyhjä taulukko @ no__t-1<br><br>**Icecream** -kokoelmaa on myös muokattu. |

Vaiheittaisia esimerkkejä kokoelman luomisesta on kohdassa [kokoelman luominen ja päivittäminen](../create-update-collection.md).

### <a name="records-and-tables"></a>Tietueet ja taulukot

Näissä esimerkeissä tarkastellaan sitä, miten **kerätyt** ja **clearcollect** -kohteen tietueet ja taulukko argumentit käsitellään.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **ClearCollect (IceCream, {&nbsp;Flavor: &nbsp; "Chocolate", &nbsp;Määrä: &nbsp;100 @ no__t-5}, {&nbsp;Flavor: &nbsp; "Vanilla", &nbsp;Quantity: &nbsp;200 @ no__t-10})** | Tyhjennä kaikki tiedot ja lisää sitten kaksi tietuetta **icecream** -kokoelmaan, joka sisältää määrän suklaata ja vanilja jäätelöä.  Lisättävät tietueet annetaan funktiolla yksittäisinä argumentteina.| ![Suklaa ja vanilja Records lisättiin kokoelmaan @ no__t-1 <br><br>**Icecream** -kokoelmaa on myös muokattu. |
| **ClearCollect (IceCream, Table ({&nbsp;Flavor: &nbsp; "Chocolate", &nbsp;Määrä: &nbsp;100 @ no__t-5}, {&nbsp;Flavor: &nbsp; "Vanilla", &nbsp;Quantity: &nbsp;200 @ no__t-10}))** | Sama kuin edellisessä esimerkissä, mutta tietueet yhdistetään taulukossa ja välitetään yksittäisen argumentin kautta. Taulukon sisältö poimitaan tietue tietueen mukaan, ennen kuin se lisätään **icecream** -kokoelmaan. | ![Suklaa ja vanilja Records lisättiin kokoelmaan @ no__t-1<br><br>**Icecream** -kokoelmaa on myös muokattu. |
| **ClearCollect (IceCream, <br> {&nbsp;MyFavorites: Taulukko ({&nbsp;Flavor: &nbsp; "Chocolate", &nbsp;Määrä: &nbsp;100 @ no__t-4}, {&nbsp;Flavor: &nbsp; "Vanilla", &nbsp;Määrä: &nbsp;200 @ no__t-9})}) 0 | Sama kuin edellisessä esimerkissä, mutta taulukko on kääritty tietueeseen.  Taulukon tietueita ei poimita, vaan koko taulukko lisätään tietueen alitaulukoksi. | ![Suklaa ja vanilja Records lisättiin kokoelmaan @ no__t-1<br><br>**Icecream** -kokoelmaa on myös muokattu. |


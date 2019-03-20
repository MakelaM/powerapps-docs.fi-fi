---
title: Collect-, Clear- ja ClearCollect-funktiot | Microsoft Docs
description: Collect-, Clear- ja ClearCollect-funktioiden viitetiedot PowerAppsissa, mukaan lukien syntaksi ja esimerkkejä
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
ms.openlocfilehash: 86d36af00d3c5aa825b01ed873150f94738a952c
ms.sourcegitcommit: b0fa125080913f7e749cc754f89424151e051a13
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/21/2019
ms.locfileid: "54418278"
---
# <a name="collect-clear-and-clearcollect-functions-in-powerapps"></a>Collect-, Clear- ja ClearCollect-funktiot PowerAppsissa

Luo ja tyhjentää [kokoelmat](../working-with-data-sources.md#collections) ja lisää [tietueita](../working-with-tables.md#records) mihin tahansa [tietolähteeseen](../working-with-data-sources.md).

## <a name="description"></a>Kuvaus

### <a name="collect"></a>Collect

**Collect**-funktio lisää tietueita tietolähteeseen. Lisättäviä kohteita voivat olla

- Yksittäinen arvo: Arvo sijoitetaan **[arvo](function-value.md)** uuden tietueen kenttää.  Kaikki muut ominaisuudet jäävät [tyhjäksi](function-isblank-isempty.md).
- Tietue: Kukin nimetty ominaisuus sijoitetaan uuden tietueen vastaavaan ominaisuuteen.  Kaikki muut ominaisuudet jäävät tyhjäksi.
- A [taulukon](../working-with-tables.md): Taulukon jokainen tietue lisätään erillisenä tietueena edellä kuvatulla tavalla tietolähteen. Taulukkoa ei lisätä sisäkkäisenä taulukkona tietueeseen. Rivitä tietueessa oleva taulukko ensin, jotta tämä onnistuu.

Kokoelmassa käytettäessä muita [sarakkeita](../working-with-tables.md#columns) luodaan tarpeen mukaan. Muiden tietolähteiden sarakkeet ovat tietolähteen mukaisesti kiinteitä, eikä uusia sarakkeita voi lisätä.  

Jos tietolähdettä ei vielä ole olemassa, luodaan kokoelma.

Kokoelmia käytetään joskus yleisten muuttujien säilyttämiseen tai tietolähteen väliaikaisen kopion tekemiseen. PowerApps perustuu kaavoihin, jotka lasketaan automaattisesti uudelleen, kun käyttäjä on vuorovaikutuksessa sovelluksen kanssa. Kokoelmat eivät tarjoa tätä etua, ja ne voivat vaikeuttaa sovelluksesi laatimista ja ymmärtämistä. Ennen kuin käytät kokoelmaa tällä tavalla, tutustu [muuttujien käyttämiseen](../working-with-variables.md).

Voit käyttää myös **[Patch](function-patch.md)**-funktiota tietolähteen tietueiden luomiseen.

**Collect** palauttaa muokatun tietolähteen taulukkona.  **Collect**-funktiota voidaan käyttää vain [toimintokaavoissa](../working-with-formulas-in-depth.md).

### <a name="clear"></a>Clear

**Clear**-funktio poistaa kaikki tietueet kokoelmasta.  Kokoelman sarakkeet säilyvät.

Huomaa, että **Clear** toimii vain kokoelmissa, ei muissa tietolähteissä.  Voit käyttää lauseketta **[RemoveIf](function-remove-removeif.md)( *DataSource*, true)** tähän tarkoitukseen.  Ole varovainen, sillä tämä poistaa kaikki tietueet tietolähteen tallennustilasta ja voi vaikuttaa muihin käyttäjiin.

Voit käyttää **[Remove](function-remove-removeif.md)**-funktiota tietueiden poistamiseen valikoivasti.

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

![Mallin tietolähde](media/function-clear-collect-clearcollect/icecream.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **ClearCollect( IceCream, {&nbsp;Flavor:&nbsp;"Strawberry",&nbsp;Quantity:&nbsp;300&nbsp;} )** |Tyhjentää kaikki tiedot **IceCream**-kokoelmasta ja lisää sitten tietueen, joka sisältää mansikkajäätelön määrän. |<style> IMG {Enimmäisleveys: ei mitään} </style> ![taulukon, jossa on yksi tietue](media/function-clear-collect-clearcollect/icecream-clearcollect.png)<br><br>**IceCream**-tietolähdettä on myös muokattu. |
| **Collect( IceCream, {&nbsp;Flavor:&nbsp;"Pistachio",&nbsp;Quantity:&nbsp;40&nbsp;}, {&nbsp;Flavor:&nbsp;"Orange",&nbsp;Quantity:&nbsp;200&nbsp;}  )** |Lisää kaksi tietuetta **IceCream**-kokoelmaan. Ne sisältävät pistaasi- ja appelsiinijäätelön määrät. |![Taulukko, jossa on kaksi tietuetta](media/function-clear-collect-clearcollect/icecream-collect.png)<br><br>**IceCream**-tietolähdettä on myös muokattu. |
| **Clear( IceCream )** |Poistaa kaikki tietueet **IceCream**-kokoelmasta. |![Tyhjä taulukko](media/function-clear-collect-clearcollect/icecream-clear.png)<br><br>**IceCream**-tietolähdettä on myös muokattu. |

Katso vaiheittaiset ohjeet siitä, miten voit luoda kokoelman esimerkkejä [Luo ja Päivitä kokoelma](../create-update-collection.md).

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
ms.openlocfilehash: 8a7c52962c23df5f2efcf76c04aeba528e94217c
ms.sourcegitcommit: 464ee88a958dda11c5de5603c608deab6c9cdcab
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/04/2018
ms.locfileid: "48578738"
---
# <a name="collect-clear-and-clearcollect-functions-in-powerapps"></a>Collect-, Clear- ja ClearCollect-funktiot PowerAppsissa
Luo ja tyhjentää [kokoelmat](../working-with-data-sources.md#collections) ja lisää [tietueita](../working-with-tables.md#records) mihin tahansa [tietolähteeseen](../working-with-data-sources.md).

## <a name="description"></a>Kuvaus
### <a name="collect"></a>Collect
**Collect**-funktio lisää tietueita tietolähteeseen. Lisättäviä kohteita voivat olla

* Yksittäinen arvo: arvo sijoitetaan uuden tietueen **[Value](function-value.md)**-kenttään.  Kaikki muut ominaisuudet jäävät [tyhjäksi](function-isblank-isempty.md).
* Tietue: Kukin nimetty ominaisuus sijoitetaan uuden tietueen vastaavaan ominaisuuteen.  Kaikki muut ominaisuudet jäävät tyhjäksi.
* [Taulukko](../working-with-tables.md): Taulukon jokainen tietue lisätään tietolähteen erillisenä tietueena edellä kuvatulla tavalla. Taulukkoa ei lisätä sisäkkäisenä taulukkona tietueeseen. Rivitä tietueessa oleva taulukko ensin, jotta tämä onnistuu.

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

* *DataSource* – pakollinen. Tietolähde, johon haluat lisätä tiedot.  Jos sitä ei vielä ole olemassa, luodaan uusi kokoelma.
* *Item* – pakollinen.  Yksi tai useampia tietueita tai taulukoita tietolähteeseen lisättäväksi.  

**Clear**( *Collection* )

* *Collection* – pakollinen. Kokoelma, jonka haluat tyhjentää.

**ClearCollect**( *Collection*, *Item*, ... )

* *Collection* – pakollinen. Kokoelma, jonka tahdot tyhjentää ja johon haluat lisätä sen jälkeen tietoa.
* *Item* – pakollinen.  Yksi tai useampia tietueita tai taulukoita tietolähteeseen lisättäväksi.  

## <a name="examples"></a>Esimerkkejä
### <a name="clearing-and-adding-records-to-a-data-source"></a>Tietolähteen tietueiden poistaminen ja lisääminen
Näissä esimerkeissä poistetaan ja lisätään kohteita kokoelmaan, jonka nimi on **IceCream**.  Tietolähde alkaa tällä sisällöllä:

![](media/function-clear-collect-clearcollect/icecream.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **ClearCollect( IceCream, {&nbsp;Flavor:&nbsp;"Strawberry",&nbsp;Quantity:&nbsp;300&nbsp;} )** |Tyhjentää kaikki tiedot **IceCream**-kokoelmasta ja lisää sitten tietueen, joka sisältää mansikkajäätelön määrän. |<style> img { max-width: none } </style> ![](media/function-clear-collect-clearcollect/icecream-clearcollect.png)<br><br>**IceCream**-tietolähdettä on myös muokattu. |
| **Collect( IceCream, {&nbsp;Flavor:&nbsp;"Pistachio",&nbsp;Quantity:&nbsp;40&nbsp;}, {&nbsp;Flavor:&nbsp;"Orange",&nbsp;Quantity:&nbsp;200&nbsp;}  )** |Lisää kaksi tietuetta **IceCream**-kokoelmaan. Ne sisältävät pistaasi- ja appelsiinijäätelön määrät. |![](media/function-clear-collect-clearcollect/icecream-collect.png)<br><br>**IceCream**-tietolähdettä on myös muokattu. |
| **Clear( IceCream )** |Poistaa kaikki tietueet **IceCream**-kokoelmasta. |![](media/function-clear-collect-clearcollect/icecream-clear.png)<br><br>**IceCream**-tietolähdettä on myös muokattu. |

### <a name="collect-a-static-list"></a>Staattisen luettelon kerääminen

1. Lisää painike ja määritä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>**Collect(Tuotteet, &quot;Europa&quot;, &quot;Ganymede&quot;, &quot;Callisto&quot;)**
   
    Tämä funktio luo kokoelman, jonka nimi on **Tuotteet** ja joka sisältää rivin kullekin kolmelle tuotteen nimelle.
    
1. Pidä Alt-näppäintä painettuna ja valitse painike.

1. (valinnainen) Jos haluat esikatsella luomaasi kokoelmaa, valitse **Tiedosto-valikosta** **Kokoelmat**.

### <a name="put-a-sharepoint-list-into-a-collection"></a>SharePoint-luettelon asettaminen kokoelmaan

1. [Yhdistä SharePoint-luetteloon](../connect-to-sharepoint.md). 

1. Lisää painike ja määritä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä funktio. Korvaa *ListName* SharePoint-luettelon nimellä:<br>
**Kerää**(**MySPCollection**, *ListName*)

    Tämä funktio luo kokoelman, jonka nimi on **MySPCollection** ja joka sisältää samat tiedot kuin SharePoint-luettelokin.
    
1. Pidä Alt-näppäintä painettuna ja valitse painike.

1. (valinnainen) Jos haluat esikatsella luomaasi kokoelmaa, valitse **Tiedosto-valikosta** **Kokoelmat**.

Artikkelista [Tietojen näyttäminen galleriassa](../connections/connection-sharepoint-online.md#show-data-in-a-gallery) saat lisätietoja siitä, miten voit esittää tietoja SharePoint-luettelossa (esimerkiksi päivämäärät, vaihtoehdot ja henkilöt). Artikkelista [Lomakkeen ja muokkaaminen ja lomakkeen ohjausobjektien näyttäminen](../controls/control-form-detail.md) saat lisätietoa siitä, miten voit esittää tietoja lomakkeessa (avattavat luettelot, päivämäärävalitsimet ja henkilövalitsimet).

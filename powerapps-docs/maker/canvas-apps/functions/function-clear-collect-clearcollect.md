---
title: Collect-, Clear- ja ClearCollect-funktiot | Microsoft Docs
description: Collect-, Clear- ja ClearCollect-funktioiden viitetiedot PowerAppsissa, mukaan lukien syntaksi ja esimerkkejä
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/01/2015
ms.author: gregli
ms.openlocfilehash: cc12241861a1dd6a0242810bb1a6faab70a2de27
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="collect-clear-and-clearcollect-functions-in-powerapps"></a>Collect-, Clear- ja ClearCollect-funktiot PowerAppsissa
Luo ja tyhjentää [kokoelmat](../working-with-data-sources.md#collections) ja lisää [tietueita](../working-with-tables.md#records) mihin tahansa [tietolähteeseen](../working-with-data-sources.md).

## <a name="description"></a>Kuvaus
### <a name="collect"></a>Collect
**Collect**-funktio lisää tietueita tietolähteeseen. Lisättävät kohteet voivat olla:

* Yksittäinen arvo: arvo sijoitetaan uuden tietueen **[Value](function-value.md)**-kenttään.  Kaikki muut ominaisuudet jäävät [tyhjäksi](function-isblank-isempty.md).
* Tietue: Kukin nimetty ominaisuus sijoitetaan uuden tietueen vastaavaan ominaisuuteen.  Kaikki muut ominaisuudet jäävät tyhjäksi.
* [Taulukko](../working-with-tables.md): Taulukon jokainen tietue lisätään tietolähteen erillisenä tietueena edellä kuvatulla tavalla. Taulukkoa ei lisätä sisäkkäisenä taulukkona tietueeseen. Rivitä tietueessa oleva taulukko ensin, jotta tämä onnistuu.

Kokoelmassa käytettäessä muita [sarakkeita](../working-with-tables.md#columns) luodaan tarpeen mukaan. Muiden tietolähteiden sarakkeet ovat tietolähteen mukaisesti kiinteitä ja uusia sarakkeita ei voi lisätä.  

Jos tietolähdettä ei vielä ole olemassa, luodaan kokoelma.

Kokoelmia käytetään joskus yleisten muuttujien säilyttämiseen tai tietolähteen väliaikaisen kopion tekemiseen. PowerApps perustuu kaavoihin, jotka lasketaan automaattisesti uudelleen, kun käyttäjä on vuorovaikutuksessa sovelluksen kanssa. Kokoelmat eivät tarjoa tätä etua ja ne voivat vaikeuttaa sovelluksesi laatimista ja ymmärtämistä. Ennen kuin käytät kokoelmaa tällä tavalla, tutustu [muuttujien käyttämiseen](../working-with-variables.md).

Voit käyttää myös **[Patch](function-patch.md)**-funktiota tietolähteen tietueiden luomiseen.

**Collect** palauttaa muokatun tietolähteen taulukkona.  **Collect**-funktiota voidaan käyttää vain [toimintokaavoissa](../working-with-formulas-in-depth.md).

### <a name="clear"></a>Clear
**Clear**-funktio poistaa kaikki tietueet kokoelmasta.  Kokoelman sarakkeet säilyvät.

Huomaa, että **Clear** toimii vain kokoelmissa, mutta ei muissa tietolähteissä.  Voit käyttää lauseketta **[RemoveIf](function-remove-removeif.md)( *Tietolähde*, true)** tähän tarkoitukseen.  Ole varovainen, sillä tämä poistaa kaikki tietueet tietolähteen tallennustilasta ja voi vaikuttaa muihin käyttäjiin.

Voit käyttää **[Remove](function-remove-removeif.md)**-funktiota tietueiden poistamiseen valikoivasti.

**Clear**-funktiolla ei ole paluuarvoa.  Sitä voidaan käyttää vain toimintokaavoissa.

### <a name="clearcollect"></a>ClearCollect
**ClearCollect**-funktio poistaa kaikki tietueet kokoelmasta ja lisää sitten eri tietuejoukon samaan kokoelmaan.  Yksittäinen **ClearCollect**-funktio suorittaa ensin funktion **Clear** ja sitten funktion **Collect** yhdistelmänä.

**ClearCollect** palauttaa muokatun kokoelman taulukkona.  **ClearCollect**-funktiota voidaan käyttää vain toimintokaavoissa.

## <a name="syntax"></a>Syntaksi
**Collect**( *Tietolähde*, *Kohde*, ... )

* *Tietolähde* – pakollinen. Tietolähde, johon haluat lisätä tiedot.  Jos sitä ei vielä ole olemassa, luodaan uusi kokoelma.
* *Kohde* – pakollinen.  Yksi tai useampia tietueita tai taulukoita tietolähteeseen lisättäväksi.  

**Clear**( *Kokoelma* )

* *Kokoelma* – pakollinen. Kokoelma, jonka haluat tyhjentää.

**ClearCollect**( *Kokoelma*, *Kohde*, ... )

* *Kokoelma* – pakollinen. Kokoelma, jonka tahdot tyhjentää ja johon haluat lisätä sen jälkeen tietoa.
* *Kohde* – pakollinen.  Yksi tai useampia tietueita tai taulukoita tietolähteeseen lisättäväksi.  

## <a name="examples"></a>Esimerkkejä
### <a name="clearing-and-adding-records-to-a-data-source"></a>Tietolähteen tietueiden poistaminen ja lisääminen
Näissä esimerkeissä poistat ja lisäät tietueita **Jäätelö**-nimisessä kokoelmassa.  Tietolähde alkaa tällä sisällöllä:

![](media/function-clear-collect-clearcollect/icecream.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **ClearCollect( Jäätelö, {&nbsp;Maku:&nbsp;"Mansikka",&nbsp;Määrä:&nbsp;300&nbsp;} )** |Tyhjentää kaikki tiedot **Jäätelö**-kokoelmasta ja lisää sitten tietueen, joka sisältää mansikkajäätelön määrän. |<style> img { max-width: none } </style> ![](media/function-clear-collect-clearcollect/icecream-clearcollect.png)<br><br>**Jäätelö**-tietolähdettä on myös muokattu. |
| **Collect( Jäätelö, {&nbsp;Maku:&nbsp;"Pistaasi",&nbsp;Määrä:&nbsp;40&nbsp;}, {&nbsp;Maku:&nbsp;"Appelsiini",&nbsp;Määrä:&nbsp;200&nbsp;}  )** |Lisää kaksi tietuetta **Jäätelö**-kokoelmaan. Ne sisältävät pistaasi- ja appelsiinijäätelön määrät. |![](media/function-clear-collect-clearcollect/icecream-collect.png)<br><br>**Jäätelö**-tietolähdettä on myös muokattu. |
| **Clear( Jäätelö)** |Poistaa kaikki tietueet **Jäätelö**-kokoelmasta. |![](media/function-clear-collect-clearcollect/icecream-clear.png)<br><br>**Jäätelö**-tietolähdettä on myös muokattu. |

### <a name="step-by-step"></a>Vaihe vaiheelta
1. Lisää painike ja määritä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>**Collect(Tuotteet, &quot;Europa&quot;, &quot;Ganymede&quot;, &quot;Callisto&quot;)**
   
    Tämä funktio luo kokoelman, jonka nimi on **Tuotteet** ja joka sisältää rivin kullekin kolmelle tuotteen nimelle.
2. Palaa suunnittelutyötilaan painamalla F5-näppäintä, napsauttamalla painiketta ja painamalla sitten Esc-näppäintä.
3. (valinnainen) Saat esiin luomasi kokoelman esikatselun napsauttamalla kohtaa **Collections** **Content**-välilehdessä.


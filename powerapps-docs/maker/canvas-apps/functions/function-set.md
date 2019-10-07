---
title: Set-funktio | Microsoft Docs
description: PowerAppsin Set-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/29/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4c84fcac442d55cd20112f49c48f544d3f5b92b3
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992197"
---
# <a name="set-function-in-powerapps"></a>PowerAppsin Set-funktio
Asettaa yleisen muuttujan arvon.

## <a name="overview"></a>Yleiskatsaus
Käytä **Set**-funktiota yleisen muuttujan arvon asettamiseen. Yleinen muuttuja säilyttää tilapäisesti tietoja, kuten montako kertaa käyttäjä on valinnut painikkeen tai tietotoiminnon tuloksen.  

Yleiset muuttujat ovat koko sovelluksen käytettävissä kaikissa sen näytöissä. Tämä on yksinkertaisin muuttujatyyppi, ja se täyttää tarpeet useimmissa tapauksissa. On myös olemassa kontekstimuuttujia, jotka toimivat yhdessä ruudussa, sekä kokoelmia, jotka mahdollistavat taulukoiden rivitason muokkaukset. Lisä tietoja näistä muista asetuksista on kohdassa [ymmärrä muuttujia](../working-with-variables.md).

PowerApps perustuu kaavoihin, jotka lasketaan automaattisesti uudelleen, kun käyttäjä on vuorovaikutuksessa sovelluksen kanssa. Muuttujasta riippuvaiset kaavat päivittyvät automaattisesti, kun ne muuttuvat. Muuttujaa ei kuitenkaan päivitetä automaattisesti, jos **määritetty** -funktiolla käytetyn kaavan arvo muuttuu. Tämä edellyttää, että sovelluksen tekijä päivittää muuttujan manuaalisesti, mikä voi olla virhealtista ja vaikeampaa toisten ymmärtämiseksi. Ennen kuin käytät muuttujaa, tarkista [ymmärrä muuttujia](../working-with-variables.md).

## <a name="description"></a>Kuvaus
Yleiset muuttujat luodaan implisiittisesti, kun **Set**-funktiota käytetään. Eksplisiittistä määritystä ei tarvita. Jos poistat yleisen muuttujan kaikki **joukko** Funktiot, yleinen muuttuja lakkaa olemasta. Voit tyhjentää muuttujan määrittämällä sen arvon [ **tyhjän** funktion](function-isblank-isempty.md)tulokselle.

Voit nähdä muuttujien arvot, määritykset ja käyttö tavat PowerApps Studio **tiedosto-** valikon muuttujat-näkymässä.

Kuten myöhemmin tämän artikkelin esimerkeissä osoitetaan, yleiset muuttujat voivat sisältää useita erilaisia tietoja, kuten seuraavat:

* yksittäinen arvo
* tietue
* taulukko
* objektiviittaus
* mikä tahansa tulos kaavasta.

Yleinen muuttuja säilyttää arvonsa, kunnes sovellus suljetaan.  Kun sovellus on suljettu, yleisen muuttujan arvo menetetään, ja se on luotava uudelleen, kun sovellus ladataan uudelleen.

Yleiset muuttujat eivät voi käyttää samaa nimeä kuin olemassa oleva kokoelma tai ohjausobjekti.  Se voi käyttää samaa nimeä kuin jokin kontekstimuuttuja.  Tee näiden välille ero käyttämällä [selvitysoperaattoria](operators.md#disambiguation-operator).

**Set**-funktiolla ei ole palautusarvoa, ja voit käyttää sitä vain [toimintakaavan](../working-with-formulas-in-depth.md) sisällä.

## <a name="syntax"></a>Syntaksi
**Set**( *VariableName*, *Value* )

* *VariableName* – Pakollinen.  Luotavan tai päivitettävän yleisen muuttujan nimi.
* *Value* – Pakollinen.  Arvo, joka määritetään kontekstimuuttujalle.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Set(&nbsp;Counter,&nbsp;1&nbsp;)** |Luo yleisen muuttujan **Counter** tai muokkaa sitä ja asettaa sen arvoksi **1**. |**Counter**-arvo on **1**. Voit viitata kyseiseen muuttujaan käyttämällä kaavassa nimeä **Counter** missä tahansa näytössä. |
| **Set(&nbsp;Counter,&nbsp;2&nbsp;)** |Määrittää edellisen esimerkin yleisen muuttujan **Counter** arvoksi **2**. |**Counter**-arvo on **2**. |
| **Set(&nbsp;Counter,&nbsp;Counter + 1&nbsp;)** |Lisää 1:n edellisen esimerkin yleisen muuttujan **Counter**-arvoon, jolloin arvo on **3**. |**Counter**-arvo on **3**. |
| **Set(&nbsp;Name,&nbsp;”Lily” )** |Luo yleisen muuttujan **Name**tai muokkaa sitä ja asettaa sen arvoksi **Lily**. |**Name**-arvo on **Lily**. |
| **Set(&nbsp;Person,&nbsp;{&nbsp;Name:&nbsp;”Milton”, Address:&nbsp;”1&nbsp;Main&nbsp;St”&nbsp;} )** |Luo yleisen muuttujan **Person** tai muokkaa sitä ja asettaa sen arvon tietueeksi. Tietue sisältää kaksi saraketta, joiden nimet ovat **Name** ja **Address**. Sarakkeen **Name** arvo on **Milton** ja sarakkeen **Address** arvo on **1 Main St**. |**Person**-kohdalla on tietueen **{&nbsp;Name:&nbsp;”Milton”, Address:&nbsp;”1&nbsp;Main&nbsp;St”&nbsp;}** arvo.<br><br>Viittaa tähän tietueeseen kokonaisuutena nimellä **Person** tai tämän tietueen yksittäiseen sarakkeeseen seuraavasti: **Person.Name** tai **Person.Address**. |
| **Set(&nbsp;Person, Patch(&nbsp;Person,&nbsp;{Address:&nbsp;”2&nbsp;Main&nbsp;St”&nbsp;}&nbsp;)&nbsp;)** |Toimii **[Patch](function-patch.md)** -funktion kanssa yleisen muuttujan **Person** päivittämiseksi ja asettaa sarakkeen **Address** arvoksi **2 Main St**. |Muuttujan **Person**  arvo on nyt tietue **{&nbsp;Name:&nbsp;”Milton”, Address:&nbsp;”2&nbsp;Main&nbsp;St”&nbsp;}** . |


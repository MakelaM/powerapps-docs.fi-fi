---
title: Joukko-funktio | Microsoft Docs
description: PowerAppsin Joukko-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 06/29/2017
ms.author: gregli
ms.openlocfilehash: 1fdf6c92fb739f1293c90322b508b46f4ec5733e
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/07/2018
ms.locfileid: "37898026"
---
# <a name="set-function-in-powerapps"></a>PowerAppsin Joukko-funktio
Asettaa yleisen muuttujan arvon.

## <a name="overview"></a>Yleiskatsaus
Käytä **Joukko**-funktiota yleisen muuttujan arvon asettamiseen. Yleinen muuttuja säilyttää tilapäisesti tietoja, kuten montako kertaa käyttäjä on valinnut painikkeen tai tietotoiminnon tuloksen.  

Yleiset muuttujat ovat koko sovelluksen käytettävissä kaikissa sen näytöissä.  Tämä on yksinkertaisin muuttujatyyppi, ja se täyttää tarpeet useimmissa tapauksissa.  On myös olemassa kontekstimuuttujia, jotka toimivat yhdessä ruudussa, sekä kokoelmia, jotka mahdollistavat taulukoiden rivitason muokkaukset.  Katso lisätietoja näistä vaihtoehdoista aiheesta [Muuttujien käyttäminen](../working-with-variables.md).

PowerApps perustuu kaavoihin, jotka lasketaan automaattisesti uudelleen, kun käyttäjä on vuorovaikutuksessa sovelluksen kanssa.  Yleiset muuttujat eivät tarjoa tätä etua, ja ne voivat vaikeuttaa sovelluksesi laatimista ja ymmärtämistä.  Ennen kuin käytät yleistä muuttujaa, tutustu kohtaan [Muuttujien käyttäminen](../working-with-variables.md).

## <a name="description"></a>Kuvaus
Yleiset muuttujat luodaan implisiittisesti, kun **Joukko**-funktiota käytetään.  Eksplisiittinen määrittely ei ole välttämätön.  Jos poistat kaikki yleisen muuttujan **Joukko**-funktiot, yleinen muuttuja lakkaa olemasta.  Poista muuttujasarjan arvot määrittämällä sen arvoksi [**Tyhjä**-funktion](function-isblank-isempty.md) tulos.

Voit nähdä-muuttujien arvot, määritelmät ja käyttötarkoitukset Tiedosto-valikon Muuttujat-näkymässä luontiympäristössä.

Kuten myöhemmin tämän artikkelin esimerkeissä osoitetaan, yleiset muuttujat voivat sisältää useita erilaisia tietoja, kuten seuraavat:

* yksittäinen arvo
* tietue
* taulukko
* objektiviittaus
* mikä tahansa tulos kaavasta.

Yleinen muuttuja säilyttää arvonsa, kunnes sovellus suljetaan.  Kun sovellus on suljettu, yleisen muuttujan arvo menetetään, ja se on luotava uudelleen, kun sovellus ladataan uudelleen.

Yleiset muuttujat eivät voi käyttää samaa nimeä kuin olemassa oleva kokoelma tai ohjausobjekti.  Se voi käyttää samaa nimeä kuin jokin kontekstimuuttuja.  Tee näiden välille ero käyttämällä [selvitysoperaattoria](operators.md#disambiguation-operator).

**Joukko**-funktiolla ei ole palautusarvoa, ja voit käyttää sitä vain [toimintakaavan](../working-with-formulas-in-depth.md) sisällä.

## <a name="syntax"></a>Syntaksi
**Set**( *VariableName*, *Value* )

* *VariableName* – Pakollinen.  Luotavan tai päivitettävän yleisen muuttujan nimi.
* *Arvo* – Pakollinen.  Arvo, joka määritetään kontekstimuuttujalle.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Set(&nbsp;Counter,&nbsp;1&nbsp;)** |Luo yleisen muuttujan **Laskuri** tai muokkaa sitä ja asettaa sen arvoksi **1**. |**Laskuri**-arvo on **1**. Voit viitata kyseiseen muuttujaan käyttämällä kaavassa nimeä **Laskuri** missä tahansa näytössä. |
| **Set(&nbsp;Counter,&nbsp;2&nbsp;)** |Määrittää edellisen esimerkin yleisen muuttujan **Laskuri** arvoksi **2**. |**Laskuri**-arvo on **2**. |
| **Set(&nbsp;Counter,&nbsp;Counter + 1&nbsp;)** |Lisää 1:n edellisen esimerkin yleisen muuttujan **Laskuri**-arvoon, jolloin arvo on **3**. |**Laskuri**-arvo on **3**. |
| **Set(&nbsp;Name,&nbsp;”Lily” )** |Luo yleisen muuttujan **Nimi**tai muokkaa sitä ja asettaa sen arvoksi **Lily**. |**Nimi**-arvo on **Lily**. |
| **Set(&nbsp;Person,&nbsp;{&nbsp;Name:&nbsp;”Milton”, Address:&nbsp;”1&nbsp;Main&nbsp;St”&nbsp;} )** |Luo yleisen muuttujan **Henkilö** tai muokkaa sitä ja asettaa sen arvon tietueeksi. Tietue sisältää kaksi saraketta, joiden nimet ovat **Nimi** ja **Osoite**. Sarakkeen **Nimi** arvo on **Milton** ja sarakkeen **Osoite** arvo on **1 Main St**. |**Henkilö**llä on tietueen **{&nbsp;Name:&nbsp;”Milton”, Address:&nbsp;”1&nbsp;Main&nbsp;St”&nbsp;}** arvo.<br><br>Viittaa tähän tietueeseen kokonaisuutena nimellä **Henkilö** tai tämän tietueen yksittäiseen sarakkeeseen seuraavasti: **Person.Name** tai **Person.Address**. |
| **Set(&nbsp;Person, Patch(&nbsp;Person,&nbsp;{Address:&nbsp;”2&nbsp;Main&nbsp;St”&nbsp;}&nbsp;)&nbsp;)** |Toimii **[Ohjelmakorjaus](function-patch.md)**-funktion kanssa yleisen muuttujan **Henkilö** päivittämiseksi ja asettaa sarakkeen **Osoite** arvoksi **2 Main St**. |Muuttujan **Henkilö**  arvo on nyt tietue **{&nbsp;Name:&nbsp;”Milton”, Address:&nbsp;”2&nbsp;Main&nbsp;St”&nbsp;}**. |


---
title: Set-funktio | Microsoft Docs
description: PowerAppsin Set-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
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
ms.date: 06/29/2017
ms.author: gregli
ms.openlocfilehash: ef44d704d16892c7c37ac4fbf7c3eebc0ffcb966
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="set-function-in-powerapps"></a>PowerAppsin Set-funktio
Asettaa yleisen muuttujan arvon.

## <a name="overview"></a>Yleiskatsaus
Käytä **Set**-funktiota yleisen muuttujan arvon asettamiseen. Yleinen muuttuja säilyttää tilapäisesti tietoja, kuten montako kertaa käyttäjä on valinnut painikkeen tai tietotoiminnon tuloksen.  

Yleiset muuttujat ovat käytettävissä koko sovelluksilla kaikilla sen näytöillä.  Tämä on yksinkertaisin muuttujatyyppi ja se täyttää tarpeet useimmissa tapauksissa.  On myös olemassa kontekstimuuttujia, jotka toimivat yhdellä ruudulla sekä kokoelmia, jotka mahdollistavat taulukoiden rivitason muokkaukset.  Katso lisätietoja näistä vaihtoehdoista aiheesta [muuttujien käyttäminen](../working-with-variables.md).

PowerApps perustuu kaavoihin, jotka lasketaan automaattisesti uudelleen, kun käyttäjä on vuorovaikutuksessa sovelluksen kanssa.  Yleiset muuttujat eivät tarjoa tätä etua, ja ne voivat vaikeuttaa sovelluksesi laatimista ja ymmärtämistä.  Ennen kuin käytät yleistä muuttujaa, tutustu kohtaan [muuttujien käyttäminen](../working-with-variables.md).

## <a name="description"></a>Kuvaus
Yleiset muuttujat luodaan implisiittisesti, kun **Set**-funktiota käytetään.  Eksplisiittinen määrittely ei ole välttämätön.  Jos poistat kaikki yleisen muuttujan **Set**-funktiot, yleinen muuttuja lakkaa olemasta.  Poista muuttujasarjan arvot määrittämällä sen arvoksi [**Blank**-funktion](function-isblank-isempty.md) tulos.

Voit nähdä muuttujien arvot, määritelmät ja käyttötarkoitukset luontiympäristön Tiedosto-valikon Muuttujat-näkymässä.

Kuten myöhemmin tämän artikkelin esimerkeissä osoitetaan, yleiset muuttujat voivat sisältää useita monenlaisia tietoja, kuten seuraavat:

* yksittäinen arvo
* tietue
* taulukko
* objektiviittaus
* mikä tahansa tulos kaavasta

Yleinen muuttuja säilyttää arvonsa, kunnes sovellus suljetaan.  Kun sovellus on suljettu, yleisen muuttujan arvo menetetään, ja se on luotava uudelleen, kun sovellus ladataan uudelleen.

Yleiset muuttujat eivät voi käyttää samaa nimeä kuin olemassa oleva kokoelma tai ohjausobjekti.  Se voi käyttää samaa nimeä kuin jokin kontekstimuuttuja.  Tee näiden välille ero käyttämällä [selvitysoperaattoria](operators.md#disambiguation-operator).

**Set**-funktiolla ei ole palautusarvoa, ja voit käyttää sitä vain [toimintakaavan](../working-with-formulas-in-depth.md) sisällä.

## <a name="syntax"></a>Syntaksi
**Set**( *MuuttujanNimi*, *Arvo* )

* *MuuttujanNimi* – Pakollinen.  Luotavan tai päivitettävän yleisen muuttujan nimi.
* *Arvo* – Pakollinen.  Arvo, joka määritetään muuttujalle.

## <a name="examples"></a>Esimerkkejä
| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Set(&nbsp;Laskuri,&nbsp;1&nbsp;)** |Luo tai muokkaa yleisen muuttujan **Laskuri** ja asettaa sen arvoksi **1**. |Muuttujan **Laskuri** arvo on **1**. Voit viitata kyseisen muuttujan nimeen **Laskuri** kaavassa millä tahansa näytöllä. |
| **Set(&nbsp;Laskuri,&nbsp;2&nbsp;)** |Määrittää edellisen esimerkin yleisen muuttujan **Laskuri** arvoksi **2**. |Muuttujan **Laskuri** arvo on **2**. |
| **Set(&nbsp;Laskuri,&nbsp;Laskuri + 1&nbsp;)** |Lisää 1:n edellisen esimerkin yleisen muuttujan **Laskuri** arvoon, jolloin arvo on **3**. |Muuttujan **Laskuri** arvo on **3**. |
| **Set(&nbsp;Nimi,&nbsp;"Lily" )** |Luo tai muokkaa yleisen muuttujan **Nimi** ja asettaa sen arvoksi **Lily**. |Muuttujan **Nimi** arvo on **Lily**. |
| **Set(&nbsp;Henkilö,&nbsp;{&nbsp;Nimi:&nbsp;"Milton", Osoite:&nbsp;"1&nbsp;Main&nbsp;St"&nbsp;} )** |Luo tai muokkaa yleisen muuttujan **Henkilö** ja asettaa sen arvon tietueeksi. Tietue sisältää kaksi saraketta, joiden nimet ovat **Nimi** ja **Osoite**. Sarakkeen **Nimi** arvo on **Milton** ja sarakkeen **Osoite** arvo on **1 Main St**. |Muuttujan **Henkilö** arvo on tietue **{&nbsp;Nimi:&nbsp;"Milton", Osoite:&nbsp;"1&nbsp;Main&nbsp;St"&nbsp;}**.<br><br>Viittaa tähän tietueeseen kokonaisuutena nimellä **Henkilö** tai viittaa tämän tietueen yksittäiseen sarakkeeseen seuraavasti: **Henkilö.Nimi** tai **Henkilö.Osoite**. |
| **Set(&nbsp;Henkilö, Patch(&nbsp;Henkilö,&nbsp;{Osoite:&nbsp;"2&nbsp;Main&nbsp;St"&nbsp;}&nbsp;)&nbsp;)** |Toimii **[Patch](function-patch.md)**-funktion kanssa yleisen muuttujan **Henkilö** päivittämiseksi ja asettaa sarakkeen **Osoite** arvoksi **2 Main St**. |Muuttujan **Henkilö**  arvo on nyt tietue **{&nbsp;Nimi:&nbsp;"Milton", Osoite:&nbsp;"2&nbsp;Main&nbsp;St"&nbsp;}**. |


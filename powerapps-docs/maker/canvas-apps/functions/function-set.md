---
title: Set-funktio | Microsoft Docs
description: PowerAppsin Set-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/29/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 96b8b8276b385a49bd29be150b9a41ba08ba67ba
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42862814"
---
# <a name="set-function-in-powerapps"></a>PowerAppsin Set-funktio
Asettaa yleisen muuttujan arvon.

## <a name="overview"></a>Yleiskatsaus
Käytä **Set**-funktiota yleisen muuttujan arvon asettamiseen. Yleinen muuttuja säilyttää tilapäisesti tietoja, kuten montako kertaa käyttäjä on valinnut painikkeen tai tietotoiminnon tuloksen.  

Yleiset muuttujat ovat koko sovelluksen käytettävissä kaikissa sen näytöissä.  Tämä on yksinkertaisin muuttujatyyppi, ja se täyttää tarpeet useimmissa tapauksissa.  On myös olemassa kontekstimuuttujia, jotka toimivat yhdessä ruudussa, sekä kokoelmia, jotka mahdollistavat taulukoiden rivitason muokkaukset.  Katso lisätietoja näistä vaihtoehdoista aiheesta [Muuttujien käyttäminen](../working-with-variables.md).

PowerApps perustuu kaavoihin, jotka lasketaan automaattisesti uudelleen, kun käyttäjä on vuorovaikutuksessa sovelluksen kanssa.  Yleiset muuttujat eivät tarjoa tätä etua, ja ne voivat vaikeuttaa sovelluksesi laatimista ja ymmärtämistä.  Ennen kuin käytät yleistä muuttujaa, tutustu kohtaan [Muuttujien käyttäminen](../working-with-variables.md).

## <a name="description"></a>Kuvaus
Yleiset muuttujat luodaan implisiittisesti, kun **Set**-funktiota käytetään.  Eksplisiittinen määrittely ei ole välttämätön.  Jos poistat kaikki yleisen muuttujan **Set**-funktiot, yleinen muuttuja lakkaa olemasta.  Poista muuttujasarjan arvot määrittämällä sen arvoksi [**Blank**-funktion](function-isblank-isempty.md) tulos.

Voit nähdä-muuttujien arvot, määritelmät ja käyttötarkoitukset Tiedosto-valikon Muuttujat-näkymässä luontiympäristössä.

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
| **Set(&nbsp;Person, Patch(&nbsp;Person,&nbsp;{Address:&nbsp;”2&nbsp;Main&nbsp;St”&nbsp;}&nbsp;)&nbsp;)** |Toimii **[Patch](function-patch.md)**-funktion kanssa yleisen muuttujan **Person** päivittämiseksi ja asettaa sarakkeen **Address** arvoksi **2 Main St**. |Muuttujan **Person**  arvo on nyt tietue **{&nbsp;Name:&nbsp;”Milton”, Address:&nbsp;”2&nbsp;Main&nbsp;St”&nbsp;}**. |


---
title: UpdateContext-funktio | Microsoft Docs
description: Viitetiedot sekä syntaksi ja esimerkkejä PowerAppsin UpdateContext-funktiolle
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/08/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7750ad239df87e99d2321be20293b64153110fc1
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71991821"
ms.PowerAppsDecimalTransform: true
---
# <a name="updatecontext-function-in-powerapps"></a>UpdateContext-funktio PowerAppsissa
Luo tai päivittää [kontekstimuuttujat](../working-with-variables.md#use-a-context-variable) nykyisessä näytössä.

## <a name="overview"></a>Yleiskatsaus
Käytä **UpdateContext** funktiota kontekstimuuttujan luomiseen. Kontekstimuuttuja säilyttää tilapäisesti tietoja, kuten montako kertaa käyttäjä on valinnut painikkeen tai tietotoiminnon tuloksen.

Kontekstimuuttujat on rajoitettu näyttöä varten, mikä tarkoittaa, ettet voi muodostaa kaavaa, joka viittaa toisessa näytössä olevaan kontekstimuuttujaan. Jos olet käyttänyt toisenlaista ohjelmointityökalua, voit ajatella kontekstimuuttujaa samanlaisena kuin paikallista muuttujaa.  Käytä [**määritä** funktio](function-set.md) -toimintoa, kun käytät muuttujia, jotka ovat käytettävissä kaikkialla sovelluksessa.  

PowerApps perustuu kaavoihin, jotka lasketaan automaattisesti uudelleen, kun käyttäjä on vuorovaikutuksessa sovelluksen kanssa.  Kontekstimuuttujat eivät tarjoa tätä etua, ja ne voivat vaikeuttaa sovelluksesi laatimista ja ymmärtämistä.  Ennen kuin käytät kontekstimuuttujaa, tutustu kohtaan [muuttujien käyttäminen](../working-with-variables.md).

## <a name="description"></a>Kuvaus
Voit luoda tai päivittää kontekstimuuttujan välittämällä yksittäisen [tietueen](../working-with-tables.md#records) **UpdateContext**-funktiolle. Määritä kullekin tietueelle [sarakkeen](../working-with-tables.md#columns) nimi, joka määrittää tai vastaa muuttujan nimeä, ja arvo, jonka haluat määrittää kyseiselle muuttujalle.

* Jos määrität muuttujan nimen, jonka olet määrittänyt aikaisemmin, **UpdateContext** asettaa muuttujan arvoksi määrittämäsi arvon.
* Jos määrität muuttujan nimen, jota ei ole vielä olemassa, **UpdateContext** luo muuttujan tällä nimellä ja asettaa tälle muuttujalle määrittämäsi arvon.
* Jos olet aiemmin määrittänyt muuttujan, mutta et määritä sitä tässä nimenomaisessa **UpdateContext**-kaavassa, sen arvo pysyy samana.

Kontekstimuuttujia luodaan implisiittisesti käyttämällä **UpdateContext**- tai [**Navigate**-funktiota](function-navigate.md).  Eksplisiittinen määrittely ei ole välttämätön.  Jos poistat kaikki **UpdateContext**- ja **Navigate**-viittaukset kontekstimuuttujaan, kyseisen kontekstimuuttujan olemassaolo päättyy.  Poista muuttujasarjan arvot määrittämällä sen arvoksi [**Blank**-funktion](function-isblank-isempty.md) tulos.

Voit nähdä-muuttujien arvot, määritelmät ja käyttötarkoitukset Tiedosto-valikon Muuttujat-näkymässä luontiympäristössä.

Voit viitata kontekstimuuttujaan kaavassa käyttämällä muuttujan sarakkeen nimeä. Esimerkiksi, **UpdateContext( { ShowLogo: true } )** luo kontekstimuuttujan, jonka nimi on **ShowLogo**, ja asettaa sen arvoksi **true**. Voit sitten käyttää tämän kontekstimuuttujan arvoa käyttämällä kaavassa nimeä **ShowLogo**.  Voit kirjoittaa **ShowLogo**n kaavaksi kuvan hallinnan **Visible**-ominaisuudelle ja näyttää tai piilottaa tämän ohjausobjektin sen perusteella, onko kontekstimuuttujan arvo **true** vai **false**.

Kuten myöhemmin tämän artikkelin esimerkeissä osoitetaan, kontekstimuuttujat voivat sisältää useita monenlaisia tietoja, kuten seuraavat:

* yksittäinen arvo
* tietue
* taulukko
* objektiviittaus
* mikä tahansa tulos kaavasta

Kontekstimuuttuja säilyttää arvonsa, kunnes sovellus on suljettu.  Jos määrität kontekstimuuttujan ja määrität sen arvon jossakin tietyssä näytössä, tieto säilyy muuttumattomana, vaikka käyttäjä siirtyisikin eri näyttöön.  Kun sovellus on suljettu, kontekstimuuttujan arvo menetetään, ja se on luotava uudelleen, kun sovellus on ladattu uudelleen.  

Jokainen kontekstimuuttuja rajoittuu näyttöön. Jos haluat määrittää kontekstimuuttujan yhdessä näytössä ja muokata kyseistä muuttujaa toisesta näytöstä, sinun täytyy muodostaa kaava, joka perustuu **[Navigate](function-navigate.md)** -funktioon.  Vaihtoehtoisesti voit käyttää yleistä muuttujaa.

**UpdateContext**-funktiolla ei ole palautusarvoa, ja voit käyttää sitä vain [toimintakaavan](../working-with-formulas-in-depth.md) sisällä.

## <a name="syntax"></a>Syntaksi
**UpdateContext**( *UpdateRecord* )

* *UpdateRecord*  – Pakollinen. Tietue, joka sisältää vähintään yhden sarakkeen nimen ja arvon tälle sarakkeelle. Kontekstimuuttuja luodaan tai päivitetään jokaiselle sarakkeelle ja arvolle, jonka määrität.

**Updatecontext**({ *kontekstimuuttuja1*: *Arvo1* [; *kontekstimuuttuja2*: *Arvo2* [;...] ] } )

* *ContextVariable1*  – Pakollinen.  Luotavan tai päivitettävän kontekstimuuttujan nimi.
* *Value1*  – Pakollinen.  Arvo, joka määritetään kontekstimuuttujalle.
* *Kontekstimuuttuja2*: *Arvo2*,...-valinnainen. Lisää kontekstimuuttujia, jotka laaditaan tai joiden arvot päivitetään.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **UpdateContext( {&nbsp;Counter:&nbsp;1&nbsp;} )** |Luo tai muokkaa kontekstimuuttujan **Counter** ja asettaa sen arvoksi **1**. |**Counter**-arvo on **1**. Voit viitata kyseisen muuttujan nimeen **Counter** kaavassa. |
| **UpdateContext( {&nbsp;Counter:&nbsp;2&nbsp;} )** |Määrittää kontekstimuuttujan **Counter** arvoksi edellisessä esimerkissä **2**. |**Counter**-arvo on **2**. |
| **UpdateContext( {&nbsp;Name:&nbsp;"Lily";&nbsp;Score:&nbsp;10&nbsp;} )** |Luo tai muokkaa kontekstimuuttujat **Name** ja **Score** ja asettaa niiden arvoiksi vastaavasti **Lily** ja **10**. |Muuttujan **Name** arvo on **Lily** ja muuttujan **Score** arvo on **10**. |
| **UpdateContext( {&nbsp;Person:&nbsp;{&nbsp;Name:&nbsp;"Milton"; Address:&nbsp;"1&nbsp;Main&nbsp;St"&nbsp;}&nbsp;} )** |Luo tai muokkaa kontekstimuuttujan **Person** ja asettaa sen tietueeksi. Tietue sisältää kaksi saraketta, joiden nimet ovat **Name** ja **Address**. Sarakkeen **Name** arvo on **Milton** ja sarakkeen **Address** arvo on **1 Main St**. |Muuttujan **Person** arvo on tietue **{&nbsp;Name:&nbsp;”Milton”; Address:&nbsp;”1&nbsp;Main&nbsp;St”&nbsp;}&nbsp;}** .<br><br>Viittaa tähän tietueeseen kokonaisuutena nimellä **Person** tai tämän tietueen yksittäiseen sarakkeeseen seuraavasti: **Person.Name** tai **Person.Address**. |
| **UpdateContext ({&nbsp;Person: Patch (&nbsp;Person; &nbsp; {Osoite: &nbsp; "2 @ no__t-3Main @ no__t-4St" &nbsp;} &nbsp;)} &nbsp;)** |Toimii **[Patch](function-patch.md)** -funktion kanssa kontekstimuuttujan **Person** päivittämiseksi ja asettaa sarakkeen **Address** arvoksi **2 Main St**. |Muuttujan **Person** arvo on nyt tietue **{&nbsp;Person:&nbsp;”Milton”; Address:&nbsp;”2&nbsp;Main&nbsp;St”&nbsp;}&nbsp;}** . |

### <a name="step-by-step-example"></a>Vaiheittainen esimerkki
1. Anna oletusnäytön nimeksi **Lähde**, lisää toinen näyttö ja anna sille nimeksi **Kohde**.
2. Lisää näytössä **Lähde** kaksi painiketta ja määritä niiden **[Text](../controls/properties-core.md)** -ominaisuudet niin, että toisessa lukee **Englanti** ja toisessa lukee **Espanja**.
3. Aseta **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi **Englanti**-painikkeelle seuraava lauseke:<br>**Navigate(Target; ScreenTransition.Fade; {Language:"Englanti"})**
4. Aseta **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi **Espanja**-painikkeelle seuraava lauseke:<br>**Navigate(Target; ScreenTransition.Fade; {Language:"Espanja"})**
5. Lisää näytössä **Kohde** otsikko ja määritä sen **[Text](../controls/properties-core.md)** -ominaisuudeksi seuraava lauseke:<br>**If(Kieli=”Englanti”; ”Hello!”; ”Hola!”)**
6. Valitse **Kohde**-näytössä **Shapes** **Lisää**-välilehdeltä ja valitse sitten taaksepäin osoittava nuoli.
7. Määritä taaksepäin osoittavan nuolen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>**Navigate(Source; ScreenTransition.Fade)**
8. Paina **Lähde**-näytössä F5-näppäintä ja valitse sitten painike molemmille kielille.

    **Kohde**-näytössä otsikko näkyy kielellä, joka vastaa valitsemaasi painiketta.
9. Valitse taaksepäin osoittava nuoli palataksesi **Lähde**-näyttöön ja valitse sitten toisen kielen painike.

    **Kohde**-näytössä otsikko näkyy kielellä, joka vastaa valitsemaasi painiketta.
10. Palaa oletustyötilaan painamalla ESC-näppäintä.

[Toinen esimerkki](../add-screen-context-variables.md)


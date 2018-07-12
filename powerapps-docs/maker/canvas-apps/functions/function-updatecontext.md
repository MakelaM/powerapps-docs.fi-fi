---
title: UpdateContext-funktio | Microsoft Docs
description: Viitetiedot sekä syntaksi ja esimerkkejä PowerAppsin UpdateContext-funktiolle
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/08/2015
ms.author: gregli
ms.openlocfilehash: e7da24eec1a85a1d57ab83476734639ef0f5dd25
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/07/2018
ms.locfileid: "37898072"
---
# <a name="updatecontext-function-in-powerapps"></a>UpdateContext-funktio PowerAppsissa
Luo tai päivittää [kontekstimuuttujat](../working-with-variables.md#create-a-context-variable) nykyisessä näytössä.

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

Jokainen kontekstimuuttuja rajoittuu näyttöön. Jos haluat määrittää kontekstimuuttujan yhdessä näytössä ja muokata kyseistä muuttujaa toisesta näytöstä, sinun täytyy muodostaa kaava, joka perustuu **[Navigate](function-navigate.md)**-funktioon.  Vaihtoehtoisesti voit käyttää yleistä muuttujaa.

**UpdateContext**-funktiolla ei ole palautusarvoa, ja voit käyttää sitä vain [toimintakaavan](../working-with-formulas-in-depth.md) sisällä.

## <a name="syntax"></a>Syntaksi
**UpdateContext**( *PäivitysTietue* )

* *PäivitysTietue* vaaditaan. Tietue, joka sisältää vähintään yhden sarakkeen nimen ja arvon tälle sarakkeelle. Kontekstimuuttuja luodaan tai päivitetään jokaiselle sarakkeelle ja arvolle, jonka määrität.

**UpdateContext**( { *Kontekstimuuttuja1*: *Arvo1* [, *Kontekstimuuttuja2*: *Arvo2* [, ... ] ] } )

* *Kontekstimuuttuja1* vaaditaan.  Luotavan tai päivitettävän kontekstimuuttujan nimi.
* *Arvo1* vaaditaan.  Arvo, joka määritetään kontekstimuuttujalle.
* *Kontekstimuuttuja2*: *Arvo2*,... – valinnainen. Lisää kontekstimuuttujia, jotka laaditaan tai joiden arvot päivitetään.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **UpdateContext( {&nbsp;Laskuri:&nbsp;1&nbsp;} )** |Luo tai muokkaa kontekstimuuttujan **Laskuri** ja asettaa sen arvoksi **1**. |Muuttujan **Laskuri** arvo on **1**. Voit viitata kyseisen muuttujan nimeen **Laskuri** kaavassa. |
| **UpdateContext( {&nbsp;Laskuri:&nbsp;2&nbsp;} )** |Määrittää kontekstimuuttujan **Laskuri** arvoksi edellisessä esimerkissä **2**. |Muuttujan **Laskuri** arvo on **2**. |
| **UpdateContext( {&nbsp;Nimi:&nbsp;”Lily”,&nbsp;Pistemäärä:&nbsp;10&nbsp;} )** |Luo tai muokkaa kontekstimuuttujat **Nimi** ja **Pistemäärä** ja asettaa niiden arvoiksi vastaavasti **Lily** ja **10**. |Muuttujan **Nimi** arvo on **Lily** ja muuttujan **Pistemäärä** arvo on **10**. |
| **UpdateContext( {&nbsp;Henkilö:&nbsp;{&nbsp;Nimi:&nbsp;”Milton”, Osoite:&nbsp;”1&nbsp;Main&nbsp;St”&nbsp;}&nbsp;} )** |Luo tai muokkaa kontekstimuuttujan **Henkilö** ja asettaa sen tietueeksi. Tietue sisältää kaksi saraketta, joiden nimet ovat **Nimi** ja **Osoite**. Sarakkeen **Nimi** arvo on **Milton** ja sarakkeen **Osoite** arvo on **1 Main St**. |Muuttujan **Henkilö** arvo on tietue **{&nbsp;Nimi:&nbsp;”Milton”, Osoite:&nbsp;”1&nbsp;Main&nbsp;St”&nbsp;}&nbsp;}**.<br><br>Viittaus tähän tietueeseen kokonaisuutena nimellä **Henkilö** tai viittaus tämän tietueen yksittäiseen sarakkeeseen seuraavasti: **Henkilö.Nimi** tai **Henkilö.Osoite**. |
| **UpdateContext( {&nbsp;Henkilö: Patch(&nbsp;Henkilö,&nbsp;{Osoite:&nbsp;”2&nbsp;Main&nbsp;St”&nbsp;}&nbsp;) }&nbsp;)** |Toimii **[Patch](function-patch.md)**-funktion kanssa kontekstimuuttujan **Henkilö** päivittämiseksi ja asettaa sarakkeen **Osoite** arvoksi **2 Main St**. |Muuttujan **Henkilö** arvo on nyt tietue **{&nbsp;Henkilö:&nbsp;”Milton”, Osoite:&nbsp;”2&nbsp;Main&nbsp;St”&nbsp;}&nbsp;}**. |

### <a name="step-by-step-example"></a>Vaiheittainen esimerkki
1. Anna oletusnäytön nimeksi **Lähde**, lisää toinen näyttö ja anna sille nimeksi **Kohde**.
2. Lisää näytössä **Lähde** kaksi painiketta ja määritä niiden **[Text](../controls/properties-core.md)**-ominaisuudet niin, että toisessa lukee **Englanti** ja toisessa lukee **Espanja**.
3. Aseta **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi **Englanti**-painikkeelle seuraava lauseke:<br>**Navigate(Target, ScreenTransition.Fade, {Kieli:”Englanti”})**
4. Aseta **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi **Espanja**-painikkeelle seuraava lauseke:<br>**Navigate(Target, ScreenTransition.Fade, {Kieli:”Espanja”})**
5. Lisää näytössä **Kohde** otsikko ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuudeksi seuraava lauseke:<br>**If(Kieli=”Englanti”, ”Hello!”, ”Hola!”)**
6. Valitse **Kohde**-näytössä **Shapes** **Lisää**-välilehdeltä ja valitse sitten taaksepäin osoittava nuoli.
7. Määritä taaksepäin osoittavan nuolen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:<br>**Navigate(Source, ScreenTransition.Fade)**
8. Paina **Lähde**-näytössä F5-näppäintä ja valitse sitten painike molemmille kielille.

    **Kohde**-näytössä otsikko näkyy kielellä, joka vastaa valitsemaasi painiketta.
9. Valitse taaksepäin osoittava nuoli palataksesi **Lähde**-näyttöön ja valitse sitten toisen kielen painike.

    **Kohde**-näytössä otsikko näkyy kielellä, joka vastaa valitsemaasi painiketta.
10. Palaa oletustyötilaan painamalla ESC-näppäintä.

[Toinen esimerkki](../add-screen-context-variables.md)


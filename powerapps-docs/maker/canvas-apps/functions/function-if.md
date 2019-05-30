---
title: If- ja Switch-funktiot | Microsoft Docs
description: PowerAppsin If- ja Switch-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/24/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 40ac3089d3563d220ddac29197b0902f4de88a25
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61562895"
---
# <a name="if-and-switch-functions-in-powerapps"></a>If- ja Switch-funktiot PowerAppsissa
Määrittää, onko mikään joukon ehdoista tosi (**If**) tai vastaako kaavan tulos mitään joukon arvoa (**Switch**), ja palauttaa sitten tuloksen tai suorittaa toiminnon.

## <a name="description"></a>Kuvaus
**If**-funktio testaa yhtä tai useampaa ehtoa, kunnes **tosi**-tulos löydetään. Jos tällainen tulos löytyy, palautetaan sitä vastaava arvo. Jos tällaista tulosta ei löydy, palautetaan oletusarvo. Kummassakin tapauksessa palautettu arvo voi olla näytettävä merkkijono, laskettava kaava tai mikä tahansa muu tulos.

**Switch**-funktio laskee kaavan ja määrittää, vastaako tulos mitään määrittämäsi jakson arvoa. Jos vastaavuus löytyy, palautetaan sitä vastaava arvo. Jos vastaavuutta ei löydy, palautetaan oletusarvo. Kummassakin tapauksessa palautettu arvo voi olla näytettävä merkkijono, laskettava kaava tai mikä tahansa muu tulos.

**If** ja **Switch** ovat hyvin samankaltaisia, mutta kannattaa käyttää tilanteeseesi parhaiten sopivaa funktiota:

* Käytä **If**-funktiota, jos lasket yksittäistä ehtoa. Funktion yleisin syntaksi on **If**( *Condition*, *ThenResult*, *DefaultResult* ), joka antaa tavallisen ”jos…  niin… muuten…” -mallin, jota käytetään muissa ohjelmointityökaluissa.
* Käytä **If**-funktiota, jos lasket useita toisiinsa liittymättömiä ehtoja. PowerAppsissa (toisin kuin Microsoft Excelissä) voit määrittää useita ehtoja ilman sisäkkäisiä **If**-kaavoja.
* Käytä **Switch**-funktiota, jos lasket yksittäistä ehtoa useita mahdollisia vastaavuuksia vastaan. Voit käyttää tässä tapauksessa myös **If**-funktiota, mutta kaava pitää toistaa jokaista mahdollista vastaavuutta kohden.

Voit käyttää molempia funktioita [toimintakaavoissa](../working-with-formulas-in-depth.md) kahden tai useamman toiminnon välillä haarautumiseen. Vain yksi haara käynnistää toiminnon. Ehdot ja vastaavuudet lasketaan järjestyksessä ja ne pysähtyvät, jos ehto on **tosi** tai vastaavuus löytyy.

*Blank* palautetaan, jos yksikään ehto ei ole **tosi**, jos vastaavuuksia ei löydetä tai jos et määrittänyt oletustulosta.

## <a name="syntax"></a>Syntaksi
**If**( *Condition*, *ThenResult* [, *DefaultResult* ] )<br>**If**( *Condition1*, *ThenResult1* [, *Condition2*, *ThenResult2*, ... [ , *DefaultResult* ] ] )

* *Condition(s)* – Pakollinen. Kaavat, jotka testaavat arvoa **tosi**. Tällaiset kaavat sisältävät usein [vertailuoperaattoreita](operators.md) (kuten **<**, **>** ja **=**) ja testausfunktioita kuten **[IsBlank](function-isblank-isempty.md)** ja **[IsEmpty](function-isblank-isempty.md)**.
* *ThenResult(s)* – Pakollinen. Vastaava arvo, joka palautetaan arvon **tosi** antavalle ehdolle.
* *DefaultResult* – Valinnainen. Palautettava arvo, jos mikään ehto ei anna arvoa **tosi**.  Jos et määritä tätä argumenttia, palautetaan arvo *tyhjä*.

**Switch**( *Formula*, *Match1*, *Result1* [, *Match2*, *Result2*, ... [, *DefaultResult* ] ] )

* *Formula* – Pakollinen. Kaava, jolla vastaavuuksia lasketaan.  Kaava lasketaan vain kerran.
* *Match(s)* – Pakollinen. Arvot, joita verrataan *Formulan* tulokseen.  Jos tarkka vastaavuus löydetään, vastaava *Result* palautetaan.
* *Result(s)* – Pakollinen. Vastaava arvo, joka palautetaan, kun tarkka vastaavuus löydetään.
* *DefaultResult* – Valinnainen. Arvo, joka palautetaan, jos tarkkaa vastaavuutta ei löydy. Jos et määritä tätä argumenttia, palautetaan arvo *tyhjä*.

## <a name="examples"></a>Esimerkkejä
### <a name="values-in-formulas"></a>Arvot kaavoissa
Seuraavissa esimerkeissä **Slider**-ohjausobjektin (nimeltä **Slider1**) arvo on **25**.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **If( Slider1.Value&nbsp;=&nbsp;25, "Result1" )** |Ehto on **tosi**, ja vastaava tulos palautetaan. |"Result1" |
| **If( Slider1.Value&nbsp;=&nbsp;25, "Result1", "Result2" )** |Ehto on **tosi**, ja vastaava tulos palautetaan. |"Result1" |
| **If( Slider1.Value&nbsp;>&nbsp;1000, "Result1" )** |Ehto on **epätosi**, eikä *DefaultResult*-arvoa ole annettu. |*tyhjä* |
| **If( Slider1.Value&nbsp;>&nbsp;1000, "Result1", "Result2" )** |Ehto on **epätosi**, ja *DefaultResult* on annettu, joten se palautetaan. |"Result2" |
| **If( Slider1.Value&nbsp;=&nbsp;25, "Result1", Slider1.Value&nbsp;>&nbsp;0, "Result2" )** |Ensimmäinen ehto on **tosi**, ja vastaava tulos palautetaan. Myös toinen ehto on **tosi**, mutta sitä ei lasketa, koska se esiintyy argumenttiluettelossa myöhemmin kuin toinen ehto, joka antaa arvon **tosi**. |"Result1" |
| **If( IsBlank(&nbsp;Slider1.Value&nbsp;), "Result1", IsNumeric(&nbsp;Slider1.Value&nbsp;), "Result2" )** |Ensimmäinen ehto on **epätosi**, koska liukusäädin ei ole *tyhjä*. Toinen ehto on **tosi**, koska liukusäätimen arvo on numero. Vastaava tulos palautetaan. |"Result2" |
| **If( Slider1.Value&nbsp;>&nbsp;1000, "Result1", Slider1.Value&nbsp;>&nbsp;50, "Result2", "Result3")** |Sekä ensimmäisen että toisen ehdon arvo on **epätosi**, mutta *OletusTulos* on annettu, joten se palautetaan. |”Tulos3” |
| **Switch( Slider1.Value, 25, "Result1" )** |Liukusäätimen arvo vastaa ensimmäistä tarkastettavaa arvoa, joten vastaava tulos palautetaan. |"Result1" |
| **Switch( Slider1.Value, 20, "Result1", 25, "Result2", 30, "Result3" )** |Liukusäätimen arvo vastaa toista tarkastettavaa arvoa, joten vastaava tulos palautetaan. |"Result2" |
| **Switch( Slider1.Value, 20, "Result1", 10, "Result2", 0, "Result3", "DefaultResult" )** |Liukusäätimen arvo ei vastaa mitään tarkistettavaa arvoa.  *DefaultResult* on annettu, joten se palautetaan. |"DefaultResult" |

### <a name="branching-in-behavior-formulas"></a>Haarautuminen toimintakaavioissa
Seuraavissa esimerkeissä **[tekstisyöte](../controls/control-text-input.md)**-ohjausobjektilla nimeltä **Etunimi** on arvo ”John”.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **If( ! IsBlank( Etunimi.Text ), Navigate(&nbsp;Screen1, ScreenTransition.None ) )** |Ehto on **tosi**, joten **[Navigate](function-navigate.md)**-funktio suoritetaan. Voit testata, onko pakollinen lomakekenttä täytetty käyttämällä **[IsBlank](function-isblank-isempty.md)**-funktiota.  Jos **Etunimi** on [tyhjä](function-isblank-isempty.md), kaavalla ei ole vaikutusta. |**tosi**<br><br>Näytöksi vaihdetaan **Screen1**. |
| **If( IsBlank( Etunimi.Text ), Navigate(&nbsp;Screen1, ScreenTransition.None ), Back() )** |Ilman **!**-operaattoria ehto on **epätosi**, joten **[Navigate](function-navigate.md)**-funktiota ei suoriteta. Annettu *OletusTulos* on **[Back](function-navigate.md)**-funktio, joten se suoritetaan. |**tosi**<br><br>Näyttö siirtyy takaisin aiemmin näytettyyn näyttöön. |
| **Switch( Etunimi.Text, "Carlos", Navigate(&nbsp;Screen1, ScreenTransition.None ), "Kirstin", Navigate( Screen2, ScreenTransition.None ), "John", Navigate( Screen3, ScreenTransition.None ) )** |**Etunimi.Text**-arvoa verrataan nimiin ”Carlos”, ”Kirstin” ja ”John” tässä järjestyksessä. Vastaavuus löytyy nimellä ”John”, joten sovellus siirtyy näyttöön **Screen3**. |**tosi**<br><br>Näytöksi vaihdetaan **Screen3**. |

### <a name="step-by-step"></a>Vaihe vaiheelta
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti ja anna sille nimeksi **Text1**, jos tämä ei ole sen oletusnimi.
2. Kirjoita kohtaan **Text1** teksti **30**.
3. Lisää **Selite**-ohjausobjekti ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **If( Value(Text1.Text) < 20, "Tilaa PALJON enemmän!", Value(Text1.Text) < 40, "Tilaa enemmän!", Text1.Text )**
   
    **Selite**-ohjausobjektissa näytetään **Tilaa enemmän!** koska kohdan **Text1** arvo on suurempi kuin 20 mutta pienempi kuin 40.
4. Kirjoita kohtaan **Text1** teksti **15**.
   
    **Selite**-ohjausobjektissa näytetään **Tilaa PALJON enemmän!** koska kohdan **Text1** arvo on pienempi kuin 20.
5. Kirjoita kohtaan **Text1** teksti **50**.
   
    **Selite**-ohjausobjektissa näytetään kirjoittamasi arvo, koska se on suurempi kuin 40.


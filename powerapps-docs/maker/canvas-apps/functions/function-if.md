---
title: If- ja Switch-funktiot | Microsoft Docs
description: PowerAppsin If- ja Switch-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkkejä
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
ms.date: 04/24/2017
ms.author: gregli
ms.openlocfilehash: 9254eaf63d816fc8ac9890026f74bdeaeaa9b1a4
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="if-and-switch-functions-in-powerapps"></a>If- ja Switch-funktiot PowerAppsissa
Määrittää, onko mikään joukon ehdoista tosi (**If**) tai vastaako kaavan tulos mitään joukon arvoa (**Switch**), ja palauttaa sitten tuloksen tai suorittaa toiminnon.

## <a name="description"></a>Kuvaus
**If**-funktio testaa yhtä tai useampaa ehtoa, kunnes **tosi**-tulos löydetään. Jos tällainen tulos löytyy, palautetaan sitä vastaava arvo. Jos tällaista tulosta ei löydy, palautetaan oletusarvo. Kummassakin tapauksessa palautettu arvo voi olla näytettävä merkkijono, laskettava kaava tai mikä tahansa muu tulos.

**Switch**-funktio laskee kaavan ja määrittää, vastaako tulos mitään määrittämäsi jakson arvoa. Jos vastaavuus löytyy, palautetaan sitä vastaava arvo. Jos vastaavuutta ei löydy, palautetaan oletusarvo. Kummassakin tapauksessa palautettu arvo voi olla näytettävä merkkijono, laskettava kaava tai mikä tahansa muu tulos.

**If** ja **Switch** ovat hyvin samankaltaisia, mutta kannattaa käyttää tilanteeseesi parhaiten sopivaa funktiota:

* Käytä **If**-funktiota, jos lasket yksittäistä ehtoa. Funktion yleisin syntaksi on **If**( *Ehto*, *SittenTulos*, *OletusTulos* ), joka antaa tavallisen ”jos…  niin… muuten…” -mallin, jota käytetään muissa ohjelmointityökaluissa.
* Käytä **If**-funktiota, jos lasket useita toisiinsa liittymättömiä ehtoja. PowerAppsissa (toisin kuin Microsoft Excelissä) voit määrittää useita ehtoja ilman sisäkkäisiä **If**-kaavoja.
* Käytä **Switch**-funktiota, jos lasket yksittäistä ehtoa useita mahdollisia vastaavuuksia vastaan. Voit käyttää tässä tapauksessa myös **If**-funktiota, mutta kaava pitää toistaa jokaista mahdollista vastaavuutta kohden.

Voit käyttää molempia funktioita [toimintakaavoissa](../working-with-formulas-in-depth.md) kahden tai useamman toiminnon välillä haarautumiseen. Vain yksi haara käynnistää toiminnon. Ehdot ja vastaavuudet lasketaan järjestyksessä ja ne pysähtyvät, jos ehto on **tosi** tai vastaavuus löytyy.

*Tyhjä* palautetaan, jos yksikään ehto ei ole **tosi**, jos vastaavuuksia ei löydetä tai jos et määrittänyt oletustulosta.

## <a name="syntax"></a>Syntaksi
**If**( *Ehto*, *SittenTulos* [, *OletusTulos* ] )<br>**If**( *Ehto1*, *SittenTulos1* [, *Ehto2*, *SittenTulos2*, ... [ , *OletusTulos* ] ] )

* *Ehdot* – Pakollinen. Kaavat, jotka testaavat arvoa **tosi**. Tällaiset kaavat sisältävät usein [vertailuoperaattoreita](operators.md) (kuten **<**, **>** ja **=**) ja testausfunktioita kuten **[IsBlank](function-isblank-isempty.md)** ja **[IsEmpty](function-isblank-isempty.md)**.
* *SittenTulokset* – Pakollinen. Vastaava arvo, joka palautetaan arvon **tosi** antavalle ehdolle.
* *OletusTulos* – Valinnainen. Palautettava arvo, jos mikään ehto ei anna arvoa **tosi**.  Jos et määritä tätä argumenttia, palautetaan arvo *tyhjä*.

**Switch**( *Kaava*, *Vastaavuus1*, *Tulos1* [, *Vastaavuus2*, *Tulos2*, ... [, *OletusTulos* ] ] )

* *Kaava* – Pakollinen. Kaava, jolla vastaavuuksia lasketaan.  Kaava lasketaan vain kerran.
* *Vastaavuudet* – Pakollinen. Arvot, joita verrataan *Kaavan* tulokseen.  Jos tarkka vastaavuus löydetään, vastaava *Tulos* palautetaan.
* *Tulokset* – Pakollinen. Vastaava arvo, joka palautetaan, kun tarkka vastaavuus löydetään.
* *OletusTulos* – Valinnainen. Arvo, joka palautetaan, jos tarkkaa vastaavuutta ei löydy. Jos et määritä tätä argumenttia, palautetaan arvo *tyhjä*.

## <a name="examples"></a>Esimerkkejä
### <a name="values-in-formulas"></a>Arvot kaavoissa
Seuraavissa esimerkeissä **Liukusäätimen** (nimeltä **Liukusäädin1**) arvo on **25**.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **If( Liukusäädin1.Value&nbsp;=&nbsp;25, "Tulos1" )** |Ehto on **tosi**, ja vastaava tulos palautetaan. |”Tulos1” |
| **If( Liukusäädin1.Value&nbsp;=&nbsp;25, "Tulos1", "Tulos2" )** |Ehto on **tosi**, ja vastaava tulos palautetaan. |”Tulos1” |
| **If( Liukusäädin1.Value&nbsp;>&nbsp;1000, "Tulos1" )** |Ehto on **epätosi**, eikä *OletusTulosta* ole annettu. |*tyhjä* |
| **If( Liukusäädin1.Value&nbsp;>&nbsp;1000, "Tulos1", "Tulos2" )** |Ehto on **epätosi**, ja *OletusTulos* on annettu, joten se palautetaan. |”Tulos2” |
| **If( Liukusäädin1.Value&nbsp;=&nbsp;25, "Tulos1", Liukusäädin1.Value&nbsp;>&nbsp;0, "Tulos2" )** |Ensimmäinen ehto on **tosi**, ja vastaava tulos palautetaan. Myös toinen ehto on **tosi**, mutta sitä ei lasketa, koska se esiintyy argumenttiluettelossa myöhemmin kuin toinen ehto, joka antaa arvon **tosi**. |”Tulos1” |
| **If( IsBlank(&nbsp;Liukusäädin1.Value&nbsp;), "Tulos1", IsNumeric(&nbsp;Liukusäädin1.Value&nbsp;), "Tulos2" )** |Ensimmäinen ehto on **epätosi**, koska liukusäädin ei ole *tyhjä*. Toinen ehto on **tosi**, koska liukusäätimen arvo on numero. Vastaava tulos palautetaan. |”Tulos2” |
| **If( Liukusäädin1.Value&nbsp;>&nbsp;1000, "Tulos1", Liukusäädin1.Value&nbsp;>&nbsp;50, "Tulos2", "Tulos3")** |Sekä ensimmäisen että toisen ehdon arvo on **epätosi**, mutta *OletusTulos* on annettu, joten se palautetaan. |”Tulos3” |
| **Switch( Liukusäädin1.Value, 25, "Tulos1" )** |Liukusäätimen arvo vastaa ensimmäistä tarkastettavaa arvoa, joten vastaava tulos palautetaan. |”Tulos1” |
| **Switch( Liukusäädin1.Value, 20, "Tulos1", 25, "Tulos2", 30, "Tulos3" )** |Liukusäätimen arvo vastaa toista tarkastettavaa arvoa, joten vastaava tulos palautetaan. |”Tulos2” |
| **Switch( Liukusäädin1.Value, 20, "Tulos1", 10, "Tulos2", 0, "Tulos3", "OletusTulos" )** |Liukusäätimen arvo ei vastaa mitään tarkistettavaa arvoa.  *OletusTulos* on annettu, joten se palautetaan. |”OletusTulos” |

### <a name="branching-in-behavior-formulas"></a>Haarautuminen toimintakaavioissa
Seuraavissa esimerkeissä **[tekstisyöte](../controls/control-text-input.md)**-ohjausobjektilla nimeltä **Etunimi** on arvo ”John”.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **If( ! IsBlank( Etunimi.Text ), Navigate(&nbsp;Screen1, ScreenTransition.None ) )** |Ehto on **tosi**, joten **[Navigate](function-navigate.md)**-funktio suoritetaan. Voit testata, onko pakollinen lomakekenttä täytetty käyttämällä **[IsBlank](function-isblank-isempty.md)**-funktiota.  Jos **Etunimi** on [tyhjä](function-isblank-isempty.md), kaavalla ei ole vaikutusta. |**tosi**<br><br>Näytöksi vaihdetaan **Screen1**. |
| **If( IsBlank( Etunimi.Text ), Navigate(&nbsp;Screen1, ScreenTransition.None ), Back() )** |Ilman **!**-operaattoria ehto on **epätosi**, joten **[Navigate](function-navigate.md)**-funktiota ei suoriteta. Annettu *OletusTulos* on **[Back](function-navigate.md)**-funktio, joten se suoritetaan. |**tosi**<br><br>Näyttö siirtyy takaisin aiemmin näytettyyn näyttöön. |
| **Switch( Etunimi.Text, "Carlos", Navigate(&nbsp;Screen1, ScreenTransition.None ), "Kirstin", Navigate( Screen2, ScreenTransition.None ), "John", Navigate( Screen3, ScreenTransition.None ) )** |**Etunimi.Text**-arvoa verrataan nimiin ”Carlos”, ”Kirstin” ja ”John” tässä järjestyksessä. Vastaavuus löytyy nimellä ”John”, joten sovellus siirtyy näyttöön **Screen3**. |**tosi**<br><br>Näytöksi vaihdetaan **Screen3**. |

### <a name="step-by-step"></a>Vaihe vaiheelta
1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti ja anna sille nimeksi **Teksti1**, jos tämä ei ole sen oletusnimi.
2. Kirjoita kohtaan **Teksti1** teksti **30**.
3. Lisää **Selite**-ohjausobjekti ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
   **If( Value(Teksti1.Text) < 20, "Tilaa PALJON enemmän!", Value(Teksti1.Text) < 40, "Tilaa enemmän!", Teksti1.Text )**
   
    **Selite**-ohjausobjektissa näytetään **Tilaa enemmän!** koska kohdan **Teksti1** arvo on suurempi kuin 20 mutta pienempi kuin 40.
4. Kirjoita kohtaan **Teksti1** teksti **15**.
   
    **Selite**-ohjausobjektissa näytetään **Tilaa PALJON enemmän!** koska kohdan **Teksti1** arvo on pienempi kuin 20.
5. Kirjoita kohtaan **Teksti1** teksti **50**.
   
    **Selite**-ohjausobjektissa näytetään kirjoittamasi arvo, koska se on suurempi kuin 40.


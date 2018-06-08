---
title: Back- ja Navigate-funktio | Microsoft Docs
description: Tietoa PowerAppsin Navigate- ja Back-funktiosta, mukaan lukien syntaksi ja esimerkkejä
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
ms.openlocfilehash: ecb8b8176dd8489866a5ca88a6b69e1520c3ad69
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31834454"
---
# <a name="back-and-navigate-functions-in-powerapps"></a>Back- ja Navigate-funktio PowerAppsissa
Nämä funktiot vaihtavat näytettävää näyttöä.

## <a name="overview"></a>Yleiskatsaus
Useimmissa sovelluksissa on useita näyttöjä.  Voit vaihtaa näytettävää näyttöä **Back**- ja **Navigate** -funktioilla. Aseta esimerkiksi jonkin painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi kaava, joka sisältää **Navigate**-funktion, jos haluat hakea näkyviin toisen näytön, kun käyttäjä valitsee kyseisen painikkeen. Voit määrittää kaavaan siirtymäefektin, kuten **Häivytys**, joka määrittää, miltä siirtymä näytöltä toiselle näyttää.  

**Back** ja **Navigate** vaihtavat vain näytettävää näyttöä. Näytöt, joita ei näytetä, toimivat edelleen taustalla. Voit rakentaa kaavoja, jotka viittaavat toisella näytöllä olevien ohjausobjektien ominaisuuksiin. Käyttäjä voi esimerkiksi muuttaa liukusäätimen arvoa yhdellä näytöllä, siirtyä sen jälkeen toiselle näytölle, joka käyttää kyseistä arvoa jossakin kaavassa, ja nähdä, kuinka tämä vaikuttaa uuteen näyttöön.  Sen jälkeen käyttäjä voi siirtyä takaisin alkuperäiseen näyttöön ja nähdä, että liukusäädin säilyttää arvonsa.

Myös [kontekstimuuttujat](../working-with-variables.md#create-a-context-variable) säilytetään, kun käyttäjä siirtyy näyttöjen välillä. **Navigate**-funktiolla voit asettaa näytölle yhden tai useamman kontekstimuuttujan, jotka kaava näyttää – tämä on ainoa tapa asettaa kontekstimuuttuja näytön ulkopuolelta. Tällä menetelmällä voit välittää näytölle parametrejä. Jos olet käyttänyt jotakin toista ohjelmointityökalua, tämä menetelmä vastaa parametrien välittämistä toimintosarjoille.

## <a name="description"></a>Kuvaus
### <a name="back"></a>Back
**Back**-funktio näyttää viimeksi avatun näytön. Tälle funktiolle ei määritetä argumentteja.

### <a name="navigate"></a>Navigate
Määritä ensimmäiseksi argumentiksi avattavan näytön nimi.  

 Määritä toiseksi argumentiksi, kuinka vanhasta näytöstä siirrytään uuteen:

| Siirtymän argumentti | Kuvaus |
| --- | --- |
| **ScreenTransition.Cover** |Uusi näyttö liukuu näkyviin ja peittää nykyisen näytön. |
| **ScreenTransition.Fade** |Vanha näyttö häivytetään, ja uusi näyttö tulee näkyviin. |
| **ScreenTransition.None** |Vanha näyttö vaihdetaan nopeasti uuteen. |
| **ScreenTransition.UnCover** |Vanha näyttö liukuu pois näkyvistä uuden näytön päältä. |

Voit käyttää **Navigate**-funktiota uuden näytön kontekstimuuttujien luomiseen tai päivittämiseen. Valinnaisena kolmantena argumenttina voidaan välittää [tietue](../working-with-tables.md#records), joka sisältää kontekstimuuttujan nimen [sarakkeen](../working-with-tables.md#columns) nimenä ja uuden arvon kontekstimuuttujalle.  Tietue on sama kuin se, jota käytetään **[UpdateContext](function-updatecontext.md)**-funktion kanssa.

Voit tehdä lisää muutoksia siirtymän aikana asettamalla vanhan näytön **[OnHidden](../controls/control-screen.md)**-ominaisuuden ja uuden näytön **[OnVisible](../controls/control-screen.md)**-ominaisuuden tai kummatkin ominaisuudet. **App.ActiveScreen**-ominaisuus päivitetään muutoksen mukaisesti.

**Back** palauttaa normaalisti arvon **tosi**, mutta se palauttaa arvon **epätosi**, jos käyttäjä on ensimmäisessä avatussa näytössä eikä edellistä näyttöä sen vuoksi ole.  **Navigate** palauttaa normaalisti arvon **tosi**, mutta se palauttaa arvon **epätosi**, jos jossakin sen argumentissa on ongelma.

Näitä funktioita voidaan käyttää vain [toimintakaavassa](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaksi
**Back**()

**Navigate**( *Näyttö*, *Siirtymä* [, *UpdateContextRecord* ] )

* *Screen* – Pakollinen. Avattava näyttö.
* *Transition* – Pakollinen.  Nykyisestä näytöstä uuteen siirtymisen visuaalinen efekti. Katso tämän argumentin kelvolliset arvot tämän aiheen aiemmasta osasta.
* *UpdateContextRecord* – Valinnainen.  Tietue, joka sisältää vähintään yhden sarakkeen nimen ja arvon jokaiselle sarakkeelle. Tämä tietue päivittää uuden näytön kontekstimuuttujat, jos se välitetään **[UpdateContext](function-updatecontext.md)**-funktiolle.

## <a name="examples"></a>Esimerkkejä
| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Navigate( Lisätiedot, ScreenTransition.None )** |Näyttää **Lisätiedot**-näytön ilman siirtymäefektiä tai muutoksia kontekstimuuttujan arvoon. |**Lisätiedot**-näyttö ilmestyy nopeasti. |
| **Navigate( Lisätiedot, ScreenTransition.Fade )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä.  Mitään kontekstimuuttujan arvoa ei muuteta. |Nykyinen näyttö häivytetään ja **Lisätiedot**-näyttö näytetään. |
| **Navigate( Lisätiedot, ScreenTransition.Fade, {&nbsp;ID:&nbsp;12&nbsp;} )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä ja päivittää **ID**-kontekstimuuttujan arvoksi **12**. |Uusi näyttö häivytetään, **Lisätiedot**-näyttö näytetään ja kyseisen näytön kontekstimuuttujan **ID**-arvoksi asetetaan **12**. |
| **Navigate( Lisätiedot, ScreenTransition.Fade, {&nbsp;ID:&nbsp;12&nbsp;,&nbsp;Shade:&nbsp;Color.Red&nbsp;} )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä. Päivittää **ID**-kontekstimuuttujan arvoksi **12** ja päivittää **Shade**-kontekstimuuttujan arvoksi **Color.Red**. |Nykyinen näyttö häivytetään ja **Lisätiedot**-näyttö näytetään. **Lisätiedot**-ruudun **ID**-kontekstimuuttujan arvoksi asetetaan **12** ja **Shade**-kontekstimuuttujan arvoksi asetetaan **Color.Red**. Jos asetat jonkin **Lisätiedot**-näytön ohjausobjektin **Fill**-ominaisuudeksi **Shade**, kyseinen ohjausobjekti näytetään punaisena. |

### <a name="step-by-step"></a>Vaiheittainen esimerkki
1. Anna oletusnäytön nimeksi **OletusNäyttö**, lisää siihen otsikko ja aseta otsikon **[Text](../controls/properties-core.md)**-ominaisuudeksi **Oletus**.
2. Lisää näyttö ja anna sille nimeksi **LisäNäyttö**.
3. Lisää **LisäNäyttö**-näytölle otsikko ja aseta sen **[Text](../controls/properties-core.md)**-ominaisuudeksi **Lisä**.
4. Lisää **LisäNäyttö**-näytölle painike ja aseta sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä funktio:<br>**Navigate(OletusNäyttö, ScreenTransition.Fade)**
5. Paina **LisäNäyttö**-näytöllä F5-näppäintä ja valitse painike.<br>**OletusNäyttö** näytetään.

[Toinen esimerkki](../add-screen-context-variables.md)


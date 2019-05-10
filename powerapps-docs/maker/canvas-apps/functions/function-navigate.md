---
title: Back- ja Navigate-funktio | Microsoft Docs
description: Tietoa PowerAppsin Navigate- ja Back-funktiosta, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0033d0a2d7473e6aaeac1e8533f62873e0d2f49a
ms.sourcegitcommit: c52c1869510a9a37d9f7b127e06f07583529588b
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/28/2019
ms.locfileid: "64670933"
---
# <a name="back-and-navigate-functions-in-powerapps"></a>Back- ja Navigate-funktio PowerAppsissa
Nämä funktiot vaihtavat näytettävää näyttöä.

## <a name="overview"></a>Yleiskatsaus
Useimmissa sovelluksissa on useita näyttöjä.  Voit vaihtaa näytettävää näyttöä **Back**- ja **Navigate** -funktioilla. Aseta esimerkiksi jonkin painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi kaava, joka sisältää **Navigate**-funktion, jos haluat hakea näkyviin toisen näytön, kun käyttäjä valitsee kyseisen painikkeen. Voit määrittää kaavaan siirtymäefektin, kuten **Häivytys**, joka määrittää, miltä siirtymä näytöltä toiselle näyttää.  

**Back** ja **Navigate** vaihtavat vain näytettävää näyttöä. Näytöt, joita ei näytetä, toimivat edelleen taustalla. Voit rakentaa kaavoja, jotka viittaavat toisella näytöllä olevien ohjausobjektien ominaisuuksiin. Käyttäjä voi esimerkiksi muuttaa liukusäätimen arvoa yhdellä näytöllä, siirtyä sen jälkeen toiselle näytölle, joka käyttää kyseistä arvoa jossakin kaavassa, ja nähdä, kuinka tämä vaikuttaa uuteen näyttöön.  Sen jälkeen käyttäjä voi siirtyä takaisin alkuperäiseen näyttöön ja nähdä, että liukusäädin säilyttää arvonsa.

Myös [kontekstimuuttujat](../working-with-variables.md#use-a-context-variable) säilytetään, kun käyttäjä siirtyy näyttöjen välillä. **Navigate**-funktiolla voit asettaa näytölle yhden tai useamman kontekstimuuttujan, jotka kaava näyttää – tämä on ainoa tapa asettaa kontekstimuuttuja näytön ulkopuolelta. Tällä menetelmällä voit välittää näytölle parametrejä. Jos olet käyttänyt jotakin toista ohjelmointityökalua, tämä menetelmä vastaa parametrien välittämistä toimintosarjoille.

## <a name="description"></a>Kuvaus
### <a name="back"></a>Back
**Back**-funktio näyttää viimeksi avatun näytön. Tälle funktiolle ei määritetä argumentteja.

### <a name="navigate"></a>Navigate
Määritä ensimmäiseksi argumentiksi avattavan näytön nimi.  

 Määritä toiseksi argumentiksi, kuinka vanhasta näytöstä siirrytään uuteen:

| Siirtymän argumentti | Kuvaus | Esittely |
| --- | --- | --- |
| **ScreenTransition.Cover** |Uusi näyttö liukuu, siirtää oikealle vasemmalle ja peittää nykyisen näytön. | ![näytön siirtymä kannen animaatio](media/function-navigate/cover.gif) |
| **ScreenTransition.CoverRight** |Uusi näyttö diat näkymään, siirtäminen vasemmalta oikealle, että se kattaa nykyisen näytön. | ![näytön siirtymä kannen juuri animaatio](media/function-navigate/coverright.gif) |
| **ScreenTransition.Fade** |Nykyinen pois, jotta uusi näyttö tulee näkyviin näytön-Häivytys. | ![näytön siirtymä fade animaatio](media/function-navigate/fade.gif) |
| **ScreenTransition.None** (oletus) |Uuden näytön korvaa nopeasti nykyisessä näytössä. | ![näytön siirtymä ei mitään animaatio](media/function-navigate/none.gif) |
| **ScreenTransition.UnCover** | Nykyinen näyttö liukuu pois näkyvistä, siirtää oikealle vasemmalle, löytää uuden näytön. | ![näytön siirtymä paljastaa animaatio](media/function-navigate/uncover.gif) |
| **ScreenTransition.UnCoverRight** | Nykyinen näyttö diat pois näkyvistä, siirtäminen vasemmalta oikealle löytää uuden näytön. | ![näytön siirtymä paljastaa juuri animaatio](media/function-navigate/uncoverright.gif) |

Voit käyttää **Navigate**-funktiota uuden näytön kontekstimuuttujien luomiseen tai päivittämiseen. Valinnaisena kolmantena argumenttina voidaan välittää [tietue](../working-with-tables.md#records), joka sisältää kontekstimuuttujan nimen [sarakkeen](../working-with-tables.md#columns) nimenä ja uuden arvon kontekstimuuttujalle.  Tietue on sama kuin se, jota käytetään **[UpdateContext](function-updatecontext.md)**-funktion kanssa.

Voit tehdä lisää muutoksia siirtymän aikana asettamalla vanhan näytön **[OnHidden](../controls/control-screen.md)**-ominaisuuden ja uuden näytön **[OnVisible](../controls/control-screen.md)**-ominaisuuden tai kummatkin ominaisuudet. **App.ActiveScreen**-ominaisuus päivitetään muutoksen mukaisesti.

**Back** palauttaa normaalisti arvon **tosi**, mutta se palauttaa arvon **epätosi**, jos käyttäjä on ensimmäisessä avatussa näytössä eikä edellistä näyttöä sen vuoksi ole.  **Navigate** palauttaa normaalisti arvon **tosi**, mutta se palauttaa arvon **epätosi**, jos jossakin sen argumentissa on ongelma.

Näitä funktioita voidaan käyttää vain [toimintakaavassa](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaksi
**Back**()

**Siirry**( *näytön* [, *siirtymä* [, *UpdateContextRecord* ]])

* *Screen* – Pakollinen. Avattava näyttö.
* *Siirtymä* – valinnainen.  Nykyisestä näytöstä uuteen siirtymisen visuaalinen efekti. Katso tämän argumentin kelvolliset arvot tämän aiheen aiemmasta osasta. Oletusarvo on **ei mitään**.
* *UpdateContextRecord* – Valinnainen.  Tietue, joka sisältää vähintään yhden sarakkeen nimen ja arvon jokaiselle sarakkeelle. Tämä tietue päivittää uuden näytön kontekstimuuttujat, jos se välitetään **[UpdateContext](function-updatecontext.md)**-funktiolle.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Navigate (lisätiedot)** |Näyttää **Lisätiedot**-näytön ilman siirtymäefektiä tai muutoksia kontekstimuuttujan arvoon. |**Lisätiedot**-näyttö ilmestyy nopeasti. |
| **Navigate( Lisätiedot, ScreenTransition.Fade )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä.  Mitään kontekstimuuttujan arvoa ei muuteta. |Nykyinen näyttö häivytetään ja **Lisätiedot**-näyttö näytetään. |
| **Navigate( Lisätiedot, ScreenTransition.Fade, {&nbsp;ID:&nbsp;12&nbsp;} )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä ja päivittää **ID**-kontekstimuuttujan arvoksi **12**. |Uusi näyttö häivytetään, **Lisätiedot**-näyttö näytetään ja kyseisen näytön kontekstimuuttujan **ID**-arvoksi asetetaan **12**. |
| **Navigate( Lisätiedot, ScreenTransition.Fade, {&nbsp;ID:&nbsp;12&nbsp;,&nbsp;Shade:&nbsp;Color.Red&nbsp;} )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä. Päivittää **ID**-kontekstimuuttujan arvoksi **12** ja päivittää **Shade**-kontekstimuuttujan arvoksi **Color.Red**. |Nykyinen näyttö häivytetään ja **Lisätiedot**-näyttö näytetään. **Lisätiedot**-ruudun **ID**-kontekstimuuttujan arvoksi asetetaan **12** ja **Shade**-kontekstimuuttujan arvoksi asetetaan **Color.Red**. Jos asetat jonkin **Lisätiedot**-näytön ohjausobjektin **Fill**-ominaisuudeksi **Shade**, kyseinen ohjausobjekti näytetään punaisena. |

### <a name="step-by-step"></a>Vaiheittainen esimerkki
1. Anna oletusnäytön nimeksi **OletusNäyttö**, lisää siihen otsikko ja aseta otsikon **[Text](../controls/properties-core.md)**-ominaisuudeksi **Oletus**.
2. Lisää näyttö ja anna sille nimeksi **LisäNäyttö**.
3. Lisää **LisäNäyttö**-näytölle otsikko ja aseta sen **[Text](../controls/properties-core.md)**-ominaisuudeksi **Lisä**.
4. Lisää **LisäNäyttö**-näytölle painike ja aseta sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä funktio:<br>**Navigate(OletusNäyttö, ScreenTransition.Fade)**
5. Paina **LisäNäyttö**-näytöllä F5-näppäintä ja valitse painike.<br>**Oletusnäyttö** fade siirtymän tulee näkyviin.

[Toinen esimerkki](../add-screen-context-variables.md)


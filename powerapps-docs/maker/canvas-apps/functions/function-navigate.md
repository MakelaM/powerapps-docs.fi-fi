---
title: Back- ja Navigate-funktio | Microsoft Docs
description: Tietoa PowerAppsin Navigate- ja Back-funktiosta, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/16/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e57cc541c753ff3f24f66a78c6e30d6e5683b41a
ms.sourcegitcommit: 57dfad065318263e162e949e26b5c2684ba0dccb
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2019
ms.locfileid: "65828167"
ms.PowerAppsDecimalTransform: true
---
# <a name="back-and-navigate-functions-in-powerapps"></a>Back- ja Navigate-funktio PowerAppsissa

Nämä funktiot vaihtavat näytettävää näyttöä.

## <a name="overview"></a>Yleiskatsaus

Useimmissa sovelluksissa on useita näyttöjä.  Voit vaihtaa näytettävää näyttöä **Back**- ja **Navigate** -funktioilla. Aseta esimerkiksi jonkin painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi kaava, joka sisältää **Navigate**-funktion, jos haluat hakea näkyviin toisen näytön, kun käyttäjä valitsee kyseisen painikkeen. Voit määrittää kaavaan siirtymäefektin, kuten **Häivytys**, joka määrittää, miltä siirtymä näytöltä toiselle näyttää.  

**Back** ja **Navigate** vaihtavat vain näytettävää näyttöä. Näytöt, joita ei näytetä, toimivat edelleen taustalla. Voit luoda kaavoja, jotka viittaavat muihin näyttöihin ohjausobjektien ominaisuudet. Käyttäjä voi esimerkiksi yhdessä näytössä liukusäätimen arvo muuttuu, siirry eri näyttö, joka käyttää tätä arvoa kaavassa ja varmistaa, miten se vaikuttaa siihen, mitä tapahtuu uuden näytön. Käyttäjä voi sitten siirtyä takaisin alkuperäiseen näyttöön ja vahvista, että liukusäädin arvonsa.

Myös [kontekstimuuttujat](../working-with-variables.md#use-a-context-variable) säilytetään, kun käyttäjä siirtyy näyttöjen välillä. **Navigate**-funktiolla voit asettaa näytölle yhden tai useamman kontekstimuuttujan, jotka kaava näyttää – tämä on ainoa tapa asettaa kontekstimuuttuja näytön ulkopuolelta. Tällä menetelmällä voit välittää näytölle parametrejä. Jos olet käyttänyt jotakin toista ohjelmointityökalua, tämä menetelmä vastaa parametrien välittämistä toimintosarjoille.

Voidaan käyttää vain funktioista [toimintakaavassa](../working-with-formulas-in-depth.md).

## <a name="navigate"></a>Navigate

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

**Siirry** palauttaa normaalisti arvon **true** mutta se palaa **false** Jos virheen.

## <a name="back"></a>Back

**Takaisin** -funktio palauttaa, joka viimeksi tuli näyttöön.

Kunkin **Navigate** puhelun, sovellus seuraa, jotka olivat näytön ja siirtymän. Voit käyttää peräkkäisten **takaisin** kutsuja palata kokonaan näyttöön, jotka olivat, kun käyttäjä käynnistää sovelluksen.

Kun **takaisin** oletusarvon mukaan käytetään funktio suoritetaan, käänteinen siirtymä. Jos näyttöön ominaisuudelta kautta **CoverRight** siirtymän **takaisin** käyttää **UnCover** (joka on vasemmalle) palautettavien.  **Häivytettävä** ja **ei mitään** ovat omia inverses. Valinnainen argumentti välittää **takaisin** pakottaa tietyn siirtymän.

**Takaisin** palauttaa normaalisti arvon **true** , mutta se palauttaa **false** Jos käyttäjä ei ole siirtyi toiseen näyttöön sovelluksen käynnistämisen jälkeen.

## <a name="syntax"></a>Syntaksi

**Takaisin**([ *siirtymä* ])

* *Siirtymä* – valinnainen. Käytä nykyisestä näytöstä ja Edellinen näyttö välillä visuaalinen siirtymä. Viittaavat tälle argumentille aiemmin tässä ohjeaiheessa kelvollisten arvojen luettelo. Siirtymä, jonka kautta näytön palauttaa on oletusarvoisesti siirtymän, jonka kautta vaikutti käänteisen.

**Siirry**( *näytön* [; *siirtymä* [; *UpdateContextRecord* ]])

* *Screen* – Pakollinen. Avattava näyttö.
* *Siirtymä* – valinnainen.  Nykyisestä näytöstä uuteen siirtymisen visuaalinen efekti. Katso tämän argumentin kelvolliset arvot tämän aiheen aiemmasta osasta. Oletusarvo on **ei mitään**.
* *UpdateContextRecord* – Valinnainen.  Tietue, joka sisältää vähintään yhden sarakkeen nimen ja arvon jokaiselle sarakkeelle. Tämä tietue päivittää uuden näytön kontekstimuuttujat, jos se välitetään **[UpdateContext](function-updatecontext.md)**-funktiolle.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Navigate (lisätiedot)** |Näyttää **Lisätiedot**-näytön ilman siirtymäefektiä tai muutoksia kontekstimuuttujan arvoon. |**Lisätiedot**-näyttö ilmestyy nopeasti. |
| **Navigate( Lisätiedot; ScreenTransition.Fade )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä.  Mitään kontekstimuuttujan arvoa ei muuteta. |Nykyinen näyttö häivytetään ja **Lisätiedot**-näyttö näytetään. |
| **Navigate( Lisätiedot; ScreenTransition.Fade; {&nbsp;ID:&nbsp;12&nbsp;} )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä ja päivittää **ID**-kontekstimuuttujan arvoksi **12**. |Uusi näyttö häivytetään, **Lisätiedot**-näyttö näytetään ja kyseisen näytön kontekstimuuttujan **ID**-arvoksi asetetaan **12**. |
| **Navigate( Lisätiedot; ScreenTransition.Fade; {&nbsp;ID:&nbsp;12&nbsp;;&nbsp;Shade:&nbsp;Color.Red&nbsp;} )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä. Päivittää **ID**-kontekstimuuttujan arvoksi **12** ja päivittää **Shade**-kontekstimuuttujan arvoksi **Color.Red**. |Nykyinen näyttö häivytetään ja **Lisätiedot**-näyttö näytetään. **Lisätiedot**-ruudun **ID**-kontekstimuuttujan arvoksi asetetaan **12** ja **Shade**-kontekstimuuttujan arvoksi asetetaan **Color.Red**. Jos asetat jonkin **Lisätiedot**-näytön ohjausobjektin **Fill**-ominaisuudeksi **Shade**, kyseinen ohjausobjekti näytetään punaisena. |
| **Back()** | Näyttää edellisen näytön, jossa oletusarvon palautuksen siirtymä. | Näyttää edellisen näytön käänteinen siirtymä siirtymän, jonka kautta nykyisessä näytössä ominaisuudelta kautta. |
| **Edellinen (ScreenTransition.Cover)** |  Näyttää edellisen näytön kanssa **kattaa** siirtymä. | Näyttää edellisen näytön kautta **kattaa** siirtymä riippumatta siitä, jonka kautta nykyisessä näytössä ominaisuudelta siirtymä. |

### <a name="step-by-step"></a>Vaiheittainen esimerkki

1. Luo tyhjä sovellus.

1. Lisää toinen näyttö siihen.

    Sovellus sisältää kaksi tyhjä näyttöä: **Screen1** ja **Screen2**.

1. Määritä **Täytä** ominaisuuden **Screen2** arvon `Gray`.

1. Valitse **Screen2**, Lisää painike ja määritä sen **[OnSelect](../controls/properties-core.md)** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Navigate( Screen1; ScreenTransition.Cover )
    ```

1. Kun pidät alhaalla **Alt** avaimen, valitse painike.

    **Screen1** näkyy kautta, joka kattaa vasemmalle siirtyminen valkoisella taustalla.

1. Valitse **Screen1**, Lisää painike ja määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-comma
    Back()
    ```

1. Kun pidät alhaalla **Alt** avaimen, valitse painike.

    Toisessa näytössä näkyy harmaa tausta kautta siirtymää, jota ristiriitojen ratkaisutavan oikealle (käänteisen **kattaa**).

1. Valitse kutakin näyttöä toistuvasti epäonnistumisten edestakaisin painiketta.

[Toinen esimerkki](../add-screen-context-variables.md)

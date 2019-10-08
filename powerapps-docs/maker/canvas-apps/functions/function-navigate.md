---
title: Back- ja Navigate-funktio | Microsoft Docs
description: Tietoa PowerAppsin Navigate- ja Back-funktiosta, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/16/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8f63321b128214d14cd2f4e521d7cc1b85c7b98f
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984495"
ms.PowerAppsDecimalTransform: true
---
# <a name="back-and-navigate-functions-in-powerapps"></a>Back- ja Navigate-funktio PowerAppsissa

Nämä funktiot vaihtavat näytettävää näyttöä.

## <a name="overview"></a>Yleiskatsaus

Useimmissa sovelluksissa on useita näyttöjä.  Voit vaihtaa näytettävää näyttöä **Back**- ja **Navigate** -funktioilla. Aseta esimerkiksi jonkin painikkeen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi kaava, joka sisältää **Navigate**-funktion, jos haluat hakea näkyviin toisen näytön, kun käyttäjä valitsee kyseisen painikkeen. Voit määrittää kaavaan siirtymäefektin, kuten **Häivytys**, joka määrittää, miltä siirtymä näytöltä toiselle näyttää.  

**Back** ja **Navigate** vaihtavat vain näytettävää näyttöä. Näytöt, joita ei näytetä, toimivat edelleen taustalla. Voit luoda kaavoja, jotka viittaavat ohjaus objektien ominaisuuksiin muissa näytöissä. Käyttäjä voi esimerkiksi muuttaa liuku säätimen arvoa yhdessä näytössä, siirtyä eri näyttöön, joka käyttää kyseistä arvoa kaavassa, ja selvittää, miten se vaikuttaa siihen, mitä uudessa näytössä tapahtuu. Käyttäjä voi sitten siirtyä takaisin alkuperäiseen näyttöön ja vahvistaa, että liuku säädin on säilyttänyt arvonsa.

Myös [kontekstimuuttujat](../working-with-variables.md#use-a-context-variable) säilytetään, kun käyttäjä siirtyy näyttöjen välillä. **Navigate**-funktiolla voit asettaa näytölle yhden tai useamman kontekstimuuttujan, jotka kaava näyttää – tämä on ainoa tapa asettaa kontekstimuuttuja näytön ulkopuolelta. Tällä menetelmällä voit välittää näytölle parametrejä. Jos olet käyttänyt jotakin toista ohjelmointityökalua, tämä menetelmä vastaa parametrien välittämistä toimintosarjoille.

Voit käyttää kumpaa tahansa toimintoa vain [toiminta kaavan](../working-with-formulas-in-depth.md)puitteissa.

## <a name="navigate"></a>Navigate

Määritä ensimmäiseksi argumentiksi avattavan näytön nimi.  

 Määritä toiseksi argumentiksi, kuinka vanhasta näytöstä siirrytään uuteen:

| Siirtymän argumentti | Kuvaus | Esittely |
| --- | --- | --- |
| **ScreenTransition.Cover** |Uusi näyttö liukuu näkymään ja siirtyy oikealta vasemmalle, jotta se kattaa nykyisen näytön. | ![näytön siirtymän kannen animaatio](media/function-navigate/cover.gif) |
| **ScreenTransition. CoverRight** |Uusi näyttö liukuu näkyviin ja siirtyy vasemmalle oikealle, jolloin se kattaa nykyisen näytön. | ![näytön siirtymän kannen oikea animaatio](media/function-navigate/coverright.gif) |
| **ScreenTransition.Fade** |Nykyinen näyttö poistuu, jolloin uusi näyttö tulee näkyviin. | ![näytön siirtymisen häivytys animaatio](media/function-navigate/fade.gif) |
| **Screentransition. None** (oletus) |Uusi näyttö korvaa nykyisen näytön nopeasti. | ![näytön siirtymän None-animaatio](media/function-navigate/none.gif) |
| **ScreenTransition.UnCover** | Nykyinen näyttö liukuu pois näkymästä, siirtyy oikealle vasemmalle ja paljastaa uuden näytön. | ![näytön siirtymisen paljastaen animaatio](media/function-navigate/uncover.gif) |
| **ScreenTransition. UnCoverRight** | Nykyinen näyttö liukuu pois näkymästä ja siirtyy vasemmalle oikealle, jotta uusi näyttö voidaan paljastaa. | ![näytön siirtyminen paljasta oikeaa animaatiota](media/function-navigate/uncoverright.gif) |

Voit käyttää **Navigate**-funktiota uuden näytön kontekstimuuttujien luomiseen tai päivittämiseen. Valinnaisena kolmantena argumenttina voidaan välittää [tietue](../working-with-tables.md#records), joka sisältää kontekstimuuttujan nimen [sarakkeen](../working-with-tables.md#columns) nimenä ja uuden arvon kontekstimuuttujalle.  Tietue on sama kuin se, jota käytetään **[UpdateContext](function-updatecontext.md)** -funktion kanssa.

Voit tehdä lisää muutoksia siirtymän aikana asettamalla vanhan näytön **[OnHidden](../controls/control-screen.md)** -ominaisuuden ja uuden näytön **[OnVisible](../controls/control-screen.md)** -ominaisuuden tai kummatkin ominaisuudet. **App.ActiveScreen**-ominaisuus päivitetään muutoksen mukaisesti.

**Navigoi** palauttaa normaalisti **True** , mutta palauttaa arvon **false** , jos havaittiin virhe.

## <a name="back"></a>Back

**Back** -funktio palauttaa viimeksi näytetyn näytön.

Sovellus seuraa kunkin **siirtymis** kutsun yhteydessä ilmestyneen näytön ja siirtymän näyttöä. Voit käyttää peräkkäisiä **takaisinkutsuja** palauttamaan aina näytön, joka ilmestyi, kun käyttäjä aloitti sovelluksen.

Kun **Back** -funktio suoritetaan, käänteinen siirtymä on oletus arvon mukaan käytössä. Jos esimerkiksi näyttö näyttää **Coverright** -siirtymän kautta, **takaisin** **-vaihto ehdot (vasemmalla** ) voidaan palauttaa.  **Häivytä** ja **ei mitään** ovat omat käänteisarvonsa. Siirrä valinnainen argumentti **takaisin** , jos haluat pakottaa tietyn siirtymän.

**Takaisin** normaalisti palauttaa arvon **True** , mutta palauttaa arvon **false** , jos käyttäjä ei ole siirtynyt toiseen näyttöön sovelluksen käynnistämisen jälkeen.

## <a name="syntax"></a>Syntaksi

**Takaisin**([ *siirtyminen* ])

* *Siirtymä* – valinnainen. Visuaalisen siirtymän käyttäminen nykyisen näytön ja edellisen näytön välillä. Katso tämän ohje aiheen aiemmin määritetty tämän argumentin kelvollisten arvojen luettelo. Oletus arvon mukaan siirtymä, jonka kautta näyttö palautuu, on käänteissiirtymä, jonka kautta se ilmestyi.

**Navigoi**( *Screen* [; *Transition* [; *updatecontextrecord* ]])

* *Screen* – Pakollinen. Avattava näyttö.
* *Siirtymä* – valinnainen.  Nykyisestä näytöstä uuteen siirtymisen visuaalinen efekti. Katso tämän argumentin kelvolliset arvot tämän aiheen aiemmasta osasta. Oletus arvo on **none**.
* *UpdateContextRecord* – Valinnainen.  Tietue, joka sisältää vähintään yhden sarakkeen nimen ja arvon jokaiselle sarakkeelle. Tämä tietue päivittää uuden näytön kontekstimuuttujat, jos se välitetään **[UpdateContext](function-updatecontext.md)** -funktiolle.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Navigoi (tiedot)** |Näyttää **Lisätiedot**-näytön ilman siirtymäefektiä tai muutoksia kontekstimuuttujan arvoon. |**Lisätiedot**-näyttö ilmestyy nopeasti. |
| **Navigate( Lisätiedot; ScreenTransition.Fade )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä.  Mitään kontekstimuuttujan arvoa ei muuteta. |Nykyinen näyttö häivytetään ja **Lisätiedot**-näyttö näytetään. |
| **Navigate( Lisätiedot; ScreenTransition.Fade; {&nbsp;ID:&nbsp;12&nbsp;} )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä ja päivittää **ID**-kontekstimuuttujan arvoksi **12**. |Uusi näyttö häivytetään, **Lisätiedot**-näyttö näytetään ja kyseisen näytön kontekstimuuttujan **ID**-arvoksi asetetaan **12**. |
| **Navigate( Lisätiedot; ScreenTransition.Fade; {&nbsp;ID:&nbsp;12&nbsp;;&nbsp;Shade:&nbsp;Color.Red&nbsp;} )** |Näyttää **Lisätiedot**-näytön **Fade**-siirtymällä. Päivittää **ID**-kontekstimuuttujan arvoksi **12** ja päivittää **Shade**-kontekstimuuttujan arvoksi **Color.Red**. |Nykyinen näyttö häivytetään ja **Lisätiedot**-näyttö näytetään. **Lisätiedot**-ruudun **ID**-kontekstimuuttujan arvoksi asetetaan **12** ja **Shade**-kontekstimuuttujan arvoksi asetetaan **Color.Red**. Jos asetat jonkin **Lisätiedot**-näytön ohjausobjektin **Fill**-ominaisuudeksi **Shade**, kyseinen ohjausobjekti näytetään punaisena. |
| **Back()** | Näyttää edellisen näytön, jossa on oletusarvoinen paluu siirtymä. | Näyttää edellisen näytön sen siirtymän käänteissiirtymän kautta, jota nykyinen näyttö näyttää. |
| **Takaisin (ScreenTransition. Cover)** |  Näyttää edellisen näytön, jossa on **kannen** siirtymä. | Näyttää edellisen näytön **kannen** siirtymän kautta riippumatta siitä, minkä siirtymän kautta nykyinen näyttö ilmestyi. |

### <a name="step-by-step"></a>Vaiheittainen esimerkki

1. Luo tyhjä sovellus.

1. Lisää siihen toinen näyttö.

    Sovellus sisältää kaksi tyhjää näyttöä: **Screen1** ja **Screen2**.

1. Määritä **Screen2** -kohteen **Fill** -ominaisuudeksi arvo `Gray`.

1. Lisää **Screen2**painike ja määritä sen **[onselect](../controls/properties-core.md)** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Navigate( Screen1; ScreenTransition.Cover )
    ```

1. Pidä **Alt** -näppäintä painettuna ja valitse painike.

    **Screen1** näkyy valkoisella taustalla siirtymästä, joka peittää vasemmalle.

1. Lisää **Screen1**painike ja määritä sen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Back()
    ```

1. Pidä **Alt** -näppäintä painettuna ja valitse painike.

    Toinen näyttö tulee näkyviin harmaan taustan kautta sellaisen siirtymän kautta, joka poistaa oikealla olevat kannet (käänteinen **kansi**).

1. Valitse jokaisen näytön painike toistuvasti, jotta voit toipua edestakaisin.

[Toinen esimerkki](../add-screen-context-variables.md)

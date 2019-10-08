---
title: Osien toiminta kaavat | Microsoft Docs
description: Käynnistä sovellus suorittamaan vähintään yksi tehtävä, kun komponenttipohjainen toiminto suoritetaan.
author: yifwang
ms.service: powerapps
ms.topic: article
ms.date: 9/30/2019
ms.author: yifwang
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: baf7e74581819b3ea21542f30f96a0a6f517c0d5
ms.sourcegitcommit: 60fd1792430b9f3da08ec161cb2277506d795e3a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/01/2019
ms.locfileid: "71705038"
ms.PowerAppsDecimalTransform: true
---
# <a name="behavior-formulas-for-components"></a>Komponenttien toiminta kaavat

> [!IMPORTANT]
> Ominaisuus on edelleen kokeellinen, ja se on oletus arvon mukaan poistettu käytöstä. Lisä tietoja on kohdassa [Experimental-ja Preview-ominaisuudet](working-with-experimental.md).

Määritä vähintään yksi [toiminta kaava](working-with-formulas-in-depth.md) , joka suoritetaan, kun tapahtuma käynnistää osan esiintymien muutoksen. Voit esimerkiksi määrittää komponentin **Onreset** -ominaisuudeksi yhden tai useamman kaavan, joka suorittaa alustuksen, tyhjentää syötteen ja nollata arvot, kun **reset** -funktiolla suoritetaan komponentti esiintymiä.

## <a name="onreset"></a>OnReset

Kun komponentti Master on valittuna, valitse **Onreset** avattavasta ominaisuuksien luettelosta (kaava rivin vasemmassa reunassa) ja kirjoita vähintään yksi kaava.

> [!div class="mx-imgBorder"]
> ![OnReset-esimerkki @ no__t-1

Voit testata **Onreset**-määritystä määrittämällä ohjaus objektin nollaamaan komponentin. Voit esimerkiksi määrittää painikkeen **onselect** -ominaisuudeksi tämän kaavan: **Nollaa**(*componentname*).

### <a name="example---reset-timer"></a>Esimerkki – Nollaa ajastin

> [!div class="mx-imgBorder"]
> ![OnReset-esimerkki @ no__t-1

Tässä ajan valitsin-osassa näytetään kaksi muuttujaa Time _selectedHour ja _selectedMinute. Kun valitsin palautetaan, Nämä muuttujat on palautettava oletus arvoon, eli 12: 12.  Komponentin OnReset-ominaisuudella on seuraava kaava: **Asetus (_selectedHour, 12); Asetus (_selectedMinute, 12)**

Jos haluat käynnistää nollauksen, siirry näyttöön ja Lisää komponentin esiintymä. Lisää painike ja määritä OnSelect-painike kutsuäksesi **reset (TimerComponent_instance)** käynnistämään onreset.

> [!div class="mx-imgBorder"]
> ![Reset-painike @ no__t-1

## <a name="update-onreset-using-custom-property"></a>Päivitä OnReset käyttäen mukautettua ominaisuutta

Component-esiintymän nollaamisen lisäksi komponentin ulkopuolelta on olemassa toinen menetelmä, joka käynnistää OnReset-kohteen sisäpuolelta. "**Nosta onreset, kun arvon muutokset**" on vaihto ehto luotaessa mukautettua syöte ominaisuutta, ja se sallii tämän ominaisuuden arvon muuttamisen käynnistävän komponentin onreset-määrityksen. Tämä menetelmä on suunniteltu asettamaan ja nollaamaan oletus arvo helposti. 

> ![OnReset-esimerkki](./media/component-behavior/property-trigger.png)

### <a name="example"></a>Esimerkki

> [!div class="mx-imgBorder"]
> ![OnReset-esimerkki @ no__t-1

Tämä on esimerkki järjestys numeroiden tarkistamisesta ja lukujen päivittämisestä. Numero ylös ja alas-osaa käytetään tilausten määrän lisäämiseen tai pienentymiseen. Kun valitset valikoiman vasemmalla puolella, numero ylös ja alas-osan oletus arvo palautetaan näyttämään valitun työkalun järjestys numero. "**Nosta OnReset, kun arvon muutokset**"-vaihto ehdon avulla voitiin nollata oletus arvo, kun syöte muuttuu. 

Voit tehdä tämän valitsemalla Lisää**OnReset, kun arvon muutokset**on oletus syöte-ominaisuudessa. Komponentin **Onreset** on määritetty arvoksi **(_numericValue; numero ylös alas). DefaultValue)** . _numericValue on muuttuja, joka tallentaa nykyisen tila uksen arvon arvon. Ja Määritä teksti syöte-ohjaus objektin **oletus** arvoksi **if (Onblank (_numericValue), ' numeric up Down '. DefaultValue, _numericValue)** . 

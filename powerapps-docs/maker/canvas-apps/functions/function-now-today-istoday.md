---
title: Now-, Today- ja IsToday-funktiot | Microsoft Docs
description: Viitetiedot PowerAppsin Now-, Today- ja IsToday-funktioille, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/09/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 748f76835e9a66281f4723b88ed7249a7a07e091
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61544161"
---
# <a name="now-today-and-istoday-functions-in-powerapps"></a>Now-, Today- ja IsToday-funktiot PowerAppsissa
Palauttaa nykyisen päivämäärän ja ajan ja testaa, vastaako päivämäärä/aika-arvo tätä päivää.

## <a name="description"></a>Kuvaus
**Now**-funktio palauttaa nykyisen päivämäärän ja ajan päivämäärä/aika-arvona.

**Today**-funktio palauttaa nykyisen päivämäärän päivämäärä/aika-arvona. Aikaosa vastaa keskiyötä. **Today**-funktiolla on sama arvo koko päivän ajan tämän päivän keskiyöstä huomiseen keskiyöhön.

**IsToday**-funktiolla testataan, onko päivämäärä/aika-arvo tämän päivän keskiyön ja huomisen keskiyön välillä. Tämä funktio palauttaa totuusarvon (**true** tai **false**).

Kaikki nämä funktiot toimivat nykyisen käyttäjän paikallisen ajan mukaisesti.

Lisätietoja on kohdassa [Päivämäärien ja kellonaikojen käsitteleminen](../show-text-dates-times.md).

## <a name="volatile-functions"></a>Muuttuvat funktiot
**Now** ja **Today** ovat muuttuvia funktioita.  Aina, kun jotakin näistä funktioista arvioidaan, se palauttaa eri arvon.  

Kun muuttuvaa funktiota käytetään työnkulun kaavassa, muuttuva funktio palauttaa eri arvon vain arvioitaessa uudelleen kaavaa, jossa se esiintyy.  Jos mitään muuta ei muuteta kaavassa, sillä on sama arvo koko sovelluksesi suorittamisen ajan.

Esimerkiksi nimen ohjausobjekti, jossa **Label1.Text = Now()**, ei muutu, kun sovelluksesi on aktiivinen.  Uusi arvo luodaan vain sulkemalla sovellus ja avaamalla se uudelleen.

Funktio arvioidaan uudelleen, jos se on osa kaavaa, jossa jotakin muuta kohtaa on muutettu.  Jos lisäämme esimerkkiimme liukusäätimen ohjausobjektin, jossa **Label1.Text = DateAdd (Now(), Slider1.Value, Minutes)**, senhetkinen aika noudetaan aina, kun liukusäätimen ohjausobjektin arvo muuttuu ja otsikon tekstin ominaisuutta arvioidaan uudelleen.

Kun sitä käytetään [käytöskaavassa](../working-with-formulas-in-depth.md), muuttuvia funktioita arvioidaan aina, kun käytöskaavaa arvioidaan.  Katso esimerkki alta.

## <a name="syntax"></a>Syntaksi
**Now**()

**Today**()

**IsToday**( *DateTime* )

* *DateTime* – Pakollinen.  Testattava päivämäärä/aika-arvo.

## <a name="examples"></a>Esimerkkejä
Tämän osion esimerkkejä varten nykyinen aika on **03.59** **12. helmikuuta 2015** ja kieli on **en-us**.

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Text( Now(), "mm/dd/yyyy hh:mm:ss" )** |Hakee nykyisen päivämäärän ja ajan ja näyttää sen merkkijonona. |"02/12/2015 03:59:00" |
| **Text( Today(), "mm/dd/yyyy hh:mm:ss" )** |Hakee vain nykyisen päivämäärän, jättää aikaosan keskiyöhön ja näyttää tuloksen merkkijonona. |"02/12/2015 00:00:00" |
| **IsToday( Now() )** |Testaa, onko nykyinen päivämäärä ja aika tämän päivän keskiyön ja huomisen keskiyön välillä. |**true** |
| **IsToday( Today() )** |Testaa, onko nykyinen päivämäärä tämän päivän keskiyön ja huomisen keskiyön välillä. |**true** |
| **Text( DateAdd( Now(), 12 ), "mm/dd/yyyy hh:mm:ss" )** |Hakee nykyisen päivämäärän ja ajan, lisää tulokseen 12 päivää ja näyttää tuloksen merkkijonona. |"02/24/2015 03:59:00" |
| **Text( DateAdd( Today(), 12 ), "mm/dd/yyyy hh:mm:ss" )** |Hakee nykyisen päivämäärän, lisää tulokseen 12 päivää ja näyttää tuloksen merkkijonona. |"02/24/2015 00:00:00" |
| **IsToday( DateAdd( Now(), 12 ) )** |Testaa, onko nykyinen päivämäärä ja aika plus 12 päivää tämän päivän keskiyön ja huomisen keskiyön välillä. |**false** |
| **IsToday( DateAdd( Today(), 12 ) )** |Testaa, onko nykyinen päivämäärä plus 12 päivää tämän päivän keskiyön ja huomisen keskiyön välillä. |**false** |

#### <a name="display-a-clock-that-updates-in-real-time"></a>Reaaliaikaisesti päivittyvän kellon näyttäminen

1. Lisää **[Ajastin](../controls/control-timer.md)**-ohjausobjekti, määritä sen **Duration**-ominaisuuden arvoksi **1000** ja sen **Repeat**-ominaisuudeksi **true**.

    Ajastin käy sekunnin ja aloittaa automaattisesti alusta jatkaen tätä mallia. 

1. Määritä ohjausobjektin **OnTimerEnd**-ominaisuus tähän kaavaan:

    **Set( CurrentTime, Now() )**

    Aina, kun ajastin aloittaa alusta (jokaisen sekunnin jälkeen), tämä kaava määrittää yleisen **CurrentTime**-muuttujan **Now**-funktion nykyiseen arvoon.

    ![Näyttö, joka sisältää ajastimen ohjausobjektin ja kaavan OnTimerEnd = Set(CurrentTime, Now())](media/function-now-today-istoday/now-set-currenttime.png)

1. Lisää **[Selite](../controls/control-text-box.md)**-ohjausobjekti ja määritä sen **Text**-ominaisuus tähän kaavaan:

    **Text( CurrentTime, LongTime24 )**

    Voit **[Text](function-text.md)**-funktion avulla muotoilla päivämäärän ja ajan haluamaksesi tai määrittää täksi ominaisuudeksi **CurrentTime**, jotta se näyttää tunnit ja minuutit sekuntien sijasta.

    ![Näyttö, joka sisältää selitteen ohjausobjektin, jossa Text-ominaisuudeksi on määritetty Text( CurrentTime, LongTime24)](media/function-now-today-istoday/now-use-currenttime.png)

1. Voit esikatsella sovellusta painamalla F5 ja käynnistää sitten ajastimen napsauttamalla tai napauttamalla sitä.

    Selite näyttää jatkuvasti senhetkisen ajan sekunteihin asti.

    ![Neljä näyttöä, jotka näyttävät neljä aika-arvoa (13:50:22, 13:50:45, 13:51:03 ja 13:51:25)](media/function-now-today-istoday/now-four-times.png)

1. Määritä ajastimen **AutoStart**-ominaisuudeksi **true** ja **Visible**-ominaisuudeksi **false**.

    Ajastin on näkymätön ja käynnistyy automaattisesti.

1. Määritä näytön **[OnStart](../controls/control-screen.md)**-ominaisuus, jotta **CurrentTime**-muuttujalla on voimassaoleva arvo, kuten seuraavassa esimerkissä:

    **Set(CurrentTime, Now())**

    Selite tulee näkyviin heti, kun sovellus käynnistyy (ennen kuin ajastin käy koko sekunnin ajan).

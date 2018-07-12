---
title: Update- ja UpdateIf-funktiot | Microsoft Docs
description: PowerAppsin Update- ja UpdateIf-funktioiden viittaustietoja, kuten syntaksi ja esimerkkejä
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: 3046aa93941a07d44345e09b442cb57b623946c3
ms.sourcegitcommit: 6d9fe9967841e381b108a7fb53c9057e295336ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/11/2018
ms.locfileid: "38078435"
---
# <a name="update-and-updateif-functions-in-powerapps"></a>Update- ja UpdateIf-funktiot PowerAppsissa
Päivittää [tietolähteen](../working-with-data-sources.md) [tietueet](../working-with-tables.md#records).

## <a name="description"></a>Kuvaus
### <a name="update-function"></a>Update-funktio
Käytä **Update**-funktiota tietolähteen koko tietueen korvaamiseen. **UpdateIf**- ja **[Patch](function-patch.md)**-funktiot muokkaavat yhtä tai useampaa tietueen arvoa muokkaamatta muita arvoja.

[Kokoelmaa](../working-with-data-sources.md#collections) varten koko tietueen on oltava funktion mukainen. Kokoelmissa sallitaan tietueiden kaksoiskappaleet, joten useat tietueet voivat vastata. Voit käyttää **All**-argumenttia tietueen kaikkien kopioiden päivittämiseen. Muuten vain yksi tietueen kopio päivitetään.

Jos tietolähde luo sarakkeen arvon automaattisesti, tämän [sarakkeen](../working-with-tables.md#columns) arvo pitää vahvistaa uudelleen.

### <a name="updateif-function"></a>UpdateIf-funktio
Käyttämällä **UpdateIf**-funktiota voit muokata yhtä tai useampaa ehtoa vastaavan yhden tai useamman tietueen yhtä tai useampaa arvoa. Ehto voi olla mikä tahansa kaava, jonka tulos on **tosi** tai **epätosi**, ja se voi viitata tietolähteen sarakkeisiin nimen mukaan. Funktio arvioi jokaisen tietueen ehtoa ja muokkaa kaikkia tietueita, joiden tulos on **tosi**.  

Määritä muokkaus käyttämällä uudet ominaisuusarvot sisältävää muutostietuetta. Jos lisäät tämän muutostietueen sisäisesti kaarisulkeilla, ominaisuuskaavat voivat viitata muokattavan tietueen ominaisuuksiin. Tämän toiminnan avulla voit muokata tietueita kaavan perusteella.

Voit myös käyttää **[Patch](function-patch.md)**-funktiota **UpdateIf**-funktion tavoin tietueen tiettyjen sarakkeiden muuttamiseen muita sarakkeita muuttamatta.

Sekä **Update** että **UpdateIf** palauttavat muokatun tietolähteen [taulukkona](../working-with-tables.md). Käytä toista näistä funktioista [toimintakaavassa](../working-with-formulas-in-depth.md).

### <a name="delegation"></a>Delegointi
[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaksi
**Update**( *Tietolähde*, *VanhaTietue*, *UusiTietue* [, **All** ] )

* *Tietolähde* – Pakollinen. Tietolähde, joka sisältää korvattavan tietueen.
* *VanhaTietue* – Pakollinen. Korvattava tietue.
* *UusiTietue* – Pakollinen. Korvaava tietue. Tämä ei ole muutostietue. Koko tietue korvataan, ja puuttuvat ominaisuudet sisältävät arvon *tyhjä*.
* **All** – Valinnainen. Sama tietue voi näkyä kokoelmassa useamman kerran. Määritä **All**-argumentti tietueen kaikkien kopioiden poistamiseksi.

**UpdateIf**( *Tietolähde*, *Ehto1*, *Muutostietue1* [, *Ehto2*, *Muutostietue2* , ... ] )

* *Tietolähde* – Pakollinen. Tietolähde, joka sisältää muokattavan tietueen tai tietueet.
* *Ehto* – Pakollinen. Kaava, joka palauttaa tuloksen **tosi** muokattavalle tietueelle tai tietueille.  Voit käyttää *Tietolähteen* sarakkeiden nimiä kaavassa.  
* *Muutostietue* – Pakollinen.  Muutostietue uusista ominaisuusarvoista jokaista vastaavaa ehtoa varten. Käytetään ehtoa vastaavan *tietolähteen* tietueissa. Jos lisäät tietueen sisäisesti käyttämällä kaarisulkeita, olemassa olevan tietueen ominaisuusarvoja voidaan käyttää ominaisuuskaavoissa.

## <a name="examples"></a>Esimerkkejä
Näissä esimerkeissä korvataan tai muokataan tietueita tietolähteessä, jonka nimi on **IceCream** ja joka alkaa seuraavan taulukon tiedoilla:

![](media/function-update-updateif/icecream.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Update(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Chocolate"&nbsp;)&nbsp;), {&nbsp;ID:&nbsp;1,&nbsp;Flavor:&nbsp;"Mint&nbsp;Chocolate",&nbsp;Quantity:150&nbsp;} )** |Korvaa tietolähteen tietueen. |<style> img { max-width: none } </style> ![](media/function-update-updateif/icecream-mint.png)<br><br>**IceCream**-tietolähdettä on muokattu. |
| **UpdateIf(&nbsp;IceCream, Quantity > 175, {&nbsp;Quantity:&nbsp;Quantity&nbsp;+&nbsp;10&nbsp;} )** |Muokkaa tietueita, joiden **Quantity** on suurempi kuin **150**.  **Quantity**-kentän arvoon lisätään 10. Muita kenttiä ei muokata. |![](media/function-update-updateif/icecream-mint-plus10.png)<br><br>**IceCream**-tietolähdettä on muokattu. |
| **Update(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream, Flavor="Strawberry"&nbsp;)&nbsp;),<br>{&nbsp;ID:&nbsp;3, Flavor:&nbsp;"Strawberry Swirl"} )** |Korvaa tietolähteen tietueen. **Quantity**-ominaisuutta ei ole lisätty korvaavaan tietueeseen, joten tämä ominaisuus on tuloksessa *tyhjä*. |![](media/function-update-updateif/icecream-mint-swirl.png)<br><br>**IceCream**-tietolähdettä on muokattu. |
| **UpdateIf(&nbsp;IceCream, true, {&nbsp;Quantity:&nbsp;0&nbsp;} )** |Määrittää tietolähteen jokaisen tietueen **Quantity**-ominaisuuden arvoksi 0. |![ ](./media/function-update-updateif/icecream-mint-zero.png)<br> <br>**IceCream**-tietolähdettä on muokattu. |

### <a name="step-by-step"></a>Ohjeet vaihe vaiheelta
1. Tuo tai luo kokoelma, jonka nimi on **Luettelo**, ja näytä se valikoimassa artikkelin [Tietojen näyttäminen valikoimassa](../show-images-text-gallery-sort-filter.md) mukaan.
2. Anna valikoiman nimeksi **Tuotevalikoima**.
3. Lisää liukusäädin, jonka nimi on **MyydytKappaleet**, ja määritä sen **Suurin**-ominaisuudeksi tämä lauseke:<br>**Tuotevalikoima.Valittu.KappalettaVarastossa**
4. Lisää painike ja määritä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>**UpdateIf(Luettelo, Tuotenimi = Tuotevalikoima.Valittu.Tuotenimi, {KappalettaVarastossa:KappalettaVarastossa-MyydytKappaleet.Arvo})**
5. Paina F5-näppäintä, valitse tuote valikoimasta, määritä arvo liukusäätimellä ja valitse painike.
   
    Määrittämäsi tuotteen varastossa olevien kappaleiden lukumäärästä vähennetään määrittämäsi määrä.


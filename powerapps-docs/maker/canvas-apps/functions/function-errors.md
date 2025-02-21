---
title: Virheet-funktio | Microsoft Docs
description: Tietoja PowerAppsin Errors-funktiosta, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/11/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 114474696f85980da315b6dd225250dc1b197805
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992781"
ms.PowerAppsDecimalTransform: true
---
# <a name="errors-function-in-powerapps"></a>PowerAppsin Virheet-funktio
Antaa [tietolähteen](../working-with-data-sources.md) edellisiin muutoksiin liittyviä virhetietoja.

## <a name="overview"></a>Yleiskatsaus
Virheitä voi tapahtua, kun tietolähteen [tietuetta](../working-with-tables.md#records) muutetaan.  Tähän voi olla useita syitä, kuten verkkokatkokset, riittämättömät käyttöoikeudet ja muokkausristiriidat.  

**[Patch](function-patch.md)** -funktio ja muut datafunktiot eivät suoraan palauta virheitä. Sen sijaan ne palauttavat niiden toiminnon tuloksen. Kun datafunktio suoritetaan, voit käyttää **Errors**-funktiota virheiden tietojen hankkimiseen.  Voit tarkistaa virheiden olemassaolon kaavan **IsEmpty( Errors ( ... ) )** funktiolla **[IsEmpty]** .

Voit välttää joitakin virheitä, ennen kuin ne tapahtuvat, käyttämällä **[Validate](function-validate.md)** - ja **[DataSourceInfo](function-datasourceinfo.md)** -funktioita.  Katso lisäehdotuksia siitä, miten virheitä käsitellään ja vältetään, aiheesta [tietolähteiden käsitteleminen](../working-with-data-sources.md).

## <a name="description"></a>Kuvaus
**Errors**-funktio palauttaa virheiden [taulukon](../working-with-tables.md), joka sisältää seuraavat [sarakkeet](../working-with-tables.md#columns):

* **Record**.  Tietolähteessä oleva tietue, jossa virhe ilmeni.  Jos virhe ilmeni tietueen luonnin aikana, tämä sarake on *tyhjä*.
* **Column**.  Sarake, joka aiheutti virheen, jos virheen voidaan katsoa johtuneen yhdestä sarakkeesta. Jos ei, tämä on *tyhjä*.
* **Message**.  Virheen kuvaus.  Tämä virhemerkkijono voidaan näyttää loppukäyttäjälle.  Huomioi, että tietolähde saattaa muodostaa tämän viestin ja se voi olla pitkä ja sisältää raakoja sarakkeiden nimiä, jotka eivät ehkä merkitse käyttäjälle mitään.
* **Error**.  Virhekoodi, jota voidaan käyttää kaavoissa ratkaisemaan virhe:

| ErrorKind | Kuvaus |
| --- | --- |
| ErrorKind.Conflict |Toinen muutos tehtiin samaan tietueeseen, mikä aiheutti muutosristiriidan.  Lataa tietue uudestaan **[Refresh](function-refresh.md)** -funktiolla ja yritä tehdä muutos uudelleen. |
| ErrorKind.ConstraintViolation |Yhtä tai useampaa rajoitusta on rikottu. |
| ErrorKind.CreatePermission |Tietue yritettiin luoda, eikä nykyisellä käyttäjällä ole tietueiden luontioikeutta. |
| ErrorKind.DeletePermission |Tietue yritettiin poistaa, eikä nykyisellä käyttäjällä ole tietueiden poisto-oikeutta. |
| ErrorKind.EditPermission |Tietuetta yritettiin muokata, eikä nykyisellä käyttäjällä ole tietueiden muokkausoikeutta. |
| ErrorKind.GeneratedValue |Tietolähteen automaattisesti luomaa saraketta yritettiin muuttaa. |
| ErrorKind.MissingRequired |Pakollisen sarakkeen arvo puuttuu tietueesta. |
| ErrorKind.None |Ei virhettä. |
| ErrorKind.NotFound |Tietuetta yritettiin muokata tai se yritettiin poistaa, mutta tietuetta ei löytynyt.  Toinen käyttäjä on ehkä muuttanut tietuetta. |
| ErrorKind.ReadOnlyValue |Vain luettavaa saraketta yritettiin muuttaa. |
| ErrorKind.Sync |Tietolähde ilmoitti virheestä.  Lisätietoja on Viesti-sarakkeessa. |
| ErrorKind.Unknown |Ilmeni virhe, mutta sen laji on tuntematon. |
| ErrorKind.Validation |Havaittiin yleinen vahvistusongelma, joka ei sopinut mihinkään muuhun lajiin. |

Virheitä voidaan palauttaa koko tietolähteestä tai vain valitusta rivistä antamalla funktiolle *Tietue*-argumentti.  

**[Patch](function-patch.md)** tai jokin toinen datafunktio saattaa palauttaa *tyhjän* arvon, jos esimerkiksi tietuetta ei voitu luoda. Voit välittää *tyhjän* arvon **Errors**-funktiolle, ja se palauttaa asianmukaiset virhetiedot näissä tapauksissa.  Datafunktioiden seuraava käyttökerta samalla tietolähteellä tyhjentää nämä virhetiedot.

Jos virheitä ei ole, taulukko, jonka **Errors** palauttaa, on [tyhjä](function-isblank-isempty.md) ja sitä voidaan testata **[IsEmpty](function-isblank-isempty.md)** -funktiolla.

## <a name="syntax"></a>Syntaksi
**Errors**( *DataSource* [; *Record* ] )

* *DataSource* – Pakollinen. Tietolähde, jolle haluat palauttaa virheitä.
* *Record* – Valinnainen.  Tietty tietue, jolle haluat palauttaa virheitä. Jos et määritä tätä argumenttia, funktio palauttaa virheitä koko tietolähteelle.

## <a name="examples"></a>Esimerkkejä
### <a name="step-by-step"></a>Vaihe vaiheelta
Tässä esimerkissä käytämme **IceCream**-tietolähdettä:

![](media/function-errors/icecream.png)

Sovelluksessa käyttäjä lataa Chocolate-tietueen tietolomakkeeseen ja muuttaa sitten **Quantity**-arvoksi luvun 90.  Työstettävä tietue sijoitetaan [kontekstimuuttujaan](../working-with-variables.md#use-a-context-variable)**EditRecord**:

* **UpdateContext ({Edittacord: First (Filter (IceCream; Flavor = "Chocolate"))})**

Tämä muutos tehdään tietolähteeseen **[Patch](function-patch.md)** -funktiolla:

* **Patch( IceCream; EditRecord; Gallery.Updates )**

jossa **valikoima. päivitykset** antaa tulokseksi **{määrä: 90}** , koska vain **quantity** -ominaisuutta on muokattu.

Valitettavasti, juuri ennen kuin **[Patch](function-patch.md)** -funktio käynnistettiin, joku muu muutti Chocolate-tietueen **Quantity**-arvoksi luvun 80.  PowerApps tunnistaa tämän eikä salli ristiriitaista muutosta.  Voit tarkistaa tällaisen tilanteen seuraavalla kaavalla:

* **IsEmpty( Errors( IceCream; EditRecord ) )**

joka palauttaa **epätoden**, koska **Errors**-funktio palautti seuraavan taulukon:

| Tietue | Sarake | Viesti | Virhe |
| --- | --- | --- | --- |
| Maku "Suklaa", määrä: 100} |*tyhjä* |”Toinen käyttäjä on muokannut tietuetta, jota yrität muokata. Lataa tietue uudestaan ja yritä uudelleen.” |ErrorKind.Conflict |

Voit sijoittaa lomakkeeseen selitteen, joka näyttää tämän virheen käyttäjälle.

* Näytä virhe määrittämällä selitteen **[Teksti](../controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>
  **Label.Text = First(Errors( IceCream; EditRecord )).Message**

Voit myös lisätä **Lataa uudelleen** -painikkeen lomakkeeseen, jotta käyttäjä voi ratkaista ristiriidan tehokkaasti.

* Näytä painike vain, kun ristiriita on esiintynyt, määrittämällä painikkeen **[Visible](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:<br>
    **!IsEmpty( Lookup( Errors( IceCream; EditRecord ); Error = ErrorKind.Conflict ) )**
* Kumoa muutos, kun käyttäjä valitsee painikkeen, määrittämällä sen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:<br>
    **ReloadButton.OnSelect = Revert( IceCream; EditRecord )**


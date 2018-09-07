---
title: Virheet-funktio | Microsoft Docs
description: Tietoja PowerAppsin Errors-funktiosta, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/11/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 886479b4cd2f7e04e9949c99ba05e6219e92b2b3
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42859982"
---
# <a name="errors-function-in-powerapps"></a>PowerAppsin Virheet-funktio
Antaa [tietolähteen](../working-with-data-sources.md) edellisiin muutoksiin liittyviä virhetietoja.

## <a name="overview"></a>Yleiskatsaus
Virheitä voi tapahtua, kun tietolähteen [tietuetta](../working-with-tables.md#records) muutetaan.  Tähän voi olla useita syitä, kuten verkkokatkokset, riittämättömät käyttöoikeudet ja muokkausristiriidat.  

**[Patch](function-patch.md)**-funktio ja muut datafunktiot eivät suoraan palauta virheitä. Sen sijaan ne palauttavat niiden toiminnon tuloksen. Kun datafunktio suoritetaan, voit käyttää **Virheet**-funktiota virheiden tietojen hankkimiseen.  Voit tarkistaa virheiden olemassaolon kaavan **IsEmpty( Errors ( ... ) )** funktiolla **[IsEmpty]**.

Voit välttää joitakin virheitä, ennen kuin ne tapahtuvat, käyttämällä **[Vahvista](function-validate.md)**- ja **[DataSourceInfo](function-datasourceinfo.md)**-funktioita.  Katso lisäehdotuksia siitä, miten virheitä käsitellään ja vältetään, aiheesta [tietolähteiden käsitteleminen](../working-with-data-sources.md).

## <a name="description"></a>Kuvaus
**Errors**-funktio palauttaa virheiden [taulukon](../working-with-tables.md), joka sisältää seuraavat [sarakkeet](../working-with-tables.md#columns):

* **Tietue**.  Tietolähteessä oleva tietue, jossa virhe ilmeni.  Jos virhe ilmeni tietueen luonnin aikana, tämä sarake on *tyhjä*.
* **Sarake**.  Sarake, joka aiheutti virheen, jos virheen voidaan katsoa johtuneen yhdestä sarakkeesta. Jos ei, tämä on *tyhjä*.
* **Viesti**.  Virheen kuvaus.  Tämä virhemerkkijono voidaan näyttää loppukäyttäjälle.  Huomioi, että tietolähde saattaa muodostaa tämän viestin ja se voi olla pitkä ja sisältää raakoja sarakkeiden nimiä, jotka eivät ehkä merkitse käyttäjälle mitään.
* **Virhe**.  Virhekoodi, jota voidaan käyttää kaavoissa ratkaisemaan virhe:

| ErrorKind | Kuvaus |
| --- | --- |
| ErrorKind.Conflict |Toinen muutos tehtiin samaan tietueeseen, mikä aiheutti muutosristiriidan.  Lataa tietue uudestaan **[Refresh](function-refresh.md)**-funktiolla ja yritä tehdä muutos uudelleen. |
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

**[Korjaustiedosto](function-patch.md)** tai jokin toinen datafunktio saattaa palauttaa *tyhjän* arvon, jos esimerkiksi tietuetta ei voitu luoda. Voit välittää *tyhjän* arvon **Errors**-funktiolle, ja se palauttaa asianmukaiset virhetiedot näissä tapauksissa.  Datafunktioiden seuraava käyttökerta samalla tietolähteellä tyhjentää nämä virhetiedot.

Jos virheitä ei ole, taulukko, jonka **Errors** palauttaa, on [tyhjä](function-isblank-isempty.md) ja sitä voidaan testata **[IsEmpty](function-isblank-isempty.md)**-funktiolla.

## <a name="syntax"></a>Syntaksi
**Errors**( *Tietolähde* [, *Tietue* ] )

* *Tietolähde* – pakollinen. Tietolähde, jolle haluat palauttaa virheitä.
* *Tietue* – valinnainen.  Tietty tietue, jolle haluat palauttaa virheitä. Jos et määritä tätä argumenttia, funktio palauttaa virheitä koko tietolähteelle.

## <a name="examples"></a>Esimerkkejä
### <a name="step-by-step"></a>Vaihe vaiheelta
Tässä esimerkissä käytämme **IceCream**-tietolähdettä:

![](media/function-errors/icecream.png)

Sovelluksessa käyttäjä lataa Chocolate-tietueen tietolomakkeeseen ja muuttaa sitten **Quantity**-arvoksi luvun 90.  Työstettävä tietue sijoitetaan [kontekstimuuttujaan](../working-with-variables.md#create-a-context-variable)**EditRecord**:

* **UpdateContext( { EditRecord: First( Filter( IceCream, Flavor = "Chocolate" ) ) } )**

Tämä muutos tehdään tietolähteeseen **[Patch](function-patch.md)**-funktiolla:

* **Patch( IceCream, EditRecord, Gallery.Updates )**

jossa **Gallery.Updates** saa arvon **{ Quantity: 90 }**, koska vain **Quantity**-ominaisuutta on muokattu.

Valitettavasti, juuri ennen kuin **[Korjaustiedosto](function-patch.md)**-funktio käynnistettiin, joku muu muutti Chocolate-tietueen **Quantity**-arvoksi luvun 80.  PowerApps tunnistaa tämän eikä salli ristiriitaista muutosta.  Voit tarkistaa tällaisen tilanteen seuraavalla kaavalla:

* **IsEmpty( Errors( IceCream, EditRecord ) )**

joka palauttaa **epätoden**, koska **Errors**-funktio palautti seuraavan taulukon:

| Tietue | Sarake | Viesti | Virhe |
| --- | --- | --- | --- |
| { Flavor: "Chocolate", Quantity: 100 } |*tyhjä* |”Toinen käyttäjä on muokannut tietuetta, jota yrität muokata. Lataa tietue uudestaan ja yritä uudelleen.” |ErrorKind.Conflict |

Voit sijoittaa lomakkeeseen selitteen, joka näyttää tämän virheen käyttäjälle.

* Näytä virhe määrittämällä selitteen **[Teksti](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:<br>
  **Label.Text = First(Errors( IceCream, EditRecord )).Message**

Voit myös lisätä **Lataa uudelleen** -painikkeen lomakkeeseen, jotta käyttäjä voi ratkaista ristiriidan tehokkaasti.

* Näytä painike vain, kun ristiriita on esiintynyt, määrittämällä painikkeen **[Visible](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
    **!IsEmpty( Lookup( Errors( IceCream, EditRecord ), Error = ErrorKind.Conflict ) )**
* Kumoa muutos, kun käyttäjä valitsee painikkeen, määrittämällä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:<br>
    **ReloadButton.OnSelect = Revert( IceCream, EditRecord )**


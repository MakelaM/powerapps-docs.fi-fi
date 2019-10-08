---
title: 'Näytetty lomake- ja Muokattu lomake -ohjausobjektit: viittaus | Microsoft Docs'
description: Näytetty lomake- ja Muokattu lomake -ohjausobjekteja koskevaa tietoa, kuten ominaisuuksia ja esimerkkejä
author: aneesmsft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 07/06/2017
ms.author: aneesa
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0b25a22e732c96bf35f8951602e706f71b1733a7
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986719"
ms.PowerAppsDecimalTransform: true
---
# <a name="edit-form-and-display-form-controls-in-powerapps"></a>Muokattu lomake- ja Näytetty lomake -ohjausobjektit PowerAppsissa
Näytä ja luo tietue tai muokkaa sitä tietolähteessä.

## <a name="description"></a>Kuvaus
Jos lisäät **Näytetty lomake** -ohjausobjektin, käyttäjä voi näyttää kaikki tietueen kentät tai vain määritetyt kentät. Jos lisäät **Muokattu lomake** -ohjausobjektin, käyttäjä voi muokata kenttiä, luoda tietueita ja tallentaa muutokset tietolähteeseen.

![Esimerkkilomake ja lomakenäkymän ohjausobjektit](./media/control-form-detail/form-detail-intro.png)

Jos lisäät **[Valikoima](control-gallery.md)** -ohjausobjektin, voit määrittää sen näyttämään taulukon tietolähteessä. Tämän jälkeen voit määrittää lomakkeen näyttämään tietueen, jonka käyttäjä valitsee valikoimasta. Voit myös lisätä yhden tai useamman **[Painike](control-button.md)** -ohjausobjektin, joiden avulla käyttäjä voi tallentaa tai peruuttaa muokkauksia ja luoda tietueita. Ohjausobjekteja yhdistelemällä voit [luoda täydellisen ratkaisun](../working-with-forms.md).

### <a name="record-selection"></a>Tietueen valitseminen
Määritä kumman tahansa lomaketyypin **DataSource**-ominaisuudeksi taulukon tietueet ja määritä lomakkeen **Item**-ominaisuus näyttämään tietty tietue kyseisessä taulukossa. Voit esimerkiksi määrittää lomakkeen **Item**-ominaisuudeksi **[Valikoima](control-gallery.md)** -ohjausobjektin **SelectedItem**-ominaisuuden. Kun käyttäjä valitsee valikoimasta tietueen, sama tietue näytetään myös lomakkeessa, mutta siinä voidaan näyttää enemmän kenttiä. Jos käyttäjä palaa valikoimaan ja valitsee toisen tietueen, valikoiman **SelectedItem**-ominaisuus muuttuu. Tämä muutos päivittää lomakkeen **Item**-ominaisuuden, jonka jälkeen lomakkeessa näytetään juuri valittu tietue.

Voit myös määrittää lomakkeen **Item**-ominaisuus käyttämällä **avattavan luettelon** ohjausobjektia [Tietueen tarkasteleminen, muokkaaminen tai lisääminen](../add-form.md) -kohdassa kuvatulla tavalla, tai funktiota, kuten **Haku** tai **Ensimmäinen**. Voit esimerkiksi valita, että **Item** -ominaisuudeksi on määritetty jompikumpi näistä kaavoista, jotta voit näyttää Fabrikam-merkinnän **accounts** -entiteetissä Common Data Service:

```First(Accounts)```

```Lookup(Accounts; "Fabrikam" in name)```

Jokainen Lomake-ohjausobjekti sisältää vähintään yhden **[Kortti](control-card.md)** -ohjausobjektin. Voit [määrittää, minkä kentän kortti näyttää ja muita tietoja](../add-form.md) määrittämällä kortin **[DataField](control-card.md)** -ominaisuuden.

### <a name="create-a-record"></a>Tietueen luominen
Kun **Muokattu lomake** -ohjausobjekti on **Muokkaa**-tilassa, käyttäjä voi päivittää tietueen, joka on määritetty lomakkeen **Item**-ominaisuudessa. **Mode**-ominaisuus palauttaa tarkastettaessa arvon **Muokkaa**.

Kun **Muokattu lomake** -ohjausobjekti on **Uusi**-tilassa, **Item**-ominaisuus ohitetaan. Lomake ei näytä olemassa olevaa tietuetta. Sen sijaan kunkin kentän arvot vastaavat lomakkeen määrittämiseen käytetyn tietolähteen oletusarvoja. **[NewForm](../functions/function-form.md)** -funktio siirtää lomakkeen tähän tilaan.

Voit esimerkiksi määrittää painikkeen **[Teksti](properties-core.md)** -ominaisuuden näyttämään **Uusi** ja **[OnSelect](properties-core.md)** -ominaisuuden näyttämään kaavan, joka sisältää **[NewForm](../functions/function-form.md)** -funktion. Jos käyttäjä valitsee kyseisen painikkeen, lomake siirtyy **Uusi**-tilaan ja käyttäjä voi luoda tietueen, joka alkaa tunnetuilla arvoilla.

Jos joko **[ResetForm](../functions/function-form.md)** -funktion tai **[SubmitForm](../functions/function-form.md)** -funktion suorittaminen onnistuu, lomake siirtyy takaisin **Muokkaa**-tilaan.

* Voit esimerkiksi määrittää painikkeen **[Teksti](properties-core.md)** -ominaisuuden näyttämään **Peruuta** ja **[OnSelect](properties-core.md)** -ominaisuuden näyttämään kaavan, joka sisältää **[ResetForm](../functions/function-form.md)** -funktion. Jos käyttäjä valitsee kyseisen painikkeen, keskeneräiset muutokset hylätään, ja lomakkeen arvot vastaavat jälleen tietolähteen oletusarvoja.
* Voit esimerkiksi määrittää painikkeen **[Teksti](properties-core.md)** -ominaisuuden näyttämään **Tallenna muutokset** ja **[OnSelect](properties-core.md)** -ominaisuuden näyttämään kaavan, joka sisältää **[SubmitForm](../functions/function-form.md)** -funktion. Jos käyttäjä valitsee kyseisen painikkeen ja tietolähde päivitetään, lomakkeen arvot palautetaan tietolähteen oletusarvoiksi.

### <a name="save-changes"></a>Muutosten tallentaminen
Jos luot **Tallenna muutokset** -painikkeen edellisessä osassa kuvatulla tavalla, käyttäjä voi luoda tai päivittää tietuetta ja tallentaa tekemänsä muutokset tietolähteeseen valitsemalla painikkeen. Voit halutessasi määrittää **[Kuva](control-image.md)** -ohjausobjektin tai jonkin muun ohjausobjektin suorittamaan saman tehtävän, kunhan määrität kyseiselle ohjausobjektille **[SubmitForm](../functions/function-form.md)** -funktion. **Virhe**-, **ErrorKind**-, **OnSuccess**- ja **OnFailure**-ominaisuudet antavat joka tapauksessa palautetta tuloksesta.

Kun **[SubmitForm](../functions/function-form.md)** -funktio suoritetaan, se vahvistaa ensin tiedot, jotka käyttäjä haluaa lähettää. Jos pakollinen kenttä ei sisällä arvoa tai jokin toinen arvo ei vastaa muita rajoitteita, **ErrorKind**-ominaisuudet määritetään ja **OnFailure**-kaava suoritetaan. Voit määrittää **Tallenna muutokset** -painikkeen tai muun ohjausobjektin siten, että käyttäjä voi valita sen vain, jos tiedot ovat kelvolliset (toisin sanoen, jos **Valid**-ominaisuuden arvo on **true**). Huomaa, että käyttäjän on paitsi korjattava ongelma, myös valittava **Tallenna muutokset** -painike uudelleen (tai hylättävä muutokset valitsemalla **Peruuta**-painike aiempien ohjeiden mukaisesti), joka nollaa **Virhe**- ja **ErrorKind**-ominaisuudet.

Jos tiedot läpäisevät tarkistuksen, **[SubmitForm](../functions/function-form.md)** lähettää ne tietolähteeseen. Lähettämisessä voi kestää jonkin aikaa verkkoviiveen vuoksi.

* Jos lähetys onnistuu, **Virhe**-ominaisuus tyhjennetään, **ErrorKind**-ominaisuudeksi määritetään **ErrorKind.None** ja **OnSuccess**-kaava suoritetaan. Jos käyttäjä on luonut tietueen (eli jos lomake oli aiemmin **Uusi**-tilassa), lomake siirtyy **Muokkaa**-tilaan, jotta käyttäjä voi muokata juuri luomaansa tietuetta tai jotain toista tietuetta.
* Jos lähetys epäonnistuu, **Virhe**-ominaisuus sisältää käyttäjäystävällisen virhesanoman tietolähteestä, joka selittää ongelman. **ErrorKind**-ominaisuus määritetään ongelman mukaan ja **OnFailure**-kaava suoritetaan.

Jotkin tietolähteet voivat tunnistaa, jos kaksi henkilöä yrittää päivittää samaa tietuetta samaan aikaan. Tässä tapauksessa **ErrorKind**-ominaisuudeksi määritetään **ErrorKind.Conflict**. Ongelma korjataan päivittämällä tietolähde toisen käyttäjän muutoksilla ja ottamalla käyttäjän muutokset käyttöön uudelleen.

> [!TIP]
> Lomakkeessasi voi olla **Peruuta**-painike, jolla käyttäjä voi hylätä keskeneräiset muutokset. Voit lisätä painikkeen **[OnSelect](properties-core.md)** -ominaisuuteen **[ResetForm](../functions/function-form.md)** -funktion, vaikka ominaisuus sisältäisi myös **[Siirry](../functions/function-navigate.md)** -funktion näytön vaihtamiseen. Muussa tapauksessa lomake säilyttää käyttäjän tekemät muutokset.

### <a name="layout"></a>Asettelu
Kortit sijoitetaan oletusarvoisesti yhteen sarakkeeseen puhelinsovelluksissa ja kolmeen sarakkeeseen tablettisovelluksissa. Voit määrittää, kuinka monta saraketta lomakkeessa on, ja kohdistetaanko kortit sarakkeisiin, kun määrität lomaketta. Nämä asetukset eivät näy ominaisuuksina, koska niitä käytetään vain korttien **X**-, **Y**- ja **Leveys**-ominaisuuksien määrittämiseen.

Lisätietoja on kohdassa [Tutustu tietolomakkeiden asetteluun](../working-with-form-layout.md).

## <a name="key-properties"></a>Keskeiset ominaisuudet
**DataSource** – Tietolähde, joka sisältää käyttäjän näyttämän, muokkaaman tai luoman tietueen.

* Jos et määritä tätä ominaisuutta, käyttäjä ei voi näyttää, muokata tai luoda tietueita, eikä muita metatietoja tai vahvistusta anneta.

**DefaultMode** – Lomake-ohjausobjektin alkuperäinen tila.  Hyväksyttävät arvot ja niiden merkitykset ovat näkyvissä alla olevassa **tilojen** kuvauksessa. 

**DisplayMode** – Tila, jota käytetään Lomake-ohjausobjektin tietokorteissa ja ohjausobjekteissa.  

Johdettu **Mode**-ominaisuudesta, eikä sitä voi määrittää erikseen:

| Tila | DisplayMode | Kuvaus |
| --- | --- | --- |
| **FormMode.Edit** |**DisplayMode.Edit** |Tietokortit ja ohjausobjektit ovat muokattavissa ja valmiit hyväksymään muutoksia tietueeseen. |
| **FormMode.New** |**DisplayMode.Edit** |Tietokortit ja ohjausobjektit ovat muokattavissa ja valmiit hyväksymään uuden tietueen. |
| **FormMode.View** |**DisplayMode.View** |Tietokortit ja ohjausobjektit eivät ole muokattavissa vaan optimoituja tarkastelemista varten. |

**Virhe** – Lomakkeessa näytettävä käyttäjäystävällinen virhesanoma, kun **[SubmitForm](../functions/function-form.md)** -funktio epäonnistuu.

* Tämä ominaisuus koskee vain **Muokattu lomake** -ohjausobjektia.
* Tämä ominaisuus muuttuu vain, kun **[SubmitForm](../functions/function-form.md)** -, **EditForm**-, tai **[ResetForm](../functions/function-form.md)** -funktio suoritetaan.
* Jos virhettä ei tapahdu, ominaisuus on *tyhjä* ja **ErrorKind** määritetään arvoksi **ErrorKind.None**.
* Jos mahdollista, palautettu virhesanoma näytetään käyttäjän kielellä. Jotkin virhesanomat ovat peräisin suoraan tietolähteestä, eikä niitä voida välttämättä näyttää käyttäjän kielellä.

**ErrorKind** – Ilmaisee tapahtuneen virheen lajin, jos **SubmitForm**-funktiota suorittaessa ilmenee virhe.

* Koskee vain **Muokattu lomake** -ohjausobjektia.
* Tällä ominaisuudella on sama luettelointi kuin **[Virheet](../functions/function-errors.md)** -funktiolla. **Muokattu lomake** -ohjausobjekti voi palauttaa seuraavat arvot:

| ErrorKind | Kuvaus |
| --- | --- |
| **ErrorKind.Conflict** |Toinen käyttäjä muutti samaa tietuetta, mikä aiheutti muutosristiriidan. Lataa tietue uudestaan suorittamalla **[Päivitä](../functions/function-refresh.md)** -funktio ja yritä tehdä muutos uudelleen. |
| **ErrorKind.None** |Virheen laji on tuntematon. |
| **ErrorKind.Sync** |Tietolähde ilmoitti virheestä. Jos haluat lisätietoa, tarkasta **Virhe**-ominaisuus. |
| **ErrorKind.Validation** |Yleinen vahvistusongelma havaittu. |

**Item** – **Tietolähteen** tietue, jonka käyttäjä aikoo näyttää tai jota hän aikoo muokata.

**LastSubmit** – Viimeinen onnistuneesti lähetetty tietue, mukaan lukien palvelimen luomat kentät.

* Tämä ominaisuus koskee vain **Muokattu lomake** -ohjausobjektia.
* Jos tietolähde laskee tai luo automaattisesti kenttiä, kuten yksilöllisesti numeroidun **tunnus**kentän, **LastSubmit**-ominaisuus saa tämän uuden arvon, kun **SubmitForm** suoritetaan onnistuneesti.
* Ominaisuuden arvo on käytettävissä **OnSuccess**-kaavassa.

**Mode** – Ohjausobjekti on **Muokkaa**- tai **Uusi**-tilassa.

| Tila | Kuvaus |
| --- | --- |
| **FormMode.Edit** |Käyttäjä voi muokata tietuetta lomakkeen avulla. Lomakkeen korteissa olevat arvot on täytetty olemassa olevalla tietueella. Käyttäjä voi muuttaa niitä halutessaan. Jos **[SubmitForm](../functions/function-form.md)** -funktion suorittaminen onnistuu, olemassa olevaa tietuetta muokataan. |
| **FormMode.New** |Käyttäjä voi luoda tietueen lomakkeen avulla. Lomakkeen ohjaus objektien arvoihin täytetään valmiiksi tieto lähteen tietueen oletus arvot. Jos **[Submitform](../functions/function-form.md)** -funktiolla suoritetaan onnistuneesti, tietue luodaan. |
| **FormMode.View** |Käyttäjä voi tarkastella tietuetta lomakkeen avulla. Lomakkeen ohjaus objektien arvoihin täytetään valmiiksi tieto lähteen tietueen oletus arvot. |

Lomake siirtyy **Uusi**-tilasta **Muokkaa**-tilaan, kun jokin seuraavista muutoksista tapahtuu:

* Lomakkeen lähettäminen onnistuu ja tietue luodaan. Jos valikoima on määritetty siirtämään valinta automaattisesti uuteen tietueeseen, lomake on luodun tietueen osalta **Muokkaa**-tilassa, jotta käyttäjä voi tehdä lisämuutoksia.
* **[EditForm](../functions/function-form.md)** -funktio suoritetaan.
* **[ResetForm](../functions/function-form.md)** -funktio suoritetaan. Käyttäjä voi esimerkiksi valita **Peruuta**-painikkeen, johon on määritetty tämä funktio.

**OnFailure** – Kuinka sovellus vastaa, kun tietotoiminto epäonnistuu.

* Tämä ominaisuus koskee vain **Muokattu lomake** -ohjausobjektia.

**OnReset** – Kuinka sovellus vastaa, kun **Muokattu lomake** -ohjausobjekti nollataan.

* Tämä ominaisuus koskee vain **Muokattu lomake** -ohjausobjektia.

**OnSuccess** – Kuinka sovellus vastaa, kun tietotoiminto onnistuu.

* Tämä ominaisuus koskee vain **Muokattu lomake** -ohjausobjektia.

**Tallentamaton** – Tosi, jos **Muokattu lomake** -ohjausobjekti sisältää käyttäjän tekemiä muutoksia, joita ei ole tallennettu.

* Tämä ominaisuus koskee vain **Muokattu lomake** -ohjausobjektia.
* Tällä ominaisuudella voit varoittaa käyttäjää ennen tallentamattomien tietojen menettämistä.  Voit estää käyttäjää valitsemasta eri tietuetta **[Valikoima](control-gallery.md)** -ohjausobjektissa ennen muutosten tallentamista nykyiseen tietueeseen, kun määrität valikoiman **[Poistettu käytöstä](properties-core.md)** -ominaisuuden arvoksi **Form.Unsaved** ja poistat päivitystoiminnot käytöstä.

**Päivitykset** – Lomakeohjausobjektiin ladatun tietueen arvot, jotka kirjoitetaan takaisin tietolähteeseen.  

* Tämä ominaisuus koskee vain **Muokattu lomake** -ohjausobjektia.
* Tämän ominaisuuden avulla voit poimia kenttäarvoja ohjausobjektin korteista.  Voit käyttää näitä arvoja tietolähteen manuaaliseen päivittämiseen **[Ohjelmakorjaus](../functions/function-patch.md)** -funktiokutsulla tai muulla yhteyden näyttämällä menetelmällä.  Tätä toimintoa ei tarvita, jos **[SubmitForm](../functions/function-form.md)** -funktio on käytössä.
* Ominaisuus palauttaa tietueen arvoista.  Jos lomake-ohjaus objekti sisältää esimerkiksi **nimi** -ja **määrä** -kenttien kortti-ohjaus objektin ja kyseisten korttien **[päivitys](control-card.md)** ominaisuuksien arvot palauttavat pienoissovelluksen ja 10: n, lomake-ohjaus objektin **päivitykset** -ominaisuus palauttaisi **{Name: "Widget"; määrä: 10}** .

**Valid** – Sisältääkö **[Kortti](control-card.md)** - tai **Muokattu lomake** -ohjausobjekti kelvollisia merkintöjä, jotka voidaan lähettää tietolähteeseen.

* Tämä ominaisuus koskee vain **Muokattu lomake** -ohjausobjektia.
* **Lomake**-ohjausobjektin **Valid**-ominaisuus koostaa kaikkien lomakkeen **[Kortti](control-card.md)** -ohjausobjektien **Valid**-ominaisuudet. Lomakkeen **Valid**-ominaisuuden arvo on **true** vain, jos lomakkeen kaikkien korttien tiedot ovat kelvollisia. Muussa tapauksessa **Valid**-ominaisuus on **false**.
* Voit määrittää painikkeen tallentamaan muutokset vain, jos lomakkeen tiedot ovat kelvollisia, mutta niitä ei ole vielä lähetetty, määrittämällä painikkeen **DisplayMode**-arvoksi seuraavan kaavan:
  
    **SubmitButton.DisplayMode = If(IsBlank( Form.Error ) || Form.Valid; DisplayMode.Edit; DisplayMode.Disabled)**

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Korkeus](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[Näkyvissä](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="more-information"></a>Lisätietoja
Kattavampi yleiskatsaus lomakkeiden toiminnasta on kohdassa [Tutustu tietolomakkeisiin](../working-with-forms.md).

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* Harkitse otsikon lisäämistä lomakkeeseen **[selitteen](control-text-box.md)** avulla.

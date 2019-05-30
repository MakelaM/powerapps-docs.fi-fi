---
title: Kortti-ohjausobjekti | Microsoft Docs
description: Tietoja korttien hallinnasta, mukaan lukien ominaisuudet ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: gregli
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: cc4338e37b7ecde2e2e2e9ad5c5ac6e96d116b58
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61559474"
---
# <a name="card-control-in-powerapps"></a>Korttien hallinta PowerAppsissa
Käsittää näytön ja muokkauksen **[Näytä lomake](control-form-detail.md)** - tai **[Muokkaa lomaketta](control-form-detail.md)** -ohjausobjektin yhdessä kentässä.

## <a name="description"></a>Kuvaus
**[Näytä lomake](control-form-detail.md)** - ja **[Muokkaa lomaketta](control-form-detail.md)** -ohjausobjektit toimivat säilöinä kokonaisten tietueiden näyttöä ja tarkastelua varten. Jokaiseen säilöön mahtuu joukko **Kortti**-ohjausobjekteja, jotka näyttävät yksittäisiä kenttiä tai tarjoavat tavan päivittää kyseiset kentät. Jokaisessa kortissa on **DataField**-ominaisuus, joka määrittää, mihin tietueen kenttään se vaikuttaa.  

Ennalta määritetyt kortit on määritetty eri tietotyyppejä ja käyttäjäkokemuksia varten.  Käytettävissä saattaa olla esimerkiksi kortti, joka muokkaa numerokenttää käyttäen **[Tekstisyöte](control-text-input.md)** -ohjausobjektia. Tämä sopii hyvin käytettäväksi näppäimistön avulla. Toinen kortti saattaa sen sijaan tukea numeron muokkaamista **[liukusäätimen](control-slider.md)** avulla. Kun lomakkeen ohjausobjekti on valittuna, voit helposti valita kortin oikeanpuoleisessa ruudussa kentän perusteella.

Itse kortit sisältävät ohjausobjekteja. Kortin ohjausobjektit määrittävät yhden kentän näyttöön ja muokkaamiseen liittyvän käyttökokemuksen. Esimerkiksi numerokortti voi koostua **[Selite](control-text-box.md)** -ohjausobjektista, jolla määritetään kentän näyttönimi ja **[Tekstisyöte](control-text-input.md)** -ohjausobjektista, joka tarjoaa editorin kentän arvon muokkaamista varten. Kortissa voi olla myös **[Nimi](control-text-box.md)** -ohjausobjekti, joka näyttää mahdolliset validointivirheet, sekä **[Nimi](control-text-box.md)** -ohjausobjekti tavalliselle tähdelle, joka ilmaisee, että kentän täyttämistä vaaditaan.

Voit mukauttaa ennalta määritetyn kortin ohjausobjekteja muuttamalla sen kokoa, siirtämällä sitä, piilottamalla sen, lisäämällä siihen ohjausobjekteja ja tekemällä muita muutoksia. Voit myös aloittaa täysin tyhjällä kortilla, ”mukautettavalla kortilla”, johon lisäät ohjausobjekteja alusta alkaen.

Ennalta määritetyt kortit on oletusarvoisesti *lukittu*. Voit muokata vain lukitun kortin tiettyjä ominaisuuksia tai ohjausobjekteja, etkä voi poistaa lukittua korttia. Voit nähdä, onko kortti lukittu, ja poistaa lukituksen käytöstä **Lisäasetukset**-näkymän **Näkymä**-välilehdessä. Jos ominaisuus on lukittu eikä sitä voi muokata, sen nimen vieressä näkyy lukkokuvake. Kortin lukituksen poistaminen on kehittynyt toimenpide ja sitä tulee käyttää varoen, koska kortin automaattinen kaavan muodostus ei enää toimi etkä voi lukita korttia uudelleen.

Lomakkeen säilössä on käytettävissä **ThisItem**-tietue, joka sisältää kaikki tietueen kentät.  Esimerkiksi kortin **[Default](properties-core.md)** -ominaisuuden arvoksi asetetaan usein **ThisItem**. *FieldName*.

Voit käyttää **ylätason** viittausta määrittämään ohjausobjektin viittaamaan kortin ominaisuuksiin.  Ohjausobjektin tulisi esimerkiksi käyttää **Parent.Default**-arvoa kentän alkuperäisen tilan lukemiseen tietolähteestä. Jos käytät **ylätasoa** sen sijaan, että käyttäisit tietoa suoraan, kortti on tiiviimpi ja voit muuttaa sen eri kenttään rikkomatta sisäisiä kaavoja.

Katso kohdasta [Tutustu tietokortteihin](../working-with-cards.md) esimerkkejä korttien mukauttamisesta, lukituksen poistamisesta ja korttien luomisesta.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**DataField** – Ilmaisee sen tietueessa olevan kentän nimen, jonka tämä kortti näyttää ja jota se muokkaa.

* Määritä nimi staattisena merkkijonona, joka on kirjoitettu lainausmerkkeihin (esimerkiksi **"Name"** ), ei kaavaa.
* Poista kortin sidonta määrittämällä sen **DataField**-ominaisuus *tyhjäksi*. Sitomattoman kortin ominaisuudet **Valid** ja **Update** ohitetaan.

**[Default](properties-core.md)** – Ilmaisee ohjausobjektin alkuarvon ennen käyttäjän siihen tekemiä muutoksia.

* Määritä tämän ominaisuuden arvoksi kortin kullekin ohjausobjektille **Parent.Default** viittaamaan tietolähteen mukaiseen kentän oletusarvoon. Voit esimerkiksi määrittää liukusäätimen **[Default](properties-core.md)** -ominaisuuden arvoksi **Parent.Default** sen varmistamiseksi, että käyttäjä aloittaa käyttämällä kyseisen liukusäätimen yleistä arvoa.

**DisplayMode** – Arvo voi olla **Muokkaa, Näytä** tai **Ei käytössä**. Määrittää kortissa olevan ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Muokkaa**) tai vain tarkastella tietoja (**Näytä**) vai onko ominaisuus kokonaan poissa käytöstä (**Ei käytössä**).  

* Sallii yksittäisen kortin käyttämisen lomakkeiden muokkaamiseen ja tarkastelemiseen muokkaamalla tätä ominaisuutta, joka on sidottu oletusarvoisesti lomakkeen käyttäytymiseen.
* **Näytä**-tilassa alitason ohjausobjektit, kuten **[Tekstisyöte](control-text-input.md)** , **[Avattava valikko](control-drop-down.md)** ja **[Päivämäärävalitsin](control-date-picker.md)** näyttävät vain tekstiarvon. Vuorovaikutteisia elementtejä tai muotoiluja ei esitetä.

**DisplayName** – Ilmaisee kentän kutsumanimen tietolähteessä.

* **[DataSourceInfo](../functions/function-datasourceinfo.md)** -funktio tarjoaa metatietoja tietolähteestä.
* Kortin ohjausobjekteille kannattaa käyttää arvoa **Parent.DisplayName** viittaamaan kentän nimeen.

**Error** – Käyttäjäystävällinen virhesanoma, joka näytetään, kun tämän kentän vahvistus epäonnistuu.

* Tämä ominaisuus määritetään, kun **SubmitForm** kutsutaan.  
* Viestissä kuvaillaan vahvistusongelmia, jotka perustuvat tietolähteen metatietoihin ja kortin **Required**-ominaisuuden tarkistukseen.

**Required** – Ilmaisee, onko kortilla oltava arvo tietolähteen kenttää muokattaessa.

* **[DataSourceInfo](../functions/function-datasourceinfo.md)** -funktio tarjoaa tarvittavia metatietoja tietolähteestä.
* Kortin ohjausobjekteille tulisi käyttää arvoa **Parent.Required** sen määrittämiseksi, onko kortin kyseinen arvo pakollinen.

**Päivitä** – Arvo, joka kirjoitetaan takaisin kentän tietolähteeseen.

* Käytä tämän ominaisuuden kaavaa noutaaksesi arvoja kortin muokkausohjausobjekteista takaisin tietolähteeseen kirjoittamista varten. Voit esimerkiksi määrittää kortin **Update**-ominaisuuden arvoksi **Slider.Value**, jolloin tietolähde päivitetään kyseisen kortin liukusäätimen arvolla.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[WidthFit](properties-size-location.md)**  – kasvaako ohjausobjekti automaattisesti vaakasuunnassa täyttämään tyhjän tilan säilön ohjausobjektissa, kuten **[Muokkaa lomaketta](control-form-detail.md)** -ohjausobjektissa. Jos monelle kortille on asetettu tämän ominaisuuden arvoksi **tosi**, tyhjä tila jaetaan niiden kesken. Lisätietoja on kohdassa [Tutustu tietolomakkeiden asetteluun](../working-with-form-layout.md).

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Täyttö](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**Valid** – Sisältääkö **Kortti**- tai **[Muokkaa lomaketta](control-form-detail.md)** -ohjausobjekti kelvollisia merkintöjä, jotka voidaan lähettää tietolähteeseen.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvissä vai piilossa.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys. Jos **[Kortti](control-card.md)** -ohjausobjekti on säilössä, jossa on useita sarakkeita, tämä ominaisuus määrittää sarakkeen, johon kortti tulee näkyviin.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys. Jos **[Kortti](control-card.md)** -ohjausobjekti on säilössä, jossa on useita rivejä, tämä ominaisuus määrittää rivin, johon kortti tulee näkyviin.

## <a name="examples"></a>Esimerkkejä
Tutustu esimerkkeihin kohdissa [Tutustu tietokortteihin](../working-with-cards.md) ja [Tutustu tietolomakkeiden asetteluun](../working-with-form-layout.md).


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **[Täyttö](properties-color-border.md)**  ja kaikki aliohjausobjektit. Jos kortti sisältää esimerkiksi **[selitteen](control-text-box.md)** , jonka täyttö on läpinäkyvä, kortin **[Täyttö](properties-color-border.md)** toimii käytännössä selitteen taustavärinä. Näin ollen kortin **[Täyttö](properties-color-border.md)** -objektin ja selitteen **[Väri](properties-color-border.md)** -objektin välisen kontrastin on oltava riittävä.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **DisplayName** on oltava olemassa.

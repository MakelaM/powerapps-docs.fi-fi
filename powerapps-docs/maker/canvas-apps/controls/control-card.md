---
title: Kortti-ohjausobjekti | Microsoft Docs
description: Tietoja korttien hallinnasta, mukaan lukien ominaisuudet ja esimerkkejä
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: gregli
ms.openlocfilehash: 7d44ba120a68d08f5779b8383df5b2263f228438
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="card-control-in-powerapps"></a>Korttien hallinta PowerAppsissa
Käsittää näytön ja muokkauksen **[Näytä lomake](control-form-detail.md)**- tai **[Muokkaa lomaketta](control-form-detail.md)** -ohjausobjektin yhdessä kentässä.

## <a name="description"></a>Kuvaus
**[Näytä lomake](control-form-detail.md)**- ja **[Muokkaa lomaketta](control-form-detail.md)** -ohjausobjektit toimivat säilöinä kokonaisten tietueiden näyttöä ja tarkastelua varten. Jokaiseen säilöön mahtuu joukko **kortti**-ohjausobjekteja, jotka näyttävät yksittäisiä kenttiä tai tarjoavat tavan päivittää kyseisten kenttien päivittämistä varten. Jokaisessa kortissa on **DataField**-ominaisuus, joka määrittää, mihin tietueen kenttään se vaikuttaa.  

Ennalta määritetyt kortit on määritetty eri tietotyyppejä ja käyttäjäkokemuksia varten.  Käytettävissä saattaa olla esimerkiksi kortti, joka muokkaa numerokenttää käyttäen **[tekstisyöte](control-text-input.md)**-ohjausobjektia. Tämä sopii hyvin käyttöön näppäimistön avulla. Toinen kortti ehkä tukee sen sijaan numeron muokkaamista **[liukusäätimen](control-slider.md)** avulla. Kun lomakkeen ohjausobjekti on valittuna, voit helposti valita kortin oikeanpuoleisessa ruudussa kentän perusteella.

Itse kortit sisältävät ohjausobjekteja. Kortin ohjausobjektit määrittävät yhden kentän näyttöön ja muokkaamiseen liittyvän käyttökokemuksen. Esimerkiksi numerokortti voi koostua **[selite](control-text-box.md)**-ohjausobjektista, jolla määritetään kentän näyttönimi ja **[tekstisyöte](control-text-input.md)**-ohjausobjektista, joka tarjoaa editorin kentän arvon muokkaamista varten. Kortissa voi olla myös **[selite](control-text-box.md)**-ohjausobjekti, joka näyttää mahdolliset validointivirheet ja **[selite](control-text-box.md)**-ohjausobjekti tavalliselle tähdelle, joka ilmaisee, että kentän täyttämistä vaaditaan.

Voit mukauttaa ennalta määritetyn kortin ohjausobjekteja muuttamalla sen kokoa, siirtämällä sitä, piilottamalla sen, lisäämällä siihen ohjausobjekteja ja tekemällä muita muutoksia. Voit myös aloittaa täysin tyhjiä kortilla, ”mukautettavalla kortilla”, johon lisäät ohjausobjekteja alusta alkaen.

Ennalta määritetyt kortit on oletusarvoisesti *lukittu*. Voit muokata vain lukitun kortin tiettyjä ominaisuuksia tai ohjausobjekteja etkä voi poistaa lukittua korttia. Voit nähdä, onko kortti lukittu ja poistaa lukituksen käytöstä **Lisäasetukset**-näkymän **Näkymä**-välilehdessä. Jos ominaisuus on lukittu, eikä sitä voi muokata, sen nimen vieressä näkyy lukkokuvake. Kortin lukituksen poistaminen on kehittynyt toimenpide ja sitä tulee käyttää varoen, koska kortin automaattinen kaavan muodostus ei enää toimi etkä voi lukita korttia uudelleen.

Lomakkeen säilössä on käytettävissä **ThisItem**-tietue, joka sisältää kaikki tietueen kentät.  Esimerkiksi kortin **[oletus](properties-core.md)**-ominaisuuden arvoksi asetetaan usein **ThisItem**. *FieldName*.

Voit käyttää **ylätason** viittausta määrittämään ohjausobjekti viittaamaan kortin ominaisuuksiin.  Esimerkiksi, ohjausobjektin tulisi käyttää **Parent.Default**-arvoa kentän alkuperäisen tilan lukemiseen tietolähteestä. Käyttämällä **ylätasoa** sen sijaan, että käyttäisit tietoa suoraan, kortti on tiiviimpi ja voit muuttaa sen eri kenttään rikkomatta sisäisiä kaavoja.

Katso kohdasta [Tutustu tietokortteihin](../working-with-cards.md) esimerkkejä korttien mukauttamisesta, lukituksen poistamisesta ja korttien luomisesta.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**DataField** – Sen tietueessa olevan kentän nimi, jonka tämä kortti näyttää ja jota se muokkaa.

* Määritä nimi staattisena merkkijonona, joka on kirjoitettu lainausmerkkeihin (esimerkiksi **"Name"**), ei kaavaa.
* Poista kortin sidonta määrittämällä sen **DataField**-ominaisuus *tyhjäksi*. Sitomattoman kortin ominaisuudet **Kelvollinen** ja **Päivitys** ohitetaan.

**[Default](properties-core.md)** – Ohjausobjektin alkuarvo, ennen kuin käyttäjä muuttaa sitä.

* Määritä tämän ominaisuuden arvoksi kortin kullekin ohjausobjektille **Parent.Default** viittaamaan tietolähteen mukaiseen kentän oletusarvoon. Voit esimerkiksi määrittää liukusäätimen **[oletus](properties-core.md)**-ominaisuuden arvoksi **Parent.Default** sen varmistamiseksi, että käyttäjä aloittaa käyttämällä kyseisen liukusäätimen yleistä arvoa.

**DisplayMode** – Arvo voi olla **Edit, View** tai **Disabled**. Määrittää kortissa olevan ohjausobjektin näyttötilan: onko käyttäjällä oikeus muokata (**Edit**) tai vain tarkastella tietoja (**View**) vai onko ominaisuus kokonaan poissa käytöstä (**Disabled**).  

* Sallii yksittäisen kortin käyttämisen lomakkeiden muokkaamiseen ja tarkastelemiseen muokkaamalla tätä ominaisuutta, joka on sidottu oletusarvoisesti lomakkeen käyttäytymiseen.
* **Näytä**-tilassa alitason ohjausobjektit, kuten **[tekstisyöte](control-text-input.md)**, **[avattava valikko](control-drop-down.md)** ja **[päivämäärävalitsin](control-date-picker.md)** näyttävät vain tekstiarvon. Vuorovaikutteisia elementtejä tai muotoiluja ei esitetä.

**DisplayName** – Kentän kutsumanimi tietolähteessä.

* **[DataSourceInfo](../functions/function-datasourceinfo.md)**-funktio tarjoaa metatietoja tietolähteestä.
* Kortin ohjausobjekteille kannattaa käyttää arvoa **Parent.DisplayName** viittaamaan kentän nimeen.

**Virhe** – Käyttäjäystävällinen virhesanoma, joka näytetään, kun tämän kentän vahvistus epäonnistuu.

* Tämä ominaisuus määritetään, kun **SubmitForm** kutsutaan.  
* Viestissä kuvaillaan vahvistusongelmia, jotka perustuvat tietolähteen metatietoihin ja kortin **pakollinen**-ominaisuuden tarkistukseen.

**Pakollinen** – Onko kortilla oltava arvo, tietolähteen kenttää muokattaessa.

* **[DataSourceInfo](../functions/function-datasourceinfo.md)**-funktio tarjoaa tarvittavia metatietoja tietolähteestä.
* Kortin ohjausobjekteille tulisi käyttää arvoa **Parent.Required** sen määrittämiseksi, onko kortin kyseinen arvo pakollinen.

**Päivitä** – Arvo, joka kirjoitetaan takaisin kentän tietolähteeseen.

* Käytä tämän ominaisuuden kaavaa noutaaksesi arvoja kortin muokkaus-ohjausobjekteista takaisin tietolähteeseen kirjoittamista varten. Voit esimerkiksi määrittää kortin **Päivitä**-ominaisuuden arvoksi **Slider.Value**, jolloin tietolähde päivitetään kyseisen kortin liukusäätimen arvolla.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[WidthFit](properties-size-location.md)**  – kasvaako ohjausobjekti automaattisesti vaakasuunnassa täyttämään tyhjän tilan säilön ohjausobjektissa, kuten **[Muokkaa lomaketta](control-form-detail.md)** -ohjausobjektissa. Jos monelle kortille on asetettu tämän ominaisuuden arvoksi **true**, tyhjä tila jaetaan niiden kesken. Lisätietoja on kohdassa [Tutustu tietolomakkeiden asetteluun](../working-with-form-layout.md).

## <a name="additional-properties"></a>Lisäominaisuudet
**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)**  – Onko ohjausobjektin reuna **Solid** (kiinteä), **Dashed** (katkoviiva), **Dotted** (pisteviiva) vai **None** (ei mitään).

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[Fill](properties-color-border.md)** – Ohjausobjektin taustaväri.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**Valid** – Sisältääkö **kortti** tai **[muokkaa lomaketta](control-form-detail.md)** -ohjausobjekti kelvollisia merkintöjä, jotka voidaan lähettää tietolähteeseen.

**[Visible](properties-core.md)** – Onko ohjausobjekti näkyvissä vai piilossa.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys. Jos **[Kortti](control-card.md)**-ohjausobjekti on säilössä, jossa on useita sarakkeita, tämä ominaisuus määrittää sarakkeen, johon kortti tulee näkyviin.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön (tai näytön, jos pääsäilöä ei ole) yläreunan välinen etäisyys. Jos **[Kortti](control-card.md)**-ohjausobjekti on säilössä, jossa on useita rivejä, tämä ominaisuus määrittää rivin, johon kortti tulee näkyviin.

## <a name="examples"></a>Esimerkkejä
Tutustu esimerkkeihin kohdissa [Tutustu tietokortteihin](../working-with-cards.md) ja [Tutustu tietolomakkeiden asetteluun](../working-with-form-layout.md).


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **[Täyttö](properties-color-border.md)**  ja kaikki aliohjausobjektit. Jos kortti sisältää esimerkiksi **[selitteen](control-text-box.md)**, jonka täyttö on läpinäkyvä, kortin **[Täyttö](properties-color-border.md)** toimii käytännössä selitteen taustavärinä. Näin ollen kortin **[Täyttö](properties-color-border.md)**-objektin ja selitteen **[Väri](properties-color-border.md)**-objektin välisen kontrastin on oltava riittävä.

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **DisplayName** on oltava olemassa.

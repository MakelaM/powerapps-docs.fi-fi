---
title: Kangas sovellusten helppokäyttöominaisuudet | Microsoft Docs
description: Viite tietoja ominaisuuksista, kuten Tabindeksistä ja työkalu vihjeestä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/26/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e1baf96ab96dc6fe783fccdf243c0ae4ba6d0c1d
ms.sourcegitcommit: b4df7d781cda50dfe2f6609f1cc4d2b531428b3c
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/29/2019
ms.locfileid: "70161277"
---
# <a name="accessibility-properties-for-canvas-apps"></a>Kangas sovellusten helppokäyttöominaisuudet

Ominaisuuksia, jotka on määritetty auttamaan toimintarajoitteisia ihmisiä käyttämään ohjausobjekteja.

## <a name="properties"></a>Ominaisuudet

**AccessibleLabel** – Näytönlukuohjelmien käyttämä selite. Jos kuvan, kuvakkeen tai muodon ohjausobjektin kohdalla on tyhjä arvo, ohjausobjekti piilotetaan näytönlukijalta ja sitä käsitellään muotoiluna.

**Live** – miten näytön luku ohjelmien pitäisi ilmoittaa sisältöön tehdyistä muutoksista. Käytettävissä vain **[Selite](control-text-box.md)** -ohjaus objektissa.

* Kun asetus on ei **käytössä**, näytön luku ohjelma ei ilmoita muutoksista.
* Kun asetus on **kohtelias**, näytönlukija lopettaa puhumisen ennen näytön luku ohjelman puhumisen aikana tapahtuneiden muutosten ilmoittamista.
* Kun asetus on **vakuuttava**, näytönlukija keskeyttää itsensä ilmoittaakseen muutoksista, jotka tapahtuivat näytön luku ohjelman puhuttua.

Opi ilmoittamaan [Dynaamiset muutokset reaaliaikaisilla alueilla](../accessible-apps-live-regions.md).

**Tabdex** – määrittää, onko ohjaus objekti osa näppäimistö siirtymistä.

Näppäimistö siirtyminen on tärkeä osa mitä tahansa sovellusta.  Monille näppäimistö on tehokkaampi kuin kosketus käyttö tai hiiri, ja se mahdollistaa näkövammaisten näytön luku ohjelmat.  Siirtymis järjestyksen tulee:
- Peilaa, mitä visuaalisesti nähdään.
- Vain vuorovaikutteisissa ohjaus objekteissa on SARKAIN kohta.
- Seuraa joko intuitiivinen-kohtaa ja sitten alas "Z"-järjestystä tai alas ja sitten yli "käänteinen-N" järjestyksessä.

Yllä olevat vaatimukset on täytetty käyttäen oletus arvoista **Tabindexes** -arvoa, ja suosittelemme, että et muuta niitä.  Oletus arvo on se, mitä useimmat käyttäjät odottavat visuaalisesti, ja se toimii hyvin näytön luku ohjelman kanssa.  Saattaa kuitenkin olla tilanteita, joissa haluat ohittaa Oletus arvon.  Voit tehdä muutoksia siirtymis järjestykseen **Tabdex** -ominaisuuden ja [ **parannetun Group** -ohjaus objektin](https://powerapps.microsoft.com/en-us/blog/enhanced-group-experimental-control-with-layout-control-and-nesting/) (kokeellinen) avulla.  

**Tabdex** -ominaisuudella on kaksi suositeltua arvoa:

| Tabdex-arvo | Toiminta | Oletus arvo kohteelle |
|----------------|----------|-------------|
| 0 | Ohjaus objekti osallistuu näppäimistö navigointiin. | [**Painikkeen**](control-button.md), [**tekstin syötön**](control-text-input.md), [**yhdistelmä ruudun**](control-combo-box.md)ja muiden yleensä vuorovaikutteisten ohjaus objektien välillä. |
| &minus;1 | Ohjaus objekti ei osallistu näppäimistö navigointiin. | [**Otsikko**](control-text-box.md), [**kuva**](control-image.md), [**kuvake**](control-shapes-icons.md)ja muut yleensä ei-vuorovaikutteiset ohjaus painikkeet. |

Siirtymis järjestys kulkee yleensä vasemmalta oikealle ja sitten ylhäältä alas "Z"-rakenteessa. Järjestys perustuu ohjaus objektien **X** -ja **yn** -ominaisuus arvoihin. Jos ohjaus objekteilla siirretään dynaamisesti näytössä esimerkiksi kaavan **X** -tai y:lle, joka perustuu ajastimeen tai muuhun ohjaus objektiin, myös siirtymis järjestys muuttuu dynaamisesti.

Käytä [ **parannettua Group** Control](https://powerapps.microsoft.com/en-us/blog/enhanced-group-experimental-control-with-layout-control-and-nesting/) (experimental)-menetelmää niputtaa ohjaus objekteista, jotka tulee yhdistää yhteen, tai luoda sarakkeita käänteis-N-malliin.  Seuraavan esimerkin yläosassa olevat nimi kentät sisältyvät laajennettuun ryhmä ohjaus objektiin, joka saa siirtymisen siirtymään alaspäin ennen siirtymistä.  Esimerkin alaosassa ei käytetä ryhmä ohjaus objektia, ja siirtyminen etenee normaalisti ja alas normaalisti, mikä ei ole intuitiivista ohjaus objektien ryhmittelyjen vuoksi. 

![Animaatio, joka näyttää parannetun ryhmän ohjaus objektin, joka aiheuttaa siirtymisen alaspäin ryhmässä ennen siirtymistä](media/properties-accessibility/enhanced-group.gif)

Samoin tabbing säilöjen, kuten [**lomakkeiden**](control-form-detail.md) ja [**valikoima**](control-gallery.md) -ohjaus objektien, kautta siirtyvät kaikki säiliön elementit ennen kuin siirrytään seuraavaan ohjaus objektiin, joka on säiliön ulkopuolella.  

Ohjaus objektien, joiden **näkyvä** -ominaisuuden arvo on *false* tai Disabled **DisplayMode** -ominaisuuden arvo on **poistettu käytöstä** , ei sisällytetä siirtymis kohtaan.  

Kun käytät selainta, siirtyminen näytön viimeisestä ohjaus objektista siirtyy selaimen sisäänrakennettuihin ohjaus objekteihin, kuten URL-osoitteeseen.  

> [!WARNING]
> Vältä **Tabdex** -arvoja, jotka ovat suurempia kuin 0. Viime kädessä kontrollit hahmonnetaan HTML-muodossa, jossa myös [W3C on varoittanut](https://www.w3.org/TR/wai-aria-practices/#kbd_general_between) "KIRJOITTAJIA kehotetaan olemaan käyttämättä näitä arvoja." Monet HTML-työkalut varoittavat arvoja, jotka ovat suurempia kuin 0, kuten [sovelluksen tarkistus toiminto](../accessibility-checker.md) ilmoittaa, kun se raportoi "Tarkista näyttö kohteiden järjestys".  Kaikki on hyvästä syystä: käyttämällä **Tabindextä** tällä tavalla voi olla hyvin vaikea saada oikeutta ja tehdä avustavien tekniikoiden, kuten näytönlukijoiden, käyttökelvottomia.
> 
> Kun ohjaus objektien olemassa on suurempi kuin 0, käyttäjät siirtyvät ohjaus objekteihin, joissa on yhä **TabIndex** -arvoja (1, sitten 2 jne.). Kun käyttäjät ovat suunnistaa kaikki ohjaus objektit positiivisilla **tabindexes** -arvoilla, he siirtyvät lopulta ohjaus objekteihin, joissa on 0, mukaan lukien selaimen sisäiset ohjaus objektit. Kun samassa **Tabindexissä**on useita ohjaus objektin, niiden **X** -ja **Y** -sijainnit määrittävät suhteellisen järjestyksen.






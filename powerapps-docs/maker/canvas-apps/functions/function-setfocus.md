---
title: SetFocus-funktion | Microsoft Docs
description: Powerappsin SetFocus-funktion viite tiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 08/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fce0148e77432aa136a6279eb7fb69c0ca3b0846
ms.sourcegitcommit: de77b6d5f77e84961fff9a399622ba8eeb48d4c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037048"
---
# <a name="setfocus-function-in-powerapps"></a>SetFocus-funktion Powerappsissa
Siirtää syöte kohdistuksen tiettyyn ohjaus objektiin. 

## <a name="description"></a>Kuvaus
**SetFocus** -funktiolla hallitaan syöte kohdistusta.  Tämä ohjaus objekti vastaanottaa käyttäjän näppäin painallukset, jolloin he voivat kirjoittaa teksti syöte-ohjaus objektiin tai valita painikkeen *ENTER* -näppäimen avulla.  Käyttäjä voi myös siirtää syöte kohdistuksen itse käyttämällä *SARKAIN* -näppäintä, kosketus näyttöä, hiirtä tai muuta liikettä. *Sarkaimen* toimintaa säätelee [ **tabindexty** -ominaisuus](../controls/properties-accessibility.md).

Aseta kohdistus **SetFocus** -funktiolla, kun (kukin esimerkki alla):
- Äskettäin suojaamaton tai käytössä oleva syöte ohjaus objekti, joka opastaa käyttäjää seuraavassa ja nopeammassa tietojen syötössä.
- lomake on vahvistettu, jotta se voidaan keskittää ja näyttää ongelman aiheuttava syöte-ohjaus objekti nopeaa ratkaisemista varten.
- näyttöön tulee näyttö, joka keskittää ensimmäisen syöte ohjaus objektin [**näytön**](../controls/control-screen.md) **onvisible** -ominaisuuteen.

Kohdistuksen ohjaus objekti voi olla visuaalisesti erilainen [**Focusedbordercolor**](../controls/properties-color-border.md) -ja [**Focusedborderpaksuus**](../controls/properties-color-border.md) -ominaisuuksien perusteella.

## <a name="limitatoins"></a>Limatowins

**SetFocus** -kohdetta voi käyttää vain:
- [**Painike**](../controls/control-button.md) -ohjaus objekti
- [**Kuvakkeen**](../controls/control-shapes-icons.md) ohjaus objekti
- [**Kuva**](../controls/control-image.md) -ohjaus objekti
- [**Nimi**](../controls/control-text-box.md)-ohjausobjekti
- [**TextInput**](../controls/control-text-input.md) -ohjaus objekti

Et voi määrittää kohdistusta ohjaus objekteille, jotka kuuluvat [**valikoima**](../controls/control-gallery.md) -ohjaus objektiin, [**Muokkaa lomaketta**](../controls/control-form-detail.md) -ohjaus objektiin tai [osaan](../create-component.md).  **SetFocus** -toimintoa voidaan käyttää ohjaus objektin kanssa scrollbale-näytössä.

Voit määrittää kohdistuksen ohjaus objekteille, jotka ovat samassa näytössä kuin **SetFocus** -kutsun sisältävä kaava.

Jos yrität määrittää kohdistuksen ohjaus objektiin, jonka [**DisplayMode**](../controls/properties-core.md) -ominaisuudeksi on määritetty **poistettu käytöstä** , ei ole vaikutusta.  Kohdistus säilyy, kun se oli aiemmin.

Apple iOS:ssä pehmeä näppäimistö näytetään automaattisesti vain, jos **SetFocus** aloitettiin suoralla käyttäjä toiminnolla.  Esimerkiksi painikkeen **onselect** -ominaisuudesta käynnistäminen näyttää pehmeän näppäimistön, kun se kutsuu näytön **onvisible** -kohteesta. 

Voit käyttää **SetFocus** -toimintoa vain [toiminta kaavoissa](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaksi
**SetFocus** ( *Ohjaus objekti* )

* *Control* – Pakollinen.  Ohjaus objekti, joka antaa syöte kohdistuksen.

## <a name="examples"></a>Esimerkkejä

### <a name="focus-on-a-newly-exposed-or-enabled-input-control"></a>Keskity äskettäin avoimena olevaan tai käytössä olevaan syöte ohjaus objektiin

Monet ostos kärryt sallivat asiakkaan käyttää toimitus osoitetta laskutus osoitteena, mikä lieventää tarvetta antaa samat tiedot kahdesti.  Jos haluat käyttää eri laskutus osoitetta, laskutus osoitteen teksti syöte ruudut ovat käytössä, ja on hyödyllistä ohjata asiakasta näihin juuri käytössä oleviin ohjaus objekteihin nopeampaan tietojen syöttämiseen.  

![Animaatio, joka koskee mukautetun laskutus osoitteen valitsemista, kun kohdistus on siirretty laskutuksen nimi-syöte-ohjaus objektiin, jolloin automaattinen synkronointi ei ole käytössä toimitus osoitteiss-toiminnolla](media/function-setfocus/shipping-billing.gif)

Tässä pelissä on monia kaavoja, mutta kohdistus on **valinta ruutu** -ohjaus objektin **onuncheck** -ominaisuudessa:

```powerappa-dot
SetFocus( BillingName ) 
```

*Sarkaimen* avulla voidaan myös siirtää kohdistusta nopeasti kentästä toiseen.  Jos haluat havainnollistaa sitä paremmin, *SARKAINTA* ei käytetty animaatiossa.

Tämän esimerkin luominen:
1. Luo uusi sovellus.
1. Lisää nimi- [ ohjaus objekteihin](../controls/control-text-box.md) teksti "toimitus osoite", "nimi:", "Osoite:", "laskutus osoite", "nimi:" ja "Osoite:" ja sijoita ne animaatiossa esitetyllä tavalla.
1. Lisää [ **teksti syöte** -ohjaus objekti](../controls/control-text-input.md) ja nimeäse uudelleen.
1. Lisää [ **teksti syöte** -ohjaus objekti](../controls/control-text-input.md) ja nimeäse uudelleen.
1. Lisää [ **valinta ruutu** -ohjaus objekti](../controls/control-check-box.md) ja nimeä sen **syncaddresses**uudelleen.
1. Määrittää tämän ohjaus objektin **Text** -ominaisuudeksi kaavan `"Use Shipping address as Billing address"`.
1. Lisää [ **teksti syöte** -ohjaus objekti](../controls/control-text-input.md) ja nimeä se uudelleen **nimellä billingname**.
1. Määrittää tämän ohjaus objektin **oletus** ominaisuudeksi kaavan `ShippingName`.
1. Voit määrittää tämän ohjaus objektin **DisplayMode** -ominaisuudeksi `If( SyncAddresses.Value, DisplayMode.View, DisplayMode.Edit )`kaavan.  Tämä ottaa tämän ohjaus objektin automaattisesti käyttöön tai poistaa sen käytöstä valinta ruutu-ohjaus objektin tilan perusteella.
1. Lisää [ **teksti syöte** -ohjaus objekti](../controls/control-text-input.md) ja anna sille nimeksi **billingaddress**.
1. Määrittää tämän ohjaus objektin **oletus** ominaisuudeksi kaavan `ShippingAddress`.
1. Voit määrittää tämän ohjaus objektin **DisplayMode** -ominaisuudeksi `If( SyncAddresses.Value, DisplayMode.View, DisplayMode.Edit )`kaavan.  Tämä ottaa tämän ohjaus objektin automaattisesti käyttöön tai poistaa sen käytöstä valinta ruutu-ohjaus objektin tilan perusteella.
1. Valitse valinta ruudun **oletus** ominaisuudeksi kaava `true`.  Oletus arvon mukaan laskutus osoite käyttää samaa arvoa kuin toimitus osoite.
1. Valitse valinta ruudun **onCheck** -ominaisuudeksi kaava `Reset( BillingName ); Reset( BillingAddress )`.  Jos käyttäjä haluaa synkronoida toimitus-ja laskutus osoitteita, se tyhjentää kaikki käyttäjän syötettä laskutus osoite-kenttiin, jolloin niiden **oletus** ominaisuudet ovat samat kuin vastaavien toimitus osoite kenttien arvot.
1. Valitse valinta ruudun **Onunpoista** -ominaisuudeksi kaava `SetFocus( BillingName )`.  Jos käyttäjä haluaa käyttää eri laskutus osoitetta, kohdistus siirretään laskutus osoitteen ensimmäiseen ohjaus objektiin.  Ohjaimet on jo otettu käyttöön **DisplayMode** -ominaisuuksien vuoksi.

### <a name="focus-on-validation-issues"></a>Keskity vahvistus ongelmiin

> [!NOTE]
> Vaikka tämä esimerkki vaikuttaa olevan **muokkaus lomake** -ohjaus objekti, kyseinen ohjaus objekti ei valitettavasti vielä tue **SetFocus** -toimintoa.  Sen sijaan tässä esimerkissä käytetään vieritettävää näyttöä syöte ohjaus objektien isännöintiin.

Kun lomaketta vahvistetaan, voi olla hyödyllistä, että sanoma näytetään vain, jos ongelma on olemassa, mutta käyttäjä voi myös viedä käyttäjän kenttään, joka on loukkaava.  Tästä voi olla hyötyä erityisesti silloin, jos kyseinen kenttä vieritetään pois näytöstä, eikä se ole näkyvissä.

![Animaatio, joka vahvistaa tietojen syöttö lomakkeen, mutta ei ainoastaan näytetyn sanoman, vaan myös määrittää syöte kohdistuksen loukkaavan syötteen ohjaus objektiin, vaikka se olisi vieritetty näytöstä.](media/function-setfocus/scrollable-screen.gif)

Tässä animaatiossa vahvistus painiketta painetaan toistuvasti, kunnes kaikki kentät on täytetty oikein.  Ota huomioon, että hiiren osoitin ei siirry alas näytön yläreunasta.   Sen sijaan **SetFocus** -funktiolla on siirretty kohdistus ohjaus objektiin, joka vaatii huomiota tällä kaavalla:

```powerapps-dot
If( IsBlank( Name ), 
        Notify( "Name requires a value", Error ); SetFocus( Name ),
    IsBlank( Street1 ), 
        Notify( "Street Address 1 requires a value", Error ); SetFocus( Street1 ),
    IsBlank( Street2 ), 
        Notify( "Street Address 2 requires a value", Error ); SetFocus( Street2 ),
    IsBlank( City ), 
        Notify( "City requires a value", Error ); SetFocus( City ),
    IsBlank( County ), 
        Notify( "County requires a value", Error ); SetFocus( County ),
    IsBlank( StateProvince ), 
        Notify( "State or Province requires a value", Error ); SetFocus( StateProvince ),
    IsBlank( PostalCode ), 
        Notify( "Postal Code requires a value", Error ); SetFocus( PostalCode ),
    IsBlank( Phone ), 
        Notify( "Contact Phone requires a value", Error ); SetFocus( Phone ),
    Notify( "Form is Complete", Success )
)
```

Tämän esimerkin luominen:
1. Luo uusi, tyhjä Puhelin sovellus.
1. Valitse **Lisää** -valikosta **Uusi näyttö**ja valitse sitten **vieritettävä**.
1. Lisää näytön Keski osassa **teksti syöte** -ohjaus objekti ja anna sille nimeksi **nimi**, **Street1**, **Street2**, **kaupunki**, **maakunta**, osavaltio, **Posti numero**ja **Puhelin**numero. Voit tunnistaa kentät lisäämällä niiden yläpuolelle **Selite** -ohjaus objektin.  Saatat joutua muuttamaan osan kokoa, jos se ei ole tarpeeksi pitkä sopimaan kaikkiin ohjaus objekteihin.
1. Lisää valinta merkki [ **kuvake** ohjaus objekti](../controls/control-shapes-icons.md) näytön yläreunaan vieritettävän osan yläpuolelle.  
1. Määritä Icon-ohjaus objektin **onselect** -ominaisuudeksi yllä esitetty `If( IsBlank( ...` kaava.

### <a name="focus-when-displaying-a-screen"></a>Kohdistus, kun näyttö näytetään

> [!NOTE]
> Vaikka tämä esimerkki vaikuttaa olevan **muokkaus lomake** -ohjaus objekti, kyseinen ohjaus objekti ei vielä tue Unforunatley **SetFocus** -kohdetta.  Sen sijaan tässä esimerkissä käytetään vieritettävää näyttöä syöte ohjaus objektien isännöintiin.

Samalla tavalla kuin syöte-ohjaus objektin altistaminen, kun tietojen syöttö näyttö näytetään, on hyödyllistä keskittää ensimmäinen syöte ohjaus objekti nopeampaan tietojen syöttämiseen.

![Animaatio, joka näyttää vierekkäin verrattuna SetFocus-toiminnon käyttämiseen, ei käytä sitä, kun se näyttää tietojen syöttö näytön](media/function-setfocus/visible-setfocus.gif)

Tässä animaatiossa vasemmalla oleva tietojen syöttäminen-näyttö ei käytä **SetFocus**-toimintoa.  Kun näyttö ei ole syöte-ohjaus objekti on kohdistus, joka edellyttää, että käyttäjä on Tab, kosketa, hiiri tai käytä toista keinoa keskittää **nimi** -kenttä, ennen kuin arvo voidaan kirjoittaa siihen.

Oikealla on täsmälleen sama sovellus, jossa on Data Entry-näytön **Onvisible** -ominaisuus, joka on määritetty tähän kaavaan:

```powerapps-dot
SetFocus( Name )
```

Tämä asettaa kohdistuksen **nimi** -kenttään automaattisesti.  Käyttäjä voi aloittaa kirjoittamisen ja tabbing kenttien välillä välittömästi ilman edeltävää toimintoa.

Tämän esimerkin luominen:
1. Luo yllä oleva Focus on validation-ongelmat-sovellus.
1. Valitse tässä näytössä **Onvisible** -ominaisuudeksi kaava `SetFocus( Name )`.
1. Lisää toinen näyttö.
1. Lisää [ **painike** -ohjaus objekti](../controls/control-button.md).
1. Määritä tämän ohjaus objektin **onselect** -ominaisuudeksi kaava `Navigate( Screen1 )`.
1. Esikatsele sovellusta tästä näytöstä.  Paina painiketta.  **Onvisible** -kaava lasketaan, ja **nimi** -kenttä on automaattisesti kohdistettuna.

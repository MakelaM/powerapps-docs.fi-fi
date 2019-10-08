---
title: Astynpe-ja IsType-Funktiot kangas sovelluksissa | Microsoft Docs
description: Viite tiedot, mukaan lukien syntaksi ja esimerkki, Astynpe-ja IsType-funktioille kangas sovelluksissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/17/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0ecb30a5a452a6ee092ccf9bc9d47f6182ef60ab
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992988"
ms.PowerAppsDecimalTransform: true
---
# <a name="astype-and-istype-functions-in-canvas-apps"></a>Astynpe-ja IsType-Funktiot kangas sovelluksissa

Tarkistaa määritetyn entiteettityypin (**Istype**) tietue viittauksen ja käsittelee viitta uksen määritetyllä tyyppinä (**astynpe**).

## <a name="description"></a>Kuvaus

Lue Tutustu [tietue viittauksiin ja polymorfisten hakujen](../working-with-references.md) laajempaan käyttöönottoon ja lisä tietoihin.

Haku kenttä viittaa yleensä tietyn entiteetin tietue isiin. Koska entiteettityyppi on vakiintunut, voit käyttää haku kenttiä yksinkertaisen piste merkinnän avulla. Esimerkiksi **First (accounts). Ensisijainen yhteys henkilö. Koko nimi** kulkee **accounts** -entiteetistä **yhteys tiedot** -entiteetin **ensisijaiseen yhteyshenkilö** tietueeseen ja poimii **koko nimi** -kentän.

Common Data Service tukee myös polymorfisiä haku kenttiä, jotka voivat tarkoittaa entiteettien joukosta perä isin olevia tietueita, kuten Näissä esimerkeissä.

| Haku kenttä | Voi tarkoittaa |
|--------------|--------------|
| **Omistaja** | **Käyttäjät** tai **tiimit** |
| **Asiakas** | **Asiakkaat** tai **yhteys henkilöt** |
| **Koskevat** | **Asiakkaat**, **yhteys henkilöt**, **tietämys artikkelit**jne. |

<!--note from editor: Change "Knowledge Articles" to "Knowledge Base articles" if that is what is being referenced.   -->

Canvas-App-kaavoissa voit käyttää tietue viittauksia, jotka toimivat polymorfisten hakujen kanssa. Koska tietue viittaus voi viitata eri entiteetteihin, et tiedä, mitkä kentät ovat käytettävissä, kun kirjoitat kaavaa. *. Kentän* merkintä ei ole käytettävissä. Näiden kaavojen on mukauduttava tietue isiin, joita sovellus kohtaa, kun se suoritetaan.

**Istype** -funktiolla testataan, viittaanko tietue viittaus tiettyyn entiteettityypin. Funktio palauttaa totuus arvon TRUE tai FALSE.

**Asttype** -funktiolla käsitellään tietue viittausta tiettynä entiteettityypinä, jota kutsutaan joskus myös *valu*-kohteeksi. Voit käyttää Tulosta ikään kuin se olisi tietue entiteetistä ja käyttää sitten kohdetta *. Kentän* merkintä, joka käyttää kaikkia kyseisen tietueen kenttiä. Virhe ilmenee, jos viittaus tyyppi ei ole määritetty.

Käytä näitä funktioita yhdessä, testaa ensin tietueen entiteettityyppiä ja käsittele se sitten kyseisen tyypin tietueena niin, että kentät ovat käytettävissä:

```powerapps-comma
If( IsType( First( Accounts ).Owner; Users );
    AsType( First( Accounts ).Owner; Users ).'Full Name';
    AsType( First( Accounts ).Owner; Teams ).'Team Name'
)
```

Tarvitset näitä funktioita vain, jos käytät tietue viittauksen kenttiä. Voit esimerkiksi käyttää [**Filter**](function-filter-lookup.md) -funktion tietue viittauksia ilman istype-tai **astynpe** -funktioita:

```powerapps-comma
Filter( Accounts; Owner = First( Users ) )
```

Voit käyttää myös tietue viittauksia [**patch**](function-patch.md) -funktiolla:

```powerapps-comma
Patch( Accounts; First( Accounts ); { Owner: First( Teams ) } )
```  

Jos käytetään tietue kontekstia, kuten [**valikoiman**](../controls/control-gallery.md) tai [**Muokkaa lomaketta**](../controls/control-form-detail.md) -ohjaus objektin kanssa, sinun on ehkä käytettävä [yleistä täsmennys operaattoria](operators.md#disambiguation-operator) entiteettityypin viittaamiseksi. Tämä kaava olisi esimerkiksi tehokas valikoima, joka näyttää luettelon yhteys henkilöistä, joissa **yrityksen nimi** on **asiakas** haku:

```powerapps-comma
If( IsType( ThisItem.'Company Name'; [@Accounts] );
    AsType( ThisItem.'Company Name'; [@Accounts] ).'Account Name';
    AsType( ThisItem.'Company Name'; [@Contacts] ).'Full Name'
)
```

Molemmissa funktioissa voit määrittää tyypin entiteettiin yhdistetyn tieto lähteen nimen kautta. Jotta kaava toimisi, sinun on myös lisättävä sovellukseen tieto lähde mille tahansa tyypille, jota haluat testata tai luoda. Sinun on esimerkiksi lisättävä **käyttäjät** -entiteetti tieto lähteeksi, jos haluat käyttää istype-ja **astype** - tietoja **omistaja** haun ja kyseisen entiteetin tietueiden kanssa. Voit lisätä vain tieto lähteitä, joita itse käytät sovelluksessasi. sinun ei tarvitse lisätä kaikkia entiteettejä, joihin haku voi viitata.

Jos tietue viittaus on *tyhjä*, istype palauttaa arvon FALSE, ja **astynpe** palauttaa *tyhjän*. Kaikki *tyhjän* tietueen kentät ovat *tyhjiä*.

## <a name="syntax"></a>Syntaksi

**Asttype**( *recordreference*; *EntityType* )

- *Recordreference* – pakollinen. Tietue viittaus, joka on usein haku kenttä, joka voi viitata minkä tahansa useamman entiteetin tietueeseen.
- *EntityType* – pakollinen. Tietty entiteetti, jolle testataan.

**Istype**( *recordreference*; *EntityType* )

- *Recordreference* – pakollinen. Tietue viittaus, joka on usein haku kenttä, joka voi viitata minkä tahansa useamman entiteetin tietueeseen.
- *EntityType* – pakollinen. Tietty entiteetti, johon tietue tulee lähettää.

## <a name="example"></a>Esimerkki

[Tutustu tietue viittauksiin ja polymorfisiin](../working-with-references.md) hakuihin sisältää laajoja esimerkkejä.

1. Luo tyhjä kangas sovellus tableteille.

1. Valitse **näkymä** -väli lehdeltä **tieto lähteet**ja lisää sitten **yhteys tiedot** -ja **accounts** -entiteetit tieto lähteinä.
    > [!div class="mx-imgBorder"]
    > @no__t – 0Tyhjä sovellus, jossa on kaksi tieto lähdettä: asiakkuudet ja yhteys henkilöt @ no__t-1

1. Lisää **valikoima** -ohjaus objekti, jossa on **tyhjä pystysuuntainen** suunta.

    > [!div class="mx-imgBorder"]
    > ![Lisää valikoima-ohjaus objekti, jossa on tyhjä pystysuuntainen ulkoasu @ no__t-1

1. Valitse **Ominaisuudet** -väli lehden näytön oikean puolen lähellä olevan valikoiman **kohteet** -ominaisuudeksi **yhteys tiedot**.

    > [!div class="mx-imgBorder"]
    > ![kohteiden lisääminen yhteys tietoihin ominaisuudet-ruudussa @ no__t-1

1. Valitse valikoiman asetteluksi **otsikko ja alaotsikko**.

    > [!div class="mx-imgBorder"]
    > ![Avaa asemointi valitsin ominaisuudet-ruudusta @ no__t-1

    > [!div class="mx-imgBorder"]
    > ![Valitse asetteluksi title ja Subtitle @ no__t-1

1. Avaa **tiedot** -ruudussa **Title1** -lista ja valitse sitten **koko nimi**.

    > [!div class="mx-imgBorder"]
    > ![Sarjan otsikon arvo @ no__t-1

1. Valitse **Subtitle1** -otsikko-ohjaus objekti.

    > [!div class="mx-imgBorder"]
    > ![Valitse tekstityksen arvo @ no__t-1

1. Valitse **Subtitle1** **Text** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    If( IsBlank( ThisItem.'Company Name' ); "--";
        IsType( ThisItem.'Company Name'; [@Accounts] );
            "Account: " & AsType( ThisItem.'Company Name'; [@Accounts] ).'Account Name';
        "Contact: " & AsType( ThisItem.'Company Name'; [@Contacts] ).'Full Name'
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Screen on nyt valmis, sillä asiakkaat ja yhteys henkilöt näkyvät valikoimassa @ no__t-1

    Valikoiman alaotsikko sisältää seuraavat arvot:
    - "--" Jos **yrityksen nimi** on *tyhjä*.
    - "Tili:" ja sitten tilin **nimi** -kenttä **accounts** -entiteetistä, jos **yrityksen nimi** -kenttä viittaa tiliin.
    - "Contact:" ja sitten **koko nimi** -kenttä **yhteys tiedot** -entiteetistä, jos **yrityksen nimi** -kenttä viittaa yhteys tietoon.

    Tulokset saattavat poiketa tästä aiheesta, koska se käyttää malli tietoja, joita muokattiin näyttämään lisää tulos tyyppejä.

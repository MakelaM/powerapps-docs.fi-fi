---
title: AsType ja IsType funktioiden pohjaan perustuvien sovellusten | Microsoft Docs
description: Viitetiedot, mukaan lukien syntaksi ja Esimerkki AsType ja IsType-funktioiden pohjaan perustuvia sovelluksia
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/17/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 999653159f838e840f7f569aa9953633a6a70065
ms.sourcegitcommit: 93096dfa1aadba77159db1e5922f3d5528eecb7a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/21/2019
ms.locfileid: "65986320"
---
# <a name="astype-and-istype-functions-in-canvas-apps"></a>AsType ja IsType funktioiden pohjaan perustuvia sovelluksia

Määritetyn entiteettityypin tietueen viittaus tarkistaa (**IsType**) ja käsittelee viittaus tietyn tyypin (**AsType**).

## <a name="description"></a>Kuvaus

Lue [ymmärtämään tietueen viittaukset ja polymorfinen hakuja](../working-with-references.md) laajempi esittelyn ja lisätietoja.

Hakukentän viittaa yleensä tietyn entiteetin tietueet. Kohteen tyyppi on hyvin muodostettu, voit käyttää haun kentät käyttämällä yksinkertaisia piste-merkintätapaa. Esimerkiksi **ensimmäisen (tiliä) ”. Ensisijainen yhteyshenkilö ' ”. Koko nimi ”** Ohjaa **tilit** entiteetti **ensisijaisen yhteyshenkilön** tietue **yhteystiedot** entiteetin ja otteet **KokoNimi**  kenttä.

Common Data Service tukee myös polymorfinen hakukenttiä, jotka voivat viitata tietueita entiteettien, kuten näissä esimerkeissä joukosta.

| Hakukenttä | Voit viitata |
|--------------|--------------|
| **Omistaja** | **Käyttäjien** tai **ryhmät** |
| **Asiakas** | **Tilien** tai **yhteystiedot** |
| **Liittyy** | **Tilien**, **yhteystiedot**, **tietoartikkelit**jne. |

<!--note from editor: Change "Knowledge Articles" to "Knowledge Base articles" if that is what is being referenced.   -->

Pohjaan perustuvien sovellusten kaavoissa polymorfinen hakuja käsitellä tietueen viittausten avulla. Koska tietueen viittaus voi viitata eri entiteettien, et tiedä, mitkä kentät ovat käytettävissä, kun kirjoitat kaavaa. *. Kentän* notation ei ole käytettävissä. Nämä kaavat on mukautettava tietueet, jotka sovelluksen havaitsee, kun se suoritetaan.

**IsType** funktio Testaa, onko tietue viittaus viittaa tiettyyn entiteettiin. Funktio palauttaa totuusarvo TOSI tai EPÄTOSI.

**AsType** funktio käsittelee tietueen viitata tiettyyn entiteettityyppi, jota kutsutaan joskus *muuntamista*. Voit käyttää tuloksen kuin jos se olisi entiteetin tietueen ja, käyttää uudelleen *. Kentän* merkintätapaa kaikki tietueen kentät. Jos viittaus ei ole tietyn tapahtuu virhe.

Näiden funktioiden avulla yhdessä Testaa ensin entiteettityyppi tietueen ja käsitellä sitä kyseisen tietueena niin, että kentät ovat käytettävissä:

```powerapps-dot
If( IsType( First( Accounts ).Owner, Users ),
    AsType( First( Accounts ).Owner, Users ).'Full Name',
    AsType( First( Accounts ).Owner, Teams ).'Team Name'
)
```

Tarvitset näitä funktioita vain, jos käytät viittaus tietueen kentät. Voit esimerkiksi käyttää tietueen viitteet [ **suodatin** ](function-filter-lookup.md) toimi ilman **IsType** tai **AsType**:

```powerapps-dot
Filter( Accounts, Owner = First( Users ) )
```

Vastaavasti voit käyttää tietueen viitteiden [ **Patch** ](function-patch.md) funktio:

```powerapps-dot
Patch( Accounts, First( Accounts ), { Owner: First( Teams ) } )
```  

Jos käytetään tietueen kontekstissa, kuten [ **valikoiman** ](../controls/control-gallery.md) tai [ **muokkauslomake** ](../controls/control-form-detail.md) ohjausobjektin, saatat joutua käyttämään [Yleinen selvitysoperaattoria](operators.md#disambiguation-operator) viittaamaan kohteen tyyppi. Esimerkiksi Tämä kaava on tehokas valikoiman, jossa näkyy luettelo yhteystiedot jossa **yrityksen nimi** on **asiakkaan** lookup:

```powerapps-dot
If( IsType( ThisItem.'Company Name', [@Accounts] ),
    AsType( ThisItem.'Company Name', [@Accounts] ).'Account Name',
    AsType( ThisItem.'Company Name', [@Contacts] ).'Full Name'
)
```

Molemmille funktioille Määritä tietolähde, joka on yhdistetty entiteettiin tyypin nimi kautta. Kaavan työpaikkaan Lisää myös tietolähde tyyppejä, joita haluat testata tai pakottaa sovellukseen. Esimerkiksi, sinun on lisättävä **käyttäjät** entiteetin tietolähteenä, jos haluat käyttää **IsType** ja **AsType** kanssa **omistaja** haku- ja tietueet entiteetistä. Voit lisätä tietolähteitä, joita itse asiassa käyttää sovelluksessasi; Sinun ei tarvitse lisätä kaikki entiteetit, haun voi viitata.

Jos tietue-viittaus on *tyhjä*, **IsType** palauttaa arvon FALSE, ja **AsType** palauttaa *tyhjä*. Kaikki kentät *tyhjä* tietue on *tyhjä*.

## <a name="syntax"></a>Syntaksi

**AsType**( *RecordReference*, *EntityType* )

- *RecordReference* – pakollinen. Tietue-viittaus usein hakukenttä, joka voi viitata missä tahansa useita entiteettejä tietueeseen.
- *EntityType* – pakollinen. Tiettyyn entiteettiin, jonka voit testata.

**IsType**( *RecordReference*, *EntityType* )

- *RecordReference* – pakollinen. Tietue-viittaus usein hakukenttä, joka voi viitata missä tahansa useita entiteettejä tietueeseen.
- *EntityType* – pakollinen. Tiettyyn entiteettiin, johon tietueen kohdetyypille.

## <a name="example"></a>Esimerkki

[Tutustu tietueen viittaukset ja polymorfinen hakuja](../working-with-references.md) sisältää kattavat esimerkkejä.

1. Luo tyhjä kangas-sovellus tabletille.

1. Käyttöön **Näytä** -välilehden **tietolähteet**, ja lisää sitten **yhteystiedot** ja **tilit** entiteetit tietolähteinä.
    > [!div class="mx-imgBorder"]
    > ![Tyhjä sovellus ja kahdesta tietolähteestä: tilit ja yhteystiedot](media/function-astype-istype/contacts-add-datasources.png)

1. Lisää **valikoiman** ohjausobjektin **tyhjä, pysty** suunta.

    > [!div class="mx-imgBorder"]
    > ![Lisää Valikoimaohjausobjekti, jolla on tyhjä pystysuuntainen asettelu](media/function-astype-istype/contacts-customer-gallery.png)

1. Valitse **ominaisuudet** välilehti lähellä näytön oikealla puolella, Määritä valikoiman **kohteet** -ominaisuuden arvoksi **yhteystiedot**.

    > [!div class="mx-imgBorder"]
    > ![Määritä kohteiden yhteystietoihin ominaisuudet-ruutu](media/function-astype-istype/contacts-customer-datasource.png)

1. Aseta valikoiman asettelu **otsikko ja alaotsikko**.

    > [!div class="mx-imgBorder"]
    > ![Avaa asettelu-valitsin ominaisuudet-ruutu](media/function-astype-istype/contacts-customer-layout.png)

    > [!div class="mx-imgBorder"]
    > ![Määritetty asettelu otsikko ja alaotsikko](media/function-astype-istype/contacts-customer-flyout.png)

1. - **Tietojen** ruutu, avattuna **Title1** luettelo ja valitse sitten **KokoNimi**.

    > [!div class="mx-imgBorder"]
    > ![Otsikon arvo](media/function-astype-istype/contacts-customer-title.png)

1. Valitse **Subtitle1** Selite-ohjausobjekti.

    > [!div class="mx-imgBorder"]
    > ![Alaotsikko arvo](media/function-astype-istype/contacts-customer-subtitle.png)

1. Määritä **tekstin** ominaisuuden **Subtitle1** tämä kaava:

    ```powerapps-dot
    If( IsBlank( ThisItem.'Company Name' ), "--",
        IsType( ThisItem.'Company Name', [@Accounts] ),
            "Account: " & AsType( ThisItem.'Company Name', [@Accounts] ).'Account Name',
        "Contact: " & AsType( ThisItem.'Company Name', [@Contacts] ).'Full Name'
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Näyttö on nyt valmis näytetään tilit ja yhteystiedot myöskään keskenään valikoimassa](media/function-astype-istype/contacts-customer-complete.png)

    Valikoiman alaotsikko näyttää nämä arvot:
    - ”--” Jos **yrityksen nimi** on *tyhjä*.
    - ”Tili”: ja valitse sitten **tilin nimi** kenttä **tilit** entiteetin Jos **yrityksen nimi** kenttä viittaa tiliä.
    - ”Ota yhteyttä”: ja valitse sitten **KokoNimi** kenttä **yhteystiedot** entiteetin Jos **yrityksen nimi** kenttä viittaa yhteystiedon.

    Tulokset saattavat poikkeavat tämän ohjeaiheen koska se käyttää mallitietoja, joiden muokattiin muita sisältötyyppejä tulokset.

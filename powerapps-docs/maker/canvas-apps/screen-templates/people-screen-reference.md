---
title: Henkilö näytön malli viittaus | Microsoft Docs
description: Tietoja siitä, miten Canvas-sovellusten People-Screen-malli toimii Powerappsissa
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 1/2/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0a1626583300e6fe696415a91de68ff08596f081
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71989396"
---
# <a name="reference-information-about-the-people-screen-template-for-canvas-apps"></a>Viite tietoja Canvas-sovellusten ihmisinäyttömallista

Powerappsin Canvas-sovelluksissa opit ymmärtämään, miten jokainen tärkeä ihmisten näytön mallin ohjaus objekti vaikuttaa näytön yleisiin oletus toimintoihin. Tämä Deep Dive esittelee toiminta kaavoja ja muiden ominaisuuksien arvoja, jotka määrittävät, miten ohjaus objekti reagoi käyttäjän syöttämiseen. Lisä tietoja tämän näytön oletusarvoisesta toiminnosta on Ohje aiheessa [ihmisten näytön yleiskatsaus](people-screen-overview.md).

Tässä ohje aiheessa esitellään joitakin merkittäviä ohjaus objekteja ja selitetään lausekkeet tai kaavat, joille on määritetty eri ominaisuudet (kuten **kohteet** ja **onselect**):

* [Teksti haku ruutu](#text-search-box)
* [Käyttäjän selaus valikoima](#user-browse-gallery) (+ aliohjausobjektit)
* [Käyttäjät lisätty valikoima](#people-added-gallery) (+ aliohjausobjektit)

## <a name="prerequisite"></a>Edellytys

Perehtyneisyys näyttöjen ja muiden ohjaus objektien lisäämiseen ja määrittämiseen [, kun luot sovelluksen Powerappsissa](../data-platform-create-app-scratch.md).

## <a name="text-search-box"></a>Tekstihakukenttä

![TextSearchBox-ohjaus objekti](media/people-screen/people-search-box.png)

Parilla muulla ohjaus objekteilla on vuoro vaikutuksessa tai on riippuvuussuhde teksti haku ruutuun:

* Jos käyttäjä alkaa kirjoittaa tekstiä, **Userbrowsegallery** tulee näkyviin.
* Kun käyttäjä valitsee henkilön, joka sijaitsee **Userbrowsegallery**-kohteessa, haku sisältö nollataan.

## <a name="user-browse-gallery"></a>Käyttäjän selaus valikoima

![UserBrowseGallery-ohjaus objekti](media/people-screen/people-browse-gall.png)

* Ominaisuuden **Kohteet**<br>
    Arvo Logiikka, joka etsii käyttäjiä, kun käyttäjä aloittaa kirjoittamisen:
    
    ```powerapps-dot
    If( !IsBlank( Trim( TextSearchBox.Text ) ), 
        'Office365Users'.SearchUser(
            {
                searchTerm: Trim( TextSearchBox.Text ), 
                top: 15
            }
        )
    )
    ```
    
Tämän valikoiman kohteet täytetään haku tuloksilla [office365. SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) -toiminnosta. Toiminto vie tekstin `Trim(TextSearchBox)` haku terminä ja palauttaa tämän haun perusteella 15 parasta tulosta. **Textsearchbox** on kääritty `Trim()`-funktiolla, koska käyttäjä haku väli lyönneillä ei kelpaa.

@No__t-0-toiminto kääritään `If(!IsBlank(Trim(TextSearchBox.Text)) ... )`-funktiolla, koska sinun tarvitsee kutsua vain toiminto, kun haku ruutu sisältää käyttäjän määrittämän tekstin. Tämä parantaa suoritus kykyä.

### <a name="userbrowsegallery-title-control"></a>UserBrowseGallery-otsikon ohjaus objekti

![UserBrowseGallery-otsikon ohjaus objekti](media/people-screen/people-browse-gall-title.png)

* Ominaisuuden **Teksti**<br>Arvo: `ThisItem.DisplayName`

  Näyttää henkilön näyttö nimen Office 365-profiilista.

* Ominaisuuden **OnSelect**<br>
    Arvo Koodi, jolla käyttäjä lisätään sovellus tason kokoelmaan, ja valitse sitten käyttäjä:

    ```powerapps-dot
    Concurrent(
        Set( _selectedUser, ThisItem ),
        Reset( TextSearchBox ),
        If( Not( ThisItem.UserPrincipalName in MyPeople.UserPrincipalName ), 
            Collect( MyPeople, ThisItem )
        )
    )
    ```
Tämän ohjaus objektin valitseminen tekee kolme asiaa samanaikaisesti:

   * Määrittää valitulle kohteelle **\_selectedUser-** muuttujan.
   * Nollaa haku termin **Textsearchbox**-kohteessa.
   * Lisää valitun kohteen **Mypeople** -kokoelmaan, joka on kokoelma kaikkia käyttäjiä, jotka sovellus käyttäjä on valinnut.

### <a name="userbrowsegallery-profileimage-control"></a>UserBrowseGallery Profiledimage-ohjaus objekti

![UserBrowseGallery Profiledimage-ohjaus objekti](media/people-screen/people-browse-gall-image.png)

* Ominaisuuden **Kuva**<br>
    Arvo Käyttäjän profiili kuvan noutamiseen käytettävä logiikka.

    ```powerapps-dot
    If( !IsBlank( ThisItem.Id ) && 
            'Office365Users'.UserPhotoMetadata( ThisItem.Id ).HasPhoto,
        'Office365Users'.UserPhoto( ThisItem.Id )
    )
    ```

**Kuva** -ohjaus objekti noutaa käyttäjän kuvan [Office365Users. userphoto](https://docs.microsoft.com/connectors/office365users/#get-user-photo--v1-) -toiminnolla. Ennen sitä se tarkistaa kuitenkin kaksi asiaa:
  
   * Onko tunnus kenttä tyhjä vai ei tyhjä. Tämä estää **kuva** -ohjaus objektia yrittämästä noutaa käyttäjän valo kuvaa, ennen kuin valikoima on täytetty haku tuloksilla.
   * Onko käyttäjällä valo kuva ( [Office365Users. UserPhotoMetadata](https://docs.microsoft.com/connectors/office365users/#get-user-photo-metadata) -toiminto). Tämä estää `Office365Users.UserPhoto`-haku-funktion palauttamasta poikkeusta, jos käyttäjällä ei ole profiili kuvaa.

Ota huomioon, että jos kuvaa ei noudeta, **kuva** -ohjaus objekti on tyhjä ja **iconuser** -ohjaus objekti näkyy sen sijaan.

## <a name="people-added-gallery"></a>Henkilö-lisätty valikoima

![PeopleAddedGallery-ohjaus objekti](media/people-screen/people-people-gall.png)

* Ominaisuuden **Kohteet**<br>
    Arvo: `MyPeople`

Tämä on kokoelma henkilöitä, jotka on alustettu tai lisätty, valitsemalla **Userbrowsegallery-otsikko** -ohjaus objekti.

### <a name="peopleaddedgallery-title-control"></a>PeopleAddedGallery-otsikon ohjaus objekti

![PeopleAddedGallery-otsikon ohjaus objekti](media/people-screen/people-people-gall-title.png)

* Ominaisuuden **OnSelect**<br>
    Arvo: `Set( _selectedUser, ThisItem )`

Määrittää **_Selecteduser** -muuttujan kohteelle, joka on valittu **emailpeoplegallery**-kohteessa.

### <a name="peopleaddedgallery-iconremove-control"></a>Peopenleaddedgallery iconRemove-ohjaus objekti

![Peopenleaddedgallery iconRemove-ohjaus objekti](media/people-screen/people-people-gall-delete.png)

* Ominaisuuden **OnSelect**<br>
    Arvo: `Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) )`

Hakee tietueen **Mypeople** -kokoelmasta, jossa **userPrincipalName** vastaa valitun kohteen **userPrincipalName** -kohdetta, ja poistaa sitten tietueen kokoelmasta.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Lue lisä tietoja tästä näytöstä](./people-screen-overview.md).
* [Lue lisä tietoja Office 365 Outlook Connectorista](../connections/connection-office365-outlook.md).
* [Lue lisä tietoja Office 365-käyttäjien liittimestä](../connections/connection-office365-users.md).

---
title: Käyttäjät-näytön mallin viittauksen | Microsoft Docs
description: Tutustu powerappsin pohjaan perustuvat sovellukset käyttäjät-näytön malli toimintaan tiedot
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 1/2/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 09b92a1e2bc87ac6f4e2ec651aa67a845e0f07b1
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459455"
---
# <a name="reference-information-about-the-people-screen-template-for-canvas-apps"></a>Lisätietoja pohjaan perustuvat sovellukset käyttäjät-näytön-malli

Pohjaan perustuvia sovelluksia powerappsissa ymmärrä, miten merkittäviä ohjausobjekteja käyttäjät-näytön mallin osallistuu näytön yleistä oletusarvon toimintoja. Nämä esittää toimintakaavoissa ja muita ominaisuuksia, jotka määrittävät, miten ohjausobjektit vastata käyttäjän syötettä arvot. Lisätietoja korkean tason tässä näytössä oletusarvon toiminnot-kohdassa [ihmiset näytön yleiskatsaus](people-screen-overview.md).

Tässä ohjeaiheessa korostaa joitakin merkittäviä ohjausobjekteja ja kerrotaan lausekkeita tai kaavoja mitä eri ominaisuuksia (kuten **kohteet** ja **OnSelect**) ohjausobjektit on määritetty:

* [Tekstihakukenttä](#text-search-box)
* [Käyttäjä Selaa valikoimaa](#user-browse-gallery) (+ aliohjausobjektit)
* [Ihmisiä lisätä valikoiman](#people-added-gallery) (+ aliohjausobjektit)

## <a name="prerequisite"></a>Edellytys

Miten voit lisätä ja määrittää näyttöjä ja muita ohjausobjekteja sinuna tuntee [sovelluksen luominen powerappsin](../data-platform-create-app-scratch.md).

## <a name="text-search-box"></a>Tekstihakukenttä

![TextSearchBox ohjausobjekti](media/people-screen/people-search-box.png)

Muutamia muita ohjausobjekteja toimia, tai se on riippuvuus teksti-hakuruudun:

* Jos käyttäjä kirjoittaa tekstiä, käynnistää **UserBrowseGallery** tulee näkyviin.
* Kun käyttäjä valitsee käyttäjän **UserBrowseGallery**, Etsi sisältö palautetaan.

## <a name="user-browse-gallery"></a>Käyttäjä Selaa valikoimaa

![UserBrowseGallery ohjausobjekti](media/people-screen/people-browse-gall.png)

* Ominaisuus: **Kohteet**<br>
    Arvo: Voit hakea käyttäjille, kun käyttäjä aloittaa kirjoittamisen Logic:
    
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
    
Valikoiman kohteet täytetään hakutulosten mukaan [Office365.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) toiminto. Toiminto hakee teksti `Trim(TextSearchBox)` kuin etsinnän termi ja palauttaa ylimmät 15 tulosten perusteella kyseistä hakua. **TextSearchBox** rivittyy `Trim()` funktiolla, koska käyttäjän haku välilyöntejä, on virheellinen.

`Office365Users.SearchUser` Toiminto rivittyy `If(!IsBlank(Trim(TextSearchBox.Text)) ... )` funktiolla, koska haluat kutsua toimintoa, kun hakuruutuun sisältää käyttäjän teksti. Tämä parantaa suorituskykyä.

### <a name="userbrowsegallery-title-control"></a>UserBrowseGallery otsikko-ohjausobjekti

![UserBrowseGallery otsikko-ohjausobjekti](media/people-screen/people-browse-gall-title.png)

* Ominaisuus: **Teksti**<br>Arvo: `ThisItem.DisplayName`

  Näyttää niiden Office 365-profiilista henkilön näyttönimi.

* Ominaisuus: **OnSelect**<br>
    Arvo: Voit lisätä käyttäjän sovelluksen tason kokoelmaan Code ja valitse sitten käyttäjä:

    ```powerapps-dot
    Concurrent(
        Set( _selectedUser, ThisItem ),
        Reset( TextSearchBox ),
        If( Not( ThisItem.UserPrincipalName in MyPeople.UserPrincipalName ), 
            Collect( MyPeople, ThisItem )
        )
    )
    ```
Valitsemalla tämän ohjausobjektin tekee kolmesta samanaikaisesti:

   * Määrittää  **\_selectedUser** muuttujan valittuna.
   * Nollaa hakuehto- **TextSearchBox**.
   * Lisää valittu kohde **MyPeople** kokoelman, kaikki käyttäjät kokoelma sovelluksen käyttäjälle on valittu.

### <a name="userbrowsegallery-profileimage-control"></a>UserBrowseGallery ProfileImage ohjausobjekti

![UserBrowseGallery ProfileImage ohjausobjekti](media/people-screen/people-browse-gall-image.png)

* Ominaisuus: **Kuva**<br>
    Arvo: Noutaa käyttäjäprofiilin valokuva logiikka.

    ```powerapps-dot
    If( !IsBlank( ThisItem.Id ) && 
            'Office365Users'.UserPhotoMetadata( ThisItem.Id ).HasPhoto,
        'Office365Users'.UserPhoto( ThisItem.Id )
    )
    ```

**Kuvan** ohjausobjekti hakee käyttäjän kuvan [Office365Users.UserPhoto](https://docs.microsoft.com/connectors/office365users/#get-user-photo--v1-) toiminto. Ennen kuin teet, se etsii kaksi asiaa:
  
   * Onko tunnuskenttä tyhjä, tai sitä ei ole tyhjä. Tämä estää **kuvan** ohjausobjekti-yritettäessä noutaa käyttäjän valokuva, ennen kuin valikoima on täytetty hakutulokset.
   * Onko käyttäjän valokuva (kanssa [Office365Users.UserPhotoMetadata](https://docs.microsoft.com/connectors/office365users/#get-user-photo-metadata) toiminto). Tämä estää `Office365Users.UserPhoto` haun palauttamasta poikkeus, jos käyttäjällä ei ole profiilikuvan.

Huomaa, että jos kuvaa ei ole noudetaan, **kuvan** ohjausobjekti on tyhjä, ja **iconUser** ohjausobjekti näkyy sen sijaan.

## <a name="people-added-gallery"></a>Ihmisiä lisätä valikoima

![PeopleAddedGallery ohjausobjekti](media/people-screen/people-people-gall.png)

* Ominaisuus: **Kohteet**<br>
    Arvo: `MyPeople`

Tämä on alustettu tai valitsemalla lisätään kokoelma **UserBrowseGallery otsikko** ohjausobjektin.

### <a name="peopleaddedgallery-title-control"></a>PeopleAddedGallery otsikko-ohjausobjekti

![PeopleAddedGallery otsikko-ohjausobjekti](media/people-screen/people-people-gall-title.png)

* Ominaisuus: **OnSelect**<br>
    Arvo: `Set( _selectedUser, ThisItem )`

Määrittää **_selectedUser** muuttujan valitun kohteen **EmailPeopleGallery**.

### <a name="peopleaddedgallery-iconremove-control"></a>PeopleAddedGallery iconRemove ohjausobjekti

![PeopleAddedGallery iconRemove ohjausobjekti](media/people-screen/people-people-gall-delete.png)

* Ominaisuus: **OnSelect**<br>
    Arvo: `Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) )`

Etsii tietueen **MyPeople** kokoelma, jossa **UserPrincipalName** vastaa **UserPrincipalName** valitun kohteen ja sitten poistaa, tietue kokoelma.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Lue lisätietoja tässä näytössä](./people-screen-overview.md).
* [Lue lisätietoja Office 365 Outlook-liittimessä](../connections/connection-office365-outlook.md).
* [Lue lisätietoja Office 365-käyttäjät-liittimen](../connections/connection-office365-users.md).

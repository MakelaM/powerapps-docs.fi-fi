---
title: Pohja sovellusten Sähkö posti näytön mallin viite tiedot | Microsoft Docs
description: Tietoja siitä, miten Sähkö posti näytön malli pohja sovelluksille toimii Powerappsissa
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/31/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7663668b77c6f8186ef54c3182230fa843f86577
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995707"
---
# <a name="reference-information-about-the-email-screen-template-for-canvas-apps"></a>Viite tietoja Sähkö posti näytön mallista pohjaan liittyviä sovelluksia varten

Powerappsin Canvas-sovelluksissa opit ymmärtämään, miten Sähkö posti näytön mallin kaikki merkittävät ohjaus toiminnot edistävät näytön yleistä oletus toiminnallisuutta. Tämä Deep Dive esittelee toiminta kaavat ja muiden ominaisuuksien arvot, jotka määrittävät, miten ohjaus objekti reagoi käyttäjän syöttämiseen. Lisä tietoja tämän näytön oletusarvoisesta toiminnosta on [Sähkö posti-näytön yleiskatsauksessa](email-screen-overview.md).

Tässä ohje aiheessa esitellään joitakin merkittäviä ohjaus objekteja ja selitetään lausekkeet tai kaavat, joille on määritetty eri ominaisuudet (kuten **kohteet** ja **onselect**):

* [Teksti haku ruutu](#text-search-box)
* [Lisää kuvake](#add-icon)
* [Henkilöiden selaus valikoima](#people-browse-gallery)
* [Sähkö postin käyttäjien valikoima](#email-people-gallery) (+ aliohjausobjektit)
* [Sähkö posti-kuvake](#mail-icon)

## <a name="prerequisite"></a>Edellytys

Perehtyneisyys näyttöjen ja muiden ohjaus objektien lisäämiseen ja määrittämiseen [, kun luot sovelluksen Powerappsissa](../data-platform-create-app-scratch.md).

## <a name="text-search-box"></a>Tekstihakukenttä

   ![TextSearchBox-ohjaus objekti](media/email-screen/email-search-box.png)

Useilla muilla näytön ohjaus objekteilla on riippuvuussuhde **teksti haku ruutu** -ohjaus objektiin:

* Jos käyttäjä alkaa kirjoittaa tekstiä, näkyviin tulee **Peoplebrowsegallery** .
* Jos käyttäjä käyttää kelvollista Sähkö posti osoitetta, esiin tulee **addon** .
* Kun käyttäjä valitsee henkilön **Peoplebrowsegallery**-kohteessa, haku sisältö nollataan.

## <a name="add-icon"></a>Lisäämiskuvake

   ![Addiktoiva ohjaus objekti](media/email-screen/email-add-icon.png)

**Lisää kuvake** -ohjaus objektin avulla sovelluksen käyttäjät voivat lisätä henkilöitä, jotka eivät ole organisaatiossaan, vastaanottajien luettelon muodostamasta Sähkö posti viestistä.

* Ominaisuuden **Näkyvissä**<br>
    Arvo Logiikka, joka näyttää ohjaus objektin vain, kun käyttäjä kirjoittaa kelvollisen Sähkö posti osoitteen haku ruutuun:

    ```powerapps-dot
    !IsBlank( TextSearchBox.Text ) &&
        IsMatch( TextSearchBox.Text, Match.Email ) &&
        Not( Trim( TextSearchBox.Text ) in MyPeople.UserPrincipalName )
    ```
  Rivin mukaan, edeltävä koodi lohko kertoo, että **Lisää kuvake** -ohjaus objekti näkyy vain, jos:

    * **Textsearchbox** sisältää tekstiä.
    * **Textsearchbox** -teksti on kelvollinen Sähkö posti osoite.
    * **Textsearchbox** -teksti ei ole jo olemassa **mypeople** -kokoelmassa.

* Ominaisuuden **OnSelect**<br>
    Arvo Tämän valitseminen lisää kelvollisen Sähkö posti osoitteen **Mypeople** -kokoelmaan. Näyttö käyttää tätä kokoelmaa vastaanottajaluettelossa:

    ```powerapps-dot
    Collect( MyPeople,
        { 
            DisplayName: TextSearchBox.Text, 
            UserPrincipalName: TextSearchBox.Text, 
            Mail: TextSearchBox.Text
        }
    );
    Reset( TextSearchBox )
    ```
  
  Tämä koodi lohko lisää rivin **Mypeople** -kokoelmaan ja täyttää kolme kenttää **Textsearchbox**-tekstillä. Nämä kolme kenttää ovat **DisplayName**, **userPrincipalName**ja **Mail**. Sen jälkeen se palauttaa **Textsearchbox**-kohteen sisällön.

## <a name="people-browse-gallery"></a>Henkilöiden selaus valikoima

   ![PeopleBrowseGallery-ohjaus objekti](media/email-screen/email-browse-gall.png)

* Ominaisuuden **Kohteet**<br>
    Arvo **Textsearchbox** -ohjaus objektiin kirjoitetun haku tekstin Top 15-haku tulokset:
    
    ```powerapps-dot
    If( !IsBlank( Trim(TextSearchBox.Text ) ), 
        'Office365Users'.SearchUser( {searchTerm: Trim( TextSearchBox.Text ), top: 15} )
    )
    ```

  Tämän valikoiman kohteet täytetään haku tuloksilla [office365. SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) -toiminnosta. Toiminto vie tekstin `Trim(TextSearchBox)` haku terminä ja palauttaa tämän haun perusteella 15 parasta tulosta.
  
  **Textsearchbox** on kääritty `Trim()`-funktiolla, koska käyttäjä haku väli lyönneillä ei kelpaa. Toiminto `Office365Users.SearchUser` kääritään `If(!IsBlank(Trim(TextSearchBox.Text)) ... )`-funktiolla, mikä tarkoittaa, että toiminto suoritetaan vain, jos haku ruutu sisältää käyttäjän määrittämän tekstin. Tämä parantaa suoritus kykyä. 

### <a name="people-browse-gallery-title-control"></a>Käyttäjät selaavat valikoiman otsikko-ohjaus objektia

   ![PeopleBrowseGallery-otsikon ohjaus objekti](media/email-screen/email-browse-gall-title.png)

* Ominaisuuden **Teksti**<br>
    Arvo: `ThisItem.DisplayName`

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

   * Määrittää **_Selecteduser** -muuttujan valittuun kohteeseen.
   * Nollaa haku termin **Textsearchbox**-kohteessa.
   * Lisää valitun kohteen **Mypeople** -kokoelmaan, joka on kokoelma kaikkia valittuja käyttäjiä, joita Sähkö posti näyttö käyttää vastaanottajien joukossa.

## <a name="email-people-gallery"></a>Sähkö postin käyttäjien valikoima

   ![EmailPeopleGallery-ohjaus objekti](media/email-screen/email-people-gall.png)

* Ominaisuuden **Kohteet**<br>
    Arvo: `MyPeople`

  Tämä on kokoelma henkilöitä, jotka on alustettu tai lisätty, valitsemalla **Peoplebrowsegallery-otsikko** -ohjaus objekti.

* Ominaisuuden **Korkeus**<br>
    Arvo Logiikka, joka vahvistaa korkeuden valikoimassa parhaillaan olevien kohteiden määrän perusteella:

    ```powerapps-dot
    Min( 
        ( EmailPeopleGallery.TemplateHeight + EmailPeopleGallery.TemplatePadding * 2) *
            RoundUp(CountRows(EmailPeopleGallery.AllItems) / 2, 0 ),
        304
    )
    ```

  Tämän valikoiman korkeus muuttuu valikoiman kohteiden määrän mukaan, ja suurin korkeus on 304.
  
  Se kestää `TemplateHeight + TemplatePadding * 2`, kun yksi rivi on **Emailpeoplegallery**-kohteen kokonaiskorkeus, ja kertoo sen sitten rivien määrän mukaan. Koska `WrapCount = 2`, todellisten rivien määrä on `RoundUp(CountRows(EmailPeopleGallery.AllItems) / 2, 0)`.

* Ominaisuuden **ShowScrollbar**<br>
    Arvo: `EmailPeopleGallery.Height >= 304`
  
  Kun valikoiman korkeus on 304, vieritys palkki on näkyvissä.

### <a name="email-people-gallery-title-control"></a>Sähkö postin käyttäjien valikoiman otsikko-ohjaus objekti

   ![EmailPeopleGallery-otsikko-ohjaus objekti](media/email-screen/email-people-gall-text.png)

* Ominaisuuden **OnSelect**<br>
    Arvo: `Set(_selectedUser, ThisItem)`

  Määrittää **_Selecteduser** -muuttujan kohteelle, joka on valittu **emailpeoplegallery**-kohteessa.

### <a name="email-people-gallery-iconremove-control"></a>Sähkö postin käyttäjien valikoima iconRemove-ohjaus objekti

   ![Kuukauden päivä valikoiman otsikko-ohjaus objekti](media/email-screen/email-people-gall-delete.png)

* Ominaisuuden **OnSelect**<br>
    Arvo: `Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) )`

  Hakee tietueen **Mypeople** -kokoelmasta, jossa **userPrincipalName** vastaa valitun kohteen **userPrincipalName** -kohdetta, ja poistaa kyseisen tietueen kokoelmasta.

## <a name="mail-icon"></a>Sähkö posti-kuvake

* Ominaisuuden **OnSelect**<br>
    Arvo Käyttäjän Sähkö posti viestin lähettämisen logiikka:

    ```powerapps-dot
    Set( _emailRecipientString, Concat( MyPeople, Mail & ";" ) );
    'Office365'.SendEmail( _emailRecipientString, 
        TextEmailSubject.Text,  
        TextEmailMessage.Text, 
        { Importance:"Normal" }
    );
    Reset( TextEmailSubject );
    Reset( TextEmailMessage );
    Clear( MyPeople )
    ```

  Sähkö posti viestin lähettäminen edellyttää puoli pistein eroteltuja Sähkö posti osoitteiden merkki jonoja. Edellisessä koodissa:
  1. Ensimmäinen koodi rivi vie **Sähkö posti** -kentän kaikista **mypeople** -kokoelman riveistä, yhdistää ne yksittäiseksi merkki jonoksi puoli pisteillä eroteltuina ja asettaa **_emailRecipientString** -muuttujan kyseiselle merkki jonolle. arvo.

  1. Sen jälkeen se lähettää sähkö posti viestin vastaanottajille käyttämällä [office365. SendEmail](https://docs.microsoft.com/connectors/office365/#sendemail) -toimintoa.
    Toiminnolla on kolme pakollista parametria:, **Aihe**ja **leipä teksti**sekä yksi valinnainen **parametri –** **tärkeys**. Edellisessä koodissa Nämä ovat **_emailRecipientString**, **textemailsubject**. Teksti, **Textemailmessage**. Teksti ja **Normaali**.
  1. Lisäksi se Nollaa **Textemailsubject** -ja **Textemailmessage** -ohjaus objektin ja tyhjentää **mypeople** -kokoelman.

* Ominaisuuden **Haluat viitata DisplayMode**<br>
    Arvo `If( Len( Trim( TextEmailSubject.Text ) ) > 0 && !IsEmpty( MyPeople ), DisplayMode.Edit, DisplayMode.Disabled )` Sähkö posti viesti lähetetään, sähkö posti viestin aihe rivillä on oltava teksti, ja vastaanottajan (**Mypeople**) kokoelma ei saa olla tyhjä.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Lue lisä tietoja tästä näytöstä](./email-screen-overview.md)
* [Lue lisä tietoja Office 365 Outlook Connectorista Powerappsissa](../connections/connection-office365-outlook.md)
* [Lue lisä tietoja Office 365-käyttäjien liittimestä Powerappsissa](../connections/connection-office365-users.md)

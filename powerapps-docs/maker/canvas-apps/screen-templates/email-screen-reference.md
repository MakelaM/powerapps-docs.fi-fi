---
title: Viittaus pohjaan perustuvat sovellukset sähköpostin näytön-malli | Microsoft Docs
description: Tutustu powerappsin pohjaan perustuvat sovellukset sähköpostin näytön malli toimintaan tiedot
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/31/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8f77fe1194ace2f8cb5abeb3f9657cc76aab263a
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459478"
---
# <a name="reference-information-about-the-email-screen-template-for-canvas-apps"></a>Lisätietoja sähköpostin näytön malli on tarkoitettu pohjaan perustuvat sovellukset

Pohjaan perustuvia sovelluksia powerappsissa ymmärrä, miten merkittäviä ohjausobjekteja sähköpostin näytön mallin osallistuu näytön yleistä oletusarvon toimintoja. Nämä esittää toiminta-kaavat ja arvot muita ominaisuuksia, jotka määrittävät, miten ohjausobjektit vastata käyttäjän syötettä. Lisätietoja korkean tason tässä näytössä oletusarvon toiminnot-kohdassa [sähköpostin näytön yleiskatsaus](email-screen-overview.md).

Tässä ohjeaiheessa korostaa joitakin merkittäviä ohjausobjekteja ja kerrotaan lausekkeita tai kaavoja mitä eri ominaisuuksia (kuten **kohteet** ja **OnSelect**) ohjausobjektit on määritetty:

* [Tekstihakukenttä](#text-search-box)
* [Lisäämiskuvake](#add-icon)
* [Ihmiset Selaa valikoimaa](#people-browse-gallery)
* [Sähköpostiviestin käyttäjien valikoiman](#email-people-gallery) (+ aliohjausobjektit)
* [Sähköposti-kuvaketta](#mail-icon)

## <a name="prerequisite"></a>Edellytys

Miten voit lisätä ja määrittää näyttöjä ja muita ohjausobjekteja sinuna tuntee [sovelluksen luominen powerappsin](../data-platform-create-app-scratch.md).

## <a name="text-search-box"></a>Tekstihakukenttä

   ![TextSearchBox ohjausobjekti](media/email-screen/email-search-box.png)

Useita näytössä muiden ohjausobjektien ole riippuvuutta **tekstihakukenttä** ohjausobjekti:

* Jos käyttäjä kirjoittaa tekstiä, käynnistää **PeopleBrowseGallery** tulee näkyviin.
* Jos käyttäjä kirjoittaa ulos kelvollinen sähköpostiosoite **AddIcon** tulee näkyviin.
* Kun käyttäjä valitsee käyttäjän **PeopleBrowseGallery**, Etsi sisältö palautetaan.

## <a name="add-icon"></a>Lisäämiskuvake

   ![AddIcon ohjausobjekti](media/email-screen/email-add-icon.png)

**Lisää kuvake** ohjausobjektin avulla sovelluksen käyttäjät voivat lisätä käyttäjät, joilla ei ole parhaillaan toistetusta sähköpostiviestin vastaanottajaluetteloon niiden organisaation sisällä.

* Ominaisuus: **Näkyvissä**<br>
    Arvo: Logic ohjausobjekti näyttää vain, kun käyttäjä kirjoittaa hakuruutuun kelvollinen sähköpostiosoite:

    ```powerapps-dot
    !IsBlank( TextSearchBox.Text ) &&
        IsMatch( TextSearchBox.Text, Match.Email ) &&
        Not( Trim( TextSearchBox.Text ) in MyPeople.UserPrincipalName )
    ```
  Rivi kerrallaan edellisen koodilohko, joka lukee **Lisää kuvake** ohjausobjekti näytetään vain, jos:

    * **TextSearchBox** sisältää tekstin.
    * Tekstin **TextSearchBox** on kelvollinen sähköpostiosoite.
    * Tekstin **TextSearchBox** ei jo ole olemassa **MyPeople** kokoelma.

* Ominaisuus: **OnSelect**<br>
    Arvo: Valitsemalla tämä Lisää kelvollinen sähköpostiosoite **MyPeople** kokoelma. Tämän kokoelman käyttämän näytön vastaanottajaluettelon:

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
  
  Tämä koodilohko Lisää rivin **MyPeople** kokoelma ja täyttää kolme kenttää tekstillä **TextSearchBox**. Nämä kolme kentät ovat **DisplayName**, **UserPrincipalName**, ja **sähköpostia**. Se sitten palauttaa sisällön **TextSearchBox**.

## <a name="people-browse-gallery"></a>Ihmiset Selaa valikoimaa

   ![PeopleBrowseGallery ohjausobjekti](media/email-screen/email-browse-gall.png)

* Ominaisuus: **Kohteet**<br>
    Arvo: Kirjoitetun tekstin top 15 hakutulokset **TextSearchBox** ohjausobjekti:
    
    ```powerapps-dot
    If( !IsBlank( Trim(TextSearchBox.Text ) ), 
        'Office365Users'.SearchUser( {searchTerm: Trim( TextSearchBox.Text ), top: 15} )
    )
    ```

  Valikoiman kohteet täytetään hakutulosten mukaan [Office365.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) toiminto. Toiminto hakee teksti `Trim(TextSearchBox)` kuin etsinnän termi ja palauttaa ylimmät 15 tulosten perusteella kyseistä hakua.
  
  **TextSearchBox** rivittyy `Trim()` funktiolla, koska käyttäjän haku välilyöntejä, on virheellinen. `Office365Users.SearchUser` Toiminto rivittyy `If(!IsBlank(Trim(TextSearchBox.Text)) ... )` funktio, joka tarkoittaa, että toiminto suoritetaan vain, jos hakuruutuun sisältää käyttäjän tekstiä. Tämä parantaa suorituskykyä. 

### <a name="people-browse-gallery-title-control"></a>Ihmiset Selaa valikoimassa otsikko

   ![PeopleBrowseGallery otsikko-ohjausobjekti](media/email-screen/email-browse-gall-title.png)

* Ominaisuus: **Teksti**<br>
    Arvo: `ThisItem.DisplayName`

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

   * Määrittää **_selectedUser** muuttujan valittuna.
   * Nollaa hakuehto- **TextSearchBox**.
   * Lisää valittu kohde **MyPeople** kokoelman, kaikki valittujen käyttäjien, joka käyttää joukon vastaanottajat sähköpostiviesti-ruutu kokoelma.

## <a name="email-people-gallery"></a>Sähköpostiviestin käyttäjien valikoima

   ![EmailPeopleGallery ohjausobjekti](media/email-screen/email-people-gall.png)

* Ominaisuus: **Kohteet**<br>
    Arvo: `MyPeople`

  Tämä on alustettu tai valitsemalla lisätään kokoelma **PeopleBrowseGallery otsikko** ohjausobjektin.

* Ominaisuus: **Korkeus**<br>
    Arvo: Logic määrittämään korkeus valikoiman olevien kohteiden määrän perusteella:

    ```powerapps-dot
    Min( 
        ( EmailPeopleGallery.TemplateHeight + EmailPeopleGallery.TemplatePadding * 2) *
            RoundUp(CountRows(EmailPeopleGallery.AllItems) / 2, 0 ),
        304
    )
    ```

  Valikoiman korkeus säätää valikoiman kohteiden määrä enimmäiskorkeus 304 kanssa.
  
  Kestää `TemplateHeight + TemplatePadding * 2` kuin yhteensä yksittäisen rivin korkeus **EmailPeopleGallery**, kertoo sen rivien määrän mukaan. Koska `WrapCount = 2`, true rivien määrä on `RoundUp(CountRows(EmailPeopleGallery.AllItems) / 2, 0)`.

* Ominaisuus: **ShowScrollbar**<br>
    Arvo: `EmailPeopleGallery.Height >= 304`
  
  Kun valikoiman korkeus 304, vierityspalkin on näkyvissä.

### <a name="email-people-gallery-title-control"></a>Sähköpostin ihmiset valikoiman ohjausobjektin otsikko

   ![EmailPeopleGallery otsikko-ohjausobjekti](media/email-screen/email-people-gall-text.png)

* Ominaisuus: **OnSelect**<br>
    Arvo: `Set(_selectedUser, ThisItem)`

  Määrittää **_selectedUser** muuttujan valitun kohteen **EmailPeopleGallery**.

### <a name="email-people-gallery-iconremove-control"></a>Sähköpostiviestin käyttäjien iconRemove valikoimassa

   ![MonthDayGallery otsikko-ohjausobjekti](media/email-screen/email-people-gall-delete.png)

* Ominaisuus: **OnSelect**<br>
    Arvo: `Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) )`

  Etsii tietueen **MyPeople** kokoelma, jossa **UserPrincipalName** vastaa **UserPrincipalName** valitun kohteen ja poistaa, tietue kokoelma.

## <a name="mail-icon"></a>Sähköposti-kuvaketta

* Ominaisuus: **OnSelect**<br>
    Arvo: Käyttäjän sähköpostin lähettäminen Logic:

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

  Lähettää sähköpostiviestin edellyttää sähköpostiosoitteet puolipistein eroteltu merkkijonon. Edellisen koodi:
  1. Koodin ensimmäisen rivin tulee **sähköpostia** kenttä kaikki rivit **MyPeople** kokoelman, yhdistää ne yksittäiseksi merkkijonoksi sähköpostiosoitteet puolipisteillä eroteltuina ja määrittää **_ emailRecipientString** muuttujan merkkijono arvoon.

  1. Se sitten käyttää [Office365.SendEmail](https://docs.microsoft.com/connectors/office365/#sendemail) toiminto, joka lähettää sähköpostiviestin.
    Toiminto on kolme pakolliset parametrit **-**, **aihe**, ja **leipätekstin**, ja yksi valinnainen parametri--**tärkeyden**. Edellisen koodi nämä ovat **_emailRecipientString**, **TextEmailSubject**. Teksti, **TextEmailMessage**. Teksti, ja **Normaali**, tässä järjestyksessä.
  1. Lopuksi nollaa **TextEmailSubject** ja **TextEmailMessage** ohjausobjekteja ja tyhjentää **MyPeople** kokoelma.

* Ominaisuus: **DisplayMode**<br>
    Arvo: `If( Len( Trim( TextEmailSubject.Text ) ) > 0 && !IsEmpty( MyPeople ), DisplayMode.Edit, DisplayMode.Disabled )` Sähköpostin lähettäminen sähköpostiviestin aiherivillä on oltava teksti ja vastaanottajan (**MyPeople**) kokoelma ei saa olla tyhjä.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Lue lisätietoja tässä näytössä](./email-screen-overview.md)
* [Lue lisätietoja Office 365 Outlook-liittimellä powerappsissa](../connections/connection-office365-outlook.md)
* [Lue lisätietoja Office 365-käyttäjät-liittimellä powerappsissa](../connections/connection-office365-users.md)

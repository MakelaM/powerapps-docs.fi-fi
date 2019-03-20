---
title: Sähköpostin näytön malli | Microsoft Docs
description: Ymmärtää, miten sähköpostin näytön malli on tarkoitettu pohjaan perustuvat sovellukset toimivat ja laajenna oman käyttötapauksissa näytön
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/29/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a1aad5ca9e8c7f8b55b1645b04d6c8dc0b9c707b
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459547"
---
# <a name="overview-of-the-email-screen-template-for-canvas-apps"></a>Pohjaan perustuvat sovellukset sähköpostin näytön-mallin yleiskatsaus

Lisää pohjaan perustuvan sovelluksen, sähköpostiviesti-ruutu, jossa käyttäjät voivat lähettää sovelluksesta sähköpostiviestin Office 365 Outlook-tilinsä. Käyttäjät voivat etsiä niiden orgs vastaanottajat ja Lisää ulkoinen sähköpostiosoitteet liian. Voit lisätä kuvan liitteen tuki, muuttaa käyttäjätietoja, jotka näkyvät Hae valikoiman ja tehdä muita mukautuksia.

Voit myös lisätä malliin perustuvan muun, jotka näyttävät eri Office 365: stä tietoja, kuten käyttäjän [kalenterin](calendar-screen-overview.md), [ihmiset](people-screen-overview.md) organisaatiossasi, ja [käytettävyysryhmän](meeting-screen-overview.md) . ihmiset käyttäjien kannattaa kutsua kokoukseen.

Tästä yleiskatsauksesta opetetaan:
> [!div class="checklist"]
> * Miten voit käyttää sähköpostia oletusnäytön.
> * Miten voit muokata sitä.
> * Miten integrointi sovellukseen.

Katso tarkemmin tarkemmin tässä näytössä oletusarvon toimintoja [sähköpostin näytön viittaus](email-screen-reference.md).

## <a name="prerequisite"></a>Edellytys

Miten voit lisätä ja määrittää näyttöjä ja muita ohjausobjekteja sinuna tuntee [sovelluksen luominen powerappsin](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Default-toiminnot

Lisää sähköpostiviesti-ruutu mallista:

1. [Kirjaudu sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin, ja luo sovellus tai avaa olemassa olevaa sovellusta PowerApps Studio.

    Tässä aiheessa näytetään puhelinsovelluksen, mutta samat käsitteet koskevat tablettisovellusta.

1. Valitse **aloitus** Valitse valintanauhan välilehti **uusi näyttö** > **sähköpostin**.

    Oletusarvon mukaan näytön näyttää tältä:

    ![Sähköpostiviesti-ruutu](media/email-screen/email-screen-full.png)

Joitakin hyödyllisiä Huomautuksia:

* Etsi käyttäjät organisaatiossasi, ala kirjoittaa nimensä tekstisyötteen ruutu ”-” alla.
* Ihmiset etsittäessä vain 15 parhaat tulokset palautetaan.
* Lisää sähköpostiosoitteet sähköpostin vastaanottajat organisaatiosi ulkopuolella, kirjoita ulos koko, kelvollinen sähköpostiosoite ja valitse ”+”-kuvakkeen, joka vaikuttaa sen oikealla puolella.
* Lisää vähintään yksi henkilö vastaanottajan ja annettava lähettää sähköpostiviestin aihe.
* Kun lähetät sähköpostiviestin, aiherivin ja viestin sekä vastaanottajaluettelon sisällön kaikki poistetaan.

## <a name="modify-the-screen"></a>Muokkaa näyttö

Tämä näyttö oletusarvon toimintoja voit muokata joitakin yleisiä käyttötapoja:

* [Lisää kuva-liitteen-tuki](email-screen-overview.md#add-image-attachment-support)
* [Näytä eri ihmisiä](email-screen-overview.md#show-different-data-for-people)

Jos haluat muokata näytön tarkemmin [sähköpostin näytön viittaus](./email-screen-reference.md) ohjeena.

> [!IMPORTANT]
> Seuraavissa vaiheissa oletetaan, että olet lisännyt vain yksi sähköpostiviesti-ruutu sovellukseen. Jos olet lisännyt useampi kuin yksi, ohjausobjektin nimet (kuten **iconMail1**) päättyy numeroon, ja sinun on säätää kaavat vastaavasti.

### <a name="add-image-attachment-support"></a>Lisää kuva-liitteen-tuki

Näin käyttäjät voivat lähettää yhtenä kuvana niiden sähköpostitse liitteenä.

1. Valitse **Lisää** -välilehden **Media**, ja valitse sitten **Lisää kuva**.
1. Määritä uuden ohjausobjektin **Y** ominaisuudeksi seuraava lauseke:

    `TextEmailMessage1.Y + TextEmailMessage1.Height + 20`
    
1. Kanssa **AddMediaWithImage** ohjausobjekti lisätty, määritä sen korkeus on pienempi kuin 210.
1. Valitse ohjausobjekti puunäkymä **AddMediaWithImage** > **...**   >  **Järjestäminen uudelleen** > **Lähetä taustalle**.
   Tämä ohjausobjekti estää Istuva eteen **PeopleBrowseGallery** ohjausobjektin.
1. Muuta **korkeus** ominaisuuden **EmailPeopleGallery** tämä kaava:

    ```powerapps-dot
    Min( 
        ( EmailPeopleGallery1.TemplateHeight + EmailPeopleGallery1.TemplatePadding * 2 ) *
            RoundUp( CountRows( EmailPeopleGallery1.AllItems ) / 2, 0 ), 
        304
    )
    ```

1. Määritä **ShowScrollbar** ominaisuuden **EmailPeopleGallery** seuraava lauseke:

    ```EmailPeopleGallery1.Height >= 304```
    
    Tämä estää enimmäisarvo korkeus katsomalla **AddMediaWithImage** ohjausobjektin sivun ulkopuolella.
    
1. Muuta **OnSelect** -ominaisuuden **iconMail** ominaisuudeksi tämä kaava:

    ```powerapps-dot
    Set( _emailRecipientString, Concat(MyPeople, Mail & ";") );
    If( IsBlank( UploadedImage1 ),
        'Office365'.SendEmail( _emailRecipientString, 
            TextEmailSubject1.Text, 
            TextEmailMessage1.Text, 
            { Importance: "Normal" }
        ),
        'Office365'.SendEmail( _emailRecipientString, 
            TextEmailSubject1.Text, 
            TextEmailMessage1.Text, 
            {
                Importance: "Normal",
                Attachments: Table(
                    {
                        Name: "Image.jpg", 
                        ContentBytes: UploadedImage1.Image
                    }
                )
            }
        )
    );
    Reset( TextEmailSubject1 );
    Reset( TextEmailMessage1 );
    Reset( AddMediaButton1 );
    Clear( MyPeople )
    ```
    
    Tämä kaava tarkistaa ladatun kuvan. Jos ei mitään, sitten se käyttää samaa `Office365.SendEmail` toiminto kuin aiemmin. Jos kuvan, se lisätään liitteenä liitteitä-taulukossa.
    Sähköposti, ylimääräinen lähettämisen jälkeen **vaihtaa** toiminto suoritetaan **AddMediaButton** poistaa ladatun kuvan.
> [!NOTE]
> Useamman kuin yhden sähköpostiviestin liitteen lisäämiseen lisätä tietueita liitteitä-taulukkoon.

### <a name="show-different-data-for-people"></a>Näytä eri ihmisiä

Tämä näyttö käyttää [Office365Users.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) toiminto etsiä käyttäjiä, org. Se tarjoaa Lisää kenttiä-tapahtuman ulkopuolella mitä tulee näkyviin **PeopleBrowseGallery** ohjausobjektin. Lisätä tai muuttaa valikoimassa kentät on yksinkertainen:

1. Tässä **PeopleBrowseGallery** ohjausobjekti, valitse Muokkaa (tai Lisää yksi ja valittuna) nimi.

1. Kanssa sen **tekstin** ominaisuus on valittuna kaavariville, korvaa sisältöä `ThisItem.`

    IntelliSense näkyy luettelo kentistä, jotka voit valita.

1. Valitse haluamasi kenttä.

    **Tekstin** ominaisuuden päivittää `ThisItem.{FieldSelection}`.

## <a name="integrate-the-screen-into-an-app"></a>Näytön integrointi sovellukseen

Sähköpostiviesti-ruutu on tehokas nipun ohjausobjektien oma, mutta se toimii parhaiten yleensä suurempi, monipuolisempia sovelluksen osana. Voit integroida suurempi sovelluksen useilla eri tavoilla, mukaan lukien tämä näyttö [kalenterin näytön linkittäminen](email-screen-overview.md#linking-to-the-calendar-screen).

### <a name="linking-to-the-calendar-screen"></a>Linkittäminen Kalenteri-näyttö

”Näytä tapahtuman osallistujat” osan ohjeiden [kalenterin näytön yleiskatsaus](./calendar-screen-overview.md#show-event-attendees) kuitenkin viimeinen vaihe, Määritä **Navigate** funktio avaa sähköpostiviesti-ruutu. Kun nämä vaiheet on suoritettu **MyPeople** kokoelma täytetään, jonka avulla käyttäjät voivat lähettää sähköpostiviestin niille henkilöille, jotka ovat osallistua valitun tapahtuman.

> [!NOTE]
> Tämän sähköpostin lähettäminen lähettää erilliset sähköpostiviestin Outlook todellinen tapahtumasta.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Näytä tämä näyttö ohjeessa](./email-screen-reference.md).
* [Lue lisätietoja Office 365-käyttäjät-liittimellä powerappsissa](../connections/connection-office365-users.md).
* [Katso kaikki käytettävissä olevat yhteydet powerappsin](../connections-list.md).
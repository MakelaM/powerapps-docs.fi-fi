---
title: Sähkö posti-näytön malli | Microsoft Docs
description: Tutustu siihen, miten pohjaan kuuluvien sovellusten Sähkö posti näytön malli toimii, ja laajenna näyttöä omiin käyttö tapauksiisi
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/29/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 2fd03b1a54b54c1abe1d6c30270861b6fc9b8054
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71989346"
ms.PowerAppsDecimalTransform: true
---
# <a name="overview-of-the-email-screen-template-for-canvas-apps"></a>Pohjaan kuuluvien sovellusten Sähkö posti näytön mallin yleiskatsaus

Lisää kangas sovelluksessa Sähkö posti näyttö, jonka avulla käyttäjät voivat lähettää sähkö posti viestin Office 365 Outlook-tililtäsi. Käyttäjät voivat hakea vastaanottajia niiden orgista ja lisätä myös ulkoisia Sähkö posti osoitteita. Voit lisätä kuva-liitteen tuen, muuttaa käyttäjä tietoja, jotka näkyvät haku valikoimassa, ja tehdä muita mukautuksia.

Voit myös lisätä muita mallipohjaisia näyttöjä, jotka näyttävät eri tietoja Office 365: sta, kuten käyttäjän [kalenterista](calendar-screen-overview.md), organisaation [henkilöistä](people-screen-overview.md) ja käyttäjien [saatavuudesta](meeting-screen-overview.md) .

Tässä yleiskatsauksessa opit:
> [!div class="checklist"]
> * Oletus Sähkö posti näytön käyttäminen.
> * Sen muokkaaminen.
> * Miten voit integroida sen sovellukseen.

Lisä tietoja tämän näytön oletusarvoisesta toiminnosta on [Sähkö posti-näytön viitta](email-screen-reference.md)uksessa.

## <a name="prerequisite"></a>Edellytys

Perehtyneisyys näyttöjen ja muiden ohjaus objektien lisäämiseen ja määrittämiseen [, kun luot sovelluksen Powerappsissa](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Oletus toiminto

Sähkö posti näytön lisääminen mallista:

1. [Kirjaudu sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin ja luo sitten sovellus tai Avaa olemassa oleva sovellus PowerApps Studio.

    Tässä ohje aiheessa näytetään Puhelin sovellus, mutta samat käsitteet koskevat myös Tablet-sovellusta.

1. Valitse valinta nauhan **Aloitus** -väli lehdeltä **Uusi näyttö** > **Sähkö posti**.

    Oletus arvon mukaan näyttö näyttää seuraavanlaiselta:

    ![Sähkö posti näyttö](media/email-screen/email-screen-full.png)

Muutama hyödyllinen Huomautus:

* Jos haluat hakea käyttäjiä organisaatiollesi, ala kirjoittaa heidän nimeään teksti syöte ruutuun alla "to".
* Kun etsit henkilöitä, vain 15 parasta tulosta palautetaan.
* Jos haluat lisätä Sähkö posti osoitteita organisaatiosi ulkopuolisille Sähkö posti vastaanottajille, kirjoita täydellinen, kelvollinen Sähkö posti osoite ja valitse sen oikealla puolella näkyvä +-kuvake.
* Sinun on lisättävä vähintään yksi henkilö vastaanottajaksi ja annettava aihe, jotta voit lähettää sähkö posti viestin.
* Kun olet lähettänyt Sähkö posti viestin, Kaikki Aihe rivin ja viestin leipä tekstin sisällöt sekä vastaanottajien luettelo poistetaan.

## <a name="modify-the-screen"></a>Muokkaa näyttöä

Voit muokata tämän näytön oletus toimintoja muutamalla yhteisellä tavalla:

* [Lisää Image-Attachment-tuki](email-screen-overview.md#add-image-attachment-support)
* [Näytä eri tiedot henkilöille](email-screen-overview.md#show-different-data-for-people)

Jos haluat muokata näyttöä edelleen, käytä apuna [Sähkö posti näytön viittausta](./email-screen-reference.md) .

> [!IMPORTANT]
> Seuraavissa vaiheissa oletetaan, että olet lisännyt sovellukseen vain yhden Sähkö posti näytön. Jos olet lisännyt useamman kuin yhden, ohjaus objektien nimet (kuten **iconMail1**) päättyvät eri numeroon, ja sinun on säädettävä kaavoja vastaavasti.

### <a name="add-image-attachment-support"></a>Lisää Image-Attachment-tuki

Tämän avulla käyttäjät voivat lähettää yksittäisen kuvan Sähkö posti osoitteenaan liitteenä.

1. Valitse **Lisää** -väli lehdeltä **tieto väline**ja valitse sitten **Lisää kuva**.
1. Määrittää uuden ohjaus objektin **yy** -ominaisuudeksi tämän lausekkeen:

    `TextEmailMessage1.Y + TextEmailMessage1.Height + 20`
    
1. Kun **Addmediawithimage** -ohjaus objekti on asetettu, sen korkeuden on oltava pienempi kuin 210.
1. Valitse Control Tree-näkymässä **Addmediawithimage** >  **.** ..  > **järjestä**@no__t uudelleen-5**Lähetä takaisin-kohtaan**.
   Tämä estää ohjaus objektin käyttämisen **Peoplebrowsegallery** -ohjaus objektin edessä.
1. Muuta **Emailpeoplegallery** -ominaisuuden **Korkeus** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Min( 
        ( EmailPeopleGallery1.TemplateHeight + EmailPeopleGallery1.TemplatePadding * 2 ) *
            RoundUp( CountRows( EmailPeopleGallery1.AllItems ) / 2; 0 ); 
        304
    )
    ```

1. Voit valita **Emalyscrollery** -kohteen **Showscrollbar** -ominaisuudeksi tämän lausekkeen:

    ```EmailPeopleGallery1.Height >= 304```
    
    Tämä estää enimmäiskorkeuden työntämästä **Addmediawithimage** -ohjaus objektia pois sivulta.
    
1. Muuta **Iconmail** -ohjaus objektin **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Set( _emailRecipientString; Concat(MyPeople; Mail & ";") );;
    If( IsBlank( UploadedImage1 );
        'Office365'.SendEmail( _emailRecipientString; 
            TextEmailSubject1.Text; 
            TextEmailMessage1.Text; 
            { Importance: "Normal" }
        );
        'Office365'.SendEmail( _emailRecipientString; 
            TextEmailSubject1.Text; 
            TextEmailMessage1.Text; 
            {
                Importance: "Normal";
                Attachments: Table(
                    {
                        Name: "Image.jpg"; 
                        ContentBytes: UploadedImage1.Image
                    }
                )
            }
        )
    );;
    Reset( TextEmailSubject1 );;
    Reset( TextEmailMessage1 );;
    Reset( AddMediaButton1 );;
    Clear( MyPeople )
    ```
    
    Tämä kaava tarkistaa ladatun kuvan. Jos sellaista ei ole, se käyttää samaa `Office365.SendEmail`-toimintoa kuin ennen. Jos kuvassa on kuva, se lisätään liitteenä Liite-taulukkoon.
    Kun sähkö posti viesti on lähetetty, lisä **reset** -toiminto suoritetaan **Addmediabuctton** -kohteelle, joka poistaa ladatun kuvan.
> [!NOTE]
> Jos haluat lisätä sähkö postiin useamman kuin yhden liitteen, lisää tietueita Liite-taulukkoon.

### <a name="show-different-data-for-people"></a>Näytä eri tiedot henkilöille

Tämä näyttö käyttää [Office365Users. SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) -toimintoa etsimään käyttäjiä organisaatiollesi. Se tarjoaa lisä kenttiä kullekin tapahtumalle sen jälkeen, mitä **Peoplebrowsegallery** -ohjaus objektissa näkyy. Kenttien lisääminen tai muuttaminen valikoimassa on yksinkertaista:

1. Valitse **Peoplebrowsegallery** -ohjaus objektissa nimi, jota muokataan (tai Lisää sellainen ja säilytä se valittuna).

1. Kun sen **teksti** -ominaisuus on valittuna, korvaa sisältö kaava rivillä `ThisItem.`

    IntelliSense esittää luettelon kentistä, joita voit valita.

1. Valitse haluamasi kenttä.

    **Text** -ominaisuus päivittyy `ThisItem.{FieldSelection}`.

## <a name="integrate-the-screen-into-an-app"></a>Näytön integroiminen sovellukseen

Sähkö posti näyttö on tehokas nippu ohjaus objektien omaa oikeutta, mutta se toimii yleensä parhaiten osana suurempaa, monipuolisempaa sovellusta. Voit integroida tämän näytön suurempaan sovellukseen useilla eri tavoilla, kuten [linkittämällä kalenteri-näyttöön](email-screen-overview.md#linking-to-the-calendar-screen).

### <a name="linking-to-the-calendar-screen"></a>Linkittäminen kalenteri-näyttöön

Noudata [Calendar Screen yleiskatsaus](./calendar-screen-overview.md#show-event-attendees) -osion Näytä tapahtuman osallistujat-osion ohjeita, mutta viimeisessä vaiheessa voit avata Sähkö posti näytön **siirtymällä Navigoi** -funktiolla. Kun olet suorittanut nämä vaiheet, **Mypeople** -kokoelma täytetään, jonka avulla käyttäjät voivat lähettää sähkö postia valittuun tapahtumaan osallistuville henkilöille.

> [!NOTE]
> Tämän Sähkö posti viestin lähettäminen lähettää erillisen Sähkö posti viestin Outlookin todellisesta tapahtumasta.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Näytä tämän näytön viite asiakirjat](./email-screen-reference.md).
* [Lue lisä tietoja Office 365-käyttäjien liittimestä Powerappsissa](../connections/connection-office365-users.md).
* [Näytä kaikki Powerappsin käytettävissä olevat yhteydet](../connections-list.md).
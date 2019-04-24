---
title: Käyttäjät-näytön malli | Microsoft Docs
description: Ymmärtämään, miten ihmiset näytön malli on tarkoitettu pohjaan perustuvat sovellukset toimii ja miten laajentaa oman käyttötapauksissa näytön
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/30/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 85da6f5414cc25d1145f0fa8910e8c78bfb74533
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61536111"
---
# <a name="overview-of-the-people-screen-template-for-canvas-apps"></a>Pohjaan perustuvat sovellukset käyttäjät-näytön-mallin yleiskatsaus

Lisää ihmisiä näyttö, jossa käyttäjät voivat etsiä henkilöitä niiden organisaatioiden kangas-sovellus. Käyttäjät voivat etsiä, valitse ja lisää ihmisiä kokoelma. Voit muuttaa näytettävien tietojen näkyvät valikoimassa haun tulos ihmiset valinnat avulla voit lähettää sähköpostiviestin ja tehdä muita mukautuksia.

Voit myös lisätä malliin perustuvan muun, joka näyttää eri Office 365: stä kuten [sähköpostin](email-screen-overview.md), käyttäjän [kalenterin](calendar-screen-overview.md), ja [käytettävyysryhmän](meeting-screen-overview.md) ihmisten käyttäjät saattavat haluat kutsua kokoukseen.

Tästä yleiskatsauksesta opetetaan:
> [!div class="checklist"]
> * Miten ihmiset oletusnäytön.
> * Miten voit muokata näytön.
> * Miten voit integroida näytön sovelluksiin.

Katso tarkemmin tarkemmin tässä näytössä oletusarvon toimintoja [ihmiset näytön viittaus](people-screen-reference.md).

## <a name="prerequisite"></a>Edellytys

Miten voit lisätä ja määrittää näyttöjä ja muita ohjausobjekteja sinuna tuntee [sovelluksen luominen powerappsin](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Default-toiminnot

Lisää käyttäjät-näytön mallista:

1. [Kirjaudu sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin, ja luo sovellus tai avaa olemassa olevaa sovellusta PowerApps Studio.

    Tässä aiheessa näytetään puhelinsovelluksen, mutta samat käsitteet koskevat tablettisovellusta.

1. Valitse **aloitus** Valitse valintanauhan välilehti **uuden näytön** > **ihmiset**.

    Oletusarvon mukaan näytön näyttää tältä:

    ![Alkuperäinen ihmiset näytön tila](media/people-screen/people-screen-empty.png)

1. Käynnistä etsintä käyttäjille, Valitse yläreunan tekstisyötteen ruutu ja ala kirjoittaa työtoveri käyttäjän nimi. Hakutulokset näkyvät alla tekstisyötteen ruutu:

    ![ihmiset näytön haun tila](media/people-screen/people-browse-gall-full.png)

1. Kun valitset hakutuloksista henkilöille, ne lisätään **MyPeople** kokoelma. Hae palkki Syötearvon nollataan paljastamaan ihmiset, jotka olet valinnut kokoelma:

    ![ihmiset näytön kokoelma tulokset](media/people-screen/people-people-gall-full.png)

## <a name="modify-the-screen"></a>Muokkaa näyttö

Voit muokata oletusarvon mukaan tämä näyttö toimintoja [näytetään eri ihmisiä](people-screen-overview.md#show-different-data-for-people).

Jos haluat muokata näytön tarkemmin, käytä [ihmiset näytön viittaus](./people-screen-reference.md) ohjeena.

### <a name="show-different-data-for-people"></a>Näytä eri ihmisiä

Tämä näyttö käyttää [Office365Users.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) toiminto etsiä käyttäjiä, org. Se tarjoaa Lisää kenttiä-tapahtuman ulkopuolella mitä tulee näkyviin **UserBrowseGallery** ohjausobjektin. Lisätä tai muuttaa valikoimassa kentät on yksinkertainen prosessi:

1. Tässä **UserBrowseGallery**, valitse Muokkaa (tai Lisää yksi ja valittuna) nimi.

1. Kanssa sen **tekstin** ominaisuus on valittuna kaavariville, korvaa sisältöä `ThisItem.`

    IntelliSense näkyy luettelo kentistä, jotka voit valita.

1. Valitse haluamasi kenttä.

    **Tekstin** ominaisuuden tulee päivittää `ThisItem.{FieldSelection}`.

## <a name="integrate-the-screen-into-an-app"></a>Näytön integrointi sovellukseen

Käyttäjät-näytön on tehokas nipun ohjausobjektien oma, mutta se toimii parhaiten yleensä suurempi, monipuolisempia sovelluksen osana. Voit integroida suurempi sovelluksen useilla eri tavoilla, mukaan lukien tämä näyttö [käyttämällä välimuistissa luettelon ihmisistä](people-screen-overview.md#use-your-cached-list-of-people).

### <a name="use-your-cached-list-of-people"></a>Käytä välimuistiin henkilöiden-luettelo

Käyttäjät-näytön lisää ihmisiä tekemiesi valintojen **MyPeople** kokoelma. Tulee liiketoiminnan skenaarion kutsua henkilön hakua varten, sinun on tietää, miten voit käyttää tämän kokoelman. Tässä käy läpi tässä näytössä yhdistäminen rudimentary sähköpostiviesti-ruutu ja sähköpostiviestien lähettämiseen käyttäjille **MyPeople** kokoelma. Saat myös tietoja siitä, kuinka [sähköpostin näytön](./email-screen-overview.md) toimii.

1. Office 365 Outlook-tietolähteen lisääminen sovellukseen valitsemalla **Näytä** välilehti valitsemalla **tietolähteet** > **Lisää tietolähde**, ja etsit Office 365 outlook-liitintä. Joudut ehkä valitsemaan **uusi yhteys** löytää se.
1. Kun käyttäjät-näytön, Lisää uusi tyhjä näyttö. Tämän näytön sisällä Lisää takaisin-nuolikuvakkeen, kaksi tekstisyötteen ruutua ja Lähetä-kuvake.
1. Anna näytölle **EmailScreen**, takaisin-nuolikuvake **BackIcon**, yksi Tekstisyöte-ruutuun **SubjectLine**, muu **MessageBody**, ja Lähetä-kuvake **SendIcon**.
1. Määritä **OnSelect** ominaisuuden **BackIcon** - `Back()`.
1. Määritä **OnSelect** ominaisuuden **SendIcon** tämä kaava:

    ```powerapps-dot
    Office365.SendEmail( 
        Concat( MyPeople, UserPrincipalName & ";" ), 
        SubjectLine.Text, 
        MessageBody.Text 
    )
    ```
    
    Käytät tässä, Lähetä sähköpostiviesti Outlook-liitintä. Se välittää `Concat(MyPeople, UserPrincipalName & ";")` vastaanottajat luettelona. Tämä kaava yhdistää kaikki olevia sähköpostiosoitteita **MyPeople** kokoelma puolipisteillä erottelemalla ne yksittäiseksi merkkijonoksi. Tämä ei ole poikkeaa kirjoitettaessa ulos sähköpostiosoitteet puolipisteillä eroteltuina suosikkisähköpostiasi asiakkaan ”-”-rivillä merkkijonon.
    * Olet välittämällä `SubjectLine.Text` viestin aihe mukaan ja `MessageBody.Text` viestin tekstiosassa.
1. Lisää käyttäjät-näytön oikeassa yläkulmassa **sähköpostia** kuvake.
   Muuta kuvakkeen väri riippumatta sinulle sopii sinulle.
1. Määritä **OnSelect** -ominaisuuden **SendIcon** - `Navigate( EmailScreen, None )`.

    Sinulla on nyt kaksi näytön sovellus, jossa voit valita käyttäjät, laadi sähköpostiviestin niille ja lähettää sen. Voit testata sitä, mutta ole varovainen, sillä sovellus lähettää sähköpostiviesteille kaikille voit lisätä **MyPeople** kokoelma.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Näytä tämä näyttö ohjeessa](./people-screen-reference.md).
* [Lue lisätietoja Office 365 Outlook-liittimessä](../connections/connection-office365-outlook.md).
* [Lue lisätietoja Office 365-käyttäjät-liittimen](../connections/connection-office365-users.md).

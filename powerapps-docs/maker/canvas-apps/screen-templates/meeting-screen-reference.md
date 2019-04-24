---
title: Viittaus pohjaan perustuvat sovellukset kokouksen näytön-malli | Microsoft Docs
description: Tutustu powerappsin pohjaan perustuvat sovellukset kokouksen näytön malli toimintaan tiedot
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/03/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a7559f84b43d3c0372dea71d49c35461ba9d4e57
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61539518"
---
# <a name="reference-information-about-the-meeting-screen-template-for-canvas-apps"></a>Lisätietoja pohjaan perustuvat sovellukset kokouksen näytön-malli

Pohjaan perustuvia sovelluksia powerappsissa ymmärrä, miten merkittäviä ohjausobjekteja kokouksen näytön mallin osallistuu näytön yleistä oletusarvon toimintoja. Nämä esittää toiminta-kaavat ja arvot muita ominaisuuksia, jotka määrittävät, miten ohjausobjektit vastata käyttäjän syötettä. Lisätietoja korkean tason tässä näytössä oletusarvon toiminnot-kohdassa [kokouksen näytön yleiskatsaus](meeting-screen-overview.md).

Tässä ohjeaiheessa korostaa joitakin merkittäviä ohjausobjekteja ja kerrotaan lausekkeita tai kaavoja mitä eri ominaisuuksia (kuten **kohteet** ja **OnSelect**) ohjausobjektit on määritetty:

* [Kutsu välilehti (LblInviteTab)](#invite-tab)
* [Desimaali (LblScheduleTab)](#schedule-tab)
* [Tekstihakukenttä](#text-search-box)
* [Lisää kuvake (AddIcon)](#add-icon)
* [Ihmiset Selaa valikoimaa](#people-browse-gallery) (+ aliohjausobjektit)
* [Kokouksen ihmiset valikoiman](#meeting-people-gallery) (+ aliohjausobjektit)
* [Kokouksen päivämäärävalitsin (MeetingDateSelect)](#meeting-date-picker)
* [Kokouksen kesto avattavasta (MeetingDurationSelect)](#meeting-duration-drop-down)
* [Etsi kokouksen ajat valikoiman](#find-meeting-times-gallery) (+ aliohjausobjektit)
* [Tilaa voit selata](#room-browse-gallery) (+ aliohjausobjektit)
* [Takaisin chevron (RoomsBackNav)](#back-chevron) (ei ehkä näy, jos vuokraajan huoneet luetteloa ei ole)
* [Lähetä-kuvake](#send-icon)

## <a name="prerequisite"></a>Edellytys

Miten voit lisätä ja määrittää näyttöjä ja muita ohjausobjekteja sinuna tuntee [sovelluksen luominen powerappsin](../data-platform-create-app-scratch.md).

## <a name="invite-tab"></a>Kutsu välilehti

   ![LblInviteTab ohjausobjekti](media/meeting-screen/meeting-invite-text.png)

* Ominaisuus: **Väri**<br>
    Arvo: `If( _showDetails, LblRecipientCount.Color, RectQuickActionBar.Fill )`

    **_showDetails** on selvittää muuttuja, **LblInviteTab** ohjausobjektin tai **LblScheduleTab** ohjausobjekti on valittuna. Jos arvo **_showDetails** on **true**, **LblScheduleTab** valitaan; Jos arvo on **false**, **LblInviteTab**  on valittuna. Tämä tarkoittaa, että jos arvon **_showDetails** on **true** (tämän välilehden *ei ole* valitun), välilehti väri vastaa **LblRecipientCount**. Muussa tapauksessa se vastaa täyttö arvo **RectQuickActionBar**.

* Ominaisuus: **OnSelect**<br> 
    Arvo: `Set( _showDetails, false )`

    Määrittää **_showDetails** muuttujan **false**, mikä tarkoittaa sitä, kutsu-välilehden ovat näkyvissä ja sisällön **aikataulun** välilehti on piilotettu.

## <a name="schedule-tab"></a>Aikataulu-välilehti

   ![LblInviteTab ohjausobjekti](media/meeting-screen/meeting-schedule-text.png)

* Ominaisuus: **Väri**<br>
    Arvo: `If( !_showDetails, LblRecipientCount.Color, RectQuickActionBar.Fill )`

    **_showDetails** on selvittää muuttuja, **LblInviteTab** ohjausobjektin tai **LblScheduleTab** ohjausobjekti on valittuna. Jos se on TOSI, **LblScheduleTab** valitaan; Jos arvo on false, **LblInviteTab** on. Tämä tarkoittaa, että jos **_showDetails** on tosi (tämän välilehden *on* valitun), välilehti väri täyttö-arvo vastaa **RectQuickActionBar**. Muussa tapauksessa se vastaa väriarvon **LblRecipientCount**.

* Ominaisuus: **OnSelect**<br>
    Arvo: `Set( _showDetails, true )`

    Määrittää **_showDetails** muuttujan **true**, mikä tarkoittaa desimaali sisällön ovat näkyvissä ja kutsu-välilehden on piilotettu.

## <a name="text-search-box"></a>Tekstihakukenttä

   ![TextSearchBox ohjausobjekti](media/meeting-screen/meeting-search-box.png)

<!--Include description of text search box control?-->

Useita näytössä muiden ohjausobjektien on riippuvuus kohteeseen:

* Jos käyttäjä kirjoittaa tekstiä, käynnistää **PeopleBrowseGallery** tulee näkyviin.
* Jos käyttäjä kirjoittaa kelvollinen sähköpostiosoite **AddIcon** tulee näkyviin.
* Kun käyttäjä valitsee käyttäjän **PeopleBrowseGallery** haku-sisältö palautetaan.

## <a name="add-icon"></a>Lisäämiskuvake

   ![AddIcon ohjausobjekti](media/email-screen/email-add-icon.png)

Tämän ohjausobjektin avulla käyttäjät voivat lisätä ihmiset, jotka eivät ole osallistujien luetteloon että toistetusta kokouksen niiden organisaation sisällä.

* Ominaisuus: **Näkyvissä**<br>
    Arvo: Kolme looginen tarkistaa, että kaikki arvoksi on tultava **true** ohjausobjektin näkyvät:

    ```powerapps-dot
    !IsBlank( TextSearchBox.Text ) &&
        IsMatch( TextSearchBox.Text, Match.Email ) &&
        Not( Trim( TextSearchBox.Text ) in MyPeople.UserPrincipalName )
    ```

  Rivi kerrallaan tämän koodilohko ilmoittaa, **AddIcon** ohjausobjekti näkyy vain, jos:

  * **TextSearchBox** sisältää tekstin.
  * Tekstin **TextSearchBox** on kelvollinen sähköpostiosoite.
  * Tekstin **TextSearchBox** ei jo ole olemassa **MyPeople** kokoelma.

* Ominaisuus: **OnSelect**<br> 
    Arvo: A **kerätä** lauseke Lisää käyttäjä osallistuja luettelo toisen päivityksen käytettävissä kokouksen ajat ja useita muuttujan käytössä tai pois käytöstä:

    ```powerapps-dot
    Collect( MyPeople,
        { 
            DisplayName: TextSearchBox.Text, 
            UserPrincipalName: TextSearchBox.Text, 
            Mail: TextSearchBox.Text
        }
    );
    Concurrent(
        Reset( TextSearchBox ),
        Set( _showMeetingTimes, false ),
        UpdateContext( { _loadMeetingTimes: true } ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false ),
        ClearCollect( MeetingTimes, 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    { 
                        RequiredAttendees: Concat(MyPeople, UserPrincipalName & ";")
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ),
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                        MaxCandidates: 15, 
                        MinimumAttendeePercentage:1, 
                        IsOrganizerOptional: false, 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions,
                "StartTime", MeetingTimeSlot.Start.DateTime, 
                "EndTime", MeetingTimeSlot.End.DateTime
            )
        )
    );
    UpdateContext( { _loadingMeetingTimes: false } );
    Set( _showMeetingTimes, true )
    ```

  Valitsemalla tämän ohjausobjektin Lisää kelvollinen sähköpostiosoite (näkyvissä vain, jos kelvollinen sähköpostiosoite on kirjoitettu **TextSearchBox**)- **MyPeople** kokoelma (tässä kokoelmassa on osallistujien luettelo) ja sitten päivittää käytettävissä ajat uuden käyttäjän tapahtuman.

  Alhaisen tason, tämä koodilohko:
  1. Kerää tietoja sähköpostiosoite **MyPeople** kokoelman, kerätä tietoja sähköpostiosoite **DisplayName**, **UserPrincipalName**, ja **sähköpostia**  kentät.
  1. Palauttaa sisällön **TextSearchBox** ohjausobjektin.
  1. Määrittää **_showMeetingTimes** muuttujan **false**. Tämä muuttujaa määrittää näkyvyyden **FindMeetingTimesGallery**, joka näyttää avoinna kertaa valitun osallistujien täyttämiseksi.
  1. Määrittää **_loadMeetingTimes** kontekstimuuttujan **true**. Tämä muuttujaa määrittää lataamisen-tilassa, joka näyttää tai piilottaa näkyvyyden tilan ohjausobjekteja, kuten ladataan **_LblTimesEmptyState** osoittamaan käyttäjälle, että niiden tiedot ladataan.
  1. Määrittää **_selectedMeetingTime** - **kohteen Blank()**. **_selectedMeetingTime** on valittu tietue **FindMeetingTimesGallery** ohjausobjektin. Se on tyhjinä tähän toinen osallistujien lisäämistä saattaa tarkoittaa, Edellinen määritys **_selectedMeetingTime** on ei ole käytettävissä kyseisen osallistujan.
  1. Määrittää **_selectedRoom** - **kohteen Blank()**. **_selectedRoom** on valittu tilaa tietueen **RoomBrowseGallery**. Tilaa saatavuuden määritetään arvosta **_selectedMeetingTime**. Kyseistä arvoa nimet **_selectedRoom** arvo ei ole enää kelvollinen, joten se on nimet.
  1. Määrittää **_roomListSelected** - **false**. Tämä rivi ei ehkä ole käytettävissä kaikille. Office-voi ryhmitellä-tiloissa eri ”huoneluettelo”. Jos sinulla on huoneluettelot, tämä näyttö muuttujalle kyseisen, jonka avulla voit valita huoneluettelo ennen kuin valitset huoneessa kuin kyseisen luettelon. Arvon **_roomListSelected** on mikä määrittää, onko käyttäjä (vuokraajan kanssa vain huoneluettelot) tarkastelevat huoneet huoneluettelo tai huoneluettelot joukko. Se määritetään **false** pakottaa käyttäjät voivat valita uuden huoneluettelo.
  1. Käyttää [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) toiminto määrittää ja kerätä käytettävissä kokouksen ajat osallistujien. Tämä toiminto siirtää:
      * **UserPrincipalName** kukin valitun käyttäjän *RequiredAttendees* parametri.
      * **MeetingDurationSelect**. Selected.Minutes into *MeetingDuration* parametri.
      * MeetingDateSelect.SelectedDate + kahdeksan tunnin jakson into *Aloita* parametri. Kahdeksan tunnin lisätään, koska kalenteri-ohjausobjektin koko päivämäärä/kellonaika on oletusarvoisesti 12:00 AM valittu päivämäärä. Haluat todennäköisesti noutaa saatavuuden normaalin työajan sisällä. Normaali työ alkamisaika olisi klo 8.00.
      * **MeetingDateSelect**. SelectedDate + 17 tuntia into *loppuun* parametri. 17 tuntia lisätään, koska 12:00 AM + 17 = 5:00 PM. Normaali työ päättymisaika olisi 5:00 PM.
      * *15* into *MaxCandidates* parametri. Tämä tarkoittaa sitä toiminto palauttaa vain alusta 15 vapaan ajan varten valittu päivämäärä. Tämä on järkevää, koska on vain kuusitoistavuotias 30 minuutin lohkot 8 tuntia työpäivä ja 30 minuutin kokous on vähintään yksi määritetty tässä näytössä.
      * *1* into *MinimumAttendeePercentage* parametri. Käytännössä, jos ei ole osallistujat eivät ole käytettävissä, kokouksen aika noudetaan.
      * **EPÄTOSI** into *IsOrganizerOptional* parametri. Sovelluksen käyttäjälle ei ole valinnainen osallistujien kokoukselle.
      * ”Työ” *ActivityDomain* parametri. Tämä tarkoittaa, että noutaa ajat ovat vain ne sisällä normaalin työajan ajan.
  1. **ClearCollect** funktio lisää myös kaksi saraketta: ”StartTime” ja ”EndTime”. Tämä yksinkertaistaa palautetut tiedot. 
  Kenttä, joka sisältää käytettävissä alkamis- ja päättymispäivät **MeetingTimeSlot** kenttä. Tämä kenttä on tietueen, joka sisältää alun ja lopun tietueita, joiden sisältää **DateTime** ja **aikavyöhyke** niiden vastaavan ehdotus arvot. Sijaan yritettäessä noutaa tämän sisäkkäisyyttä tietueiden, lisäämällä ”StartTime” ja ”EndTime” sarakkeet **MeetingTimes** kokoelma tuo ne **Aloita > DateTime** ja **loppuun > DateTime** surface kokoelman arvot.
  1. Kun nämä funktiot kaikki on valmis, **_loadingMeetingTimes** muuttuja on asetettu **false**, poistetaan lataamista, tila ja **_showMeetingTimes** asetetaan**true**, näkyvä **FindMeetingTimesGallery**.

## <a name="people-browse-gallery"></a>Ihmiset Selaa valikoimaa

   ![PeopleBrowseGallery ohjausobjekti](media/meeting-screen/meeting-browse-gall.png)

* Ominaisuus: **Kohteet**<br>
    Arvo: 
    ```powerapps-dot
    If( !IsBlank( Trim( TextSearchBox.Text ) ), 
        'Office365Users'.SearchUser( { searchTerm: Trim(TextSearchBox.Text), top: 15 } )
    )
    ```

Valikoiman kohteet täytetään hakutulosten mukaan [Office365.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) toiminto. Toiminto hakee teksti `Trim(**TextSearchBox**)` kuin etsinnän termi ja palauttaa ylimmät 15 tulosten perusteella kyseistä hakua.
  
**TextSearchBox** rivittyy **Trim** funktiolla, koska käyttäjän haku välilyöntejä, ei ole kelvollinen. `Office365Users.SearchUser` Toiminto rivittyy `If(!IsBlank(Trim(TextSearchBox.Text)) ... )` funktiolla, koska suorituskyky kätevästi noudetaan hakutulokset, ennen kuin käyttäjä etsintä on on.

### <a name="people-browse-gallery-title"></a>Ihmiset Selaa valikoimaa otsikko

   ![PeopleBrowseGallery otsikko-ohjausobjekti](media/meeting-screen/meeting-browse-gall-title.png)

* Ominaisuus: **Teksti**<br>
    Arvo: `ThisItem.DisplayName`

    Näyttää niiden Office 365-profiilista henkilön näyttönimi.

* Ominaisuus: **OnSelect**<br>
    Arvo: A **kerätä** lauseke Lisää käyttäjä osallistuja luettelo toisen päivityksen käytettävissä kokouksen ajat ja useita muuttujan käytössä tai pois käytöstä:

    ```powerapps-dot
    Concurrent(
        Reset( TextSearchBox ),
        Set( _selectedUser, ThisItem ),
        If( Not( ThisItem.UserPrincipalName in MyPeople.UserPrincipalName ), 
            Collect( MyPeople, ThisItem ); 
            Concurrent(
                Set( _showMeetingTimes, false ),
                UpdateContext( { _loadMeetingTimes: true } ),
                Set( _selectedMeetingTime, Blank() ),
                Set( _selectedRoom, Blank() ),
                Set( _roomListSelected, false ),
                ClearCollect( MeetingTimes, 
                    AddColumns(
                        'Office365'.FindMeetingTimes(
                            {
                                RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ),
                                MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                                Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ),
                                End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                                MaxCandidates: 15, 
                                MinimumAttendeePercentage: 1, 
                                IsOrganizerOptional: false, 
                                ActivityDomain: "Work"
                            }
                        ).MeetingTimeSuggestions,
                        "StartTime", MeetingTimeSlot.Start.DateTime, 
                        "EndTime", MeetingTimeSlot.End.DateTime
                    )
                )
            );
            UpdateContext( { _loadingMeetingTimes: false } );
            Set( _showMeetingTimes, true )
        )
    )
    ```

    Suuren tasolla tämän ohjausobjektin valitsemalla Lisää henkilö **MyPeople** kokoelma (sovelluksen tallennus osallistujien luettelo) ja päivittää käytettävissä kokouksen ajat perusteella käyttäjä lisätty.

    Valitsemalla tämän ohjausobjektin muistuttaa valitsemalla **AddIcon** ohjausobjektin; ainoa ero on se, että `Set(_selectedUser, ThisItem)` lauseke ja toiminnot suorittamisen järjestystä. Näin ollen tämän keskustelun ei ole yhtä syvä. Lue täydellisemmän selitys [AddIcon ohjausobjektin](#add-icon) osiossa.

    Valitsemalla tämän ohjausobjektin nollaa **TextSearchBox**. Jos valinta ei ole **MyPeople** kokoelman, ohjausobjekti:
    1. Määrittää **_loadMeetingTimes** tila- **true** ja **_showMeetingTimes** tila- **false**, tyhjät **_ selectedMeetingTime** ja **_selectedRoom** muuttujia ja päivityksiä **MeetingTimes** kokoelma, jossa on lisätty **MyPeople** kokoelma. 
    1. Määrittää **_loadMeetingTimes** tila- **false**, ja asettaa **_showMeetingTimes** - **true**. Jos valinta on jo kokoelmassa **MyPeople** kokoelman, se palauttaa vain sisällön **TextSearchBox**.

## <a name="meeting-people-gallery"></a>Kokouksen ihmiset valikoima

   ![MeetingPeopleGallery ohjausobjekti](media/meeting-screen/meeting-people-gall.png)

* Ominaisuus: **Kohteet**<br>
    Arvo: `MyPeople`

    **MyPeople** kokoelma on alustettu tai valitsemalla lisätään kokoelma **PeopleBrowseGallery otsikko** ohjausobjektin.

* Ominaisuus: **Korkeus**<br>
    Arvo: Salli valikoiman kasvamaan enimmäiskorkeus 350 logiikan:

    ```powerapps-dot
    Min( 
        76 * RoundUp( CountRows( MeetingPeopleGallery.AllItems ) / 2, 0 ),
        350
    )
    ```

  
   Valikoiman korkeus säätää enimmäiskorkeus 350 valikoiman kohteiden määrä. Kaavalle 76 kuin yhden rivin korkeus **MeetingPeopleGallery**, kertoo sen rivien määrän mukaan. **WrapCount** ominaisuuden arvo on 2, joten true rivien määrä on `RoundUp(CountRows(MeetingPeopleGallery.AllItems) / 2, 0)`.

* Ominaisuus: **ShowScrollbar**<br>
    Arvo: `MeetingPeopleGallery.Height >= 350`

    Kun valikoiman enimmäiskorkeus on saavutettu (350), vierityspalkin on näkyvissä.

### <a name="meeting-people-gallery-title"></a>Kokouksen ihmiset valikoiman otsikko

   ![MeetingPeopleGallery otsikko-ohjausobjekti](media/meeting-screen/meeting-people-gall-title.png)

* Ominaisuus: **OnSelect**<br>
    
    Arvo: `Set(_selectedUser, ThisItem)`
    
    Määrittää **_selectedUser** muuttujan valitun kohteen **MeetingPeopleGallery**.

### <a name="meeting-people-gallery-iconremove"></a>Kokouksen ihmiset valikoiman iconRemove

   ![MeetingPeopleGallery iconRemove ohjausobjekti](media/meeting-screen/meeting-people-gall-delete.png)

* Ominaisuus: **OnSelect**<br>
    Arvo: A **poistaa** lauseke, voit poistaa käyttäjän osallistujien-luettelosta **kerätä** lauseke päivittää käytettävissä kokouksen ajat ja useita muuttujan käytössä tai pois käytöstä:

    ```powerapps-dot
    Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) );
    Concurrent(
        Reset( TextSearchBox ),
        Set( _showMeetingTimes, false ),
        UpdateContext( { _loadMeetingTimes: true } ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false ),
        ClearCollect( MeetingTimes, 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    {
                        RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ), 
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ), 
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                        MaxCandidates: 15, 
                        MinimumAttendeePercentage: 1, 
                        IsOrganizerOptional: false, 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions,
                "StartTime", MeetingTimeSlot.Start.DateTime, 
                "EndTime", MeetingTimeSlot.End.DateTime
            )
        )
    );
    UpdateContext( { _loadingMeetingTimes: false } );
    Set( _showMeetingTimes, true )
    ```

  Tason valitsemalla tämän ohjausobjektin poistaa henkilön osallistujien-luettelosta ja päivittää käytettävissä kokouksen ajat, tämä henkilö poistaminen perusteella.

  Edellä oleva koodi ensimmäisen rivin jälkeen valitsemalla tämä ohjausobjekti on lähes samanlaista valitsemalla **AddIcon** ohjausobjektin. Näin ollen tämän keskustelun eivät ole yhtä syvä. Lue täydellisemmän selitys [AddIcon ohjausobjektin osan](#add-icon).

  Valittu kohde poistetaan koodin ensimmäisellä rivillä **MyPeople** kokoelma. Koodin sitten:
  1. Palauttaa **TextSearchBox**, ja poistaa valinnan **MyPeople** kokoelma. 
  1. Määrittää **_loadMeetingTimes** tila- **true** ja **_showMeetingTimes** tila- **false**, tyhjät **_ selectedMeetingTime** ja **_selectedRoom** muuttujia ja päivityksiä **MeetingTimes** kokoelma, jossa on lisätty **MyPeople** kokoelma. 
  1. Määrittää **_loadMeetingTimes** tila- **false**, ja asettaa **_showMeetingTimes** - **true**.

## <a name="meeting-date-picker"></a>Kokouksen päivämäärävalitsin

   ![MeetingDateSelect ohjausobjekti](media/meeting-screen/meeting-datepicker.png)

* Ominaisuus: **DisplayMode**<br>
    Arvo: `If( IsEmpty(MyPeople), DisplayMode.Disabled, DisplayMode.Edit )`

    Kokouksen päivämäärä ei voi valita, kunnes vähintään yksi osallistujien on lisätty **MyPeople** kokoelma.

* Ominaisuus: **OnChange**<br>
    Arvo: `Select( MeetingDateSelect )`

    Valitun päivämäärän muuttaminen käynnistää koodia **OnSelect** Text suorittamiseen.

* Ominaisuus: **OnSelect**<br>
    Arvo: A **kerätä** lauseke päivittää käytettävissä kokouksen ajat ja useita muuttujan käytössä tai pois käytöstä:
  
    ```powerapps-dot
    Concurrent(
        Reset( TextSearchBox ),
        Set( _showMeetingTimes, false ),
        UpdateContext( { _loadingMeetingTimes: true } ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false ),
        ClearCollect( MeetingTimes, 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    {
                        RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ), 
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ), 
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                        MaxCandidates: 15, 
                        MinimumAttendeePercentage: 1, 
                        IsOrganizerOptional: false, 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions,
                "StartTime", MeetingTimeSlot.Start.DateTime, 
                "EndTime", MeetingTimeSlot.End.DateTime
            )
        )
    );
    UpdateContext( { _loadingMeetingTimes: false } );
    Set( _showMeetingTimes, true )
    ```

  Korkean tason valitsemalla tämä ohjausobjekti päivittyy käytettävissä kokouksen ajat. Tämä on arvokas, koska jos käyttäjä muuttaa päivämäärän, käytettävissä kokouksen ajat tarvitse päivitetään osallistujien saatavuuden päivän.

  Lukuun ottamatta alkuperäiset **kerätä** lauseke, tämä on sama kuin **OnSelect** toimintoja **AddIcon** ohjausobjektin. Näin ollen tämän keskustelun eivät ole yhtä syvä. Lue täydellisemmän selitys [AddIcon ohjausobjektin](#add-icon) osiossa.

  Valitsemalla tämän ohjausobjektin nollaa **TextSearchBox**. Se sitten: 
  1. Määrittää **_loadMeetingTimes** tila- **true** ja **_showMeetingTimes** tila- **false**, tyhjät **_ selectedMeetingTime** ja **_selectedRoom** muuttujia ja päivityksiä **MeetingTimes** kokoelma, jossa on uusi päivämäärä-valinta. 
  1. Määrittää **_loadMeetingTimes** tila- **false**, ja asettaa **_showMeetingTimes** - **true**.

## <a name="meeting-duration-drop-down"></a>Kokouksen kesto avattava valikko

   ![MeetingDateSelect ohjausobjekti](media/meeting-screen/meeting-timepicker.png)

* Ominaisuus: **DisplayMode**<br>
    Arvo: `If( IsEmpty(MyPeople), DisplayMode.Disabled, DisplayMode.Edit )`

    Kokouksen kesto ei voi valita, kunnes vähintään yksi osallistujien on lisätty **MyPeople** kokoelma.

* Ominaisuus: **OnChange**<br>
    Arvo: `Select(MeetingDateSelect1)`

    Muuttaa valitun kesto käynnistää koodia **OnSelect** -ominaisuuden **MeetingDateSelect** ohjausobjektin suorittamiseen.

## <a name="find-meeting-times-gallery"></a>Etsi kokouksen ajat valikoima

   ![FindMeetingTimesGallery ohjausobjekti](media/meeting-screen/meeting-time-gall.png)

* Ominaisuus: **Kohteet**<br>
    Arvo: `MeetingTimes`

    Mahdollinen kokouksen ajat kokoelma noudetut [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) toiminto.

* Ominaisuus: **Näkyvissä**<br>
    Arvo: `_showMeetingTimes && _showDetails && !IsEmpty( MyPeople )`

    Valikoiman on näkyvissä vain, jos **_showMeetingTimes** asetetaan **true**, käyttäjä on valinnut **LblScheduleTab** ohjausobjektin, ja vähintään yksi osallistujien lisätään kokouksen.

### <a name="find-meeting-times-gallery-title"></a>Etsi kokouksen ajat valikoiman otsikko

   ![FindMeetingTimesGallery otsikko-ohjausobjekti](media/meeting-screen/meeting-time-gall-title.png)

* Ominaisuus: **Teksti**<br>
    Arvo: Muuntaminen, joka näytetään käyttäjän paikallisen ajan alkamisaika:

    ```powerapps-dot
    Text(
        DateAdd(
            DateTimeValue( ThisItem.StartTime ),
            - TimeZoneOffset(), 
            Minutes
        ),
        DateTimeFormat.ShortTime
    )
    ```

  Noudetun arvon **StartTime** ovat UTC-muodossa. Jos haluat [muuntaa paikallisen ajan UTC](../functions/function-dateadd-datediff.md#converting-from-utc), **DateAdd** funktio otetaan käyttöön.
  [Tekstitoiminto](../functions/function-text.md#datetime) ottaa päivämäärän/ajan sen ensimmäinen argumentti ja sen perustuvat toisen argumentin. Voit välittää sitä paikallisen ajan muuntaminen **ThisItem.StartTime**, ja Näytä se **DateTimeFormat.ShortTime**.

* Ominaisuus: **OnSelect**<br>
    Arvo: Useita **kerätä** lausekkeita kerätä kokouksen huoneet ja niiden ehdotetut saatavuuden sekä useita muuttujan käytössä tai pois käytöstä:

    ```powerapps-dot
    Set( _selectedMeetingTime, ThisItem );
    UpdateContext( { _loadingRooms: true } );
    If( IsEmpty( RoomsLists ),
        ClearCollect( RoomsLists, 'Office365'.GetRoomLists().value) );
    If( CountRows( RoomsLists ) <= 1,
        Set( _noRoomLists, true );
        ClearCollect( AllRooms, 'Office365'.GetRooms().value );
        Set( _allRoomsConcat, Concat( FirstN( AllRooms, 20 ), Address & ";" ) );
        ClearCollect( RoomTimeSuggestions, 
            'Office365'.FindMeetingTimes(
                {
                    RequiredAttendees: _allRoomsConcat, 
                    MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                    Start: _selectedMeetingTime.StartTime & "Z", 
                    End: _selectedMeetingTime.EndTime & "Z", 
                    MinimumAttendeePercentage: "1",
                    IsOrganizerOptional: "false", 
                    ActivityDomain: "Unrestricted"
                }
            ).MeetingTimeSuggestions
        );
        ClearCollect( AvailableRooms, 
            AddColumns(
                AddColumns(
                    Filter( 
                        First( RoomTimeSuggestions ).AttendeeAvailability,
                        Availability="Free"
                    ), 
                    "Address", Attendee.EmailAddress.Address
                ), 
                "Name", LookUp( AllRooms, Address = Attendee.EmailAddress.Address ).Name 
            )
        );
        ClearCollect( AvailableRoomsOptimal, 
            DropColumns(
                DropColumns( AvailableRooms, "Availability" ), 
                "Attendee" 
            )
        ),
        Set( _roomListSelected, false) 
    );
    UpdateContext( {_loadingRooms: false} )
    ```

  Tason tämä koodilohko rekisteröitävät käyttäjät, joilla ei ole käytettävissä tilat tiloissa luetteloita, kokouksen valittu päivämäärä/kellonaika. Se muussa tapauksessa yksinkertaisesti hakee huoneet luettelot.

  Alhaisen tason, tämä koodilohko:
  1. Määrittää **_selectedMeetingTime** valittuun kohteeseen. Tätä käytetään mitä tilat ovat käytettävissä tänä aikana.
  1. Määrittää lataamista tila muuttujan **_loadingRooms** - **true**, ladataan-tila käyttöön.
  1. Jos **RoomsLists** kokoelma on tyhjä, se hakee käyttäjän vuokraajassa huoneet luetteloita ja tallentaa ne **RoomsLists** kokoelma.
  1. Jos käyttäjä ei ole huoneluettelo tai yksi huoneluettelo:
      1. **NoRoomLists** muuttuja on asetettu **true**, ja tämä muuttujaa käytetään määrittämään näkyvät kohteet **RoomBrowseGallery** ohjausobjektin.
      1. `Office365.GetRooms()` Toiminnolla noutaa heidän vuokraajakäytännöissään ensimmäiset 100 tiloissa. Nämä tallennetaan **AllRooms** kokoelma.
      1. **_AllRoomsConcat** muuttuja on asetettu ensimmäisen huoneiden 20 sähköpostiosoitteet puolipistein eroteltu merkkijonon **AllRooms** kokoelma. Tämä johtuu siitä, [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) on rajoitettu käytettävissä kertaa objektien 20 henkilön yhdellä toiminnolla haetaan.
      1. **RoomTimeSuggestions** kokoelma käyttää [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) noutaa ensin 20 tiloissa saatavuuden **AllRooms** kokoelman, mukaan on aika-arvoista **_selectedMeetingTime** muuttuja. Huomaa, että `& "Z"` on käytettävä muotoilumerkkijono oikein **DateTime** arvo.
      1. **AvailableRooms** luodaan kokoelma. Tämä on yksinkertaisesti **RoomTimeSuggestions** osallistujien saatavuuden kaksi muita saraketta, se lisätään sisältävä kokoelma: ”Address” ja ”Name”. ”Address” on huoneen sähköpostiosoite ja ”Name” on ryhmän nimen.
      1. Sitten, **AvailableRoomsOptimal** luodaan kokoelma. Tämä on vain **AvailableRooms** kokoelma, jossa on sarakkeet ”Käytettävyysryhmän” ja ”osallistuja” on poistettu. Tämä vastaa rakenteet **AvailableRoomsOptimal** ja **AllRooms**. Näin voit käyttää molemmat kokoelmat- **kohteet** -ominaisuuden **RoomBrowseGallery**.
      1. **_roomListSelected** asetetaan **false**.
  1. Ladataan-tilassa, **_loadingRooms**, on määritetty **false** kun kaikki muut suorittaminen on päättynyt.

## <a name="room-browse-gallery"></a>Valikoiman selauksen tilaa

   ![RoomBrowseGallery ohjausobjekti](media/meeting-screen/meeting-rooms-gall.png)

* Ominaisuus: **Kohteet**<br>
    Arvo: Määritä loogisesti kaksi identtistä rakenne, sen mukaan, onko käyttäjä on valinnut huoneluettelo tai huoneet luettelot heidän vuokraajakäytännöissään sisäinen kokoelmia:

    ```powerapps-dot
    Search(
        If( _roomListSelected || _noRoomLists, AvailableRoomsOptimal, RoomsLists ),
        Trim(TextMeetingLocation1.Text), 
        "Name", 
        "Address"
    )
    ```

  Tämä valikoima näyttää **AvailableRoomsOptimal** kokoelma Jos **_roomListSelected** tai **_noRoomLists** on **true**. Muussa tapauksessa se näyttää **RoomsLists** kokoelma. Tämä onnistuu, koska nämä kokoelmat rakenteen ovat samat.

* Ominaisuus: **Näkyvissä**<br>
    Arvo: ```_showDetails && !IsBlank( _selectedMeetingTime ) && !_loadingRooms```

    Valikoimassa näkyy vain, jos kolmen edellisen lausekkeita arvoksi tulee **true**.

### <a name="roombrowsegallery-title"></a>RoomBrowseGallery otsikko

   ![RoomBrowseGallery otsikko-ohjausobjekti](media/meeting-screen/meeting-rooms-gall-title.png)

* Ominaisuus: **OnSelect**<br>
    Arvo: Joukon loogisesti sidotun **kerätä** ja **määrittää** lausekkeita, joka saattaa tai saattaa ei voi käynnistää, sen mukaan, onko käyttäjä tarkastelee huoneluettelot tai tilat:

    ```powerapps-dot
    UpdateContext( { _loadingRooms: true } );
    If( !_roomListSelected && !noRoomLists,
        Set( _roomListSelected, true );
        Set( _selectedRoomList, ThisItem.Name );
        ClearCollect( AllRooms, 'Office365'.GetRoomsInRoomList( ThisItem.Address ).value );
        Set( _allRoomsConcat, Concat( FirstN( AllRooms, 20 ), Address & ";" ) );
        ClearCollect( RoomTimeSuggestions, 
            'Office365'.FindMeetingTimes(
                {
                    RequiredAttendees: _allRoomsConcat, 
                    MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: _selectedMeetingTime.StartTime & "Z", 
                    End: _selectedMeetingTime.EndTime & "Z", 
                    MinimumAttendeePercentage: "1",
                    IsOrganizerOptional: "false", 
                    ActivityDomain: "Unrestricted"
                }
            ).MeetingTimeSuggestions
        );
        ClearCollect( AvailableRooms, 
            AddColumns(
                AddColumns(
                    Filter(
                        First( RoomTimeSuggestions ).AttendeeAvailability, 
                        Availability = "Free"
                    ),
                    "Address", Attendee.EmailAddress.Address 
                ), 
                "Name", LookUp( AllRooms, Address = Attendee.EmailAddress.Address ).Name
            )
        );
        ClearCollect( AvailableRoomsOptimal, 
            DropColumns(
                DropColumns( AvailableRooms, "Availability" )
            ), 
            "Attendee" )
        ),
        Set( _selectedRoom, ThisItem )
    );
    UpdateContext( {_loadingRooms: false} )
    ```

  Toiminnot, jotka ilmetä, kun tämä ohjausobjekti on valittuna määräytyvät sen mukaan, onko tällä hetkellä tarkastellaan joukon huoneluettelot tai joukko tiloissa. Jos se on ensiksi valitsemalla sitten tämän ohjausobjektin noutaa valitun tilaa luettelosta valitun milloin käytettävissä olevat tiloissa. Jos se on jälkimmäisen, valitsemalla tämän ohjausobjektin määrittää **_selectedRoom** muuttujan valittuun kohteeseen. Edellisen lauseke muistuttaa **Valitse** -lauseen [ **FindMeetingTimesGallery otsikko**](#find-meeting-times-gallery).

  Alhaisen tason, edellisen koodilohko:
  1. Ladataan osavaltio tiloissa ottaa käyttöön määrittämällä **_loadingRooms** - **true**.
  1. Tarkistaa, huoneluettelo on valittu ja vuokraajan on tilaa luettelo. Jos näin:
      1. Määrittää **_roomListSelected** - **true** ja määrittää **_selectedRoomList** valittuun kohteeseen.
      1. **_AllRoomsConcat** muuttuja on asetettu ensimmäisen huoneiden 20 sähköpostiosoitteet puolipistein eroteltu merkkijonon **AllRooms** kokoelma. Tämä johtuu siitä, [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) toiminto on rajoitettu käytettävissä kertaa objektien 20 henkilön yhdellä toiminnolla haetaan.
      1. **RoomTimeSuggestions** kokoelma käyttää [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) noutaa saatavuuden ensin 20 huoneiden toimintoa **AllRooms** kokoelma, perusteella aika-arvoista **_selectedMeetingTime** muuttuja. Huomaa, että `& "Z"` on käytettävä muotoilumerkkijono oikein **DateTime** arvo.
      1. **AvailableRooms** luodaan kokoelma. Tämä on yksinkertaisesti **RoomTimeSuggestions** osallistujien saatavuuden kaksi muita saraketta, se lisätään sisältävä kokoelma: ”Address” ja ”Name”. ”Address” on huoneen sähköpostiosoite ja ”Name” on ryhmän nimen.
      1. Sitten, **AvailableRoomsOptimal** luodaan kokoelma. Tämä on vain **AvailableRooms** kokoelma, jossa on sarakkeet ”Käytettävyysryhmän” ja ”osallistuja” on poistettu. Tämä vastaa rakenteet **AvailableRoomsOptimal** ja **AllRooms**. Näin voit käyttää molemmat kokoelmat- **kohteet** ominaisuuden **RoomBrowseGallery**.
      1. **_roomListSelected** asetetaan **false**.
  1. Ladataan-tilassa, **_loadingRooms**, on määritetty **false** kun kaikki muut suorittaminen on päättynyt.

## <a name="back-chevron"></a>Takaisin kaksoisnuolikuvake

   ![RoomsBackNav ohjausobjekti](media/meeting-screen/meeting-back.png)

* Ominaisuus: **Näkyvissä**<br>
    Arvo: `_roomListSelected && _showDetails`

    Tämä ohjausobjekti on näkyvissä vain, jos molemmat huoneluettelo on valittu ja **aikataulun** välilehti on valittuna.

* Ominaisuus: **OnSelect**<br>
    Arvo: `Set( _roomListSelected, false )`

    Kun **_roomListSelected** asetetaan **false**, se muuttuu **RoomBrowseGallery** ohjausobjekti, joka näyttää kohteita **RoomsLists** kokoelma.

## <a name="send-icon"></a>Lähetä-kuvake

   ![IconSendItem ohjausobjekti](media/meeting-screen/meeting-send-icon.png)

* Ominaisuus: **DisplayMode**<br>
    Arvo: Pakota käyttäjä antamaan kokouksen tietyt tiedot, ennen kuin tulee muokattavissa logiikan.
    
    ```powerapps-dot
    If( Len( Trim( TextMeetingSubject1.Text ) ) > 0
        && !IsEmpty( MyPeople ) && !IsBlank( _selectedMeetingTime ),
        DisplayMode.Edit, DisplayMode.Disabled
    )
    ```
  Kuvake on valittavissa vain, jos kokouksen aihe on arvo, on vähintään yksi osallistujien kokouksen ja kokouksen ajan on valittu. Muussa tapauksessa se on poistettu käytöstä.

* Ominaisuus: **OnSelect**<br>

    Arvo: Lähetä kokouksen kutsu valitun osallistujille ja poista kaikki syöttökenttiä koodi:

    ```powerapps-dot
    Set( _myCalendarName, LookUp( 'Office365'.CalendarGetTables().value, DisplayName = "Calendar" ).Name );
    Set( _myScheduledMeeting, 
        'Office365'.V2CalendarPostItem( _myCalendarName,
            TextMeetingSubject1.Text, 
            Text(DateAdd(DateTimeValue( _selectedMeetingTime.StartTime), -TimeZoneOffset(), Minutes) ),
            Text(DateAdd(DateTimeValue( _selectedMeetingTime.EndTime), -TimeZoneOffset(), Minutes) ),
            {
                RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ) & _selectedRoom.Address, 
                Body: TextMeetingMessage1.Text, 
                Location: _selectedRoom.Name, 
                Importance: "Normal", 
                ShowAs: "Busy", 
                ResponseRequested: true
            }
        )
    );
    Concurrent(
        Reset( TextMeetingLocation1 ),
        Reset( TextMeetingSubject1 ),
        Reset( TextMeetingMessage1 ),
        Clear( MyPeople ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoomList, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false )
    )
    ```
  
  Alhaisen tason, tämä koodilohko:
  1. Määrittää **_myCalendarName** kalenteriin [Office365.CalendarGetTables()](https://docs.microsoft.com/connectors/office365/#get-calendars) toiminto, jolla **DisplayName** ”kalenterin”.
  1. Ajoitukset kokouksen kaikille syötteen arvot eri valinnat käyttäjän tekemät koko näytön avulla [Office365.V2CalendarPostItem](https://docs.microsoft.com/connectors/office365/#create-event--v2-) toiminto.
  1. Palauttaa kaikki kenttää ja kokouksen luonnissa käytettyä muuttujia.

> [!NOTE]
> -Alueen mukaan kalenteri, haluat ehkä ole näyttönimi ”kalenterin”. Siirry Outlook-kalenterin otsikko on ja tee tarvittavat muutos sovelluksessa.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Lue lisätietoja tässä näytössä](./meeting-screen-overview.md)
* [Lue lisätietoja Office 365 Outlook-liittimellä powerappsissa](../connections/connection-office365-outlook.md)
* [Lue lisätietoja Office 365-käyttäjät-liittimellä powerappsissa](../connections/connection-office365-users.md)

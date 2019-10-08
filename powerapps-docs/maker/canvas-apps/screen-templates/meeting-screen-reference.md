---
title: Kangas sovellusten koko uksen näytön mallin viite tiedot | Microsoft Docs
description: Lue lisä tietoja siitä, miten koko näytön malli pohja sovelluksille toimii Powerappsissa
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/03/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c62c3de56534201a81e9f4d453796ebd9b3a0366
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71989561"
ms.PowerAppsDecimalTransform: true
---
# <a name="reference-information-about-the-meeting-screen-template-for-canvas-apps"></a>Viite tietoja kangas sovellusten koko uksen näyttö mallista

Powerappsin Canvas-sovelluksissa opit ymmärtämään, miten jokainen merkittävä koko uksen näytön malli vaikuttaa näytön yleiseen oletus toimintoon. Tämä Deep Dive esittelee toiminta kaavat ja muiden ominaisuuksien arvot, jotka määrittävät, miten ohjaus objekti reagoi käyttäjän syöttämiseen. Jos kyseessä on tämän näytön oletus toiminnon korkean tason keskustelu, tutustu [koko uksen näytön yleiskatsaukseen](meeting-screen-overview.md).

Tässä ohje aiheessa esitellään joitakin merkittäviä ohjaus objekteja ja selitetään lausekkeet tai kaavat, joille on määritetty eri ominaisuudet (kuten **kohteet** ja **onselect**):

* [Kutsu-väli lehti (Liblocittetab)](#invite-tab)
* [Ajoitus-väli lehti (LblScheduleTab)](#schedule-tab)
* [Teksti haku ruutu](#text-search-box)
* [Lisää kuvake (addiktoiva)](#add-icon)
* [Henkilöiden selaus valikoima](#people-browse-gallery) (+ aliohjausobjektit)
* [Kokous henkilöiden valikoima](#meeting-people-gallery) (+ aliohjausobjektit)
* [Koko uksen päivämäärä valitsin (Meetingsdateselect)](#meeting-date-picker)
* [Koko uksen keston avattava luettelo (Meetingsdurationselect)](#meeting-duration-drop-down)
* [Etsi koko uksen ajan valikoima](#find-meeting-times-gallery) (+ aliohjausobjektit)
* [Huoneen selaus valikoima](#room-browse-gallery) (+ aliohjausobjektit)
* [Back Chevron (RoomsBackNav)](#back-chevron) (ei välttämättä näy, jos Vuokraajalla ei ole huone luetteloita)
* [Lähetä-kuvake](#send-icon)

## <a name="prerequisite"></a>Edellytys

Perehtyneisyys näyttöjen ja muiden ohjaus objektien lisäämiseen ja määrittämiseen [, kun luot sovelluksen Powerappsissa](../data-platform-create-app-scratch.md).

## <a name="invite-tab"></a>Kutsu-väli lehti

   ![Ylivintetab-ohjaus objekti](media/meeting-screen/meeting-invite-text.png)

* Ominaisuuden **Väri**<br>
    Arvo: `If( _showDetails; LblRecipientCount.Color; RectQuickActionBar.Fill )`

    **_Showdetails** on muuttuja, jota käytetään määrittämään, onko **Lblinvitetab** -ohjaus objekti tai **lblscheduletab-** ohjaus objekti valittuna. Jos **_Showdetails** -arvo on **True**, **lblscheduletab** on valittuna; Jos arvo on **false**, on valittuna **liblinvitetab** . Tämä tarkoittaa sitä, että jos **_Showdetails** -arvo on **True** (tätä väli lehteä *ei ole* valittu), väli lehden väri vastaa **LblRecipientCount**-arvoa. Muussa tapa uksessa se vastaa **Rectquictionbar**-kohteen täyttö arvoa.

* Ominaisuuden **OnSelect**<br> 
    Arvo: `Set( _showDetails; false )`

    Määrittää **_Showdetails** -muuttujan arvoksi **false**, mikä tarkoittaa, että kutsu-väli lehden sisältö on näkyvissä, ja **ajoitus** -väli lehden sisältö on piilotettu.

## <a name="schedule-tab"></a>Ajoitus-väli lehti

   ![Ylivintetab-ohjaus objekti](media/meeting-screen/meeting-schedule-text.png)

* Ominaisuuden **Väri**<br>
    Arvo: `If( !_showDetails; LblRecipientCount.Color; RectQuickActionBar.Fill )`

    **_Showdetails** on muuttuja, jota käytetään määrittämään, onko **Lblinvitetab** -ohjaus objekti tai **lblscheduletab-** ohjaus objekti valittuna. Jos se on tosi, **Lblscheduletab** on valittuna; Jos arvo on FALSE, **Blinvitetab** on. Tämä tarkoittaa sitä, että jos **_Showdetails** -arvo on TRUE (Tämä väli lehti *on* valittuna), väli lehden väri vastaa **rectquictionbar**-kohteen täyttö arvoa. Muussa tapa uksessa se vastaa väri arvoa **LblRecipientCount**.

* Ominaisuuden **OnSelect**<br>
    Arvo: `Set( _showDetails; true )`

    Määrittää **_Showdetails** -muuttujan arvoksi **True**, mikä tarkoittaa, että ajoitus-väli lehden sisältö on näkyvissä, ja kutsu-väli lehden sisältö on piilotettu.

## <a name="text-search-box"></a>Tekstihakukenttä

   ![TextSearchBox-ohjaus objekti](media/meeting-screen/meeting-search-box.png)

<!--Include description of text search box control?-->

Useilla muilla näytön ohjaus objekteilla on riippuvuussuhde tähän:

* Jos käyttäjä alkaa kirjoittaa tekstiä, **Peoplebrowsegallery** tulee näkyviin.
* Jos käyttäjä käyttää kelvollista Sähkö posti osoitetta, **riippuvuuden vaikutus** tulee näkyviin.
* Kun käyttäjä valitsee henkilön, joka sijaitsee **Peoplebrowsegallery** -kohteessa, haku sisältö nollataan.

## <a name="add-icon"></a>Lisäämiskuvake

   ![Addiktoiva ohjaus objekti](media/email-screen/email-add-icon.png)

Tämän ohjaus objektin avulla käyttäjät voivat lisätä henkilöitä, jotka eivät ole organisaatiossaan, osanottajaluetteloon, joka muodostetaan.

* Ominaisuuden **Näkyvissä**<br>
    Arvo Kolme loogista tarkistusta, joiden kaikkien on arvioitava **todeksi** , että ohjaus objekti on näkyvä:

    ```powerapps-comma
    !IsBlank( TextSearchBox.Text ) &&
        IsMatch( TextSearchBox.Text; Match.Email ) &&
        Not( Trim( TextSearchBox.Text ) in MyPeople.UserPrincipalName )
    ```

  Linja riviltä, tämä koodi lohko kertoo, että **addon-** ohjaus objekti on näkyvissä vain, jos:

  * **Textsearchbox** sisältää tekstiä.
  * **Textsearchbox** -teksti on kelvollinen Sähkö posti osoite.
  * **Textsearchbox** -teksti ei ole jo olemassa **mypeople** -kokoelmassa.

* Ominaisuuden **OnSelect**<br> 
    Arvo **Collect** -lauseke, joka lisää käyttäjän osallistujaluetteloon, toinen päivittää käytettävissä olevat Kokous ajat ja useita muuttuja vaihtaa:

    ```powerapps-comma
    Collect( MyPeople;
        { 
            DisplayName: TextSearchBox.Text; 
            UserPrincipalName: TextSearchBox.Text; 
            Mail: TextSearchBox.Text
        }
    );;
    Concurrent(
        Reset( TextSearchBox );
        Set( _showMeetingTimes; false );
        UpdateContext( { _loadMeetingTimes: true } );
        Set( _selectedMeetingTime; Blank() );
        Set( _selectedRoom; Blank() );
        Set( _roomListSelected; false );
        ClearCollect( MeetingTimes; 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    { 
                        RequiredAttendees: Concat(MyPeople; UserPrincipalName & ";")
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate; 8; Hours ); UTC );
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate; 17; Hours ); UTC );
                        MaxCandidates: 15; 
                        MinimumAttendeePercentage:1; 
                        IsOrganizerOptional: false; 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions;
                "StartTime"; MeetingTimeSlot.Start.DateTime; 
                "EndTime"; MeetingTimeSlot.End.DateTime
            )
        )
    );;
    UpdateContext( { _loadingMeetingTimes: false } );;
    Set( _showMeetingTimes; true )
    ```

  Tämän ohjaus objektin valitseminen lisää kelvollisen Sähkö posti osoitteen (näkyvissä vain, jos kelvollinen Sähkö posti osoite kirjoitetaan **Textsearchboxiin**) **mypeople** -kokoelmaan (tämä kokoelma on osallistujaluettelo) ja päivittää sitten käytettävissä olevat Kokous ajat uudella käyttäjä merkintä.

  Tällä koodi lohkolla on alhainen taso:
  1. Kerää Sähkö posti osoitteen **Mypeople** -kokoelmaan ja kerää Sähkö posti osoitteen **DisplayName**-, **userPrincipalName**-ja **Mail** -kenttiin.
  1. Nollaa **Textsearchbox** -ohjaus objektin sisällön.
  1. Määrittää **_Showmeetingtimes** -muuttujan arvoksi **false**. Tämä muuttuja määrittää **Findmeetingstimesgallery-valikoiman**näkyvyyden, jolloin valittujen osallistujien avoimet ajat näkyvät.
  1. Määrittää **_Loadmeetingtimes** -kontekstin muuttujan arvoksi **True**. Tämä muuttuja määrittää lataamis tilan, joka vaihtaa lataus tilan ohjaus objektien, kuten **_Llbltimesemptystate** , näkyvyyden, joka ilmaisee käyttäjälle, että heidän tietojaan ladataan.
  1. Määrittää **_Selectedmeetingtime** -kohteen **tyhjäksi ()** . **_Selectedmeetingtime** on valittu tietue **Findmeetingtimesgallery** -ohjaus objektista. Se on tyhjä tässä, koska toisen osallistujan lisääminen voi merkitä sitä, että aiempi **_Selectedmeetingtime** -määritys ei ole käytettävissä tälle osallistujalle.
  1. Määrittää **_Selectedroom** -kohteen **tyhjäksi ()** . **_Selectedroom** on valittu huone tietue **Roombrowsegallery-valikoimasta**. Huoneen käytettävyysarvot määritetään **_Selectedmeetingtime**-kohteen arvosta. Jos arvo on tyhjä, **_Selectedroom** -arvo ei ole enää kelvollinen, joten sen on oltava tyhjä.
  1. Määrittää **_Roollistselected** -arvoksi **false**. Tämä linja ei välttämättä sovellu kaikille. Officessa voit ryhmitellä huoneet eri huone luetteloiden mukaan. Jos sinulla on huone luetteloita, tämä näyttö näyttää sen, jolloin voit ensin valita huone luettelon ennen huoneen valitsemista kyseisestä luettelosta. **_Roollistselected** -arvo määrittää, onko käyttäjä (vain huone luetteloiden vuokraajassa) huone luettelossa tai huone luetteloiden joukossa. Sen asetus on **false** , jos käyttäjät pakotetaan valitsemaan uusi huone luettelo uudelleen.
  1. Määrittää ja kerää osallistujien käytettävissä olevat Kokous ajat käyttämällä [office365. Findmeettingtimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) -toimintoa. Tämä toiminto kulkee:
      * Kunkin valitun käyttäjän **userPrincipalName** -parametri *Requiredattendees* -parametriin.
      * **Meettingdurationselect**. Selected. minutes *Meettingduration* -parametriin.
      * Meetingsdateselect. SelectedDate + 8 tuntia *Start* -parametriin. Kahdeksan tuntia lisätään, koska Oletus arvon mukaan kalenteri-ohjaus objektin koko päivä määrä/aika on 12:00 AM valitusta päivä määrästä. Haluat luultavasti noutaa käytettävissä olevat käytettävyyskyvyt normaalin työajan aikana. Normaalin työajan alkamis aika olisi 8:00.
      * **Meetingsdateselect**. SelectedDate + 17 tuntia *End* -parametriin. Lisätään 17 tuntia, koska 12:00 AM + 17 = 5:00 PM. Normaalin työajan päättymis aika olisi 5:00 PM.
      * *15* *maxehdokkaat* -parametriin. Tämä tarkoittaa, että toiminto palauttaa vain 15 parasta käytettävissä olevaa kertaa valitulle päivä määräksi. Tämä on järkevää, koska 8 tunnin työpäivä on vain 16 30 minuuttia, ja tässä näytössä voidaan määrittää vähintään 30 minuutin kokous.
      * *1* *Minutamattendeepercentage* -parametriin. Ennen kuin osallistujia ei ole käytettävissä, koko uksen aika noudetaan.
      * **false** -arvo *Onorganizeroptional* -parametrille. Sovelluksen käyttäjä ei ole tämän koko uksen valinnainen osallistuja.
      * "Work" *Activitydomain* -parametriin. Tämä tarkoittaa, että noudetut ajat ovat vain normaalin työajan aikana.
  1. **Clearcollect** -funktiolla lisätään myös kaksi saraketta: "StartTime" ja "EndTime". Tämä yksinkertaistaa palautettuja tietoja. 
  Käytettävissä olevat alkamis-ja päättymis ajat sisältävä kenttä on **Meetingstimeslot** -kenttä. Tämä kenttä on tietue, joka sisältää alku-ja loppu tietueet, jotka sisältävät kunkin ehdotuksensa **DateTime** -ja **timezone** -arvot. Sen sijaan, että yrittäisit noutaa tämän tietueiden sisäkkäisyyden, "StartTime"-ja "EndTime"-sarakkeiden lisääminen **Meetingstimes** -kokoelmaan tuo ne **Start > DateTime** -ja **End > DateTime** -arvot kokoelman pinnalle.
  1. Kun nämä funktiot on suoritettu, **_Loadingmeetingtimes** -muuttujan arvo on **false**, lataus tilan poistaminen ja **_showmeetingtimes** -asetuksena on **True**, **findmeetingtimesgallery**näytetään.

## <a name="people-browse-gallery"></a>Henkilöiden selaus valikoima

   ![PeopleBrowseGallery-ohjaus objekti](media/meeting-screen/meeting-browse-gall.png)

* Ominaisuuden **Kohteet**<br>
    Arvo 
    ```powerapps-comma
    If( !IsBlank( Trim( TextSearchBox.Text ) ); 
        'Office365Users'.SearchUser( { searchTerm: Trim(TextSearchBox.Text); top: 15 } )
    )
    ```

Tämän valikoiman kohteet täytetään haku tuloksilla [office365. SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) -toiminnosta. Toiminto vie tekstin `Trim(**TextSearchBox**)` haku terminä ja palauttaa tämän haun perusteella 15 parasta tulosta.
  
**Textsearchbox** on pakattu **Trim** -toimintoon, koska käyttäjä haku väli lyönneillä ei ole kelvollinen. @No__t-0-toiminto rivitetään `If(!IsBlank(Trim(TextSearchBox.Text)) ... )`-funktiolla, koska haku tulosten noutaminen, ennen kuin käyttäjä on etsinyt, on suoritus kyky jätettä.

### <a name="people-browse-gallery-title"></a>Käyttäjät selaavat valikoiman otsikkoa

   ![PeopleBrowseGallery-otsikon ohjaus objekti](media/meeting-screen/meeting-browse-gall-title.png)

* Ominaisuuden **Teksti**<br>
    Arvo: `ThisItem.DisplayName`

    Näyttää henkilön näyttö nimen Office 365-profiilista.

* Ominaisuuden **OnSelect**<br>
    Arvo **Collect** -lauseke, joka lisää käyttäjän osallistujaluetteloon, toinen päivittää käytettävissä olevat Kokous ajat ja useita muuttuja vaihtaa:

    ```powerapps-comma
    Concurrent(
        Reset( TextSearchBox );
        Set( _selectedUser; ThisItem );
        If( Not( ThisItem.UserPrincipalName in MyPeople.UserPrincipalName ); 
            Collect( MyPeople; ThisItem );; 
            Concurrent(
                Set( _showMeetingTimes; false );
                UpdateContext( { _loadMeetingTimes: true } );
                Set( _selectedMeetingTime; Blank() );
                Set( _selectedRoom; Blank() );
                Set( _roomListSelected; false );
                ClearCollect( MeetingTimes; 
                    AddColumns(
                        'Office365'.FindMeetingTimes(
                            {
                                RequiredAttendees: Concat( MyPeople; UserPrincipalName & ";" );
                                MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                                Start: Text( DateAdd( MeetingDateSelect.SelectedDate; 8; Hours ); UTC );
                                End: Text( DateAdd( MeetingDateSelect.SelectedDate; 17; Hours ); UTC );
                                MaxCandidates: 15; 
                                MinimumAttendeePercentage: 1; 
                                IsOrganizerOptional: false; 
                                ActivityDomain: "Work"
                            }
                        ).MeetingTimeSuggestions;
                        "StartTime"; MeetingTimeSlot.Start.DateTime; 
                        "EndTime"; MeetingTimeSlot.End.DateTime
                    )
                )
            );;
            UpdateContext( { _loadingMeetingTimes: false } );;
            Set( _showMeetingTimes; true )
        )
    )
    ```

    Korkealla tasolla tämän ohjaus objektin valitseminen lisää henkilön **Mypeople** -kokoelmaan (sovelluksen osallistujan luettelon tallennus tilaan) ja päivittää käytettävissä olevat Kokous ajat uuden käyttäjän lisäyksen perusteella.

    Tämän ohjaus objektin valitseminen on hyvin samanlaista kuin **Adcon-** ohjaus objektin valitseminen; ainoa ero on se, että `Set(_selectedUser; ThisItem)`-lauseke ja toiminto järjestys. Näin ollen tämä keskustelu ei ole yhtä syvä. Tarkempi selitys on [Adcon-ohjaus objektin](#add-icon) osassa.

    Tämän ohjaus objektin valitseminen Nollaa **Textsearchbox**. Jos valinta ei ole **Mypeople** -kokoelmassa, ohjaus objekti:
    1. Määrittää **_Loadmeetingtimes** -tilan arvoksi **True** ja **_showmeetingtimes** -tilan arvoksi **false**, tyhjät **_Selectedmeetingtime** -ja **_selectedroom** -muuttujat ja päivittää **meetingtimes** -kohteen kokoelma, jossa on uusi lisäys **Mypeople** -kokoelmaan. 
    1. Määrittää **_Loadmeetingtimes** -tilan arvoksi **false**ja määrittää **_showmeetingtimes** -arvoksi **True**. Jos valinta on jo **Mypeople** -kokoelmassa, se palauttaa vain **Textsearchbox**-kohteen sisällön.

## <a name="meeting-people-gallery"></a>Kokous henkilöiden valikoima

   ![Meetingspeoplegallery-ohjaus objekti](media/meeting-screen/meeting-people-gall.png)

* Ominaisuuden **Kohteet**<br>
    Arvo: `MyPeople`

    **Mypeople** -kokoelma on kokoelma henkilöitä, jotka on alustettu tai lisätty, valitsemalla **Peoplebrowsegallery-otsikko** -ohjaus objekti.

* Ominaisuuden **Korkeus**<br>
    Arvo Logiikka, joka sallii valikoiman kasvavan 350-enimmäiskorkeuteen:

    ```powerapps-comma
    Min( 
        76 * RoundUp( CountRows( MeetingPeopleGallery.AllItems ) / 2; 0 );
        350
    )
    ```

  
   Tämän valikoiman korkeus mukautuu valikoiman kohteiden määrään, jonka enimmäiskorkeus on 350. Kaava ottaa 76-kohteen, jonka korkeus on **Meetingpeoplegallery**-rivi, ja kertoo sen rivien määrän mukaan. **Wrapcount** -ominaisuudeksi on määritetty 2, joten todellisten rivien määrä on `RoundUp(CountRows(MeetingPeopleGallery.AllItems) / 2; 0)`.

* Ominaisuuden **ShowScrollbar**<br>
    Arvo: `MeetingPeopleGallery.Height >= 350`

    Kun valikoiman enimmäiskorkeus saavutetaan (350), vieritys palkki on näkyvissä.

### <a name="meeting-people-gallery-title"></a>Kokous henkilöiden valikoiman otsikko

   ![Meetingspeoplegallery-otsikko ohjaus objekti](media/meeting-screen/meeting-people-gall-title.png)

* Ominaisuuden **OnSelect**<br>
    
    Arvo: `Set(_selectedUser; ThisItem)`
    
    Määrittää **_Selecteduser** -muuttujan kohteelle **Selectedpeoplegallery**.

### <a name="meeting-people-gallery-iconremove"></a>Kokous henkilöiden valikoima iconRemove

   ![Meetingspeoplegallery iconRemove-ohjaus objekti](media/meeting-screen/meeting-people-gall-delete.png)

* Ominaisuuden **OnSelect**<br>
    Arvo **Remove** -lauseke, joka poistaa käyttäjän osallistuja-listasta, joka on **Collect** -lauseke, joka päivittää käytettävissä olevat Kokous ajat ja useita muuttuja-vaihtaa:

    ```powerapps-comma
    Remove( MyPeople; LookUp( MyPeople; UserPrincipalName = ThisItem.UserPrincipalName ) );;
    Concurrent(
        Reset( TextSearchBox );
        Set( _showMeetingTimes; false );
        UpdateContext( { _loadMeetingTimes: true } );
        Set( _selectedMeetingTime; Blank() );
        Set( _selectedRoom; Blank() );
        Set( _roomListSelected; false );
        ClearCollect( MeetingTimes; 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    {
                        RequiredAttendees: Concat( MyPeople; UserPrincipalName & ";" ); 
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate; 8; Hours ); UTC ); 
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate; 17; Hours ); UTC );
                        MaxCandidates: 15; 
                        MinimumAttendeePercentage: 1; 
                        IsOrganizerOptional: false; 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions;
                "StartTime"; MeetingTimeSlot.Start.DateTime; 
                "EndTime"; MeetingTimeSlot.End.DateTime
            )
        )
    );;
    UpdateContext( { _loadingMeetingTimes: false } );;
    Set( _showMeetingTimes; true )
    ```

  Korkealla tasolla tämän ohjaus objektin valitseminen poistaa henkilön osallistujaluettelosta ja päivittää käytettävissä olevat Kokous ajat tämän henkilön poistamisen perusteella.

  Edellisen koodin ensimmäisen rivin jälkeen tämän ohjaus objektin valitseminen on lähes identtinen **Addison** -ohjaus objektin valitsemisen kanssa. Tämä keskustelu ei sinänsä ole yhtä syvä. Tarkempi selitys on [Adcon-ohjaus objektin osassa](#add-icon).

  Valitun kohteen ensimmäinen koodi rivillä on poistettu **Mypeople** -kokoelmasta. Koodi:
  1. Nollaa **Textsearchbox**-kohteen ja poistaa sitten valinnan **mypeople** -kokoelmasta. 
  1. Määrittää **_Loadmeetingtimes** -tilan arvoksi **True** ja **_showmeetingtimes** -tilan arvoksi **false**, tyhjät **_Selectedmeetingtime** -ja **_selectedroom** -muuttujat ja päivittää **meetingtimes** -kohteen kokoelma, jossa on uusi lisäys **Mypeople** -kokoelmaan. 
  1. Määrittää **_Loadmeetingtimes** -tilan arvoksi **false**ja määrittää **_showmeetingtimes** -arvoksi **True**.

## <a name="meeting-date-picker"></a>Koko uksen päivämäärä valitsin

   ![Meetingsdateselect-ohjaus objekti](media/meeting-screen/meeting-datepicker.png)

* Ominaisuuden **Haluat viitata DisplayMode**<br>
    Arvo: `If( IsEmpty(MyPeople); DisplayMode.Disabled; DisplayMode.Edit )`

    Koko uksen päivä määrää ei voi valita, ennen kuin vähintään yksi osallistuja on lisätty **Mypeople** -kokoelmaan.

* Ominaisuuden **OnChange**<br>
    Arvo: `Select( MeetingDateSelect )`

    Valitun päivä määrän muuttaminen käynnistää tämän ohjaus objektin **onselect** -ominaisuudessa olevan koodin suoritettavaksi.

* Ominaisuuden **OnSelect**<br>
    Arvo **Collect** -lauseke, joka päivittää käytettävissä olevat Kokous ajat ja useita muuttuja-vaihtaa:
  
    ```powerapps-comma
    Concurrent(
        Reset( TextSearchBox );
        Set( _showMeetingTimes; false );
        UpdateContext( { _loadingMeetingTimes: true } );
        Set( _selectedMeetingTime; Blank() );
        Set( _selectedRoom; Blank() );
        Set( _roomListSelected; false );
        ClearCollect( MeetingTimes; 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    {
                        RequiredAttendees: Concat( MyPeople; UserPrincipalName & ";" ); 
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate; 8; Hours ); UTC ); 
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate; 17; Hours ); UTC );
                        MaxCandidates: 15; 
                        MinimumAttendeePercentage: 1; 
                        IsOrganizerOptional: false; 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions;
                "StartTime"; MeetingTimeSlot.Start.DateTime; 
                "EndTime"; MeetingTimeSlot.End.DateTime
            )
        )
    );;
    UpdateContext( { _loadingMeetingTimes: false } );;
    Set( _showMeetingTimes; true )
    ```

  Korkealla tasolla tämän ohjaus objektin valitseminen päivittää käytettävissä olevat Kokous ajat. Se on arvokas, koska jos käyttäjä muuttaa päivä määrää, käytettävissä olevat Kokous ajat on päivitettävä vastaamaan kyseisen päivän osallistujien saatavuutta.

  Ensimmäistä **Collect** -lauseketta lukuun ottamatta tämä on identtinen **adadon** -ohjaus objektin **onselect** -toiminnon kanssa. Tämä keskustelu ei sinänsä ole yhtä syvä. Tarkempi selitys on [Adcon-ohjaus objektin](#add-icon) osassa.

  Tämän ohjaus objektin valitseminen Nollaa **Textsearchbox**. Sen jälkeen: 
  1. Määrittää **_Loadmeetingtimes** -tilan arvoksi **True** ja **_showmeetingtimes** -tilan arvoksi **false**, tyhjät **_Selectedmeetingtime** -ja **_selectedroom** -muuttujat ja päivittää **meetingtimes** -kohteen kokoelma, jossa on uusi päivämäärä valinta. 
  1. Määrittää **_Loadmeetingtimes** -tilan arvoksi **false**ja määrittää **_showmeetingtimes** -arvoksi **True**.

## <a name="meeting-duration-drop-down"></a>Avattavan koko uksen kesto

   ![Meetingsdateselect-ohjaus objekti](media/meeting-screen/meeting-timepicker.png)

* Ominaisuuden **Haluat viitata DisplayMode**<br>
    Arvo: `If( IsEmpty(MyPeople); DisplayMode.Disabled; DisplayMode.Edit )`

    Koko uksen kestoa ei voi valita, ennen kuin vähintään yksi osallistuja on lisätty **Mypeople** -kokoelmaan.

* Ominaisuuden **OnChange**<br>
    Arvo: `Select(MeetingDateSelect1)`

    Valitun keston muuttaminen käynnistää koodin **Meetingsdateselect** -ohjaus objektin **onselect** -ominaisuudessa suoritettavaksi.

## <a name="find-meeting-times-gallery"></a>Etsi koko uksen ajan valikoima

   ![Findmeetingstimesgallery-ohjaus objekti](media/meeting-screen/meeting-time-gall.png)

* Ominaisuuden **Kohteet**<br>
    Arvo: `MeetingTimes`

    [Office365. Findmeettingtimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) -toiminnosta noudettavien mahdollisten Kokous aikojen kokoelma.

* Ominaisuuden **Näkyvissä**<br>
    Arvo: `_showMeetingTimes && _showDetails && !IsEmpty( MyPeople )`

    Valikoima on näkyvissä vain, jos **_Showmeetingtimes** -arvo on **tosi (True**), käyttäjä on valinnut **lblscheduletab** -ohjaus objektin, ja koko ukseen on lisätty vähintään yksi osallistuja.

### <a name="find-meeting-times-gallery-title"></a>Etsi koko uksen ajan valikoiman otsikko

   ![Findmeetingstimesgallery-otsikon ohjaus objekti](media/meeting-screen/meeting-time-gall-title.png)

* Ominaisuuden **Teksti**<br>
    Arvo Käyttäjän paikallisessa ajassa näytettävän aloitus ajan muunto:

    ```powerapps-comma
    Text(
        DateAdd(
            DateTimeValue( ThisItem.StartTime );
            - TimeZoneOffset(); 
            Minutes
        );
        DateTimeFormat.ShortTime
    )
    ```

  **StartTime** -kohteen Noudettu arvo on UTC-muotoinen. **DateAdd** -FUNKTIOLLA [muunnetaan UTC-ajasta paikalliseksi ajaksi](../functions/function-dateadd-datediff.md#converting-from-utc).
  [Text-funktiolla](../functions/function-text.md#datetime) on päivä määrä/aika ensimmäisenä argumenttina, ja se muotoilee sen toisen argumentin perusteella. Ohitat sen **thisitem. Startttime**-kohteen paikallisen ajan muunnoksen ja voit näyttää sen **Datetimeformat. shorttime-muodossa**.

* Ominaisuuden **OnSelect**<br>
    Arvo Useita **Collect** -lauseita keräämään Kokous huoneita ja niiden ehdottamia käytettävyyskykyjä sekä useita muuttuja vaihtaa:

    ```powerapps-comma
    Set( _selectedMeetingTime; ThisItem );;
    UpdateContext( { _loadingRooms: true } );;
    If( IsEmpty( RoomsLists );
        ClearCollect( RoomsLists; 'Office365'.GetRoomLists().value) );;
    If( CountRows( RoomsLists ) <= 1;
        Set( _noRoomLists; true );;
        ClearCollect( AllRooms; 'Office365'.GetRooms().value );;
        Set( _allRoomsConcat; Concat( FirstN( AllRooms; 20 ); Address & ";" ) );;
        ClearCollect( RoomTimeSuggestions; 
            'Office365'.FindMeetingTimes(
                {
                    RequiredAttendees: _allRoomsConcat; 
                    MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                    Start: _selectedMeetingTime.StartTime & "Z"; 
                    End: _selectedMeetingTime.EndTime & "Z"; 
                    MinimumAttendeePercentage: "1";
                    IsOrganizerOptional: "false"; 
                    ActivityDomain: "Unrestricted"
                }
            ).MeetingTimeSuggestions
        );;
        ClearCollect( AvailableRooms; 
            AddColumns(
                AddColumns(
                    Filter( 
                        First( RoomTimeSuggestions ).AttendeeAvailability;
                        Availability="Free"
                    ); 
                    "Address"; Attendee.EmailAddress.Address
                ); 
                "Name"; LookUp( AllRooms; Address = Attendee.EmailAddress.Address ).Name 
            )
        );;
        ClearCollect( AvailableRoomsOptimal; 
            DropColumns(
                DropColumns( AvailableRooms; "Availability" ); 
                "Attendee" 
            )
        );
        Set( _roomListSelected; false) 
    );;
    UpdateContext( {_loadingRooms: false} )
    ```

  Korkealla tasolla tämä koodi lohko kerää käytettävissä olevia huoneita käyttäjille, joilla ei ole huone luetteloita, valitun koko uksen päivä määrän ja ajan perusteella. Muussa tapa uksessa se vain noutaa huone luettelot.

  Tällä koodi lohkolla on alhainen taso:
  1. Määrittää valitulle kohteelle **_Selectedmeetingtime** . Tämän avulla etsitään, mitä huoneita on käytettävissä tuona aikana.
  1. Määrittää Loading State-muuttujan **_Loadingrooms** arvoksi **True**, jolloin lataus tila on.
  1. Jos **Roomslists** -kokoelma on tyhjä, se noutaa käyttäjän tenant's Rooms-luettelot ja tallentaa ne **roomslists** -kokoelmaan.
  1. Jos käyttäjällä ei ole huone listaa tai yhden huoneen listaa:
      1. **Norooollists** -muuttujan arvo on **True**, ja tätä muuttujaa käytetään **roombbrowsegallery** -ohjaus objektissa näkyvien kohteiden määrittämiseen.
      1. @No__t-0-toimintoa käytetään hake maan vuokraajansa ensimmäiset 100 huonetta. Nämä on tallennettu **Allrooms** -kokoelmaan.
      1. **_Allroomsconat** -muuttuja on määritetty puoli pistein eroteltuna merkki jonoksi **allrooms** -kokoelman huoneiden 20 ensimmäisestä Sähkö posti osoitteesta. Tämä johtuu siitä, että [office365. Findmeettingtimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) on rajoitettu etsimään käytettävissä olevia 20 henkilön objektin aikoja yksittäisessä toiminnossa.
      1. **Roomestimesuggestions** -kokoelma käyttää **allrooms** -kokoelman ensimmäisten 20 huoneen saatavuutta [office365. findmeetingtimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) -kohteen avulla **_selectedmeetingtime** -muuttujan aika arvojen perusteella. Huomioi, että `& "Z"`: n avulla muotoillaan **DateTime** -arvo oikein.
      1. **Avatablerooms** -kokoelma luodaan. Tämä on yksinkertaisesti osallistujien **käytettävissä olevien osallistujien käytettävyyskokoelma,** johon on lisätty kaksi lisä saraketta: "Address" ja "name". Address on huoneen Sähkö posti osoite, ja nimi on huoneen nimi.
      1. Sen jälkeen **Avaitableroomsoptimal** -kokoelma luodaan. Tämä on vain **Availablerooms** -kokoelma, jossa on poistettu käytettävyys-ja osallistuja-sarakkeet. Tämä vastaa **Availlableroomsoptimal** -ja **allrooms**-rakenteiden rakenteita. Tämän avulla voit käyttää molempia kokoelmia **Roomsbrowsegallery**- **kohteen Items** -ominaisuudessa.
      1. **_Roolistselected** -arvo on **false**.
  1. Lataus tilan **_Loadingrooms**-asetus on **false** , kun kaikki muu on lopettanut suorittamisen.

## <a name="room-browse-gallery"></a>Huoneen selaus valikoima

   ![RoomBrowseGallery-ohjaus objekti](media/meeting-screen/meeting-rooms-gall.png)

* Ominaisuuden **Kohteet**<br>
    Arvo Loogisesti on määritetty kaksi sisäistä identtistä rakennetta, riippuen siitä, onko käyttäjä valinnut huone luettelon vai onko vuokraajassa huoneita luetteloita:

    ```powerapps-comma
    Search(
        If( _roomListSelected || _noRoomLists; AvailableRoomsOptimal; RoomsLists );
        Trim(TextMeetingLocation1.Text); 
        "Name"; 
        "Address"
    )
    ```

  Tämä valikoima näyttää **Avaitableroomsoptimal** -kokoelman, jos **_Roomlistselected** tai **_noromlists** on **True**. Muussa tapa uksessa se näyttää **Roomslists** -kokoelman. Tämä voidaan tehdä, koska näiden kokoelmien rakenne on sama.

* Ominaisuuden **Näkyvissä**<br>
    Arvo: ```_showDetails && !IsBlank( _selectedMeetingTime ) && !_loadingRooms```

    Valikoima näkyy vain, jos kolme edeltävää lauseketta on **tosi**.

### <a name="roombrowsegallery-title"></a>Roombbrowsegallery-otsikko

   ![RoomBrowseGallery-otsikon ohjaus objekti](media/meeting-screen/meeting-rooms-gall-title.png)

* Ominaisuuden **OnSelect**<br>
    Arvo Loogisesti sidottujen **Collect** -ja **joukko** -lausekkeiden joukko, jota saatetaan tai ei ehkä käynnistetä sen mukaan, onko käyttäjä tarkastelet huone luetteloita vai huoneita:

    ```powerapps-comma
    UpdateContext( { _loadingRooms: true } );;
    If( !_roomListSelected && !noRoomLists;
        Set( _roomListSelected; true );;
        Set( _selectedRoomList; ThisItem.Name );;
        ClearCollect( AllRooms; 'Office365'.GetRoomsInRoomList( ThisItem.Address ).value );;
        Set( _allRoomsConcat; Concat( FirstN( AllRooms; 20 ); Address & ";" ) );;
        ClearCollect( RoomTimeSuggestions; 
            'Office365'.FindMeetingTimes(
                {
                    RequiredAttendees: _allRoomsConcat; 
                    MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                        Start: _selectedMeetingTime.StartTime & "Z"; 
                    End: _selectedMeetingTime.EndTime & "Z"; 
                    MinimumAttendeePercentage: "1";
                    IsOrganizerOptional: "false"; 
                    ActivityDomain: "Unrestricted"
                }
            ).MeetingTimeSuggestions
        );;
        ClearCollect( AvailableRooms; 
            AddColumns(
                AddColumns(
                    Filter(
                        First( RoomTimeSuggestions ).AttendeeAvailability; 
                        Availability = "Free"
                    );
                    "Address"; Attendee.EmailAddress.Address 
                ); 
                "Name"; LookUp( AllRooms; Address = Attendee.EmailAddress.Address ).Name
            )
        );;
        ClearCollect( AvailableRoomsOptimal; 
            DropColumns(
                DropColumns( AvailableRooms; "Availability" )
            ); 
            "Attendee" )
        );
        Set( _selectedRoom; ThisItem )
    );;
    UpdateContext( {_loadingRooms: false} )
    ```

  Toiminnot, jotka suoritetaan, kun tämä ohjaus objekti valitaan, määräytyvät sen mukaan, tarkasteleeko käyttäjä parhaillaan joukko huone luetteloita vai huone joukkoa. Jos se on aiempi, tämän ohjaus objektin valitseminen noutaa valitun ajan valitsemat huoneet valitusta huone listasta. Jos se on jälkimmäinen, tämän ohjaus objektin valitseminen määrittää **_Selectedroom** -muuttujan valittuun kohteeseen. Edeltävä lauseke on hyvin samankaltainen kuin [**Findmeetingstimesgallery-otsikon**](#find-meeting-times-gallery) **Select** -lauseke.

  Alhaisella tasolla edeltävä koodi lohko:
  1. Ottaa käyttöön huoneiden lataamis tilan asettamalla **_Loadingrooms** -arvoksi **True**.
  1. Tarkistaa, onko huone luettelo valittuna, ja onko vuokra ajalla huone luetteloita. Jos näin on:
      1. Määrittää **_Roollistselected** -arvoksi **True** ja määrittää **_selectedroollistlist** -kohteen valitulle kohteelle.
      1. **_Allroomsconat** -muuttuja on määritetty puoli pistein eroteltuna merkki jonoksi **allrooms** -kokoelman huoneiden 20 ensimmäisestä Sähkö posti osoitteesta. Tämä johtuu siitä, että [office365. Findmeetingstimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) -toiminto on rajoitettu etsimään käytettävissä olevia 20 henkilön objektin aikoja yksittäisessä toiminnossa.
      1. **Roomestimesuggestions** -kokoelma käyttää **allrooms** -kokoelman ensimmäisten 20 huoneen saatavuutta [office365. findmeetingtimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) -toiminnolla **_selectedmeetingtime** -kohteen aika arvojen perusteella muuttuja. Huomioi, että `& "Z"` käytetään **DateTime** -arvon muotoiluun oikein.
      1. **Avatablerooms** -kokoelma luodaan. Tämä on yksinkertaisesti osallistujien **käytettävissä olevien osallistujien käytettävyyskokoelma,** johon on lisätty kaksi lisä saraketta: "Address" ja "name". Address on huoneen Sähkö posti osoite, ja nimi on huoneen nimi.
      1. Sen jälkeen **Avaitableroomsoptimal** -kokoelma luodaan. Tämä on vain **Availablerooms** -kokoelma, jossa on poistettu käytettävyys-ja osallistuja-sarakkeet. Tämä vastaa **Availlableroomsoptimal** -ja **allrooms**-rakenteiden rakenteita. Tämän avulla voit käyttää molempia kokoelmia **Roomsbrowsegallery**- **kohteen Items** -ominaisuudessa.
      1. **_Roolistselected** -arvo on **false**.
  1. Lataus tilan **_Loadingrooms**-asetus on **false** , kun kaikki muu on lopettanut suorittamisen.

## <a name="back-chevron"></a>Takaisin nuolen kärki

   ![RoomsBackNav-ohjaus objekti](media/meeting-screen/meeting-back.png)

* Ominaisuuden **Näkyvissä**<br>
    Arvo: `_roomListSelected && _showDetails`

    Tämä ohjaus objekti on näkyvissä vain, jos sekä huone luettelo on valittuna että **ajoitus** -väli lehti on valittuna.

* Ominaisuuden **OnSelect**<br>
    Arvo: `Set( _roomListSelected; false )`

    Kun **_Roomslistselected** -arvo on **false**, se muuttaa **roomsbrowsegallery** -ohjaus objektin näyttämään kohteet **roomslist** -kokoelmasta.

## <a name="send-icon"></a>Lähetä-kuvake

   ![IconSendItem-ohjaus objekti](media/meeting-screen/meeting-send-icon.png)

* Ominaisuuden **Haluat viitata DisplayMode**<br>
    Arvo Logiikka, jonka avulla käyttäjä voi syöttää tietyn koko uksen tiedot, ennen kuin kuvake muuttuu muokattavaksi.
    
    ```powerapps-comma
    If( Len( Trim( TextMeetingSubject1.Text ) ) > 0
        && !IsEmpty( MyPeople ) && !IsBlank( _selectedMeetingTime );
        DisplayMode.Edit; DisplayMode.Disabled
    )
    ```
  Kuvake on valittavissa vain, jos koko uksen aihe on täytetty, koko uksessa on vähintään yksi osallistuja ja koko uksen aika on valittu. Muussa tapa uksessa se on poistettu käytöstä.

* Ominaisuuden **OnSelect**<br>

    Arvo Koodi, joka lähettää Kokous kutsun valituille osanottajille ja tyhjentää kaikki syöte kentät:

    ```powerapps-comma
    Set( _myCalendarName; LookUp( 'Office365'.CalendarGetTables().value; DisplayName = "Calendar" ).Name );;
    Set( _myScheduledMeeting; 
        'Office365'.V2CalendarPostItem( _myCalendarName;
            TextMeetingSubject1.Text; 
            Text(DateAdd(DateTimeValue( _selectedMeetingTime.StartTime); -TimeZoneOffset(); Minutes) );
            Text(DateAdd(DateTimeValue( _selectedMeetingTime.EndTime); -TimeZoneOffset(); Minutes) );
            {
                RequiredAttendees: Concat( MyPeople; UserPrincipalName & ";" ) & _selectedRoom.Address; 
                Body: TextMeetingMessage1.Text; 
                Location: _selectedRoom.Name; 
                Importance: "Normal"; 
                ShowAs: "Busy"; 
                ResponseRequested: true
            }
        )
    );;
    Concurrent(
        Reset( TextMeetingLocation1 );
        Reset( TextMeetingSubject1 );
        Reset( TextMeetingMessage1 );
        Clear( MyPeople );
        Set( _selectedMeetingTime; Blank() );
        Set( _selectedRoomList; Blank() );
        Set( _selectedRoom; Blank() );
        Set( _roomListSelected; false )
    )
    ```
  
  Tällä koodi lohkolla on alhainen taso:
  1. Määrittää **_Mycalendarname** -kohteen [office365. CalendarGetTables ()](https://docs.microsoft.com/connectors/office365/#get-calendars) -toiminnon kalenteriin, jonka **DisplayName** on Calendar.
  1. Määrittää koko uksen kaikkien niiden syöte arvojen mukaan, jotka käyttäjä on tehnyt koko näytössä käyttäen [office365. V2CalendarPostItem](https://docs.microsoft.com/connectors/office365/#create-event--v2-) -toimintoa.
  1. Palauttaa kaikki koko uksen luonnissa käytetyt syöte kentät ja muuttujat.

> [!NOTE]
> Alueesi mukaan haluamaasi kalenteriin ei ehkä ole määritetty kalenteri-näyttö nimeä. Siirry Outlookiin, jotta näet, mitä kalenterisi otsikko on, ja tee tarvittavat muutokset sovelluksessa.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Lue lisä tietoja tästä näytöstä](./meeting-screen-overview.md)
* [Lue lisä tietoja Office 365 Outlook Connectorista Powerappsissa](../connections/connection-office365-outlook.md)
* [Lue lisä tietoja Office 365-käyttäjien liittimestä Powerappsissa](../connections/connection-office365-users.md)

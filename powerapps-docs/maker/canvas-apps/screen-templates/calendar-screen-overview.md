---
title: Kalenterin näytön malli | Microsoft Docs
description: Ymmärtää, miten kalenterin näytön malli on tarkoitettu pohjaan perustuvat sovellukset toimivat, muokata näytön ja laajenna sitä sovelluksen osana
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/28/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 745b4232a43a06c46866e83ca2452f8a55afeddf
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61536197"
ms.PowerAppsDecimalTransform: true
---
# <a name="overview-of-the-calendar-screen-template-for-canvas-apps"></a>Pohjaan perustuvat sovellukset kalenterin näytön-mallin yleiskatsaus

Lisää kalenterin näyttö, jossa kerrotaan käyttäjät tulevat tapahtumat Office 365 Outlook-tilinsä kangas-sovellus. Käyttäjät voivat valita päivämäärän kalenterista ja Selaa luettelo kyseisen päivän tapahtumista. Voit muuttaa mitkä tiedot näkyvät luettelossa, Lisää toinen näyttö, joka sisältää lisätietoja tapahtuman, Näytä tapahtuman osallistujien luettelo ja tehdä muita mukautuksia.

Voit myös lisätä malliin perustuvan muun, joka näyttää eri Office 365: stä kuten [sähköpostin](email-screen-overview.md), [ihmiset](people-screen-overview.md) organisaatiossasi, ja [käytettävyysryhmän](meeting-screen-overview.md) ihmiset käyttäjien ehkä haluat kutsua kokoukseen.

Tästä yleiskatsauksesta opetetaan:
> [!div class="checklist"]
> * Miten voit käyttää kalenterin oletusnäytön.
> * Miten voit muokata sitä.
> * Miten integrointi sovellukseen.

Katso tarkemmin tarkemmin tässä näytössä oletusarvon toimintoja [kalenterin näytön viittaus](calendar-screen-reference.md).

## <a name="prerequisite"></a>Edellytys

Miten voit lisätä ja määrittää näyttöjä ja muita ohjausobjekteja sinuna tuntee [sovelluksen luominen powerappsin](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Default-toiminnot

Lisää kalenteriin näytön mallista:

1. [Kirjaudu sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin, ja luo sovellus tai avaa olemassa olevaa sovellusta PowerApps Studio.

    Tässä aiheessa näytetään puhelinsovelluksen, mutta samat käsitteet koskevat tablettisovellusta.

1. Valitse **aloitus** Valitse valintanauhan välilehti **uuden näytön** > **kalenterin**.

    Oletusarvon mukaan näytön näyttää tältä:

    ![Kalenteri-näyttö](media/calendar-screen/calendar-initial.png)

1. Tietojen näyttämiseksi Valitse vaihtoehto avattavasta luettelosta näytön yläreunan lähellä.

    ![Kalenterin näytön, kun lataus on valmis](./media/calendar-screen/calendar-screen.png)

Joitakin hyödyllisiä Huomautuksia:

* Päivämäärä on oletusarvoisesti valittuna, ja voit helposti palauttaa se valitsemalla Kalenteri-kuvaketta oikeassa yläkulmassa.
* Jos valitset eri päivämäärän, ympyrän kahvoineen ja Vaalea suorakulmio (sininen, jos oletusteema on käytössä) ympäröi kuluvan päivän päivämäärä.
* Jos vähintään yksi tapahtumasi on ajoitettu tietyn päivämäärän, pienen värillisen ympyrän näkyy päivämäärän kalenterista.
* Jos valitset päivämäärä, jolle yhden tai useamman tapahtumat ajoitetaan, tapahtuma(t) näkyvät luettelossa, valitse kalenteri.

## <a name="modify-the-screen"></a>Muokkaa näyttö

Tämä näyttö oletusarvon toimintoja voit muokata joitakin yleisiä käyttötapoja:

* [Määrittää kalenteri](calendar-screen-overview.md#specify-the-calendar).
* [Näytä tapahtuma eri tietoja](calendar-screen-overview.md#show-different-details-about-an-event).
* [Piilota vaihtamista silloin tapahtumat](calendar-screen-overview.md#hide-nonblocking-events).

Jos haluat muokata näytön tarkemmin [kalenterin näytön viittaus](./calendar-screen-reference.md) ohjeena.

### <a name="specify-the-calendar"></a>Määrittää kalenteri

Jos tiedät jo mitä käyttäjien pitäisi tarkastella kalenteria, voit helposti näytön määrittämällä kyseisen kalenterin, ennen kuin julkaiset sovelluksen. Tämä muutos poistaa tarpeen kalenterit avattavasta luettelosta, jotta voit poistaa sen.

1. Määritä **[OnStart](../controls/control-screen.md)** ominaisuuden oletusnäytön sovelluksessa tämä kaava:

    ```powerapps-comma
    Set( _userDomain; Right( User().Email; Len( User().Email ) - Find( "@"; User().Email ) ) );;
    Set( _dateSelected; Today() );;
    Set( _firstDayOfMonth; DateAdd( Today(); 1 - Day( Today() ); Days ) );;
    Set( _firstDayInView; 
        DateAdd( _firstDayOfMonth; -( Weekday( _firstDayOfMonth) - 2 + 1 ); Days )
    );;
    Set( _lastDayOfMonth; DateAdd( DateAdd( _firstDayOfMonth; 1; Months ); -1; Days ) );;
    Set( _calendarVisible; false );;
    Set( _myCalendar; 
        LookUp( Office365.CalendarGetTables().value; DisplayName = "{YourCalendarNameHere}" )
    );;
    Set( _minDate; 
        DateAdd( _firstDayOfMonth; -( Weekday(_firstDayOfMonth) - 2 + 1 ); Days )
    );;
    Set( _maxDate; 
        DateAdd(
            DateAdd( _firstDayOfMonth; -( Weekday(_firstDayOfMonth) - 2 + 1 ); Days );
            40; 
            Days 
        )
    );;
    ClearCollect( MyCalendarEvents; 
        Office365.GetEventsCalendarViewV2( _myCalendar.Name; 
            Text( _minDate; UTC ); 
            Text( _maxDate; UTC ) 
        ).value
    );;
    Set( _calendarVisible; true )
    ```

    > [!NOTE]
    > Tämä kaava on hieman muokata oletusarvo **OnSelect** avattavan luettelon valitsemalla Kalenteri-ominaisuuden. Saat lisätietoja tämän ohjausobjektin sen-kohdassa [kalenterin näytön viittaus](./calendar-screen-reference.md#calendar-drop-down).

1. Korvaa `{YourCalendarNameHere}`, mukaan lukien aaltosulkeet kalenteria, jonka haluat näyttää nimi (esimerkiksi **kalenterin**).

    > [!IMPORTANT]
    > Seuraavissa vaiheissa oletetaan, että olet lisännyt vain yhden kalenterin näytön sovellukseen. Jos olet lisännyt useampi kuin yksi, ohjausobjektin nimet (kuten **iconCalendar1**) päättyy numeroon, ja sinun on säätää kaavat vastaavasti.

1. Määritä **Y** -ominaisuuden **iconCalendar1** ominaisuudeksi seuraava lauseke:

    `RectQuickActionBar1.Height + 20`

1. Määritä **Y** -ominaisuuden **LblMonthSelected1** ominaisuudeksi seuraava lauseke:

    `iconCalendar1.Y + iconCalendar1.Height + 20`

1. Määritä **tekstin** -ominaisuuden **LblNoEvents1** tämä arvo:

    `"No events scheduled"`

1. Määritä **näkyvissä** ominaisuuden **LblNoEvents1** tämä kaava:

    `CountRows(CalendarEventsGallery1.AllItems) = 0 && _calendarVisible`

1. Poista nämä ohjausobjektit:

    - **dropdownCalendarSelection1**
    - **LblEmptyState1**
    - **iconEmptyState1**

1. Jos kalenteri-näyttö ei ole oletusnäyttö, Lisää painike, joka siirtyy oletusarvon näytöstä kalenteri-näyttöön, jotta voit testata sovellusta.

    Voit esimerkiksi lisätä painikkeen **Screen1** , joka siirtyy **Screen2** Jos olet lisännyt kalenterin näytön sovellus, jonka olet luonut alusta alkaen.

1. Tallenna sovellus ja testaa sitä selaimessa tai mobiililaitteessa.

### <a name="show-different-details-about-an-event"></a>Tapahtuman eri tietojen näyttäminen

Oletusarvoisesti, valitse kalenteri-valikoima nimeltä **CalendarEventsGallery**, näyttää alkamisaika, kesto, aihe ja tapahtuman sijainti. Voit määrittää valikoima näyttämään minkä tahansa kentän (kuten järjestäjä), joka [Office 365-liitin](https://docs.microsoft.com/connectors/office365/#calendareventclientreceive) tukee.

1. - **CalendarEventsGallery**, Määritä **tekstin** uusi tai aiemmin selitteen ominaisuuden `ThisItem` perässä on piste.

    IntelliSense luettelo kentistä, jotka voit valita.

1. Valitse haluamasi kenttä.

    Otsikko näyttää määrittämäsi tiedon tyyppi.

### <a name="hide-nonblocking-events"></a>Piilota vaihtamista silloin tapahtumat

Monta offices tiimin jäsenille Lähetä kokouksen pyyntöjen ilmoittaa toisiinsa, kun ne olla poissa toimistosta. Estä kaikkien ajoitukset välttämiseksi pyynnön henkilön asettaa sen käytettävyysryhmän **vapaa**. Voit piilottaa nämä tapahtumat, kalenterin ja valikoiman päivittämällä muutaman ominaisuudet.

1. Määritä **kohteet** ominaisuuden **CalendarEventsGallery** tämä kaava:

    ```powerapps-comma
    SortByColumns(
        Filter(
            MyCalendarEvents;
            Text( Start; DateTimeFormat.ShortDate ) = 
                Text( _dateSelected; DateTimeFormat.ShortDate );
            ShowAs <> "Free"
        );
        "Start"
    )
    ```

    Tässä kaavassa **suodatin** funktion piilottaa nämä tapahtumia, jotka on suunniteltu kuin valittu päivämäärä paitsi myös tapahtumat, jotka saatavuutta on määritetty **vapaa**.

1. Määritä kalenteri- **näkyvissä** -ominaisuuden **ympyrä** ominaisuudeksi tämä kaava:

    ```powerapps-comma
    CountRows(
        Filter(
            MyCalendarEvents;
            DateValue( Text(Start) ) = DateAdd( _firstDayInView; ThisItem.Value; Days );
            ShowAs <> "Free"
        )
    ) > 0 && !Subcircle1.Visible && Title2.Visible
    ```
    Tämä kaava sisältää samat kuin Edellinen kaava suodattimet. Tämän vuoksi tapahtuman osoitin ympyrän kohtaan päivämäärä vain, jos se on yksi tai useampi tapahtumia, jotka ovat valittuna päivämääränä ja joka käytettävyysryhmä ei ole asetettu **vapaa**.

## <a name="integrate-the-screen-into-an-app"></a>Näytön integrointi sovellukseen

Kalenteri-näyttö on tehokas nipun ohjausobjektien oma, mutta se toimii parhaiten yleensä suurempi, monipuolisempia sovelluksen osana. Voit integroida tämän näytön suurempi sovelluksen useilla eri tavoilla, muun muassa lisätä nämä asetukset:

* [Tarkastele tapahtumatiedot](calendar-screen-overview.md#view-event-details).
* [Näytä tapahtuman osallistujat](calendar-screen-overview.md#show-event-attendees).

### <a name="view-event-details"></a>Tapahtuman tietojen tarkasteleminen

Jos käyttäjät voivat valita tapahtuma luodaan **CalendarEventsGallery**, voit avata toiseen näyttöön, joka näyttää lisätietoja siitä, että tapahtuma.

> [!NOTE]
> Seuraavassa kuvataan tapahtumatiedot valikoima, jossa dynaamista sisältöä, mutta voit saavuttaa samanlaiset tulokset ottamalla muilla. Voit esimerkiksi saada suunnittelu tarkemmin käyttämällä sarjan otsikot.

1. Lisää tyhjä näyttö, jonka nimi on **EventDetailsScreen**, joka sisältää tyhjä joustava korkeus-valikoima ja painike, joka siirtyy takaisin kalenteri-näyttöön.

1. Joustava korkeus-valikoimassa ja lisää **nimen** ohjausobjektin ja **HTML-tekstin** ohjausobjekti ja määritä **AutoHeight** ominaisuuden kummatkin **true** .

    > [!NOTE]
    > PowerApps hakee tapahtuman tekstin HTML-teksti, joten sinun tarvitsee näyttää kyseisen sisällön **HTML-tekstin** ohjausobjektin.

1. Määritä **Y** -ominaisuuden **HTML-tekstin** ominaisuudeksi seuraava lauseke:

    `Label1.Y + Label1.Height + 20`

1. Säädä lisäominaisuudet tarvittaessa, jotta tarpeisiisi tyyli.

    Esimerkiksi, haluat ehkä Lisää erottimen viivan alla **HTML-tekstin** ohjausobjektin.

1. Määritä **kohteet** ominaisuus joustava korkeus tämä kaava:

    ```powerapps-comma
    Table(
        { Title: "Subject"; Value: _selectedCalendarEvent.Subject };
        { 
            Title: "Time"; 
            Value: _selectedCalendarEvent.Start & " - " & _selectedCalendarEvent.End 
        };
        { Title: "Body"; Value: _selectedCalendarEvent.Body }
    )
    ```

    Tämä kaava Luo valikoima, jonka kenttien arvot on määritetty dynaamisen tietojen **_selectedCalendarEvent**, joka on määritetty aina, kun käyttäjä valitsee tapahtuma luodaan **CalendarEventsGallery** ohjausobjektin. Voit laajentaa valikoiman sisältämään enemmän kenttiä lisäämällä useita selitteitä, mutta on hyvä aloituskohta.

1. Määrittää valikoimakohteet paikassa, **tekstin** -ominaisuuden **nimen** ohjausobjektin `ThisItem.Title`, ja **HtmlText** -ominaisuuden **HTML-teksti**  ohjausobjektin `ThisItem.Value`.

1. - **CalendarEventsGallery**, Määritä **OnSelect** -ominaisuuden **otsikko** ominaisuudeksi tämä kaava:

    ```powerapps-comma
    Set( _selectedCalendarEvent; ThisItem );;
    Navigate( EventDetailsScreen; None )
    ```

    > [!Note]
    > Käyttämisen sijasta **_selectedCalendarEvent** muuttujan, voit sen sijaan käyttää **CalendarEventsGallery**. Valittu.

### <a name="show-event-attendees"></a>Näytä tapahtuman osallistujat

`Office365.GetEventsCalendarViewV2` Toiminto noutaa kentät kullekin tapahtumalle, mukaan lukien puolipistein eroteltu joukon pakolliset ja valinnaiset osallistujat erilaisia. Tässä toimenpiteessä jäsentää jokaiseen osallistujat, määrittää, mitkä osallistujat organisaatiossasi ja hakea, kuka tahansa ovat Office 365-profiilit.

1. Jos sovelluksesi ei ole Office 365-käyttäjät-liittimen [lisätä sen](../add-data-connection.md).

1. Noutaa kokouksen osallistujille Office 365-profiileja, Määritä **OnSelect** -ominaisuuden **otsikko** ohjausobjektia **CalendarEventsGallery** tämä kaava:

    ```powerapps-comma
    Set( _selectedCalendarEvent; ThisItem );;
    ClearCollect( AttendeeEmailsTemp;
        Filter(
            Split( ThisItem.RequiredAttendees & ThisItem.OptionalAttendees; ";" );
            !IsBlank( Result )
        )
    );;
    ClearCollect( AttendeeEmails;
        AddColumns( AttendeeEmailsTemp; 
            "InOrg";
            Upper( _userDomain ) = Upper( Right( Result; Len( Result ) - Find( "@"; Result ) ) )
        )
    );;
    ClearCollect( MyPeople;
        ForAll( AttendeeEmails; If( InOrg; Office365Users.UserProfile( Result ) ) ) 
    );;
    Collect( MyPeople;
        ForAll( AttendeeEmails;
            If( !InOrg; 
                { DisplayName: Result; Id: ""; JobTitle: ""; UserPrincipalName: Result }
            )
        )
    )
    ```

Tämän luettelon käsitellään kunkin **ClearCollect** toiminto:

- ClearCollect(AttendeeEmailsTemp)
    ```powerapps-comma
    ClearCollect( AttendeeEmailsTemp;
        Filter(
            Split( ThisItem.RequiredAttendees & ThisItem.OptionalAttendees; ";" ); 
            !IsBlank( Result)
        )
    );;
    ```

    Tämä kaava yhdistää yksittäiseksi merkkijonoksi pakolliset ja valinnaiset osallistujat ja jakaa sitten Tämä merkkijono yksittäiset osoitteet tällä kunkin puolipisteillä. Kaava sitten suodattaa pois tyhjät arvot kyseisen joukosta ja Lisää muut arvot nimeltä kokoelmaan **AttendeeEmailsTemp**.

- ClearCollect(AttendeeEmails)
    ```powerapps-comma
    ClearCollect( AttendeeEmails;
        AddColumns( AttendeeEmailsTemp; 
            "InOrg";
            Upper( _userDomain ) = Upper( Right( Result; Len(Result) - Find("@"; Result) ) )
        )
    );;
    ```
    Tämä kaava määrittää suunnilleen, onko osallistuja organisaatiossasi. Määritys **_userDomain** on yksinkertaisesti toimialueen URL-osoite on käytössä, sovelluksen henkilön sähköpostiosoite. Tämä rivi luo muita tosi/epätosi-sarakkeen nimeltä **InOrg**- **AttendeeEmailsTemp** kokoelma. Sarake sisältää **true** Jos **userDomain** sähköpostiosoitteeseen kyseisen rivin toimialueen URL-osoite vastaa **AttendeeEmailsTemp**.

    Tämä lähestymistapa ei ole aina tarkkoja, mutta noutaa melko Sulje. Esimerkiksi tietyn osallistujat organisaatiossasi saattaa olla sähköpostiosoitetta, kuten Jane@OnContoso.com, olisi **_userDomain** on Contoso.com. Sovelluksen käyttäjälle ja Jane saattaa toimia samassa yrityksessä mutta olla vähäinen variaatioita sähköpostiosoitteet. Tällaisissa tilanteissa, haluat ehkä käyttää kaavaa:

    `Upper(_userDomain) in Upper(Right(Result; Len(Result) - Find("@"; Result)))`

    Kuitenkin kaava vastaa sähköpostiosoitteet, kuten Jane@NotTheContosoCompany.com kanssa **_userDomain** kuten Contoso.com ja nämä henkilöt eivät toimi samassa yrityksessä.

- ClearCollect(MyPeople)

    ```powerapps-comma
    ClearCollect( MyPeople;
        ForAll( AttendeeEmails; 
            If( InOrg; 
                Office365Users.UserProfile( Result )
            )
        )
    );;
    Collect( MyPeople;
        ForAll( AttendeeEmails;
            If( !InOrg; 
                { 
                    DisplayName: Result; 
                    Id: ""; 
                    JobTitle: ""; 
                    UserPrincipalName: Result
                }
            )
        )
    );;
    ```
    Noutaa Office 365-profiileja, sinun on käytettävä [Office365Users.UserProfile](https://docs.microsoft.com/connectors/office365users/#userprofile) tai [Office365Users.UserProfileV2](https://docs.microsoft.com/connectors/office365users/#userprofile) toiminto. Nämä toiminnot kerää ensin kaikki Office 365-profiilit osallistujille, joilla on käyttäjän org. Sitten Toiminnot Lisää muutama kenttä osallistujat organisaatiosi ulkopuolella. Nämä kaksi kohdetta jaettu eri toimintoja koska **ForAll** silmukka ei takaa järjestyksessä. Tämän vuoksi **ForAll** saattaa kerätä osallistuja-organisaation ulkopuolisten ensin. Tässä tapauksessa rakennetta **MyPeople** sisältää vain **DisplayName**, **tunnus**, **JobTitle**, ja **UserPrincipalName** . Kuitenkin käyttäjäprofiili toiminnot noutaa paljon monipuolisempaa tietoja, jotka kuin. Jotta voit pakottaa **MyPeople** Lisää Office 365-profiileja, ennen kuin muut profiilit kokoelma.

    > [!NOTE]
    > Voit saavuttaa saman tuloksen ainoastaan yhteen **ClearCollect** funktio:

    ```powerapps-comma
    ClearCollect( MyPeople; 
        ForAll(
            AddColumns(
                Filter(
                    Split(
                        ThisItem.RequiredAttendees & ThisItem.OptionalAttendees; 
                        ";"
                    ); 
                    !IsBlank( Result )
                ); 
                "InOrg"; _userDomain = Right( Result; Len( Result ) - Find( "@"; Result ) )
            ); 
            If( InOrg; 
                Office365Users.UserProfile( Result ); 
                { 
                    DisplayName: Result; 
                    Id: ""; 
                    JobTitle: ""; 
                    UserPrincipalName: Result; 
                    Department: ""; 
                    OfficeLocation: ""; 
                    TelephoneNumber: ""
                }
            )
        )
    )
    ```

Viimeistele Tässä harjoituksessa:

1. Lisää näyttö, joka sisältää valikoima, jonka **kohteet** asetuksena on **MyPeople**.

1. - **OnSelect** -ominaisuuden **otsikko** ohjausobjektia **CalendarEventsGallery**, Lisää **Navigate** funktio näyttöön, loit edellisessä vaiheessa.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Näytä tämä näyttö ohjeessa](calendar-screen-reference.md).
* [Lue lisätietoja Office 365 Outlook-liittimessä](../connections/connection-office365-outlook.md).
* [Lue lisätietoja Office 365-käyttäjät-liittimen](../connections/connection-office365-users.md).

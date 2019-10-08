---
title: Kalenteri näytön malli | Microsoft Docs
description: Tutustu siihen, miten pohjaan kuuluvien sovellusten kalenteri näyttö malli toimii, Muokkaa näyttöä ja laajentaa sitä osana sovellusta
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/28/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 470aa0671eddc5f4d3621c4dbdd8d81036c358e4
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71989401"
ms.PowerAppsDecimalTransform: true
---
# <a name="overview-of-the-calendar-screen-template-for-canvas-apps"></a>Kangas sovellusten kalenteri näytön mallin yleiskatsaus

Lisää kangas sovelluksessa kalenteri näyttö, joka sisältää käyttäjien tulevat tapahtumat Office 365 Outlook-tiliinsä. Käyttäjät voivat valita päivä määrän kalenterista ja vierittää luettelon kyseisen päivän tapahtumista. Voit muuttaa luettelossa näkyviä tietoja, lisätä toisen näytön, joka näyttää lisä tietoja kustakin tapahtumasta, näyttää kunkin tapahtuman osallistujien luettelon ja tehdä muita mukautuksia.

Voit myös lisätä muita mallipohjaisia näyttöjä, jotka näyttävät eri tietoja Office 365-tieto koneesta, kuten [sähkö postista](email-screen-overview.md), organisaation [henkilöistä](people-screen-overview.md) ja käyttäjien [saatavuudesta](meeting-screen-overview.md) .

Tässä yleiskatsauksessa opit:
> [!div class="checklist"]
> * Oletus kalenteri näytön käyttäminen.
> * Sen muokkaaminen.
> * Miten voit integroida sen sovellukseen.

Lisä tietoja tämän näytön oletusarvoisesta toiminnosta on [kalenteri näytön viite](calendar-screen-reference.md)oppaassa.

## <a name="prerequisite"></a>Edellytys

Perehtyneisyys näyttöjen ja muiden ohjaus objektien lisäämiseen ja määrittämiseen [, kun luot sovelluksen Powerappsissa](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Oletus toiminto

Kalenteri näytön lisääminen mallista:

1. [Kirjaudu sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin ja luo sitten sovellus tai Avaa olemassa oleva sovellus PowerApps Studio.

    Tässä ohje aiheessa näytetään Puhelin sovellus, mutta samat käsitteet koskevat myös Tablet-sovellusta.

1. Valitse valinta nauhan **Aloitus** -väli lehdeltä **Uusi näyttö** > -**kalenteri**.

    Oletus arvon mukaan näyttö näyttää seuraavanlaiselta:

    ![Kalenteri näyttö](media/calendar-screen/calendar-initial.png)

1. Jos haluat näyttää tiedot, valitse vaihto ehto näytön yläreunan lähellä olevasta avattavasta luettelosta.

    ![Kalenteri näyttö lataamisen jälkeen on valmis](./media/calendar-screen/calendar-screen.png)

Muutama hyödyllinen Huomautus:

* Tämän päivän päivä määrä on oletus arvon mukaan valittuna, ja voit palata siihen helposti valitsemalla Kalenteri kuvakkeen oikeassa yläkulmassa.
* Jos valitset eri päivä määrän, ympyrä ympäröi sen ja vaalea suora kulmio (sininen, jos oletus teema otetaan käyttöön) ympäröi kuluvan päivän päivä määrää.
* Jos vähintään yksi tapahtuma on ajoitettu tietylle päivä kohdalle, kyseisenä päivä määränä näkyy pieni värillinen ympyrä kalenterissa.
* Jos valitset päivä määrän, jolloin vähintään yksi tapahtuma ajoitetaan, tapahtuma näkyy kalenterin alla olevassa luettelossa.

## <a name="modify-the-screen"></a>Muokkaa näyttöä

Voit muokata tämän näytön oletus toimintoja muutamalla yhteisellä tavalla:

* [Määritä kalenteri](calendar-screen-overview.md#specify-the-calendar).
* [Näytä tapahtuman eri tiedot](calendar-screen-overview.md#show-different-details-about-an-event).
* [Piilota muut kuin esto tapahtumat](calendar-screen-overview.md#hide-nonblocking-events).

Jos haluat muokata näyttöä edelleen, käytä apuna [kalenteri näytön viittausta](./calendar-screen-reference.md) .

### <a name="specify-the-calendar"></a>Määritä kalenteri

Jos tiedät jo, mitä kalenteria käyttäjien tulee tarkastella, voit yksinkertaistaa näyttöä määrittämällä kyseisen kalenterin, ennen kuin julkaiset sovelluksen. Tämä muutos poistaa avattavien kalenterien luettelon tarpeen, jotta voit poistaa sen.

1. Valitse sovelluksen oletus näytön **[ONSTART](../controls/control-screen.md)** -ominaisuudeksi Tämä kaava:

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
    > Tätä kaavaa muokataan hieman kalenterin valitsemisen avattavan luettelon **onselect** -ominaisuuden oletus arvosta. Lisä tietoja tästä ohjaus objektista on [kalenteri näytön viitta](./calendar-screen-reference.md#calendar-drop-down)uksen osassa.

1. Korvaa `{YourCalendarNameHere}`, mukaan lukien aalto sulkeet, sen kalenterin nimellä, jonka haluat näyttää (esimerkiksi **kalenteri**).

    > [!IMPORTANT]
    > Seuraavissa vaiheissa oletetaan, että olet lisännyt sovellukseen vain yhden kalenteri näytön. Jos olet lisännyt useamman kuin yhden, ohjaus objektien nimet (kuten **iconCalendar1**) päättyvät eri numeroon, ja sinun on säädettävä kaavoja vastaavasti.

1. Määrittää **iconCalendar1** -ohjaus objektin **yy** -ominaisuudeksi tämä lauseke:

    `RectQuickActionBar1.Height + 20`

1. Määrittää **LblMonthSelected1** -ohjaus objektin **yy** -ominaisuudeksi tämä lauseke:

    `iconCalendar1.Y + iconCalendar1.Height + 20`

1. Valitse **LblNoEvents1** -ohjaus objektin **Text** -ominaisuudeksi tämä arvo:

    `"No events scheduled"`

1. Valitse **LblNoEvents1** -ominaisuuden **Visible** -ominaisuudeksi Tämä kaava:

    `CountRows(CalendarEventsGallery1.AllItems) = 0 && _calendarVisible`

1. Poista nämä ohjaus objektin:

    - **dropdownCalendarSelection1**
    - **LblEmptyState1**
    - **iconEmptyState1**

1. Jos kalenteri näyttö ei ole oletus näyttö, Lisää painike, joka siirtyy oletus näytöstä kalenteri-näyttöön, jotta voit testata sovellusta.

    Voit esimerkiksi lisätä painikkeen **Screen1** , joka siirtyy kohteeseen **Screen2** , jos olet lisännyt kalenteri näytön sovellukseen, jonka loit tyhjästä.

1. Tallenna sovellus ja testaa sitä sitten selaimessa tai mobiililaitteessa.

### <a name="show-different-details-about-an-event"></a>Näytä tapahtuman eri tiedot

Oletus arvon mukaan kalenterissa, jonka nimi on **Calendareventsgallery**, näytetään kunkin tapahtuman alkamis aika, kesto, aihe ja sijainti. Voit määrittää valikoiman näyttämään mikä tahansa kenttä (kuten järjestäjä), jota [Office 365-liitin](https://docs.microsoft.com/connectors/office365/#calendareventclientreceive) tukee.

1. Valitse **kalenteri-valikoima**-kohdassa uuden tai aiemmin luodun otsikon **Text** -ominaisuudeksi `ThisItem` ja sen jälkeen piste.

    IntelliSense näyttää luettelon kentistä, joita voit valita.

1. Valitse haluamasi kenttä.

    Selitteessä näytetään määrittämiesi tietojen tyyppi.

### <a name="hide-nonblocking-events"></a>Piilota nonblocking-tapahtumat

Monissa toimistoissa työryhmän jäsenet lähettävät Kokous pyyntöjä ilmoittaakseen toisilleen, kun he ovat poissa toimistosta. Jos haluat estää kaikkien aika taulujen estämisen, pyynnön lähettänyt henkilö asettaa sen saatavuuden **vapaaksi**. Voit piilottaa nämä tapahtumat kalenterista ja valikoimasta päivittämällä muutaman ominaisuuden.

1. Valitse **Calendarevensgallery** - **kohteen Items** -ominaisuudeksi Tämä kaava:

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

    Tässä kaavassa **Filter** -Funktiot piilottaa ei vain ne tapahtumat, jotka on ajoitettu muulle kuin valitulle päivä määräksi, vaan myös tapahtumat, joiden käytettävyysasetukseksi on määritetty **ilmainen**.

1. Valitse kalenterissa **ympyrä** -ohjaus objektin **Visible** -ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    CountRows(
        Filter(
            MyCalendarEvents;
            DateValue( Text(Start) ) = DateAdd( _firstDayInView; ThisItem.Value; Days );
            ShowAs <> "Free"
        )
    ) > 0 && !Subcircle1.Visible && Title2.Visible
    ```
    Tämä kaava sisältää samat suodattimet kuin edellinen kaava. Tästä syystä tapahtuma ilmaisimen ympyrä näkyy päivä määrän alla vain, jos sillä on yksi tai useampi tapahtuma, joka on valitulla päivä määrällä ja jonka käytettävyysarvoksi ei ole määritetty **vapaata**.

## <a name="integrate-the-screen-into-an-app"></a>Näytön integroiminen sovellukseen

Kalenteri näyttö on tehokas nippu ohjaus objektien omaa oikeutta, mutta se toimii yleensä parhaiten osana suurempaa, monipuolista sovellusta. Voit integroida tämän näytön suurempaan sovellukseen useilla eri tavoilla, kuten lisäämällä näitä asetuksia:

* [Näytä tapahtuman tiedot](calendar-screen-overview.md#view-event-details).
* [Näytä tapahtuman osallistujat](calendar-screen-overview.md#show-event-attendees).

### <a name="view-event-details"></a>Näytä tapahtuman tiedot

Jos käyttäjät valitsevat tapahtuman **Calendarevensgallery**-kohteessa, voit avata toisen näytön, joka sisältää lisä tietoja kyseiseen tapahtumaan.

> [!NOTE]
> Tämä menettely näyttää tapahtuma tiedot valikoimassa, jossa on dynaamista sisältöä, mutta voit saavuttaa samanlaiset tulokset ottamalla muita tapoja. Voit esimerkiksi saada lisää rakenne-ohjaus objektin käyttämällä sen sijaan useita otsikoita.

1. Lisää tyhjä näyttö nimeltä **Eventdetailsscreen**, joka sisältää tyhjän joustavan korkeuden valikoiman ja painikkeen, joka siirtyy takaisin kalenteri-näyttöön.

1. Lisää joustavan korkeuden valikoimaan **Selite** -ohjaus objekti ja **HTML-teksti** -ohjaus objekti sekä määrittää molempien **Automaattinen korkeus** -ominaisuudeksi **True**.

    > [!NOTE]
    > PowerApps noutaa kunkin tapahtuman sanoman rungon HTML-tekstinä, joten sinun on näytettävä sisältö **HTML-teksti** ohjaus objektissa.

1. Määrittää **HTML-teksti** ohjaus objektin **yy** -ominaisuudeksi tämän lausekkeen:

    `Label1.Y + Label1.Height + 20`

1. Säädä lisä ominaisuuksia tarvittaessa tyylisi mukaan.

    Saatat esimerkiksi haluta lisätä erotin viivan **HTML-teksti** -ohjaus objektin alapuolelle.

1. Valitse joustavan korkeuden valikoiman **Items** -ominaisuudeksi Tämä kaava:

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

    Tämä kaava luo valikoiman dynaamisia tietoja, jotka on määritetty **_Selectedcalendarevent**-kentän arvoihin, joka määritetään aina, kun käyttäjä valitsee tapahtuman **Calendarevensgallery** -ohjaus objektissa. Voit laajentaa tämän valikoiman sisältämään lisää kenttiä lisäämällä siihen otsikoita, mutta tämä joukko antaa hyvän lähtö kohdan.

1. Kun valikoiman kohteet ovat paikallaan, Aseta **Label** -ohjaus objektin **Text** -ominaisuudeksi `ThisItem.Title` ja **HTML-teksti** ohjaus objektin **htmltext** -ominaisuudeksi `ThisItem.Value`.

1. Määritä **calendareventsgallery**-kohteessa **title** -ohjaus objektin **onselect** -ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    Set( _selectedCalendarEvent; ThisItem );;
    Navigate( EventDetailsScreen; None )
    ```

    > [!Note]
    > Sen sijaan, että käyttäisit **_Selectedcalendarevent** -muuttujaa, voit käyttää **Calendareventsgallery**-kohdetta. Valitun.

### <a name="show-event-attendees"></a>Näytä tapahtuman osallistujat

@No__t-0-toiminto noutaa kullekin tapahtumalle useita kenttiä, mukaan lukien puoli pistein eroteltu pakollisten ja valinnaisten osallistujien joukko. Tässä toimenpiteessä jäsennetään kutakin osanottajajoukkoa, määritetään, ketkä osallistujat ovat organisaatiossasi, ja nouda kaikkien niiden Office 365-profiilit.

1. Jos sovelluksesi ei sisällä Office 365-käyttäjien liitintä, [Lisää se](../add-data-connection.md).

1. Jos haluat noutaa koko uksen osallistujien Office 365-profiilit, Määritä **Calendarventsgallery** - **ohjaus objektin** **onselect** -ominaisuudeksi Tämä kaava:

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

Tässä listassa kerrotaan, mitä kukin **Clearcollect** -toiminto tekee:

- ClearCollect (Attedeeemailstemp)
    ```powerapps-comma
    ClearCollect( AttendeeEmailsTemp;
        Filter(
            Split( ThisItem.RequiredAttendees & ThisItem.OptionalAttendees; ";" ); 
            !IsBlank( Result)
        )
    );;
    ```

    Tämä kaava yhdistää pakolliset ja valinnaiset osallistujat yksittäiseksi merkki jonoksi ja jakaa sitten merkki jonon yksittäisiksi osoitteiksi kummallakin puoli pisteellä. Kaava suodattaa sitten pois tyhjät arvot kyseisestä joukosta ja Lisää Muut arvot kokoelmaan, jonka nimi on **Attedeeemailstemp**.

- ClearCollect (Attedeemails)
    ```powerapps-comma
    ClearCollect( AttendeeEmails;
        AddColumns( AttendeeEmailsTemp; 
            "InOrg";
            Upper( _userDomain ) = Upper( Right( Result; Len(Result) - Find("@"; Result) ) )
        )
    );;
    ```
    Tämä kaava määrittää suunnilleen, onko osallistuja organisaatiossasi. **_Userdomain** -määrityksen on yksinkertaisesti toimi alueen URL-osoite sovelluksen suorittavan henkilön Sähkö posti osoitteessa. Tämä linja luo ylimääräisen true/false-sarakkeen, jonka nimi on **Inorg**, **Attedeeemailstemp** -kokoelmassa. Tämä sarake sisältää arvon **True** , jos **userdomain** on sama kuin kyseisen rivin **Attendeeemailstemp**-ohjaus objektin toimi alueen URL-osoite.

    Tämä lähestymis tapa ei ole aina tarkka, mutta se tulee melko lähelle. Esimerkiksi tietyillä organisaatiosi osallistujilla voi olla Sähkö posti osoite, kuten Jane@OnContoso.com, kun taas **_Userdomain** on contoso.com. Sovelluksen käyttäjä ja Jane saattavat toimia samassa yrityksessä, mutta niiden sähkö posti osoitteissa on vähäisiä muutoksia. Tällaisissa tapa uksissa haluat ehkä käyttää seuraavaa kaavaa:

    `Upper(_userDomain) in Upper(Right(Result; Len(Result) - Find("@"; Result)))`

    Tämä kaava vastaa kuitenkin Sähkö posti osoitteita, kuten Jane@NotTheContosoCompany.com, jossa on **_Userdomain** , kuten contoso.com, ja nämä henkilöt eivät toimi samassa yrityksessä.

- ClearCollect (MyPeople)

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
    Jos haluat noutaa Officen 365-profiilit, sinun on käytettävä [Office365Users. UserProfile](https://docs.microsoft.com/connectors/office365users/#userprofile) -tai [Office365Users. UserProfileV2](https://docs.microsoft.com/connectors/office365users/#userprofile) -toimintoa. Nämä toiminnot keräävät ensin kaikki Officen 365-profiilit käyttäjän organisaatiossa oleville osallistujille. Sen jälkeen toiminnot lisäävät muutaman kentän osanottajille organisaation ulkopuolelta. Erotit nämä kaksi kohdetta erillisiin toimintoihin, koska **kokeilu** silmukka ei takaa järjestystä. Tästä syystä **kokeilu** voi kerätä osallistujan organisaation ulkopuolelta. Tässä tapa uksessa **Mypeople** -rakenne sisältää vain **DisplayName**-, **ID**-, **jobtitle**-ja **userPrincipalName-nimet**. UserProfile-toiminnot noutavat kuitenkin paljon monipuolisempia tietoja. Pakotat **Mypeople** -kokoelman lisäämään Officen 365-profiileja ennen muita profiileja.

    > [!NOTE]
    > Voit saavuttaa saman tuloksen vain yhdellä **Clearcollect** -funktiolla:

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

Viimeistele Tämä harjoitus:

1. Lisää näyttö, joka sisältää valikoiman, jonka **Items** -ominaisuudeksi on määritetty **mypeople**.

1. Lisää **kalenteri-valikoima**-kohdan **onselect** -ominaisuudeksi **siirtymis** -funktiolla edellisessä vaiheessa luomaasi näyttöön.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Näytä tämän näytön viite asiakirjat](calendar-screen-reference.md).
* [Lue lisä tietoja Office 365 Outlook Connectorista](../connections/connection-office365-outlook.md).
* [Lue lisä tietoja Office 365-käyttäjien liittimestä](../connections/connection-office365-users.md).

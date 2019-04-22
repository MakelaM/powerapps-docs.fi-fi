---
title: Viittaus pohjaan perustuvat sovellukset kalenterin näytön-malli | Microsoft Docs
description: Tutustu powerappsin pohjaan perustuvat sovellukset kalenterin näytön malli toimintaan tiedot.
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
ms.openlocfilehash: e3d5f40a604d2cbfa074ed5973d599c40a6c5c05
ms.sourcegitcommit: f84095d964fe1fe5cc5290e5edbee284bd768e1e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/18/2019
ms.locfileid: "58765579"
---
# <a name="reference-information-about-the-calendar-screen-template-for-canvas-apps"></a>Lisätietoja pohjaan perustuvat sovellukset kalenterin näytön-malli

Pohjaan perustuvia sovelluksia powerappsissa ymmärrä, miten merkittäviä ohjausobjekteja kalenterin näytön mallin osallistuu näytön yleistä oletusarvon toimintoja. Nämä esittää toiminta-kaavat ja arvot muita ominaisuuksia, jotka määrittävät, miten ohjausobjektit vastata käyttäjän syötettä. Lisätietoja korkean tason tässä näytössä oletusarvon toiminnot-kohdassa [kalenterin näytön yleiskatsaus](calendar-screen-overview.md).

Tässä ohjeaiheessa korostaa joitakin merkittäviä ohjausobjekteja ja kerrotaan lausekkeita tai kaavoja mitä eri ominaisuuksia (kuten **kohteet** ja **OnSelect**) ohjausobjektit on määritetty:

- [Kalenterin avattavasta (dropdownCalendarSelection)](#calendar-drop-down)
- [Kalenteri-kuvaketta (iconCalendar)](#calendar-icon)
- [Edellinen kuukausi chevron (iconPrevMonth)](#previous-month-chevron)
- [Seuraavan kuukauden chevron (iconNextMonth)](#next-month-chevron)
- [Kalenterin valikoima (MonthDayGallery) (+ aliohjausobjektit)](#calendar-gallery)
- [Valikoiman tapahtumat (CalendarEventsGallery)](#events-gallery)

## <a name="prerequisite"></a>Edellytys

Miten voit lisätä ja määrittää näyttöjä ja muita ohjausobjekteja sinuna tuntee [sovelluksen luominen powerappsin](../data-platform-create-app-scratch.md).

## <a name="calendar-drop-down"></a>Kalenterin avattava valikko

![dropdownCalendarSelection ohjausobjekti](media/calendar-screen/calendar-dropdown.png)

- Ominaisuus: **Kohteet**<br>
    Arvo: `Office365.CalendarGetTables().value`

    Tämä arvo on connector-toimintoa, joka noutaa sovelluksen käyttäjän Outlook kalenterit. Näet [arvo](https://docs.microsoft.com/connectors/office365/#entitylistresponse[table]) , tämä toiminto noutaa.

- Ominaisuus: **OnChange**<br>Arvo: `Select(dropdownCalendarSelection)`

    Kun käyttäjä valitsee ohjausobjektin-funktio-luettelossa vaihtoehtoa **OnSelect** ominaisuus suoritetaan.

- Ominaisuus: **OnSelect**<br>
    Arvo: **Jos** funktio, joka näkyy varten seuraava koodilohko, ja useita muita funktioita, jotka ovat varten koodilohko sen jälkeen.

   Tämä osa-kaava suoritetaan vain ensimmäisellä kerralla, että käyttäjä valitsee vaihtoehdon avattavasta luettelosta sovelluksen avaamisen jälkeen:

    ```powerapps-dot
    If( IsBlank( _userDomain ),
        UpdateContext( {_showLoading: true} );
        Set( _userDomain, Right( User().Email, Len( User().Email ) - Find( "@", User().Email ) ) );
        Set( _dateSelected, Today() );
        Set( _firstDayOfMonth, DateAdd( Today(), 1 - Day( Today() ), Days ) );  
        Set( _firstDayInView, DateAdd( _firstDayOfMonth, -(Weekday(_firstDayOfMonth) - 1), Days ) );
        Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) )  
    );
    ```

    Yllä olevaa koodia muuttujat:
    
  - **\_userDomain**: Sovelluksen käyttäjän yrityksen toimialueen, joka näkyy käyttäjän sähköpostiosoite.
  - **\_dateSelected**: Päivämäärä (oletusarvon mukaan). Kalenterin valikoiman korostaa tämä päivämäärä ja tapahtuman valikoima näyttää tapahtumia, jotka on suunniteltu päivämäärän.
  - **\_firstDayOfMonth**: Kuluvan kuukauden ensimmäisenä päivänä. Koska `(Today + (1 - Today)) = Today - Today + 1 = 1`, tämä **DateAdd** -funktio palauttaa aina kuukauden ensimmäisenä päivänä.
  - **\_firstDayInView**: Ensimmäinen päivä, kalenteri-valikoima näyttää. Tämä arvo ei ole sama kuin kuukauden ensimmäisenä päivänä ellei kuukauden alkaa sunnuntai. Voit estää näytetään edellisen kuukauden arvo koko viikko  **\_firstDayInView** on `_firstDayOfMonth - Weekday(_firstDayOfMonth) + 1`.
  - **\_lastDayOfMonth**: Kuluvan kuukauden viimeisen päivän joka on sama kuin kuukautena, miinus yksi päivä ensimmäisenä päivänä.

   Funktiot jälkeen **Jos** funktio suorittaa aina, kun käyttäjä valitsee vaihtoehdon Kalenteri avattavasta luettelosta (ei pelkästään ensimmäistä kertaa käyttäjä avaa sovelluksen):

    ```powerapps-dot
    Set( _calendarVisible, false );
    UpdateContext( {_showLoading: true} );
    Set( _myCalendar, dropdownCalendarSelection2.Selected );
    Set( _minDate, 
        DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days )
    );
    Set(_maxDate, 
        DateAdd(
            DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days ), 
            40, 
            Days
        )
    );
    ClearCollect( MyCalendarEvents, 
        'Office365'.GetEventsCalendarViewV2( _myCalendar.Name, 
            Text( _minDate, UTC ), 
            Text( _maxDate, UTC )
        ).value
    );
    UpdateContext( {_showLoading: false} );
    Set( _calendarVisible, true )
    ```

    Yllä olevaa koodia määrittää muuttujia ja yksi kokoelma:

    - **\_calendarVisible**: Määritetty **false** niin, että kalenterin ei tule näkyviin, kun uusi valinta on ladattu.
    - **\_showLoading**: Määritetty **true** niin, että lataamisen ilmaisimet näkyviin, kun uusi valinta ladataan.
    - **\_myCalendar**: Nykyinen arvo arvoksi **kalenterin avattavasta** siten, että oikea kalenterin tapahtumat noudetaan.
    - **\_minDate**: Määritä sama arvo kuin  **\_firstDayInView**. Tämä muuttujaa määrittää, mitkä tapahtumat on jo noudetut Outlook ja välimuistiin sovelluksessa.
    - **\_maxDate**: Määrittää voi tarkastella viimeisenä kalenterissa. Kaava on `_firstDayInView + 40`. Kalenterin näyttää enintään 41 päivää, joten  **\_maxDate** muuttujan aina kuvastaa viimeisenä voi tarkastella ja määrittää, mitkä tapahtumat on jo noudetut Outlook ja välimuistiin sovelluksessa.
    - **MyCalendarEvents**: Määrittää käyttäjän tapahtumien kokoelmaan valitussa kalenterissa, jonka  **\_minDate** -  **\_maxDate**.
    - **\_showLoading**: Määritetty **false**;  **\_calendarVisible** asetetaan **true** jälkeen kaikki muut on ladattu.

## <a name="calendar-icon"></a>Kalenteri-kuvaketta

![iconCalendar ohjausobjekti](media/calendar-screen/calendar-today-icon.png)

- Ominaisuus: **OnSelect**<br>
    Arvo: Neljä **määrittää** toiminnot, jotka vaihtaa kalenterin valikoiman päivämäärä:

    ```powerapps-dot
    Set( _dateSelected, Today() );
    Set( _firstDayOfMonth, DateAdd( Today(), 1 - Day( Today() ), Days) );
    Set( _firstDayInView, DateAdd(_firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days));
    Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) )
    ```

    Yllä olevaa koodia palauttaa kaikki päivämäärä-muuttujia, jotka on täytettävä asianmukaiset kalenterinäkymä näyttäminen:

    - **\_dateSelected** nollataan tänään.
    - **\_firstDayOfMonth** nollataan kuluvan kuukauden ensimmäisenä päivänä.
    - **\_firstDayInView** ensimmäisenä voi tarkastella kuluvan kuukauden valittaessa palautetaan.
    - **\_lastDayOfMonth** nollataan kuluvan kuukauden viimeisenä päivänä.

    [ **Kalenterin avattavasta** ](#calendar-drop-down) osion tässä ohjeaiheessa kerrotaan tarkemmin muuttujia.

## <a name="previous-month-chevron"></a>Edellinen kuukausi kaksoisnuolikuvake

![iconPrevMonth ohjausobjekti](media/calendar-screen/calendar-back.png)

- Ominaisuus: **OnSelect**<br>Arvo: Neljä **määrittää** Funktiot ja **Jos** funktion, joka näyttää edellisen kuukauden kalenterin valikoimassa:

    ```powerapps-dot
    Set( _firstDayOfMonth, DateAdd( _firstDayOfMonth, -1, Months ) );
    Set( _firstDayInView, 
        DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days )
    );
    Set( _lastDayOfMonth, DateAdd(DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) );
    If( _minDate > _firstDayOfMonth,
        Collect( MyCalendarEvents,
            'Office365'.GetEventsCalendarViewV2( _myCalendar.Name,
                Text( _firstDayInView, UTC ), 
                Text( DateAdd( _minDate, -1, Days ), UTC )
            ).value
        );
        Set( _minDate, _firstDayInView )
    )
    ```

    > [!NOTE]
    > Määrityksiä  **\_firstDayOfMonth**,  **\_firstDayInView**, ja  **\_lastDayOfMonth** ovat lähes samat kuin - [kalenterin avattavasta](#calendar-drop-down) tämän ohjeaiheen osan.

    Edellä oleva koodi kolme ensimmäistä riviä suoritetaan aina, kun käyttäjä valitsee nuolenkärjen edellisen kuukauden. Koodin määrittää muuttujia, jotka tarvitaan oikea kalenterinäkymä näyttämiseen. Jäljellä oleva koodi suoritetaan vain, jos käyttäjä ei ole valittu aiemmin tässä kuussa valittuun kalenteriin.

    Jos tämä on tapauksessa  **\_minDate** on ensimmäinen päivä, joka tulee näkyviin, kun edellisen kuukauden näyttää. Ennen kuin käyttäjä valitsee kuvakkeen,  **\_minDate** on pienin mahdollinen arvo kuluvan kuukauden 23. (Kun maaliskuun 1 on lauantaina,  **\_firstDayInView** maaliskuuta on helmikuun 23.) Jos käyttäjä ei ole valittuna, tässä kuussa  **\_minDate** on suurempi kuin uusi  **\_firstDayOfMonth**, ja **Jos** funktio palauttaa **true**. Koodi, suoritukset ja kokoelma ja muuttuja päivitetään:

    - **MyCalendarEvents** hakee kanssa valitun kalenterin tapahtumat [Office365.GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) toiminto. Päivämääräalue on välillä  **\_firstDayInView** päivämäärä ja  **\_minDate** – 1. Koska **MyCalendarEvents** sisältää jo tapahtumat  **\_minDate** päivämäärän 1 on vähennetty päivämäärän tämän uuden päivämäärävälin suurimman arvon.

    - **\_minDate** asetetaan nykyisen  **\_firstDayInView** koska tämä on ensimmäinen päivämäärä, jolle on noudettu tapahtumia. Jos käyttäjä palaa tämä päivämäärä edellisenä kuukautena, chevron valitsemalla **Jos** funktio palauttaa **false**; koodi ei toimi, koska tämän näkymän tapahtumat ovat jo välimuistiin  **MyCalendarEvents**.

## <a name="next-month-chevron"></a>Seuraavan kuukauden kaksoisnuolikuvake

![iconNextMonth ohjausobjekti](media/calendar-screen/calendar-forward.png)

- Ominaisuus: **OnSelect**<br>
    Arvo: Neljä **määrittää** Funktiot ja **Jos** funktion, joka näyttää seuraavan kuukauden kalenterin valikoimassa:

    ```powerapps-dot
    Set( _firstDayOfMonth, DateAdd( _firstDayOfMonth, 1, Months ) );
    Set( _firstDayInView, 
        DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days ) );
    Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) );
    If( _maxDate < _lastDayOfMonth,
        Collect( MyCalendarEvents, 
            'Office365'.GetEventsCalendarViewV2( _myCalendar.Name, 
                Text( DateAdd( _maxDate, 1, Days ), UTC ), 
                DateAdd( _firstDayInView, 40, Days )
            ).value
        );
        Set( _maxDate, DateAdd( _firstDayInView, 40, Days) )    
    )
    ```

    > [!NOTE]
    > Määrityksiä  **\_firstDayOfMonth**,  **\_firstDayInView**, ja  **\_lastDayOfMonth** ovat lähes samat kuin - [kalenterin avattavasta](#calendar-drop-down) tämän ohjeaiheen osan.

    Kolme ensimmäistä riviä edellä oleva koodi, joka suoritetaan, kun käyttäjä valitsee nuolenkärjen seuraavan kuukauden, määritä muuttujia, jotka tarvitaan oikea kalenterinäkymä näyttämiseen. Jäljellä oleva koodi suoritetaan vain, jos käyttäjä ei ole valittu aiemmin tässä kuussa valittuun kalenteriin.

    Tässä tapauksessa  **\_maxDate** viimeinen päivä, joka tulee näkyviin, kun edellisen kuukauden näyttää. Ennen kuin käyttäjä valitsee seuraavan kuukauden, chevron  **\_maxDate** on kuukautena 13th suurin mahdollinen arvo. (1. helmikuuta on käytössä muita-karkausvuosi sunnuntai, kun  **\_maxDate** on maaliskuun 13, joka on  **\_firstDayInView** + 40 päivää.) Jos käyttäjä ei ole valittuna, tässä kuussa  **\_maxDate** on suurempi kuin uusi  **\_lastDayOfMonth**, ja **Jos** funktio Palauttaa **true**. Koodi, suoritukset ja kokoelma ja muuttuja päivitetään:

    - **MyCalendarEvents** hakee kanssa valitun kalenterin tapahtumat [Office365.GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) toiminto. Päivämääräalue on  **\_maxDate** + 1 päivä ja  **\_firstDayInView** + 40 päivää. Koska **MyCalendarEvents** sisältää jo tapahtumat  **\_minDate** päivämäärän 1 lisätään tämän päivämäärän tämän uuden päivämäärävälin pienimmän arvon. **\_firstDayInView** + 40 on kaava  **\_maxDate**, joten toisen päivämäärän välillä on vain uusi  **\_maxDate**.

    - **\_maxDate** asetetaan  **\_firstDayInView** + 40 päivän viimeisen päivän aikana, koska tapahtumille, mikä on noudettu. Jos käyttäjä palaa tämä päivämäärä seuraavan kuukauden, chevron valitsemalla **Jos** funktio palauttaa **false**; koodi ei toimi, koska tämän näkymän tapahtumat ovat jo välimuistiin  **MyCalendarEvents**.

## <a name="calendar-gallery"></a>Kalenterin valikoima

![MonthDayGallery ohjausobjekti](media/calendar-screen/calendar-month-gall.png)

- Ominaisuus: **Kohteet**<br>
    Arvo: `[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,
    20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41]`
  
  0-41 joukko käytetään kalenterin valikoima kohteille, koska huonointa mahdollista tilannetta, Kalenteri-näkymässä on 42 koko päivän näyttämiseen. Näin tapahtuu, kun lauantaina toteutuu kuukauden ensimmäisen ja viimeisen kuukauden sunnuntai käyttöön. Tässä tapauksessa kalenterin näytetään kuuden kuukauden ensimmäisen sisältävän rivin edellisen kuukauden päivän ajan ja kuusi seuraavan kuukauden-rivillä, joka sisältää kuukauden viimeisen päivän ajan. Tämä on 42 yksilöivät arvot, joiden 30 ovat valitun kuukauden.

- Ominaisuus: **WrapCount**<br>
    Arvo: `7`

  Tämä arvo vastaa seitsemän päivää viikossa.

### <a name="title-control-in-the-calendar-gallery"></a>Kalenterin valikoiman ohjausobjektin otsikko

![MonthDayGallery otsikko-ohjausobjekti](media/calendar-screen/calendar-month-text.png)

- Ominaisuus: **Teksti**<br>
    Arvo: `Day( DateAdd( _firstDayInView, ThisItem.Value, Days ) )`

    Peruuta,  **\_firstDayInView** on määritetty (**\_firstDayOfMonth** -sen weekday-arvo) + 1. Tapaamiset  **\_firstDayInView** on aina sunnuntai, ja  **\_firstDayOfMonth** on aina ensimmäinen rivi **MonthDayGallery**. Nämä kaksi faktaa vuoksi  **\_firstDayInView** on aina ensimmäiselle solua **MonthDayGallery**. **ThisItem.Value** on kyseisen solun **MonthDayGallery** kohteen ominaisuuden. Siis ottaen  **\_firstDayInView** lähtökohtana, kunkin solun näyttää lisäyksen-  **\_firstDayInView** + sen vastaavan solun arvo.

- Ominaisuus: **Täyttö**<br>
    Arvo: Yksi **Jos** funktio:

    ```powerapps-dot
    If( DateAdd( _firstDayInView, ThisItem.Value ) = Today() && 
                DateAdd( _firstDayInView, ThisItem.Value ) = _dateSelected, 
            RGBA( 0, 0, 0, 0 ),
        DateAdd( _firstDayInView, ThisItem.Value) = Today(), 
            ColorFade( Subcircle.Fill, 0.67 ),
        Abs( Title.Text - ThisItem.Value) > 10,
            RGBA( 200, 200, 200, 0.3 ),
        RGBA( 0, 0, 0, 0 )
    )
    ```

  Kuvatulla tavalla kuvaus **tekstin** ominaisuutta, `DateAdd(_firstDayInView, ThisItem.Value)` edustaa päivän visible-soluun. Ottaen huomioon edellisen koodin suorittaa nämä vertailut:
  1. Jos solun arvo on päivämäärä ja solun vastaa  **\_dateSelected**, älä anna täyttö arvo.
  1. Jos solun arvo on päivämäärä, mutta ei vastaa  **\_dateSelected**, anna **ColorFade** täyttö.
  1. Viimeisin vertailu ei ole yhtä Tyhjennä. Vertailu todellinen tekstiarvo solun ja arvo (luku, Näytä) ja kohteen numero solun on on.<br>

      Paremmin ymmärtää tämän, harkitse syyskuun 2018, kuukauden, joka alkaa lauantaina ja sunnuntai päättyy. Tässä tapauksessa, esiin tulee kautta 31 elokuun ja 1 syyskuuta 26th ensimmäisellä rivillä ja `Abs(Title.Text - ThisItem.Value) = 26` kunnes syyskuun 1. Sitten `Abs(Title.Text - ThisItem.Value) = 5`. Se säilyy 5 kunnes kalenterissa, joka näyttää – 6. syyskuuta 30 ja 1. lokakuuta viimeinen rivi. Kyseisessä `Abs(Title.Text - ThisItem.Value)` edelleen on 5 syyskuuta 30, mutta on 35 lokakuuta päivämäärät.<br>

      Tämä on mallia: Näytetään edellisen kuukauden päivän `Abs(Title.Text - ThisItem.Value)` aina sama kuin `Title.Text` arvon ensimmäisen päivän näytössä. Näytetään seuraavan kuukauden, päivän `Abs(Title.Text - ThisItem.Value)` aina sama kuin **MonthDayGallery** kohteen arvo on 1 (Tässä tapauksessa 1. lokakuuta) kuukauden ensimmäiseen. Ja mikä tärkeintä, valittuna kuukauden päivinä `Abs(Title.Text - ThisItem.Value)` myös aina yhtä suuri kuin 1 kuukauden ensimmäisen kohteen arvo ja koskaan ylittää 5 edellisen esimerkin mukaisesti. Se on täysin kelvollinen kirjoittaa kaavaa, sillä `Abs(Title.Text - ThisItem.Value) > 5`.

      Tämä lauseke tarkistaa, onko date-arvon valittuna kuukauden ulkopuolella. Jos näin on, **Täytä** on osittain läpinäkymättömiä harmaa.

    > [!NOTE]
    > Voit tarkistaa viimeisen vertailu kelpoisuuden itse lisäämällä **nimen** ohjausobjektin valikoiman ja asetus sen **tekstin** ominaisuudeksi tämä arvo:<br>`Abs(Title.Text - ThisItem.Value)`.

- Ominaisuus: **Näkyvissä**<br>
    Arvo:

    ```powerapps-dot
    !(
        DateAdd( _firstDayInView, ThisItem.Value, Days ) - 
            Weekday( DateAdd( _firstDayInView, ThisItem.Value,Days ) ) + 1 
        > _lastDayOfMonth
    )
    ```

    Edellisen lauseke tarkistaa, onko solun rivillä, jossa ei ole valittuna kuukauden päivän tapahtuu. Peruuta, että kaikki päivän päivämäärä sen arvosta viikonpäivä arvojen ja lisäämällä 1 aina palauttaa ensimmäisen kohteen rivillä kyseisen päivän sijaitsee. Jotta tämä lauseke tarkistaa, onko rivillä ensimmäisenä voi tarkastella kuukauden viimeisen päivän jälkeen. Jos näin on, se ei näy, koska koko rivillä on seuraavia kuukauden päivän.

- Ominaisuus: **OnSelect**<br>
    Arvo: A **määrittää** funktion, joka määrittää  **\_dateSelected** muuttujan valitun solun päivämäärä:

    ```powerapps-dot
    Set( _dateSelected, DateAdd( _firstDayInView, ThisItem.Value, Days ) )
    ```

### <a name="circle-control-in-the-calendar-gallery"></a>Ympyrä valikoiman ohjausobjektia, kalenteri

![MonthDayGallery ympyrä-ohjausobjekti](media/calendar-screen/calendar-month-event.png)

- Ominaisuus: **Näkyvissä**<br>
    Arvo: Kaava, joka määrittää, voiko tapahtumat ajoitetaan valitun päivämäärän ja onko **Subcircle** ja **otsikko** ohjausobjektit näkyvät:

    ```powerapps-dot
    CountRows(
        Filter( MyCalendarEvents, 
            DateValue( Text( Start ) ) = DateAdd( _firstDayInView, ThisItem.Value, Days )
        )
    ) > 0 && !Subcircle.Visible && Title.Visible
    ```

    **Ympyrä** ohjausobjekti näkyy vain jos **Aloita** kenttä tapauksessa vastaa kyseisen solun päivämäärä Jos **otsikko** ohjausobjekti on näkyvissä, ja, jos  **Subcircle** ohjausobjekti ei ole näkyvissä. Toisin sanoen tämä ohjausobjekti näkyy, kun vähintään yksi tapahtuma ilmenee tämän päivän ja tämän päivän ei ole valittuna. Jos se on valittuna, kyseisen päivän tapahtumat näkyvät **CalendarEventsGallery** ohjausobjektin.

### <a name="subcircle-control-in-the-calendar-gallery"></a>Subcircle valikoiman ohjausobjektia, kalenteri

![MonthDayGallery Subcircle ohjausobjekti](media/calendar-screen/calendar-month-selected.png)

- Ominaisuus: **Näkyvissä**<br>
    Arvo:

    ```powerapps-dot
    DateAdd( _firstDayInView, ThisItem.Value ) = _dateSelected && Title.Visible
    ```

  **Subcircle** ohjausobjekti on näkyvissä, kun  **\_dateSelected** vastaa solun, Date ja **otsikko** ohjausobjekti on näkyvissä. Toisin sanoen tämän ohjausobjektin tulee näkyviin, kun solu on tällä hetkellä valittu päivämäärä.

## <a name="events-gallery"></a>Tapahtumat valikoima

![CalendarEventsGallery ohjausobjekti](media/calendar-screen/calendar-events-gall.png)

- Ominaisuus: **Kohteet**<br>
    Arvo: Kaava, joka lajittelee ja suodattaa valikoiman tapahtumat:

    ```powerapps-dot
    SortByColumns(
        Filter( MyCalendarEvents,
            Text( Start, DateTimeFormat.ShortDate ) = Text( _dateSelected, DateTimeFormat.ShortDate )
        ),
        "Start"
    )
    ```

   **MyCalendarEvents** kokoelma sisältää kaikki tapahtumat väliltä  **\_minDate** ja  **\_maxDate**. Jotta voit näyttää vain valitun päivämäärän tapahtumat, suodatin on käytössä **MyCalendarEvents** näyttämään tapahtumia, jotka on vastaa alkamispäivämäärä **\ _dateSelected**. Kohteet lajitellaan sitten niiden alkamis sijoittaminen järjestyksessä.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Lue lisätietoja tässä näytössä](./calendar-screen-overview.md)
- [Lue lisätietoja Office 365 Outlook-liittimellä powerappsissa](../connections/connection-office365-outlook.md)
- [Lue lisätietoja Office 365-käyttäjät-liittimellä powerappsissa](../connections/connection-office365-users.md)

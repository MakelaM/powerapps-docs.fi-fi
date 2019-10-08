---
title: Kangas sovellusten kalenteri näytön mallin viite tiedot | Microsoft Docs
description: Tietoja siitä, miten pohjaan liittyviä sovelluksia koskeva kalenteri näyttö malli toimii Powerappsissa.
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
ms.openlocfilehash: b9e5425244d819816fa05c4b780a6be092b0d22c
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995710"
ms.PowerAppsDecimalTransform: true
---
# <a name="reference-information-about-the-calendar-screen-template-for-canvas-apps"></a>Viite tietoja kangas sovellusten kalenteri näytön mallista

Powerappsin Canvas-sovelluksissa opit ymmärtämään, miten jokainen merkittävä kalenteri näytön malli vaikuttaa osaltaan näytön yleisiin oletus toimintoihin. Tämä Deep Dive esittelee toiminta kaavat ja muiden ominaisuuksien arvot, jotka määrittävät, miten ohjaus objekti reagoi käyttäjän syöttämiseen. Jos kyseessä on tämän näytön oletus toiminnon korkean tason keskustelu, tutustu [kalenteri näytön yleiskatsaukseen](calendar-screen-overview.md).

Tässä ohje aiheessa esitellään joitakin merkittäviä ohjaus objekteja ja selitetään lausekkeet tai kaavat, joille on määritetty eri ominaisuudet (kuten **kohteet** ja **onselect**):

- [Avattava kalenteri (dropdownCalendarSelection)](#calendar-drop-down)
- [Kalenteri kuvake (iconCalendar)](#calendar-icon)
- [Edellisen kuukauden Chevron-kuvake (Iconprempmonth)](#previous-month-chevron)
- [Seuraavan kuukauden Chevron (Iconnextomonth)](#next-month-chevron)
- [Kalenteri valikoima (MonthDayGallery) (+ aliohjausobjektit)](#calendar-gallery)
- [Tapahtuma valikoima (Calendarventsgallery)](#events-gallery)

## <a name="prerequisite"></a>Edellytys

Perehtyneisyys näyttöjen ja muiden ohjaus objektien lisäämiseen ja määrittämiseen [, kun luot sovelluksen Powerappsissa](../data-platform-create-app-scratch.md).

## <a name="calendar-drop-down"></a>Avattava kalenteri

![dropdownCalendarSelection-ohjaus objekti](media/calendar-screen/calendar-dropdown.png)

- Ominaisuuden **Kohteet**<br>
    Arvo: `Office365.CalendarGetTables().value`

    Tämä arvo on kytkentä toiminto, joka noutaa sovelluksen käyttäjän Outlook-kalenterit. Näet tämän toiminnon noutamat [arvot](https://docs.microsoft.com/connectors/office365/#entitylistresponse[table]) .

- Ominaisuuden **OnChange**<br>Arvo: `Select(dropdownCalendarSelection)`

    Kun käyttäjä valitsee luettelosta vaihto ehdon, ohjaus objektin **onselect** -ominaisuuden toiminto suoritetaan.

- Ominaisuuden **OnSelect**<br>
    Arvo **IF** -funktio, joka näkyy seuraavassa koodi lohkossa, ja useita lisä funktioita, jotka näkyvät koodi lohkossa sen jälkeen.

   Tämä osa kaavaa suoritetaan vain ensimmäisellä kerralla, kun käyttäjä valitsee vaihto ehdon avattavasta luettelo ruudusta sovelluksen avaamisen jälkeen:

    ```powerapps-comma
    If( IsBlank( _userDomain );
        UpdateContext( {_showLoading: true} );;
        Set( _userDomain; Right( User().Email; Len( User().Email ) - Find( "@"; User().Email ) ) );;
        Set( _dateSelected; Today() );;
        Set( _firstDayOfMonth; DateAdd( Today(); 1 - Day( Today() ); Days ) );;  
        Set( _firstDayInView; DateAdd( _firstDayOfMonth; -(Weekday(_firstDayOfMonth) - 1); Days ) );;
        Set( _lastDayOfMonth; DateAdd( DateAdd( _firstDayOfMonth; 1; Months ); -1; Days ) )  
    );;
    ```

    Edeltävä koodi määrittää seuraavat muuttujat:
    
  - **\_userDomain**: Sovelluksen käyttäjän yrityksen toimi alue, joka näkyy käyttäjän Sähkö posti osoitteessa.
  - **\_dateSelected**: Kuluvan päivän päivä määrä (Oletus arvon mukaan). Kalenteri valikoima korostaa tätä päivä määrää, ja tapahtuma valikoima esittää kyseiseen päivä määrään ajoitetut tapahtumat.
  - **\_Firstodayofmonth**: Nykyisen kuukauden ensimmäinen päivä. Koska `(Today + (1 - Today)) = Today - Today + 1 = 1`, tämä **DateAdd** -funktio palauttaa aina kuukauden ensimmäisen päivän.
  - **\_Firndayingview**: Ensimmäinen päivä, jonka kalenteri valikoima voi näyttää. Tämä arvo ei ole sama kuin kuukauden ensimmäinen päivä, ellei kuukausi alkaa sunnuntaina. Jos haluat estää edellisen kuukauden koko viikon, **\_Firndayinview** -arvo on `_firstDayOfMonth - Weekday(_firstDayOfMonth) + 1`.
  - **\_lastDayOfMonth**: Nykyisen kuukauden viimeisenä päivänä, joka on sama kuin seuraavan kuukauden ensimmäisenä päivänä, josta vähennetään yksi päivä.

   **IF** -funktion jälkeiset Funktiot suoritetaan aina, kun käyttäjä valitsee vaihto ehdon avattavasta Kalenteri-valikosta (ei vain ensimmäisellä kerralla, kun käyttäjä avaa sovelluksen):

    ```powerapps-comma
    Set( _calendarVisible; false );;
    UpdateContext( {_showLoading: true} );;
    Set( _myCalendar; dropdownCalendarSelection2.Selected );;
    Set( _minDate; 
        DateAdd( _firstDayOfMonth; -(Weekday( _firstDayOfMonth ) - 2 + 1); Days )
    );;
    Set(_maxDate; 
        DateAdd(
            DateAdd( _firstDayOfMonth; -(Weekday( _firstDayOfMonth ) - 2 + 1); Days ); 
            40; 
            Days
        )
    );;
    ClearCollect( MyCalendarEvents; 
        'Office365'.GetEventsCalendarViewV2( _myCalendar.Name; 
            Text( _minDate; UTC ); 
            Text( _maxDate; UTC )
        ).value
    );;
    UpdateContext( {_showLoading: false} );;
    Set( _calendarVisible; true )
    ```

    Edellä oleva koodi määrittää nämä muuttujat ja yhden kokoelman:

    - **\_calendarVisible**: Valitse **Epätosi** , jotta kalenteria ei näytetä, kun uusi valinta ladataan.
    - **\_showLoading**: Valitse **tosi** , jotta lataus ilmaisimet tulevat näkyviin, kun uutta valintaa ladataan.
    - **\_myCalendar**: Valitse **avattavasta kalenteri-** ohjaus objektista nykyinen arvo, jotta oikean kalenterin tapahtumat noudetaan.
    - **\_minDate**: Arvoksi on määritetty sama arvo kuin **\_Firndayingview**. Tämä muuttuja määrittää, mitkä tapahtumat on jo Noudettu Outlookista ja väli muistissa sovelluksessa.
    - **\_maxDate**: Valitse kalenterin viimeiseen katseltavaan päivään. Kaava on `_firstDayInView + 40`. Kalenterissa näkyy enintään 41 päivää, joten **\_maxDate-** muuttuja heijastaa aina viimeisintä katseltavaa päivää ja määrittää, mitkä tapahtumat on jo Noudettu Outlookista ja väli muistissa sovelluksessa.
    - **Mycalendarevents**: Valitse käyttäjän tapahtumien kokoelma valitusta kalenterista, joka vaihtelee **\_minDate** **\_maxdate**.
    - **\_showLoading**: Arvo on **false**; **\_calendarVisible-** arvo on **True** , kun kaikki muu on ladattu.

## <a name="calendar-icon"></a>Kalenteri kuvake

![iconCalendar-ohjaus objekti](media/calendar-screen/calendar-today-icon.png)

- Ominaisuuden **OnSelect**<br>
    Arvo Neljä toiminto **joukkoa** , jotka nollaamassa kalenteri valikoiman kuluvan päivän päivä määräksi:

    ```powerapps-comma
    Set( _dateSelected; Today() );;
    Set( _firstDayOfMonth; DateAdd( Today(); 1 - Day( Today() ); Days) );;
    Set( _firstDayInView; DateAdd(_firstDayOfMonth; -(Weekday( _firstDayOfMonth ) - 2 + 1); Days));;
    Set( _lastDayOfMonth; DateAdd( DateAdd( _firstDayOfMonth; 1; Months ); -1; Days ) )
    ```

    Edeltävä koodi palauttaa kaikki päivämäärä muuttujat, jotka ovat välttämättömiä asianmukaisen Kalenteri näkymän näyttämiseksi:

    - **\_dateSelected** on palautettu tähän päivään.
    - **\_Firstodayofmonth** palautetaan kuluvan kuukauden ensimmäisenä päivänä.
    - **\_Firndayingview** palautetaan ensimmäiseen päivään, joka on nähtävissä, kun kuluvan kuukauden kuukausi on valittuna.
    - **\_lastDayOfMonth** palautetaan kuluvan kuukauden viimeisenä päivänä.

    Tämän ohje aiheen [**avattava kalenteri-** ](#calendar-drop-down) osio kertoo Nämä muuttujat yksityiskohtaisemmin.

## <a name="previous-month-chevron"></a>Edellisen kuukauden Chevron

![Iconprevitkk-ohjaus objekti](media/calendar-screen/calendar-back.png)

- Ominaisuuden **OnSelect**<br>Arvo Neljä **joukkoa** funktioita ja **IF** -funktio, jotka näyttävät edellisen kuukauden kalenteri valikoimassa:

    ```powerapps-comma
    Set( _firstDayOfMonth; DateAdd( _firstDayOfMonth; -1; Months ) );;
    Set( _firstDayInView; 
        DateAdd( _firstDayOfMonth; -(Weekday( _firstDayOfMonth ) - 2 + 1); Days )
    );;
    Set( _lastDayOfMonth; DateAdd(DateAdd( _firstDayOfMonth; 1; Months ); -1; Days ) );;
    If( _minDate > _firstDayOfMonth;
        Collect( MyCalendarEvents;
            'Office365'.GetEventsCalendarViewV2( _myCalendar.Name;
                Text( _firstDayInView; UTC ); 
                Text( DateAdd( _minDate; -1; Days ); UTC )
            ).value
        );;
        Set( _minDate; _firstDayInView )
    )
    ```

    > [!NOTE]
    > **@No__t-1Firstodayofmonth**-, **\_Firstodayingview**-ja **\_lastdayofmonth** -määritelmät ovat lähes samanlaiset kuin tämän ohje aiheen [kalenterin avattavassa](#calendar-drop-down) osassa.

    Edellisen koodi ajon kolme ensimmäistä riviä, kun käyttäjä valitsee edellisen kuukauden nuolen kärki. Koodi määrittää muuttujat, jotka ovat välttämättömiä asianmukaisen Kalenteri näkymän näyttämiseksi. Jäljelle jäävä koodi suoritetaan vain, jos käyttäjä ei ole aiemmin valinnut tätä kuukautta valitulle kalenterille.

    Jos näin on, **\_minDate** on ensimmäinen päivä, joka näkyy, kun edellinen kuukausi näytetään. Ennen kuin käyttäjä valitsee kuvakkeen, **\_minDate-** arvo on pienin mahdollinen nykyisen kuukauden 23. (Kun 1. maaliskuuta kuuluu lauantaina, **\_Firndayingview** for March on 23. helmi kuuta.) Tämä tarkoittaa sitä, että jos käyttäjä ei ole vielä valinnut tätä kuukautta, **\_minDate** on suurempi kuin uusi **\_Firstoddayofmonth**, ja **IF** -funktio palauttaa arvon **True**. Koodi suoritetaan, ja kokoelma ja muuttuja päivitetään:

    - **Mycalendarevents** noutaa tapahtumia valitusta kalenterista [office365. GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) -toiminnolla. Päivämäärä alue on **\_Firmdayingview** -päivä määrän ja **\_mindate** -1 välillä. Koska **Mycalendarevents** sisältää jo tapahtumia **\_mindate-** päivä määränä, 1 vähennetään kyseisestä päivästä tämän uuden päivämäärä alueen enimmäisarvolle.

    - **\_minDate** on asetettu nykyiseen **\_Firsdayingview** , koska tämä on ensimmäinen päivä määrä, jolle tapahtumat on noudettu. Jos käyttäjä palaa tähän päivä määrään valitsemalla edellisen kuukauden nuolen kärki, **IF** -funktio palauttaa arvon **false**; koodia ei suoriteta, koska tämän näkymän tapahtumat on jo tallennettu väli muistiin **Mycalendarevents**-kohteessa.

## <a name="next-month-chevron"></a>Seuraavan kuukauden Chevron

![Iconnexta month-ohjaus objekti](media/calendar-screen/calendar-forward.png)

- Ominaisuuden **OnSelect**<br>
    Arvo Neljä **joukkoa** funktioita ja **IF** -funktio, jotka näyttävät kalenteri valikoiman seuraavan kuukauden:

    ```powerapps-comma
    Set( _firstDayOfMonth; DateAdd( _firstDayOfMonth; 1; Months ) );;
    Set( _firstDayInView; 
        DateAdd( _firstDayOfMonth; -(Weekday( _firstDayOfMonth ) - 2 + 1); Days ) );;
    Set( _lastDayOfMonth; DateAdd( DateAdd( _firstDayOfMonth; 1; Months ); -1; Days ) );;
    If( _maxDate < _lastDayOfMonth;
        Collect( MyCalendarEvents; 
            'Office365'.GetEventsCalendarViewV2( _myCalendar.Name; 
                Text( DateAdd( _maxDate; 1; Days ); UTC ); 
                DateAdd( _firstDayInView; 40; Days )
            ).value
        );;
        Set( _maxDate; DateAdd( _firstDayInView; 40; Days) )    
    )
    ```

    > [!NOTE]
    > **@No__t-1Firstodayofmonth**-, **\_Firstodayingview**-ja **\_lastdayofmonth** -määritelmät ovat lähes samanlaiset kuin tämän ohje aiheen [kalenterin avattavassa](#calendar-drop-down) osassa.

    Edellisen koodin kolme ensimmäistä riviä, jotka suoritetaan, kun käyttäjä valitsee seuraavan kuukauden nuolen kärki, määrittää muuttujat, jotka ovat välttämättömiä asianmukaisen Kalenteri näkymän näyttämiseksi. Jäljelle jäävä koodi suoritetaan vain, jos käyttäjä ei ole aiemmin valinnut tätä kuukautta valitulle kalenterille.

    Tässä tapa uksessa **\_maxDate** on viimeinen päivä, joka näkyy, kun edellinen kuukausi näytetään. Ennen kuin käyttäjä valitsee seuraavan kuukauden nuolen kärki, **\_maxDate** on suurin mahdollinen arvo seuraavan kuukauden 13. (Kun 1. helmi kuuta osuu muuhun kuin karkaus vuoteen sunnuntaina, **\_maxDate** on 13. maaliskuuta, joka on **\_Firndayinsview** + 40 päivää.) Tämä tarkoittaa sitä, että jos käyttäjä ei ole vielä valinnut tätä kuukautta, **\_maxDate** on suurempi kuin uusi **\_lastDayOfMonth**, ja **IF** -funktio palauttaa arvon **True**. Koodi suoritetaan, ja kokoelma ja muuttuja päivitetään:

    - **Mycalendarevents** noutaa tapahtumia valitusta kalenterista [office365. GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) -toiminnolla. Päivämäärä alue on välillä **\_maxDate** + 1 päivä ja **\_Firndayingview** + 40 päivää. Koska **Mycalendarevents** sisältää jo tapahtumia **\_mindate-** päivä määrä, 1 lisätään kyseiseen päivä määrään tämän uuden päivämäärä alueen vähimmäisarvolle. **\_Firndayingview** + 40 on **\_maxdate**-kaava, joten alueen toinen päivä määrä on vain uusi **\_maxdate**.

    - **\_maxDate** -arvoksi on asetettu **\_Firndayinsview** + 40 päivää, koska tämä on viimeinen päivä, jolle tapahtumat on noudettu. Jos käyttäjä palaa tähän päivä määrään valitsemalla seuraavan kuukauden nuolen kärki, **IF** -funktio palauttaa arvon **false**; koodia ei suoriteta, koska tämän näkymän tapahtumat on jo tallennettu väli muistiin **Mycalendarevents**-kohteessa.

## <a name="calendar-gallery"></a>Kalenteri valikoima

![Kuukauden päivä valikoima-ohjaus objekti](media/calendar-screen/calendar-month-gall.png)

- Ominaisuuden **Kohteet**<br>
    Arvo: `[0;1;2;3;4;5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;
    20;21;22;23;24;25;26;27;28;29;30;31;32;33;34;35;36;37;38;39;40;41]`
  
  Kohteen 0 – 41 joukkoa käytetään kalenteri valikoiman kohteissa, koska pahimmassa skenaariossa Kalenteri näkymän on näytettävä 42 koko naista päivää. Tämä tapahtuu, kun kuukauden ensimmäinen kuukausi on lauantai ja kuukauden viimeinen tapahtuu sunnuntaina. Tässä tapa uksessa kalenterissa on kuusi päivää edellisestä kuukaudesta, joka sisältää kuukauden ensimmäisen kuukauden, ja kuusi päivää seuraavasta kuukaudesta kuukauden viimeisen kuukauden rivillä. Tämä on 42 ainutlaatuista arvoa, joista 30 on valittua kuukautta varten.

- Ominaisuuden **WrapCount**<br>
    Arvo: `7`

  Tämä arvo vastaa seitsemän päivän viikkoa.

### <a name="title-control-in-the-calendar-gallery"></a>Otsikko-ohjaus objekti kalenteri valikoimassa

![Kuukauden päivä valikoiman otsikko-ohjaus objekti](media/calendar-screen/calendar-month-text.png)

- Ominaisuuden **Teksti**<br>
    Arvo: `Day( DateAdd( _firstDayInView; ThisItem.Value; Days ) )`

    Muista, että **\_Firstodayinview** on määritetty muodossa ( **\_Firstodayofmonth** – sen viikon päivä arvo) + 1. Tämä kertoo, että **\_Firstodayingview** on aina sunnuntai, ja **\_Firstodayofmonth** on aina kuukausi **valikoiman**ensimmäisellä rivillä. Näiden kahden faktojen vuoksi **\_Firndayingview** on aina Montdaygallery-kohteenensimmäisessä solussa. **Thisitem. Value** on kyseisen solun numero **Monthdaygallery** -kohteen ominaisuudessa. Kun aloitat **\_firndayingview-** kohteen aloitus pisteenä, jokainen solu näyttää **\_firmdayingview** +-kohteen lisäyksen vastaavan solun arvon.

- Ominaisuuden **Täyttö**<br>
    Arvo One **IF** -funktiolla:

    ```powerapps-comma
    If( DateAdd( _firstDayInView; ThisItem.Value ) = Today() && 
                DateAdd( _firstDayInView; ThisItem.Value ) = _dateSelected; 
            RGBA( 0; 0; 0; 0 );
        DateAdd( _firstDayInView; ThisItem.Value) = Today(); 
            ColorFade( Subcircle.Fill; 0,67 );
        Abs( Title.Text - ThisItem.Value) > 10;
            RGBA( 200; 200; 200; 0,3 );
        RGBA( 0; 0; 0; 0 )
    )
    ```

  Kuten **teksti** -ominaisuuden kuva uksessa on kerrottu, `DateAdd(_firstDayInView; ThisItem.Value)` edustaa näkyvää solua. Kun tämä otetaan huomioon, edeltävä koodi suorittaa nämä vertailut:
  1. Jos solun arvo on kuluvan päivän päivä määrä ja tämä solu vastaa **\_dateSelected-** arvoa, älä anna täyttö arvoa.
  1. Jos solun arvo on kuluvan päivän päivä määrä, mutta ei vastaa **\_dateSelected-** arvoa, anna **colorfade** -täyttö.
  1. Viimeinen vertailu ei ole yhtä selkeä. Siinä verrataan solun todellista teksti arvoa ja solu kohteen arvoa (näytössä oleva numero ja kohteen numero).<br>

      Jos haluat ymmärtää tämän paremmin, harkitse syyskuuta 2018, kuukausi, joka alkaa lauantaina ja päättyy sunnuntaina. Tässä tapa uksessa kalenteri näyttää 26. – 31. elokuuta ja syyskuun 1. ensimmäisen rivin ja `Abs(Title.Text - ThisItem.Value) = 26` – 1. syyskuuta. Sitten `Abs(Title.Text - ThisItem.Value) = 5`. Se pysyy 5 päivään, kunnes kalenterissa on viimeinen rivi, joka näyttää 30. syyskuuta ja 1. loka kuuta – kuudes. Tässä `Abs(Title.Text - ThisItem.Value)` on edelleen 5 30. syyskuuta, mutta se on 35 loka kuun päivä määrille.<br>

      Tämä on seuraava: Edellisen kuukauden päivien osalta `Abs(Title.Text - ThisItem.Value)` on aina yhtä suuri kuin ensimmäisen päivän `Title.Text`-arvo. Kun päivät näytetään seuraavassa kuussa, `Abs(Title.Text - ThisItem.Value)` on aina sama kuin kuukauden ensimmäisen solun kuukausi **valikoiman** kohteen arvo (tässä tapa uksessa 1. loka kuuta) vähennettynä yhdellä. Ja mikä tärkeintä, valittuna kuukautena näkyvissä päivinä `Abs(Title.Text - ThisItem.Value)` on myös aina sama kuin kuukauden ensimmäisen kohteen arvo vähennettynä arvolla 1 ja ei koskaan ylitä viittä, kuten edellisessä esimerkissä näytetään. On siis täysin perusteltua kirjoittaa kaava `Abs(Title.Text - ThisItem.Value) > 5`.

      Tämä lauseke tarkistaa, onko päivämäärä arvo valittuna olevan kuukauden ulkopuolella. Jos se on, **täyttö** on osittain läpinäkymätön harmaa.

    > [!NOTE]
    > Voit tarkistaa tämän viimeisimmän vertailun kelvollisuuden lisäämällä **Selite** -ohjaus objektin valikoimaan ja määrittämällä sen **Text** -ominaisuudeksi tämän arvon:<br>`Abs(Title.Text - ThisItem.Value)`.

- Ominaisuuden **Näkyvissä**<br>
    Arvo

    ```powerapps-comma
    !(
        DateAdd( _firstDayInView; ThisItem.Value; Days ) - 
            Weekday( DateAdd( _firstDayInView; ThisItem.Value;Days ) ) + 1 
        > _lastDayOfMonth
    )
    ```

    Edeltävä lauseke tarkistaa, onko solu rivillä, jossa ei ole valitun kuukauden päiviä. Muista, että jos minkä tahansa päivän päivä määrä-arvon ja arvon lisääminen 1-arvo vähennetään, ensimmäinen kohde palautetaan aina sen rivin ensimmäiseen kohteeseen, jossa päivä asuu. Tämä lauseke tarkistaa, onko rivin ensimmäinen päivä tarkasteltavissa olevan kuukauden viimeisenä päivänä. Jos se on, sitä ei näytetä, koska koko rivi sisältää seuraavan kuukauden päivät.

- Ominaisuuden **OnSelect**<br>
    Arvo **Set** -funktiolla, joka asettaa **\_dateselected-** muuttujan valitun solun päivä määräksi:

    ```powerapps-comma
    Set( _dateSelected; DateAdd( _firstDayInView; ThisItem.Value; Days ) )
    ```

### <a name="circle-control-in-the-calendar-gallery"></a>Ympyrä ohjaus objekti kalenteri valikoimassa

![Kuukaundaygallery-ympyrän ohjaus objekti](media/calendar-screen/calendar-month-event.png)

- Ominaisuuden **Näkyvissä**<br>
    Arvo Kaava, joka määrittää, ajoitetaanko valitun päivä määrän tapahtumat ja onko **Aliympyrä** -ja **otsikko** -ohjaus objekti näkyvissä:

    ```powerapps-comma
    CountRows(
        Filter( MyCalendarEvents; 
            DateValue( Text( Start ) ) = DateAdd( _firstDayInView; ThisItem.Value; Days )
        )
    ) > 0 && !Subcircle.Visible && Title.Visible
    ```

    **Ympyrä** -ohjaus objekti on näkyvissä, jos minkä tahansa tapahtuman **alku** -kenttä vastaa kyseisen solun päivä määrää, jos **otsikko** -ohjaus objekti on näkyvissä ja jos **aliympyröohjausobjekti** ei ole näkyvissä. Tämä ohjaus objekti on siis näkyvissä, kun vähintään yksi tapahtuma toteutuu tänä päivänä, eikä tätä päivää ole valittu. Jos se on valittuna, kyseisen päivän tapahtumat näytetään **Calendarevensgallery** -ohjaus objektissa.

### <a name="subcircle-control-in-the-calendar-gallery"></a>Alcircle-ohjaus objekti kalenteri valikoimassa

![Kuukausi valikoiman Alcircle-ohjaus objekti](media/calendar-screen/calendar-month-selected.png)

- Ominaisuuden **Näkyvissä**<br>
    Arvo

    ```powerapps-comma
    DateAdd( _firstDayInView; ThisItem.Value ) = _dateSelected && Title.Visible
    ```

  **Aliympyröohjausobjekti** on näkyvissä, kun **\_dateselected** on sama kuin solun päivä määrä ja **otsikko** -ohjaus objekti on näkyvissä. Toisin sanoen tämä ohjaus objekti tulee näkyviin, kun solu on valittuna päivänä.

## <a name="events-gallery"></a>Tapahtuma valikoima

![Kalenteri-valikoima-ohjaus objekti](media/calendar-screen/calendar-events-gall.png)

- Ominaisuuden **Kohteet**<br>
    Arvo Kaava, joka lajittelee ja suodattaa tapahtuma valikoiman:

    ```powerapps-comma
    SortByColumns(
        Filter( MyCalendarEvents;
            Text( Start; DateTimeFormat.ShortDate ) = Text( _dateSelected; DateTimeFormat.ShortDate )
        );
        "Start"
    )
    ```

   **Mycalendarevents** -kokoelma sisältää kaikki tapahtumat **\_mindate** ja **\_maxdate**välillä. Jos haluat näyttää vain valitun päivä määrän tapahtumat, **Mycalendarevents** -kohteelle käytetään suodatinta, joka näyttää tapahtumat, joiden alkamis päivä on sama kuin kohteen **\ _dateselected**. Kohteet lajitellaan sitten niiden alkamis päivien mukaan, jotta ne voidaan sijoittaa järjestyksessä.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Lue lisä tietoja tästä näytöstä](./calendar-screen-overview.md)
- [Lue lisä tietoja Office 365 Outlook Connectorista Powerappsissa](../connections/connection-office365-outlook.md)
- [Lue lisä tietoja Office 365-käyttäjien liittimestä Powerappsissa](../connections/connection-office365-users.md)

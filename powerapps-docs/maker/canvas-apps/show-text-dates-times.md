---
title: Tekstin näyttäminen ja päivämäärän ja kellonajan muotoileminen | Microsoft Docs
description: Lisää ja muotoile päivämääriä ja kellonaikoja PowerAppsissa
documentationcenter: ''
author: AFTOwen
manager: kfile
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/16/2016
ms.author: anneta
ms.openlocfilehash: faa8db15596dc0da0d5b5638f5dd9c334517fc7c
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/03/2018
---
# <a name="show-text-and-format-dates-and-times-in-powerapps"></a>Lisää tekstiä ja muotoile päivämääriä ja kellonaikoja PowerAppsissa
Lisää päivämääriä ja kellonaikoja ja muotoile niitä niin, että ne näyttävät oikean määrän tietoja tai vastaavat sijaintiasi. Laske kahden päivämäärän välinen aika tai laske päivämäärä, joka on tietyn aikaeron verran ennen tai jälkeen määrittämääsi päivämäärää. Muunna päivämäärät erillisiin päivä-, kuukausi- tai vuosiarvoihin tai päin vastoin. Muunna ajat erillisiin tunti-, minuutti- ja sekuntiarvoihin tai päin vastoin.

Lisää esimerkiksi käyttäjien antamia tietoja pörssikursseista ja asiakastapaamisista, tietoja ulkoisista tietolähteistä tai tietoja toisesta PowerAppsissa luodusta sovelluksesta. Jos tiedot sisältävät ajan millisekunnin tarkkuudella, pyöristä ne yksinkertaisuuden vuoksi lähimpään minuuttiin. Laske, montako päivää on jäljellä ennen tärkeää hetkeä. Jos haluat ajoittaa asiakastapaamisia viiden päivän välein, laske nämä päivämäärät automaattisesti. Jos 10. toukokuuta 1985 on tallennettu niin, että päivä, kuukausi ja vuosi ovat eri kentissä, yhdistä ne yhdeksi arvoksi. Voit myös toimia päin vastoin ja muuttaa päivämäärän erillisiksi arvoiksi, jos sovelluksesi käsittelee niitä erikseen.

## <a name="prerequisites"></a>Edellytykset

* [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin [ja kirjaudu sitten sisään](https://web.powerapps.com) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.
* Luo sovellus tai avaa olemassa oleva sovellus PowerAppsissa.
* Lue, miten [ohjausobjekti määritetään](add-configure-controls.md) PowerAppsissa.

## <a name="show-text-in-a-label-control"></a>Näytä selite-ohjausobjektin teksti
Näytä teksti **[selite](controls/control-text-box.md)**-ohjausobjektissa määrittämällä sen **[Text](controls/properties-core.md)**-ominaisuuden arvo. Määritä tämä ominaisuus kirjoittamalla suoraan ohjausobjektiin tai kirjoittamalla lauseke kaavarivillä.

* Jos kirjoitat suoraan ohjausobjektiin, siinä näkyy täsmälleen, mitä kirjoitat.
* Jos kirjoitat lausekkeen kaavarivillä, ohjausobjekti näyttää lausekkeen tuloksen.

Seuraavassa on joitakin esimerkkejä.

1. Lisää **[selite](controls/control-text-box.md)**-ohjausobjekti, jonka nimi on **NäytäTeksti**, ja aseta sen **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**Now()**
   
    Jos tietokoneesi aluekohtaisiksi asetuksiksi on määritetty ”en-us”, nykyinen päivämäärä ja aika näkyvät seuraavassa muodossa:  <br>*mm/dd/yyyy hh:mm AM/PM*
   
    Jos tietokoneesi aluekohtaisiksi asetuksiksi on määritetty ”fr-fr”, nykyinen päivämäärä ja aika näkyvät seuraavassa muodossa:  <br>*dd/mm/yyyy hh:mm AM/PM*
2. Määritä **NäytäTeksti**-ohjausobjektin **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateDiff(Today(), DateValue("01/01/2020"))**
   
    ![Päivien määrä tämän päivän ja 1. tammikuuta 2020 välillä](./media/show-text-dates-times/date-diff-text.png)
   
    Ohjausobjekti näyttää tämän päivän ja 1. tammikuuta 2020 välisen päivien määrän käyttämällä seuraavia funktioita:
   
   * **DateDiff**, joka laskee kahden päivämäärän välisen päivien, neljännesvuosien tai vuosien määrän.
   * **Today**, joka laskee nykyisen päivän arvona.
   * **DateValue**, joka muuntaa lainausmerkeissä olevan merkkijonoliteraalin arvoksi, jota voidaan käyttää laskutoimitusten suorittamiseen.
3. Lisää **[tekstisyöte](controls/control-text-input.md)**- ohjausobjekti, jonka nimi on **Syntymäpv**, ja siirrä se **NäytäTeksti**-ohjausobjektin alapuolelle.

4. Anna **Syntymäpv**-ohjausobjektille syntymäkuukautesi ja -päiväsi (esimerkiksi **05/18**).

5. Määritä **NäytäTeksti**-ohjausobjektin **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateDiff(Today(), DateValue(Syntymäpv.Text))**
   
    ![Päivien määrä tämän päivän ja syntymäpäiväsi välillä](./media/show-text-dates-times/birth-diff.png)
   
    **NäytäTeksti** näyttää päivien määrän tämän päivän ja minkä tahansa kohdassa **Syntymäpv** antamasi päivämäärän välillä. Jos syntymäpäiväsi on jo ollut tänä vuonna, **NäytäTeksti** näyttää negatiivisen arvon.

## <a name="format-dates-and-times-by-using-datetimevalue"></a>Muotoile päivämääriä ja aikoja DateTimeValue-funktion avulla
Muunna päivämääriä ja aikoja tekstimerkkijonoista arvoiksi, joita voit muotoilla eri tavoin ja käyttää laskutoimituksissa. Määritä muoto käyttämällä valmiita ja mukautettuja asetuksia.

> [!NOTE]
> **[DateTimeValue](functions/function-datevalue-timevalue.md)**- ja **[DateValue](functions/function-datevalue-timevalue.md)**-funktiot voivat muuntaa päivämäärät mihin tahansa seuraavista arvoista:  
> 
> * KK/PP/VVVV  
> * PP/MM/YYYY  
> * PP Kuu VVVV  
> * Kuukausi PP, VVVV  
> 
> 

1. Lisää **[tekstisyöte](controls/control-text-input.md)**-ohjausobjekti, jonka nimi on **TuloPvmAika**, ja kirjoita päivämäärä ja aika tässä muodossa:
   <br>**5/10/85 6:15 AM**
2. Lisää **[selite](controls/control-text-box.md)**-ohjausobjekti, jonka nimi on **NäytäPvm**, ja aseta sen **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateTimeValue(TuloPvmAika.Text)**
   
    ![Muuttaa päivämäärän/ajan tekstistä arvoksi](./media/show-text-dates-times/date-value.png)
   
    **NäytäPvm** näyttää samat tiedot, jotka olet kirjoittanut, mutta muunnettuna tekstistä arvoksi ja eri tavalla muotoiltuna. Esimerkiksi vuosi näkyy nelinumeroisena kahden numeron sijaan.
3. Määritä **NäytäPvm**-ohjausobjektin **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateTimeValue(TuloPvmAika.Text, "fr")**
   
    ![Näyttää päivämäärä/aika-arvon ranskalaisessa muodossa](./media/show-text-dates-times/date-value-fr.png)
   
    **NäytäPvm** näyttää päivän ennen kuukautta ranskalaisen käyttäjän odottamassa muodossa.
   
   > [!TIP]
   > Saat näkyviin luettelon muista kieliasetuksista Intellisensessä poistamalla jälkimmäisen lainausmerkin ja **fr**:n kaavasta, mutta jättämällä ensimmäisen lainausmerkin:
   > 
   > ![Kieliasetusten luettelon näyttäminen](./media/show-text-dates-times/locale-list.png)
   > 
   > 
4. Jos käytät jonkin useista valmiista muodoista, vaihda **NäytäPvm-ohjausobjektin** **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**Text(DateTimeValue(TuloPvmAika.Text), DateTimeFormat.LongDateTime)**
   
    ![Näyttää päivämäärä/aika-arvon ranskalaisessa muodossa](./media/show-text-dates-times/long-date-time.png)
   
    **NäytäPvm** näyttää viikonpäivän, päivämäärän ja ajan.
   
   > [!TIP]
   > **DateTimeFormat**-parametri tukee useita muita valmiita muotoiluja. Saat tämän luettelon näkyviin poistamalla kaavasta osan **LongDateTime**.
   > 
   > 
5. Jos haluat käyttää mukautettua muotoa, vaihda **NäytäPvm**-ohjausobjektin **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**Text(DateTimeValue(TuloPvmAika.Text), "mm/dd/yyyy hh:mm:ss.fff AM/PM")**
   
    ![Näyttää päivämäärä/aika-arvon ranskalaisessa muodossa](./media/show-text-dates-times/format-milliseconds.png)
   
    **ShowDate** näyttää päivämäärä/aika-arvon määrittämässäsi muodossa, millisekunnit mukaan lukien.
   
   > [!TIP]
   > Pyöristä aika lähimpään sekunnin kymmenes- tai sadasosaan määrittämällä kaavassa **hh:mm:ss.f** tai **hh:mm:ss.ff**.
   > 
   > 

## <a name="format-a-date-by-using-datevalue"></a>Päivämäärän muotoileminen DateValuen avulla

1. Lisää **[tekstisyöte](controls/control-text-input.md)**-ohjausobjekti, jonka nimi on **TuloPvm**, ja syötä siihen sitten päivämäärä (esimerkiksi **5/10/85**).

2. Lisää **[selite](controls/control-text-box.md)**-ohjausobjekti, jonka nimi on **MuotoilePvm**, ja määritä sen **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateValue(TuloPvm.Text)**
   
    **MuotoilePvm** näyttää kirjoittamasi päivämäärän, mutta vuosi näkyy nelinumeroisena.
3. Määritä **MuotoilePvm**-ohjausobjektin**[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateValue(TuloPvm.Text, "fr")**
   
    **MuotoilePvm** näyttää päivän ennen kuukautta ranskalaisen käyttäjän odottamassa muodossa.
4. Jos haluat käyttää jotakin monista valmiista muodoista, määritä **MuotoilePvm**-ohjausobjektin**[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**Text(DateValue(TuloPvm.Text), DateTimeFormat.LongDate)**
   
    **MuotoilePvm** näyttää viikonpäivän, kuukauden, päivän ja vuoden.
5. Jos haluat käyttää mukautettua muotoa, määritä **MuotoilePvm**-ohjausobjektin **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**Text(DateValue(TuloPvm.Text), "yy/mm/dd")**
   
    **MuotoilePvm** näyttää päivämäärän määrittämässäsi muodossa.

## <a name="format-a-time-using-datetimevalue"></a>Muotoile aika käyttämällä DateTimeValue-funktiota

1. Lisää **[tekstisyöte](controls/control-text-input.md)**- ohjausobjekti, jonka nimi on **TuloAika**, ja kirjoita sitten siihen **6:15 AM**.

2. Lisää **[selite](controls/control-text-box.md)**-ohjausobjekti, jonka nimi on**NäytäAika**.

3. Jos haluat käyttää yhtä monista valmiista muodoista, määritä **NäytäAika**-ohjausobjektin**[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**Text(DateTimeValue(TuloAika.Text), DateTimeFormat.LongTime)**
   
    **NäytäAika** näyttää määrittämäsi ajan, sekunnit mukaan lukien.
4. Jos haluat käyttää mukautettua muotoa, määritä **NäytäAika**-ohjausobjektin **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**Text(DateTimeValue(TuloAika.Text), "hh:mm:ss.fff AM/PM")**
   
    **NäytäAika** näyttää määrittämäsi ajan, sekunnit ja millisekunnit mukaan lukien.
   
   > [!TIP]
   > Pyöristä aika lähimpään sekunnin kymmenes- tai sadasosaan syöttämällä kaavassa **hh:mm:ss.f** tai **hh:mm:ss.ff**.
   > 
   > 

## <a name="show-the-time-between-dates"></a>Näytä päivämäärien välinen aika

1. Lisää kaksi **[tekstisyöte](controls/control-text-input.md)**-ohjausobjektia, joiden nimet ovat **Alku** ja **Loppu**.

2. Kirjoita **4/1/2015** **Alku**-ohjausobjektiin ja **1/1/2016** **Loppu**-ohjausobjektiin.

3. Lisää **[selite](controls/control-text-box.md)**-ohjausobjekti, jonka nimi on **AikaEro**, ja aseta sen **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateDiff(DateValue(Alku.Text), DateValue(Loppu.Text))**
   
    ![Kahden päivämäärän vertailu](./media/show-text-dates-times/date-diff.png)
   
    **AikaEro** näyttää tuloksen **275**, joka on päivien määrä päivien 1. huhtikuuta 2015 ja 1. tammikuuta 2016 välillä.
4. Määritä **AikaEro**-ohjausobjektin **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:  <br>**DateDiff(DateValue(Alku.Text), DateValue(Loppu.Text), Months)**
   
    **AikaEro** näyttää tuloksen **9**, joka on kuukausien määrä päivien 1. huhtikuuta 2015 ja 1. tammikuuta 2016 välillä. Korvaa parametri **Months** parametrilla **Quarters** tai **Years** näyttääksesi ajan kuukausina, vuosineljänneksinä tai vuosina.

## <a name="identify-a-date-before-or-after-another-date"></a>Määritä päivämäärä, joka on ennen toista päivämäärää tai sen jälkeen

1. Lisää **[tekstisyöte](controls/control-text-input.md)**- ohjausobjekti, jonka nimi on **Alku**, ja kirjoita siihen **5/10/1985**.

2. Lisää **[selite](controls/control-text-box.md)**-ohjausobjekti, jonka nimi on **PvmLisää**, ja aseta sen **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateAdd(DateValue(Alku.Text), 3)**
   
    ![Lisää kolme päivää](./media/show-text-dates-times/date-add.png)
   
    **PvmLisää** näyttää tuloksen **5/13/1985**, joka on kolme päivää **Alku**-päivämäärän jälkeen.
3. Määritä **PvmLisää**-ohjausobjektin **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateAdd(DateValue(Alku.Text), -3)**
   
    ![Vähennä kolme päivää](./media/show-text-dates-times/date-subtract.png)
   
    **PvmLisää** näyttää tuloksen **5/7/1985**, joka on kolme päivää ennen **Alku**-päivämäärää.
4. Määritä **PvmLisää**-ohjausobjektin **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**DateAdd(DateValue(Alku.Text), 3, Months)**
   
    ![Lisää kolme kuukautta](./media/show-text-dates-times/date-add-months.png)
   
    Selite näyttää tuloksen **8/10/1985**, joka on kolme kuukautta **Alku**-päivämäärän jälkeen. Korvaa parametri **Months** parametrillä **Quarters** tai **Years** laskeaksesi päivämäärän, joka on tietyn määrän vuosineljänneksiä tai vuosia **Alku**-päivämäärän jälkeen.

## <a name="calculate-dates-based-on-years-months-and-days"></a>Laske päivämääriä vuosien, kuukausien ja päivien perusteella

1. Lisää kolme **[avattava luettelo](controls/control-drop-down.md)** -ohjausobjektia, joiden nimet ovat **Vuosi**, **Kuukausi** ja **Päivä**.

2. Määritä **Vuosi**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**Table({Vuosi:"2014"}, {Vuosi:"2015"}, {Vuosi:"2016"})**

3. Määritä **Kuukausi**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**Table({Kuukausi:"1"}, {Kuukausi:"2"}, {Kuukausi:"3"}, {Kuukausi:"4"}, {Kuukausi:"5"}, {Kuukausi:"6"}, {Kuukausi:"7"}, {Kuukausi:"8"}, {Kuukausi:"9"}, {Kuukausi:"10"}, {Kuukausi:"11"}, {Kuukausi:"12"})**

4. Määritä **Päivä**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**Table({Päivä:"1"}, {Päivä:"2"}, {Päivä:"3"}, {Päivä:"4"}, {Päivä:"5"}, {Päivä:"6"}, {Päivä:"7"}, {Päivä:"8"}, {Päivä:"9"}, {Päivä:"10"}, {Päivä:"11"}, {Päivä:"12"}, {Päivä:"13"}, {Päivä:"14"}, {Päivä:"15"}, {Päivä:"16"}, {Päivä:"17"}, {Päivä:"18"}, {Päivä:"19"}, {Päivä:"20"}, {Päivä:"21"}, {Päivä:"22"}, {Päivä:"23"}, {Päivä:"24"}, {Päivä:"25"}, {Päivä:"26"}, {Päivä:"27"}, {Päivä:"28"}, {Päivä:"29"}, {Päivä:"30"}, {Päivä:"31"})**

5. Lisää **[selite](controls/control-text-box.md)**-ohjausobjekti ja määritä sen **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   <br>**Text(Date(Value(Vuosi.Selected.Value), Value(Kuukausi.Selected.Value), Value(Päivä.Selected.Value)), DateTimeFormat.LongDate)**
   
    Tuloksena näkyy oletusarvoisesti **Wednesday, January 1, 2014**. Valitse eri arvoja **[avattava luettelo](controls/control-drop-down.md)** -ohjausobjekteissa muuttaaksesi päivämäärää **[selite](controls/control-text-box.md)**-ohjausobjektissa.

Joudut ehkä muuntamaan odottamattomia tietoja. Jos lisäät **[tekstisyöte](controls/control-text-input.md)**-ohjausobjekteja **[avattava luettelo](controls/control-drop-down.md)** -ohjausobjektien sijasta, käyttäjä voi kirjoittaa virheellisen päivämäärän, kuten 45. toukokuuta. **[Date](functions/function-date-time.md)**-funktio käsittelee epätavallisia tietoja seuraavilla tavoilla:

* Jos vuosiarvo on 0–1899 (nämä arvot mukaan lukien), funktio lisää kyseisen arvon lukuun 1900 vuoden laskemista varten.
* Jos vuosiarvo on 1900–9999 (nämä arvot mukaan lukien), funktio käyttää tätä arvoa vuotena.
* Jos vuosiarvo on pienempi kuin 0 tai suurempi kuin 10 000, funktio palauttaa virhearvon.
* Jos kuukauden arvo on suurempi kuin 12, funktio lisää tämän kuukausien määrän määritetyn vuoden ensimmäiseen kuukauteen.
* Jos kuukauden arvo on pienempi kuin 1, funktio vähentää tämän kuukausien määrän määritetyn vuoden ensimmäisestä kuukaudesta.
* Jos päivien arvo on suurempi kuin määritetyn kuukauden päivien määrä, funktio lisää tämän päivien määrän kuukauden ensimmäiseen päivään ja palauttaa seuraavan kuukauden vastaavan päivämäärän.
* Jos päivien määrä on alle 1, funktio vähentää tämän päivien määrän yhdellä lisättynä määritetyn kuukauden ensimmäisestä päivästä.

## <a name="calculate-times-based-on-hours-minutes-and-seconds"></a>Laske aikoja tuntien, minuuttien ja sekuntien perusteella

1. Lisää kaksi **avattava luettelo**-ohjausobjektia, joiden nimet ovat **Tunti** ja **Minuutti**.

2. Määritä **Tunti**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**Table({Tunti:"9"}, {Tunti:"10"}, {Tunti:"11"}, {Tunti:"12"}, {Tunti:"13"}, {Tunti:"14"}, {Tunti:"15"}, {Tunti:"16"}, {Tunti:"17"})**

3. Määritä **Minuutti**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**Table({Minuutti:"0"}, {Minuutti:"15"}, {Minuutti:"30"}, {Minuutti:"45"})**

4. Lisää **[selite](controls/control-text-box.md)**-ohjausobjekti ja määritä sen **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:  
   <br>**Text(Time(value(Tunti.Selected.Value), Value(Minuutti.Selected.Value), 0), DateTimeFormat.ShortTime)**

5. Valitse **15** kohdassa **Tunti** ja **45** kohdassa **Minuutti**.
   
    **[Selite](controls/control-text-box.md)**-ohjausobjekti näyttää tuloksen **3:45 PM**.
   
    Voit lisätä vaihtoehtoja kohtiin **Tunti** ja **Minuutti**, jotta käyttäjät voivat valita suuremmasta tuntimäärästä ja määrittää tarkemman minuuttimäärän. Voit myös lisätä kolmannen **[avattava luettelo](controls/control-drop-down.md)**-ohjausobjektin, jotta käyttäjät voivat määrittää sekunnit. Jos lisäät kolmannen luettelon, määritä **[selite](controls/control-text-box.md)**-ohjausobjektin **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava lauseke:<br>**Text(Time(Value(Tunti.Selected.Value), Value(Minuutti.Selected.Value), Value(Sekunti.Selected.Value)), DateTimeFormat.LongTime)**


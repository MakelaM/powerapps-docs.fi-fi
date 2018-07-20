---
title: Kehitä offline-tilassa toimivia sovelluksia | Microsoft Docs
description: Kehitä offline-tilassa toimivia sovelluksia, niin että käyttäjät voivat työskennellä tehokkaasti myös ilman verkkoyhteyttä.
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/09/2017
ms.author: mblythe
ms.openlocfilehash: cb2ed2404f7270367b3a26bf8eccb733b09fee23
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023133"
---
# <a name="develop-offline-capable-apps-with-powerapps"></a>Kehitä offline-tilassa toimivia sovelluksia PowerAppsissa
Yksi yleisimpiä mobiilisovelluksen kehittäjänä kohtaamiasi haasteita on, miten käyttäjäsi voivat olla tuottavia, kun yhteydet ovat rajallisia tai niitä ei ole lainkaan. PowerAppsissa on joukko ominaisuuksia ja toimintatapoja, joiden avulla voit kehittää offline-tilassa toimivia sovelluksia. Voit:

* Käynnistää Powerappsin mobiilisovelluksen offline-tilassa.
* Suorittaa kehittämiäsi sovelluksia offline-tilassa.
* Määrittää, onko sovellus offline-tilassa, verkossa tai käyttääkö se käytön mukaan laskutettavaa yhteyttä käyttämällä [Connection](../canvas-apps/functions/signals.md#connection)-signaaliobjektia.
* Käyttää [kokoelmia](../canvas-apps/create-update-collection.md) ja hyödyntää funktioita, kuten [LoadData ja SaveData](../canvas-apps/functions/function-savedata-loaddata.md), perustietojen tallennukseen offline-tilassa.

## <a name="how-to-build-offline-capable-apps"></a>Offline-tilassa toimivien sovellusten luominen
Ensimmäinen asia mietittäessä offline-tilanteita on se, miten sovelluksesi käsittelevät tietoja. PowerApps-sovellukset käyttävät tietoja pääasiassa käyttöympäristön, kuten SharePointin, Office 365:n ja Common Data Servicen tarjoamien [liittimien](../canvas-apps/connections-list.md) kautta. Voit myös luoda mukautettuja liittimiä, jotka antavat sovelluksille mahdollisuuden käyttää mitä tahansa palvelua, joka tarjoaa RESTful-päätepisteen. Tämä voi olla WWW-ohjelmointirajapinta tai palvelu, kuten Azure Functions. Nämä liittimet toimivat Internetin kautta HTTPS-käytännöllä, minkä vuoksi käyttäjillä on oltava Internet-yhteys, jotta he voivat käyttää palvelun tarjoamia tietoja ja ominaisuuksia.

![PowerApps-sovellus liittimineen](./media/offline-apps/online-app.png)

### <a name="handling-offline-data"></a>Offline-tietojen käsitteleminen
PowerAppsin kiinnostavimpia puolia ovat joukko ominaisuuksia ja kaavoja, jotka mahdollistavat suodatuksen, haun, lajittelun, koostamisen ja tietojen käsittelyn yhdenmukaisesti tietolähteestä riippumatta. Lähteet voivat vaihdella sovelluksen muistissa olevista kokoelmista SharePoint-luetteloihin, SQL-tietokantoihin ja Common Data Serviceen. Tämän yhdenmukaisuuden ansiosta voit helposti kohdistaa sovelluksen eri loppukäyttäjiä varten. Tärkeintä tässä on se, että tämä mahdollistaa myös paikallisten kokoelmien käyttämisen tietojen hallintaan lähes kokonaan ilman muutoksia sovelluksen logiikkaan. Itse asiassa paikalliset kokoelmat ovat ensisijainen mekanismi offline-tietojen käsittelyyn.

## <a name="building-an-offline-twitter-app"></a>Offline-tilassa toimivan Twitter-sovelluksen rakentaminen
Jotta painopisteenä voidaan pitää sovelluskehityksen offline-ominaisuuksia, näytämme yksinkertaisen Twitteriin liittyvän skenaarion. Laadimme sovelluksen, jonka avulla voit lukea Twitter-julkaisuja ja lähettää twiittejä ollessasi offline-tilassa. Kun sovellus siirtyy online-tilaan, sovellus julkaisee twiitit ja lataa paikalliset tiedot uudelleen.

Ylätasolla sovellus tekee seuraavaa:

1. Sovelluksen käynnistyksen yhteydessä (ensimmäisen näytön **OnVisible**-ominaisuuden perusteella):

   * Jos laite on yhteydessä verkkoon, käytämme Twitter-liitintä suoraan tietojen noutamiseen ja kokoelman täyttämiseen näillä tiedoilla.
   * Jos laite on offline-tilassa, lataamme tiedot paikallisesta välimuistitiedostosta käyttämällä [LoadData](../canvas-apps/functions/function-savedata-loaddata.md)-funktiota.
   * Annamme käyttäjälle mahdollisuuden lähettää twiittejä – jos laite on yhteydessä verkkoon, voimme julkaista suoraan Twitteriin ja päivittää paikallisen välimuistin.
2. 5 minuutin välein, jos laite on online-tilassa:

   * Julkaisemme kaikki paikallisessa välimuistissa olevat twiitit.
   * Päivitämme paikallisen välimuistin ja tallennamme sen [SaveData](../canvas-apps/functions/function-savedata-loaddata.md)-funktion avulla.

### <a name="step-1-create-a-new-phone-app"></a>Vaihe 1: Luo uusi puhelinsovellus
1. Avaa PowerApps Studio.
2. Napsauta tai napauta **uusi** > **tyhjä sovellus** > **puhelinasettelu**.

    ![Tyhjä sovellus, puhelinasettelu](./media/offline-apps/blank-app.png)

### <a name="step-2-add-a-twitter-connection"></a>Vaihe 2: Lisää Twitter-yhteys

1. Napsauta tai napauta **Sisältö** > **Tietolähteet** ja valitse sitten **Lisää tietolähde** **Tietolähteet**-paneelissa.

2. Napsauta tai napauta kohtaa **Uusi yhteys**, valitse **Twitter** ja napsauta tai napauta kohtaa **Luo**.

3. Anna tunnistetietosi ja luo yhteys.

    ![Twitter-yhteyden lisääminen](./media/offline-apps/twitter-connection.png)

### <a name="step-3-load-tweets-into-a-localtweets-collection-on-app-startup"></a>Vaihe 3: Lataa twiittejä LocalTweets-kokoelmaan sovelluksen käynnistyksen yhteydessä
Valitse **OnVisible**-ominaisuus **Screen1**:lle sovelluksessa ja kopioi siihen seuraava kaava:

```
If(Connection.Connected,

    ClearCollect(LocalTweets, Twitter.SearchTweet("PowerApps", {maxResults: 100}));

    UpdateContext({statusText: "Online data"})

    ,

    LoadData(LocalTweets, "Tweets", true);

    UpdateContext({statusText: "Local data"})

);

LoadData(LocalTweetsToPost, "LocalTweets", true);

SaveData(LocalTweets, "Tweets")
```

![Kaava twiittien lataamista varten](./media/offline-apps/load-tweets.png)

Tämä kaava tarkistaa, onko laite online-tilassa:

* Jos laite on online-tilassa, se lataa **LocalTweets**-kokoelmaan enintään 100 twiittiä, jotka sisältävät hakusanan ”PowerApps”.
* Jos laite on offline-tilassa, se lataa paikalliseen välimuistiin tiedoston, jonka nimi on ”Twiittejä”, jos se on saatavilla.

### <a name="step-4-add-a-gallery-and-bind-it-to-the-localtweets-collection"></a>Vaihe 4: Lisää valikoima ja sido se LocalTweets-kokoelmaan

1. Lisää uusi valikoima, jonka korkeus on joustava: **Lisää** > **Valikoima** > **Tyhjä, joustava korkeus**.

2. Määritä **Items**-ominaisuuden arvoksi **LocalTweets**.

3. Lisää neljä **selite**-ohjausobjektia kunkin twiitin tietojen näyttämiseen ja määritä **Text**-ominaisuudet:
   * **ThisItem.TweetText**
   * **ThisItem.UserDetails.FullName & " @" & ThisItem.UserDetails.UserName**
   * **"RT: " & ThisItem.RetweetCount**
   * **Text(DateTimeValue(ThisItem.CreatedAtIso), DateTimeFormat.ShortDateTime)**
4. Lisää **Image**-ohjausobjekti ja määritä **Image**-ominaisuuden arvoksi **ThisItem.UserDetails.ProfileImageUrl**.

### <a name="step-5-add-a-connection-status-label"></a>Vaihe 5: Lisää yhteyden tilan selite
Lisää uusi **Selite**-ohjausobjekti ja määritä sen **Text**-ominaisuudeksi seuraava kaava:

```
If (Connection.Connected, "Connected", "Offline")
```

Tämä kaava tarkistaa, onko laite online-tilassa. Jos näin on, selitteen tekstinä on ”Yhdistetty”, muussa tapauksessa se on ”Offline”.

### <a name="step-6-add-a-text-input-to-compose-new-tweets"></a>Vaihe 6: Lisää tekstisyöte uusien twiittien laatimista varten

1. Lisää uusi **tekstisyöte**-ohjausobjekti, jonka nimi on ”NewTweetTextInput”.

2. Määritä tekstisyötteen **Reset**-ominaisuudeksi **resetNewTweet**.

### <a name="step-7-add-a-button-to-post-the-tweet"></a>Vaihe 7: Lisää painike, jolla twiitti lähetetään
1. Lisää **Button**-ohjausobjekti ja aseta sen **Text**-ominaisuudeksi ”Tweet”.
2. Määritä sen **OnSelect**-ominaisuudeksi seuraava kaava:

    ```
    If (Connection.Connected,

        Twitter.Tweet("", {tweetText: NewTweetTextInput.Text}),

        Collect(LocalTweetsToPost, {tweetText: NewTweetTextInput.Text});

        SaveData(LocalTweetsToPost, "LocalTweetsToPost")

    );

    UpdateContext({resetNewTweet: true});

    UpdateContext({resetNewTweet: false})
    ```  

Tämä kaava tarkistaa, onko laite online-tilassa:

* Jos laite on online-tilassa, se twiittaa tekstin heti.
* Jos laite on offline-tilassa, se sieppaa twiitin **LocalTweetsToPost**-kokoelmaan ja tallentaa sen sovellukseen.

Sitten kaava palauttaa tekstiruudun tekstin.

### <a name="step-8-add-a-timer-to-check-for-tweets-every-five-minutes"></a>Vaihe 8: Lisää ajastin, joka tarkistaa twiittejä viiden minuutin välein
Lisää uusi **Timer**-ohjausobjekti:

* Määritä **Duration**-ominaisuuden arvoksi 300000.

* Määritä **Autostart**-ominaisuuden arvoksi true.

* Määritä **OnTimerEnd**in arvoksi seuraava kaava:

    ```
    If(Connection.Connected,

        ForAll(LocalTweetsToPost, Twitter.Tweet("", {tweetText: tweetText}));

        Clear(LocalTweetsToPost);

        Collect(LocalTweetsToPost, {tweetText: NewTweetTextInput.Text});

        SaveData(LocalTweetsToPost, "LocalTweetsToPost");

        UpdateContext({statusText: "Online data"})
    )
    ```

Tämä kaava tarkistaa, onko laite online-tilassa. Jos näin on, sovellus twiittaa kaikki kohteet **LocalTweetsToPost**-kokoelmasta. Sitten se tyhjentää kokoelman.

Nyt kun sovellus on valmis, tarkastetaan, miltä se näyttää, ennen kuin voimme siirtyä testaukseen. Vasemmalla sovellus on yhdistettynä, oikealla se on offline-tilassa ja yksi twiitti on valmis lähetettäväksi, kun laite on jälleen online-tilassa.

![Valmis sovellus, jossa on online- ja offline-tilat](./media/offline-apps/finished-app.png)

## <a name="testing-the-app"></a>Sovelluksen testaaminen
Seuraavien vaiheiden avulla voit testata sovellusta:

1. Suorita PowerApps mobiililaitteessa online-tilassa. Sinun on suoritettava sovellus vähintään kerran online-tilassa, jotta voit ladata sovelluksen laitteeseen.
2. Käynnistä Twitter-sovellus.
3. Huomaa, että twiittejä on ladattu ja että tilana näkyy **Yhdistetty**.
4. Sulje PowerApps kokonaan.
5. Aseta laite lentokonetilaan varmistaaksesi, että se on offline-tilassa.
6. Suorita PowerApps. Twitter-sovellus voidaan nyt suorittaa offline-tilassa, ja voit käyttää muita sovelluksia, joita olet aiemmin suorittanut tässä laitteessa online-tilassa (ts. PowerApps piilottaa sovellukset, joita ei ole vielä ladattu laitteeseen).
7. Suorita sovellus uudelleen.
8. Huomaa, että se näyttää yhteyden tilan oikein. Se on nyt **Offline**.
9. Kirjoita uusi twiitti. Se tallennetaan paikallisesti **LocalTweetsToPost**-kokoelmaan.
10. Poistu lentokonetilasta. Kun ajastin laukeaa, sovellus julkaisee twiitin.

Toivottavasti saat tästä artikkelista käsityksen, millaisia ominaisuuksia PowerAppsissa on offline-tilassa toimivien sovellusten laatimista varten. Kuten aina, anna palautetta Microsoftin [keskustelupalstalla](https://powerusers.microsoft.com/t5/PowerApps-Forum/bd-p/PowerAppsForum1) ja jaa offline-sovellusesimerkkejäsi [PowerAppsin yhteisöblogissa](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/bg-p/PowerAppsBlog).

